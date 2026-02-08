# Prompt: Verify Key Passage

Used for spot-checking critical theoretical passages where transcription accuracy is essential.

---

## User Prompt

I am going to show you two things:

1. An image of a page from a scanned academic text
2. A markdown transcription of that page

Compare them carefully. Report:

- **Missing text:** Any sentences or phrases visible in the image that are absent from the transcription.
- **Added text:** Any text in the transcription that does not appear in the image.
- **Altered wording:** Any place where the transcription uses different words than the original.
- **Missed italics:** Any text that is italicized in the image but not marked as italic in the transcription (or vice versa).
- **Footnote errors:** Mismatched footnote numbers, missing footnotes, or incorrectly transcribed footnote text.
- **Formula errors:** Any mathematical notation or schema that was transcribed incorrectly.

If the transcription is perfect, say: "Verified: no discrepancies found."

If there are errors, list each one with:
- The location (paragraph number or nearby text)
- What the image shows
- What the transcription says
- The correction needed
