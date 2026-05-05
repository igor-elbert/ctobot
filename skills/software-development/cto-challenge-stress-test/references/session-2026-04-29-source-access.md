# Session reference: source access + fallback patterns (2026-04-29)

Use this note when the primary source page is inaccessible or partially blocked.

## What happened
- A Reddit thread in r/ExperiencedDevs could not be read directly because Reddit returned a human-verification / network-policy block.
- The thread URL also failed in `/.json` form from the browser tool.
- The fallback path used alternate retrieval methods and side channels:
  - browser navigation to confirm block status
  - terminal requests to confirm the 403
  - DuckDuckGo search for related Reddit titles and nearby threads
  - PullPush Reddit search to recover nearby / related submissions and infer the likely question family

## Lessons
1. If the source page is blocked, do not guess the missing content.
2. Try alternate retrievals before giving up:
   - `browser_navigate`
   - `browser_console`
   - terminal `requests`
   - search engines
   - third-party Reddit mirrors / archives / APIs when available
3. If the exact thread text is unavailable, answer at the theme level and say so explicitly.
4. For opinion/value questions, it is acceptable to respond with a grounded synthesis even if the thread itself cannot be fully extracted.

## Useful phrasing
- "I couldn’t reliably read the thread itself because Reddit blocked direct access, so I’m answering the underlying question at the theme level."
- "I reconstructed the likely question family from nearby accessible sources rather than pretending exact recall."
