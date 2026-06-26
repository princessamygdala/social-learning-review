# Leong & Zaki (2017)

- **study_id:** `ac114abb9dde87831_s3`
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
- **study_focus:** Social transmission of optimism bias; crowd-sourced ratings propagating biased expectations about advisor expertise (confidence: HIGH)
- **study_focus_short:** Social transmission of optimism bias
- **learning_mode_description:** - Learning mode: Learning from an advisor's prediction accuracy outcomes about the advisor's expertise, with crowd-sourced star ratings as initial expectations   - Learning from:     - Source type (social): other (financial advisor) + group (crowd-sourced ratings from Generation 1)     - Source content (social): outcomes (prediction accuracy) + state (aggregated peer ratings)   - Learning about:     - Target type (social): other (financial advisor)     - Target content (social): state (mental state; expertise/competence)
- **task_description:** Generation 1 participants performed the standard FAC task (3 advisors: 75%, 50%, 25%) and rated each advisor 1–5 stars. These averaged ratings were provided to Generation 2 participants before they performed the same task, to test whether crowd-sourced ratings propagate or correct optimism bias. (confidence: HIGH)
- **task_paradigm:** Advice-taking task
- **players:** Multi-agent (two generations of participants), multi-target (3 advisors: 75%, 50%, 25%) (confidence: HIGH)
- **n_players:** multi-target (3+)
- **partner_type:** human (live)
- **stimuli:** Photographs of White male faces (from 18-photo set), star ratings (1–5, crowd-sourced from Generation 1), fictitious stock price fluctuations, binary feedback (confidence: HIGH)
- **method:** online / behavioural
- **method_full:** behavioural / online (Amazon Mechanical Turk) (confidence: HIGH)
- **main_result:** - Generation 1 replicates Experiment 1: 50% advisor bet for >50% (M = 58%, 95% HDI [54%, 64%]); optimism bias confirmed - Generation 1 ratings: 75% advisor = 3.95 stars; 50% advisor = 2.97 stars; 25% advisor = 1.98 stars - Generation 2: 50% advisor still bet for >50% (M = 65%, 95% HDI [60%, 70%]); crowd-sourced ratings propagated (did not correct) optimism - Generation 2 initial expectations (CB model): 75% advisor αhat_1 = 0.78; 50% advisor αhat_1 = 0.63; 25% advisor αhat_1 = 0.35 - Generation 2 followed 50% advisor >50% in Joint Prediction (M = 65%, 95% HDI [60%, 70%]) with positive β = 0.70, 95% CI [0.60, 0.80] - Optimism asymmetry: 75% advisor initial expectations more extreme than 25% advisor (M_Diff = 0.10, 95% HDI [0.07, 0.13])
- **effect_size:** - Generation 1: CB model provided better fit (see supplement Table S3; not reported in main text for Gen 1) - Generation 2 Joint Prediction: 50% advisor β = 0.70, 95% CI [0.60, 0.80]; 75% vs 25% asymmetry β = −2.1, 95% CI [−2.46, −1.72]
- **learning_from:** Other (financial advisor) + group (crowd-sourced peer ratings); advisor's prediction accuracy outcomes (confidence: HIGH)
- **learning_about:** Other (financial advisor); advisor's expertise/competence (confidence: HIGH)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Confirmation Bias model (same architecture as Experiments 1–2) (confidence: HIGH)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "Bayesian Learning model", "family": "Bayesian belief updating", "n_params": 3, "metric": "AICc"} - {"name": "Confirmation Bias model", "family": "Bayesian belief updating (biased)", "n_params": 3, "metric": "AICc"}
- **model_mb_mf:** Bayesian (confidence: HIGH)
- **model_params:** (Generation 2, Confirmation Bias model, from main text) - 75% advisor αhat_1 = 0.78 (95% HDI [0.76, 0.79]) [S] - 50% advisor αhat_1 = 0.63 (95% HDI [0.60, 0.66]) [S] - 25% advisor αhat_1 = 0.35 (95% HDI [0.32, 0.38]) [S] - Full parameter values (α, β, κ) reported in supplement Table S4 (not accessible)
- **social_param:** Same confirmation bias mechanism b_t = |αhat_t − 0.5| [S]; additionally, crowd-sourced star ratings serve as a social prior that biases initial expectations [S] (confidence: HIGH)
- **social_param_name:** 75% advisor αhat_1 = 0.78
- **social_param_value:** 0.78
- **social_param_sd:** 
- **social_param_range:** 0.76–0.79
- **model_comparison_metric:** AICc; corrected average likelihood per trial (detailed results in supplement Tables S3, S4) (confidence: MEDIUM)
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
- **sample_size:** Generation 1: N = 86 (14 excluded; 58 male, 41 female, 1 did not indicate; ages 19–61, mean = 32.56; AMT). Generation 2: N = 92 (8 excluded; 52 male, 46 female, 2 did not indicate; ages 19–69, mean = 33.26; AMT) (confidence: HIGH)
- **population_category:** healthy adults
- **population_age_range:** 19–61
- **ecological_validity:** Online sample (AMT) increases generalizability; crowd-sourced rating manipulation more ecologically valid (mimics real-world rating systems like Yelp); but task still simplified with binary outcomes; shorter version of task (20 trials per advisor) (confidence: HIGH)
- **eligibility_flag:** 
- **concerns:** Shorter task (20 trials per advisor vs 36 in Exp 1) may limit learning; AMT sample quality concerns (despite >95% HIT approval filter); full model comparison results for Generation 1 only in supplement (not accessible); stimulus set limited to White male faces
- **limitations_reported:** Simplified and controlled setting with binary recommendations and immediate feedback; crowd-sourced ratings propagated rather than corrected optimism bias (confidence: HIGH)
- **limitations_categorized:** task simplicity; limited ecological validity; limited stimulus diversity; shorter task duration
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
- rr_tax_mod_cultural_network
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_mod_cultural_network
- tax_mod_instructed
- tax_model_bayesian
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_learning_rate
- tax_rr_primary_topic = cultural_transmission
- tax_rr_secondary_topic = advice_taking
- tax_rr_topic_advice_taking
- tax_rr_topic_cultural_transmission
- tax_topic_advice_taking
- tax_topic_cultural_transmission
