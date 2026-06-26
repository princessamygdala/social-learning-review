# Wu et al. (2024)

- **study_id:** `a8f3eec4be8a10e95_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Wu, C. M., Deffner, D., Kahl, B., Meder, B., Ho, M. H., & Kurvers, R. H. J. M. (2024). Visual-spatial dynamics drive adaptive social learning in immersive environments. *bioRxiv*. https://doi.org/10.1101/2023.06.28.546887
- **citation_short:** Wu et al. (2024)
- **doi:** 10.1101/2023.06.28.546887
- **publication_type:** preprint
- **year:** 2024.0
- **field_of_study:** Psychology
- **affiliations_raw:** InstituteforMind,BrainandBehavior,DepartmentofPsychology,HealthandMedicalUniversity,Potsdam,DE; DepartmentofComputationalNeuroscience,MaxPlanckInstituteforBiologicalCybernetics,Tu¨bingen,DE; etheoriesacrossasocialandsocialdomains,butalsoprovidekeyinsightsintotheadaptability; CentreforAdaptiveRationality,MaxPlanckInstituteforHumanDevelopment,Berlin,DE; ethods),wecanidentifywhich manipulatedtherewarddistribution(randomvs; mitatorsina Usinganovelmethodforautomatingthetranscriptionofvi-; mit—individual Here,weuseacollectiveforagingtaskprogrammedinan; DepartmentofComputerScience,PrincetonUniversity
- **code_url:** 

## Computational level
- **study_focus:** Collective foraging; adaptive integration of asocial and social learning; success-biased social learning; area-restricted search
- **study_focus_short:** Collective foraging
- **learning_mode_description:** - Learning mode: Learning from own foraging outcomes and observation of others' foraging success to adaptively forage and selectively imitate successful peers in a collective foraging environment.   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (individual foraging reward)     - Source type (social): other (visible group members)       - Source content (social): outcome (observed reward splash from other players)   - Learning about:     - Target type (non-social): world (spatial reward distribution)       - Target content (non-social): state (world state; where rewards are located)     - Target type (social): other (successful peers)       - Target content (social): action/policy (spatial location/foraging behavior to imitate)
- **task_description:** Participants (n=128, in groups of 4) foraged for hidden rewards in a 20x20 grid of blocks in an immersive Minecraft environment, with reward structures that were either random or spatially smooth (clustered), across solo and group conditions. In group rounds, participants could observe others' foraging successes (visible blue splash) and choose to approach or avoid peers, while competing for finite resources.
- **task_paradigm:** Stereotype learning task
- **players:** Multi-agent (groups of 4 participants), competitive (shared finite resource pool)
- **n_players:** 
- **partner_type:** human (live)
- **stimuli:** Virtual Minecraft environment with pumpkin/watermelon blocks (counterbalanced), blue splash reward feedback visible to other players, binary reward outcomes
- **method:** behavioural
- **method_full:** behavioural (computer-based virtual environment experiment)
- **main_result:** - Greater rewards in smooth vs. random environments (posterior mean: 0.22, 95% HPDI [0.19, 0.24]) - No effect of social condition on aggregate performance (0.002, [-0.02, 0.02]) - Adaptive foraging distance predicted performance in smooth environments (solo: r_tau = .20, BF = 32; group: r_tau = .18, BF = 9.9) - Success-biased social learning in smooth environments: successful proximity weight = 1.0 [0.8, 1.2]; substantially reduced in random environments (0.29 [0.07, 0.53]) - Greater social adaptation predicted better performance in group rounds (Adapt. Success: 2.99 [0.41, 5.58]) - Greater asocial adaptation predicted better performance in solo rounds (Adapt. Prox: -2.34 [-3.72, -1.03]) - ARS+Cond model vastly outperformed all others in group rounds (p(bestModel) > .999) - Success-biased cycling in smooth environments: positive correlation cluster at offset -19s to -2s between reward and proximity - Leaders received more rewards than followers during pull events (0.6 [0.3, 0.9])
- **effect_size:** - Smooth vs. random reward: posterior mean = 0.22, 95% HPDI [0.19, 0.24] - Adaptive distance-performance (smooth solo): r_tau = .20, BF = 32 - Adaptive distance-performance (smooth group): r_tau = .18, BF = 9.9 - ARS+Cond model: p(bestModel) > .999 (protected exceedance probability) - Leader vs. follower reward during pull events: 0.6 [0.3, 0.9] - Social adaptation-performance (smooth group): 2.99 [0.41, 5.58] - Asocial adaptation-performance (smooth solo): -2.34 [-3.72, -1.03]
- **learning_from:** Self; own foraging reward outcomes. Other; observed reward events from visible peers (success-biased). Source: self + other (group members).
- **learning_about:** World; spatial reward distribution (via Gaussian process reward prediction). Other; spatial location of successful peers for imitation. Target: world + other.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** ARS+Cond (Area-Restricted Search + Conditional social learner): softmax over linear combination of block features with adaptive weights. Locality and success-biased proximity weights adapt as a function of time since last individual reward. Features: Locality, Block Visibility, Reward Prediction (GP), Successful Proximity [S], Unsuccessful Proximity [S]. Dynamic weights: w_tilde = w + alpha * delta_t.
- **model_family:** Gaussian process
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Asocial", "family": "Softmax regression + GP", "n_params": 3, "metric": "WAIC + BMS"},   {"name": "Unbiased", "family": "Softmax regression + GP + social proximity", "n_params": 4, "metric": "WAIC + BMS"},   {"name": "Success-biased", "family": "Softmax regression + GP + success/unsuccess proximity", "n_params": 5, "metric": "WAIC + BMS"},   {"name": "Player-specific", "family": "Softmax regression + GP + player-specific proximity", "n_params": 6, "metric": "WAIC + BMS"},   {"name": "ARS (Area-Restricted Search)", "family": "Softmax regression + GP + adaptive locality", "n_params": 4, "metric": "WAIC + BMS"},   {"name": "Critical learner", "family": "Softmax regression + GP + success-biased + adaptive reward pred.", "n_params": 6, "metric": "WAIC + BMS"},   {"name": "Conditional learner", "family": "Softmax regression + GP + adaptive success/unsuccess proximity", "n_params": 7, "metric": "WAIC + BMS"},   {"name": "ARS+Cond (winning)", "family": "Softmax regression + GP + ARS + conditional social learning", "n_params": 8, "metric": "WAIC + BMS"} ]
- **model_mb_mf:** MB (model-based; Gaussian process generalization constitutes an internal model of the reward environment)
- **model_params:** - w_Locality: weight for inverse distance to player's current position (smooth group: population-level estimate from Fig 4d) - w_BlockVisibility: weight for blocks in player's field of view (binary) - w_RewardPrediction: weight for GP-based reward probability (smooth group: 0.41 [0.38, 0.45]) - w_SuccessfulProximity [S]: weight for proximity to visible, recently successful players (smooth: 1.0 [0.8, 1.2]; random: 0.29 [0.07, 0.53]) - w_UnsuccessfulProximity [S]: weight for proximity to visible, unsuccessful players (smooth: 0.004 [-0.14, 0.15]; random: 0.10 [-0.07, 0.25]) - alpha_Locality (ARS adaptation): rate of locality adaptation as function of time since last individual reward (smooth group: -0.91 [-1.05, -0.77]) - alpha_SuccessfulProximity [S] (Cond adaptation): rate of success-biased proximity adaptation (smooth: 0.4 [0.2, 0.5]; random: 0.10 [-0.07, 0.25]) - alpha_UnsuccessfulProximity [S] (Cond adaptation): rate of unsuccessful proximity adaptation - GP length scale l = 4 (fixed, equivalent to 48 in coordinate scale) - GP noise variance sigma_epsilon^2 = 0.0001 (fixed) - GP prior mean z_0 = log(0.25 / 0.75) (fixed)
- **social_param:** w_SuccessfulProximity [S]: weight on proximity to visible peers who were observed acquiring a reward. alpha_SuccessfulProximity [S]: adaptation rate of success-biased social imitation as a function of time since last individual reward. w_UnsuccessfulProximity [S]: weight on proximity to visible peers not observed acquiring a reward.
- **social_param_name:** w_SuccessfulProximity
- **social_param_value:** 1.0
- **social_param_sd:** 
- **social_param_range:** 0.8–1.2
- **model_comparison_metric:** Bayesian Model Selection (protected exceedance probability via Rigoux et al., 2014) + WAIC (Widely Applicable Information Criterion) for individual-level comparison
- **how_model_fit:** individual-level-fit (hierarchical Bayesian framework with individual and group random effects, fitted via Hamiltonian Monte Carlo / Stan)
- **data_type_fit_to:** choice behavior (sequential block destruction choices)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** N = 128 (82 female; M_age = 27.4, SD = 5.0); tested in groups of 4 (32 groups); 16 rounds per participant (counterbalanced: 4 conditions x 4 rounds each)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** High ecological validity relative to typical lab tasks. Immersive Minecraft environment imposes natural visual constraints (limited field of view), competitive resource dynamics, and continuous spatial trajectories. However, still a lab-based virtual environment with simplified reward structures (binary outcomes) and short timescales (2-minute rounds). Authors note the environment captures dynamics analogous to marketplace innovation and scientific research.
- **eligibility_flag:** 
- **concerns:** Preprint (not peer-reviewed). GP length scale parameter was fixed (l=4, matching the generating process), meaning reward prediction model was tuned to the true environment structure rather than learned. Agent-based simulations used arbitrary feature weights set to 1. The adaptive model parameters (number of free parameters) differ across models being compared, though WAIC and BMS should penalize complexity. Success-biased social learning persisted even in random environments where it was not adaptive, suggesting incomplete adaptation.
- **limitations_reported:** success-biased social learning was also present in random environments"; "participants were still somewhat drawn towards successful peers" even when "resources being distributed randomly"; "success-biased copying is hard for people to unlearn"; "participants may have believed there to be structure in random environments"; "these results suggest potential limitations to the degree of human adaptability and a lingering bias towards social learning"; "a more complete understanding requires connecting social learning mechanisms observed at short timescales to adaptive outcomes over long, cultural timescales
- **limitations_categorized:** limited adaptability (persistence of social learning bias in non-adaptive settings); limited ecological validity (short timescales, lab-based virtual environment); limited generalizability (non-depleting environments and cumulative cultural innovation not tested); task simplicity (binary reward outcomes)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_mb_mf: MEDIUM confidence. The GP component is model-based (internal model of reward distribution), but the social imitation component is more heuristic/model-free. Classified as MB because the GP reward prediction is the core learning mechanism. - n_params for all_models_tested: MEDIUM confidence. Exact parameter counts are inferred from the described features; the paper does not provide an explicit parameter count table. Each feature has a population-level weight + random effects structure, so "n_params" reflects the number of feature weights, not the total number of estimated parameters including hierarchical structure. - wc_rule_8 (validate winning model): MEDIUM confidence. Behavioral validation is provided but no formal posterior predictive check. - publication_type: HIGH confidence. Clearly a bioRxiv preprint.
- **cannot_find:** - Exact total number of free parameters per model (paper describes features but not a parameter count table) - Formal posterior predictive checks - Parameter recovery analysis - Model recovery / confusion matrix
- **other_notes:** This is a bioRxiv preprint (version posted October 16, 2024). A pilot version was presented at CogSci 2021 (Wu et al., 2021, ref 81), but with different data and design. The computational modeling framework is a softmax choice model over block features rather than a traditional RL model with explicit value updating; the Gaussian process provides the reward prediction component. No supplement file was found separate from the main text; supplementary material is included within the same document (Figures S1-S15 and supplementary methods). Data and code are publicly available.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_multiplayer_live
- rr_tax_mod_social_info_search
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_domain_C_exchange_interdependence
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_mod_social_info_search
- tax_model_MB
- tax_model_gaussian_process
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = gaussian_process
- tax_rr_model_gaussian_process
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = cooperation
- tax_rr_topic_cooperation
- tax_rr_topic_social_info_use
- tax_topic_cooperation
- tax_topic_social_info_use
