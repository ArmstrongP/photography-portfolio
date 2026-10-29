# Portfolio Redesign Brief — armstrongpeterson.com

This is a ground-up rebuild. Do not reuse the old site's code or structure
(inconsistent /dist and /src paths, hand-numbered photo-XX.jpg files, broken on mobile).

## Purpose
Personal showcase of all my photography (landscape, portraits, couples,
graduation) in one stream. Photos only, no video.

## Feel
Minimal white gallery. Photos are the whole experience:
generous white space, quiet typography, almost no visible UI.

## Layout (references: jamespopsys.com, snapsbyfox.com)
- Header: my name as a simple wordmark, plus small links to About and Contact
- Home: one continuous vertical stream, one centered column on white,
  consistent spacing between photos
- Tap any photo: opens a full-screen viewer, swipe left/right for next or
  previous, tap or swipe down to close
- Footer: small Instagram link and email
- Pages: Home (stream), About, Contact
- Domain stays armstrongpeterson.com

## Mobile first
- Designed for phones first; each image fills the screen width
- Desktop: same single column, centered, images sized to the viewport
- Fast load on mobile is a hard requirement: lazy loading, responsive
  image sizes, modern formats (AVIF/WebP with JPEG fallback)
- No captions or EXIF shown

## Adding photos (top priority)
- photos/pinned/  → shown first, in filename order (01-, 02-, 03-)
- photos/stream/  → everything else, newest first by capture date (EXIF)
- If a photo has no capture date, fall back to file modified date
- To add a photo: drop the full-size export in stream/, commit, push. That's it.
- To pin or unpin: move it between the two folders
- Build step auto-resizes, converts formats, and regenerates the stream
- Never require hand-editing HTML to add or remove a photo

## Tech
- Static site, deployed to Cloudflare from GitHub (main branch = production)
- Build the redesign on a separate branch and use Cloudflare preview URLs
- Keep dependencies minimal; explain any build tool you choose before adding it

## Working style
- Ask before making big structural decisions
- Work in small steps and commit after each working step
