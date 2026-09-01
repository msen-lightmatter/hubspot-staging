# OCP Global Summit Invite — HubSpot email

`index.html` is a HubSpot custom-HTML-module fragment (no `<html>`/`<head>`/`<body>`), built from the
Figma design at node `3500:20640`. All styling is inline; no external CSS/JS.

## Before sending, checklist:

1. **Upload images to HubSpot's File Manager.** The `<img src="...">` values currently point to the
   local filenames in this folder:
   - `26Q3-01-lm-wordmark-red.png`
   - `26Q3-02-lm-m1000-eclick.png`

   Upload both to HubSpot, then swap each `src` to the resulting `hubfs` CDN URL, e.g.
   `https://48038959.fs1.hubspotusercontent-na2.net/hubfs/48038959/<filename>` — matching the pattern
   used in the `post interconnect email` reference project.

2. **Set the real RSVP link.** The CTA button's `href="#"` is a placeholder — replace with the actual
   RSVP form/page URL.

3. **Confirm the signature.** "Nick Harris [TBC]" is unconfirmed — update once finalized.

4. **Logo is a PNG, not SVG, on purpose.** SVG isn't supported in Outlook desktop and renders
   inconsistently in other email clients, so the wordmark was exported as a PNG at 2x
   (676×72, displayed at 338×36) for crisp rendering on retina displays while staying broadly
   email-client compatible.

5. **Hero image is also 2x.** `26Q3-02-lm-m1000-eclick.png` is exported at 1028×612 (2x of its
   516×308 display size) for retina sharpness. Its Figma-native border was cropped off and is
   applied instead as a real `border:1px solid #D4D4D4` on the wrapping `<table>` in the HTML.

6. **Check the outer page-background wrapper in HubSpot's own preview.** The outermost `<div
   style="background:#F9F9F9;padding:24px 0;">` assumes the module drops directly into the email
   body with no other container around it. If HubSpot's template already wraps modules in its own
   padded container, this may double up spacing or get clipped — verify in HubSpot's preview and
   adjust/remove if needed.
