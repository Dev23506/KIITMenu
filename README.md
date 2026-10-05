 # Hostel Food Menu — KIIT

[![PWA Ready](https://img.shields.io/badge/PWA-Ready-blue.svg)](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v3.0-38B2AC?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Pure Vanilla JS](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A lightweight, ultra-fast, and responsive web application designed for KIIT University students to check their daily mess timetable with zero friction. No more scouring WhatsApp groups for blurry menu images — get instant, real-time meal updates directly on your device.

---

## Features

- **Smart Real-Time Meal Tracker ("Overview")**: Automatically determines whether it is currently Breakfast, Lunch, Snacks, or Dinner based on your local system time, highlighting ongoing meals and switching to tomorrow morning's breakfast late at night.
- **Multiple View Modes**:
  - **Overview**: Displays the current or immediately upcoming meal only.
  - **Today**: Provides an organized grid of all 4 meals for the current day.
  - **All**: Browse through any specific day of the week (Monday through Sunday).
- **Multi-Hostel Support**:
  - **KP-7 (ABCDEF)** (W.E.F. August 2026)
  - **QC 18 (Queens' Castle)** (W.E.F. September 2026)
  - **QC 8 (Queens' Castle)** (W.E.F. August 2026)
  - Fallback placeholder ("Cooking your menu...") for hostels awaiting timetable uploads.
  - Remembers your selected hostel in `localStorage` across visits.
- **Triple Theme Switcher**:
  -  **Light Mode**
  - **Dark Mode**
  - **AMOLED True Black Mode** (`#000000` background for maximum battery savings on OLED displays).
- **Progressive Web App (PWA)**:
  - Installable directly to your Home Screen on Android, iOS, Windows, macOS, and Linux.
  - Offline-capable using an embedded Service Worker.
  - Native iOS installation guide modal included.
- **Detailed Nutritional & Mess Guidelines**: Displays veg/non-veg splits, healthy boiled vegetable alternatives, desserts, and official portion quotas (chicken, fish, eggs, etc.).
- **Zero-Dependency Single-File App**: Everything (HTML, Tailwind configuration, SVG icons, scripts, manifest, and service worker) lives inside `index.html`.

---

## Mess Schedule Timings

| Meal | Time Window |
| :--- | :--- |
| **Breakfast** | `07:00 AM – 10:00 AM` |
| **Lunch** | `01:00 PM – 03:00 PM` |
| **Evening Snacks** | `06:00 PM – 07:00 PM` |
| **Dinner** | `08:00 PM – 10:00 PM` |

---

## How to Install as an App (PWA)

### On Android (Chrome, Brave, Edge)
1. Open the hosted website URL on your mobile browser.
2. An **Install App** button will appear in the top-right corner.
3. Click it and confirm to add it to your app drawer and home screen.

### On iOS (Safari)
1. Open the site in **Safari**.
2. Tap the **Share** button (box with an upward arrow at the bottom).
3. Scroll down and tap **"Add to Home Screen"**.
4. Tap **Add** in the top-right corner.

---

## Adding or Modifying a Hostel Menu

To update or add menus, open `index.html` and look for the `hostelMenus` JavaScript object around line 170:

```javascript
const hostelMenus = {
    "KP-7 (ABCDEF)": {
        name: "KP-7 (ABCDEF)",
        wef: "W.E.F. 24.08.2026 • KP-7 (ABCDEF)",
        notes: [
            "<strong>Applicable Quantities:</strong> Banana (1 pc), Egg (2 pcs)...",
            "<strong>Sick Boarders:</strong> Khichdi / Mix Boiled Vegetables..."
        ],
        menu: {
            "Monday": {
                breakfast: { options: "...", common: "..." },
                lunch: { common: "...", veg: "...", nonVeg: "...", healthy: "..." },
                snacks: { main: "..." },
                dinner: { common: "...", veg: "...", dessert: "...", nonVeg: "..." }
            },
            // ... Tuesday through Sunday
        }
    },
    // Add your hostel here!
};
```

Then add your hostel's name to the dropdown menu inside `<div id="dropdownContent">`.

---

## Contributing

Contributions are welcome! If you have the mess timetable for other KIIT hostels (e.g., KP-6, KP-14, KP-15, QC-4, QC-12, QC-14, etc.):

1. Fork the Project.
2. Create a Feature Branch (`git checkout -b feature/Add-KP14-Menu`).
3. Commit your changes (`git commit -m 'Add timetable for KP-14'`).
4. Push to the branch (`git push origin feature/Add-KP14-Menu`).
5. Open a Pull Request.

---

## Live Demo & Deployment

Because this project is a standalone single file, deploying it takes less than 30 seconds:

### Deploying to GitHub Pages (Recommended)

1. Fork or push this repository to GitHub.
2. Go to your repository **Settings** tab.
3. Scroll down on the left navigation to **Pages** (under the "Code and automation" section).
4. Under **Build and deployment > Branch**:
   - Select branch: `main` (or `master`).
   - Select folder: `/ (root)`.
   - Click **Save**.
5. Your website will be live at `https://<your-username>.github.io/<repo-name>/` in 1–2 minutes!

---

## License

Free to use, modify and distribute.

---

<p align="center">Made with 🩵 for KIITians</p>
