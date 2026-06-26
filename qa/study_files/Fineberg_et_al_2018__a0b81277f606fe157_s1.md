# Fineberg et al. (2018)

- **study_id:** `a0b81277f606fe157_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Fineberg, S. K., Leavitt, J., Stahl, D. S., Kronemer, S., Landry, C. D., Alexander-Bloch, A., Hunt, L. T., & Corlett, P. R. (2018). Differential valuation and learning from social and nonsocial cues in borderline personality disorder. *Biological Psychiatry*, *84*(12), 838–845.
- **citation_short:** Fineberg et al. (2018)
- **doi:** 10.1016/j.biopsych.2018.05.020
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** laboratory-based reinforcement learning paradigm with social duringthe“volatilephase”ofthetask,whenrewardforthesocial; sectionofsocialandnonsocialbeliefupdatinginBPD,whichholdspromiseforthedevelopmentofnovelclinical; ETHODS:Subjects(n=20BPD,n=23control subjects)playedanextendedrewardlearningtaskwithapartner; ethods and Materials for details; ethodsandMaterialsfordetails); ethodsandMaterials
- **code_url:** 

## Computational level
- **study_focus:** Social and nonsocial cue valuation and learning under volatility in borderline personality disorder (BPD). Examining how BPD patients differentially weight social versus nonsocial cues and how learning rates respond to changes in reward volatility.
- **study_focus_short:** Social and nonsocial cue valuation and learning under volatility in borderline
- **learning_mode_description:** - Learning mode: Learning from social advice and nonsocial perceptual cues about reward contingencies under varying volatility   - Learning from:     - Source type (social): other (confederate game partner)     - Source content (social): action/policy (advice about which color to pick)     - Source type (non-social): world     - Source content (non-social): outcome (reward feedback on chosen color)   - Learning about:     - Target type (non-social): world     - Target content (non-social): state (reward probability of color cues)     - Target type (social): other (confederate)     - Target content (social): state (mental state; trustworthiness/reliability of advice)
- **task_description:** On each of 290 trials, participants chose between a green and blue card, guided by point values, nonsocial cue reward probabilities, and advice from a confederate (actually computer-controlled). Social and nonsocial reward probabilities and volatility varied orthogonally across the task (the Social Valuation Task; Behrens et al., 2008).
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant), single target (confederate partner; actually computer-controlled)
- **n_players:** single agent (1)
- **partner_type:** confederate
- **stimuli:** Colored cards (green/blue) with point values, binary advice from confederate, reward feedback
- **method:** behavioural
- **method_full:** Behavioural
- **main_result:** - BPD subjects weighted social cues more heavily than control subjects: social reward probability (likelihood ratio chi-square = -5.98, p = .015, group coefficient = 0.12) - BPD subjects weighted nonsocial cues more heavily: reward probability (likelihood ratio chi-square = -4.03, p = .045, group coefficient = 0.11) - Blunted learning rate response to nonsocial volatility in BPD (group x condition interaction: F(1,41) = 19.78, p < .001) - Blunted learning rate response to social volatility in BPD (group x condition interaction: F(2,40) = 5.81, p < .01) - BPD subjects showed slower social learning across all phases (stable reliable t = 4.02, p < .001; volatile t = 2.90, p < .01; stable misleading t = 3.44, p < .005) - BPD subjects mentioned confederate more in debriefing (mean BPD = 11.60 vs. control = 4.77; t(21) = -2.67, p = .01) - Time x group interaction for self-referential language (F = 6.16, p = .02)
- **effect_size:** - BPD subjects weighted social cues more heavily than control subjects: social reward probability (likelihood ratio chi-square = -5.98, p = .015, group coefficient = 0.12) - BPD subjects weighted nonsocial cues more heavily: reward probability (likelihood ratio chi-square = -4.03, p = .045, group coefficient = 0.11) - Blunted learning rate response to nonsocial volatility in BPD (group x condition interaction: F(1,41) = 19.78, p < .001) - Blunted learning rate response to social volatility in BPD (group x condition interaction: F(2,40) = 5.81, p < .01) - BPD subjects showed slower social learning across all phases (stable reliable t = 4.02, p < .001; volatile t = 2.90, p < .01; stable misleading t = 3.44, p < .005) - BPD subjects mentioned confederate more in debriefing (mean BPD = 11.60 vs. control = 4.77; t(21) = -2.67, p = .01) - Time x group interaction for self-referential language (F = 6.16, p = .02)
- **learning_from:** Other (confederate advice; social) and world (color reward feedback; non-social)
- **learning_about:** World (reward contingencies of color cues) and other (trustworthiness of confederate's advice)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Rescorla-Wagner (delta rule): V(t+1) = V(t) + A * (R(t) - V(t)), with learning rate A and inverse temperature tau, fit separately per phase/cue type using hBayesDM bandit2arm_delta. Additionally, mixed-effects logistic regression models compared cue weighting using Bayes-optimal probability and volatility values from Behrens et al. (2007).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - For cue weighting: Nested mixed-effects regression models compared via likelihood ratio tests (full model with group x predictor interaction; reduced model without interaction; further reduced without group; null model with random effects only). These are not computational models per se but statistical models. - For learning rates: Rescorla-Wagner (2-armed bandit delta model) via hBayesDM  So formally: [{"name": "RW delta (bandit2arm_delta)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "hierarchical Bayesian fitting (hBayesDM)"}, {"name": "Mixed-effects logistic regression (full: group x predictor)", "family": "logistic regression", "n_params": "varies", "metric": "likelihood ratio chi-square"}, {"name": "Mixed-effects logistic regression (reduced: no interaction)", "family": "logistic regression", "n_params": "varies", "metric": "likelihood ratio chi-square"}, {"name": "Mixed-effects logistic regression (further reduced: no group)", "family": "logistic regression", "n_params": "varies", "metric": "likelihood ratio chi-square"}, {"name": "Mixed-effects logistic regression (null: random effects only)", "family": "logistic regression", "n_params": "varies", "metric": "likelihood ratio chi-square"}]
- **model_mb_mf:** MF
- **model_params:** - A (learning rate): estimated per subject per phase via hierarchical Bayesian fitting. No single mean reported; plotted in Figure 5. [No social marker — same parameter applied to both social and nonsocial cue phases separately] - tau (inverse temperature): sensitivity to expected value differences. No mean reported.
- **social_param:** No explicitly social parameter. The social dimension is captured by fitting the RW model separately to social vs. nonsocial cue phases rather than through a dedicated social parameter.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Likelihood ratio chi-square tests (for regression models). Hierarchical Bayesian estimation (for RW model — no formal model comparison between alternative computational models).
- **how_model_fit:** Individual-level fit (hierarchical Bayesian via hBayesDM for RW); group-level mixed-effects regression for cue weighting.
- **data_type_fit_to:** Choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 43 (23 control, 20 BPD); all female; ages 18–63
- **population_category:** clinical
- **population_age_range:** 18–63
- **ecological_validity:** Moderate. Participants met and interacted with a confederate before the task, adding some ecological validity to the social dimension. However, the confederate was not visible during the task itself, advice was actually computer-controlled (deception paradigm), and the task lacks the emotional engagement of real-world social interactions. Authors acknowledge this limitation.
- **eligibility_flag:** 
- **concerns:** - The RW model is applied in a relatively simple way (fit separately per phase) rather than as a single model capturing volatility-sensitivity. The Bayes-optimal volatility estimates used in the regression come from Behrens et al. (2007), not from fitting subjects' own data. - No formal model comparison between alternative computational models (e.g., HGF vs. RW). - Small sample size (N = 43, all female). - No parameter recovery or model recovery reported. - Mixed-effects regression with Bayes-optimal estimates as regressors is a hybrid approach that is not straightforward to categorize.
- **limitations_reported:** Sample is small and all female, cannot generalize to men; symptomatic patient group precludes dimensional analysis of symptom burden on behavior; did not test relationship of task behavior to emotional state via self-reports or physiological arousal; task does not meet criteria for an "engaged" task per Schilbach et al.; modeling approach uses mixed-effects regression compared to ideal Bayesian observer rather than individual-level hierarchical model; future work should use HGF for subject-specific estimates.
- **limitations_categorized:** Small sample size; limited generalizability (single gender); limited ecological validity; task simplicity; model simplicity; no physiological measures; no dimensional symptom analysis
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `model_params`: MEDIUM — exact mean fitted values for learning rate and tau not reported numerically (only plotted in figures) - `social_param`: MEDIUM — no explicitly social parameter; social dimension captured by separate fitting per cue type - `winning_model`: MEDIUM — the paper uses two complementary approaches (RW for learning rates, mixed-effects regression for cue weighting) rather than a single winning model
- **cannot_find:** - Mean fitted parameter values (A, tau) — plotted but not reported numerically in text or supplement - Formal model comparison between alternative computational models
- **other_notes:** This paper uses the Social Valuation Task (SVT) originally developed by Behrens et al. (2008). The computational modeling is relatively simple — a standard RW model fit via hBayesDM with no model comparison, supplemented by mixed-effects regression using Bayes-optimal values derived from Behrens et al.'s model rather than from subjects' own data. The authors acknowledge that future work should use the HGF for more sophisticated individual-level modeling. The Behrens et al. (2007, 2008) papers are the foundational references for the task and the Bayes-optimal values used here.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_bpd
- pop_healthy_adults
- rr_pop_bpd
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = general
- spec_locus = source+context
- spec_source = partly
- spec_target = partly
- tax_domain_C_exchange_interdependence
- tax_domain_G_uncertainty_volatility
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = G_uncertainty_volatility
- tax_rr_domain_C_exchange_interdependence
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_uncertainty
- tax_rr_secondary_topic = trust
- tax_rr_topic_social_uncertainty
- tax_rr_topic_trust
- tax_social_nonsocial_comparison
- tax_topic_social_uncertainty
- tax_topic_trust
