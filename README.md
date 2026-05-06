# STRATIS RSVP — An Exclusive Evening

Standalone landing page for the STRATIS demo dinner on **Tuesday, June 2, 2026** at **The Aster, Hollywood**. Form submissions go to **jberger@push.agency**.

## Files
- `index.html` — the entire page (HTML, CSS, JS inline; no build step).
- `vercel.json` — Vercel routing + security headers.

## Local preview
Open `index.html` in a browser, or:
```
npx serve .
```

## Deploy to Vercel
```
npm i -g vercel        # if not already installed
vercel                 # first deploy (preview URL)
vercel --prod          # promote to a free *.vercel.app domain
```
Or drag the folder into the Vercel dashboard.

## Activate the form (one-time)
The form posts to **FormSubmit.co**, a no-account form-to-email service.

1. Once deployed, fill out the form and submit it once.
2. FormSubmit will email **jberger@push.agency** with a confirmation link.
3. Julie clicks the link to confirm — done. Every submission after that lands in her inbox with all fields formatted as a table.

If Julie wants a different destination email, change the form `action` in `index.html`:
```html
<form action="https://formsubmit.co/ajax/EMAIL_HERE" ...>
```
The first submission to a new email triggers a fresh confirmation.

## Notes
- The `_subject`, `_template=table`, `_captcha=false`, and `_honey` fields are FormSubmit config (subject line, table-formatted email body, disable their captcha redirect since we use AJAX, hidden honeypot field for spam bots).
- AJAX submission keeps users on the page and shows the inline success state instead of redirecting to FormSubmit's thank-you page.
- The page is fully responsive, dark-mode by default, and uses Inter from Google Fonts.
