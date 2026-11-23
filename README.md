# Odak

Arabic / English product page for a study-planner app aimed at university students in the Gulf, with the app running inside the phone mockup.

**Live demo:** https://mohamed-yehia-ismail.github.io/odak-app/

## Features

- Working focus timer (25 / 5 / 15) with sessions, course selection and a demo-speed switch
- Exam countdown and task list inside the phone, saved in localStorage
- Weekly stats with per-course breakdown and streak
- Exam-mode widget that plans backwards from the exam date and reserves revision days
- Focus sounds (rain, brown noise, quiet room) generated live with the Web Audio API
- 20-week heatmap, pricing in SAR with a monthly / yearly toggle and a university-email discount, changelog and FAQ

## Engineering notes

- The timer stores an end timestamp instead of counting ticks, so it stays exact when the tab sleeps.
- Noise buffers are synthesized, filtered with BiquadFilters and visualised with an AnalyserNode.
- Full right-to-left layout using CSS logical properties; dates localised with Intl.

## Performance and scale

The site is a single static file: no server, no database, no build step. Every visitor's browser does its own work, so traffic only reaches the CDN that serves the file (GitHub Pages), which is built for very high traffic. Orders and bookings go straight to WhatsApp, so there is no backend that can fail under load. Fonts load with `display=swap`, and state is kept in `localStorage` with safe fallbacks.

## Tech

HTML5, CSS3 (custom properties, grid, logical properties for RTL), vanilla JavaScript, inline SVG. No frameworks. Fonts from Google Fonts.

## Run locally

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

This is a demo project for my portfolio; the business, people and prices are fictional.

## Author

Mohamed Yehia · [GitHub](https://github.com/Mohamed-Yehia-ismail) · [LinkedIn](https://www.linkedin.com/in/mohamed-yehia-ismail)
