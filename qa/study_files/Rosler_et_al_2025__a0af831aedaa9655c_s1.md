# Rosler et al. (2025)

- **study_id:** `a0af831aedaa9655c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Rosler, I. K., Kerber, I., & Amodio, D. M. (2025). Effects of moral stereotypes on the formation and persistence of group preferences. *Journal of Experimental Social Psychology, 119*, 104750. https://doi.org/10.1016/j.jesp.2025.104750
- **citation_short:** Rosler et al. (2025)
- **doi:** 10.1016/j.jesp.2025.104750
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** ether moral stereotypes, as compared with stereotypes butes, stereotypes can bias impressions and thus contribute to prejudice; Department of Psychology, University of Amsterdam, Nieuwe Achtergracht 129, REC G, 1001 NK Amsterdam, Netherlands; ether such impressions are more resistant to Although the content and functions of moral stereotypes have been; University of Berlin, Faculty of Life Sciences, Institute of Psychology, Unter den Linden 6, 10099, Berlin; University of Amsterdam, Department of Psychology, PO Box 15900, 1001 NK Amsterdam, The Netherlands; Department of Psychology, Humboldt U
- **code_url:** 

## Computational level
- **study_focus:** Moral stereotype learning; how moral (vs. nonmoral/competence) stereotypes influence formation and persistence of group-based impression updating through social-interactive reinforcement learning.
- **study_focus_short:** Moral stereotype learning
- **learning_mode_description:** - Learning mode: Learning from reward feedback of stereotyped group members about individual group member reward value, modulated by moral vs. nonmoral group stereotypes   - Learning from:     - Source type (social): other (group members/players)     - Source content (non-social): outcome (reward feedback: +1 or 0 points)   - Learning about:     - Target type (social): other (individual group members) / group (group-level value representations)     - Target content (social): state (mental state; expected reward value / trustworthiness implied by stereotype)
- **task_description:** Participants completed a probabilistic reward reinforcement learning task in which they chose between two players (one from each of two stereotyped groups) on each trial and received binary reward feedback (+1 or 0 points). Prior to the task, participants read moral or nonmoral (competence) group stereotype descriptions. Despite stereotypes, average reward rates were equated across groups. A test phase assessed persistence of learned preferences without feedback.
- **task_paradigm:** Stereotype learning task
- **players:** Single agent (participant), multi-target (8 players across 2 groups; 4 per group with reward rates of 30%, 40%, 60%, 70%)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Avatar images (varying hair color, eye color, clothing), text-based stereotype descriptions (moral or competence-related), binary reward feedback (+1 or 0 points)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Training phase (first 30 trials): Stereotype Valence x Stereotype Morality interaction on choice (d = -0.51, z = -2.21, p = .027)   - Moral condition stereotype valence effect on initial choices (d = 1.72)   - Nonmoral condition stereotype valence effect on initial choices (d = 1.27)   - Test phase: Stereotype Valence x Stereotype Morality interaction (d = -0.66, z = -2.94, p = .003)   - Test phase moral condition: significant stereotype valence effect (d = 0.50)   - Test phase nonmoral condition: no stereotype valence effect (d = 0.50, p = .923)   - Computational model: Stereotype-learning model (Model 4) best fit by AIC (Mdn AIC = 88.00 in Study 1)   - Prior parameter: stronger in moral (Mdn = 0.26) vs. nonmoral (Mdn = -0.01) condition (W = 415, p < .045)   - Learning rate: marginally higher in moral (Mdn = 0.317) vs. nonmoral (Mdn = 0.210) condition (t(134) = 1.98, p = .050)
- **effect_size:** - Main Results:   - Training phase (first 30 trials): Stereotype Valence x Stereotype Morality interaction on choice (d = -0.51, z = -2.21, p = .027)   - Moral condition stereotype valence effect on initial choices (d = 1.72)   - Nonmoral condition stereotype valence effect on initial choices (d = 1.27)   - Test phase: Stereotype Valence x Stereotype Morality interaction (d = -0.66, z = -2.94, p = .003)   - Test phase moral condition: significant stereotype valence effect (d = 0.50)   - Test phase nonmoral condition: no stereotype valence effect (d = 0.50, p = .923)   - Computational model: Stereotype-learning model (Model 4) best fit by AIC (Mdn AIC = 88.00 in Study 1)   - Prior parameter: stronger in moral (Mdn = 0.26) vs. nonmoral (Mdn = -0.01) condition (W = 415, p < .045)   - Learning rate: marginally higher in moral (Mdn = 0.317) vs. nonmoral (Mdn = 0.210) condition (t(134) = 1.98, p = .050)
- **learning_from:** Other (group members); reward feedback from chosen player indicating whether they shared a point.
- **learning_about:** Other (individual group members) and group (group-level value representations); reward value / behavioral tendencies of stereotyped group members.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** RW with group-based prior and separate group learning rates (Model 4: αPos, αNeg, P, β; 4 params)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Model 1: Standard Q-learning", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AIC/BIC"},   {"name": "Model 2: Q-learning + group prior", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC/BIC"},   {"name": "Model 3: Q-learning + separate group LRs", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC/BIC"},   {"name": "Model 4: Q-learning + group prior + separate group LRs (winning)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "AIC/BIC"},   {"name": "Model 5: Q-learning + reward/loss LRs", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC/BIC"},   {"name": "Model 6: Q-learning + reward/loss LRs + prior", "family": "Rescorla-Wagner", "n_params": 4, "metric": "AIC/BIC"},   {"name": "Model 7: Q-learning + group x reward/loss LRs", "family": "Rescorla-Wagner", "n_params": 5, "metric": "AIC/BIC"},   {"name": "Model 8: Q-learning + group x reward/loss LRs + prior", "family": "Rescorla-Wagner", "n_params": 6, "metric": "AIC/BIC"},   {"name": "Model 9: Q-learning + PE+/- LRs", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC/BIC"},   {"name": "Model 10: Q-learning + group x reward/loss LRs + confirmation bias", "family": "Rescorla-Wagner", "n_params": 6, "metric": "AIC/BIC"} ]
- **model_mb_mf:** MF
- **model_params:** - αPos [S]: learning rate for positively-stereotyped group members (Study 1 moralized Mdn = 0.13, non-moralized Mdn = 0.02) - αNeg [S]: learning rate for negatively-stereotyped group members (Study 1 moralized Mdn = 0.16, non-moralized Mdn = 0.02) - P [S]: group-based symmetrical prior (opposing initial values for positively vs. negatively stereotyped groups; Study 1 moralized Mdn = 0.26, non-moralized Mdn = -0.01) - β: inverse temperature (Study 1 moralized Mdn = 0.19, non-moralized Mdn = 0.05)
- **social_param:** P (prior) — group-based symmetrical prior reflecting initial stereotyped expectancy, set as +P for positively-stereotyped group and -P for negatively-stereotyped group. αPos and αNeg — separate group-based learning rates capturing group-level (rather than individual-level) updating of impressions.
- **social_param_name:** αPos
- **social_param_value:** 0.13
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC, BIC
- **how_model_fit:** individual-level-fit (MLE, 50 random starting points per participant)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A — no neuroimaging
- **key_regions:** N/A — no neuroimaging
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Study 1: N = 80 recruited, N = 69 after exclusions (Mage = 42.35, SDage = 13.67; 32 females, 37 males); US-based, online (CloudResearch)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Limited ecological validity. Minimal social interactions with avatar-represented "players" in a probabilistic reward task. Stereotype descriptions were experimentally created rather than reflecting real-world group stereotypes. Authors acknowledge the task prioritized construct and internal validity over ecological validity.
- **eligibility_flag:** 
- **concerns:** The social "learning" is primarily reward-based reinforcement learning with stereotype priors, rather than purely social learning per se — the feedback is binary reward, not social information. The "group-level updating" mechanism is captured by separate learning rates for each group rather than an explicit group-level representation. Task relevance confound: sharing points may be more relevant to moral (trustworthiness) than competence traits; authors address this but cannot fully rule it out. Between-subjects manipulation of stereotype morality means individual differences could contribute to condition effects.
- **limitations_reported:** Stereotype descriptions may not reflect the complexity or specific characteristics associated with stereotypes for real groups in different cultures and societies; the task procedure prioritized construct and internal validity, limiting ecological validity; everyday interactions involve more nuance and complexity than the controlled task; impressions formed through interaction incorporate other kinds of information beyond stereotypes and feedback; task context of sharing points may be more relevant to moral than competence traits; did not observe expected valence asymmetry effect, possibly due to dichotomous choice measure
- **limitations_categorized:** limited ecological validity; task simplicity; limited generalizability; potential confound (task relevance); stimulus validity
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_D_group_structure_identity
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_valence_asymmetry
- tax_popclass_healthy
- tax_rr_domain = D_group_structure_identity
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = stereotype_updating
- tax_rr_secondary_topic = intergroup_bias
- tax_rr_topic_intergroup_bias
- tax_rr_topic_stereotype_updating
- tax_topic_intergroup_bias
- tax_topic_stereotype_updating
