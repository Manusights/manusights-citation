# Changelog

All notable changes to the Manusights citation repository are recorded here. This file follows the [Keep a Changelog](https://keepachangelog.com/) convention; the citation repository follows [semantic versioning](https://semver.org/).

The Zenodo concept DOI [`10.5281/zenodo.20072010`](https://doi.org/10.5281/zenodo.20072010) always resolves to the latest version.

## v1.1.0 — 2026-05-07

Polished the deposit metadata to FORCE11 + Software Sustainability Institute exemplary-deposit standard.

- `LICENSE`: switched from custom prose to canonical Creative Commons Attribution 4.0 International (CC BY 4.0) text. SPDX-detectable.
- `CITATION.cff`: added `contact`, `repository-artifact`, `identifiers` (concept DOI + version DOI + URL identifiers), `references` (FORCE11 software-citation principles paper), `license` (SPDX `CC-BY-4.0`), and a richer `preferred-citation` block with publisher.
- `README.md`: added DOI, license, and CITATION.cff badges; expanded "How to cite" section with concept-DOI vs version-DOI guidance; added disclosure norm; added contact section.
- `methods.md`: expanded methodology summary with anchor-literature references; added service-scope framing; clarified versioning semantics.
- `CHANGELOG.md` (this file): created.

## v1.0.2 — 2026-05-07

Initial successful Zenodo auto-deposit. Concept DOI minted: `10.5281/zenodo.20072010`. Version DOI for v1.0.2: `10.5281/zenodo.20072011`.

- Removed non-SPDX license field from `CITATION.cff` to unblock Zenodo import (subsequent v1.1.0 reintroduces a proper SPDX license).
- v1.0.0 webhook returned 403 (Zenodo OAuth token had not yet propagated to the new repository).
- v1.0.1 webhook returned 500 (Zenodo's import rejected the non-SPDX `LicenseRef-Proprietary` value).
- v1.0.2 succeeded.

## v1.0.0 — 2026-05-07

Initial repository setup. Citation metadata, README, methodology summary, and license file. Public repository created at https://github.com/Manusights/manusights-citation under the Manusights GitHub organization.
