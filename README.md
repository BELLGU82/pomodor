# Pomodor — Neumorphic Pomodoro Timer with YouTube Playlist

> A minimalist Pomodoro timer in Hebrew (RTL) with a neumorphic design, automatic work/break switching, break recommendations, editable task names, and a dedicated YouTube playlist player.
> 

### ✨ Features

- **Circular countdown timer** with large display and document title updates.
- **Preset modes**: Sprint (30/5), Focus (60/15), Deep (90/25).
- **Music for focus**: Widget that embeds a YouTube playlist (`videoseries?list=PLDhuj9rNT6pkbPaMSKxIcbETHyI0Ofn5X`) on click.
- **Break recommendations**: Modal with curated links depending on break length (5/15/25 min).
- **Controls**: Play/pause, reset with confirmation, and settings modal.
- **Clock**: Local time display in 24‑hour format (`he-IL`).
- **RTL support** with Hebrew labels.
- **Editable task name** directly in the header.
- **Notification sound** at the end of each mode.

### 🧱 Stack & Technical Notes

- Single file: **HTML + CSS + Vanilla JS** (no framework).
- Font: Inter, Icons: Boxicons.
- Design: Neumorphism with soft shadows, rounded cards, recessed/raised buttons.
- Accessibility: YouTube iframe with `allow="autoplay; encrypted-media"`.

### 🚀 Quickstart

```
# Save the file as index.html and open in browser
open index.html  # macOS
# or drag the file into your browser window
```

### 🧩 Possible Extensions

- Change the `playlistID` to your own curated playlist.
- Add circular SVG/CSS progress animation around the timer.
- Persist settings/mode in LocalStorage.
- Keyboard shortcuts: Space to play/pause, R to reset.

### 📄 Structure

```
.neumorphism-card
  ├─ .header (time, task name, settings button)
  ├─ .main-content
  │   ├─ .timer-container > #timer-display
  │   └─ .right-panel
  │       ├─ .music-widget (iframe on click)
  │       └─ .main-controls (reset/play-pause)
  └─ modals: #settings-modal, #recommendation-modal
```

### 🛡️ Privacy / User Notice

- Embedding YouTube means metadata is shared with YouTube when loading/playing.
- **Custom playlist:** If you want to use your own playlist, open the code and replace the `playlistID` variable inside the `embedPlaylist()` function with your preferred YouTube playlist ID. For example:

```
function embedPlaylist() {
  if (isPlayerEmbedded) return;
  isPlayerEmbedded = true;
  // 🔽 Change this line to your playlist
  const playlistID = "YOUR_PLAYLIST_ID";
  const iframeSrc = `https://www.youtube.com/embed/videoseries?list=${playlistID}&autoplay=1`;
  musicWidget.innerHTML = `<iframe src="${iframeSrc}" style="width:100%; height:100%; border:0; border-radius: 25px;" allow="autoplay; encrypted-media" allowfullscreen></iframe>`;
  musicWidget.classList.add('player-embedded');
}
```

This will switch the embedded player to your custom playlist.

### 📜 License

MIT © 2025 Bell
