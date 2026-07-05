# AFTER9 — Static Site

Static export of the AFTER9 site, ready for GitHub Pages.

## Structure
```
index.html
style.css
script.js
assets/img/tee-front.jpg
assets/img/tee-back.jpg
assets/img/about-graphic.jpg
```

## Deploy to GitHub Pages
1. Push this folder's contents to the root of a GitHub repo.
2. In the repo: **Settings → Pages → Build and deployment → Source** → "Deploy from a branch".
3. Pick the `main` branch and `/ (root)` folder, then Save.
4. Live at `https://<username>.github.io/<repo-name>/` within a minute or two.

## What's new in this version
- A **Pre-Order** section that lets people buy any of the five "Coming Soon" pieces early via Paystack, even before the main drop unlocks.
- Email is now fully wired up through **FormSubmit** (`caseyfoatykvs@gmail.com`) instead of the old placeholder — the notify form, contact form, and completed Paystack orders all land in that inbox.
- The drop countdown is now frozen at `00:00:00:00` and the "Aug 1" date is blurred on purpose — your own code comment confirms this is intentional (mystery-drop styling), not a bug in the export.
- Bug fix carried over from your file: the checkout callback now captures the product before the modal closes, so Paystack's callback can't lose track of what was being paid for.

## Before you go live
1. **Paystack public key** — still a placeholder (`pk_test_xxxx...`) in `script.js` line 4. Add your real key or checkout won't process payments.
2. **FormSubmit activation** — the first real submission to `caseyfoatykvs@gmail.com` triggers a one-time confirmation email from FormSubmit. It has to be clicked once or none of the emails (notify signups, contact messages, order alerts) will actually deliver.
3. **Two of the four Limited Edition photos are duplicates** — `leExtra1Img` reuses the exact same photo as `leFrontImg`, and `leExtra2Img` reuses `leBackImg` (confirmed byte-for-byte identical, so the export saved only the 3 unique images rather than 5). Looks like placeholders for two more angles you haven't shot yet — worth swapping in before launch if so.
4. **Admin password in plain text** — `ADMIN_PASSWORD = 'NBA123DR'` in `script.js`. Your comment already notes it's a convenience UI, not real security, but on a public repo/page it's fully visible to anyone who looks.
5. **What ships by default** — tee photos blurred, stock 99/99, pre-orders open, main drop not forced live. The Admin panel only lets you preview changes in your own browser tab; the real defaults live in `LE_STATE`/`DROP_CONFIG` in `script.js`.
