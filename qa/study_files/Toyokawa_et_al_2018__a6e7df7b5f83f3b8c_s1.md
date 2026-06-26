# Toyokawa et al. (2018)

- **study_id:** `a6e7df7b5f83f3b8c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Toyokawa, W., Whalen, A., & Laland, K. N. (2018). Social learning strategies regulate the wisdom and madness of interactive online crowds. *bioRxiv*, 326637. https://doi.org/10.1101/326637
- **citation_short:** Toyokawa et al. (2018)
- **doi:** 10.1101/326637
- **publication_type:** preprint
- **year:** 2018.0
- **field_of_study:** Psychology
- **affiliations_raw:** SchoolofBiology,UniversityofStAndrews,HaroldMitchelBuilding,StAndrews,Fife,KY169TH,; DepartmentofEvolutionaryStudiesofBiosystems,SchoolofAdvancedSciences,SOKENDAI(The; etherand,ifso,howitispossibletopreventorreducetheriskofmaladaptiveherdbehaviour,; UniversityforAdvancedStudies),ShonanVillage,Hayama,Kanagawa240-0193,Japan; Institute,UniversityofEdinburgh,Midlothian,SCT,EH259RG,Scotland; ethebenefitsofswarmintelligence,but; etheriskofmaladaptiveherding; mitateeachothers(Kamedaand; emails: wt25@st-andrews.ac.uk
- **code_url:** https://github.com/WataruToyokawa/

## Computational level
- **study_focus:** Social learning strategies in collective decision-making; frequency-dependent social learning and conformity bias in multi-armed bandit tasks; relationship between individual social learning strategies and collective outcomes (swarm intelligence vs. maladaptive herding).
- **study_focus_short:** Social learning strategies in collective decision-making
- **learning_mode_description:** - Learning mode: Learning from others' choice frequencies about which option yields the best reward in a multi-armed bandit task   - Learning from:     - Source type (social): group (other group members)       - Source content (social): action/policy (frequency distribution of others' choices)     - Source type (non-social): self       - Source content (non-social): outcome (monetary reward from chosen slot)   - Learning about:     - Target type (non-social): world (which slot machine yields highest reward)       - Target content (non-social): stimulus (option value / expected reward)
- **task_description:** Participants played a 70-round three-armed bandit task online in groups of varying size (1-30), choosing between slot machines that yielded noisy monetary rewards. At round 41, one poor option became the best option (environmental change). Each round, participants saw the frequency distribution of other group members' choices from the preceding round.
- **task_paradigm:** Multi-armed bandit
- **players:** Multi-agent (groups of 1–30 participants), symmetric
- **n_players:** 
- **partner_type:** human (live)
- **stimuli:** Three abstract slot machines, monetary reward feedback, social frequency information (bar chart of others' choices)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Conformity exponent increased with task uncertainty (95% Bayesian CI = [0.38, 1.41])   - Social learning weight increased with group size (95% Bayesian CI = [0.15, 0.93])   - Social learning weight decreased with task uncertainty (95% Bayesian CI = [-0.98, -0.22])   - Proportion using positive frequency-dependent copying decreased with task uncertainty (95% Bayesian CI = [-1.88, -0.25])   - When conformity exponent was high (theta-bar = 3.0 in Moderate-uncertainty), larger groups got stuck on suboptimal options after environmental change   - When conformity exponent was low (theta-bar = 1.65 in Low-uncertainty), larger groups maintained swarm intelligence advantage   - Parameter recovery: at least 93% of true individual parameter values correctly recovered within 95% Bayesian CI
- **effect_size:** - Main Results:   - Conformity exponent increased with task uncertainty (95% Bayesian CI = [0.38, 1.41])   - Social learning weight increased with group size (95% Bayesian CI = [0.15, 0.93])   - Social learning weight decreased with task uncertainty (95% Bayesian CI = [-0.98, -0.22])   - Proportion using positive frequency-dependent copying decreased with task uncertainty (95% Bayesian CI = [-1.88, -0.25])   - When conformity exponent was high (theta-bar = 3.0 in Moderate-uncertainty), larger groups got stuck on suboptimal options after environmental change   - When conformity exponent was low (theta-bar = 1.65 in Low-uncertainty), larger groups maintained swarm intelligence advantage   - Parameter recovery: at least 93% of true individual parameter values correctly recovered within 95% Bayesian CI
- **learning_from:** Group; frequency distribution of other group members' choices (social); own reward outcomes from chosen slot (non-social)
- **learning_about:** World; which of three slot machines provides the highest expected monetary reward  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Rescorla-Wagner + frequency-dependent social influence with conformity exponent (6 params per individual: alpha_i, beta*_i0, epsilon_i, sigma*_i0, delta_i, theta_i), fitted via hierarchical Bayesian method
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "RW + frequency-dependent social learning (time-independent theta)", "family": "Rescorla-Wagner + social influence", "n_params": 6, "metric": "parameter recovery / post-hoc simulation"}, {"name": "RW + frequency-dependent social learning (time-dependent theta)", "family": "Rescorla-Wagner + social influence", "n_params": 7, "metric": "parameter recovery"}] - Note: The main model used a time-independent conformity exponent theta_i. An alternative model with time-dependent theta_i,t was considered but the parameter recovery test showed gamma_i (slope of theta over time) was not reliably recovered, so the time-independent model was preferred.
- **model_mb_mf:** MF
- **model_params:** - α_i: learning rate (0 <= α <= 1), weight given to new experience in Q-value updating. Fitted global means: Low-uncertainty group = 0.99, Moderate = 0.90, High = 0.61 [confidence: HIGH] - β*_i,0: initial inverse temperature (exploitation vs. exploration in asocial softmax). Fitted global means: Low = 1.84, Moderate = 1.68, High = 1.38 [confidence: HIGH] - ε_i: slope of inverse temperature over time (β_i,t = β*_i,0 + ε_i * t/70). Fitted global means: Low = 3.70, Moderate = 3.01, High = 2.97 [confidence: HIGH] - σ*_i,0 [S]: initial social learning weight (logit-transformed intercept of sigmoid). Fitted global means: Low = -1.55, Moderate = -2.37, High = -2.16 [confidence: HIGH] - δ_i [S]: slope of social learning weight over time. Fitted global means: Low = -1.39, Moderate = -1.55, High = -1.87 [confidence: HIGH] - θ_i [S]: conformity exponent controlling frequency-dependent copying. Fitted global means: Low = 1.65, Moderate = 3.00, High = 2.67 [confidence: HIGH]
- **social_param:** θ_i (conformity exponent) — controls degree of frequency-dependent bias in copying others' choices; values > 1 indicate conformity bias (disproportionate influence of majority). σ_i,t (social learning weight) — controls relative weight of social vs. asocial influence on choice probability; δ_i controls its temporal dynamics.
- **social_param_name:** σ*_i,0
- **social_param_value:** -1.55
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Parameter recovery test (proportion of true values within 95% Bayesian CI); post-hoc simulation accuracy (visual comparison of simulated vs. observed decision trajectories). No formal model comparison metric (e.g., BIC, WAIC) reported between competing models.
- **how_model_fit:** individual-level-fit (hierarchical Bayesian method using Stan/MCMC with 4+ parallel chains; individual parameters estimated within group-level hyperparameter distributions)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** N=699 (573 in group condition, 126 solitary); from initial N=755. Three between-subject uncertainty conditions: Low (N=113), Moderate (N=132), High (N=454). Mean age = 34.33 (SD = 10.9); 354 female, 377 male, 2 other, 22 unspecified.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Abstract multi-armed bandit task with slot machines — low ecological validity. Monetary incentives via Amazon Mechanical Turk. Online paradigm allows larger and more diverse samples than lab-based studies but raises questions about participant engagement. Social information limited to frequency counts (no rich social cues). Environmental change at fixed time point (round 41) is somewhat artificial.
- **eligibility_flag:** 
- **concerns:** (1) This is a bioRxiv preprint (not peer-reviewed as of posting date May 2018 — should check if a published version exists, which could create a duplicate). (2) No formal model comparison between the main model and alternatives (e.g., time-dependent vs. time-independent theta) using information criteria (BIC, WAIC, etc.) — model selection was based on parameter recovery rather than fit to data. (3) The alternative model with time-dependent theta was not reliably recovered, which may reflect identifiability issues rather than model inadequacy. (4) Group sizes varied naturalistically rather than being experimentally controlled (participants arrived at different rates), introducing potential confounds.
- **limitations_reported:** There are always questions about the validity of participants' behaviour when deploying the web-based method"; the conformity exponent parameter recovery was limited — could not reliably detect weak positive frequency dependence (0 < theta <= 1) due to statistical power limitations; some individuals with true conformity in this range would have been misclassified as random choice strategists; the time-dependent theta model's slope parameter gamma_i was not reliably recovered.
- **limitations_categorized:** limited ecological validity; online experiment validity concerns; limited parameter identifiability; classification accuracy limitations; task simplicity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_comparison_metric: LOW — no formal information criterion reported; model selection based on parameter recovery - wc_guidelines Rule 7: MEDIUM — no formal model comparison, though parameter recovery was used as basis for model selection - publication_type: HIGH — clearly stated as bioRxiv preprint; should check for published version (potential duplicate risk)
- **cannot_find:** - Formal model comparison statistics (BIC, AIC, WAIC) — not reported - Supplement not available as separate file (supplementary figures/tables referenced but no supplement file found in papers folder)
- **other_notes:** The paper references numerous supplementary figures (S1-S26) and tables (S1-S8) that appear to be part of the appendix within the main document rather than a separate supplement file. The table in the main text (Table 2) appears to have been extracted in reversed text order (likely a formatting artifact from PDF conversion). This is a preprint — a published version may exist (Toyokawa et al., 2019, Nature Human Behaviour — should check for duplicate). The model is notable for combining Rescorla-Wagner reinforcement learning with a frequency-dependent social influence function parameterized by a conformity exponent, allowing individual-level heterogeneity in social learning strategies.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_source = partly
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_social_weight
- tax_param_temperature
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_social_weight
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_norm_conformity
- tax_rr_topic_social_info_use
- tax_social_nonsocial_comparison
- tax_topic_norm_conformity
- tax_topic_social_info_use
