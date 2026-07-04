# Consulting website — Damian Chandia-Poblete (RWE & Biostatistics)

A single-file, static site. No build step, no dependencies — just `index.html`.

## Before you publish — edit 3 things

Open `index.html` and search for these markers (each is commented `EDIT ME`):

1. **`YOUR-FORM-ID`** → your Formspree form endpoint (see "Contact form" below). This is what makes the form email you.
2. **`YOUR-CALENDLY-LINK`** → your booking link (Calendly, Cal.com, or similar). Free tier is fine.
3. **LinkedIn URL** → replace `https://www.linkedin.com/` in the About section with your actual profile URL.

Everything else (copy, services, methods) is already tailored to your profile — adjust freely.

## Contact form — connect it to your inbox (5 minutes)

The site has a real contact form, but GitHub Pages only serves static files, so a small relay service forwards submissions to your email. The form is pre-wired for **Formspree** (free tier: 50 submissions/month, no card needed):

1. Sign up at [formspree.io](https://formspree.io) with the email you want messages sent to.
2. Create a new form → it gives you an endpoint like `https://formspree.io/f/abcdwxyz`.
3. In `index.html`, find `action="https://formspree.io/f/YOUR-FORM-ID"` and replace `YOUR-FORM-ID` with your ID (e.g. `abcdwxyz`).
4. Deploy, submit the form once yourself — Formspree emails you to confirm the address the first time. Done.

The form submits without leaving the page and shows a confirmation message on success. A hidden honeypot field quietly filters most spam bots. If you'd rather use a different relay, **Web3Forms**, **Basin**, or **Formcarry** all work the same way — just swap the `action` URL and, if needed, the field for the access key.

No email address ever appears in the page source, so scrapers can't harvest it.

## Publish on GitHub Pages (5 minutes)

1. Create a new public repo, e.g. `damianchp.github.io` (this exact name gives you the root URL `https://damianchp.github.io`). Any other repo name works too — it just lives at `/reponame`.
2. Upload `index.html` (and this README) to the repo root — drag-and-drop in the GitHub web UI is fine.
3. Repo **Settings → Pages → Source: Deploy from a branch → `main` / `root` → Save.**
4. Wait ~1 minute; your site is live at the URL shown on that Pages screen.

## Custom domain (optional, recommended)

A domain like `chandiapoblete.dk` or `[yourname]rwe.com` (~50–100 DKK/yr) makes the business email and site look established.

1. Buy the domain (e.g. via one.com, Simply.com, or Namecheap).
2. In the repo, **Settings → Pages → Custom domain** → enter your domain → Save. GitHub creates a `CNAME` file automatically.
3. At your registrar, add a `CNAME` record pointing `www` to `damianchp.github.io`, and the four GitHub `A` records for the apex domain (GitHub's Pages docs list the current IPs).
4. Tick **Enforce HTTPS** once the certificate provisions.

## Design notes

- **Palette:** deep petrol green + warm ochre on cool paper — a Nordic-clinical identity, deliberately away from the generic consulting-cream look.
- **Signature:** the hero graphic is a Kaplan–Meier–style survival curve — the actual method you sell, animated on load and disabled under reduced-motion.
- **Type:** Fraunces (display) · IBM Plex Sans (body) · IBM Plex Mono (data labels), loaded from Google Fonts.
- Responsive to mobile, keyboard-focusable, and respects `prefers-reduced-motion`.

## Later additions worth making

- A **case studies / selected work** section once you have a client testimonial (even an anonymised project outline).
- A one-page **Services PDF** linked from the hero for people who want to forward it internally.
- Your **CVR number** in the footer once the enkeltmandsvirksomhed is registered — it signals a real, invoiceable business.
