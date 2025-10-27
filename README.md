# 🌅 Auto Night Mode by Sunrise/Sunset

Automatically switch between **day** and **night** themes on your website using the **real sunrise and sunset times** for the user’s location.

This project detects the user’s location via the browser’s Geolocation API, fetches sunrise/sunset times from the [Sunrise–Sunset API](https://sunrise-sunset.org/api), and adjusts your site’s theme accordingly. It also supports a manual toggle with local preference storage.

---

## ✨ Features

* 🌞 **Automatic light/dark mode** based on real local sunrise/sunset
* 📍 Uses browser **geolocation** (with fallback to local time if unavailable)
* 💾 **Remembers user preference** in `localStorage`
* 🌓 Smooth **animated transition** between themes
* 🔧 **Fully client-side**, no backend required

---

## 🧠 How It Works

1. The script gets the user’s latitude and longitude using `navigator.geolocation`.
2. It sends a request to the Sunrise–Sunset API:

   ```
   https://api.sunrise-sunset.org/json?lat={LAT}&lng={LNG}&formatted=0
   ```
3. It receives sunrise and sunset times in UTC.
4. It compares those times with the current UTC time and toggles `.night-mode` accordingly.
5. If geolocation or the API fails, it falls back to a simple rule (night = 7 PM – 7 AM).

---

## 💻 Demo

You can try it by opening the included `index.html` file in your browser.
The background and text color will automatically switch based on your local sunrise and sunset times.

---

## 📂 File Structure

```
auto-night-mode/
├── index.html     # Complete working example
└── README.md      # Project documentation
```

---

## ⚙️ Installation & Usage

1. Clone or download this repository:

   ```bash
   git clone https://github.com/yourusername/auto-night-mode.git
   ```
2. Open `index.html` in your browser — no build step or server required.
3. Allow location access when prompted.
4. Optionally, customize the CSS inside `<style>` to fit your website design.

---

## 🌗 Manual Theme Toggle

A simple button lets users manually switch between modes.
Their choice is saved in `localStorage` and overrides auto-detection on future visits.

```html
<button id="theme-toggle">Toggle Theme</button>
```

---

## 🔒 Privacy Note

The geolocation is only used locally in the browser.
Coordinates are **not stored or sent anywhere** except to the public Sunrise–Sunset API, which receives only latitude and longitude—no personal identifiers.

---

## 🧩 API Reference

* **Sunrise–Sunset API:**
  [https://sunrise-sunset.org/api](https://sunrise-sunset.org/api)

Example response:

```json
{
  "results": {
    "sunrise": "2025-10-27T05:50:00+00:00",
    "sunset": "2025-10-27T17:30:00+00:00",
    ...
  },
  "status": "OK"
}
```

---

## 💡 Credits

Created by [Zlatan Salkic](https://github.com/zlatsal)
