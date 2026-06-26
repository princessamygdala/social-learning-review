# Schultner et al. (2024)

- **study_id:** `a89810dc3e613b00c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Schultner, D. T., Lindstrom, B. R., Cikara, M., & Amodio, D. M. (2024). Transmission of social bias through observational learning. *Science Advances*, *10*(26), eadk2030. https://doi.org/10.1126/sciadv.adk2030
- **citation_short:** Schultner et al. (2024)
- **doi:** 10.1126/sciadv.adk2030
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Psychology
- **affiliations_raw:** Faculty of Social and Behavioral Sciences, department of Psychology, University ment may create a unique kind of ambiguity: when learning from a; division of Psychology, department of clini- demonstrator’s actions, it may be unclear to the observer whethe; mitted between individuals through observa- chosen target (29); ether an actor’s back from the chosen target (28, 30, 31); lability of these two sources of reinforce-; ether social learning may; ether that; etherlands
- **code_url:** https://osf.io/en92m/

## Computational level
- **study_focus:** Observational learning of social group bias / prejudice transmission via value shaping
- **study_focus_short:** Observational learning of social group bias / prejudice transmission via value
- **learning_mode_description:** - Learning mode: Learning from observing a demonstrator's biased choices and targets' reward feedback about group members' reward value   - Learning from:     - Source type (social): other (demonstrator)       - Source content (social): action/policy (choice behavior toward group members)     - Source type (non-social): world       - Source content (non-social): outcome (reward feedback from chosen target)   - Learning about:     - Target type (social): group (two social groups)       - Target content (social): stimulus (reward value / preference for group members)
- **task_description:** Participants observed a demonstrator's choices between members of two social groups (avatars) in a probabilistic learning task and the resulting reward feedback, then made their own incentivized choices between group members in a test phase without feedback.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (observer/participant), multi-target (8 avatars from 2 groups; yoked to 1 demonstrator)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Avatars representing social group members (blue/green group cues), binary monetary feedback ("Shared +1" or "Shared 0")
- **method:** online / behavioural
- **method_full:** behavioural / online (lab-based for Study 1)
- **main_result:** - Observers acquired demonstrators' group bias (group effect: β = 0.30, Wald z = 2.63) - Observers also learned individual reward rates (reward effect: β = 1.15, Wald z = 7.14) - Demonstrator bias predicted observer bias (β = 0.41, r = .29) - Observers misperceived group difference in sharing rates (β = 3.50, t = 2.40) - Observers unaware of demonstrator group preference (BF = 0.047, supporting null) - (Mis)perceived player rewards more strongly predicted own preferences than perceived demonstrator preferences (F = 21.7)
- **effect_size:** - Group effect on choice: β = 0.30, SE = 0.12 - Reward effect on choice: β = 1.15, SE = 0.16 - Demonstrator-observer bias correlation: r = .29 - Misattributed group sharing difference: β = 3.50, SE = 1.43 - BF for null (no awareness of demonstrator group preference) = 0.047
- **learning_from:** Other (demonstrator's biased choice actions) + world (reward outcomes from group member targets)
- **learning_about:** Social group members' reward value; group-level preference  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Hybrid RW with valenced reward learning + group-level action learning (Model 5: α+, α-, κ_group, β). Note: Model 6 (target-level) had lower mean AIC (115.17 vs 117.80) but authors report 57% group-level Akaike weight favoring Model 5.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "M1: Basic reward learning", "family": "RW", "n_params": 2, "metric": "AIC"} - {"name": "M2: Valenced reward learning", "family": "RW", "n_params": 3, "metric": "AIC"} - {"name": "M3: Group-level action learning", "family": "RW (action)", "n_params": 2, "metric": "AIC"} - {"name": "M4: Target-level action learning", "family": "RW (action)", "n_params": 2, "metric": "AIC"} - {"name": "M5: Valenced reward + group-level action (WINNING)", "family": "Hybrid RW", "n_params": 4, "metric": "AIC"} - {"name": "M6: Valenced reward + target-level action", "family": "Hybrid RW", "n_params": 4, "metric": "AIC"}
- **model_mb_mf:** MF
- **model_params:** - α+ (positive reward learning rate) [0,1]: Mean = .34, Median = .19 (Study 1, Model 6 reported; Model 5 not separately reported) - α- (negative reward learning rate) [0,1]: Mean = .29, Median = .08 - κ (action learning rate) [S] [0,1]: Mean = .13, Median = .02 - β (inverse temperature) [0.01, 100]: Mean = .56, Median = .12  Note: Table S3/S4 report parameters for Model 6 (target-level), not Model 5 (group-level). The paper designates Model 5 as winning by Akaike weights but only reports fitted parameters for Model 6.
- **social_param:** κ (action learning rate) -- captures how much the demonstrator's choice (action toward a social group member) shapes the observer's own valuation; this is the "value shaping" parameter
- **social_param_name:** κ
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 0–1
- **model_comparison_metric:** AIC (Akaike Information Criterion), Akaike weights
- **how_model_fit:** individual-level-fit (Nelder-Mead optimization with 50 random starting points per participant)
- **data_type_fit_to:** choice behavior (test phase choices)  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 290 (from 336 recruited; 156 women, 64 men, 1 other, 69 unreported; M_age = 19.42, SD = 1.26; NYU undergraduates)
- **population_category:** undergraduates
- **population_age_range:** 
- **ecological_validity:** Minimal social interaction -- participants observed avatar-based choices and binary monetary feedback. Groups were fictional with arbitrary color cues. No face-to-face interaction. Authors acknowledge "only a minimal form of social interaction.
- **eligibility_flag:** 
- **concerns:** Model 5 designated as winning by Akaike weight comparison (57% vs 43%) but Model 6 has lower mean AIC in Study 1 (115.17 vs 117.80) and all other studies -- this discrepancy is not fully explained. Fitted parameters only reported for Model 6, not the designated winning Model 5.
- **limitations_reported:** reliance on experimental tasks that, while permitting rigorous tests of our behavioral and computational hypotheses, presented only a minimal form of social interaction to observers"; authors note findings are consistent with more ecologically valid designs
- **limitations_categorized:** limited ecological validity; task simplicity
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 9.0
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - winning_model (MEDIUM): Paper designates Model 5 (group-level) as winning via Akaike weights (57% vs 43%), but Table S2 shows Model 6 (target-level) has lower mean AIC in all studies including Study 1 - model_params (MEDIUM): Fitted parameter values (Tables S3, S4) are reported for Model 6 only, not the designated winning Model 5 - wc_10 (MEDIUM): No explicit data/code sharing statement found in paper or supplement
- **cannot_find:** - Fitted parameter values for Model 5 (group-level hybrid) -- only Model 6 parameters reported in Tables S3/S4 - Explicit data/code availability statement
- **other_notes:** - Total N across all 6 studies = 1,550 (after exclusions: 290 + 114 + 141 + 339 + 365 + 303 = 1,552; paper states 1,550) - An "additional study" (N = ~120 after exclusions, based on Study 1 demonstrators) was conducted before Study 5 but deemed inconclusive and not included as a main study - Model recovery (Fig S12): 5 of 6 models were identifiable - Parameter recovery (Model 6): ρ = .54 (α+), .50 (α-), .67 (κ), .61 (β) - Studies 1 and 4-6 were preregistered; Studies 2-3 were not but were close replications - The paper is behavioural only -- no neuroimaging
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_vicarious_outcome
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- spec_target = partly
- tax_domain_D_group_structure_identity
- tax_mod_action_observation
- tax_mod_vicarious_outcome
- tax_model_MB_MF_hybrid
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_bonus
- tax_popclass_healthy
- tax_rr_domain = D_group_structure_identity
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_social_weight
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = intergroup_bias
- tax_rr_secondary_topic = stereotype_updating
- tax_rr_topic_intergroup_bias
- tax_rr_topic_stereotype_updating
- tax_topic_intergroup_bias
- tax_topic_stereotype_updating
