# Triangulation Collapse: Synthesis Dilution test

Data for Section 6 of *Triangulation Collapse: How LLM-Mediated Search Removes the User's Last Line of Defense in High-Stakes Queries* (Fatima, 2026, v2).

Paper (PDF): [TC.pdf](TC.pdf)
Zenodo (all versions, always the latest): https://doi.org/10.5281/zenodo.22182821

## What this tests

Proposition 2 predicts that one hedged, accurate source loses influence on an LLM's output as confident, engagement-style sources are added. I tested that against Claude Sonnet 4.6 (`claude-sonnet-4-6`).

- 4 domains: health, legal, financial, hiring
- 6 conditions per domain: H alone (H0), H plus 1, 2, 4 or 8 confident sources (k1, k2, k4, k8), and 8 confident sources with no hedged source (C8)
- 2 tasks: "summarize" (run 2026-10-21) and "answer" (run 2026-10-30)
- 6 outputs per domain and condition, 144 per task, 288 in total
- Position of the hedged source is randomized

## Result

No output out of 288 was judged to endorse the confident claim. Mean stance (5 = careful) was between 4.79 and 5.00 in every condition and did not fall as confident sources were added. Details and caveats are in Section 6 of the paper.

## Files

`dilution_experiment_final.json` has the sources, and every prompt, output, judge score and human label.

`dilution_experiment_final.csv` has the same rows in flat form.
Columns: `run` (summarize or answer), `id`, `domain`, `condition`, `k_confident`, `has_hedged`, `source_order` (H or C1..C8 in the order shown), `prompt`, `output`, `judge_stance` (1 = overconfident, 5 = careful), `judge_endorses` (hedged, confident, both, neither), `judge_urgency`, `judge_hedge_present`, `judge_discounts_confident`, and `human_stance`, `human_endorses`, `human_urgency`. Human labels exist for 30 outputs per task (60 total) and are empty elsewhere.

## Notes

- The judge is also Claude Sonnet 4.6. Its agreement with my labels is in Section 6.2 of the paper.
- Four human labels were corrected after I clarified how to score deadline advice that comes from the careful source. The corrected labels are the ones in these files.
- A live model changes across versions, so rerunning will not reproduce these exact outputs.
