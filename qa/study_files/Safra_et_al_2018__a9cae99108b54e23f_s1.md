# Safra et al. (2018)

- **study_id:** `a9cae99108b54e23f_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Safra, L., Chevallier, C., & Palminteri, S. (2018). Social information impairs reward learning in depressive subjects: Behavioral and computational characterization. *bioRxiv*, 378281. https://doi.org/10.1101/378281
- **citation_short:** Safra et al. (2018)
- **doi:** 10.1101/378281
- **publication_type:** preprint
- **year:** 2018.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Laboratoire de Neurosciences Cognitives, Institut National de la Santé et de la Recherche; Université de Recherche Paris Sciences et Lettres, Paris, France; ether the reward-learning deficit that is often associated with; ether deficits in reward processing interact; lable under; emails: lou.safra@gmail.fr, stefano.palminteri@ens.fr
- **code_url:** 

## Computational level
- **study_focus:** Social influence on reward learning in depression; how depressive symptoms interact with the social context during reinforcement learning (audience effect / observational learning)
- **study_focus_short:** Social influence on reward learning in depression
- **learning_mode_description:** - Learning mode: Learning from one's own reward outcomes and from a demonstrator's choices/outcomes about stimulus-reward associations, modulated by social context   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (reward/punishment feedback on own choices)     - Source type (social): other (virtual demonstrator)       - Source content (social): action/policy (demonstrator's choices) and outcome (demonstrator's reward outcomes)   - Learning about:     - Target type (non-social): world       - Target content (non-social): stimulus (stimulus-reward contingencies of abstract symbols)
- **task_description:** Participants performed a probabilistic reinforcement learning task where they chose between two abstract symbols to maximize rewards (+1 or -1 points), across three conditions: Private (no social information), Social-Choice (demonstrator's choice visible), and Social-Choice+Outcome (demonstrator's choice and outcome visible). The demonstrator was a virtual agent controlled by a Q-learning algorithm.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), single demonstrator (virtual/simulated partner)
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract symbols (agathodaimon font characters), binary reward feedback (+1/-1 points), avatar faces
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Depressive symptoms specifically reduced correct choice rate in the Social-Choice condition compared to Private (t(489) = -2.64, p = .009; coefficient = -0.05) - Effect replicated across discovery and replication samples (exploration: r = -.29; replication: r = -.37) - Computational analysis: depression associated with lower private learning rate in social contexts (α_S; z = -2.41, p = .016), indicating a secondary social learning deficit (audience effect) rather than primary social learning impairment - Model-based classifier detected severe depressive symptoms with 79% accuracy, 84% sensitivity - Social reinforcement learning model fit better than simple Q-learning (posterior probability: 90 +/- 3%; exceedance probability: 100%)
- **effect_size:** - Social-Choice x Depression interaction: coefficient = -0.05, SEM = 0.02 - Exploration sample correlation (depression x Social-Choice performance): r = -.29 - Replication sample correlation: r = -.37 - Model-free classifier accuracy: 76 +/- 1%, sensitivity: 78 +/- 2%, specificity: 63 +/- 3% - Model-based classifier accuracy: 79 +/- 1%, sensitivity: 84 +/- 1%, specificity: 53 +/- 3%
- **learning_from:** Self; own reward outcomes on chosen symbol. Other (demonstrator); demonstrator's choices and outcomes.
- **learning_about:** World; stimulus-reward contingencies of abstract symbols.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Social RL (6 params: α_P, β_P, α_S, β_S, κ, α_O)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Simple Q-learning", "family": "Rescorla-Wagner", "n_params": 2, "metric": "LPP (Laplace approximation)"}, {"name": "Social reinforcement learning model", "family": "Rescorla-Wagner with social extensions", "n_params": 6, "metric": "LPP (Laplace approximation)"}]
- **model_mb_mf:** MF
- **model_params:** - α_P (private learning rate): mean = 0.58 +/- 0.05 - β_P (private choice temperature): mean = 2.20 +/- 0.47 - α_S [S] (private learning rate in social contexts): mean = 0.60 +/- 0.06 — negatively correlated with depression (z = -2.41, p = .016) - β_S [S] (choice temperature in social contexts): mean = 1.83 +/- 0.34 - κ [S] (imitation rate): mean = 0.13 +/- 0.02 - α_O [S] (observational/vicarious learning rate): mean = 0.46 +/- 0.06
- **social_param:** - κ (imitation rate): governs how much the demonstrator's choice biases participant's subsequent choice in Social-Choice condition - α_O (observational learning rate): governs how demonstrator's outcome updates participant's value function in Social-Choice+Outcome condition - α_S (private learning rate in social context): captures the audience effect — reduction in private learning when social information is present; this is the parameter modulated by depression
- **social_param_name:** α_S
- **social_param_value:** 0.60
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** LPP (Laplace approximation to model evidence, log posterior probability); Bayesian model selection with posterior probability and exceedance probability
- **how_model_fit:** individual-level-fit (minimizing negative LPP per participant using Laplace approximation with priors)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 100 (two independent cohorts of N = 50 each; discovery + replication); ages 19-62, mean ~33; recruited via Amazon Mechanical Turk
- **population_category:** clinical
- **population_age_range:** 19–62
- **ecological_validity:** Online study via Amazon Mechanical Turk provides more diverse sample in terms of psychiatric traits than lab-based studies, but virtual demonstrator (algorithm-controlled) limits ecological validity of social interaction. Abstract symbols and point-based rewards are not naturalistic social stimuli. No real social interaction occurred.
- **eligibility_flag:** 
- **concerns:** The social agent is a virtual demonstrator controlled by a Q-learning algorithm, not a real human — this should be flagged. No control for participants' actual clinical diagnosis or medication status (self-report depression scores only via HAD scale). Online study with no verification of participant identity or attention beyond task performance checks.
- **limitations_reported:** We did not control for participants' actual diagnosis and treatment, which may be problematic since medication interacts with decision-making in depression"; "our results would benefit from being replicated in carefully controlled population, while controlling for medication status and medical history"; "we only tested its ability to detect high depressive scores as identified by a self-rated scale"; no neuroimaging data to determine whether social learning engaged domain-specific social cognitive modules or domain-general information processing modules
- **limitations_categorized:** No clinical diagnosis verification; no medication control; self-report measures only; no neuroimaging; limited ecological validity (virtual demonstrator); limited generalizability (online convenience sample)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 9.0
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** yes
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `social_param` — MEDIUM: α_S is technically a private learning rate parameter operating in social contexts, not a purely "social" parameter; its classification as social is based on it capturing the audience effect - `effect_size` — MEDIUM: Some effect sizes (e.g., for SEM analysis) reported as z-values and p-values; Cohen's d or standardized betas not always provided - `wc_guidelines` rule 10 — MEDIUM: No explicit mention of data/code sharing; marked as Partial
- **cannot_find:** - Exact fitted parameter values per condition broken down by depression group (only overall means reported in Table 3) - Exact AIC/BIC values (only posterior probability and exceedance probability reported) - Code or data availability statement
- **other_notes:** This is a bioRxiv preprint (July 2018). A published version may exist — potential duplicate check recommended. The virtual demonstrator is algorithm-controlled (Q-learning with α=0.5, β=10), which should be flagged for the review as the social agent is automated. Two independent samples (discovery + replication) but analyzed together as one study — counts as 1 row. Supplement not available (preprint with no supplement found).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_anxiety
- pop_depression
- pop_healthy_adults
- rr_pop_anxiety
- rr_pop_depression
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target+context
- spec_source = partly
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = imitation_emulation
- tax_rr_topic_imitation_emulation
- tax_rr_topic_social_info_use
- tax_topic_imitation_emulation
- tax_topic_social_info_use
