# Unraid Glass

A custom CSS theme for the Unraid web UI with a rounded glass aesthetic.

![Dashboard Light](screenshot-dashboard.png)

---

## Features

- **Glass panels** — frosted tile surfaces with backdrop blur and specular edge lighting
- **Custom background** — fixed wallpaper image with parallax-style glass overlay
- **Apple color palette** — system green, blue, orange, red, teal throughout
- **Pill buttons & tabs** — rounded controls on every form, dialog, and nav element
- **Themed navigation** — floating frosted nav tiles with active/hover states
- **Light & dark mode** — full support for both via `prefers-color-scheme`
- **Mobile responsive** — stacked nav tiles, adaptive layouts for small screens

---

## Dependencies

### Required

| Plugin | Purpose |
|--------|---------|
| [Custom.CSS](https://github.com/WuSiYu/unraid-custom-css) | Injects the CSS and hosts the background image |

Install **Custom.CSS** via Community Applications (search `Custom WebUI CSS`).

## Installation

### 1. Install the Custom.CSS plugin

Search for **Custom WebUI CSS** in Community Applications and install it.

### 2. Set the Dynamix color theme to Black

**Main menu → Settings → Display Settings → Color theme → Black**

This is required. The glass overlay assumes a dark base (other color themes will conflict with the CSS).

### 3. Add a background image

Place your wallpaper at:

```
/boot/config/plugins/custom.css/assets/bg.jpg
```

Any image works. Landscape photos or abstract gradients look best. Falls back to a dark navy `#152843` base background color).

### 4. Apply the CSS

**Main menu → Settings → Custom WebUI CSS**

Paste the full contents of `unraid-glass.css` into the Global CSS box, then click **Apply**.

### 5. Reload the Unraid web UI

Hard-refresh your browser (`Cmd+Shift+R` / `Ctrl+Shift+R`) to clear the stylesheet cache.

---

## Customization

All colors and surface values are CSS variables defined at the top of the file under `:root`. You can override any of them without touching the rest of the stylesheet.

### Key variables

```css
:root {
  --custom-theme-accent:          #f97316;  /* orange accent */
  --custom-theme-nav-line:        #30D158;  /* green active indicator */
  --custom-dashboard-tile-bg:     rgba(200, 200, 200, 0.12);
  --custom-dashboard-tile-blur:   20px;
  --custom-dashboard-tile-radius: 18px;
}
```

### Light mode

Light mode overrides are in the `@media (prefers-color-scheme: light)` block. The theme switches automatically based on your OS or browser preference.

---

## Compatibility

Tested on **Unraid 7.x** with Chrome/Chromium-based browsers. Firefox is supported but `backdrop-filter` blur rendering may differ slightly on older versions.

---

## License

MIT
