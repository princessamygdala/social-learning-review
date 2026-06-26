# Gershman et al. (2017)

- **study_id:** `a894d6f4ea6856b0c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Gershman, S. J., Pouncy, H. T., & Gweon, H. (2017). Learning the structure of social influence. *Cognitive Science, 41*(Suppl. 3), 545–575. https://doi.org/10.1111/cogs.12480
- **citation_short:** Gershman et al. (2017)
- **doi:** 10.1111/cogs.12480
- **publication_type:** peer-reviewed journal
- **year:** 2017.0
- **field_of_study:** Psychology
- **affiliations_raw:** ether, our findings demonstrate that structure learning is a powerful framework for explaining; ether other toys share similar features (Gweon, Tenenbaum, & Schulz, 2010) and how; mpirical results on infants’ understanding of others’ preferences, presenting an; Departmentof Psychology andCenterforBrain Science, HarvardUniversity; lab-raised rhesus monkeys develop fear responses to snakes; Department of Psychology, Harvard University, 52; Departmentof Psychology,StanfordUniversity; mpirical and the-; emails: gershman@fas.harvard.edu
- **code_url:** 

## Computational level
- **study_focus:** Social influence learning / social structure learning — how people infer latent social group structure from observed choice patterns and use this to guide their own choices.
- **study_focus_short:** Social influence learning / social structure learning
- **learning_mode_description:** - Learning mode: Learning from others' observed choice patterns about latent social group structure to guide own future choices   - Learning from:     - Source type (social): other / group (multiple individuals A, B, C)     - Source content (social): action/policy (observed binary choices between items)   - Learning about:     - Target type (social): group / social structure (latent group assignments)     - Target content (social): state (latent social group membership; shared utility functions/preferences)
- **task_description:** Participants chose between pairs of movie posters, then observed 2-3 other individuals' choices between the same pairs. On critical "mystery choice" trials, participants chose between two unknown items after seeing the other individuals make opposite choices, or explicitly grouped the individuals, or re-rated familiar movies.
- **task_paradigm:** Social influence task
- **players:** Single agent (participant), multi-target (2-3 other individuals with manipulated choice overlap)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Movie poster images (48 movies, 24 genre-matched pairs), binary choices, mystery items (question marks)
- **method:** online / behavioural
- **method_full:** behavioural / online (Amazon Mechanical Turk)
- **main_result:** - Main Results:   - Exp 1: Significant effect of choice overlap condition on probability of following Individual B (F(171) = 7.33, p < .001); 25-75 condition significantly above chance (t(60) = 5.03); model r with data not reported for Exp 1 but qualitative fit shown   - Exp 2: Probability of following B significantly different between 75% and 25% agreement conditions (t(151) = 3.31, p < .005) — no free parameters fit (zero-parameter prediction)   - Exp 3: Model-data correlation across 7 conditions (r = .79, p < .05, permutation test) — zero free parameters   - Exp 4: P+B groupings significantly more likely than P+A groupings despite equal dyadic overlap (t(103) = 3.93, p < .001); model-data correlation on log-transformed grouping probabilities (r = .57, p < .05)   - Exp 5: Significant positive rating change in response to B's endorsement (t(108) = 3.09, p < .005), but not A's endorsement (t(108) = 1.32, p = .19)
- **effect_size:** F(171) = 7.33; t(60) = 5.03; t(151) = 3.31; r = .79 (Exp 3 model-data); t(103) = 3.93; r = .57 (Exp 4 model-data); t(108) = 3.09
- **learning_from:** Others' observed binary choices between items (source: other/group)
- **learning_about:** Latent social group structure; shared preference/utility structure (target: group/social structure)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Bayesian nonparametric structure learning with Chinese Restaurant Process prior over group assignments + Dirichlet-Multinomial likelihood + Luce choice rule (1 free parameter: inverse temperature β)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - [{"name": "Bayesian latent group model (CRP + Dirichlet-Multinomial)", "family": "Bayesian nonparametric", "n_params": 1, "metric": "squared error (grid search)"}] - Note: Dyadic similarity models are discussed as a comparison class but are not formally fit — they serve as a theoretical contrast rather than a quantitatively compared alternative.
- **model_mb_mf:** Bayesian
- **model_params:** - β (inverse temperature / response stochasticity): MLE = 11.05 (fit from Exp 1 via grid search over squared error; used for all subsequent experiments) - α (concentration parameter of CRP): integrated out (uniform prior on [0.00001, 10]); not a free parameter - γ (Dirichlet hyperparameter): fixed at 1 (uniform distribution); sensitivity analysis showed negligible effect of changing to 0.1 or 2
- **social_param:** α (concentration parameter) [S] — controls the tendency to create new social groups vs. assign individuals to existing groups. Higher α favors more groups (more social differentiation). In developmental simulations, lower α for younger children reflects stronger bias toward single-group (shared preferences) structure.
- **social_param_name:** α
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 0.00001–10
- **model_comparison_metric:** Squared error minimization (grid search) for β; qualitative model comparison against dyadic similarity models (theoretical, not formal statistical comparison)
- **how_model_fit:** Group-level fit — β was fit to aggregate data from Experiment 1 by minimizing squared error between model predictions and group-level choice probabilities; same β used for Experiments 2-5 with no additional fitting.
- **data_type_fit_to:** Choice behavior (binary choice probabilities; grouping judgments in Exp 4; rating changes in Exp 5)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** Exp 1: N = 172 (61, 51, 60 across conditions); Exp 2: N = 152; Exp 3: N = 305; Exp 4: N = 104; Exp 5: N = 109. Total N = 842. All adults recruited via Amazon Mechanical Turk.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Online paradigm using real movie posters provides some ecological validity for preference/choice domain. However, choices between pairs of movie posters are relatively simple compared to real-world social learning, and "other individuals" were simulated (choices were predetermined by experimenters to achieve target overlap percentages). Experiment 5 provides a more ecologically valid test by examining changes in ratings for familiar items.
- **eligibility_flag:** Borderline — the model is Bayesian structure learning (inference), not iterative trial-by-trial learning with prediction errors. Learning occurs over the course of observing choices (accumulating evidence for group assignments via Bayesian updating), so there is temporal updating. However, this is closer to one-shot Bayesian inference over accumulated data than incremental trial-by-trial learning. FLAG: borderline learning-vs-inference case. The model performs Bayesian inference over the full set of observed choices rather than sequential updating, though the developmental simulations show how the prior shifts with accumulating experience.
- **concerns:** - The "other individuals" are not real — their choices are predetermined by experimenters. This is acknowledged but limits claims about genuine social interaction. - Only one free parameter (β) was fit, and only to Experiment 1. While this is presented as a strength (parsimony), it also means the model was not rigorously compared against fitted alternatives. - Dyadic similarity models are discussed as a theoretical contrast but never formally fit or statistically compared — the comparison is conceptual rather than quantitative. - The developmental simulations (Repacholi & Gopnik; Doan et al.) are post-hoc qualitative demonstrations, not quantitative model fits. - α is integrated out rather than fit, which is principled but means individual differences in grouping tendency are not captured.
- **limitations_reported:** Although we used a Bayesian modeling framework to formalize latent grouping, other clustering algorithms (e.g., K-means) might also have been able to capture our findings"; the model assumes a single grouping structure rather than cross-cutting categories; social influence is modeled in one direction only (from others to participant); explicit group cues (age, gender, language) are ignored; the model is agnostic to features of choices; changes in ratings may reflect anticipated utility rather than actual preference change; the model does not claim to infer "true preferences" but rather expected utility from group structure.
- **limitations_categorized:** Limited model comparison; task simplicity; unidirectional social influence; no feature-based choice modeling; limited ecological validity; no real social interaction; post-hoc developmental simulations
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - eligibility_flag: MEDIUM — borderline learning-vs-inference; Bayesian inference over accumulated choices rather than iterative trial-by-trial learning - model_comparison_metric: LOW — β fit by squared error grid search; no formal model comparison statistic (BIC, AIC, etc.) because only one model was formally tested - social_param: MEDIUM — α is integrated out, not fit; its role as "social parameter" is interpretive (controls group differentiation tendency) - wc_guidelines rule 7: HIGH — only one model formally fit; dyadic models discussed but not implemented
- **cannot_find:** - No supplement available; no supplement referenced in the paper - No formal model comparison statistics (BIC, AIC, etc.) - No parameter recovery analysis - No data or code sharing links - No effect sizes in standard units (Cohen's d, η²) — only t-values, F-values, and correlations reported
- **other_notes:** - This paper is primarily a computational cognitive science / Bayesian modeling paper rather than a computational psychiatry or neuroscience paper. It focuses on social cognition and structure learning. - The model has strong connections to nonparametric Bayesian methods (Chinese Restaurant Process, Dirichlet process mixtures) from machine learning. - The developmental application (simulating Repacholi & Gopnik, 1997; Doan et al., 2015) is a secondary contribution — qualitative demonstration, not a formal model fit. - The paper treats all 5 experiments as a single coherent study with one model and one fitted parameter, making it appropriate to extract as a single row.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_social_info_search
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_D_group_structure_identity
- tax_mod_action_observation
- tax_mod_social_info_search
- tax_model_bayesian
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = D_group_structure_identity
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_network_structure
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_social_info_use
- tax_rr_topic_social_network_structure
- tax_topic_social_info_use
- tax_topic_social_network_structure
