# Schultner et al. (2024)

- **study_id:** `a89810dc3e613b00c_s6`
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
- **study_focus:** Effect of perceived demonstrator competence on observational bias transmission
- **study_focus_short:** Effect of perceived demonstrator competence on observational bias transmission
- **learning_mode_description:** - Learning mode: Learning from observing a demonstrator's biased choices and targets' reward feedback about group members' reward value   - Learning from:     - Source type (social): other (demonstrator)       - Source content (social): action/policy (choice behavior toward group members)     - Source type (non-social): world       - Source content (non-social): outcome (reward feedback from chosen target)   - Learning about:     - Target type (social): group (two social groups)       - Target content (social): stimulus (reward value / preference for group members)
- **task_description:** Same paradigm but participants were told the demonstrator performed either well (80% correct) or poorly (40% correct) on a prior task, to test whether perceived competence modulates the strength of observational bias acquisition.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (observer/participant), multi-target (8 avatars from 2 groups; yoked to demonstrator, 2 participants per demonstrator per condition)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Same as Study 1, plus graphical competence manipulation (performance display)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Group bias present (β = 0.49, Wald z = 2.52) - Competence moderated demonstrator-observer bias link (interaction: β = -0.51, Wald z = -2.66) - High competence: r = .49 demonstrator-observer correlation - Low competence: r = .28 demonstrator-observer correlation - No competence x group membership interaction on overall group bias (β = -0.24, Wald z = -0.62, BF(incl) = 0.01) - Misperceived group sharing difference (β = 2.43, Wald z = 3.15)
- **effect_size:** - Group effect: β = 0.49, SE = 0.20 - Competence x Observed bias interaction: β = -0.42, SE = 0.19 (robust to outlier exclusion) - High competence dem-obs correlation: ρ = .51 (Spearman) - Low competence dem-obs correlation: ρ = .30 - Group misperception: β = 2.43, SE = 0.77
- **learning_from:** Other (demonstrator's biased choice actions) + world (reward outcomes from group member targets)
- **learning_about:** Same as Study 1  ### ALGORITHMIC LEVEL  Same model space. Model 6 mean AIC = 97.98 (lowest across all studies).
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Hybrid RW with valenced reward learning + group-level action learning (Model 5: α+, α-, κ_group, β). Note: Model 6 (target-level) had lower mean AIC (115.17 vs 117.80) but authors report 57% group-level Akaike weight favoring Model 5.
- **model_family:** Rescorla-Wagner
- **model_class:** Other
- **all_models_tested:** - {"name": "M1: Basic reward learning", "family": "RW", "n_params": 2, "metric": "AIC"} - {"name": "M2: Valenced reward learning", "family": "RW", "n_params": 3, "metric": "AIC"} - {"name": "M3: Group-level action learning", "family": "RW (action)", "n_params": 2, "metric": "AIC"} - {"name": "M4: Target-level action learning", "family": "RW (action)", "n_params": 2, "metric": "AIC"} - {"name": "M5: Valenced reward + group-level action (WINNING)", "family": "Hybrid RW", "n_params": 4, "metric": "AIC"} - {"name": "M6: Valenced reward + target-level action", "family": "Hybrid RW", "n_params": 4, "metric": "AIC"}
- **model_mb_mf:** MF
- **model_params:** α+ mean = .31, α- mean = .26, κ mean = .15, β mean = .56  All other algorithmic fields same as Study 1.  ### IMPLEMENTATION LEVEL  N/A. **analysis_type**: N/A  ### QUALITY
- **social_param:** κ (action learning rate) -- captures how much the demonstrator's choice (action toward a social group member) shapes the observer's own valuation; this is the "value shaping" parameter
- **social_param_name:** κ
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC
- **how_model_fit:** individual-level-fit
- **data_type_fit_to:** choice behavior  ### IMPLEMENTATION LEVEL  Same as Study 1 (no neuroimaging). **analysis_type**: N/A  ### QUALITY

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
- **sample_size:** N = 303 (from 355; 149 women, 149 men, 1 other, 2 nonconforming, 2 unreported; M_age = 40.76, SD = 12.25; MTurk)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Same as Study 1; competence manipulation adds ecological dimension
- **eligibility_flag:** 
- **concerns:** None additional
- **limitations_reported:** Same as overall paper
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
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- spec_target = social
- tax_domain_D_group_structure_identity
- tax_mod_action_observation
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_param_learning_rate
- tax_param_social_bonus
- tax_param_valence_asymmetry
- tax_popclass_healthy
- tax_rr_domain = D_group_structure_identity
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_social_weight
- tax_rr_primary_topic = intergroup_bias
- tax_rr_secondary_topic = stereotype_updating
- tax_rr_topic_intergroup_bias
- tax_rr_topic_stereotype_updating
- tax_topic_intergroup_bias
- tax_topic_stereotype_updating
