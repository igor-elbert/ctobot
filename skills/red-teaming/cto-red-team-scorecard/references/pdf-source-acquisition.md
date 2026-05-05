# PDF source acquisition for CTO red-teaming

Use this when the source is a PDF and the direct web fetch is flaky or blocked.

## Reliable fallback sequence
1. Try the direct URL with a normal browser / download.
2. If that fails, ask the user for a local copy or upload.
3. If the PDF exists locally, open it with `file:///absolute/path/to.pdf` in the browser viewer.
4. Use the viewer thumbnail sidebar and page-number box to move page by page.
5. When text extraction tools are unavailable, use visual page reads (browser vision) to read the rendered page.

## What worked in this session
- Remote McKinsey PDF fetch failed with HTTP/2 / protocol errors.
- The user placed the PDF in `~/Downloads`.
- Opening `file:///Users/<user>/Downloads/<name>.pdf` in the browser viewer succeeded.
- The browser viewer exposed page thumbnails and page navigation even when command-line PDF tools were unavailable.
- Page-level facts were recoverable with browser vision on visible pages.

## Pitfalls
- A blank or dark page in the screenshot can mean the viewer has not fully rendered yet; confirm the page number in the viewer before concluding the PDF is empty.
- Search engines may trigger bot challenges; do not spend too long on them if the user can provide the source locally.
- If the page shown is not the requested page, jump using the page-number input rather than cycling thumbnails blindly.

## Good practice
- Record only the practical source-acquisition workaround, not the whole document content.
- Keep the scorecard focused on the leadership challenge; use the PDF workaround only to get the source text.