# Leong & Zaki (2017)

- **study_id:** `ac114abb9dde87831_s2`
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
- **study_focus:** Learning from advice; manipulation of initial expectations on optimism bias; learning about advisor expertise (confidence: HIGH)
- **study_focus_short:** Learning from advice
- **learning_mode_description:** - Learning mode: Learning from an advisor's prediction accuracy outcomes about the advisor's expertise, with experimentally manipulated initial expectations via star ratings   - Learning from:     - Source type (social): other (financial advisor)     - Source content (social): outcomes (prediction accuracy)   - Learning about:     - Target type (social): other (financial advisor)     - Target content (social): state (mental state; expertise/competence)
- **task_description:** Participants were given star ratings (1–4 stars) for four advisors before observing them predict stock fluctuations. The 4-star (75% accurate) and 1-star (25%) advisors differed in accuracy, while the 3-star and 2-star advisors were both at chance (50%). Participants bet on advisors' predictions and later made stock predictions using advisor recommendations. (confidence: HIGH)
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant), multi-target (4 advisors: 4-star/75%, 3-star/50%, 2-star/50%, 1-star/25%) (confidence: HIGH)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Photographs of White male faces (IASLab Face Set), star ratings (1–4), fictitious stock price fluctuations, binary feedback (confidence: HIGH)
- **method:** behavioural
- **method_full:** behavioural (confidence: HIGH)
- **main_result:** - 3-star advisor bet for more than 2-star advisor (M_Diff = 34%, 95% HDI [18%, 51%]) despite identical 50% accuracy - 3-star advisor bets >50% (M = 76%, 95% HDI [69%, 84%]); 2-star advisor not different from chance (M = 42%, 95% HDI [31%, 52%]) - Confirmation Bias model better fit (27/30 participants; M_CB-BL = 0.044, 95% HDI [0.025, 0.063]; effect size = 0.93, 95% HDI [0.49, 1.39]) - Star ratings biased initial beliefs: 4-star αhat_1 = 0.72; 3-star αhat_1 = 0.69; 2-star αhat_1 = 0.45; 1-star αhat_1 = 0.43 - Joint Prediction: 3-star advisor followed 74% (95% HDI [67%, 80%]) vs 2-star 48% (95% HDI [38%, 58%]) - 3-star advisor β = 0.55, 95% CI [0.48, 0.63]; 2-star advisor β = −0.04 (ns) - Explicit ratings: 3-star rated 57.4% (95% HDI [53%, 62%]); 2-star rated 50.4% (95% HDI [45%, 55%])
- **effect_size:** - CB vs BL model: effect size = 0.93 (95% HDI [0.49, 1.39]) - Mixed effects logistic regression: stock trend β = 0.52, 95% CI [0.44, 0.62]; 4-star β = 1.04, 95% CI [0.93, 1.17]; 1-star β = −0.50, 95% CI [−0.58, −0.42]; 3-star β = 0.55, 95% CI [0.48, 0.63]
- **learning_from:** Other (financial advisor); advisor's prediction accuracy outcomes (confidence: HIGH)
- **learning_about:** Other (financial advisor); advisor's expertise/competence (confidence: HIGH)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Confirmation Bias model (Bayesian belief updating with confirmation bias; separate α, β per advisor + 1 κ) (confidence: HIGH)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "Bayesian Learning model", "family": "Bayesian belief updating", "n_params": 9, "metric": "AICc"} - {"name": "Confirmation Bias model", "family": "Bayesian belief updating (biased)", "n_params": 9, "metric": "AICc"}
- **model_mb_mf:** Bayesian (confidence: HIGH)
- **model_params:** - α_4star: 4.22 (SE = 0.15); β_4star: 1.69 (SE = 0.18); αhat_1 = 0.72 [S] - α_3star: 4.21 (SE = 0.19); β_3star: 1.83 (SE = 0.17); αhat_1 = 0.69 [S] - α_2star: 2.64 (SE = 0.29); β_2star: 3.32 (SE = 0.31); αhat_1 = 0.45 [S] - α_1star: 2.95 (SE = 0.33); β_1star: 3.64 (SE = 0.23); αhat_1 = 0.43 [S] - κ: 8.4 (SE = 0.74)
- **social_param:** Same as Experiment 1: b_t = |αhat_t − 0.5| confirmation bias weight [S]; additionally, separate α/β priors per advisor capture different initial expectations about each advisor's social expertise [S] (confidence: HIGH)
- **social_param_name:** Same as Experiment 1
- **social_param_value:** 4.22
- **social_param_sd:** SE=0.15
- **social_param_range:** 
- **model_comparison_metric:** AICc; corrected average likelihood per trial; Robust Bayesian estimation (confidence: HIGH)
- **how_model_fit:** individual-level-fit (MAP estimation) (confidence: HIGH)
- **data_type_fit_to:** choice behavior (binary bets) (confidence: HIGH)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** N = 30 (14 male, 16 female; ages 19–49, mean = 26.3) (confidence: HIGH)
- **population_category:** healthy adults
- **population_age_range:** 19–49
- **ecological_validity:** Star rating manipulation adds ecological validity (mimics Yelp-style ratings), but task remains simplified with binary outcomes and immediate feedback (confidence: HIGH)
- **eligibility_flag:** 
- **concerns:** Stimuli limited to White male faces; same simplified task structure as Exp 1
- **limitations_reported:** Same as general discussion limitations; simplified and controlled setting with binary recommendations and immediate explicit feedback (confidence: HIGH)
- **limitations_categorized:** task simplicity; limited ecological validity; limited stimulus diversity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Partial
- **wc_rule6:** Partial
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9.0
- **wc_total:** 9.0

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
- rr_tax_mod_instructed
- spec_context = partly
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_instructed
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
