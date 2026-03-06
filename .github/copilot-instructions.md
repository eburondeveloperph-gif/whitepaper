# Sovereign workspace instructions

- This repository is primarily a strategy/whitepaper workspace, not an application monorepo. Most changes should preserve narrative clarity, document structure, and consistency across artifacts.
- Treat `01-Executive-Summary/expanded-executive-summary.md` as the most detailed source of truth for the platform narrative. It contains the fuller positioning, quantified benefits, security controls, and the 4-phase rollout.
- Treat `index.html` as the presentation artifact: a polished, single-file landing page that condenses the whitepaper into an interactive demo with inline CSS and JavaScript.
- Preserve the numbered top-level folders (`01-...` through `09-...`). They define the intended whitepaper/briefing structure; add new content to the relevant numbered section instead of creating ad hoc files in the repo root.
- Several numbered directories are currently placeholders. If you add material there, keep filenames and section titles aligned with the existing sovereign/offline-defense storyline.

## Content and tone

- Write in a formal, strategic, defense-briefing tone. This repo consistently uses terms like **sovereign**, **offline-capable**, **graceful degradation**, **Zero Trust**, and **decision-support**.
- Maintain the positioning that Eburon augments legacy systems rather than replacing them. The markdown explicitly frames this as “no rip-and-replace” and the Counter-UAS capability as an information-fusion layer, not autonomous action.
- Keep phase names and sequencing consistent with the existing documents: Remote Discovery & Architecture, Sovereign Deployment Pilot, Counter-UAS Augmentation Pilot, Executive Review & National Rollout Planning.
- When updating claims, keep metrics and terminology synchronized between `index.html` and `01-Executive-Summary/expanded-executive-summary.md` so the short-form site does not drift from the long-form paper.

## Working in `index.html`

- `index.html` is intentionally self-contained: HTML, CSS, and JavaScript live in one file. Do not introduce a build step, framework, or bundler unless the user explicitly asks for a restructure.
- Preserve the DOM contract used by the translation flow in `handleTranslationRequest()`: `#translatable-hero`, `#translatable-doc`, `wrapper-hero`, and `wrapper-doc` must remain stable or the EBURON HTML round-trip will break.
- Keep interactive controls outside the translatable containers when possible. The current file does this deliberately for the play button so model-generated translations do not damage event wiring.
- Preserve the browser-entered API key flow (`#apiKey`) unless asked to redesign it. Never hardcode secrets or commit real API keys.
- If you change the translation or TTS logic, verify the fetch targets and expected response shapes still match the current EBURON endpoints used in `handleTranslationRequest()` and `toggleAudio()`.

## Workflow expectations

- There is no discovered build, test, or package-manager workflow in this repo. For front-end changes, validation is manual: review the file diff and open `index.html` in a browser or simple static server.
- Prefer small, surgical edits over broad rewrites. In this workspace, large wording changes can unintentionally alter strategic meaning.
- When adding new sections or diagrams, cross-reference the existing architecture themes: sovereign connectivity, sovereign compute/local cloud, legacy integration overlay, and sovereign voice intelligence/offline AI workspace.
- Use concrete file references in your reasoning and edits, for example `index.html` for UI/interaction behavior and `01-Executive-Summary/expanded-executive-summary.md` for canonical messaging.
