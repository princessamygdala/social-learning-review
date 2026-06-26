# Leong & Zaki (2017)

- **study_id:** `ac114abb9dde87831_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Leong, Y. C., & Zaki, J. (2017). Unrealistic optimism in advice taking: A computational account. *Journal of Experimental Psychology: General*, 0(999), 000. http://dx.doi.org/10.1037/xge0000382
- **citation_short:** Leong & Zaki (2017)
- **doi:** 10.1037/xge0000382
- **publication_type:** peer-reviewed journal
- **year:** 2017.0
- **field_of_study:** Psychology
- **affiliations_raw:** DepartmentofPsychology,StanfordUniversity,450Serra been used in the related literature, including judge, client, advice-seeker; laboratory experiments, human participants Decision-makers often have to quickly judge an advisor’s ex-; etheseadvisorsmakeany attributabletooptimisticinitialexpectations,confirmationbiasor; ether the optimism bias “spreads”; University,Stanford,CA94305-2130; ethenexploredcrowdsourcedratings; DepartmentofPsychology,Stanford; lableonGitHub:https://github; emails: ycleong@stanford.edu
- **code_url:** https://github.com/ycleong/

## Computational level
- **study_focus:** Learning from advice; optimism bias in advice taking; learning about advisor expertise (confidence: HIGH)
- **study_focus_short:** Learning from advice
- **learning_mode_description:** - Learning mode: Learning from an advisor's prediction accuracy outcomes about the advisor's expertise   - Learning from:     - Source type (social): other (financial advisor)     - Source content (social): outcomes (prediction accuracy)   - Learning about:     - Target type (social): other (financial advisor)     - Target content (social): state (mental state; expertise/competence)
- **task_description:** Participants first predicted stock price fluctuations, then observed three financial advisors (75%, 50%, 25% accuracy) predicting a stock and bet on whether each advisor's predictions would be correct. Finally, participants predicted a third stock while receiving advisor recommendations. (confidence: HIGH)
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant), multi-target (3 advisors varying in accuracy: 75%, 50%, 25%) (confidence: HIGH)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Photographs of White male faces (IASLab Face Set), fictitious stock price fluctuations, binary feedback (correct/incorrect) (confidence: HIGH)
- **method:** behavioural
- **method_full:** behavioural (confidence: HIGH)
- **main_result:** - Participants bet for the 50% advisor >50% of trials (M = 67%, 95% HDI [60%, 78%]), indicating optimism bias - Participants bet for 75% advisor more than against 25% advisor (M_Diff = 6%, 95% HDI [0%, 12%]) - Confirmation Bias model fit better than Bayesian Learning model (M_CB-BL = 0.03, 95% HDI [0.01, 0.05]; effect size = 0.61, 95% HDI [0.16, 1.06]) - Both models estimated optimistic initial beliefs (CB model: M αhat_1 = 0.62, 95% HDI [0.55, 0.70]; Bayesian model: M = 0.59, 95% HDI [0.56, 0.65]) - Participants followed 50% advisor's advice more than chance in Joint Prediction (M = 68%, 95% HDI [0.59, 0.79]) - Explicit ratings of 75% advisor optimistic (M = 81%, 95% HDI [78%, 87%]); 50% advisor optimistic (M = 58%, 95% HDI [53%, 61%])
- **effect_size:** - Confirmation Bias vs Bayesian Learning model: effect size = 0.61 (95% HDI [0.16, 1.06]) - Joint Prediction: stock trend β = 0.37, 95% CI [0.29, 0.45]; 50% advisor β = 0.45, 95% CI [0.39, 0.51]; 75% advisor β = 1.42, 95% CI [1.32, 1.52]; 25% advisor β = −0.97, 95% CI [−1.05, −0.90] - Advisor × Advice interaction β = 0.84, 95% CI [0.63, 1.01]
- **learning_from:** Other (financial advisor); advisor's prediction accuracy outcomes (confidence: HIGH)
- **learning_about:** Other (financial advisor); advisor's expertise/competence (confidence: HIGH)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Confirmation Bias model (Bayesian belief updating with confirmation bias; 3 params: α, β, κ) (confidence: HIGH)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "Bayesian Learning model", "family": "Bayesian belief updating", "n_params": 3, "metric": "AICc / corrected average likelihood per trial"} - {"name": "Confirmation Bias model", "family": "Bayesian belief updating (biased)", "n_params": 3, "metric": "AICc / corrected average likelihood per trial"} - {"name": "Win-Stay-Lose-Shift (WSLS)", "family": "Heuristic", "n_params": "not specified", "metric": "AICc"} - {"name": "Temporal Difference (TD) RL", "family": "Reinforcement learning", "n_params": "not specified", "metric": "AICc"} - {"name": "Null model", "family": "Baseline", "n_params": 1, "metric": "AICc"}
- **model_mb_mf:** Bayesian (confidence: HIGH)
- **model_params:** - α (alpha): shape parameter of Beta prior distribution, defines initial beliefs about advisor expertise; best-fit mean = 3.23 (SE = 0.51) - β (beta): shape parameter of Beta prior distribution; best-fit mean = 1.96 (SE = 0.28) - κ (kappa): logistic function gain parameter, determines choice sensitivity; best-fit mean = 7.97 (SE = 0.84) - Derived: αhat_1 = α/(α+β) = estimated initial belief about advisor expertise [S]; M = 0.62 (95% HDI [0.55, 0.70]) - b_t = |αhat_t − 0.5|: confirmation bias weight term, scales with current expectation [S]
- **social_param:** b_t = |αhat_t − 0.5|: confirmation bias term that scales with participant's current estimate of advisor expertise; modifies the likelihood function to underweight expectation-inconsistent information about the advisor [S] (confidence: HIGH)
- **social_param_name:** b_t = |αhat_t − 0.5|
- **social_param_value:** 0.62
- **social_param_sd:** 
- **social_param_range:** 0.55–0.70
- **model_comparison_metric:** AICc (finite sample corrected AIC); corrected average likelihood per trial (derived from AICc); Robust Bayesian estimation comparing within-participant differences (confidence: HIGH)
- **how_model_fit:** individual-level-fit (MAP estimation with regularizing Gamma(2,3) priors) (confidence: HIGH)
- **data_type_fit_to:** choice behavior (binary bets for/against advisor predictions) (confidence: HIGH)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (confidence: HIGH)
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 26 (1 excluded for missing >10% trials; original N = 27; 18 male, 9 female; ages 19–43, mean = 24.2) (confidence: HIGH)
- **population_category:** healthy adults
- **population_age_range:** 19–43
- **ecological_validity:** Simplified lab task mimicking financial advice-taking with binary outcomes and immediate feedback; authors acknowledge real-world scenarios involve more complex feedback and advisors who embellish recommendations; stimuli limited to White male faces (confidence: HIGH)
- **eligibility_flag:** 
- **concerns:** Small sample size (N = 26); stimuli limited to White male advisor faces; WSLS and TD model parameters not reported in main text (supplement not accessible); task simplicity relative to real-world advice scenarios
- **limitations_reported:** Our task was set in a simplified and controlled setting — in which advisors made binary recommendations and decision-makers received immediate and explicit feedback about the advisor's performance"; authors acknowledge effects of expectations and confirmation bias would likely be stronger in more realistic decision-making scenarios with delayed/complex feedback; limited to financial domain (confidence: HIGH)
- **limitations_categorized:** task simplicity; limited ecological validity; limited generalizability (financial domain only); limited stimulus diversity (White male faces only)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Partial
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9.5
- **wc_total:** 9.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - WSLS and TD model n_params: not reported in main text (MEDIUM confidence; details may be in supplement) - Experiment 3 Generation 1 model comparison details: referenced as Table S3 in supplement (MEDIUM; supplement not accessible) - Experiment 3 Generation 2 full model parameters: referenced as Table S4 in supplement (MEDIUM; supplement not accessible) - Model recovery (WC Rule 6): described as parameter recovery in supplement (MEDIUM; cannot confirm confusion matrix exists)
- **cannot_find:** - Full parameter values for WSLS and TD comparison models (supplement) - Experiment 3 detailed model comparison statistics for Generation 1 (supplement Table S3) - Experiment 3 full α, β, κ parameter estimates (supplement Table S4) - Exact formulas for WSLS and TD models (supplement)
- **other_notes:** Supplement referenced at http://dx.doi.org/10.1037/xge0000382.supp but not available as a file in the papers folder. The paper explicitly states that full algebraic formulation of the Bayesian model, additional comparison models (WSLS, TD, Null), parameter recovery study, and trial-by-trial model comparisons are in supplemental materials. Data and code are publicly available on GitHub (https://github.com/ycleong/AdviceTaking). The paper was published in Journal of Experimental Psychology: General (2017). The Confirmation Bias model is a novel modification of standard Bayesian belief updating that incorporates expectation-consistent weighting of evidence.
- **re_extract_flag:** false (full text was available; however, supplement was not accessible, so some model details are missing)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_social_info_search
- spec_context = partly
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_social_info_search
- tax_model_bayesian
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_learning_rate
- tax_rr_primary_topic = advice_taking
- tax_rr_secondary_topic = reputation_learning
- tax_rr_topic_advice_taking
- tax_rr_topic_reputation_learning
- tax_topic_advice_taking
- tax_topic_reputation_learning
