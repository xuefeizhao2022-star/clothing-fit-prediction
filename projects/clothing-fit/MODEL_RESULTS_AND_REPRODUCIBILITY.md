# Model results and reproducibility | Clothing Fit Risk Prediction

> Portfolio verification note · 17 November 2026. This document distinguishes **saved notebook output** from **the original report figure**. The original university submission is not silently altered.

## Project and dataset
- Source: UCSD McAuley Lab public RentTheRunway review dataset.
- Dataset URL as recorded in the corrected notebook: `https://mcauleylab.ucsd.edu/public_datasets/data/renttherunway/renttherunway_final_data.json.gz`.
- Target: `small`, `fit`, `large`.
- Stratified data split: 70% training / 15% validation / 15% test, with a fixed `RANDOM_STATE` in the notebook.
- Saved split sizes: train 134,648; validation 28,853; test 28,854.
- Candidate approaches: logistic regression variants, Random Forest and a majority-class baseline.
- Final model: scikit-learn Pipeline with preprocessing and Logistic Regression (`solver="lbfgs"`, `max_iter=500`, class weights `fit:1, small:3, large:3`). Final fitting used the training/validation data as configured in the corrected notebook.

## Results: corrected notebook's saved test output
| Metric | Test |
|---|---:|
| Accuracy | 0.6770 |
| Balanced accuracy | 0.5728 |
| Macro F1 | 0.5493 |
| Misfit recall | 0.5196 |
| Misfit precision | 0.4198 |
| False alert rate | 0.2553 |

Validation in the same saved comparison: Accuracy 0.6812, balanced accuracy 0.5789, macro F1 0.5546, misfit recall 0.5306, false alert rate 0.2523.

## Figure version audit
The publicly displayed confusion matrix was supplied from the original course report, **not regenerated from the corrected notebook**.

| Actual / Predicted | small | fit | large |
|---|---:|---:|---:|
| small | 1,841 | 1,892 | 129 |
| fit | 2,786 | 15,879 | 2,622 |
| large | 120 | 1,759 | 1,826 |

Total 28,854; diagonal sum 19,546; figure-derived accuracy **19,546 / 28,854 = 0.6774**. This differs slightly from the corrected notebook's saved output (0.6770). These are separate result snapshots. **Do not interpret the figure as a visualization of the 0.6770 run.** The feature-coefficient figure is likewise a course-report snapshot and should not be assumed to be from the corrected run.

## Interpretation
- The project optimized for detecting unsuitable fit, not raw accuracy alone.
- The majority-class baseline may score well on accuracy while failing to identify misfits.
- Product identity matters; generalization to unseen products is a limitation.
- Coefficients are model associations, not causal effects.
- The prototype was not deployed to customers.

## Reproduction checklist
1. Download the public dataset using the URL recorded above.
2. Use the corrected notebook's original preprocessing and fixed random state.
3. Re-run all cells in order and save the newly produced test metrics and plots together.
4. Compare test confusion matrix and derived metrics **from the same run** before replacing report-version figures.
5. Do not publish a modified academic report as though it were the originally submitted version.

**Code publication status:** The corrected source notebook has been located in the user's uploaded files but has not yet been published to this GitHub repository. No public code download link is claimed here.
