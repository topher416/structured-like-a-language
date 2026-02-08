# Prompt: Assembly and Cleanup Pass

Used by `assemble_markdown.py` after individual pages have been transcribed. This prompt handles the second pass that turns concatenated page transcriptions into a single coherent document.

---

## User Prompt

You are assembling individually transcribed pages of an academic text into a single clean markdown document. The pages have already been transcribed faithfully. Your job is to clean up the seams between pages without altering the content.

Do the following:

1. **Fix cross-page breaks:** Where a sentence is split across two pages (the first page ends mid-sentence, the next page begins mid-sentence), join them into a single paragraph. Remove any duplicate words at the boundary.

2. **Fix hyphenation:** Where a word is hyphenated across a page break (e.g., "uncon-" at the end of one page and "scious" at the start of the next), rejoin it as a single word.

3. **Unify footnote numbering:** The original transcriptions have per-page footnote numbers. Renumber all footnotes sequentially from 1 across the entire document. Update both the in-text markers (`[^N]`) and the footnote definitions.

4. **Remove duplicate headers:** If a running header (title, author name) was accidentally included despite instructions, remove it.

5. **Insert page break comments:** At each point where a new page begins in the original, insert a comment: `<!-- p. [number] -->` (if page numbers are known) or `<!-- page break -->` (if not).

6. **Preserve everything else:** Do not change wording, do not fix perceived errors in the original text, do not add interpretation. If a passage seems garbled, leave it as-is — it may reflect the original or may need human review.

7. **Add YAML frontmatter** at the top of the document:
   ```yaml
   ---
   title: "[Title of the text]"
   author: "[Author]"
   translator: "[Translator, if applicable]"
   year: [year of original publication]
   source_file: "raw/[filename]"
   pages: "[page range processed]"
   phase: "[which research phase this source belongs to]"
   ---
   ```

Return the complete assembled document.
