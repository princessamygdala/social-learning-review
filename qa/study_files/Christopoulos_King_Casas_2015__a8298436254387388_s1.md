# Christopoulos & King-Casas (2015)

- **study_id:** `a8298436254387388_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Christopoulos, G. I., & King-Casas, B. (2015). With you or against you: Social orientation dependent learning signals guide actions made for others. *NeuroImage*, *104*, 326–335. https://doi.org/10.1016/j.neuroimage.2014.09.011
- **citation_short:** Christopoulos & King-Casas (2015)
- **doi:** 10.1016/j.neuroimage.2014.09.011
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** lableonline16September2014 value-basedpredictionerrorsforoutcomestooneself;also,recentworksuggeststhatneuralactivityinprefrontal; etheritbeforagingforfoodor theiractionsandtheirenvironment,anddopaminergicsignalingisbe-; DepartmentofPsychiatry,VirginiaTechCarilionSchoolofMedicine,Roanoke,VA,USA; lableoptions lievedtounderlietheselearningsignals(BayerandGlimcher,2005;; School,NanyangTechnologicalUniversity,50NanyangAvenue,639798,Singapore; UniversitySchoolofBiomedicalEngineeringandSciences,Blacksburg,VA,USA; ethatsocialdecisionsareguidedbyasocialorientation-dependent; DepartmentofPsychology,Virg
- **code_url:** 

## Computational level
- **study_focus:** Social orientation-dependent reward learning for others; how cooperative vs. competitive social value orientation modulates reinforcement learning signals when actions produce outcomes for both self and a social partner.
- **study_focus_short:** Social orientation-dependent reward learning for others
- **learning_mode_description:** - Learning mode: Learning from one's own choice outcomes (for self and for an anonymous other) about the value of actions that produce consequences for both self and other, modulated by social value orientation.   - Learning from:     - Source type (non-social): self       - (choices made by participant)     - Source content (non-social): outcome       - (monetary outcomes for self)     - Source content (social): outcome       - (monetary outcomes delivered to other)   - Learning about:     - Target type (social): other (anonymous partner)       - Target content (social): outcome (value of actions for other, weighted by social orientation)     - Target type (non-social): self       - Target content (non-social): outcome (value of actions for self)
- **task_description:** Participants chose between two fractal stimuli probabilistically (80:20) associated with monetary gains or losses for themselves and an anonymous social partner across six conditions varying the magnitude and valence of self- and other-outcomes. Social value orientation (cooperative, individualistic, competitive) was assessed separately via a parametric estimation by sequential testing (PEST) procedure.
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), single anonymous other (passive recipient)
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Abstract fractals, monetary outcomes (±$70 ± noise) for self and other
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - PE_S correlated with bilateral ventral striatum activity across all conditions (peak: 4, 10, -4; p < .01 FWE whole-brain corrected) - PE_O (preference-dependent) correlated with mPFC activity (peak: 10, 54, 0; p < .01 FWE whole-brain corrected) - Region x PE type interaction: F(1,71) = 9.3, p < .005, confirming double dissociation between striatum (PE_S) and mPFC (PE_O) - SVO correlated with mPFC BOLD response difference at 4s post-outcome (r = .37, p < .005) - SVO correlated with model-free logistic regression beta for other-outcomes (R² = .22, p < .001) - Cooperative individuals: negative mPFC response to positive PE_O; Competitive individuals: positive mPFC response to positive PE_O - Winning model (with gamma) AIC = 531.08 vs. model without gamma AIC = 558.6
- **effect_size:** - Region x PE type interaction: F(1,71) = 9.3 - SVO-BOLD correlation: r = .37 - SVO-model-free correlation: R² = .22 - Mean pseudo-R² for winning model: .32
- **learning_from:** Self and other; monetary outcomes of own choices for oneself and for an anonymous social partner
- **learning_about:** Other (anonymous partner); value of actions for social partner, weighted by social orientation (gamma parameter)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Hybrid Q-learning with separate self/other PE and social orientation weighting: EV_S updated by α_S * PE_S; EV_O updated by α_O * PE_O where PE_O = γ(V_O) - EV_O; choice via softmax on EV_NET = EV_S + EV_O with temperature β. γ = +1 or -1 (cooperative/competitive).
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Hybrid model (γ = ±1)", "family": "Q-learning", "n_params": 19, "metric": "AIC = 531.08"} - {"name": "Alt (i): γ free in [-1,1]", "family": "Q-learning", "n_params": 19, "metric": "AIC = 533.5"} - {"name": "Alt (ii): No γ", "family": "Q-learning", "n_params": 18, "metric": "AIC = 558.6"} - {"name": "Alt (iii): Single bundled value (V_tot = V_self + γV_other)", "family": "Q-learning", "n_params": 13, "metric": "AIC = 562.40"} - {"name": "Alt (iv): γ = 0 (ignore other)", "family": "Q-learning", "n_params": 12, "metric": "AIC = 561.85"} - {"name": "Alt (v): Single α for self and other", "family": "Q-learning", "n_params": 13, "metric": "AIC = 563.37"}
- **model_mb_mf:** MF
- **model_params:** - α_S: learning rate for self-outcomes (mean values vary by condition and SVO group; e.g., Condition A cooperative: 0.512, individualistic: 0.348, competitive: 0.297) - α_O: learning rate for other-outcomes (mean values vary by condition and SVO group; e.g., Condition A cooperative: 0.395, individualistic: 0.357, competitive: 0.279) - β: temperature/inverse temperature parameter (mean values vary; e.g., Condition A cooperative: 0.472, individualistic: 0.194, competitive: 0.231) - γ [S]: social orientation weighting parameter, takes values +1 (cooperative) or -1 (competitive); transforms other-value prediction error according to social preference
- **social_param:** γ (gamma) — social orientation weighting parameter that transforms monetary outcomes received by the social partner according to the decision-maker's cooperative (+1) or competitive (-1) orientation. Positive γ means positive other-outcomes produce positive PE_O; negative γ reverses this.
- **social_param_name:** γ
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (Akaike Information Criterion); also pseudo-R² for model fit assessment. AIC = 2k - 2Log(L).
- **how_model_fit:** individual-level-fit (parameters estimated per subject; γ estimated from two conditions then held constant for remaining four; α_S, α_O, β estimated per block)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — PE_S and PE_O from computational model used as parametric modulators of outcome phase in GLM
- **contrast:** - PE_S parametric modulator at outcome phase: ventral striatum (4, 10, -4; p < .01 FWE whole-brain corrected) - PE_O parametric modulator at outcome phase: mPFC (10, 54, 0; p < .01 FWE whole-brain corrected) - PE_O × SVO correlation at mPFC (r = .37, p < .005) - Region × PE type interaction (F(1,71) = 9.3, p < .005)
- **key_regions:** Self-value PE in bilateral ventral striatum; preference-dependent other-value PE in anterior rostral mPFC (arMPC); SVO modulates magnitude and direction of mPFC PE_O signal.
- **key_regions_abbrev:** VS, striatum, mPFC
- **coordinates_peak:** PE_O across all conditions combined: - Frontal Sup Medial R (mPFC): 10, 54, 0 - Insula R: 42, 18, -12 - BA 13: 22, 16, -12 - Frontal Mid R: 22, 56, 28 - BA 25: 2, 6, -6  PE_S across all conditions combined: - Caudate R (ventral striatum): 4, 10, -4 - Putamen L: -8, 8, -8 - Extra-Nuclear: 28, -24, 2 - Fusiform R: 28, -40, -10 - Parahippocampal L: -30, -34, -12 - Caudate L: -12, 20, 10 - Cuneus R: 12, -88, 26 - Cerebellum Crus 1 R: 38, -58, -30 - Amygdala L: -19, -2, -11  PE_O Condition C [S+/O- vs S+/O+]: - Frontal Sup Medial R: 4, 60, 14 - Frontal Sup Medial L: 0, 52, 8 - Precuneus R: 11, -50, 26  PE_O Condition D [S-/O- vs S-/O+]: - Frontal Sup Medial R: 12, 58, 12 - Frontal Sup L: -14, 60, 16 - Precuneus R: 22, -42, 2  Individual condition PE_S peaks (from Fig 3a): - Condition A: 6, 4, -4 - Condition B: -8, 20, -2 - Condition E: 16, 6, -8 - Condition F: -14, -2, 6
- **analysis_type:** whole-brain  ---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 90 recruited; 10 excluded for unreliable SVO; 7 excluded for excessive movement; 1 excluded for missing responses; 1 condition of 1 subject excluded. Final N = 72 for neuroimaging analysis. Mean age 27.37 years; 28 female.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low ecological validity. Anonymous, non-interactive partner; participant never meets or learns identity of other; partner makes no decisions affecting participant. Highly controlled lab task with abstract fractal stimuli and fixed monetary outcomes. No real social interaction. SVO measured separately and treated as stable trait.
- **eligibility_flag:** 
- **concerns:** - γ parameter restricted to binary values (+1 or -1), which is a strong assumption that may not capture the full range of social orientations (individualists forced to average of -1 and +1) - SVO group boundaries defined by mean ± 0.5 SD, which is arbitrary - No parameter recovery or model recovery analyses reported - No simulation of model before fitting - AIC used for model comparison but authors note AIC cannot capture the reduced parameter space of the winning model (γ restricted to ±1 vs. free) - Participants may have inferred task structure beyond simple RL - mPFC PE_O signal shows negative coding (preference-incongruent outcomes increase BOLD), functional interpretation speculative
- **limitations_reported:** The present design does not exhaustively examine how V_s and V_o are integrated in the human brain; alternative models including fairness or inequity considerations could make similar predictions within the limited allocation space used; it could be suggested that the MPFC PE_O signal reflects a non-social perceptual or learning process rather than specifically social learning; further work required to elucidate the exact nature of the preference-dependent PE_O signal and its relationship to PE_S; the current task does not include any strategic component.
- **limitations_categorized:** limited ecological validity; limited model space; potential alternative explanations for neural signals; task simplicity; no strategic interaction
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - wc_3 (simulate): LOW confidence — no mention of simulation before fitting anywhere in text or supplement - wc_5 (parameter recovery): LOW confidence — not mentioned - wc_6 (model recovery): LOW confidence — not mentioned - model_params mean values: MEDIUM confidence — means reported per condition per SVO group in SM Table 1, but no single overall mean per parameter - ecological_validity: HIGH confidence — directly described in methods
- **cannot_find:** - Overall mean fitted parameter values collapsed across conditions (only condition x group means in SM Table 1) - Formal posterior predictive check - Data/code sharing statement
- **other_notes:** This is a single-study paper. The γ parameter is the key social parameter, elegantly capturing how cooperative vs. competitive orientation transforms other-value learning. The paper demonstrates a double dissociation between striatal PE_S and mPFC PE_O. The study is a good example of model-based fMRI where computational model regressors are used to identify neural correlates of distinct learning signals. The paper was published in NeuroImage in 2015.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dissociated
- spec_source = social
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_social_weight
- tax_param_valence_asymmetry
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_topic_prosocial_altruism
