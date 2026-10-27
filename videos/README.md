# Videos — file conventions (AAA builds)

Videos are hosted as **separate files** in this folder and referenced by
relative URL from `index.html` (e.g. `videos/trailer.mp4`). **Never**
base64-inline a video into the HTML — it would blow GitHub's 100 MB
per-file limit.

Naming for later batches (per-case intro videos, suspect videos):

- `trailer.mp4` — the game trailer, played from the home screen.
- `case-XX-intro.mp4` — cinematic intro video for case XX (01–32).
- `case-XX-suspect-<suspect-id>.mp4` — suspect interrogation video, the
  suspect speaking. Suspect IDs match the case data (e.g. `case-01-suspect-sofia-reyes.mp4`).

Player component: the reusable `aaaVideoPlayer(videoEl, playBtn, muteBtn, noteEl)`
helper in `index.html` wires play + mute for any video; reuse it for new
players instead of writing a second one. If a video file is missing, the
player hides its card (error handler) instead of breaking the page.

Keep each video small (720p, ~10s, a few MB). The whole repo tree must stay
well under GitHub's limits; the HTML file itself is already ~29 MB.
