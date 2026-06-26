# Oktar et al. (2024)

- **study_id:** `a0cdadbb47a85fb46_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Oktar, K., Sumers, T., & Griffiths, T. L. (2024). A rational model of vigilance in motivated communication. In L. K. Samuelson, S. L. Frank, M. Toneva, A. Mackey, & E. Hazeltine (Eds.), *Proceedings of the 46th Annual Conference of the Cognitive Science Society*.
- **citation_short:** Oktar et al. (2024)
- **doi:** Not reported in the paper. Permalink: https://escholarship.org/uc/item/3kv0c8b7
- **publication_type:** conference proceedings (peer-reviewed)---
- **year:** 2024.0
- **field_of_study:** Cognitive science
- **affiliations_raw:** etheprimaryevidenceinatrial, 75%ofdefendantsare ference are present both in adults and children (Aboody,; lable under the terms of a Creative Commons Attribution License,; DepartmentofPsychologyandComputerScience,PrincetonUniversity; DepartmentofComputerScience,PrincetonUniversity; DepartmentofPsychology,PrincetonUniversity; ethandefendants? Andwhydoproductre-; ethanadvertisements, accordingtoa; lable at https://creativecommons; emails: sumers@princeton.edu, oktar@princeton.edu, tomg@princeton.edu
- **code_url:** 

## Computational level
- **study_focus:** Epistemic vigilance of motivation in social learning from testimony — how listeners adjust trust in a speaker's testimony based on the speaker's instrumental self-interest (referral bonus) and perceived altruism (relationship closeness).
- **study_focus_short:** Epistemic vigilance of motivation in social learning from testimony
- **learning_mode_description:** - Learning mode: Learning from a social informant's testimony about the quality of a product, adjusting belief based on the informant's inferred motivations.   - Learning from:     - Source type (social): other (informant — stranger, neighbor, close friend, romantic partner)     - Source content (social): action/policy (verbal testimony/recommendation about credit card quality)   - Learning about:     - Target type (non-social): world (quality of credit card)     - Target content (non-social): state (world state — true value of the recommended action for the listener)
- **task_description:** Participants read vignettes where a social informant (stranger, neighbor, close friend, or romantic partner) recommends a credit card. Participants rated the card's quality after learning the informant would receive varying referral bonuses ($0, $10, $100, $1000) for their sign-up.
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant), multi-target (4 informant types: stranger, neighbor, close friend, romantic partner)
- **n_players:** multi-target (3+)
- **partner_type:** human (live)
- **stimuli:** Text vignettes, 7-point Likert scale ratings, slider ratings (0-100) for altruism, reward utility, and competence
- **method:** online / behavioural
- **method_full:** Behavioural (online)
- **main_result:** - Altruism moderates trust: participants drew stronger inferences from testimony of more altruistic characters (beta = 3.07, 95% CI [2.81, 3.34], t(74.00) = 22.52) - Incentives moderate trust: increased speaker incentives (referral bonuses) led to lower trust (beta = -0.23, 95% CI [-0.35, -0.11], t(74.00) = -3.70) - Interaction between altruism and incentives: higher prior altruism beliefs protected trust from the negative effect of incentives (beta = 0.05, 95% CI [0.01, 0.09], t(74.00) = 2.34) - Manipulation checks: perceived altruism increased with relationship closeness (beta = 21.27, 95% CI [19.11, 23.42], t(74.01) = 19.37); perceived bonus utility increased with dollar amount (beta = 29.07, 95% CI [26.62, 31.51], t(74.00) = 23.30)
- **effect_size:** 
- **learning_from:** Other (social informant — stranger/neighbor/friend/partner); verbal testimony about a credit card recommendation
- **learning_about:** World; true quality/value of recommended credit card for the listener---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Bayesian vigilant listener model (RSA extension): P(R_L | u) proportional to P(u | R_S, R_L, lambda, A) * P(R_S) * P(R_L) * P(lambda); with parameters beta_S = beta_L = 10, uniform priors over reward functions, lambda (speaker altruism) in [0,1].
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** Only one computational model is presented (the Bayesian vigilant listener model). No formal model comparison is conducted. Statistical analyses use linear mixed-effects regressions to test qualitative predictions of the model, not to compare competing computational models.
- **model_mb_mf:** Bayesian
- **model_params:** - lambda [S]: speaker altruism parameter, in [0,1]; lambda=0 purely self-interested, lambda=1 purely altruistic - beta_S: speaker softmax optimality (set to 10) - beta_L: listener softmax optimality (set to 10) - R_S(a): speaker's instrumental reward function [S] - R_L(a): listener's instrumental reward function - Uniform priors over possible reward functions
- **social_param:** lambda (speaker altruism) — interpolates between purely self-interested (lambda=0) and purely altruistic (lambda=1) speaker; R_S (speaker's instrumental reward) — reflects the speaker's personal stakes in the listener's action.
- **social_param_name:** lambda
- **social_param_value:** 0
- **social_param_sd:** 
- **social_param_range:** 0–1
- **model_comparison_metric:** N/A — no formal model comparison conducted. Model predictions tested qualitatively against behavioral data using linear mixed-effects regressions (lme4 in R).
- **how_model_fit:** Simulate-and-compare (qualitative comparison of model simulations to participant behavior patterns; model was NOT formally fit to participant data — the authors explicitly note this as a limitation: "the computational model needs to be fit to participant data to enable quantitative comparisons between model predictions and human inferences")
- **data_type_fit_to:** Choice behavior (Likert-scale card quality ratings) — qualitative comparison only---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging)---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 77 (48 male, 29 female, 0 other; mean age = 37.4); recruited on Prolific; within-subjects design (4 characters x 4 bonus levels = 16 conditions per participant)
- **population_category:** healthy adults
- **population_age_range:** M=37.4
- **ecological_validity:** LOW — hypothetical vignette-based design with text-only credit card recommendation scenarios. No real financial stakes, no real social interaction. However, vignettes are grounded in everyday consumer contexts (credit card recommendations with referral bonuses), which adds some ecological relevance. The authors acknowledge the need for generalization to other domains (e.g., politics).
- **eligibility_flag:** FLAG — This paper presents a computational model of social inference from testimony, but it is unclear whether "learning over time" occurs. The task involves one-shot belief updating in response to a single recommendation under varying conditions, not iterative learning over multiple trials. The model formalizes rational inference rather than a learning process that unfolds over time. Borderline: social inference / one-shot Bayesian belief updating rather than learning over time. Additionally, the model is not formally fit to participant data — only qualitative predictions are tested.
- **concerns:** - Model is not formally fit to participant data (authors acknowledge this limitation explicitly) - No formal model comparison — only one computational model presented - Qualitative comparison only between model predictions and empirical data - No iterative/trial-by-trial learning — single-shot vignette-based judgments - Small sample size (N=77) for a within-subjects online study - No parameter recovery, model recovery, or posterior predictive checks - Conference proceedings paper (6 pages) — abbreviated methods and results - Softmax parameters (beta_S, beta_L = 10) and priors set a priori, not estimated from data
- **limitations_reported:** The computational model needs to be fit to participant data to enable quantitative comparisons between model predictions and human inferences"; "further experiments are necessary to investigate how well our model generalizes to other cases"; "people's judgment and decision-making is remarkably sensitive to the decision domain in question... our model might need additional contextual information to be able to predict inferences across contexts"
- **limitations_categorized:** No formal model fitting; limited generalizability; task simplicity; domain specificity
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** No
- **wc_rule3:** Yes
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Partial
- **wc_rule10:** No
- **wc_score:** 2.5
- **wc_total:** 2.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_instructed
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = target
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
- tax_rr_secondary_topic = strategic_reasoning
- tax_rr_topic_advice_taking
- tax_rr_topic_strategic_reasoning
- tax_topic_advice_taking
- tax_topic_strategic_reasoning
