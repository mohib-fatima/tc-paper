# Triangulation Collapse: How LLM-Mediated Search Removes the User's Last Line of Defense in High-Stakes Queries

Research repository accompanying:

**Triangulation Collapse: How LLM-Mediated Search Removes the User's Last Line of Defense in High-Stakes Queries**

**Mohib Fatima · 2026 · Technical Report**

[Read the paper on Zenodo](https://doi.org/10.5281/zenodo.22182822) · [DOI: 10.5281/zenodo.22182822](https://doi.org/10.5281/zenodo.22182822)

---

## Overview

For decades, search engines functioned as triangulation tools: a user comparing multiple sources, noticing disagreement, and forming their own judgment. LLM-mediated search, which synthesizes ranked results into a single authoritative-sounding response, is systematically eliminating this behavior. This paper names this elimination **Triangulation Collapse (TC)**, formalizes the engagement-accuracy decoupling mechanism that drives it, and proposes a mitigation framework.

For the full formal model and propositions, see the paper directly.

## Key Propositions

1. **Engagement-Accuracy Decoupling** — engagement-ranked source selection can achieve maximum attainable engagement while its reliability is arbitrarily worse than the best available, whenever engagement and reliability are inversely ordered.
2. **Synthesis Dilution** — a single accurate, hedged source contributes an arbitrarily small share of the synthesized output as the salience-weighted share of engagement-optimized sources grows.
3. **Verification Suppression** — presenting results as a single synthesized answer fixes observed disagreement at its minimum value, collapsing verification-seeking to its floor rate regardless of true underlying disagreement.

## SARI: Stakes-Aware Re-ranking and Inference

SARI is proposed as a two-stage mitigation: accuracy-weighted re-ranking before retrieval, and stakes-conditioned generation (uncertainty surfacing, epistemic humility framing, professional referral integration) at inference time.

## Evidence and Scope

This repository does not claim:

- a controlled empirical study of Triangulation Collapse;
- a production-scale implementation of SARI;
- a validated stakes classifier; or
- empirical proof that SARI improves user outcomes.

These are identified as future work in the paper's limitations section.

## Repository Structure
