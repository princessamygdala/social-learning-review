# Barnby et al. (2022)

- **study_id:** `afd606b4dc8edcad1_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Barnby, J. M., Mehta, M. A., & Moutoussis, M. (2022). The computational relationship between reinforcement learning, social inference, and paranoia. *PLoS Computational Biology*, *18*(7), e1010326. https://doi.org/10.1371/journal.pcbi.1010326
- **citation_short:** Barnby et al. (2022)
- **doi:** 10.1371/journal.pcbi.1010326
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Psychology
- **affiliations_raw:** CollegeLondonmemberoftheMRCDoctoral opmentofsymptomsofseverementaldisorders,suchaspersecutorydelusions; DepartmentofPsychology,RoyalHolloway,UniversityofLondon,London,UnitedKingdom,2 Culturaland; lablehere: takeslongertoresolve,althoughwedemonstratethatthisuncertaintyisexpressedasym-; UCLCentre ingtherelationshipbetweencomputationalmechanismsgoverningnon-socialdecision; CollegeLondon,UniversityofLondon,London,UnitedKingdom,4 WellcomeCentre; etherthesamepopulation(n=693)respondedsimilarlytonon-socialandsocial; UniversityCollegeLondon,London,UnitedKingdom,5 Max-Planck–UCLCentre; DepartmentofNeur
- **code_url:** 

## Computational level
- **study_focus:** Paranoia and social inference learning; relationship between non-social reinforcement learning and social attribution updating under contingency reversals, and how pre-existing paranoia modulates both.
- **study_focus_short:** Paranoia and social inference learning
- **learning_mode_description:** - Learning mode: Learning from partner's sharing behaviour about partner's harmful intent and self-interest attributions, and from non-social probabilistic feedback about card reward contingencies   - Learning from:     - Source type (social): other (partner/dictator)       - Source content (social): action/policy (sharing decisions)     - Source type (non-social): world       - Source content (non-social): outcome (reward feedback from card selection)   - Learning about:     - Target type (social): other (partner/dictator)       - Target content (social): state (mental state; harmful intent and self-interest attributions)     - Target type (non-social): world       - Target content (non-social): stimulus (card reward contingencies)
- **task_description:** Participants completed a 60-trial probabilistic reversal learning task (choosing among three cards with different reward probabilities that reversed at trial 30) and a 20-trial modified repeated reversal Dictator Game (inferring a partner's harmful intent and self-interest from their fair/unfair allocation decisions, with partner policy reversing at trial 10).
- **task_paradigm:** Dictator game
- **players:** Single agent (participant), single target (computer-programmed partner in Dictator Game; no social agent in reversal learning task). N=693.
- **n_players:** network (5+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract card symbols with probabilistic reward/loss outcomes (+10 or -5 points); avatars representing Dictator partner, monetary allocation decisions (split vs. keep 10 points), 0–100 rating scales for harmful intent and self-interest attributions.
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Paranoia associated with increased decision temperature (τ) in the non-social reversal learning task (β = 0.13, 95% CI: 0.05, 0.20) - Paranoia associated with stronger priors over harmful intent (pHI₀; β = 0.16, 95% CI: 0.09, 0.24), greater uncertainty over partner policies (uπ; β = 0.17, 95% CI: 0.10, 0.25), and greater sensitivity to update self-interest attributions (wSI; β = 0.15, 95% CI: 0.08, 0.22) in the social task - Decision temperature in non-social task positively associated with strength of priors over harmful intent (ρ = 0.16) and paranoia (ρ = 0.16), bridging non-social and social computational mechanisms - Paranoia associated with choosing worst card after reversal (β = 0.04, 95% CI: 0.01, 0.08) and greater win-switch rates after reversal (β = 0.09, 95% CI: 0.02, 0.17) in the non-social task - Harmful intent attributions were more rigid (less flexible to reversal) in higher paranoia (β = -0.05, 95% CI: -0.08, -0.03)
- **effect_size:** β = 0.13 (95% CI: 0.05, 0.20) for paranoia–decision temperature; β = 0.16 (95% CI: 0.09, 0.24) for paranoia–pHI₀; β = 0.17 (95% CI: 0.10, 0.25) for paranoia–uπ; β = 0.15 (95% CI: 0.08, 0.22) for paranoia–wSI; ρ = 0.16 for decision temperature–pHI₀; ρ = 0.16 for decision temperature–paranoia
- **learning_from:** Non-social task: world; reward outcome on chosen card. Social task: other (partner); partner's sharing/allocation decisions.
- **learning_about:** Non-social task: world; card reward contingencies. Social task: other (partner); partner's harmful intent and self-interest attributions (mental states/traits).  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** - Non-social task: Modified Pearce-Hall Q-learning with reset-at-reversal (5 params: τ, λ, S, φ, ηpr) - Social task: Extended Bayesian-Belief attribution model with single switching parameter (9 params: pHI₀, uHI₀, pSI₀, uSI₀, uπ, w₀, wHI, wSI, ηdg)
- **model_family:** Bayesian
- **model_class:** PE learning / Belief updating
- **all_models_tested:** - Non-social task (k=8):   - [{"name": "Q-learning (core 3-param)", "family": "Q-learning", "n_params": 3, "metric": "BIC/AIC"}]   - [{"name": "Q-learning + Pearce-Hall salience", "family": "Q-learning + Pearce-Hall", "n_params": 3, "metric": "BIC/AIC"}]   - [{"name": "Q-learning + memory decay", "family": "Q-learning", "n_params": 4, "metric": "BIC/AIC"}]   - [{"name": "Q-learning + lapse rate", "family": "Q-learning", "n_params": 4, "metric": "BIC/AIC"}]   - [{"name": "Modified Pearce-Hall + reset-at-reversal (WINNING)", "family": "Q-learning + Pearce-Hall", "n_params": 5, "metric": "BIC/AIC"}]   - [{"name": "Q-learning + dual learning rate", "family": "Q-learning", "n_params": 4, "metric": "BIC/AIC"}]   - [{"name": "Win-Stay Lose-Switch", "family": "WSLS", "n_params": 2, "metric": "BIC/AIC"}]   - [{"name": "Pure Pearce-Hall", "family": "Pearce-Hall", "n_params": 3, "metric": "BIC/AIC"}] - Social task — Bayesian-Belief models (k=6, tested via concurrent Bayesian modelling):   - [{"name": "No-η Bayes-Belief", "family": "Bayesian belief updating", "n_params": 7, "metric": "BIC/AIC/CBM exceedance probability"}]   - [{"name": "1-η Bayes-Belief (WINNING)", "family": "Bayesian belief updating", "n_params": 9, "metric": "BIC/AIC/CBM exceedance probability"}]   - [{"name": "2-η Bayes-Belief", "family": "Bayesian belief updating", "n_params": 10, "metric": "BIC/AIC/CBM exceedance probability"}] - Social task — Associative models (k=7, details in S1 Text):   - [{"name": "Associative social models (multiple variants)", "family": "Rescorla-Wagner / associative", "n_params": "varies", "metric": "BIC/AIC"}]
- **model_mb_mf:** - Non-social: MF (model-free Q-learning) - Social: Bayesian
- **model_params:** - Non-social winning model:   - τ (decision temperature; inverse temperature in Softmax) — higher = noisier choices   - λ (learning rate) — single learning rate across task   - S (salience; Pearce-Hall weighting of absolute prediction error)   - φ (memory decay; decay of unchosen option values toward mean)   - ηpr (reset-at-reversal; degree Q-values reset toward mean at reversal point) - Social winning model:   - pHI₀ [S] (strength of prior over harmful intent)   - uHI₀ [S] (uncertainty of prior over harmful intent)   - pSI₀ [S] (strength of prior over self-interest)   - uSI₀ [S] (uncertainty of prior over self-interest)   - uπ [S] (uncertainty over partner's policy; how consistently partner actions map to true intentions)   - w₀ [S] (policy-map intercept)   - wHI [S] (sensitivity to update harmful intent attributions from partner behaviour)   - wSI [S] (sensitivity to update self-interest attributions from partner behaviour)   - ηdg [S] (reset-at-reversal; degree beliefs reset toward prior after contingency change)
- **social_param:** - pHI₀: Strength of prior belief about partner's harmful intent — higher values mean stronger initial expectations of harm - uπ: Uncertainty over partner's behavioural policy — captures how consistently partner's actions reflect their true intentions - wSI: Sensitivity to explain behavioural changes through self-interest attributions — higher values mean more likely to attribute partner behaviour change to self-interest rather than harmful intent - wHI: Sensitivity to update harmful intent attributions following partner's behavioural changes
- **social_param_name:** pHI₀
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC, AIC (non-social task: MAP estimation with model comparison); Concurrent Bayesian Modelling (CBM; Piray et al., 2019) with exceedance probabilities and protected exceedance probabilities (social task). AICc with multi-model averaging for regression analyses.
- **how_model_fit:** individual-level-fit (MAP estimation with weak regularising priors; simulated annealing followed by gradient descent for non-social; CBM hierarchical Bayesian for social)
- **data_type_fit_to:** choice behavior (non-social task); self-report ratings (harmful intent and self-interest attribution ratings on 0–100 scales; social task)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study only)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=693 (66% female; ages 18–65; non-clinical online sample via Prolific Academic; 692 for non-social task, 689 for joint analysis)
- **population_category:** healthy adults
- **population_age_range:** 18–65
- **ecological_validity:** Online behavioural study using abstract probabilistic tasks; Dictator Game involves programmed partner rather than real social interaction; single reversal in non-social task limits assessment of volatility learning; non-clinical sample limits clinical generalisability. However, the use of two conceptually parallel tasks (social and non-social) with reversal structure provides reasonable ecological validity for measuring contingency learning processes.
- **eligibility_flag:** 
- **concerns:** The non-social and social tasks require different computational models, limiting direct parameter-by-parameter comparison across domains. The social task partner was programmed (not a real human making real-time decisions), though participants were told decisions were from real partners and were matched with real dictators post-task. Single reversal in non-social task may limit the buildup of volatility expectations. Non-clinical population; unclear whether results generalise to clinical paranoia.
- **limitations_reported:** While the similarity of constructs across different, ecologically valid tasks is a strength of our study, it also means we cannot directly compare behaviour in one task to another as they require different models/task content"; "we use a non-clinical population, and it is unclear whether the parameter estimates derived from our models in those with higher pre-existing paranoia would exist in clinical populations"; "we did not use varying volatility in our non-social task, keeping the same probabilistic environment with a single reversal. It may be that our single reversal meant participants had less time to build up expectations of contingency changes, despite not being told when the reversal might occur
- **limitations_categorized:** limited ecological validity; limited generalizability (non-clinical sample); task simplicity (single reversal, no varying volatility); cross-task comparability limited by different model structures
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - all_models_tested: MEDIUM — exact parameter counts for some social associative model variants not fully enumerated in main text (details in S1 Text supplement which was not separately accessible as a standalone file) - model_params fitted values: MEDIUM — mean fitted parameter values not reported as a table for individual parameters; only regression estimates of associations with paranoia are provided. Some simulation parameter values reported in S11 Fig caption (e.g., for low paranoia: w₀ = -0.935, wHI = 0.102, wSI = 0.129; for high paranoia: w₀ = -1.174, wHI = 0.121, wSI = 0.158)
- **cannot_find:** - Mean fitted parameter values for all model parameters (only regression coefficients against paranoia reported, not group-level means/SDs for each parameter) - Exact number of parameters and model specifications for all 7 associative social models (described as being in S1 Text supplement)
- **other_notes:** This paper uses two separate tasks (non-social probabilistic reversal learning + social modified repeated reversal Dictator Game) analysed with separate model families (Q-learning variants vs. Bayesian belief models), then bridges them through cross-task parameter correlations. The extended Bayesian belief model is a notable contribution as it captures asymmetric attribution updating (harmful intent vs. self-interest) — a feature with clear clinical relevance to paranoia phenomenology. The study replicates and extends Barnby et al. (2020). No supplement was separately available as a .txt or .pdf file with "_Supplements" suffix; supplementary figures and tables are embedded within the main paper text.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_paranoia
- rr_pop_healthy_adults
- rr_pop_paranoia
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_bayesian
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_temperature
- tax_rr_primary_topic = reputation_learning
- tax_rr_secondary_topic = volatility
- tax_rr_topic_reputation_learning
- tax_rr_topic_volatility
- tax_social_nonsocial_comparison
- tax_topic_reputation_learning
- tax_topic_volatility
