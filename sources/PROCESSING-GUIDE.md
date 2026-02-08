# Primary Source Processing Guide

This folder holds the pipeline for converting primary sources — scanned PDFs, text PDFs, EPUBs, and other formats — into clean, readable markdown that a research agent can engage with genuinely.

The goal is a **database of primary sources** in `processed/`, one markdown file per text, structured consistently so that any agent can read, search, and cite them without fighting format issues.

---

## Folder Structure

```
sources/
├── PROCESSING-GUIDE.md    ← you are here
├── SOURCE-REGISTRY.md     ← index of all sources, status, and notes
├── raw/                   ← original files (PDFs, EPUBs, etc.)
├── processed/             ← clean markdown output, one file per text
└── scripts/               ← Python scripts for each processing type
```

---

## Output Format (All Sources)

Every processed file in `processed/` should follow this structure:

```markdown
---
title: "The Instance of the Letter in the Unconscious, or Reason Since Freud"
author: Jacques Lacan
translator: Bruce Fink
year: 1957
source_file: raw/lacan-ecrits-fink.pdf
pages: 493–528
phase: "1.1"
---

# The Instance of the Letter in the Unconscious, or Reason Since Freud

## [Section heading if applicable]

Body text here. *Italics preserved.* Paragraph breaks preserved.

> Block quotes for extended citations within the text.

Formulas rendered as LaTeX where possible: $\frac{f(S')}{S} \cdot S \cong S(+)s$

[^1]: Footnotes collected with markdown footnote syntax.
```

### Requirements for all processed files:
- **Faithful transcription** — no paraphrasing, no summarizing, no "cleaning up" Lacan's style
- **Italics preserved** — many terms carry theoretical weight in italics
- **Footnotes preserved** — numbered continuously, collected at end of each section or chapter
- **Section breaks preserved** — use `##` headers matching the text's own divisions
- **Page numbers noted** — insert `<!-- p. 497 -->` comments at page breaks for citation
- **Unclear passages flagged** — use `[unclear: ...]` for anything the OCR or transcription is uncertain about
- **Formulas and schemas** — use LaTeX notation or ASCII art; flag with `<!-- schema -->` if complex
- **No French** — English translations only, unless a French term is used untranslated in the English text (e.g., *jouissance*, *point de capiton*)

---

## Source Types and Approaches

### Type A: Scanned PDF, Side-by-Side French/English

**Example:** Lacan, *Écrits* (Fink translation) — French on left page, English on right page.

**Pipeline:**
1. **PDF → page images** at 300 DPI using `pdf2image` (requires `poppler`)
2. **Isolate English pages** — either filter by page number (right-side pages) or crop right half of spread images
3. **Vision-based transcription** — feed each English page image to Claude with the transcription prompt (see `scripts/prompts/transcribe-page.md`)
4. **Assembly** — concatenate pages, fix cross-page sentence breaks
5. **Cleanup pass** — unify footnote numbering, add section headers, strip running headers/page numbers
6. **Spot-check** — verify key theoretical passages against the French original for transcription accuracy

**Key challenges:**
- Spread images require cropping; individual pages just need filtering
- Footnotes span page bottoms and may continue across pages
- Lacan's formulas (the algorithm of metaphor, the graph of desire) need special attention
- Some pages have schemas/diagrams that need manual description

**Chunking strategy:** Process 5–10 pages at a time. Each chunk gets its own transcription pass, then chunks are assembled.

---

### Type B: Scanned PDF, English Only

**Example:** Older academic press editions, photocopied seminar translations.

**Pipeline:**
1. **PDF → page images** at 300 DPI
2. **Vision-based transcription** — feed each page to Claude (no cropping needed)
3. **Assembly and cleanup** — same as Type A steps 4–5

**Key challenges:**
- Scan quality varies (library photocopies, margin notes, bleed-through)
- No French to spot-check against, so flag uncertain passages more aggressively

---

### Type C: Text-Selectable PDF

**Example:** Modern academic papers (Vaswani et al., Elhage et al., Templeton et al.), recent book PDFs.

**Pipeline:**
1. **Extract text directly** using `pymupdf` (fitz) or `pdfplumber`
2. **Clean extracted text** — fix line breaks, hyphenation, header/footer removal
3. **Convert to markdown** — add section headers, format equations, handle tables
4. **Verify** — compare extracted text against PDF visually for any garbled sections (especially equations and tables)

**Key challenges:**
- Equations often extract as garbled Unicode; may need vision fallback for equation-heavy pages
- Tables may not extract cleanly; use vision for those pages
- Two-column layouts (common in ML papers) need column-order reassembly

**Detection:** Try text extraction first. If the extracted text is mostly empty or garbled, fall back to Type A/B vision approach.

---

### Type D: EPUB or Digital Text

**Example:** Some translations available as EPUBs, Kindle extracts, or web-published texts.

**Pipeline:**
1. **Extract HTML/text** from EPUB using `ebooklib` or `pandoc`
2. **Convert to markdown** via `pandoc` or direct HTML-to-markdown
3. **Clean** — strip DRM artifacts, fix encoding issues, normalize formatting

**Key challenges:**
- DRM-protected files cannot be processed
- Encoding issues with special characters (diacritics, em-dashes)

---

### Type E: Very Long Sources (Books)

**Example:** Freud's *Interpretation of Dreams*, full Seminar volumes (300+ pages).

**Strategy:** Do not process the entire book. Process only the chapters/sections the research plan specifies:
- Freud: Chapter 6 ("The Dream-Work") only
- Seminar III: Key chapters on signifying chains and psychosis
- Seminar XI: Chapters on the unconscious as discourse of the Other
- Seminar XX: Chapters on *lalangue* and limits of formalization

**Pipeline:** Same as the appropriate type (A/B/C/D) above, but applied to a page range rather than the full file. Note the page range in the YAML frontmatter.

---

## Processing Order (Recommended)

Follow the reading order from Phase 1.1 of the research plan:

| Priority | Source | Type | Pages/Sections |
|----------|--------|------|----------------|
| 1 | Lacan, "Instance of the Letter" (*Écrits*) | A | pp. 493–528 |
| 2 | Lacan, "Function and Field of Speech" (*Écrits*) | A | pp. 197–268 |
| 3 | Lacan, *Seminar III: The Psychoses* | B or C | Key chapters TBD |
| 4 | Lacan, *Seminar XI: Four Fundamental Concepts* | B or C | Key chapters TBD |
| 5 | Lacan, *Seminar XX: Encore* | B or C | Key chapters TBD |
| 6 | Jakobson, "Two Aspects of Language" | B or C | Full essay (~20 pp.) |
| 7 | Saussure, *Course in General Linguistics* | B or C | Key chapters TBD |
| 8 | Freud, *Interpretation of Dreams* Ch. 6 | B or C | Ch. 6 only |

Secondary sources (Fink, Milner, Borch-Jacobsen, Laplanche) processed as needed.

Computational sources (Vaswani et al., Elhage et al., etc.) are likely Type C and should be straightforward.

---

## Scripts

Scripts live in `scripts/`. Each script should:
- Accept a source file path and output path as arguments
- Log what it's doing so processing can be resumed if interrupted
- Be idempotent — running it twice on the same input produces the same output

### Planned scripts:
- `pdf_to_images.py` — converts PDF pages to PNGs (uses pdf2image/poppler)
- `crop_spreads.py` — crops spread images to isolate right (English) pages
- `transcribe_pages.py` — sends page images to Claude API for vision transcription
- `extract_text_pdf.py` — extracts text from text-selectable PDFs
- `assemble_markdown.py` — concatenates page transcriptions into a single clean file
- `verify_transcription.py` — spot-checks key passages

### Prompts:
- `prompts/transcribe-page.md` — the prompt used for vision-based page transcription
- `prompts/cleanup-pass.md` — the prompt used for the assembly/cleanup step

---

## Dependencies

```bash
pip install pdf2image pymupdf pdfplumber Pillow anthropic
brew install poppler  # required by pdf2image on macOS
```

---

## Quality Checklist (Per Source)

Before marking a source as "processed" in the registry:

- [ ] Every page of the relevant section has been transcribed
- [ ] No paragraphs dropped (compare page count to output)
- [ ] Italics preserved where present in original
- [ ] Footnotes numbered continuously and collected properly
- [ ] Section headers match the original text's structure
- [ ] Formulas/schemas rendered or flagged
- [ ] Page-break comments inserted for citation
- [ ] Unclear passages flagged with `[unclear: ...]`
- [ ] Key theoretical passages spot-checked for accuracy
- [ ] YAML frontmatter complete
- [ ] Entry added to SOURCE-REGISTRY.md
