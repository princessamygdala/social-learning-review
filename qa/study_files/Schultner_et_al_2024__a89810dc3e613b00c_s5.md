# Schultner et al. (2024)

- **study_id:** `a89810dc3e613b00c_s5`
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
- **study_focus:** Testing whether a human demonstrator is necessary for observational bias transmission (human vs computer demonstrator)
- **study_focus_short:** Testing whether a human demonstrator is necessary for observational bias
- **learning_mode_description:** Same as Study 1 (note: in computer condition, "demonstrator" is described as algorithm, but the selection pattern is identical)
- **task_description:** Same paradigm but participants either observed a human demonstrator or were told selections were randomly determined by a computer algorithm, to test whether mental state inference is necessary.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (observer/participant), multi-target (8 avatars from 2 groups; yoked to demonstrator data, framed as human or computer)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Avatars representing social group members (blue/green group cues), binary monetary feedback ("Shared +1" or "Shared 0")
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Group bias not moderated by human vs computer condition (β = 0.60, Wald z = 1.84) - Group bias in human condition (β = 1.12, Wald z = 5.10) and computer condition (β = 1.77, Wald z = 7.23) - Misperceived group reward difference (β = 22.41, t = 9.59) - Perceived demonstrator preference (β = 8.32, t = 5.25) - Misperception of player feedback more strongly predicted preferences than perception of demonstrator preferences (F = 49.65) - Demonstrator-observer correlation: ρ = .22
- **effect_size:** - Group x Condition: β = 0.60, SE = 0.33 - Human group effect: β = 1.12, SE = 0.22 - Computer group effect: β = 1.77, SE = 0.25 - Group reward misperception: β = 22.41, SE = 2.34 - Demonstrator-observer: ρ = .22
- **learning_from:** Same as Study 1 (human or computer source)
- **learning_about:** Same as Study 1  ### ALGORITHMIC LEVEL  Same model space. Model 6 mean AIC = 100.04.
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Hybrid RW with valenced reward learning + group-level action learning (Model 5: α+, α-, κ_group, β). Note: Model 6 (target-level) had lower mean AIC (115.17 vs 117.80) but authors report 57% group-level Akaike weight favoring Model 5.
- **model_family:** Rescorla-Wagner
- **model_class:** Other
- **all_models_tested:** - {"name": "M1: Basic reward learning", "family": "RW", "n_params": 2, "metric": "AIC"} - {"name": "M2: Valenced reward learning", "family": "RW", "n_params": 3, "metric": "AIC"} - {"name": "M3: Group-level action learning", "family": "RW (action)", "n_params": 2, "metric": "AIC"} - {"name": "M4: Target-level action learning", "family": "RW (action)", "n_params": 2, "metric": "AIC"} - {"name": "M5: Valenced reward + group-level action (WINNING)", "family": "Hybrid RW", "n_params": 4, "metric": "AIC"} - {"name": "M6: Valenced reward + target-level action", "family": "Hybrid RW", "n_params": 4, "metric": "AIC"}
- **model_mb_mf:** MF
- **model_params:** α+ mean = .33, α- mean = .25, κ mean = .19, β mean = .42  All other algorithmic fields same as Study 1.  ### IMPLEMENTATION LEVEL  N/A. **analysis_type**: N/A  ### QUALITY
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
- **sample_size:** N = 365 (from 427; 184 human, 181 computer; 152 women, 193 men, 5 other, 12 unreported; M_age = 38.35, SD = 11.42; MTurk)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Same as Study 1; additional limitation that the "computer" condition tests a non-social source
- **eligibility_flag:** FLAG -- In the computer condition, the "social agent" is an automated system. The learning paradigm still involves social targets (group members), so this remains social learning, but the demonstrator source is non-social in one condition.
- **concerns:** Computer condition arguably tests non-social observational learning (source is automated system)
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
- spec_source = social
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
