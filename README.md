# RadioFragile Player

A custom browser-based streaming radio player with real-time audio visualization, WebGL holographic effects, and a retro CRT terminal aesthetic. Built for [RadioFragile](https://fragilefm.webflow.io/) — an experimental electronic music archive and record label.

## Features

- **Custom Audio Player** — Web Audio API with play/pause, prev/next, seek, and block-style volume control
- **Waveform Visualization** — Real-time spike/EKG canvas that reacts to audio frequency data
- **Stereo VU Meter** — 20-band frequency analyzer with peak hold, split into L/R channels
- **WebGL Holographic Overlay** — Full-screen fresnel lens shader with chromatic aberration and scan lines
- **Audio Effects** — Real-time filter (FLTR), delay with feedback (DLY), and waveshaper distortion (CRSH)
- **Shuffle Mode** — Fisher-Yates shuffle with current-track preservation
- **Immersive Mode** — Dims UI to focus on the visualizations
- **Terminal Typewriter Marquee** — Now playing / next / prev info with character-by-character typing animation
- **CRT Aesthetic** — Scan lines, flicker, vignette, noise overlay on every panel
- **iOS Compatibility** — AudioContext workaround with synthetic frequency data fallback
- **MediaSession API** — Lock screen / notification controls on mobile
- **Responsive Design** — Optimized from desktop down to 380px
- **Smooth Scrolling Playlist** — Auto-scroll with pause on hover, thumbnail grid

## Tech Stack

- Vanilla JavaScript (no frameworks)
- Web Audio API (AnalyserNode, BiquadFilter, WaveShaper, Delay)
- WebGL (custom GLSL fragment shader)
- Canvas 2D (waveform + VU meter)
- CSS3 animations and custom properties
- Designed for Webflow CMS integration

## File Structure

```
radiofragile-player/
├── css/
│   └── radiofragile-player.css    # Full stylesheet with CRT effects & responsive
├── js/
│   └── radiofragile-player.js     # Complete player engine (V56 - HoloGL Terminal)
├── html/
│   ├── player.html                # Player HTML structure
│   └── playlist.html              # Playlist HTML structure
└── README.md
```

## Usage with Webflow

This player is designed to work with Webflow's CMS. Tracks are loaded from `img` elements with `data-filename` attributes in the page:

```html
<img src="thumbnail.jpg"
     data-filename="track.mp3"
     data-source="hostinger"
     data-folder="AUDIO"
     data-dropbox-id="optional"
     data-rlkey="optional">
```

### Integration

1. Paste the CSS into Webflow's **Custom Code > Head**
2. Add the player and playlist HTML as **Embed** elements
3. Paste the JS into Webflow's **Custom Code > Footer**

## Audio Effects

| Control | Effect | Levels |
|---------|--------|--------|
| `FLTR` | Low-pass filter | OFF → 800Hz → 2kHz → 6kHz |
| `DLY` | Delay + feedback | OFF → 150ms → 300ms → 600ms |
| `CRSH` | Waveshaper distortion | OFF → Light → Medium → Heavy |
| `SHF` | Shuffle playlist | ON / OFF |

## Version History

This project evolved through 56+ iterations, from a basic audio player to a full terminal-style radio interface with WebGL effects. Key milestones:

- **V1-V5** — Basic player with CSS styling
- **V6-V10** — Neon aesthetic, spectrum visualization
- **V11-V15** — ASCII mirror effects, responsive fixes
- **V16-V20** — WebGL ASCII, heartbeat animation, EKG display
- **V21-V25** — ASCII EKG, playlist improvements, neon updates
- **V26-V30** — Immersive mode, terminal UI redesign
- **V31-V40** — ASCII art, terminal refinements
- **V40-V55** — Terminal polish, performance optimization
- **V56** — HoloGL Terminal: WebGL holographic overlay, final version

## License

This project is open source. Feel free to use, modify, and learn from it.

## Credits

Built by [fragilefm-afk](https://github.com/fragilefm-afk) for [RadioFragile](https://fragilefm.webflow.io/)
