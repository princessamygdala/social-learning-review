# Guo et al. (2024)

- **study_id:** `aa1cfaa7c0b32b5c0_s2`
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
- **study_focus:** altruistic punishment; developmental trajectory; ingroup bias; cultural norm internalization
- **study_focus_short:** altruistic punishment
- **learning_mode_description:** - Learning mode: Learning from social feedback (observers' approval/disapproval) about punishment norms for ingroup vs. outgroup members across age (12-52)     - Learning from:       - Source type (social): group (observers in the waiting room)       - Source content (social): outcomes (thumbs-up/thumbs-down social approval feedback)     - Learning about:       - Target type (social): self (own punishment policy toward ingroup/outgroup)       - Target content (social): action/policy (whether to punish unfair allocators from ingroup vs. outgroup)
- **task_description:** Same paradigm as Study 1. Chinese participants aged 12-52 (213 adolescents + 217 adults from Study 1) observed unfair allocations by ingroup/outgroup Player 1 and chose to accept or punish, receiving probabilistic social feedback.
- **task_paradigm:** Minimal group paradigm
- **players:** Single agent (participant as Player 3), multi-target (ingroup and outgroup dividers; simulated observers)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Color-coded team membership (blue/yellow/red); unfair monetary allocations; thumbs-up/thumbs-down social feedback
- **method:** online / behavioural
- **method_full:** behavioural (adolescents offline; adults online from Study 1)
- **main_result:** - Ingroup punishment decreased with age (pre-test: b = -0.03, SE = 0.02, z = -2.05) while outgroup punishment remained stable (b = -0.01, SE = 0.02, z = -0.34)   - Learning rate for ingroup punishment norms decreased with age (b = -0.14, SE = 0.03, t = -4.21) while outgroup alpha was stable (b = -0.02, SE = 0.03, t = -0.68)   - Bias term increased with age regardless of punishment norms (b = 0.13, SE = 0.05, t = 2.65)   - Temperature lower for ingroup than outgroup norms (b = -0.25, SE = 0.05, t = -5.36) and decreased with age (b = -0.12, SE = 0.04, t = -2.74)   - Adolescents showed higher learning rates than adults when socially incentivized to accept unfairness (b = 0.50, SE = 0.11, t = 4.66)
- **effect_size:** - Age x divider group interaction (learning rates): b = -0.06, SE = 0.02, t = -2.99   - Ingroup alpha-age: b = -0.14, SE = 0.03, t = -4.21   - Bias-age: b = 0.13, SE = 0.05, t = 2.65   - Divider group effect on beta: b = -0.25, SE = 0.05, t = -5.36   - Age effect on beta: b = -0.12, SE = 0.04, t = -2.74   - Adolescent vs. adult learning rate (acceptance condition): b = 0.50, SE = 0.11, t = 4.66
- **learning_from:** Group (observers); social approval/disapproval feedback
- **learning_about:** Self; own punishment policy toward ingroup vs. outgroup norm violators  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RW (4alpha, 2beta + bias): same structure as Study 1 (7 params)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Same 6 models as Study 1 (see S15 Table); winning model identical
- **model_mb_mf:** MF
- **model_params:** - alpha_in_block1: learning rate for ingroup dividers, block 1 (adolescents M = 0.41, SD = 0.23)   - alpha_in_block2: learning rate for ingroup dividers, block 2   - alpha_out_block1: learning rate for outgroup dividers, block 1   - alpha_out_block2: learning rate for outgroup dividers, block 2   - beta_in [S]: temperature for ingroup dividers (adolescents M = 0.42, SD = 0.23)   - beta_out: temperature for outgroup dividers   - bias [S]: constant ingroup-acceptance bias term
- **social_param:** bias [S]: pre-existing action bias that increases with age in Chinese participants; beta_in [S]: ingroup-specific temperature
- **social_param_name:** beta_in
- **social_param_value:** 0.42
- **social_param_sd:** 0.23
- **social_param_range:** 
- **model_comparison_metric:** Integrated BIC (iBIC)
- **how_model_fit:** individual-level-fit (hierarchical MAP with EM)
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
- **sample_size:** N = 430 (217 Chinese adults from Study 1, Mage = 28.01; 213 Chinese adolescents, Mage = 15.01, SDage = 1.82, range 12-18, 108 males)
- **population_category:** mixed
- **population_age_range:** 12–18
- **ecological_validity:** Moderate; same as Study 1; adolescent sample tested offline providing more controlled environment
- **eligibility_flag:** 
- **concerns:** Reuses adult Chinese data from Study 1 (not independent); cross-sectional design used to infer developmental trajectory; supplement tables not accessible; adolescent sample tested offline while adults online (different testing modalities)
- **limitations_reported:** Same as Study 1 plus: causality between cultural and developmental factors unclear; longitudinal methods recommended to trace development; no fair trials to investigate mixed-context learning strategies; cross-sectional design limits causal claims
- **limitations_categorized:** cross-sectional design; limited ecological validity; cultural proxy confound; task simplicity; data reuse
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
- **flagged_fields:** model_params (MEDIUM: adolescent-specific means partially reported; adult data shared with Study 1); sample independence (MEDIUM: adult Chinese data reused from Study 1)
- **cannot_find:** Full iBIC values for Study 2 model comparison (S15 Table); block-specific alpha means by age group
- **other_notes:** Shares adult Chinese data with Study 1. Supplement (.DOC files) not available in papers folder. Adolescents showed no ingroup-outgroup difference in learning rates, suggesting sensitive period for norm internalization.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_source = social
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_domain_D_group_structure_identity
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_developmental
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
