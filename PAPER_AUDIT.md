# Final paper audit

Final title: **ProvGuard: Confusion-Selected Hard Negatives for Reducing Prompt-Injection Over-Defense under Distribution Shift**.

The anonymous manuscript is a completed empirical study of the required experiment matrix. It retains mixed outcomes and explicitly separates incomplete optional checks. No acceptance or universal-superiority claim is made.

## Template and presentation

- Original `IEEEtran` conference class, version 1.8b, from the supplied template; class SHA-256 `c972aca108fda004c3514d63658e02816da2e54d9a1451e870b9bd970e003f55`.
- Final length: **6 US-letter pages, including references**. Body remains the template's 10-point Times-family type (rendered as Nimbus Roman); no margin, geometry, or body-font reduction.
- Anonymous IEEE author block retained; no funding, affiliation, or conference identity invented.
- All six final rendered pages and seven figure assets were visually inspected after iterative compilation. No clipped tables, overlapping labels, missing glyphs, or orphan headings remain. The final bibliography columns are balanced using the class's own reference-trigger command.
- Final log: **0 overfull boxes, 0 unresolved citations, 0 unresolved cross-references, 0 missing-glyph warnings**. One ordinary underfull vertical-box warning remains during IEEE float packing; inspected columns are filled and unclipped. Initial XeTeX class font-encoding warnings resolve to the verified Times-compatible body fonts.

## Completed experimental evidence

- **30/30 required runs**, six arms, five training seeds **13, 42, 123, 2024, 7777**.
- All thirty saved model/configuration bindings and all seven prediction files per run checked independently; **210 paper metrics** recalculated from probabilities and compared with the frozen master results.
- Required arms: Baseline, Curated-HN, Random-Real-1000, ProvGuard-250/500/1000.
- Curated augmentation: **343 valid unique rows**; no size-matching claim. Both primary real augmentation arms have 1000 rows.
- Six completed three-seed source-augmentation checks were verified and reported descriptively. They change augmentation source only; original PIDS training is retained. No fully held-out-corpus claim.
- Optional DeBERTa baseline attempt failed because its pretrained assets could not be downloaded or found in cache. Remaining architecture runs are not reported as completed. Extra random-control samples await semantic reviews; no result is fabricated.

## Correct denominators and selection

- Released HB rows: **1472**. Accessible evaluation text: **808 = 600 curated + 208 external**. **664 withheld LMSYS texts excluded**.
- External corpus coverage: 68 Dolly and 140 OASST1 prompts. Stress-set FPR is not a deployment prevalence estimate.
- Original PIDS train/validation/IID counts: 27093 / 3989 / 3918.
- Primary configuration is predefined **K=1000**, not the test-best K. K=250 and K=500 are nested ablations; all thresholds are fixed at 0.5.
- Selector ensemble: baseline seeds 13/42/123, fixed for the study. Leakage-filtered real pool: 17400. Two separately instantiated automated passes review 2927 records; both BENIGN is required. This is **not human annotation** and shared model errors remain possible.
- Source/length quotas match between the two real primary arms; sample overlap of 213 examples is permitted. No syntactic or structure-matching claim.

## Headline numerical checks

| Quantity | Final measured value |
|---|---:|
| Baseline external FPR | 20.67% |
| Curated-HN external FPR | 18.46% |
| Random-Real external FPR | 7.31% |
| ProvGuard external FPR | 4.23% |
| Baseline-to-ProvGuard external reduction | 16.44 pp; 79.5% relative |
| IID F1, baseline to ProvGuard | 98.15% to 98.26% |
| IID F1 change, from unrounded means | +0.12 pp |
| Attack recall, baseline to ProvGuard | 98.71% to 98.69% |
| Attack recall change, from unrounded means | -0.03 pp |
| External Random-Real minus ProvGuard FPR CI | [0.0096, 0.0548] |
| Aggregate Random-Real minus ProvGuard FPR CI | [-0.0050, 0.1408] |

The external Random-Real comparison is supported by a positive **pointwise**, unadjusted crossed-bootstrap interval. The aggregate interval crosses zero; the predefined joint novelty verdict remains **inconclusive**. Curated-HN wins aggregate HB FPR. Structural benign FPR decreases, but domain-OOD F1 also decreases. All six aggregate 10000-resample intervals were reproduced from paired seed/shared-prompt predictions. Seed predictions are not pooled as independent examples.

## Data separation and validity limits

No accessible evaluation record was added as training augmentation. The original frozen train and validation files are unchanged. A freshly loaded persisted TF-IDF character-boundary 3--5 index rejects exact/high-lexical-similarity matches at cosine 0.90; all five augmentation files independently pass. The unsupervised exclusion representation is fitted on available benchmark and potential augmentation text; this exposure is disclosed. It does not guarantee semantic independence or certify original upstream splits beyond their frozen hashes.

The candidate/evaluation corpora share provenance; externally sourced is not equivalent to unseen corpus. Automated adjudication is fallible, scores were hidden but ranked order was visible, and the exact serving model version was not exposed. The **172-row** `reports/MANUAL_AUDIT_QUEUE.csv` provides high-score texts for a future human review. Its human fields are empty; no completed human audit is claimed.

## Numerical, citation, and reviewer audits

- `96` summary mean/SD cells checked against per-seed results; all **six table sources** checked in exact numeric order.
- `89` used numerical macros bind `133` prose/caption occurrences to canonical evidence. The ledger records calculation, display rounding, source path, and input hash. Remaining literal decimal values are definitions or recorded protocol bounds, not copied observations.
- All **14** bibliography entries are cited, checked against primary metadata, and resolve in the compiled bibliography. No unused template references or `??` markers.
- Source metadata and DOI/arXiv identifiers are documented in `paper/citation_audit.json`; some publisher resolvers were inaccessible, so successful live resolution of every DOI is not asserted.
- No stale partial-result statements remain in the final manuscript. Optional unfinished checks are explicitly distinguished from the completed required study.
- Figures and tables use final artifacts only, with color/pattern/marker consistency and numeric input hashes. Seven vector PDFs, seven editable SVGs, seven 400 dpi PNGs, and the shared Python generation source are supplied.
- `paper/REVIEWER_PASS.md` records the fifteen requested skeptical objections and the manuscript responses. Literature positioning acknowledges established mining and prior over-defense mitigation.

## Single-file build and files

The final `ProvGuard.tex` embeds all 153 numerical macro definitions, the three
manuscript tables, fourteen IEEE-formatted references, and all seven vector
figures as native TikZ geometry. It contains no external project-file calls.
The manuscript uses four embedded figures; the other three remain available
as optional macros. Standard IEEEtran and declared TeX packages are required.

**PASSED:** a fresh folder containing only `ProvGuard.tex` compiled to six pages
with identical extracted text, resolved citations/references, and zero overfull
boxes or missing glyphs. All six final pages were inspected, including corrected
PDF hatch tiling. The current numeric audit checks embedded macros and tables
against the same canonical experiment evidence. The earlier independent deep
model/prediction audit remains archived in `paper/numerical_audit_modular.json`;
models and experiments were not rerun for the single-file conversion.

The portable archive contains the single source, compiled PDF, build and
numerical audits, and compilation instructions. Previous modular source, PDF,
audit, and archive are preserved under `paper/`.

Final source SHA-256: `eda328b4d7ba9fa99665cc3aa94e19ba8f2e9b616a3501931695bb978cb60b1f`.

Final PDF SHA-256: `1103f485132e91d4610a145d52ba18fdcab0c6c0941685cfeb46cca24fab1b95`.

Frozen master results SHA-256: `0475aa8b9e86781d19d8987134bbb71673c14bfd3ec39fc0f71bead3c93ed3bc` (unchanged).

Release note: neural model weights are excluded. The deep model audit describes the original study; the release verifier independently checks archived predictions and statistics. PDF identifying/time metadata is cleared.
