# Frey (2019)

- **study_id:** `aec7a0ba248d26cad_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Frey, A.-L. (2019). Social learning in depression: Evidence from computational modelling, neuroimaging, and neurotransmitter depletion (Doctoral thesis, University of Reading). Study 1 (Chapter 2).
- **citation_short:** Frey (2019)
- **doi:** Not available for thesis; published version likely has a separate DOI.
- **publication_type:** thesis
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Centre for Integrative Neuroscience and Neurodynamics; School of Psychology and Clinical Language Sciences; mitters in the learning process by; mitter Involvement in Learning; mitter Functioning and Social; mitted for the degree of; ethora of research has; mitter
- **code_url:** 

## Computational level
- **study_focus:** Social reinforcement learning; linking social learning deficits to real-life social experiences in depression
- **study_focus_short:** Social reinforcement learning
- **learning_mode_description:** - Learning mode: Learning from social approval/disapproval feedback about optimal party decoration choices   - Learning from:     - Source type (social): other (two purported partners giving thumbs up/down feedback)       - Note: Feedback was computer-generated but believed to be from other people     - Source content (social): outcomes (approval/disapproval; thumbs up/neutral/down)   - Learning about:     - Target type (non-social): world (which party decoration items yield positive vs. negative feedback)     - Target content (non-social): action/policy (which items to choose to maximize positive outcomes)
- **task_description:** Participants chose between pairs of party decoration items and received social feedback (purportedly from two other people: thumbs up/neutral/down) or monetary feedback (win/no change/lose 5p). Each item was probabilistically associated with positive, neutral, or negative outcomes. Subjects also completed real-life social experience questionnaires.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), multi-target (2 purported partners providing feedback; feedback actually computer-generated)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Party decoration item images (balloons, garlands, lanterns, etc.), social feedback (thumbs up/neutral/down icons), monetary feedback (coin images), visual analogue rating scales
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - HD participants showed significantly lower social learning rates than LD controls (Q16: U = 1277, p = .040; Q4: U = 1314, p = .019) - No group differences in non-social learning rates (Q5: U = 1025, p = .968) - HD subjects reported more time in unpleasant social situations (U = 486, p < .001) - Lower social learning rates predicted more time in unpleasant social situations (Q16: beta = -0.45, p = .046; Q4: beta = -0.31, p = .020) - Higher outcome valuation (d) predicted more time in unpleasant social situations (Q16: beta = 0.31, p = .016) - Social anhedonia (RSAS) predicted less time in pleasant social situations (beta = -0.49, p < .001) - HD showed higher negative feedback expectancy biases (F(1,88) = 5.33, p = .023) - HD showed higher arousal to negative social feedback (F(1,85) = 4.84, p = .030)
- **effect_size:** - Social learning rate group difference: U = 1277, p = .040 (Q16); U = 1314, p = .019 (Q4) - Time in unpleasant social situations regression: R squared = 0.19 (Q16); R squared = 0.20 (Q4) - Time in pleasant social situations regression: R squared = 0.22 (Q16); R squared = 0.23 (Q4) - Social anhedonia predicting time with friends: R squared = 0.31, L(4) = 25.70, p < .001 - Model fit: pseudo-R squared = 0.34 (social), pseudo-R squared = 0.33 (non-social)
- **learning_from:** other (purported); social approval/disapproval feedback (thumbs up/down from two others)
- **learning_about:** world; which items yield positive vs. negative social feedback  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Q-learning with 1 learning rate (alpha), outcome valuation (d), memory decay (omega), temperature (tau) [social condition; Q16]. Non-social: Q-learning with 1 alpha, d, choice bias (phi), tau [Q5].  Social condition formula: Q_A(t+1) = Q_A(t) + alpha * max[0, r(t) - Q_A(t)] + alpha * min[0, r(t) - Q_A(t)] where r(t) = 1-d for rewards, -d for punishments, midpoint for neutral Softmax: P_A(t) = exp((Q_A(t) + c_A(t)*phi)/tau) / [exp((Q_A(t) + c_A(t)*phi)/tau) + exp((Q_B(t) + c_B(t)*phi)/tau)] Memory decay: Q_i(37) = Q_i(37) + omega * [0 - Q_i(37)]
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Q1", "family": "Q-learning", "n_params": 1, "metric": "AIC weight"}, {"name": "Q2", "family": "Q-learning", "n_params": 2, "metric": "AIC weight"}, {"name": "Q3", "family": "Q-learning", "n_params": 3, "metric": "AIC weight"}, {"name": "Q4", "family": "Q-learning", "n_params": 2, "metric": "AIC weight"}, {"name": "Q5", "family": "Q-learning", "n_params": 3, "metric": "AIC weight"}, {"name": "Q6", "family": "Q-learning", "n_params": 4, "metric": "AIC weight"}, {"name": "Q7", "family": "Q-learning (2 LR)", "n_params": 2, "metric": "AIC weight"}, {"name": "Q8", "family": "Q-learning (2 LR)", "n_params": 3, "metric": "AIC weight"}, {"name": "Q9", "family": "Q-learning (2 LR)", "n_params": 4, "metric": "AIC weight"}, {"name": "Q10", "family": "Q-learning (2 LR)", "n_params": 3, "metric": "AIC weight"}, {"name": "Q11", "family": "Q-learning (2 LR)", "n_params": 4, "metric": "AIC weight"}, {"name": "Q12", "family": "Q-learning (2 LR)", "n_params": 5, "metric": "AIC weight"}, {"name": "Q13", "family": "Q-learning", "n_params": 2, "metric": "AIC weight"}, {"name": "Q14", "family": "Q-learning", "n_params": 3, "metric": "AIC weight"}, {"name": "Q15", "family": "Q-learning", "n_params": 4, "metric": "AIC weight"}, {"name": "Q16", "family": "Q-learning", "n_params": 3, "metric": "AIC weight"}, {"name": "Q17", "family": "Q-learning", "n_params": 4, "metric": "AIC weight"}, {"name": "Q18", "family": "Q-learning", "n_params": 5, "metric": "AIC weight"}, {"name": "Q19", "family": "Q-learning (2 LR)", "n_params": 3, "metric": "AIC weight"}, {"name": "Q20", "family": "Q-learning (2 LR)", "n_params": 4, "metric": "AIC weight"}, {"name": "Q21", "family": "Q-learning (2 LR)", "n_params": 5, "metric": "AIC weight"}, {"name": "Q22", "family": "Q-learning (2 LR)", "n_params": 4, "metric": "AIC weight"}, {"name": "Q23", "family": "Q-learning (2 LR)", "n_params": 5, "metric": "AIC weight"}, {"name": "Q24", "family": "Q-learning (2 LR)", "n_params": 6, "metric": "AIC weight"}]
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate): single learning rate for positive and negative PEs [S - social condition only showed group difference]; mean fitted values not explicitly reported - d (outcome valuation): determines reward/punishment impact relative to initial expectation; values not explicitly reported - omega (memory decay): captures forgetting during rating breaks [social condition model] - tau (temperature): explore/exploit trade-off - phi (choice bias / sticky choice): tendency to repeat choices [non-social condition model]
- **social_param:** alpha (learning rate) [S] -- significantly lower in HD than LD in social but not non-social condition, indicating social-specific learning impairment
- **social_param_name:** alpha
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC weights (Akaike Information Criterion weights, computed as in Wagenmakers & Farrell, 2004)
- **how_model_fit:** individual-level-fit (two-step hierarchical MLE: step 1 = MLE without prior; step 2 = MLE with multivariate Gaussian prior derived from step 1 estimates)
- **data_type_fit_to:** choice behavior  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** 
- **analysis_type:** N/A  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 92 (52 LD, 40 HD); ages 18-45; 72 females, 20 males; mixed online (N=42) and in-lab (N=50)
- **population_category:** clinical
- **population_age_range:** 18–45
- **ecological_validity:** Task used purported social feedback from real people (though computer-generated) alongside a cover story involving party planning with two other individuals; real-life social experience measures collected. However, feedback credibility was moderate (mean certainty ~5/10). Online and in-lab mixed testing.
- **eligibility_flag:** 
- **concerns:** - Moderate believability of social manipulation (certainty ~5/10) - Low-magnitude monetary outcomes in non-social condition may have prevented detection of group differences - Retrospective self-report of social experiences subject to memory bias - Subclinical HD sample (BDI-based, not clinically diagnosed) - Comorbid anxiety not fully controlled - Small sample size for computational modeling
- **limitations_reported:** Small sample size; HD defined by BDI scores not clinical diagnosis; potential memory biases in social experience reports; low magnitude monetary outcomes in non-social condition prevent specificity claims; comorbid anxiety symptoms could contribute to effects; probabilistic social feedback may have seemed unrealistic; online vs. in-lab testing variability
- **limitations_categorized:** sample size; limited ecological validity; subclinical sample; potential response bias; task simplicity; limited generalizability; confound (comorbid anxiety)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 8.5
- **wc_total:** 8.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - Study 1: doi (LOW -- thesis doi not provided; published version doi not given in thesis text) - Study 1: model_params mean fitted values (MEDIUM -- individual parameter distributions shown in figures but exact mean values not reported in text) - Studies 2 & 3: model comparison (LOW -- only one model structure tested; no alternative models) - Study 3: eligibility_flag (MEDIUM -- healthy volunteers only; social learning from automated face stimuli) - All studies: preregistered (MEDIUM -- not mentioned, assumed No)
- **cannot_find:** - Exact mean fitted parameter values for Studies 1-3 (distributions shown in figures but precise values for each group not tabulated) - DOIs for published versions of Studies 1 and 2 - Any preregistration information
- **other_notes:** - This is a PhD thesis containing 3 studies. Studies 1 and 2 appear to have been published as journal articles: Frey, Frank, & McCabe (2019) and Frey & McCabe (2019). FLAG as potential duplicates if these published versions are also in the paper set. - The thesis provides an exceptionally thorough literature review on social learning, reinforcement learning in depression, and neurotransmitter roles that is highly relevant to the review narrative. - Study 1 used a deceptive paradigm (participants believed feedback came from real people). Study 2 used Pavlovian learning (no choice/action). Study 3 was pharmacological in healthy volunteers. - The integration across three studies (behavioral, neural, pharmacological) provides a rare multi-level investigation of social learning. - The computational modeling is relatively basic in Studies 2 and 3 (single RW model, no model comparison), which is a notable limitation compared to Study 1's comprehensive 24-model comparison. - Key finding across studies: social reward prediction encoding was reversed (tracking neutral faces rather than happy faces) in both HD individuals and 5-HT depleted healthy volunteers, suggesting a serotonergic mechanism for social learning deficits in depression.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_depression
- pop_healthy_adults
- rr_pop_depression
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = general
- spec_locus = source
- spec_source = social
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_decay
- tax_param_learning_rate
- tax_param_social_weight
- tax_param_temperature
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_topic_social_approval_reward
