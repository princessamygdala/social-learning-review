# Vidal-Perez et al. (2025)

- **study_id:** `aacdf803808aa7093_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Vidal-Perez, J., Dolan, R. J., & Moran, R. (2025). Disinformation elicits learning biases. *eLife*, *3*(v3). https://doi.org/10.7554/eLife.106073.3
- **citation_short:** Vidal-Perez et al. (2025)
- **doi:** 10.7554/eLife.106073.3
- **publication_type:** reviewed preprint (elife)
- **year:** 2025.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Centre for Computational Psychiatry and Ageing, University College London, London, United Kingdom; School of Biological and Behavioural Sciences, Queen Mary University of London, London, United; Centre for Human Neuroimaging, University College London, London, United Kingdom • Department; mping to conclusions) and exacerbated a normalized measure of “positivity bias”; mitigating its harmful impacts; mited success to date (17 ); ethodologically; ether and how
- **code_url:** https://osf.io/preprints/psyarxiv/4zkxw/

## Computational level
- **study_focus:** Learning from disinformation — how source credibility modulates reinforcement learning biases (positivity bias, contrast effects, truth-inference bias) in a social feedback context.
- **study_focus_short:** Learning from disinformation
- **learning_mode_description:** - Learning mode: Learning from feedback agents of varying credibility about which bandit is more rewarding   - Learning from:     - Source type (social): other (computerized feedback agents representing social agents)     - Source content (non-social): outcome (reward/non-reward feedback about bandit choice)   - Learning about:     - Target type (non-social): world (bandit reward probabilities)     - Target content (non-social): outcome (which bandit is more rewarding)
- **task_description:** Participants completed a two-armed bandit task where true choice outcomes were latent; instead, computerized feedback agents of varying credibility (50%, 75%, 100% truth-telling in the main study; 50%, 70%, 85%, 100% in the discovery study) reported whether the chosen bandit yielded a reward or non-reward.
- **task_paradigm:** Two-armed bandit
- **players:** Single agent (participant), multi-target (3 computerized feedback agents of varying credibility in main study; 4 agents in discovery study)
- **n_players:** small group (4)
- **partner_type:** computer (algorithmic)
- **stimuli:** Identicons (bandits), star-rated feedback agents, binary reward/non-reward feedback (dollar sign / sad emoji)
- **method:** online / behavioural
- **method_full:** Behavioural / online (Prolific + Gorilla platform)
- **main_result:** - Learning (credit assignment) increased as a function of source credibility (CA differed across agents: F(2,609)=212.65; 3-star vs 1-star: b=1.24, t(609)=19.31) - Credibility-CA model provided superior fit over instructed-credibility Bayesian model for 71% of participants (sign test p<0.001) and over free-credibility Bayesian for 53.9% - Participants learned from fully non-credible (random) feedback in the main study (1-star CA: b=0.23, t(609)=4.54) - Relative positivity bias amplified for low-credibility sources (rVBI varied by credibility: F(2,609)=14.83; 3-star rVBI lower than 1-star: b=-0.22, t(609)=-4.41) - Credible feedback effect boosted when preceded by low-credibility context (feedback x contextual credibility interaction: F(2,2086)=11.47) - Positive truth bonus: participants increased credit assignment for feedback more likely to be true (truth bonus mean=0.21, t(203)=3.12)
- **effect_size:** Regression coefficients (b) and F-statistics reported throughout; no standardized effect sizes (Cohen's d, r, etc.) reported.
- **learning_from:** Other (feedback agents of varying credibility); reward/non-reward outcome feedback
- **learning_about:** World; bandit reward probabilities (which option is more rewarding)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Credibility-Valence-CA model (6 CA params: CA+/CA- per agent; plus forgetting f_Q, perseveration PERS, f_p). Also important: Truth-CA model used as measurement tool.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Null-CA", "family": "Credit Assignment RL", "n_params": 4, "metric": "BGLRT"} 2. {"name": "Credibility-CA", "family": "Credit Assignment RL", "n_params": 6, "metric": "BGLRT/PBCM"} 3. {"name": "Credibility-Valence-CA", "family": "Credit Assignment RL", "n_params": 9, "metric": "BGLRT"} 4. {"name": "Constant-Feedback-Valence-Bias CA", "family": "Credit Assignment RL", "n_params": 7, "metric": "BGLRT"} 5. {"name": "Truth-CA", "family": "Credit Assignment RL", "n_params": 7, "metric": "used as measurement tool"} 6. {"name": "Instructed-Credibility Bayesian", "family": "Bayesian belief updating", "n_params": 1, "metric": "PBCM"} 7. {"name": "Free-Credibility Bayesian", "family": "Bayesian belief updating", "n_params": 3, "metric": "PBCM"} 8. {"name": "Instructed-Credibility Bayesian + perseveration", "family": "Bayesian belief updating", "n_params": 3, "metric": "PBCM"} 9. {"name": "Free-Credibility Bayesian + perseveration", "family": "Bayesian belief updating", "n_params": 5, "metric": "PBCM"}
- **model_mb_mf:** MF
- **model_params:** - CA (credit assignment per agent) — magnitude of Q-value update after feedback. In credibility-CA: CA_1star, CA_2star, CA_3star. In credibility-valence-CA: CA+_1star, CA-_1star, CA+_2star, CA-_2star, CA+_3star, CA-_3star - f_Q (forgetting rate for Q-values, [0,1]) - PERS (perseveration magnitude) - f_p (forgetting rate for perseveration, [0,1]) - TB (truth bonus, in Truth-CA model; mean=0.21) - [S] CA parameters are implicitly social as they are modulated by social agent credibility - For Bayesian models: β (inverse temperature), C_1star, C_2star (free credibility params) - Mean fitted values not systematically reported for all parameters (individual-level ML fitting; see SI 3.3 tables for distributions)
- **social_param:** [S] Credibility-dependent CA parameters — credit assignment magnitude modulated by social agent credibility (star rating). The credibility parameters in the free-credibility Bayesian model (C_1star, C_2star) represent distorted credibility attributed to social agents.
- **social_param_name:** [S] Credibility-dependent CA parameters
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Parametric Bootstrap Cross-fitting Method (PBCM) for Bayesian vs CA models; Bootstrap Generalized Likelihood Ratio Test (BGLRT) for nested CA models
- **how_model_fit:** individual-level-fit (ML estimation, 10 random initializations per participant)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Main study: N=204 (after excluding 42 from 246 recruited; mean age 39.33 +/- 12.65, 112 female). Discovery study: N=104 (after excluding 7 from 111; mean age 36.23 +/- 11.26, 50 female). Total: N=308 across both studies.
- **population_category:** healthy adults
- **population_age_range:** M=39.33
- **ecological_validity:** Limited. Participants were explicitly instructed about agent credibility levels, unlike real-world disinformation where credibility must be inferred. Feedback agents were computerized, not real social agents. Agents lied randomly rather than strategically. Participants had no control over information source selection. Minimal emotional engagement; task concerned abstract bandits rather than identity-relevant issues.
- **eligibility_flag:** The "social agent" is an automated/computerized system (not a real human partner). The social context is minimal — participants learn about non-social outcomes (bandit reward probabilities) from computerized feedback agents. Flag: borderline social context; social source but non-social learning target.
- **concerns:** - No standardized effect sizes reported (no Cohen's d, r, etc.) — only regression coefficients and F-statistics - Feedback agents are computerized, not real social agents - The learning target (bandit reward probability) is non-social; only the information source is social - Discovery study and main study differ in task structure (number of agents, block structure), making direct comparison imperfect - Exact fitted parameter means not systematically reported in the main text (distributions shown in SI figures) - "Truth-CA" model acknowledged by authors as mechanistically implausible (oracle model)
- **limitations_reported:** Several factors may limit the external validity of the task, including that participants were explicitly instructed about the credibility of information sources; in many real-life scenarios, individuals need to learn the credibility of information sources based on their own experience; in the task, the experimenter fully controlled the credibility of the information source, whereas in real life people can exercise a degree of control over information credibility; feedback agents served as rudimentary representations of social agents who lied randomly and arbitrarily rather than strategically; further studies are required to determine whether positivity bias in the task is indeed a form of confirmation bias; future studies could benefit from designs that better dissociate learning asymmetries from gradual perseveration.
- **limitations_categorized:** Limited ecological validity; task simplicity; artificial social agents; no real social interaction; confound between positivity bias and perseveration; instruction-based vs experience-based credibility learning; limited generalizability to strategic deception contexts
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 9.5
- **wc_total:** 9.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM — only regression coefficients (b) and F-statistics reported; no standardized effect sizes - social_param: MEDIUM — CA parameters are modulated by social agent credibility but the parameters themselves are not exclusively social - eligibility_flag: MEDIUM — borderline social context (automated social agents; non-social learning target) - model_params fitted values: LOW — mean fitted values for all parameters not systematically reported in text (shown in SI figure distributions)
- **cannot_find:** - Standardized effect sizes (Cohen's d, r, eta-squared) - Exact mean fitted parameter values for all model parameters (only truth bonus mean=0.21 reported in text; others shown in figures) - Preregistration status
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_decay
- tax_param_perseveration
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_social_weight
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = reputation_learning
- tax_rr_topic_reputation_learning
- tax_rr_topic_social_info_use
- tax_topic_reputation_learning
- tax_topic_social_info_use
