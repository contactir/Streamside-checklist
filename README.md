# Streamside Checklist — Full App (Auto Email + All Rules)

This is the complete, touch‑friendly checklist with **all house rules** and **automatic email sending** (via EmailJS).

## Host on GitHub Pages
1. Create a new repo (e.g., `streamside-checklist`).
2. Upload `index.html` to the repo root.
3. Go to **Settings → Pages** → set **Deploy from branch** (main / root).

## Enable Auto Email (EmailJS)
In `index.html`, fill these constants near the bottom:
```js
const EMAILJS_PUBLIC_KEY = "YOUR_PUBLIC_KEY";
const EMAILJS_SERVICE_ID = "YOUR_SERVICE_ID";
const EMAILJS_TEMPLATE_ID = "YOUR_TEMPLATE_ID";
const TO_EMAIL = "scott@scottberry.ca";
```
Then create an EmailJS template with variables:
```
to_email, subject, body, guest_name, arrival_date, departure_date
```
Set template subject to:
```
{{subject}}
```

When all checklist items are checked, an email is sent automatically. Guests can also tap **Email Completed Checklist** to send manually.

## Notes
- Progress auto‑saves locally (localStorage).
- The fallback uses `mailto:` if EmailJS isn’t configured or fails.
- Customize wording directly in `index.html`.
