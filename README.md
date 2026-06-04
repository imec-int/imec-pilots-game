# PILOTS IPIC 2026 Booth Game

This repository contains a static HTML, CSS and JavaScript game for the PILOTS project booth at IPIC 2026. The experience turns certified container weighing into a short guided challenge about event-based process sharing.

## What is included

- Vertical mobile-friendly booth flow with five configurable process steps
- Step definitions stored in JSON so the number of steps can change without rewriting the UI
- Embedded lead capture across the flow for name, email, company and optional container number
- ISO 6346 container number control-digit validation when a container number is entered
- Quiz scoring that reinforces the process-sharing story
- Formspree submission hook for final lead capture and prize entry

## Files

- `index.html`: static shell and templates
- `styles.css`: PILOTS-inspired booth UI and timeline animation
- `app.js`: flow engine, scoring, container validation and Formspree submission
- `data/process-steps.json`: editable process definition
- `config.js`: local configuration for the Formspree endpoint

Each step in `data/process-steps.json` can define an `icon` (for example `"booking.svg"` or `"booking"`) to control the icon used in both the progress bar and step card.

## Configure Formspree

Edit `config.js` and set:

```js
window.APP_CONFIG = {
  formspreeEndpoint: "https://formspree.io/f/your-form-id"
};
```

The app submits JSON to Formspree after the final step.

## Static hosting

The app is designed for plain static hosting. No build pipeline is required.

## Project History and Handover

For implementation history, major decisions, and iteration context, see `PROJECT_CONTEXT.md`.

## Questions To Answer Before Booth Launch

1. What is the exact Formspree endpoint that should receive the submissions?
2. Should lead capture be framed as community sign-up, prize entry, or both?
3. Do you need an explicit consent checkbox and privacy wording for storing contact details?
4. Should the game remain English-only, or do you want a French and Dutch variant for the booth?
5. Do you want the result screen to promise a concrete prize, and if yes, what is that prize text?