# Tarantola et al. (2017)

- **study_id:** `a8f9db013045d1900_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Tarantola, T., Kumaran, D., Dayan, P., & De Martino, B. (2017). Prior preferences beneficially influence social and non-social learning. *Nature Communications*, *8*, 817. https://doi.org/10.1038/s41467-017-00826-8
- **citation_short:** Tarantola et al. (2017)
- **doi:** 10.1038/s41467-017-00826-8
- **publication_type:** peer-reviewed journal
- **year:** 2017.0
- **field_of_study:** Psychology
- **affiliations_raw:** ether they merely act as priors in a learning process, or that the influences we observed in our experimental data—on; ether these influences are exclusively social or performance on average, suggesting that they may actually be; DepartmentofPsychology,UniversityofCambridge,DowningStreet,CambridgeCB23EB,UK; ethatotherpeople modelsfedvalueslearnedoverseveraltrialsintoadriftdiffusion; ether average performance of artificial actors who were influenced by; ethertheypersistently biastheintra-trialchoice process; InstituteofCognitiveNeuroscience,UniversityCollege; ethecorrectanswerwith80%probability
- **code_url:** 

## Computational level
- **study_focus:** Learning others' food preferences (social projection / egocentric bias in preference learning)
- **study_focus_short:** Learning others' food preferences
- **learning_mode_description:** - Learning mode: Learning another person's food preferences from probabilistic feedback, biased by one's own prior preferences   - Learning from:     - Source type (non-social): world       - Probabilistic feedback (yellow box indicating correct answer with 80% probability)     - Source content (non-social): outcome       - Binary feedback on correctness of prediction   - Learning about:     - Target type (social): other (randomly assigned partner)     - Target content (social): action/policy (food preference choices)
- **task_description:** Participants first expressed their own food preferences via bidding and forced-choice tasks, then learned which of 20 snack pairs a partner had chosen by making predictions and receiving probabilistic feedback (80% accurate) over 30 trials per pair (600 trials total). A second group performed the identical task but was not told the items reflected another person's choices.
- **task_paradigm:** Impression formation task
- **players:** Single agent (participant), single target (one randomly assigned pilot participant whose choices were learned). Between-subjects: social group (n=31) and non-social group (n=30).
- **n_players:** network (5+)
- **partner_type:** unclear
- **stimuli:** Food snack images (40 items in 20 pairs), binary probabilistic feedback (yellow box around one item)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Preference congruence (Δv) significantly predicted accuracy across all trials in both social (coefficient=0.56, SE=0.04, z=13.9) and non-social (coefficient=0.44, SE=0.03, z=13.1) groups - Preference congruence significantly predicted faster RTs for preference-congruent responses in both groups (social: coefficient=-0.12, SE=0.01, t=-12.3; non-social: coefficient=-0.08, SE=0.01, t=-8.7) - Social group performed significantly better on first trials than non-social group (coefficient=0.38, SE=0.13, z=2.9) - Item popularity significantly improved first-trial performance more in the social than non-social group (group x popularity interaction: χ2(1)=5.7, p=0.017) - Dual influence model (priors + choice bias) best predicted behavior in both groups (social ELPD=-8,077.8; non-social ELPD=-11,141.8), significantly outperforming the second-best influenced choice model (ELPD difference=82.1/117.2, SE=19.4/20.4) - Adding item popularity further improved the model for the social group (ELPD difference=59.6, SE=15.4) but not non-social (ELPD difference=17.5, SE=10.8) - Simulations showed dual influence strategy outperformed neutral learner by mean 0.71 percentage points; was near-optimal for p(random) between 0.05 and 0.37
- **effect_size:** - Effect of Δv on performance (social, all trials): coefficient=0.56, SE=0.04, z=13.9 - Effect of Δv on performance (non-social, all trials): coefficient=0.44, SE=0.03, z=13.1 - Effect of Δv on RT (social): coefficient=-0.12, SE=0.01, t=-12.3, χ2(1)=151.0 - Effect of Δv on RT (non-social): coefficient=-0.08, SE=0.01, t=-8.7, χ2(1)=74.6 - Social group first-trial advantage: coefficient=0.38, SE=0.13, z=2.9 - Correlation between own preference and others' preference: Pearson's r=0.48 - Dual influence vs influenced choice ELPD difference: 82.1 (SE=19.4) social; 117.2 (SE=20.4) non-social
- **learning_from:** World; probabilistic binary feedback on correctness of prediction (80% accurate yellow box)
- **learning_about:** Other (partner); food preference choices  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Bayesian dual influence model with item popularity: Bayesian belief updating with preference-influenced prior (softmax of Δv and item popularity ρ) feeding into DDM with preference-influenced starting point bias. P(A)_{n=1} = 1/(1+e^{-(β_Δv·Δv + β_ρ·ρ)}); drift d_n = ω·(P(A|data_n) - P(B|data_n)); starting point z = 1/(1+e^{-κ·Δv})
- **model_family:** Bayesian
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Neutral model", "family": "Bayesian + DDM", "n_params": 3, "metric": "ELPD (LOO-CV)"},   {"name": "Influenced prior model", "family": "Bayesian + DDM", "n_params": 4, "metric": "ELPD (LOO-CV)"},   {"name": "Influenced choice model", "family": "Bayesian + DDM", "n_params": 4, "metric": "ELPD (LOO-CV)"},   {"name": "Dual influence model", "family": "Bayesian + DDM", "n_params": 5, "metric": "ELPD (LOO-CV)"},   {"name": "Dual influence model with item popularity", "family": "Bayesian + DDM", "n_params": 6, "metric": "ELPD (LOO-CV)"} ]  Note: Rescorla-Wagner versions of the models were also tested and achieved comparable results (Supplementary Fig. 2), but the Bayesian versions were the primary models reported.
- **model_mb_mf:** Bayesian
- **model_params:** MEDIUM confidence -- exact numerical point estimates for β_Δv, β_ρ, κ group means are derived from simulation parameter descriptions and graphical displays (Fig. 6b) rather than being explicitly reported in a table. The values ω=1.53 and a=2.10 are stated in the figure caption for Fig. 7.
- **social_param:** HIGH confidence -- clearly described in text.
- **social_param_name:** HIGH confidence
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Expected log pointwise predictive density (ELPD) via leave-one-out cross-validation (LOO-CV), compared using two-tailed t-tests of ELPD differences with standard errors.
- **how_model_fit:** individual-level-fit (hierarchical Bayesian estimation using No-U-Turn Sampling in Stan; group-level hyperparameters with participant-level parameters)
- **data_type_fit_to:** choice behavior, response times  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study only)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=61 total (social group: N=31 after 2 exclusions from 33 recruited, 21 female, ages 19-51, mean=26.7, SD=8.3; non-social group: N=30 after 5 exclusions from 35 recruited, 25 female, ages 18-48, mean=24.8, SD=6.7). Pilot: N=12 (9 female, ages 19-37, mean=25.8, SD=5.1) for generating partner preference data.
- **population_category:** healthy adults
- **population_age_range:** 19–51
- **ecological_validity:** Moderate. Uses real food snack items that participants could purchase, with real monetary incentives (£0.01 per correct response). Fasting requirement ensured motivation. However, the learning context is artificial (probabilistic feedback boxes rather than natural social observation), and the partner interaction is entirely passive (no real-time social exchange). The social framing is minimal -- participants are merely told they are learning another person's choices.
- **eligibility_flag:** 
- **concerns:** - The social manipulation is relatively thin (only the framing differs between groups; the actual task is identical). The "social" aspect is limited to knowing the items represent another person's choices. - Between-subject design means individual differences between groups could confound social vs. non-social comparison. - Exclusion criteria based on logistic regression prediction of choices appears unusual and post-hoc (2/33 social, 5/35 non-social excluded). - Exact fitted parameter values for key social parameters (β_Δv, β_ρ, κ) are only shown graphically as posterior distributions, not reported as precise numerical estimates in text or tables. - No parameter recovery analysis reported. - No model recovery analysis reported.
- **limitations_reported:** While our paradigm was designed to be somewhat naturalistic -- learning others' preferences often requires remembering discrete choices -- learning about others can also involve added layers of complexity"; "certain types of preference information might be useful for inferring more general features of others' personalities, which can in turn help us predict how they might behave in other contexts"; "another open question is whether the biases we observe in both social and non-social groups are sensitive to the level of noise in the environment"; "our task used a stable level of stochasticity -- correct answers being indicated with a probability of 0.8 -- while many natural reward environments contain volatility
- **limitations_categorized:** limited ecological validity; task simplicity; no volatility manipulation; limited social interaction; limited generalizability
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
- **ctx_copresence:** unclear
- **ctx_observability:** unclear
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
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = structural
- spec_locus = source
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MB_MF_hybrid
- tax_model_bayesian
- tax_model_drift_diffusion
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_drift_diffusion
- tax_rr_model_family = drift_diffusion
- tax_rr_param_learning_rate
- tax_rr_primary_topic = trait_impression
- tax_rr_topic_trait_impression
- tax_topic_trait_impression
