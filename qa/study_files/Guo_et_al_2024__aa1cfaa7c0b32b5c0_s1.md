# Guo et al. (2024)

- **study_id:** `aa1cfaa7c0b32b5c0_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Guo, Z., Yu, J., Wang, W., Lockwood, P., & Wu, Z. (2024). Reinforcement learning of altruistic punishment differs between cultures and across the lifespan. PLoS Computational Biology, 20(7), e1012274. https://doi.org/10.1371/journal.pcbi.1012274
- **citation_short:** Guo et al. (2024)
- **doi:** 10.1371/journal.pcbi.1012274
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Psychology
- **affiliations_raw:** ethatreplicateallresultsinthemanuscriptand individuals,comparedtoAmericans,quicklyassociatepunishingunfairactionswith; labilityStatement:Dataandanalysis participantsfromChinaandtheUSA,andfromearlyadolescencetoadulthood; DepartmentofPsychologicalandCognitiveSciences,TsinghuaUniversity,Beijing,China,2 Labfor; mpiricalevidenceislackinginshowinghowthesebiasesarelearnedandinfluencedbysocial; University,Beijing,China,3 CentreforHumanBrainHealthandInstitutefor; SchoolofPsychology,UniversityofBirmingham,Birmingham,UnitedKingdom; etheprofoundimpactofourgroup-centricnatureonmoralstandards; mittedcoopera
- **code_url:** 

## Computational level
- **study_focus:** altruistic punishment; ingroup bias; cross-cultural social norm learning
- **study_focus_short:** altruistic punishment; ingroup bias; cross-cultural social norm learning
- **learning_mode_description:** - Learning mode: Learning from social feedback (observers' approval/disapproval) about punishment norms for ingroup vs. outgroup members     - Learning from:       - Source type (social): group (observers in the waiting room)       - Source content (social): outcomes (thumbs-up/thumbs-down social approval feedback)     - Learning about:       - Target type (social): self (own punishment policy toward ingroup/outgroup)       - Target content (social): action/policy (whether to punish unfair allocators from ingroup vs. outgroup)
- **task_description:** Participants (Player 3) observed unfair allocations by Player 1 (ingroup or outgroup via minimal group paradigm) and chose to accept or punish at cost. Social feedback (80%/20% probabilistic thumbs up/down from observers) was given after each decision, incentivizing either punishment or acceptance depending on condition.
- **task_paradigm:** Minimal group paradigm
- **players:** Single agent (participant as Player 3), multi-target (ingroup and outgroup dividers; simulated observers)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Color-coded team membership (blue/yellow/red); unfair monetary allocations; thumbs-up/thumbs-down social feedback
- **method:** online / behavioural
- **method_full:** behavioural (online)
- **main_result:** - Chinese participants exhibited stronger ingroup bias in pre-test punishment than Americans (b = -0.82, SE = 0.29, z = -2.94)   - Chinese participants had lower learning rates for ingroup norms (b = -0.07, SE = 0.01, t = -5.51) while Americans showed no difference (b = -0.02, SE = 0.01, t = -1.46)   - Chinese participants had lower beta for ingroup norms (b = -0.23, SE = 0.04, t = -5.85) while Americans showed no difference (b = -0.08, SE = 0.04, t = -1.90)   - Chinese participants showed stronger bias term than Americans when punishment was rewarded (MDiff = 0.06, SE = 0.01, t = 5.11)   - Group identity mediated culture-learning rate relationship (standardized indirect effect = 0.07, 95% CI [0.003, 0.140])
- **effect_size:** - Ingroup bias culture interaction (pre-test): b = -0.82, SE = 0.29, z = -2.94   - Culture x divider group interaction (learning rates): b = -0.09, SE = 0.04, t = -2.58   - Culture x divider group interaction (temperature): b = -0.14, SE = 0.06, t = -2.48   - Culture x norms interaction (bias term): F(1, 385) = 7.25, eta_p2 = 0.018   - Mediation indirect effect: 0.07, 95% CI [0.003, 0.140]   - alpha-punishment rate correlation (punishment-encouragement): r = 0.29   - alpha-punishment rate correlation (acceptance-encouragement): r = -0.21
- **learning_from:** Group (observers); social approval/disapproval feedback
- **learning_about:** Self; own punishment policy toward ingroup vs. outgroup norm violators  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RW (4alpha, 2beta + bias): separate alpha for ingroup/outgroup x block1/block2; separate beta for ingroup/outgroup; 1 ingroup-acceptance bias term (7 params)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "1alpha1beta", "family": "RW", "n_params": 2, "metric": "iBIC"},    {"name": "2alpha1beta", "family": "RW", "n_params": 3, "metric": "iBIC"},    {"name": "2alpha2beta", "family": "RW", "n_params": 4, "metric": "iBIC"},    {"name": "4alpha1beta", "family": "RW", "n_params": 5, "metric": "iBIC"},    {"name": "4alpha2beta", "family": "RW", "n_params": 6, "metric": "iBIC"},    {"name": "4alpha2beta+bias (winning)", "family": "RW", "n_params": 7, "metric": "iBIC"}]
- **model_mb_mf:** MF
- **model_params:** - alpha_in_block1: learning rate for ingroup dividers, block 1 (Chinese M = 0.28, SD = 0.24; American M = 0.21, SD = 0.24)   - alpha_in_block2: learning rate for ingroup dividers, block 2   - alpha_out_block1: learning rate for outgroup dividers, block 1   - alpha_out_block2: learning rate for outgroup dividers, block 2   - beta_in [S]: temperature for ingroup dividers (Chinese M = 0.39, SD = 0.37; American M = 0.31, SD = 0.28)   - beta_out: temperature for outgroup dividers   - bias [S]: constant ingroup-acceptance bias term (shifts preference toward accepting ingroup members' unfair allocations)
- **social_param:** bias [S]: pre-existing action bias favoring acceptance of ingroup members' norm violations, resistant to social feedback; beta_in [S]: temperature for ingroup norms (lower = more value-driven, less random)
- **social_param_name:** beta_in
- **social_param_value:** 0.39
- **social_param_sd:** 0.37
- **social_param_range:** 
- **model_comparison_metric:** Integrated BIC (iBIC)
- **how_model_fit:** individual-level-fit (hierarchical MAP with EM; iterative expectation-maximization)
- **data_type_fit_to:** choice behavior  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 389 (217 Chinese adults, Mage = 28.01, SDage = 7.46, 69 males; 172 American adults, Mage = 35.01, SDage = 9.90, 89 males)
- **population_category:** healthy adults
- **population_age_range:** 12–52
- **ecological_validity:** Moderate; minimal group paradigm captures general ingroup bias but lacks emotional depth and history of real social groups; online study; socially contextualized RL task (punishment of unfair allocators) has greater ecological validity than abstract probabilistic tasks
- **eligibility_flag:** 
- **concerns:** Supplement tables (S1-S10) referenced as .DOC files but not accessible in papers folder; country used as proxy for culture may confound with other socio-ecological factors; demographic differences between samples (age, gender) controlled as covariates but may still confound; no fair trials included
- **limitations_reported:** Ingroup bias observed in minimal groups but variability in social decision-making among real-world groups underscores need for investigation within natural groups; country used as proxy for culture may not fully account for confounding variables between Western and Chinese samples; unaddressed socio-ecological factors may influence ingroup bias and norm learning; causality between cultural and developmental factors remains unclear; no fair trials included which limits understanding of learning in mixed contexts
- **limitations_categorized:** limited ecological validity; cultural proxy confound; limited generalizability; cross-sectional design; task simplicity
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
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** model_params (MEDIUM: block-specific means not broken out individually; overall means reported); all_models_tested (MEDIUM: full iBIC values in inaccessible S5 Table supplement)
- **cannot_find:** Exact iBIC values for model comparison (in S5 Table supplement, not accessible); block-specific mean parameter values for alpha
- **other_notes:** Two-study paper; Study 1 is cross-cultural (Chinese vs. American adults). Patricia Lockwood is a co-author. Supplement files (.DOC) referenced but not available in papers folder. Supplement not accessible.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_domain_D_group_structure_identity
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_perseveration
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = intergroup_bias
- tax_rr_topic_intergroup_bias
- tax_rr_topic_norm_conformity
- tax_topic_intergroup_bias
- tax_topic_norm_conformity
