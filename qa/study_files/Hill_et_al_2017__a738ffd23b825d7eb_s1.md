# Hill et al. (2017)

- **study_id:** `a738ffd23b825d7eb_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hill, C. A., Suzuki, S., Polania, R., Moisa, M., O'Doherty, J. P., & Ruff, C. C. (2017). A causal account of the brain network computations underlying strategic social behavior. *Nature Neuroscience*, *20*(8), 1142–1149. https://doi.org/10.1038/nn.4602
- **citation_short:** Hill et al. (2017)
- **doi:** 10.1038/nn.4602
- **publication_type:** peer-reviewed journal---
- **year:** 2017.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Laboratory for Social and Neural Systems Research (SNS-Lab), Department of Economics, University of Zurich, Zurich, Switzerland; ether neural computations in the rTPJ are TPJ (posterior superior temporal sulcus, pSTS)2; ether resemble the the associated neural processes in the stimulated area and intercon-; Institute of Development, Aging and Cancer, Tohoku University, Sendai, Miyagi, Japan; Division of the Humanities and Social Sciences, California Institute of Technology,; Institute of Technology, Pasadena, California, USA; University and ETH of Zurich, Zurich, Switzerland; ether disrupting
- **code_url:** 

## Computational level
- **study_focus:** Mentalizing learning / strategic social learning — how agents learn to anticipate the influence of their own actions on an opponent's future behavior during competitive interaction (second-order belief updating).
- **study_focus_short:** Mentalizing learning / strategic social learning
- **learning_mode_description:** - Learning mode: Learning from one's own and opponent's choice history about the opponent's likely future actions (second-order belief updating in competitive interaction)   - Learning from:     - Source type (social): other (anonymous opponent/employer)       - Source content (social): action/policy (opponent's choice history)     - Source type (non-social): self       - Source content (non-social): action/policy (own choice history)   - Learning about:     - Target type (social): other (opponent/employer)       - Target content (social): state (mental state; opponent's beliefs about the agent's strategy — second-order beliefs)
- **task_description:** In the inspection game (a 2x2 competitive game with asymmetric payoffs), the scanned participant played as Employee (choosing Work or Shirk) against a live human Employer over 160 trials, with outcomes determined jointly by both players' simultaneous choices. Before scanning, participants received inhibitory cTBS over either rTPJ or a vertex control site.
- **task_paradigm:** Inspection game
- **players:** Single agent (scanned participant as Employee), dyadic (anonymous human Employer opponent in adjacent room)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Abstract pictograms representing choice options (Work/Shirk), monetary point outcomes (0–100 points), binary feedback
- **method:** fMRI / TMS
- **method_full:** fMRI + TMS (cTBS)
- **main_result:** - Main Results:   - Influence model provided best fit to data vs. mixed equilibrium, RL, and fictitious play (DIC comparison; best in both cTBS groups)   - Influence parameter κ positively related to total payoff (t₅₄ = 2.38; unstandardized β not reported)   - rTPJ-cTBS reduced switch frequency vs. vertex-cTBS (t₅₆ = −2.04)   - rTPJ-cTBS increased predictability from past choice (t₅₆ = −2.03)   - rTPJ-cTBS reduced population-level κ (P_MCMC = 0.003)   - No significant cTBS effect on η (P_MCMC = 0.65) or β (P_MCMC = 0.12)   - Influence-update signal replicated in bilateral pSTS (R pSTS: MNI 54, −64, 4; t₅₆ = 6.36; L pSTS: MNI −48, −70, 10; t₅₆ = 5.12)   - rTPJ-cTBS reduced influence-update BOLD in rTPJ (MNI 39, −46, 28; t₅₅ = 3.65)   - rTPJ-cTBS reduced rTPJ–dmPFC connectivity at feedback (MNI −9, 41, 40; Ke = 332, nonparametric P_FWE = 0.03)   - rTPJ-cTBS reduced influence-update-related rTPJ–vmPFC connectivity (MNI 9, 26, −14; t₅₅ = 3.95)   - rTPJ–vmPFC connectivity disruption associated with reduced κ (t₅₁ = 2.84; interaction: t₅₁ = 2.34)   - κ strongly associated with logit past-choice predictability (t₅₄ = 7.39) and switch frequency (t₅₄ = 5.4)
- **effect_size:** - Main Results:   - Influence model provided best fit to data vs. mixed equilibrium, RL, and fictitious play (DIC comparison; best in both cTBS groups)   - Influence parameter κ positively related to total payoff (t₅₄ = 2.38; unstandardized β not reported)   - rTPJ-cTBS reduced switch frequency vs. vertex-cTBS (t₅₆ = −2.04)   - rTPJ-cTBS increased predictability from past choice (t₅₆ = −2.03)   - rTPJ-cTBS reduced population-level κ (P_MCMC = 0.003)   - No significant cTBS effect on η (P_MCMC = 0.65) or β (P_MCMC = 0.12)   - Influence-update signal replicated in bilateral pSTS (R pSTS: MNI 54, −64, 4; t₅₆ = 6.36; L pSTS: MNI −48, −70, 10; t₅₆ = 5.12)   - rTPJ-cTBS reduced influence-update BOLD in rTPJ (MNI 39, −46, 28; t₅₅ = 3.65)   - rTPJ-cTBS reduced rTPJ–dmPFC connectivity at feedback (MNI −9, 41, 40; Ke = 332, nonparametric P_FWE = 0.03)   - rTPJ-cTBS reduced influence-update-related rTPJ–vmPFC connectivity (MNI 9, 26, −14; t₅₅ = 3.95)   - rTPJ–vmPFC connectivity disruption associated with reduced κ (t₅₁ = 2.84; interaction: t₅₁ = 2.34)   - κ strongly associated with logit past-choice predictability (t₅₄ = 7.39) and switch frequency (t₅₄ = 5.4)
- **learning_from:** Other (opponent's choice history) + self (own choice history); opponent's actions and own actions jointly inform belief updating
- **learning_about:** Other (opponent); opponent's beliefs about the agent's own strategy (second-order beliefs)---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Influence model (fictitious play + second-order belief update; η first-order learning rate, κ influence/second-order belief weight, β inverse temperature)Formula: p^{NotInspect}_{t+1} = p^{NotInspect}_t + η(P_t − p^{NotInspect}_t) + κ(Q_t − q^{Work}_t)  where q^{Work}_t is the second-order belief (opponent's inferred probability the employee will Work), updated via the opponent's fictitious play model.
- **model_family:** Multi-agent RL
- **model_class:** PE learning / Belief updating
- **all_models_tested:** 1. {"name": "Mixed Nash Equilibrium (ME)", "family": "Random responding / game-theoretic equilibrium", "n_params": 1, "metric": "DIC"} 2. {"name": "Reinforcement Learning (RF)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "DIC"} 3. {"name": "Fictitious Play (FICT)", "family": "Fictitious play", "n_params": 2, "metric": "DIC"} 4. {"name": "Influence Model (INF)", "family": "Fictitious play + second-order beliefs", "n_params": 3, "metric": "DIC"}  (Also a mixture model variant controlling for random responding, but this was a robustness check, not a primary competitor.)
- **model_mb_mf:** MB (model-based — the influence model explicitly simulates the opponent's learning/beliefs)
- **model_params:** - η: first-order learning rate (tracks opponent's action history); population-level posterior mean not explicitly reported numerically - κ [S]: influence parameter / second-order belief weight (weight given to how own actions influence opponent's beliefs); rTPJ-cTBS < vertex-cTBS (P_MCMC = 0.003); mean fitted value not reported numerically - β: inverse temperature (softmax); population-level posterior mean not explicitly reported numerically  (Confidence: HIGH for parameter identification; MEDIUM for mean values — posterior distributions shown in figures but exact numerical means not provided in text)
- **social_param:** κ [S] — the influence parameter capturing the weight given to second-order beliefs about how the agent's own actions influence the opponent's future behavior.
- **social_param_name:** κ
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** DIC (Deviance Information Criterion — generalization of BIC for hierarchical Bayesian models)
- **how_model_fit:** Individual-level fit within hierarchical Bayesian framework (MCMC estimation with population-level priors; beta-distributed individual parameters with group-level hyperparameters)
- **data_type_fit_to:** Choice behavior (binary: Work/Shirk)---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors: expected value of chosen option at decision onset; reward, first-order PE, and influence update at feedback onset) + PPI (psychophysiological interaction analysis for connectivity)
- **contrast:** - Influence update signal > baseline (bilateral pSTS/TPJ) - Influence update: vertex-cTBS > rTPJ-cTBS (rTPJ) - PPI: rTPJ–dmPFC connectivity at feedback, vertex-cTBS > rTPJ-cTBS - PPI: rTPJ–vmPFC influence-update-modulated connectivity, vertex-cTBS > rTPJ-cTBS - Chosen value signal in vmPFC (vertex-cTBS group) - Influence model reliance × influence update in dmPFC
- **key_regions:** Influence update signal in bilateral pSTS/TPJ; cTBS reduced influence-update representation in rTPJ; disrupted rTPJ–dmPFC connectivity at feedback (dorsal dmPFC); disrupted rTPJ–vmPFC influence-update connectivity overlapping with value representation; vmPFC value coding present in vertex-cTBS but absent in rTPJ-cTBS group.
- **key_regions_abbrev:** vmPFC, mPFC, dmPFC, TPJ, STS
- **coordinates_peak:** - R pSTS (influence update, combined): 54, −64, 4 - L pSTS (influence update, combined): −48, −70, 10 - R pSTS/TPJ (influence update, vertex-cTBS): 45, −46, 28 - R dlPFC (influence update, vertex-cTBS): 51, 23, 37 - L dlPFC (influence update, vertex-cTBS): −39, 23, 49 - L pSTS/TPJ (influence update, vertex-cTBS): −33, −46, 46 - rTPJ (cTBS reduction of influence update): 39, −46, 28 - rTPJ stimulation site (surface): 61, −52, 35 - dmPFC (influence model reliance × influence update): −3, 44, 22 - dmPFC (PPI, cTBS-induced connectivity reduction): −9, 41, 40 - vmPFC (value signal, vertex-cTBS): 9, 29, −11 - vmPFC (PPI, influence-update connectivity): 9, 26, −14 - R Post.Occi/STS/TPJ (influence update, combined): 33, −88, −2 - Precuneus (influence update, combined): 6, −58, 49 - L Post.Occi (influence update, combined): −24, −68, −8 - L STS/TPJ (influence update, combined): −48, −70, 10 - R dlPFC (influence update, combined): 48, 17, 46 - L dlPFC (influence update, combined): −36, 26, 49
- **analysis_type:** Both (ROI analyses based on a priori coordinates from Hampton et al. 2008 + exploratory whole-brain analyses with nonparametric cluster-level FWE correction)---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 120 total (60 scanned Employees: 30 rTPJ-cTBS, 30 vertex-cTBS; 60 unscanned Employers); ages 18–25; 60 females. After exclusions: N = 58 for fMRI (1 lost data, 1 anxious in rTPJ-cTBS; 1 anxious in vertex-cTBS).
- **population_category:** healthy adults
- **population_age_range:** 18–25
- **ecological_validity:** Lab-based competitive game with real human opponents in adjacent room (enhances ecological validity vs. computer opponents); however, the inspection game is an abstract 2x2 matrix game with no naturalistic context; interaction is anonymous and mediated by computer interface.
- **eligibility_flag:** 
- **concerns:** - Between-subjects design for TMS manipulation limits ability to control for individual differences (acknowledged by authors) - Mean fitted parameter values (η, κ, β) not reported numerically — only posterior distributions shown in figures - Effect sizes for key behavioral comparisons are modest (t-values around 2.0) - 80% power calculated for large effect size (d = 0.75) only - No formal test of normality assumption for OLS regressions - Data from 2 participants excluded; questionnaire data incomplete for 3 additional participants
- **limitations_reported:** Between-subjects design makes it difficult to account for pre-existing group differences; directionality of rTPJ–dmPFC communication cannot be inferred from PPI alone; correlations between model-derived parameters and BOLD signals do not imply causal mapping; different competing models rarely directly tested against each other or assessed for stability by direct replications; PPI cannot determine direction of information flow between regions.
- **limitations_categorized:** Between-subjects design limitations; limited causal inference from connectivity analyses; model identifiability; limited generalizability; directionality of neural communication unclear
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params mean fitted values: MEDIUM — posterior distributions shown in figures but exact numerical means not reported in text - effect_size for κ–payoff relationship: MEDIUM — t-value reported but no standardized effect size (d, r, β)
- **cannot_find:** - Exact numerical mean fitted values for η, κ, β (shown graphically only) - Standardized effect sizes for behavioral comparisons (only t-values reported)
- **other_notes:** - This study extends Hampton et al. (2008) by adding a causal TMS manipulation - The influence model was originally developed by Hampton et al. (2008) — not novel to this paper - Data and code publicly available at https://doi.org/10.5281/zenodo.808428 - The paper provides strong causal evidence via TMS+fMRI combination for rTPJ's role in computing second-order beliefs - Nonparametric permutation testing (SnPM, 5000 permutations) used for whole-brain correction — methodologically rigorous
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_mentalizing_inference
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = structural
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_active_interaction
- tax_mod_mentalizing_inference
- tax_mod_multiplayer_live
- tax_model_MB
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = multi_agent_RL
- tax_rr_model_multi_agent_RL
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = strategic_reasoning
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_strategic_reasoning
- tax_topic_mentalizing
- tax_topic_strategic_reasoning
