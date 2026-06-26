# Lockwood et al. (2019)

- **study_id:** `af1312d6aa6d6f781_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lockwood, P. L., Klein-Flugge, M. C., Abdurahman, A., & Crockett, M. J. (2019). Neural signatures of model-free learning when avoiding harm to self and other. *bioRxiv*, 718106. https://doi.org/10.1101/718106
- **citation_short:** Lockwood et al. (2019)
- **doi:** 10.1101/718106
- **publication_type:** preprint
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department of Experimental Psychology, University of Oxford, Oxford OX1 3PH, United; Centre for Integrative Neuroimaging, Department of Experimental Psychology,; Department of Psychology, Yale University, New Haven, CT, 06511, USA; Department of Psychology, 2 Hillhouse Avenue, New Haven, CT 06511,; division between ‘model-free’ algorithms that; University of Birmingham University of Oxford; lable under a CC-BY-NC-ND 4; University of Oxford, OX1; emails: patricia.lockwood@psy.ox.ac.uk, molly.crockett@yale.edu, miriam.klein-flugge@psy.ox.ac.uk
- **code_url:** https://osf.io/3stp9/files/

## Computational level
- **study_focus:** Moral learning / harm avoidance learning — whether model-free vs. model-based learning strategies differ when learning to avoid harmful (painful) outcomes for oneself versus a stranger.
- **study_focus_short:** Moral learning / harm avoidance learning
- **learning_mode_description:** - Learning mode: Learning from aversive outcomes (electric shock / no shock) about which actions avoid harm to self and to another person   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (shock / no shock delivered to self or other)   - Learning about:     - Target type (social): other (stranger)       - *Also* Target type (non-social): self     - Target content (social): action/policy (which first-stage action minimizes harmful outcomes for the other person)       - *Also* Target content (non-social): action/policy (which first-stage action minimizes harmful outcomes for self)  Note: The task has two conditions (self, other). In the "other" condition, outcomes are social (harm to a stranger). In the "self" condition, outcomes are non-social. The key finding concerns the difference between these conditions. Both conditions involve learning from one's own action-outcome contingencies.
- **task_description:** Participants completed a two-step decision-making task (hybrid Daw/Kool paradigm) in which first-stage choices probabilistically led to one of two second-stage states, where a further choice resulted in either an electric shock or no shock for either the participant (self blocks) or a stranger (other blocks). Outcome probabilities drifted throughout the task, requiring continuous learning.
- **task_paradigm:** Two-step task
- **players:** Single agent (participant), single target (stranger receiver)
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Abstract fractal images, coloured zones indicating second-stage states, shock/no-shock outcome symbols
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Model-free learning was prioritized when avoiding harm to others vs. self: outcome x recipient interaction (d = -0.39) - Model-free contribution: main effect of outcome on stay/switch (d = 0.77) - Model-based contribution: transition x outcome interaction (d = -0.53) - Winning model w parameter lower for other (0.45) than self (0.55) (d = 0.40) - Thalamus/caudate distinguished model-free PEs for other > self (FWE-SVC p = .033) - sgACC encoded model-free influence (stay > switch after no pain) for other (FWE whole-brain p = .028) - rTPJ showed inverse pattern (switch > stay after no pain for other; FWE-SVC p = .03) - sgACC-dlPFC connectivity increased when resisting model-free influence for other (FWE whole-brain p = .039) - Anti-utilitarian moral judgment correlated with model-free moral behaviour (r = 0.37) - Outcome sensitivity correlated with model-free switching for other (r = -.37), thalamus/caudate PE (r = .385), sgACC response (r = -.374)
- **effect_size:** - Model-free main effect: d = 0.77 - Model-based interaction: d = -0.53 - Outcome x recipient (MF prioritization for other): d = -0.39 - w_self vs w_other: d = 0.40 - sgACC response ~ MF x recipient behaviour: r = .36 - Instrumental harm ~ MF moral behaviour: r = 0.37 - Instrumental harm ~ dlPFC-sgACC connectivity: r = 0.43 - Outcome sensitivity ~ MF switching for other: r = -.37 - Outcome sensitivity ~ thalamus/caudate PE: r = .385 - Outcome sensitivity ~ sgACC response: r = -.374
- **learning_from:** Self; own action-outcome contingencies (shock/no-shock outcomes experienced for self or delivered to other)
- **learning_about:** Self and other (stranger); which actions avoid harmful outcomes for self and for another person  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Hybrid MB/MF with 6 params: separate LRs for pain/no-pain (α_Pain, α_NoPain), single β, perseverance ρ, and separate w_Self, w_Other (M6 from pooled analysis)  Note: When fitting self and other blocks separately, the 5-parameter model (M5) won for both. When fitting pooled data, M6 (with separate w for self and other) was preferred by BICint.
- **model_family:** MB/MF hybrid
- **model_class:** PE learning
- **all_models_tested:** Fitted separately per condition: - M1: 7-param (α_S1, α_S2, β_S1, β_S2, ρ, λ, w) — n_params: 7, metric: BICint - M2: 6-param (α_Pain, α_NoPain, β_S1, β_S2, ρ, λ=1, w) — n_params: 6, metric: BICint - M3: 5-param (α, β, ρ, λ, w) — n_params: 5, metric: BICint - M4: 4-param (α, β, ρ, λ=1, w) — n_params: 4, metric: BICint - M5: 5-param (α_Pain, α_NoPain, β, ρ, λ=1, w) — n_params: 5, metric: BICint [WINNER per condition]  Fitted on pooled data: - M5 pooled: 5-param shared — n_params: 5, metric: BICint - M6 pooled: 6-param (separate w_Self, w_Other) — n_params: 6, metric: BICint [WINNER pooled] - M7 pooled: 7-param (separate ρ_Self, ρ_Other, w_Self, w_Other) — n_params: 7, metric: BICint
- **model_mb_mf:** MB/MF hybrid
- **model_params:** - α_Pain: learning rate for pain outcomes (mean = 0.35) - α_NoPain: learning rate for no-pain outcomes (mean = 0.35) - β: inverse temperature (mean = 3.81) - ρ: perseverance parameter (mean = 0.63) - w_Self [S]: model-based/model-free weighting for self (mean = 0.55; higher = more MB) - w_Other [S]: model-based/model-free weighting for other (mean = 0.45; higher = more MB)
- **social_param:** w_Other — the model-based/model-free weighting parameter specific to learning about outcomes for the other person. Lower w_Other (0.45) relative to w_Self (0.55) indicates greater model-free reliance when learning to avoid harm to others.
- **social_param_name:** w_Self
- **social_param_value:** 0.55
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BICint (integrated BIC), exceedance probabilities via SPM BMS
- **how_model_fit:** individual-level-fit (hierarchical Bayesian MAP estimation with EM)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors from computational model) + PPI
- **contrast:** - GLM1: Model-free PE at outcome (self + other; main effect) — bilateral ventral striatum - GLM1: Model-free PE other > self at outcome — thalamus/caudate (FWE-SVC) - GLM1: Inverse value difference at first-stage choice — dACC/pre-SMA, bilateral IPC, MFG - GLM1: State PE at second stage — dACC - GLM2: Stay > switch after no pain for other at first-stage choice — sgACC (FWE whole-brain) - GLM2: Switch > stay after no pain for other — rTPJ (FWE-SVC) - GLM3 (PPI): sgACC connectivity during switch > stay after no pain for other — dlPFC (FWE whole-brain, negative association)
- **key_regions:** Model-free PE for both self and other in bilateral ventral striatum; differential other > self PE in thalamus/caudate; model-free influence (stay > switch after no pain for other) in sgACC; inverse model-free pattern (switch > stay) in rTPJ; sgACC-dlPFC connectivity when resisting model-free influence for other.
- **key_regions_abbrev:** VS, caudate, striatum, dlPFC, ACC, sgACC, TPJ, AI, thalamus
- **coordinates_peak:** - Ventral striatum (R): 10, 12, -4 - Ventral striatum (L): -16, 6, -10 - Thalamus/caudate (other > self PE): 16, -18, 0 - dACC (state PE): -6, 10, 52 - sgACC (model-free influence, other): -2, 36, 6 - rTPJ (inverse model-free, other): 54, -38, 34 - dlPFC (PPI with sgACC): -46, 38, 26
- **analysis_type:** both (whole-brain FWE cluster correction + small volume correction for a priori ROIs)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 41 recruited; N = 36 for behavioural analyses (16 female, age 18–36); N = 34 for parametric fMRI; N = 33 for stay/switch fMRI analysis
- **population_category:** healthy adults
- **population_age_range:** 18–36
- **ecological_validity:** Laboratory-based task with real electric shocks adding ecological validity to the aversive outcomes; however, the social interaction is minimal (participant never directly interacts with the stranger, and no shocks are delivered during scanning — 10% delivered post-scan). The two-step task is abstract and does not resemble real-world moral decision-making.
- **eligibility_flag:** 
- **concerns:** (1) This is a preprint (bioRxiv, July 2019) — should check whether a peer-reviewed published version exists and flag potential duplicate. (2) Sample size is modest (N=36 behavioural, N=33-34 fMRI). (3) The BICint model comparison for the pooled models (M5 vs M6 vs M7) does not strongly favour M6 — the authors themselves note "This does not support a strong conclusion" (Supplement Table 4), though BICint slightly prefers M6. (4) Hierarchical Bayesian fitting with separate priors for self/other may bias toward finding parameter differences (authors acknowledge this). (5) No shocks delivered during scanning — participants accumulated shocks for post-scan delivery, which may reduce the salience of outcomes.
- **limitations_reported:** Because of the nature of hierarchical fitting, which uses separate priors for self and other parameters, this method is somewhat biased towards finding differences"; task design measures relative balance rather than absolute levels of MB/MF; findings may not generalize to other social decisions (reward-based, monetary, non-human); model comparison for pooled data "does not support a strong conclusion"; individual difference correlations are from a modest sample and should be investigated in larger samples.
- **limitations_categorized:** model fitting bias; limited generalizability; task simplicity; weak model comparison evidence; sample size
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
- **flagged_fields:** - publication_type: MEDIUM — This is a bioRxiv preprint; a published version may exist (should check for duplicate with peer-reviewed version) - model_comparison (pooled): MEDIUM — Authors themselves note the BICint comparison does not strongly support one model; M6 only slightly preferred - coordinates_peak: HIGH — all coordinates directly reported in text - All other fields: HIGH
- **cannot_find:** No fields left blank. All information extracted from full text and supplement.
- **other_notes:** This paper is by Patricia Lockwood (one of the authors listed in the project). A peer-reviewed version of this preprint may have been published subsequently — this should be checked to avoid duplicate extraction. The paper provides a strong test of MB/MF arbitration in a social (moral) context. The Oxford Utilitarianism Scale and Harmful Action Outcome Scale correlation analyses are exploratory individual-difference findings. Data and code are openly available.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = partly
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MB
- tax_model_MB_MF_hybrid
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
- tax_rr_primary_topic = moral_harm
- tax_rr_secondary_topic = prosocial_altruism
- tax_rr_topic_moral_harm
- tax_rr_topic_prosocial_altruism
- tax_topic_moral_harm
- tax_topic_prosocial_altruism
