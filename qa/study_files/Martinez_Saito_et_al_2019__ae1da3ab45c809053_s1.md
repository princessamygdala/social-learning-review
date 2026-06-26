# Martinez-Saito et al. (2019)

- **study_id:** `ae1da3ab45c809053_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Martinez-Saito, M., Konovalov, R., Piradov, M. A., Shestakova, A., Gutkin, B., & Klucharev, V. (2019). Action in auctions: Neural and computational mechanisms of bidding behaviour. *European Journal of Neuroscience*, *50*(6), 3327–3348. https://doi.org/10.1111/ejn.14492
- **citation_short:** Martinez-Saito et al. (2019)
- **doi:** 10.1111/ejn.14492
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** School of Economics, Moscow, been widely used to model competition of individuals for resources, and bidding behav-; Centre for Cognition model bid is “nudged” depending on whether it was accepted or rejected, along with; University Ecole subjects (nine male) played a prototypical bidding game: a double action, with three; mittberger, & Schwarze, framework that is particularly suitable for bidding, directional; University Competition for resources is a fundamental characteristic of evolution; mits use, distribution and reproduction in any medium, provided the original; School of Economics, Mya
- **code_url:** 

## Computational level
- **study_focus:** Social competition learning / bidding behaviour learning under market competition
- **study_focus_short:** Social competition learning / bidding behaviour learning under market
- **learning_mode_description:** - Learning mode: Learning from binary transaction outcomes (accepted/rejected) about optimal bidding strategy under social competition   - Learning from:     - Source type (social): other (competing buyers and sellers — prerecorded human opponents)       - Market outcome depends on competitors' bids/ask prices     - Source content (non-social): outcome (binary accepted/rejected + profit if accepted)   - Learning about:     - Target type (non-social): world (market clearing price / optimal bid level)     - Target content (non-social): action/policy (preferred bid value per market type)
- **task_description:** Participants played the role of buyers in a double auction with first-price sealed bids across three market types differing in competition level (seller competition, no competition, buyer competition). On each trial, they selected a bid on a 101-point slider; if their bid exceeded the seller's ask price (and competing buyer's bid in BC), they received profit (10 minus bid); otherwise they received zero.
- **task_paradigm:** Ultimatum game
- **players:** Single agent (participant as buyer), multi-target (prerecorded human opponents; 1–2 sellers and 0–1 competing buyers depending on market type)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Market type labels (colour-coded), 101-point Likert bid scale, binary outcome feedback (accepted/rejected with profit)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - DL algorithms fit behaviour better than RL algorithms (all DL BIC scores lower than all RL BIC scores) - 74.99% of trials matched best DL algorithm predictions - DL-compliance score correlated with profit (r = 0.47, p = 0.011, 95% CI [0.12, 0.71]) - Market discrimination index (MDI) correlated with profit (r = 0.52, p = 0.003, 95% CI [0.20, 0.75]) - Bids decreased over time in SC (β = −0.027, t₅₈₈ = −4.44, p = 5.4×10⁻⁶) and increased in BC (β = 0.086, t₅₈₇ = 14.264, p = 4×10⁻⁴⁰) - Bayesian model comparison of neural data: P_exc(DL) = 0.95 > P_exc(RL) = 0.05 (BF > 19) - DS signal in posterior putamen (T = 7.90, MNI: −30, −10, 8; FWER p < 0.001) - Pseudo-RPE signal in NAcc/anterior putamen (T = 7.18, MNI: 12, 17, −11; FWER p < 0.001) - PPC encoded preferred bid value during choice (T = 3.99, MNI: −47, −48, 52) - Frontopolar PFC distinguished market types (T = 5.05, MNI: 21, 59, 19) - Two-way ANOVA (region × learning signal) interaction: F = 11.08, p = 0.0012
- **effect_size:** r = 0.47 (DL-compliance vs. profit); r = 0.52 (MDI vs. profit); BF > 19 (DL vs. RL neural model comparison)
- **learning_from:** Other (competitors' bids/ask prices via market outcome); outcome (binary accepted/rejected + profit)
- **learning_about:** World (market clearing price); action/policy (optimal bid per market type)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** DL delta rule with asymmetric leptokurtic noise (5 params: α, σₐ, σᵣ, σ₀, k)
- **model_family:** Heuristic
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "DL delta rule + leptokurtic jitter", "family": "Directional learning", "n_params": 5, "metric": "BIC"} 2. {"name": "DL delta rule + Gaussian jitter", "family": "Directional learning", "n_params": 2, "metric": "BIC"} 3. {"name": "Naive DL + leptokurtic jitter (nudge)", "family": "Directional learning", "n_params": 4, "metric": "BIC"} 4. {"name": "Model-based RL (counterfactual learning) + softmax", "family": "Rescorla-Wagner / counterfactual RL", "n_params": 2, "metric": "BIC"} 5. {"name": "Model-free RL (coarse bid space) + softmax", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"} 6. {"name": "Model-free RL + softmax", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"} 7. {"name": "Null model", "family": "Null", "n_params": 0, "metric": "BIC"}
- **model_mb_mf:** MB (DL requires model of action space structure — it is model-based in the sense it uses prior knowledge about bid ordering)
- **model_params:** - α = 0.53 (learning rate / gain for delta rule updating of preferred bid) - σₐ = 0.70 (Laplace distribution variance for accepted trials — above preferred bid) - σᵣ = 0.79 (Laplace distribution variance for rejected trials — below preferred bid) - σ₀ = 0.65 (Laplace distribution variance for other cases) - k = 0.39 (proportion of explorative vs. exploitative trials)  (Fixed-effects fitted values reported from Table 1)
- **social_param:** None explicitly designated as social. Market type recognition is handled by maintaining separate preferred bids per market condition, not by a dedicated social parameter.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion); also Bayesian model selection (exceedance probability) for neural model comparison
- **how_model_fit:** group-level-fit (fixed effects, yoked parameters across all 27 subjects; also checked with individual-level fits for consistency)
- **data_type_fit_to:** choice behavior (bid selections)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — DS and pseudo-RPE from best-fitting DL algorithm used as parametric modulators in GLM
- **contrast:** - DS signal at OUTCOME (posterior putamen; FWER p < 0.05) - Pseudo-RPE signal at OUTCOME (NAcc/anterior putamen; FWER p < 0.05) - Ort-DS (DS orthogonalized w.r.t. pseudo-RPE; posterior putamen) - Ort-pseudo-RPE (pseudo-RPE orthogonalized w.r.t. DS; caudate/ventral striatum, MFG, SPL) - CHOICE_PBV (preferred bid value at choice; left SPL) - MARKETxBC vs MARKETxNC (bilateral SPL) - MARKETxSC vs MARKETxNC (left SPL) - REJECTED vs ACCEPTED modulated by MDI (right SFG/frontopolar PFC) - ACCEPTED bid-increase modulated (dlPFC, striatum) - REJECTED bid-increase modulated (right putamen)
- **key_regions:** Binary directional signature (DS) in posterior putamen; pseudo-RPE in NAcc and anterior putamen; preferred bid value encoded in left superior PPC; market type discrimination in frontopolar PFC and vmPFC; bid adjustment signals in dlPFC and dorsal striatum.
- **key_regions_abbrev:** NAcc, putamen, dStr, striatum, vmPFC, mPFC, dlPFC, ACC
- **coordinates_peak:** DS: - Left Putamen: −30, −10, 8 (T = 7.90) - Right Putamen: 30, −10, 4 (T = 7.62) - Left Caudate: −24, −19, 23 (T = 7.30) - Right Caudate: 24, −10, 26 (T = 7.29) - Right SPL: 45, −43, 60 (T = 6.38)  Pseudo-RPE: - Right NAcc: 12, 17, −11 (T = 7.18) - Right Putamen: 21, 14, −11 (T = 7.16) - Right Putamen: 30, −13, 8 (T = 6.87) - Left SMG: −57, −34, 45 (T = 6.81) - Left MFG: −36, 35, 30 (T = 6.66)  Ort-DS: - Left Caudate: −27, −7, 26 (T = 5.36) - Right Caudate: 24, −10, 26 (T = 5.06)  Ort-pseudo-RPE: - Left MFG: −24, 20, 63 (T = 5.14) - Left SPL: −21, −46, 45 (T = 4.58)  CHOICE_PBV: - Left SPL: −47, −48, 52 (T = 3.99)  Market type (BC vs NC): - Left SPL: −33, −46, 48 (T = 5.31) - Right SPL: 36, −46, 60 (T = 4.55)  MDI-modulated (REJECTED vs ACCEPTED): - Right SFG (frontopolar): 21, 59, 19 (T = 5.05)  ACCEPTED bid-increase: - Right Putamen: 18, 8, −11 (T = 5.13) - Right Caudate: 18, 5, 19 (T = 5.21) - Left MFG: −30, 41, 34 (T = 4.62)  REJECTED bid-increase: - Right Putamen: 24, 14, −3 (T = 4.19)
- **analysis_type:** both (whole-brain at FWER p < 0.05 for DS/pseudo-RPE; ROI analysis for striatum subdivisions and PPC; exploratory whole-brain at p < 0.001 uncorrected for orthogonalized contrasts)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 27 (9 male, 2 left-handed; after excluding 2 of 29 for excessive head motion); ages not reported
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate. Double auction is a standard economic paradigm with real monetary incentives. However, opponents were prerecorded (not live), which limits real-time social interaction. The market types are simplified relative to real markets. The task does capture key features of competitive bidding.
- **eligibility_flag:** Borderline — learning occurs over repeated trials and is computational, but the "social" element is limited: opponents are prerecorded humans replayed by computer, and what is learned is market clearing price (a non-social quantity), not properties of social agents per se. The competition context is social, but the learning target is non-social (optimal bid). Flag as: social agent is automated/prerecorded; learning target is arguably non-social (market price/bidding strategy).
- **concerns:** - Opponents were prerecorded, not live — limits social interaction - Fixed-effects model fitting (yoked parameters) prevents individual differences analysis in model parameters - Only 24 trials per market type per subject — limited data for fitting 101-action-space models - Some RL model fits did not converge for individual subjects - Exploratory whole-brain analyses at p < 0.001 uncorrected have inflated false-positive rates (acknowledged by authors) - Ages of participants not reported - Table 1 is garbled in the text extraction (reversed text), but BIC values and parameter estimates were recoverable from the text
- **limitations_reported:** Used prerecorded opponent data which may not allow disentangling market-based prior strategies from feedback-based learning; studies using live opponents eschew this limitation but cannot control for variability induced by repeated mutual feedback; further studies needed to verify role of feedback-based learning in double auctions.
- **limitations_categorized:** Limited ecological validity (prerecorded opponents); limited social interaction; task simplicity; limited generalizability
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - social_param: MEDIUM — no explicit social parameter; market type separation is structural, not parameterized as social - eligibility_flag: MEDIUM — social context is present (competition with other humans) but learning target is non-social - model_mb_mf: MEDIUM — DL is described as model-based (requires prior knowledge of action space structure) but is not MB in the standard MB/MF RL sense - sample_size (ages): LOW — participant ages not reported in accessible text - Table 1 parameters: MEDIUM — table text was garbled/reversed; parameter values extracted from readable portions
- **cannot_find:** - Participant age range (not reported in accessible text) - Supplement (referenced as "Additional supporting information" but no supplement file available) - Individual-level BIC scores (only group-level fixed-effects BIC reported)
- **other_notes:** - The paper makes an important distinction between directional learning (action-space updating) and reinforcement learning (value-space updating). DL is not a standard RL model — it updates a preferred bid directly rather than maintaining an action-value function. - Data and code are openly available (GitHub + OpenNeuro). - The paper mentions supporting information exists online but no supplement file was found in the papers folder. Model equations and coordinates were all in the main text. - Neural model comparison (BMS) was also performed, showing DL explains striatal activity better than RL (exceedance probability 0.95 vs 0.05).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = general
- spec_locus = source
- spec_neural = shared
- spec_source = partly
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MB
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = heuristic
- tax_rr_model_heuristic
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = competition
- tax_rr_topic_competition
- tax_topic_competition
