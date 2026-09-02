# OCP Global Summit Invite — HubSpot email

Three design options for this invite, each built from Figma (file "Events", `RVf3jOKgFR31N3wYWxPY4r`):

- **`option-1.html`** — light, hero is a flattened Lightmatter&times;OCP logo lockup graphic.
  (Figma node `3517:13174`)
- **`option-2.html`** — dark card, hero is the neon Lightmatter sign photo with the OCP logo and
  "Networking reception" label baked in. (Figma node `3517:13194`)
- **`option-3.html`** — light, hero is a product photo (Guide DR tray) with a separate wordmark
  logo and sub-headline above it. This is the original/current design. (Figma node `3504:21422`)

Each is a standalone HubSpot custom-HTML-module fragment (no `<html>`/`<head>`/`<body>`). All
styling is inline; no external CSS/JS.

`index.html` is **not** an email fragment — it's a local-only viewer with a nav that switches
between the three options in an iframe, so they can be compared side by side before picking one.
Open it directly in a browser to preview; nothing in it goes to HubSpot.

## Before sending, checklist (applies to whichever `option-*.html` is chosen):

1. **Upload that option's image(s) to HubSpot's File Manager.** The `<img src="...">` values
   currently point to local filenames in this folder:
   - Option 1: `26Q3-03-lm-x-ocp-lockup-option1.png`
   - Option 2: `26Q3-04-lm-neon-sign-ocp-option2.png`
   - Option 3: `26Q3-01-lm-wordmark-red.png` and `26Q3-02-lm-guide-dr-tray-ocp-summit.png`

   Upload the relevant file(s) to HubSpot, then swap each `src` to the resulting `hubfs` CDN URL,
   e.g. `https://48038959.fs1.hubspotusercontent-na2.net/hubfs/48038959/<filename>` — matching the
   pattern used in the `post interconnect email` reference project.

2. **RSVP link is set** to the HubSpot form (`https://share-na2.hsforms.com/2TaObo0SySeCGyV9qEmkTsAsln3j`),
   with UTM/tracking params stripped from the shared link. Double-check it's still current before
   sending.

3. **All raster art is PNG, not SVG, on purpose.** SVG isn't supported in Outlook desktop and
   renders inconsistently in other email clients, so every logo/hero graphic (wordmark, LM&times;OCP
   lockup, neon sign, product photo) was exported as a flattened PNG at 2x for crisp rendering on
   retina displays while staying broadly email-client compatible. Sizes:
   - Option 1 hero `26Q3-03-lm-x-ocp-lockup-option1.png`: 1032&times;360 (2x of 516&times;180)
   - Option 2 hero `26Q3-04-lm-neon-sign-ocp-option2.png`: 1032&times;550 (2x of 516&times;275)
   - Option 3 wordmark `26Q3-01-lm-wordmark-red.png`: 676&times;72 (2x of 338&times;36)
   - Option 3 hero `26Q3-02-lm-guide-dr-tray-ocp-summit.png`: 1028&times;612 (2x of 516&times;308) —
     its Figma-native border was cropped off and is applied instead as a real
     `border:1px solid #D4D4D4` on the wrapping `<table>` in the HTML.

   Whichever hero art changes in Figma, re-export at 2x (and, for option 3's product-photo style,
   re-crop the border the same way) and replace the file in this folder.

5. **Check the outer page-background wrapper in HubSpot's own preview.** The outermost `<div
   style="background:#F9F9F9;padding:24px 0;">` assumes the module drops directly into the email
   body with no other container around it. If HubSpot's template already wraps modules in its own
   padded container, this may double up spacing or get clipped — verify in HubSpot's preview and
   adjust/remove if needed.
