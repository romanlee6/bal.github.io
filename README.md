# BAL project page

Project page for *Bayesian Active Learning for Intent Disambiguation in Interactive Robot Planning* (CoRL 2026).
Served by GitHub Pages from the `main` branch root.

## Adding videos
- Overview video: upload to YouTube, replace `VIDEO_ID` in `index.html`.
- Demo clips: put `demo_school.mp4`, `demo_factory.mp4`, `demo_panda.mp4`, `demo_city.mp4` in `static/videos/`
  (H.264, ≤1080p, <10 MB each: `ffmpeg -i in.mov -vf scale=-2:720 -c:v libx264 -crf 26 -an out.mp4`).
- Optional teaser: `static/videos/teaser.mp4`, then swap the teaser `<img>` for the commented `<video>` block.

Template: [Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template) (CC BY-SA 4.0).
