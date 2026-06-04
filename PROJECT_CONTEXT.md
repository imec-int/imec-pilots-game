# Project Context and Chat History

This file captures the key implementation history, decisions, and iteration notes from the assistant-driven build of this booth game. It is intended as a handover artifact so future contributors can continue without losing context.

## Project Goal

Build a static booth game for PILOTS at IPIC 2026 that guides visitors through a 5-step process-sharing challenge, captures leads, validates ISO 6346 container numbers, scores quiz interactions, and submits entries to Formspree.

## Technology and Architecture

- Static stack: HTML, CSS, vanilla JavaScript
- Data-driven flow: process steps configured in `data/process-steps.json`
- Rendering strategy: template-based step and summary rendering in `index.html` + `app.js`
- Form submission: Formspree endpoint configured in `config.js`
- Hosting target: plain static hosting (including GitHub Pages)

## Major Iteration History

1. Initial build
- Created core files: `index.html`, `styles.css`, `app.js`, `data/process-steps.json`, `config.js`, `README.md`.
- Implemented multi-step flow, lead capture, quiz support, score tracking, and final summary.
- Added ISO 6346 control-digit validation for optional container numbers.

2. Rendering and validation fixes
- Fixed step submission/validation context issue by using live rendered DOM references.
- Improved field validation UX and invalid-state visibility.

3. UI and layout redesign
- Reframed experience title to "Process Sharing Challenge".
- Switched from a left vertical timeline panel to a horizontal progress bar.
- Added responsive/mobile spacing and wrapping refinements.
- Moved event feed below question and made it collapsible with a Show/Hide toggle.

4. Branding and interaction polish
- Applied PILOTS-aligned palette and typography updates.
- Linked PILOTS logo to website and removed redundant step-level link.
- Compact step card adjustments (inline icon near step header).
- Updated transition bubble text to use arrow symbol.

5. Timeline animation enhancements
- Added desktop-only moving truck icon to progress bar.
- Iterated truck movement behavior for smoother continuity and visibility control.
- Refactored progress rendering to update in place rather than redraw each step.

6. Summary and completion updates
- Converted completion data into one vertical captured-data tile.
- Hid top restart action on completion to avoid duplicate controls.
- Added perfect-score celebration: congratulatory message and centered/intensified confetti.

7. Data-model and quiz logic adjustments
- Moved company field to Step 1 and made it optional.
- Corrected last-step quiz grading for single-select questions with multiple accepted correct values.

8. Git and publishing support
- Resolved non-fast-forward push by rebasing local `main` on `origin/main`.
- Successfully pushed current state to `imec-int/imec-pilots-game`.

## Current Behavior Snapshot

- Five-step challenge flow with progress bar and per-step quiz/interaction.
- Lead capture integrated throughout flow.
- Optional container number validated with ISO 6346 algorithm.
- Formspree submission executed at the end of the journey.
- Responsive layout tuned for booth screens and mobile.

## Known Follow-ups / Optional Next Work

1. Verify final GitHub Pages deployment and live URL behavior.
2. Run one visual QA pass on truck animation alignment across screen sizes.
3. Confirm perfect-score confetti intensity on target booth hardware.

## Collaboration Notes

- Keep this file updated when major UX, logic, or deployment decisions are made.
- Prefer adding date-stamped entries for substantial future changes.
- If changing quiz semantics, keep `data/process-steps.json` and grading logic in `app.js` aligned.