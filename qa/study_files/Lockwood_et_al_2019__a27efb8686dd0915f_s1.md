# Lockwood et al. (2019)

- **study_id:** `a27efb8686dd0915f_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lockwood, P. L., Klein-Flugge, M. C., Abdurahman, A., & Crockett, M. J. (2019). Neural signatures of model-free learning when avoiding harm to self and other. *bioRxiv*. https://doi.org/10.1101/718106
- **citation_short:** Lockwood et al. (2019)
- **doi:** 10.1101/718106
- **publication_type:** preprint
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department of Experimental Psychology, University of Oxford, Oxford OX1 3PH, United; Centre for Integrative Neuroimaging, Department of Experimental Psychology,; Department of Psychology, Yale University, New Haven, CT, 06511, USA; Department of Psychology, 2 Hillhouse Avenue, New Haven, CT 06511,; division between ‘model-free’ algorithms that; University of Birmingham University of Oxford; lable under a CC-BY-NC-ND 4; University of Oxford, OX1; emails: patricia.lockwood@psy.ox.ac.uk, molly.crockett@yale.edu, miriam.klein-flugge@psy.ox.ac.uk
- **code_url:** https://osf.io/3stp9/files/

## Computational level
- **study_focus:** Harm avoidance learning -- model-free vs. model-based learning when avoiding painful outcomes for self versus a stranger.
- **study_focus_short:** Harm avoidance learning -- model-free vs. model-based learning when avoiding
- **learning_mode_description:** - Learning mode: Learning from aversive outcomes (electric shocks) to oneself and a stranger about which actions avoid harm   - Learning from:     - Source type (non-social): self (own choices and experienced transitions)     - Source content (non-social): outcome (pain / no pain)   - Learning about:     - Target type (social): other (stranger/receiver) -- and also self     - Target content (social): outcome (harm avoidance -- which actions avoid delivering pain to other)     - Target content (non-social): outcome (harm avoidance -- which actions avoid pain to self)  Note: The task has two conditions (self, other). For the "other" condition: learning from one's own action outcomes about how to avoid harm to another person. For the "self" condition: learning from one's own action outcomes about how to avoid harm to oneself (non-social). The key finding concerns the *social* condition (other), where:   - Source type (non-social): self   - Source content (non-social): outcome (pain/no-pain feedback)   - Target type (social): other (stranger)   - Target content (social): outcome (pain/harm to other)
- **task_description:** In a two-stage decision-making task (adapted from Daw et al., 2011), participants made sequential choices between fractal images that probabilistically led to one of two states, then chose again, receiving pain (electric shock) or no-pain outcomes for either themselves or a stranger. The probability of pain drifted over 136 trials per agent (self/other), and 10% of accumulated shocks were delivered at session end.
- **task_paradigm:** Two-step task
- **players:** Single agent (participant), single target (stranger/receiver)
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Abstract fractal images, colored zones, pain (electric shock) / no-pain outcome symbols
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Model-free learning (main effect of outcome on stay/switch): d = 0.77   - Model-based learning (outcome x transition interaction): d = -0.53   - Greater model-free learning for other vs. self (outcome x recipient interaction): d = -0.39   - w parameter lower for other (0.45) than self (0.55): t(35) = 2.41, d = 0.40   - Ventral striatum tracked model-free PE bilaterally (R: x=10, y=12, z=-4, Z=5.84; L: x=-16, y=6, z=-10, Z=5.77; FWE whole-brain corrected)   - Thalamus/caudate distinguished other > self PE (x=16, y=-18, z=0, Z=3.50, FWE-SVC)   - sgACC tracked model-free influence for other (stay > switch after no pain; x=-2, y=36, z=6, Z=3.88, FWE whole-brain corrected)   - sgACC response correlated with model-free x recipient behavioral interaction: r(33) = .36   - TPJ tracked inverse model-free influence for other (switch > stay after no pain; x=54, y=-38, z=34, Z=3.56, FWE-SVC)   - sgACC-dlPFC connectivity increased during switch vs. stay after no pain for other (x=-46, y=38, z=26, Z=4.12, FWE whole-brain corrected)   - Anti-utilitarianism (OUS instrumental harm) correlated with model-free moral behavior: r(36) = 0.37   - dlPFC-sgACC connectivity correlated with instrumental harm: r(33) = 0.43   - Outcome sensitivity correlated with switching after harm to others: r(36) = -.37   - Outcome sensitivity correlated with thalamus/caudate other > self PE: r(34) = .385   - Outcome sensitivity correlated with sgACC model-free signal: r(33) = -.374
- **effect_size:** - Main Results:   - Model-free learning (main effect of outcome on stay/switch): d = 0.77   - Model-based learning (outcome x transition interaction): d = -0.53   - Greater model-free learning for other vs. self (outcome x recipient interaction): d = -0.39   - w parameter lower for other (0.45) than self (0.55): t(35) = 2.41, d = 0.40   - Ventral striatum tracked model-free PE bilaterally (R: x=10, y=12, z=-4, Z=5.84; L: x=-16, y=6, z=-10, Z=5.77; FWE whole-brain corrected)   - Thalamus/caudate distinguished other > self PE (x=16, y=-18, z=0, Z=3.50, FWE-SVC)   - sgACC tracked model-free influence for other (stay > switch after no pain; x=-2, y=36, z=6, Z=3.88, FWE whole-brain corrected)   - sgACC response correlated with model-free x recipient behavioral interaction: r(33) = .36   - TPJ tracked inverse model-free influence for other (switch > stay after no pain; x=54, y=-38, z=34, Z=3.56, FWE-SVC)   - sgACC-dlPFC connectivity increased during switch vs. stay after no pain for other (x=-46, y=38, z=26, Z=4.12, FWE whole-brain corrected)   - Anti-utilitarianism (OUS instrumental harm) correlated with model-free moral behavior: r(36) = 0.37   - dlPFC-sgACC connectivity correlated with instrumental harm: r(33) = 0.43   - Outcome sensitivity correlated with switching after harm to others: r(36) = -.37   - Outcome sensitivity correlated with thalamus/caudate other > self PE: r(34) = .385   - Outcome sensitivity correlated with sgACC model-free signal: r(33) = -.374
- **learning_from:** Self; own action outcomes (pain/no-pain feedback from choices in two-step task)
- **learning_about:** Other (stranger); which actions avoid delivering pain to another person. Also self (which actions avoid pain to oneself).  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Hybrid MB/MF with separate w for self/other: 2 LRs ($\alpha_{Pain}$, $\alpha_{NoPain}$), 1 $\beta$, 1 $\rho$, $\omega_{Self}$, $\omega_{Other}$ (6 params, $\lambda$ fixed to 1)  Note: When fitted separately per agent, a 5-parameter model wins (M5: $\alpha_{Pain}$, $\alpha_{NoPain}$, $\beta$, $\rho$, $\omega$; $\lambda$=1). When fitted to pooled self+other data, the 6-parameter model (M6) with separate $\omega_{Self}$ and $\omega_{Other}$ wins.
- **model_family:** MB/MF hybrid
- **model_class:** PE learning
- **all_models_tested:** *Fitted separately for self and other (5 models):* - M1: 7-param full Daw model ($\alpha_{S1}$, $\alpha_{S2}$, $\beta_{S1}$, $\beta_{S2}$, $\rho$, $\lambda$, $\omega$); n_params=7; metric=BICint, XP - M2: 6-param ($\alpha_{S1}$, $\alpha_{S2}$, $\beta_{S1}$, $\beta_{S2}$, $\rho$, $\omega$; $\lambda$=1); n_params=6; metric=BICint, XP - M3: 5-param ($\alpha$, $\beta$, $\rho$, $\lambda$, $\omega$); n_params=5; metric=BICint, XP - M4: 4-param ($\alpha$, $\beta$, $\rho$, $\omega$; $\lambda$=1); n_params=4; metric=BICint, XP - M5 (winner): 5-param ($\alpha_{Pain}$, $\alpha_{NoPain}$, $\beta$, $\rho$, $\omega$; $\lambda$=1); n_params=5; metric=BICint, XP (self XP=0.9999, other XP=0.9588)  *Fitted to pooled data (3 models):* - M5: 5-param shared across agents; n_params=5; metric=BICint, XP - M6 (winner): 6-param with separate $\omega_{Self}$, $\omega_{Other}$; n_params=6; metric=BICint (XP=0.1088 but BICint preferred) - M7: 7-param with separate $\rho$ and $\omega$ for self/other; n_params=7; metric=BICint, XP
- **model_mb_mf:** MB/MF hybrid
- **model_params:** - $\alpha_{Pain}$: learning rate for pain outcomes (mean = 0.35) - $\alpha_{NoPain}$: learning rate for no-pain outcomes (mean = 0.35) - $\beta$: inverse temperature (mean = 3.81) - $\rho$: perseverance (mean = 0.63) - $\omega_{Self}$: MB/MF weighting for self (mean = 0.55) [S] - $\omega_{Other}$: MB/MF weighting for other (mean = 0.45) [S] - $\lambda$: fixed to 1 (eligibility trace)
- **social_param:** $\omega_{Other}$ -- model-free/model-based weighting parameter for the other (stranger) condition. Lower $\omega$ = more model-free. Significantly lower for other than self, indicating prioritization of model-free learning when avoiding harm to others.
- **social_param_name:** $\omega_{Other}$
- **social_param_value:** 0.55
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BICint (integrated BIC), exceedance probability (XP), protected XP; also reported negLL, AIC, BIC
- **how_model_fit:** individual-level-fit (hierarchical Bayesian MAP estimation with EM)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors from computational model) + PPI
- **contrast:** - Model-free PE (main effect, both agents): VS bilateral (FWE whole-brain) - Model-free PE other > self: thalamus/caudate (FWE-SVC) - Stay > switch after no pain for other (model-free influence): sgACC (FWE whole-brain) - Switch > stay after no pain for other (anti-model-free): rTPJ (FWE-SVC) - PPI: sgACC seed, switch > stay after no pain for other: dlPFC (FWE whole-brain) - Value difference (inverse): dACC/pre-SMA, bilateral inferior parietal, MFG (FWE whole-brain) - State prediction error: dACC (FWE whole-brain)
- **key_regions:** Model-free PE in bilateral ventral striatum for both agents; thalamus/caudate distinguished other > self PE; sgACC encoded model-free influence at choice for other; rTPJ showed inverse pattern (switch > stay); dlPFC-sgACC connectivity when overriding model-free influence for other; dACC tracked state PE.
- **key_regions_abbrev:** VS, caudate, striatum, dlPFC, dACC, ACC, sgACC, TPJ, thalamus
- **coordinates_peak:** - Ventral striatum (R): 10, 12, -4 - Ventral striatum (L): -16, 6, -10 - Thalamus/caudate (other > self PE): 16, -18, 0 - sgACC (stay > switch after no pain other): -2, 36, 6 - rTPJ (switch > stay after no pain other): 54, -38, 34 - dlPFC (PPI with sgACC, switch > stay other): -46, 38, 26 - dACC (state PE): -6, 10, 52  Note: Supplementary Table 1 (whole-brain analysis) was referenced but the table content did not extract from the supplement text file. The coordinates above are from the main text.
- **analysis_type:** both (whole-brain FWE cluster correction + ROI/SVC for a priori regions: caudate, thalamus, TPJ, sgACC, dlPFC)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N=41 recruited; N=36 for behavioral analyses (16 female, age 18-36); N=34 for parametric fMRI; N=33 for stay/switch fMRI analysis. 80% power to detect d=0.50.
- **population_category:** healthy adults
- **population_age_range:** 18–36
- **ecological_validity:** Lab-based with electric shocks as aversive outcomes, which is more ecologically grounded than monetary losses for studying harm avoidance. However, the social interaction is minimal (anonymous stranger, no face-to-face contact), and the two-step task structure is abstract. Shocks were delivered post-scan (10% of accumulated), reducing immediacy.
- **eligibility_flag:** 
- **concerns:** - This is a bioRxiv preprint (July 2019), not peer-reviewed. Should check for a published version. - Hierarchical fitting with separate priors for self/other may bias toward finding parameter differences (authors acknowledge this). - The BICint for the pooled model comparison only "slightly" prefers M6 over M5 (XP=0.1088 for M6 vs 0.8911 for M5) -- the authors note this "does not support a strong conclusion." The separate-w model is preferred by BICint but not by XP. - Supplementary Table 1 (whole-brain coordinates) could not be extracted from the txt file. - No correction for multiple correlations with individual difference measures (moral judgment). - Relatively small sample for individual difference analyses (N=33-36).
- **limitations_reported:** Authors acknowledge: model-free moral learning was specifically driven by lower probability of repeating harmful choices rather than higher probability of staying after no-pain; cannot confidently attribute TPJ/dlPFC patterns to model-based control; results from individual difference analyses are "preliminary" and need replication in larger samples; unclear whether prioritization of model-free learning extends to other social decisions (rewards for others, monetary losses, non-human species).
- **limitations_categorized:** limited generalizability; small sample for individual differences; correlational individual difference analyses; task simplicity (abstract two-step task); limited ecological validity; preprint (not peer-reviewed)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.5
- **wc_total:** 8.5

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - Supplementary Table 1 coordinates: LOW confidence -- table header present but content not extracted from txt file. Main text coordinates are complete for key contrasts. - Publication status: This is a bioRxiv preprint. A published version may exist (Lockwood et al., 2020, PNAS is a possibility based on the authors and topic -- but this cannot be confirmed from the file). Flag as potential duplicate if a published version appears in the corpus. - Model comparison for pooled data: MEDIUM confidence -- BICint slightly prefers M6 but XP strongly prefers M5. Authors report M6 as winning but acknowledge weak evidence.
- **cannot_find:** - Full coordinate table from Supplementary Table 1 (extraction failed for formatted table) - Whether this preprint was subsequently published in a peer-reviewed journal
- **other_notes:** Joint first authorship (Lockwood and Klein-Flugge). The paper is notable for being one of the first to apply the two-step MB/MF paradigm to social/moral learning. The key finding -- that model-free learning is prioritized for others vs. self -- has implications for computational accounts of moral cognition. Data and code available on OSF. The first author (Patricia Lockwood) is one of the review authors, which should be disclosed.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_MB_MF_balance
- tax_param_PE_signal
- tax_param_perseveration
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_MB_MF_hybrid
- tax_rr_model_family = MB_MF_hybrid
- tax_rr_param_MB_MF_balance
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = moral_harm
- tax_rr_topic_moral_harm
- tax_rr_topic_prosocial_altruism
- tax_topic_moral_harm
- tax_topic_prosocial_altruism
