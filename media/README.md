# Media

Drop files here with these exact names and the site picks them up automatically —
no HTML edits needed. Until a file exists, the page shows a labeled empty slot.

| File | Where it appears | Notes |
|---|---|---|
| `headshot.jpg` | Hero, top right | Square crop, ≥ 600×600 px. |
| `mitospace.mp4` (or `.webm`) | Selected work → MitoSpace | H.264 MP4 (or VP9 WebM), muted, loops. 4:3 or square looks best; ≤ 10 MB keeps the page fast. |
| `readdy-cell.mp4` | Selected work → ReaDDy Cell | same |
| `mitotnt.mp4` | Selected work → MitoTNT | same |
| `livelattice.mp4` | Selected work → LiveLattice | same |
| `mitospace.jpg`, `readdy-cell.jpg`, `mitotnt.jpg`, `livelattice.jpg` | Poster frames shown before each video loads | Optional. |
| `full/mitospace.mp4`, `full/readdy-cell.mp4`, `full/mitotnt.mp4`, `full/livelattice.mp4` | Opened by the "Full size" button on each card (or by clicking the video) | Optional. Higher resolution (up to 1080p), no audio. If a file is missing the button falls back to the small card video. |
| `life-snowboarding.jpg`, `life-scuba.jpg`, `life-cats.jpg`, `life-cs2.jpg` | Outside the lab → photo grid | Cropped to 4:3 already. Shown without captions. |

To make a small, web-friendly MP4 from a screen recording or a GIF:

```bash
ffmpeg -i input.mov -an -vf "scale=960:-2,fps=24" -c:v libx264 -crf 26 -pix_fmt yuv420p -movflags +faststart mitospace.mp4
```

Videos autoplay muted (like a GIF) except for visitors who have "reduce motion"
enabled, who get play controls instead.
