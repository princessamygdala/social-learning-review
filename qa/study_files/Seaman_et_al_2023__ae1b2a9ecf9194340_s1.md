# Seaman et al. (2023)

- **study_id:** `ae1b2a9ecf9194340_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Seaman, K. L., Christensen, A. P., Senn, K. D., Cooper, J. A., & Cassidy, B. S. (2023). Age-related differences in the social associative learning of trust information. *Neurobiology of Aging*, *125*, 32–40. https://doi.org/10.1016/j.neurobiolaging.2023.01.011
- **citation_short:** Seaman et al. (2023)
- **doi:** 10.1016/j.neurobiolaging.2023.01.011
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Center for Vital Longevity, University of Texas at Dal- by the investor is considered an indication of trust; Department of Psychiatry and Behavioral Sciences, Emory University School of Medicine, Atlanta, GA, USA; Department of Psychology, University of North Carolina at Greensboro, Greensboro, NC, USA; Department of Psychology and Human Development, Vanderbilt University, Nashville, TN, US; School of Social Work, University of North Carolina-Chapel Hill, Chapel Hill, NC, USA; Center for Vital Longevity, University of Texas at Dallas, Dallas, TX, USA; Department of Psychology, University of T
- **code_url:** https://osf.io/b3au5

## Computational level
- **study_focus:** Trust learning — age-related differences in how younger and older adults learn partner trustworthiness through repeated interaction in an iterated trust game.
- **study_focus_short:** Trust learning
- **learning_mode_description:** - Learning mode: Learning from partner's reciprocation/defection outcomes about partner's trustworthiness over repeated interactions   - Learning from:     - Source type (social): other (trust game partner)     - Source content (social): outcome (reciprocation or defection by partner)   - Learning about:     - Target type (social): other (trust game partner)     - Target content (social): state (mental state; trustworthiness / probability of reciprocation)
- **task_description:** Participants played an iterated trust game with 3 partners (trustworthy [93% reciprocation], neutral [60%], untrustworthy [7%]) over 45 trials (15 per partner). On each trial, participants chose how much of a $9 endowment to share; shared amounts were quadrupled, and the partner chose to reciprocate half or keep all.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (3 fictitious partners varying in trustworthiness)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Face photographs with names representing partners, monetary endowments ($0/$3/$6/$9 sharing options), binary feedback (reciprocate/keep)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Older adults shared more with untrustworthy partners than younger adults (t = 4.25, p = .001; confidence: HIGH) - Age Group x Partner Type interaction on sharing: significant for neutral (b = -1.07, 95% CI [-1.63, -0.51]) and untrustworthy (b = -1.29, 95% CI [-1.90, -0.69]) contrasts (confidence: HIGH) - Age Group x Partner Type x Experience three-way interaction: older adults showed blunted learning slopes relative to younger adults for untrustworthy partner (b = -0.52, 95% CI [-0.79, -0.25]) (confidence: HIGH) - Marginal R² = 0.270, Conditional R² = 0.531 for behavioral mixed model (confidence: HIGH) - No age-related differences in gain or loss learning rates from computational model (ps > .05) (confidence: HIGH) - ~1/3 of older adults (N = 11) best fit by baseline (non-learning) model (confidence: HIGH) - Older adult learners > non-learners: greater reputation-related activity in R angular gyrus (48, -36, 24; t = 4.02) and R parahippocampal gyrus (24, -20, -18; t = 3.59) during decision phase (confidence: HIGH) - Prediction error positively related to striatum, insula, and frontal regions across all participants (confidence: HIGH) - Post-experiment likability: younger adults differentiated partners (η² = 0.426); older adults did not (η² = 0.059) (confidence: HIGH) - Sharing-likability correlation: younger adults r = .720, older adults r = .235; difference z = 4.51, p < .001 (confidence: HIGH)
- **effect_size:** See inline above. Key: Marginal R² = 0.270; η² = 0.426 (younger partner differentiation); η² = 0.138 (age x partner interaction on likability); r = .720 (younger sharing-likability); r = .235 (older sharing-likability)
- **learning_from:** Other (partner); reciprocation/defection outcomes in trust game
- **learning_about:** Other (partner); trustworthiness (probability of reciprocation)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Gain-loss learning model (RW-type, 2 LRs: α_gain, α_loss; 1 β; softmax decision)  Formula: p_i(t) = p_i(t-1) + α_gain * max(γ - p_i(t-1), 0) + α_loss * min(γ - p_i(t-1), 1), where γ = 1 (partner shares) or 0 (partner keeps). EV_ai(t) = p_i(t) * v_i(t) + v_r(t). Choice via softmax with β.  Fitted values (means): - Younger: α_gain = 0.16 (SD = 0.29), α_loss = 0.27 (SD = 0.34), β = 10.81 (SD = 9.65) - Older: α_gain = 0.25 (SD = 0.38), α_loss = 0.30 (SD = 0.37), β = 7.95 (SD = 9.39)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. Baseline model (random/equal probability) — 0 free params — AIC: 129.51 (YA), 128.04 (OA); BIC: 126.71 (YA), 125.22 (OA) 2. General learning model (single α, β) — 2 free params — AIC: 95.94 (YA), 111.99 (OA); BIC: 96.93 (YA), 112.95 (OA) 3. Gain-loss learning model (α_gain, α_loss, β) — 3 free params — AIC: 87.11 (YA), 104.68 (OA); BIC: 91.89 (YA), 109.42 (OA) **[WINNER]** 4. Forgetting general learning model (α, β, φ) — 3 free params — described in supplement, did not provide good fit 5. Forgetting gain-loss learning model (α_gain, α_loss, β, φ) — 4 free params — described in supplement, did not provide good fit 6. Initial beliefs gain-loss learning model (α_gain, α_loss, β, p_initial_trustworthy, p_initial_neutral, p_initial_untrustworthy) — 6 free params — described in supplement, did not provide good fit
- **model_mb_mf:** MF
- **model_params:** - α_gain [S]: learning rate for gains (partner reciprocates). Mean: YA = 0.16, OA = 0.25 - α_loss [S]: learning rate for losses (partner defects). Mean: YA = 0.27, OA = 0.30 - β: softmax inverse temperature (decision noise). Mean: YA = 10.81, OA = 7.95 - p_i(0) = 0.5 (fixed initial probability, not free)
- **social_param:** α_gain and α_loss — learning rates for updating perceived trustworthiness (probability of partner reciprocation) following positive (gain) and negative (loss) social feedback.
- **social_param_name:** α_gain
- **social_param_value:** 0.16
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC, BIC
- **how_model_fit:** individual-level-fit (scipy.optimize in Python)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors — reputation at decision phase, prediction error at feedback phase)
- **contrast:** - Reputation (probability of reciprocation) as parametric modulator during decision phase: all participants, YA > OA, OA > YA, OA learners > OA non-learners - Prediction error as parametric modulator during feedback phase: all participants, YA > OA, OA > YA, OA learners > OA non-learners - Threshold: p < .005, k = 50 (exploratory)
- **key_regions:** Reputation during decision: L middle occipital gyrus (all); R IFG (OA > YA); R angular gyrus and R parahippocampal gyrus/hippocampus (OA learners > non-learners). Prediction error during feedback: fusiform, insula, putamen, frontal regions (all); L hippocampus (OA > YA); L superior temporal gyrus (OA non-learners > learners).
- **key_regions_abbrev:** putamen, insula, hippocampus, FFA, IFG
- **coordinates_peak:** Reputation — All participants: - L middle occipital gyrus: -30, -74, 36  Reputation — YA > OA: - R lingual gyrus: 16, -78, 2  Reputation — OA > YA: - R inferior frontal gyrus: 52, 28, 24  Reputation — OA learners > OA non-learners: - L postcentral/supramarginal gyrus: -50, -20, 26 - R superior temporal/angular gyrus: 48, -36, 24 - L angular gyrus/middle temporal: -46, -52, 26 - R parahippocampal gyrus/hippocampus: 24, -20, -18 - L precuneus/cuneus: -2, -60, 28  Reputation — OA non-learners > OA learners: - L superior temporal gyrus/pole: -44, -8, -8 - L middle cingulate gyrus: -10, -44, 36 - R cuneus/superior occipital/precuneus: 18, -66, 32  Prediction error — All participants: - L fusiform gyrus: -46, -56, -16 - R middle occipital gyrus: 30, -92, 2 - L precentral/IFG: -40, 2, 36 - R superior frontal/IFG: 28, 10, 64 - L insula/putamen: -30, 16, -4 - L superior frontal gyrus: -20, 26, 56  Prediction error — OA > YA: - L superior occipital/cuneus: -20, -78, 20 - L superior/middle temporal gyrus: -50, -18, 4 - R inferior temporal/lingual/middle temporal: 46, -66, -8 - R precentral gyrus: 42, -6, 52 - L hippocampus: -22, -36, 8
- **analysis_type:** whole-brain  ---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 63 (33 younger adults, M_age = 22.45, SD = 3.62, range 19–32, 19 female; 30 older adults, M_age = 69.27, SD = 5.49, range 61–80, 21 female). For exploratory imaging: 1 older adult excluded (scanner error), yielding N = 62 for fMRI. OA learners N = 19, OA non-learners N = 11.
- **population_category:** mixed
- **population_age_range:** 19–32
- **ecological_validity:** Moderate. Uses an iterated trust game with face stimuli representing partners, which captures repeated social learning. However, partners are fictitious (pre-programmed reciprocation probabilities), interaction is not face-to-face, and outcomes are monetary rather than capturing full range of trust-related consequences.
- **eligibility_flag:** 
- **concerns:** - Exploratory fMRI analyses used liberal threshold (p < .005, k = 50, uncorrected) — findings should be interpreted cautiously - OA learner vs. non-learner comparison is notably unbalanced (N = 19 vs. N = 11) and underpowered, as authors themselves acknowledge - No age-related differences in computational model parameters despite clear behavioral differences — model may lack sensitivity - Model parameter recovery was moderate (α_gain: r = .68; α_loss: r = .55; β: r = .41) — β recovery relatively weak - Partners were all younger men, introducing potential in-group/out-group confound for older adults
- **limitations_reported:** Our notably unbalanced and underpowered analysis comparing older learners to older non-learners does not support this compensatory interpretation"; "these analyses are exploratory and are intended to inform future work"; "these analyses are not corrected for multiple comparisons, and only one would survive correction for multiple comparisons"; authors note partners were all younger men creating potential age group in-group confound
- **limitations_categorized:** underpowered subgroup comparison; uncorrected multiple comparisons; exploratory analyses; limited generalizability (partner demographics); task simplicity (fictitious partners)
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 10
- **wc_total:** 10.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - Fit statistics for models 4–6 (forgetting and initial beliefs models): not reported numerically in text or supplement — flagged as MEDIUM confidence that they were inferior (authors state "did not provide a good fit") - β parameter recovery relatively weak (r = .41) — noted but not flagged by authors
- **cannot_find:** Exact AIC/BIC values for forgetting general learning model, forgetting gain-loss learning model, and initial beliefs gain-loss learning model (supplement states they "did not provide a good fit" but does not report numeric fit statistics for these three models)
- **other_notes:** This is a well-conducted study with strong adherence to Wilson & Collins guidelines (all 10 criteria met). The study is preregistered and data/code are shared. The computational modeling is relatively standard (RW-type) but the application to aging differences in trust learning is novel. The key finding is that ~1/3 of older adults are best fit by a non-learning (baseline) model, and that older adult learners show stronger reputation signals in mentalizing/memory regions (angular gyrus, parahippocampal gyrus) during decision-making.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_older_adults
- rr_pop_healthy_adults
- rr_pop_older_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_param_valence_asymmetry
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = trust
- tax_rr_secondary_topic = reputation_learning
- tax_rr_topic_reputation_learning
- tax_rr_topic_trust
- tax_topic_reputation_learning
- tax_topic_trust
