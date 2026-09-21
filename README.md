Interactive Animated Heart

A lightweight, zero-dependency, pure front-end romantic web experience. It features 100 floating love phrases moving along mathematical parametric curves to trace out an animated heart, an automatic 13-color theme cycle every 3 seconds, and a centerpiece typewriter animation.

---

## ✨ Features

- **Mathematical Parametric Heart:** 100 independent floating phrases orbiting along coordinated horizontal and vertical CSS keyframe trajectories to form a heart silhouette.
- **Centerpiece Typewriter Effect:** An elegant, loop-based typewriter animation with a soft blinking cursor, positioned in the visual center of the heart.
- **Dynamic 13-Color Palette Transitions:** Seamlessly transitions between 13 romantic hues every 3 seconds with a smooth 1-second ease.
- **Crisp & Clean Aesthetic:** Pure solid-color typography rendered over a true black background (`#000`) without blur or visual clutter.
- **Zero Dependencies:** Built entirely with standard HTML5, CSS3, and vanilla JavaScript. No external libraries, build steps, or frameworks required.
- **Cross-Platform Compatibility:** Responsive and lightweight across desktop, tablet, and mobile browsers.

---

## 🎨 Color Palette Cycle

The project cycles through 13 curated romantic colors every 3 seconds:

| # | Color Name | Hex Code | Visual Preview |
|---|------------|----------|----------------|
| 1 | Rose Pink | `#ea80b0` | <img src="https://via.placeholder.com/15/ea80b0/000000?text=+" width="15" height="15"/> `#ea80b0` |
| 2 | Deep Red | `#ff3366` | <img src="https://via.placeholder.com/15/ff3366/000000?text=+" width="15" height="15"/> `#ff3366` |
| 3 | Violet / Purple | `#b388ff` | <img src="https://via.placeholder.com/15/b388ff/000000?text=+" width="15" height="15"/> `#b388ff` |
| 4 | Sky Blue | `#00d2ff` | <img src="https://via.placeholder.com/15/00d2ff/000000?text=+" width="15" height="15"/> `#00d2ff` |
| 5 | Gold | `#ffd700` | <img src="https://via.placeholder.com/15/ffd700/000000?text=+" width="15" height="15"/> `#ffd700` |
| 6 | Coral | `#ff6b81` | <img src="https://via.placeholder.com/15/ff6b81/000000?text=+" width="15" height="15"/> `#ff6b81` |
| 7 | Fresh Green | `#2ed573` | <img src="https://via.placeholder.com/15/2ed573/000000?text=+" width="15" height="15"/> `#2ed573` |
| 8 | Pure White | `#ffffff` | <img src="https://via.placeholder.com/15/ffffff/000000?text=+" width="15" height="15"/> `#ffffff` |
| 9 | Hot Magenta | `#ff007f` | <img src="https://via.placeholder.com/15/ff007f/000000?text=+" width="15" height="15"/> `#ff007f` |
| 10 | Warm Amber | `#ff9f43` | <img src="https://via.placeholder.com/15/ff9f43/000000?text=+" width="15" height="15"/> `#ff9f43` |
| 11 | Bright Turquoise | `#00f5d4` | <img src="https://via.placeholder.com/15/00f5d4/000000?text=+" width="15" height="15"/> `#00f5d4` |
| 12 | Soft Lilac Pink | `#f368e0` | <img src="https://via.placeholder.com/15/f368e0/000000?text=+" width="15" height="15"/> `#f368e0` |
| 13 | Royal Blue | `#54a0ff` | <img src="https://via.placeholder.com/15/54a0ff/000000?text=+" width="15" height="15"/> `#54a0ff` |

---

## 📁 Project Structure

```text
HEART V3/
│
├── Love You Heart/
│   └── index.html        # Complete self-contained animation file
└── README.md             # Project documentation
```

---

## 🚀 Getting Started

### 1. Direct Execution
Simply locate `index.html` inside the `Love You Heart/` directory and open it with any modern web browser:
- Google Chrome
- Mozilla Firefox
- Apple Safari
- Microsoft Edge

### 2. Local Development Server
To serve it locally over HTTP:
```bash
# Using Python 3:
cd "Love You Heart"
python -m http.server 8000
```
Then navigate to `http://localhost:8000` in your web browser.

---

## ⚙️ Customization Guide

All logic and styling are consolidated directly within `index.html`.

### 1. Changing the Centerpiece Name
Open `index.html` and locate the typewriter configuration script around line 170:
```javascript
// Set your desired name or message:
const targetName = "Your Custom Name";
```

### 2. Adjusting the Color Transition Speed
To change how frequently colors switch, update the interval timing (default: `3000` ms / 3 seconds):
```javascript
setInterval(() => {
  colorIndex = (colorIndex + 1) % colors.length;
  document.documentElement.style.setProperty('--heart-color', colors[colorIndex]);
}, 3000); // Adjust milliseconds here
```

### 3. Modifying Orbiting Heart Text
To alter the text forming the heart outline, update line 138:
```javascript
word.textContent = 'I love you'; // Change to any preferred phrase or nickname
```

### 4. Customizing Color Themes
Add, remove, or modify hex color strings within the `colors` array:
```javascript
const colors = [
  '#ea80b0',
  '#ff3366',
  '#b388ff',
  // Add your custom hex codes here
];
```

---

## 🔬 Technical Details

- **CSS Variables & Runtime Updates:** Dynamic themes leverage the `--heart-color` CSS custom property on the root document element. Updating this property synchronously recolors both the typewriter centerpiece and all orbiting text instances.
- **Phase-Shifted CSS Animations:** Each phrase calculates its individual timeline offset using `calc(var(--i) * -300ms)`. This distributes the 100 elements evenly across the parametric curve.
- **Hardware-Accelerated Transforms:** Uses `transform: translateX(...)` and `translateY(...)` to ensure smooth 60 FPS rendering on mobile devices and low-power hardware.

---

## 📄 License

This project is open-source and free to use under the [MIT License](LICENSE).
