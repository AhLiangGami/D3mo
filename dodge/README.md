# Meteor Dodge

A small arcade game in a single HTML file. It has no build step and no dependencies apart from Google Fonts, which have fallbacks.

## Play

Open `dodge/index.html` in any browser, or serve the folder:

```sh
python3 -m http.server -d dodge 8000   # then visit http://localhost:8000
```

## Controls

- **← / →** or **A / D** to steer
- **Move the mouse** (no click needed) or **drag with touch** to steer
- **Space / Enter** or the button to launch

Meteors spawn faster and fall faster the longer you survive. Your best time is saved in your browser's localStorage.

## Tweak it

The difficulty curve is two one-liners in `index.html`:

```js
const spawnInterval = t => Math.max(0.12, 0.7 - t * 0.018);
const fallSpeed = t => 140 + t * 9;
```

`t` is seconds survived. `spawnInterval` is the delay in seconds between meteors, and it never drops below 0.12. `fallSpeed` is the base fall speed in pixels per second, and each meteor randomly varies from it by ±25%.
