# Velez & Gweon (2019)

- **study_id:** `a29f8f737795fdfad_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Velez, N., & Gweon, H. (2019). Integrating incomplete information with imperfect advice. *Topics in Cognitive Science*, *11*(2), 299-315. https://doi.org/10.1111/tops.12388
- **citation_short:** Velez & Gweon (2019)
- **doi:** 10.1111/tops.12388
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Psychology
- **affiliations_raw:** etheychoseto“stay”withacardofknownvalueor“switch”toanunknowncard,givenanadvi-; school-aged children appropriately penalized the informant when she; University, 450 Serra Mall, Jordan Hall, Stanford, CA 94305; ethebestofevennoisy,impoverishedsocialinformation; mited as our own, and the information they pro-; Department ofPsychology, StanfordUniversity; mited,weoftenturntoothersforinformation; ethertomakeutility-maximizingdecisions; emails: nvelez@stanford.edu
- **code_url:** 

## Computational level
- **study_focus:** Learning from advice; mentalizing learning; reasoning about others' inferences/goals/beliefs
- **study_focus_short:** Learning from advice · mentalizing learning
- **learning_mode_description:** - Learning mode: Learning from an advisor's imperfect advice (based on partial information) about the value of a hidden card, to make utility-maximizing stay/switch decisions.   - Learning from:     - Source type (social): other (advisor)     - Source content (social): action/policy (advice to stay or switch)   - Learning about:     - Target type (non-social): world (hidden card value)     - Target content (non-social): state (world state; value of hidden card)
- **task_description:** Participants played a card game where they saw one card's value and received advice from an advisor (who saw some subset of the cards) to "stay" or "switch." Participants chose to keep their visible card or switch to the hidden card, aiming to maximize total points earned across trials.
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant), dyadic (simulated advisor)
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract cards with integer values (+1 to +8), binary advice ("stay"/"switch")
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Experiment 1: Participants used advice strategically based on advisor's information access; earned more points with imperfect (Hidden) advice than random (None) advice (Hidden M = 312.16 vs. None M = 304.54; W = 637.5, p < .001) - Experiment 1: Both models fit equally well (Mental-state Reasoning: R^2 = .96; Accuracy Heuristic: R^2 = .96) - Experiment 2: Mental-state Reasoning model captured more variance (R^2 = .92) than Accuracy Heuristic (R^2 = .83; t = 3.95, p < .001) - Experiment 3: Mental-state Reasoning model (R^2 = .93) outperformed Accuracy Heuristic (R^2 = .85; t = 2.22, p < .035); participants differentiated advisors matched on accuracy but differing in strategy
- **effect_size:** - Exp 1: Mental-state Reasoning R^2 = .96; Accuracy Heuristic R^2 = .96 - Exp 2: Mental-state Reasoning R^2 = .92; Accuracy Heuristic R^2 = .83 - Exp 3: Mental-state Reasoning R^2 = .93; Accuracy Heuristic R^2 = .85
- **learning_from:** other (advisor); advisor's advice (stay/switch) based on partial card information
- **learning_about:** world; value of the hidden card to maximize payoff  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Bayesian Mental-state Reasoning model (joint inference over advisor's choice function parameters m_A, b_A and hidden card value C_H; softmax choice rule with free parameter m_L)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "Mental-state Reasoning", "family": "Bayesian belief updating", "n_params": 3, "metric": "posterior predictive correlation (R^2)"},   {"name": "Accuracy Heuristic", "family": "Heuristic/softmax", "n_params": 2, "metric": "posterior predictive correlation (R^2)"} ]
- **model_mb_mf:** Bayesian
- **model_params:** - m_A [S]: steepness of advisor's inferred choice function (advisor's sensitivity to hidden card value). Hierarchical prior: m_A ~ N(mu_m, sigma_m). No mean fitted value reported for individual participants. - b_A [S]: horizontal shift of advisor's inferred choice function (advisor's bias toward stay/switch). Hierarchical prior: b_A ~ N(mu_b, sigma_b). No mean fitted value reported. - m_L: softmax temperature for learner's choice. Hierarchical prior: m_L ~ Gamma(k, theta). No mean fitted value reported.  For Accuracy Heuristic (alternative model): - acc: estimated advisor accuracy, acc ~ Beta(a_acc, b_acc) - m_L: softmax temperature, m_L ~ Gamma(k, theta)
- **social_param:** m_A (steepness of advisor's inferred choice function -- captures how the advisor's advice depends on the hidden card value); b_A (bias in advisor's choice function -- captures advisor's strategy/tendency toward stay or switch)
- **social_param_name:** m_A
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Posterior predictive correlation (R^2 between model posterior predictive and observed human behavior); comparison between model correlations using t-test on correlation coefficients
- **how_model_fit:** group-level-fit (hierarchical Bayesian model with MCMC via Metropolis-Hastings; 750,000 samples over 3 chains; posterior predictives generated from 10,000 posterior samples)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Experiment 1: N = 50 (online, Amazon Mechanical Turk); Experiment 2: N = 150 (Helpful N = 56, Opposite N = 50, Random N = 44); Experiment 3: N = 150 (Conservative N = 83, Risky N = 67). Total N = 350.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low ecological validity. Advisor was simulated (not a real person). Task was abstract card game with no real social interaction. Communication was unidirectional (advisor to participant only). Advisor strategies were static and pre-programmed. However, the decision structure (integrating partial information from an advisor) captures a core element of real-world advice-taking.
- **eligibility_flag:** Borderline -- learning over time is limited. The models assume static beliefs about the advisor (no trial-by-trial learning/updating of model parameters). The paper describes participants learning about the advisor early in the task (behavioral data), but the computational models themselves do not capture this learning process -- they fit static parameters across all trials. The "social agent" is a simulated automated system. Flag: borderline learning-vs-decision-making; automated social agent.
- **concerns:** (1) The computational models assume static beliefs -- they do not model trial-by-trial learning/updating, which limits how well this fits "learning over time" inclusion criteria. (2) The advisor is a simulated agent, not a real person. (3) Model comparison is based on posterior predictive correlation (R^2) rather than formal model comparison metrics (BIC, AIC, Bayes factors); the correlation difference is tested with a t-test on correlations. (4) No parameter recovery or model recovery reported. (5) Supplement referenced (Fig. S5, S8, etc.) but not accessible for verification.
- **limitations_reported:** We used a simulated agent with static strategies as the 'advisor' and did not consider learning"; "real human advisors may show richer, more complex behaviors"; "advisors might change their strategies over time or even tailor their advice based on the learner's behavior"; "one might wonder whether inferring the value of the hidden card 'qualifies' as mental-state reasoning"; "participants failed to capitalize on the Opposite advisor's advice"; "communication between the learner and the advisor was unidirectional"; "access to information was fixed throughout
- **limitations_categorized:** limited ecological validity; simulated social agent; no dynamic learning in model; unidirectional communication; task simplicity; limited generalizability
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - eligibility_flag: MEDIUM confidence -- the models are static (not learning over time), but participants demonstrably learn about the advisor early in the task; borderline case - model_params (fitted values): LOW confidence -- individual or group mean fitted parameter values not reported in main text; posterior distributions referenced in supplement (Fig. S5) which is not accessible - wc_guidelines rule 3: MEDIUM confidence -- pilot experiment and posterior predictives exist but no explicit simulate-before-fitting protocol described
- **cannot_find:** - Mean fitted parameter values for m_A, b_A, m_L (referenced as in supplement Fig. S5, not in main text) - Supplement content (Supporting Information referenced but not available as a separate file) - Exact formulas in standard notation (OCR artifacts in equations)
- **other_notes:** - The paper contains 3 experiments but they share the same models and task structure, varying only conditions. They are best treated as a single study with 3 experiments rather than 3 separate studies, as the models are the same throughout and no separate model fitting occurs per experiment beyond condition-specific parameters. - Data and code available at OSF (http://osf.io/w37up). - The supplement is referenced extensively (Figs. S2, S3, S5, S6, S8; Supporting Information for regression analyses) but no supplement file was found in the papers folder. Supplement not accessible. - Published in 2018 (received/accepted dates) but volume is 2019.
- **re_extract_flag:** false (full text was accessible; however, supplement was not accessible -- relevant fields flagged)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_instructed
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_instructed
- tax_mod_mentalizing_inference
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = advice_taking
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_advice_taking
- tax_rr_topic_mentalizing
- tax_topic_advice_taking
- tax_topic_mentalizing
