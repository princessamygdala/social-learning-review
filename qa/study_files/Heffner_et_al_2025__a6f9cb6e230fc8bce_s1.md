# Heffner et al. (2025)

- **study_id:** `a6f9cb6e230fc8bce_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Heffner, J., Frömer, R., Nassar, M. R., & FeldmanHall, O. (2025). Separable neural signals for reward and emotion prediction errors. *Nature Communications*, 16, 7849. https://doi.org/10.1038/s41467-025-63135-5
- **citation_short:** Heffner et al. (2025)
- **doi:** 10.1038/s41467-025-63135-5
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ethatthebrainfunctionsasaprediction where participants (N=41) interacted with three different partner; ethat emotion serves asa toinferparticipants’rewardexpectations30,31,weaskedthemtoreport; centersaroundwhatexactlyisrewardandhowdoesthe shotchoicesduringasocialexchangetask19; etherthey agnosticastowhichneuralsignalwouldpreferentiallyindexreward; etheterm ationalizedaffectwithinanRLframework,whichledtothehypoth-; ethatthebrainprocessesnotonlyrewardPEsbut neutral;seeMethodsandFig; CentreforHumanBrainHealth,UniversityofBirmingham,Birmingham,UK; etherthereisneuralseparabilitybetweenemotionandrew
- **code_url:** https://github.com/jpheffne/2025_epe_eeg

## Computational level
- **study_focus:** Social learning; affective prediction error learning; emotion-reward dissociation in social exchange
- **study_focus_short:** Social learning · affective prediction error learning
- **learning_mode_description:** - Learning mode: Learning from monetary offers and emotional reactions about partner fairness/trustworthiness during a repeated social exchange   - Learning from:     - Source type (social): other (partner proposer)       - Source content (non-social): outcome (monetary offer)     - Source type (non-social): self       - Source content (social): state (mental state; affective experience — valence and arousal)   - Learning about:     - Target type (social): other (partner proposer)       - Target content (social): state (mental state; partner's fairness/behavioral tendencies)     - Target type (non-social): self       - Target content (social): state (mental state; own affective reactions to partner)
- **task_description:** Participants played a repeated Ultimatum Game with 36 unique partners (12 fair, 12 neutral, 12 unfair), interacting for 5 rounds per partner. On each trial, participants reported reward expectations and affect predictions before receiving an offer, then reported affective experience and decided to accept or reject.
- **task_paradigm:** Ultimatum game
- **players:** Single agent (participant), multi-target (36 partners; 12 per type: fair, neutral, unfair)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Faces from MR2 database, monetary offers ($0-$10), 2D affect grid (valence x arousal)
- **method:** EEG
- **method_full:** EEG
- **main_result:** - Valence PEs independently predict punishment decisions more strongly than reward PEs, especially under high uncertainty (first round) (valence PE: β = -0.76, z = -6.65; reward PE: β = -0.67, z = -4.75) - Valence PE influence on choice diminishes over rounds as uncertainty decreases (valence PE x round: β = 0.08, z = 2.30) - FRN is consistently linked to reward PEs (conditional: β = -0.04, t = -2.75; unconditional: p = 0.047) - P3b is consistently linked to valence PEs (conditional: β = 0.06, t = 3.98; unconditional: p < 0.001) - P3b is the only ERP predicting choice (β = 0.29, z = 3.30), with an attenuating effect over rounds (P3b x round: β = -0.07, z = -2.65) - Mass univariate analysis reveals separable spatiotemporal clusters: valence PEs in parietal areas (460-670ms), reward PEs in frontal areas (326-790ms) - Reward PEs are resolved by adjusting expectations; affective PEs are managed by aligning emotional experiences with predictions
- **effect_size:** - Valence PE on choice: β = -0.76 (95% CI [-1.00, -0.53]) - Reward PE on choice: β = -0.67 (95% CI [-0.96, -0.38]) - Valence PE x Round on choice: β = 0.08 (95% CI [0.01, 0.14]) - P3b on choice: β = 0.29 (95% CI [0.12, 0.47]) - P3b x Round on choice: β = -0.07 (95% CI [-0.12, -0.02]) - FRN ~ reward PE (conditional): β = -0.04 (95% CI [-0.06, -0.01]) - P3b ~ valence PE (conditional): β = 0.06 (95% CI [0.03, 0.09]) - Round 1-2 reward expectation update (unfair partner): d = -2.73 (95% CI [-3.56, -1.90]) - Round 1-2 valence expectation update (unfair partner): d = -1.78 (95% CI [-2.32, -1.23])
- **learning_from:** Other's monetary offers (reward) and self's affective reactions (valence, arousal); source: other (partner) + self
- **learning_about:** Partner's behavioral tendencies (fairness) and own emotional responses; target: other (partner) + self  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Empirical prediction error model (no formal computational model fitted). Reward PE = offer - reward expectation; Valence PE = valence experience - valence expectation; Arousal PE = arousal experience - arousal expectation. These empirical PEs entered as predictors in generalized linear mixed-effects models predicting choice.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** No formal model comparison was conducted. The study uses empirically computed prediction errors (reward PE, valence PE, arousal PE) as regressors in linear mixed-effects models. Multiple regression specifications were tested (conditional vs. unconditional, signed vs. unsigned PEs, with/without experience controls), but these are statistical models, not competing computational models of learning.
- **model_mb_mf:** N/A (not RL; descriptive PE computation)
- **model_params:** - No fitted computational model parameters. The "model" consists of empirical prediction errors computed from self-report:   - δ (reward PE) = offer received - reward expectation (reported by participant)   - ν (valence PE) = valence experience - valence expectation (reported by participant)   - α (arousal PE) = arousal experience - arousal expectation (reported by participant) - These are entered as predictors in GLMMs with random effects structures. No learning rate or other RL parameters are fitted.
- **social_param:** Valence PE (ν) and arousal PE (α) — affective prediction errors that capture the social-emotional dimension of learning about partners [S]. These are the key "social parameters" distinguishing this approach from standard reward-only PE models.
- **social_param_name:** Valence PE
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Conditional R-squared for GLMMs (reported for additive vs. separate PE models: R² = 0.63 vs. 0.65). No formal model comparison metric (BIC, AIC, etc.) for competing computational models.
- **how_model_fit:** params-calculated-independently (PEs computed directly from self-report, not fitted)
- **data_type_fit_to:** choice behavior (accept/reject decisions), EEG ERP amplitudes (FRN, P3a, P3b)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (EEG study; ERP analysis + mass univariate analysis)
- **contrast:** - FRN ~ absolute reward PE (fronto-central ROI, 315-415ms): β = -0.04, t = -2.75 - P3b ~ absolute valence PE (parietal ROI, 530-630ms): β = 0.06, t = 3.98 - P3b ~ signed reward PE (parietal ROI): β = -0.04, t = -2.74 - Mass univariate: valence PE cluster (460-670ms, parietal), reward PE cluster (326-790ms, frontal) - P3b predicting choice: β = 0.29, z = 3.30 - P3b x Round predicting choice: β = -0.07, z = -2.65
- **key_regions:** FRN (fronto-central: F3, Fz, F4, FC3, FCz, FC4, C3, Cz, C4) indexes reward PEs; P3b (parietal: CP1, CPz, CP2, P1, Pz, P2, PO3, POz, PO4) indexes valence PEs and predicts choice; P3a (fronto-central) linked to offer extremity.
- **key_regions_abbrev:** parietal
- **coordinates_peak:** unavailable — EEG study; scalp electrode locations reported but no MNI coordinates (not applicable for EEG)
- **analysis_type:** N/A (EEG, not neuroimaging; ROI-based ERP analysis + mass univariate whole-scalp analysis)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 41 (25 female; mean age = 20.8 +/- 4.4 years)
- **population_category:** healthy adults
- **population_age_range:** M=20.8
- **ecological_validity:** Moderate ecological validity concerns. Partners were described as past participants but were actually computer-generated from fixed distributions. Monetary offers ranged $0-$10 but were drawn from narrow normal distributions (SD = $0.50). The affect grid is a validated measure of subjective feeling but is inherently reductive. The Ultimatum Game is well-established in behavioral economics but simplifies real social exchange. 5 rounds per partner limits learning trajectory length. Age distribution skews younger (university sample).
- **eligibility_flag:** FLAG — The paper does not fit a formal computational model to data. It computes empirical prediction errors directly from participant self-reports and uses them as regressors in GLMMs. There is no fitted RL or Bayesian model. The paper clearly involves social learning over time, and the PE framework is conceptually computational, but no computational model is formally specified, fitted, or compared. This is borderline for "uses computational modeling" inclusion criterion.
- **concerns:** - No formal computational model is fitted — PEs are computed directly from self-report expectations and experiences, not from a learning model - No model comparison of alternative computational models - Reward expectations are elicited directly from participants rather than estimated from a computational model, which means the "prediction errors" are empirical rather than model-derived - Valence expectations and experiences are both self-reported, introducing potential confound (experience may already reflect PE) - Partners are not real past participants (deception) - No formal RL model fitted means no learning rate parameters estimated - Sample skews young (university students) - No correction for multiple comparisons in most analyses
- **limitations_reported:** It is notoriously difficult to dissociate emotion and reward"; sample's age distribution was not representative and skewed younger; study was not powered to detect sex-based differences; valence expectation and experience are both self-reported, meaning "the participant's valence experience may already be in relation to their expectations, and thus could potentially already represent part of the affective PE"; "there could of course be other candidate variables that are interrelated, such as confidence or state uncertainty estimation"; neural ERPs were largely predicted by unsigned PEs, and the transformation from unsigned to signed PEs remains unexplored; broader manipulations of outcome stochasticity, volatility, and temporal structure are needed in future work
- **limitations_categorized:** difficulty dissociating constructs; limited generalizability (age); underpowered for subgroup analyses; construct validity (self-report confound); omitted variables; limited mechanistic understanding (unsigned-to-signed PE transformation); task simplicity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 3.5
- **wc_total:** 3.5

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `winning_model`: LOW — No formal computational model fitted; "model" is empirical PE computation + GLMM regression - `model_family`: LOW — Described as "prediction error" but no formal model (e.g., Rescorla-Wagner) is specified or fitted - `model_class`: LOW — Classified as "prediction error learning" but the PEs are empirically computed, not model-derived - `eligibility_flag`: MEDIUM — Borderline for inclusion criterion "uses computational modeling"; the PE framework is conceptually computational but no model is formally fitted - `model_comparison_metric`: LOW — No formal model comparison conducted - `social_param`: MEDIUM — Valence and arousal PEs are the social-affective parameters but are not parameters of a computational model
- **cannot_find:** - Formal computational model specification (none exists — by design, the study uses empirical PEs) - Model comparison metrics (BIC, AIC, etc.) — not applicable - Fitted learning rate or other computational model parameters - MNI coordinates — not applicable (EEG study)
- **other_notes:** This is an EEG study published in Nature Communications (2025) that makes an important contribution to understanding the role of affective prediction errors in social learning. The key novelty is demonstrating neural separability (FRN vs P3b) between reward and affective PEs during social exchange. However, the study does not fit a formal computational model — it relies entirely on empirically computed PEs from self-report and uses these as predictors in statistical models. This places it at the boundary of inclusion for a review of "computational models of social learning." The paper explicitly contrasts its approach with formal RL models and argues for the importance of incorporating emotion into computational frameworks, but does not itself implement such a framework. If included, it should be noted as using a descriptive PE approach rather than a fitted computational model. The paper cites Heffner, Son, & FeldmanHall (2021) as prior work using the same paradigm in a behavioral context, and the current study extends this to EEG.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_neural = shared
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_primary_topic = reputation_learning
- tax_rr_secondary_topic = fairness_inequity
- tax_rr_topic_fairness_inequity
- tax_rr_topic_reputation_learning
- tax_topic_fairness_inequity
- tax_topic_reputation_learning
