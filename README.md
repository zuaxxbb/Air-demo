# Meridian Air — Booking Verification (Demo)

A single self-contained `index.html` — glassmorphism-free, "flight-deck" themed airline
booking verification portal, built as a portfolio/design demo. **All passenger and
booking data is fictional.**

## Run locally
Just open `index.html` in a browser — no build step, no server required.

## Deploy
Upload `index.html` to any static host (GitHub Pages, Netlify, Vercel, S3, etc.) and
you'll get a public URL, e.g. `https://yourname.github.io/meridian-demo/`.

## The QR code
The QR codes on the page currently point to a placeholder URL:
`https://meridianair.example/verify/XZ7Q2K`

Once deployed, open `index.html` and update this line near the bottom of the file:

```js
const verifyUrl = `https://meridianair.example/verify/${booking.pnr}`;
```

Replace it with your real deployed URL, then reload — both QR codes (on the boarding
pass stub and in the "scan me" card) regenerate automatically from that value.

## Editing the sample data
All fields live in one place, near the bottom of `index.html`:

```js
const booking = {
  pnr: "XZ7Q2K",
  flight: "MQ 482",
  passenger: "DOE/JOHN MR",
  date: "2026-08-15",
  departureTime: "14:15",
  seat: "14C"
};
```

Changing these updates the QR payload, the countdown timer, and the download file.
The rest of the visible fields (airports, terminal, gate, class, baggage, etc.) are
plain HTML in the `<section id="pass">` and `<section>` details grid — edit the text
directly there.

## Notes
- Everything (HTML/CSS/JS) lives in the one `index.html` file for simplicity.
- Fonts load from Google Fonts; the QR library loads from a CDN — both need internet
  access in the browser viewing the page.
- This is a demo/portfolio piece with placeholder data, not a real booking system.
