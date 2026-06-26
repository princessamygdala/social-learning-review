# Hertz et al. (2021)

- **study_id:** `a4af8527b1cc684fd_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hertz, U., Bell, V., & Raihani, N. (2021). Trusting and learning from others: immediate and long-term effects of learning from observation and advice. *Proceedings of the Royal Society B: Biological Sciences*, *288*(1961), 20211414. https://doi.org/10.1098/rspb.2021.1414
- **citation_short:** Hertz et al. (2021)
- **doi:** 10.1098/rspb.2021.1414
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Psychology
- **affiliations_raw:** DepartmentofClinical,Education and HealthPsychology,University College London,London, UK; DepartmentofExperimentalPsychology,University College London,WC1H 0AP, London, UK; ethaninresponsetoobserved them to establish some expectations of the lakes; DepartmentofCognitiveSciences, UniversityofHaifa,Haifa, Israel; lable that they will be copied by others [13,20–23]; mittedinformation,howthisvarieswiththeneedtoevalu-; mits unrestricted use, provided the original; mitted information; emails: uhertz@cog.haifa.ac.il
- **code_url:** https://osf.io/kxwtn/

## Computational level
- **study_focus:** Social learning from advice vs. observation; trust and paranoia effects on social information use
- **study_focus_short:** Social learning from advice vs. observation
- **learning_mode_description:** - Learning mode: Learning from an expert's social information (advice or observed choice) about which option yields higher reward   - Learning from:     - Source type (social): other (expert player)       - In advice condition: expert intentionally broadcasts recommendation       - In observation condition: participant secretly observes expert's choice     - Source content (social): action/policy (expert's choice or recommendation of which lake to fish)   - Learning about:     - Target type (non-social): world (reward environment)     - Target content (non-social): stimulus (which lake/option has higher expected reward)
- **task_description:** In a two-armed bandit fishing task, participants chose between two lakes over 15 trials per block, receiving stochastic reward feedback. After the first 4 trials, social information (advice from or observed choice of an expert) was presented once, always indicating the higher-paying option; a control block provided no social information.
- **task_paradigm:** Two-armed bandit
- **players:** Single agent (participant), single demonstrator (expert player, not a real participant; computer-generated social information)
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Two abstract lakes (named "Bagel" and "Pacman"), numeric fish reward feedback, text-based social information framing (advice vs. observation)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Participants more likely to immediately follow advice than to copy observed choice (chi-squared = 45.9, p < 0.001)   - Paranoia negatively associated with advice-following but not observation-copying (chi-squared = 6.18, p = 0.045)   - Long-term performance higher in advice than observation or control (chi-squared = 28.5, p < 0.001)   - Advice led to faster convergence to good option than observation/control (chi-squared = 8.63, p = 0.013)   - Bimodal distribution of beta-boost: ~39% high beta-boost in advice condition, ~34% in observation condition   - High beta-boost participants responded faster (chi-squared = 10.39, p = 0.0012) and earned more reward (chi-squared = 224.89, p < 0.0001)   - Paranoia associated with lower beta-boost values overall (chi-squared = 5.46, p = 0.02)
- **effect_size:** No standardized effect sizes (Cohen's d, r, eta-squared, etc.) reported; only chi-squared and t-statistics with p-values. Flagged in concerns.
- **learning_from:** Other (expert player); expert's choice or recommendation indicating which lake to choose
- **learning_about:** World; which lake/option has higher expected reward (non-social stimulus value)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Q-learning with Qboost (immediate value boost, 2 params: Qboost_Advice, Qboost_Observation) and beta-boost (long-term precision boost, 2 params: beta-Boost_Advice, beta-Boost_Observation); total 6 free params: {beta, alpha, Qboost_Advice, Qboost_Observation, beta-Boost_Advice, beta-Boost_Observation}
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** Only one model was tested. No model comparison was performed. [{"name": "Q-learning with Qboost + betaBoost", "family": "Q-learning", "n_params": 6, "metric": "log-likelihood (individual fitting)"}]
- **model_mb_mf:** MF
- **model_params:** - beta: inverse temperature / precision parameter. Median = 8.57, Mean = 15.2 [range 0.1-50] - alpha: learning rate. Median = 0.49, Mean = 0.52 [range 0.05-0.95] - Qboost_Advice [S]: immediate value boost for advised option. Median = 1, Mean = 0.85 [range 0-1] - Qboost_Observation [S]: immediate value boost for observed option. Median = 1, Mean = 0.80 [range 0-1] - beta-Boost_Advice [S]: long-term precision parameter after advice. Median = 15.2, Mean = 25.0 [range 0.1-50] - beta-Boost_Observation [S]: long-term precision parameter after observation. Median = 14.1, Mean = 23.5 [range 0.1-50]
- **social_param:** Qboost_Advice/Observation: immediate one-trial value boost to the socially indicated option (sets Q-value to max when = 1). beta-Boost_Advice/Observation: post-social-information precision parameter governing long-term exploitation vs. exploration of socially indicated option.
- **social_param_name:** Qboost_Advice
- **social_param_value:** 0.85
- **social_param_sd:** 
- **social_param_range:** 0–1
- **model_comparison_metric:** N/A (only one model fitted; log-likelihood reported per individual)
- **how_model_fit:** individual-level-fit (L-BFGS-B constrained quasi-Newton optimization via R optim function, fitted independently per participant)
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
- **sample_size:** N = 1492 (after 6 excluded for incomplete data from original 1498; 592 F, 895 M, 11 non-binary/other; mean age 29.2, SD = 10.4); online participants via Prolific Academic
- **population_category:** healthy adults
- **population_age_range:** M=29.2
- **ecological_validity:** Online two-armed bandit task with abstract lake stimuli; social information provided once as text framing (not real interactive social exchange); social information always accurate, which is unrealistic; limited ecological validity as a controlled lab-style paradigm delivered online.
- **eligibility_flag:** 
- **concerns:** - Only one computational model tested; no model comparison performed. This severely limits inference about the winning model's superiority. - No standardized effect sizes reported (only chi-squared, t-values, and p-values). - Social information was always accurate (always indicated the better option), limiting generalizability to real-world settings where advice can be inaccurate. - The social agent was not a real person -- social information was computer-generated and framed as coming from an "expert player." - The supplement (.txt) contains only peer review history, not supplementary methods/data tables. The actual electronic supplementary material is referenced as hosted on figshare (https://dx.doi.org/10.6084/m9.figshare.c.5662343) and was not available for extraction.
- **limitations_reported:** Data came from UK-based participants recruited via Prolific Academic, limiting generalizability to other groups and contexts; the experimental design is an engineered situation that may not reflect complexity of real-world social learning; social information was always on-average informative, not reflecting the potential range of advice accuracy in broader social situations; did not ask participants whether they perceived advice vs. observation as differentially reliable or felt obliged to follow social information; some tendency to follow advice could be explained by normative expectation rather than trust.
- **limitations_categorized:** limited generalizability; limited ecological validity; task simplicity (always-accurate social information); no manipulation check; demand characteristics (normative expectation confound)
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size: LOW -- no standardized effect sizes reported; only chi-squared and t-statistics with p-values - model_comparison_metric: LOW -- N/A because only one model was tested - wc_guidelines Rule 8: MEDIUM -- simulations demonstrate qualitative fit but no formal posterior predictive check - social agent authenticity: MEDIUM -- social information was computer-generated, not from a real expert player; this is stated in the methods but could affect interpretation
- **cannot_find:** - Standardized effect sizes (Cohen's d, r, eta-squared, beta weights) -- not reported in main text - Electronic supplementary material tables (S1-S10 referenced in text) -- actual supplement hosted on figshare not accessible in the provided files; the _Supplements.txt file contains only peer review history - Model comparison with alternative models -- not performed - Parameter recovery analysis -- not performed - Exact model formula beyond what is in the main text (equations 3.1 and 3.2) -- no supplement accessible
- **other_notes:** The paper is pre-registered with 5 main hypotheses. The computational modeling was described as an "exploratory analysis" in the pre-registration. The bimodal distribution of beta-boost parameters (exploiters vs. explorers) is a key finding, with ~39% classified as high beta-boost in the advice condition and ~34% in the observation condition. The supplement file available in the papers folder is the peer review history, not the actual electronic supplementary material (which is on figshare). The Q-learning model update rule is: Q_LakeA(t+1) = Q_LakeA(t) + alpha * (Fish(t) - Q_LakeA(t)), with softmax choice rule using precision parameter beta. Social parameters Qboost set the value of the indicated lake to maximum after social information; beta-Boost sets precision for subsequent trials after social information.
- **re_extract_flag:** false (full text was read; however, the electronic supplementary material tables S1-S10 on figshare were not accessible -- flagged but the main text extraction is complete)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_paranoia
- rr_pop_healthy_adults
- rr_pop_paranoia
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- tax_domain_A_influence_transmission
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_precision
- tax_param_social_bonus
- tax_param_temperature
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_social_bonus
- tax_rr_param_temperature
- tax_rr_primary_topic = advice_taking
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_advice_taking
- tax_rr_topic_social_info_use
- tax_social_nonsocial_comparison
- tax_topic_advice_taking
- tax_topic_social_info_use
