# Huang et al. (2025)

- **study_id:** `a3bad33b1442f406f_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Huang, C., Su, Y., Yang, B., Liu, Z., Liu, C., Zhang, L., Li, L., Zhou, R., Luo, Y.-J., & Feng, C. (2025). Neurocomputational mechanisms of social presence effects on instrumental learning. *Communications Biology*, 8, 1656. https://doi.org/10.1038/s42003-025-09043-2
- **citation_short:** Huang et al. (2025)
- **doi:** 10.1038/s42003-025-09043-2
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** LaboratoryofReadingandDevelopmentinChildrenandAdolescents(SouthChinaNormalUniversity),MinistryofEducation,Guangzhou,China; LaboratoryofBrain,CognitionandEducationSciences,MinistryofEducation,SouthChinaNormalUniversity,Guangzhou,China; LaboratoryofMentalHealthandCognitiveScience,SouthChinaNormalUniversity,Guangzhou,China; Center,UniversityMedicalCenterGroningen,UniversityofGroningen,Groningen,TheNetherlands; CenterforStudiesofPsychologicalApplication,SouthChinaNormalUniversity,Guangzhou,China; LabofCognitiveandLearning,FacultyofPsychology,BeijingNormalUniversity,Beijing,China; InstituteforNeuro
- **code_url:** https://github.com/Bonnie-bing/

## Computational level
- **study_focus:** Social facilitation/inhibition of instrumental learning; how social presence (evaluative observation) modulates distinct cognitive components of reinforcement learning including performance monitoring, choice perseverance, and working memory.
- **study_focus_short:** Social facilitation/inhibition of instrumental learning
- **learning_mode_description:** - Learning mode: Learning stimulus-response associations from probabilistic feedback under social observation versus alone   - Learning from:     - Source type (non-social): world       - Source content (non-social): outcome (probabilistic positive/negative feedback on button press)   - Learning about:     - Target type (non-social): world       - Target content (non-social): stimulus-action mapping (which button press is correct for each picture stimulus)  Note: The social presence (audience observation) is a contextual moderator of learning, not something learned from or about. The core learning loop is non-social: learning stimulus-response mappings from probabilistic feedback. The social component (being observed by a confederate) modulates the cognitive processes underlying this non-social learning. This is a borderline case for "social learning" -- see eligibility_flag.
- **task_description:** Participants performed a two-choice probabilistic learning task in which they learned associations between pictures and correct button presses (left or right) through trial-and-error feedback, under three feedback validity conditions (100%, 80%, 52%). They completed the task either alone or while being observed by a confederate seated behind them.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), between-subjects social context manipulation (observed by 1 confederate vs. alone)
- **n_players:** single agent (1)
- **partner_type:** confederate
- **stimuli:** Standardized object pictures (from Snodgrass & Vanderwart set; clothes, vehicles, furniture, etc.), binary feedback (checkmark = positive, cross = negative)
- **method:** EEG / behavioural
- **method_full:** EEG / behavioural / computational modeling
- **main_result:** - Social presence improved learning accuracy specifically in the high-validity condition during late learning stage (odds ratio = 2.18, z = 3.15) - Social presence increased win-stay behavior in high-validity condition (odds ratio = 2.04, z = 3.32) - Social presence increased lose-switch behavior in high-validity condition (odds ratio = 1.60, z = 2.95) - Social presence was associated with enhanced CRN amplitudes in late vs. early stage under high validity (interaction: F(1,36) = 9.29, eta_p^2 = 0.21) - Social presence reduced theta power in high-validity condition (audience: M = -0.30 vs. alone: M = 0.07; interaction social context x validity: F(1.97, 82.54) = 3.23, eta_p^2 = 0.071) - Computational modeling: social presence reduced forgetfulness parameter f (95% HDI of difference: [-0.41, -0.01]) - Computational modeling: social presence increased choice perseverance parameter tau_CK (95% HDI of difference: [0.29, 1.33]) - Forgetfulness (f) negatively correlated with accuracy in high- (r = -0.793, q(FDR) < 0.001) and medium-validity (r = -0.751, q(FDR) < 0.001) conditions - Choice perseverance (tau_CK) positively associated with accuracy in high- (r = 0.463, q(FDR) = 0.007) and medium-validity (r = 0.411, q(FDR) = 0.021) conditions
- **effect_size:** - Accuracy (social context x validity x stage): chi-squared(2) = 8.84 - High-validity late stage accuracy audience vs. alone: odds ratio = 2.18 - Win-stay high-validity audience vs. alone: odds ratio = 2.04 - Lose-switch high-validity audience vs. alone: odds ratio = 1.60 - CRN learning stage main effect: eta_p^2 = 0.14 - CRN social context x stage interaction: eta_p^2 = 0.14; in high-validity: eta_p^2 = 0.21 - ERN learning stage main effect: eta_p^2 = 0.35 - ERN validity main effect: eta_p^2 = 0.31 - FRN validity main effect: eta_p^2 = 0.12 - Theta power validity main effect: eta_p^2 = 0.14 - Theta power social context x validity interaction: eta_p^2 = 0.071 - Forgetfulness-accuracy correlation (high validity): r = -0.793 - tau_CK-accuracy correlation (high validity): r = 0.463
- **learning_from:** World; probabilistic binary feedback on button press correctness
- **learning_about:** World; correct stimulus-response (picture-button press) mappings  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** M7g: RP + RLF + CK with validity-dependent learning rate decay (alpha_0_pos, alpha_0_neg, theta_100%, theta_80%, theta_50%, f, alpha_CK, tau_CK); 8 free parameters
- **model_family:** MB/MF hybrid
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "M1 (RW)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "LOOIC"},   {"name": "M2 (RP)", "family": "Reward-Punishment", "n_params": 3, "metric": "LOOIC"},   {"name": "M3 (RLF)", "family": "Forgetful RL", "n_params": 3, "metric": "LOOIC"},   {"name": "M4 (CK)", "family": "Choice Kernel", "n_params": 3, "metric": "LOOIC"},   {"name": "M5 (RP+RLF)", "family": "Hybrid RP+RLF", "n_params": 4, "metric": "LOOIC"},   {"name": "M6 (RP+CK)", "family": "Hybrid RP+CK", "n_params": 4, "metric": "LOOIC"},   {"name": "M7 (RP+RLF+CK)", "family": "Hybrid RP+RLF+CK", "n_params": 5, "metric": "LOOIC"},   {"name": "M7b (M7 + validity-mod alpha)", "family": "Hybrid RP+RLF+CK", "n_params": 11, "metric": "LOOIC"},   {"name": "M7c (M7 + validity-mod tau)", "family": "Hybrid RP+RLF+CK", "n_params": 8, "metric": "LOOIC"},   {"name": "M7d (M7 + validity-mod f)", "family": "Hybrid RP+RLF+CK", "n_params": 8, "metric": "LOOIC"},   {"name": "M7e (M7 + validity-mod alpha_CK)", "family": "Hybrid RP+RLF+CK", "n_params": 8, "metric": "LOOIC"},   {"name": "M7f (M7 + validity-mod tau_CK)", "family": "Hybrid RP+RLF+CK", "n_params": 8, "metric": "LOOIC"},   {"name": "M7g (M7 + validity-mod theta)", "family": "Hybrid RP+RLF+CK", "n_params": 8, "metric": "LOOIC"} ]
- **model_mb_mf:** MF
- **model_params:** - alpha_0_pos: initial learning rate for positive feedback (0 <= alpha_0_pos <= 1); audience 95% HDI [0.32, 0.76], alone [0.20, 0.57] - alpha_0_neg: initial learning rate for negative feedback (0 <= alpha_0_neg <= 1); audience 95% HDI [0.15, 0.40], alone [0.08, 0.31] - theta_100%: learning rate decay for high-validity condition (0 <= theta <= 5); audience [0.02, 0.45], alone [0.06, 0.47] - theta_80%: learning rate decay for medium-validity condition; audience [0.12, 0.50], alone [0.00, 0.21] - theta_50%: learning rate decay for low-validity condition; audience [0.006, 0.44], alone [0.02, 0.39] - f: forgetting parameter (0 <= f <= 1); audience [0.10, 0.29], alone [0.23, 0.58]; **between-context difference 95% HDI [-0.41, -0.01] (significant)** - alpha_CK: choice kernel learning rate (0 <= alpha_CK <= 1); audience [0.10, 0.18], alone [0.08, 0.21] - tau_CK: sensitivity to CK value differences (0 <= tau_CK <= 10); audience [2.00, 2.63], alone [1.13, 1.93]; **between-context difference 95% HDI [0.29, 1.33] (significant)** [S]
- **social_param:** tau_CK (choice kernel sensitivity/choice perseverance) and f (forgetfulness) -- these parameters significantly differed between social presence and alone conditions. tau_CK [S] was higher under social observation, indicating greater reliance on choice history. f was lower under social observation, indicating reduced forgetting of learned values (enhanced working memory). Neither parameter is inherently social in the model; they become social parameters by virtue of being modulated by social context.
- **social_param_name:** tau_CK
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 2.00–2.63
- **model_comparison_metric:** LOOIC (leave-one-out information criterion)
- **how_model_fit:** individual-level-fit (hierarchical Bayesian analysis with MCMC; group-level priors constraining individual parameters)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (EEG study)
- **contrast:** - CRN: correct-response negativity at FCz (-50 to 50 ms), social context x learning stage interaction (high-validity: audience late > early, eta_p^2 = 0.21) - ERN: error-related negativity at FCz (-50 to 50 ms), learning stage main effect (late > early, eta_p^2 = 0.35), validity main effect (high and medium > low, eta_p^2 = 0.31) - FRN: feedback-related negativity at FCz (peak-to-peak 150-350 ms), validity main effect (low > high, eta_p^2 = 0.12) - Theta power: 4-7 Hz at FCz (100-300 ms post-feedback), social context x validity interaction (audience < alone in high-validity, eta_p^2 = 0.071)
- **key_regions:** Fronto-central scalp region (FCz electrode) for all ERP components (CRN, ERN, FRN) and theta oscillatory activity. Social presence enhanced CRN in late learning stage (high validity), and reduced theta power in high-validity condition, consistent with shift from external feedback processing to internal performance monitoring.
- **coordinates_peak:** N/A -- EEG study, no MNI/Talairach coordinates applicable. Scalp electrode: FCz.
- **analysis_type:** N/A (EEG, not neuroimaging; scalp-level ERP and time-frequency analyses)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 47 (23 alone context [11 males], 24 audience context [12 males]); mean age = 22.91 years (SD = 2.01). Note: various exclusions for specific analyses -- 7 participants excluded from RT and CRN/ERN analyses due to technical issues; 4 additional excluded from CRN/ERN for insufficient trials; 4 excluded from FRN for insufficient trials.
- **population_category:** healthy adults
- **population_age_range:** M=22.91
- **ecological_validity:** Between-subjects design with live confederate observer present in the room (evaluative presence, not mere physical presence), providing some ecological validity. However, confederate could not interact verbally or nonverbally with participant. Experimenter left the room. Task itself (probabilistic stimulus-response learning with abstract object pictures) has limited real-world ecological validity.
- **eligibility_flag:** BORDERLINE -- The study uses computational modeling and human behavioral data, and learning occurs over time. However, the learning itself is non-social (learning picture-button mappings from probabilistic feedback). The social component (being observed) is a contextual moderator, not the content of learning. The "social context" modulates learning parameters but participants do not learn from or about social agents. This is social facilitation of non-social learning rather than social learning per se. Flag as borderline for inclusion criterion "learning occurs in a social context.
- **concerns:** - Between-subjects design with relatively small N (23-24 per group) for detecting interactions - Programming error in stimulus E feedback contingencies during late learning stage (acknowledged by authors; those trials excluded) - No measure of social anxiety or evaluation apprehension as individual difference moderators - Model fitted to choice behavior only; did not jointly model RT or EEG data - No parameter recovery or model recovery analyses reported - The winning model M7g outperformed M7 despite no significant group-level parameter differences in theta parameters (authors discuss this in Supplementary Discussion as distinction between model selection and parameter inference)
- **limitations_reported:** Sample size was relatively small for a between-subjects design; replication in larger samples is necessary; a programming issue caused a subset of trials for one stimulus to deviate from intended feedback contingencies during the late learning stage; computational modeling focused solely on choice behavior rather than jointly incorporating choice, reaction time, and EEG data; the study examined evaluative presence rather than mere physical presence, and these may exert qualitatively distinct influences on behavior and neurocognitive processes; individual differences in social anxiety were not assessed or controlled for; both contextual and individual variability may elicit distinct motivational states in response to social presence
- **limitations_categorized:** sample size; programming error in experimental task; limited model scope (choice only, not joint RT/EEG); limited ecological validity (evaluative vs. physical presence not compared); no individual difference moderators measured; limited generalizability
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
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** yes
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - eligibility_flag: MEDIUM confidence -- borderline case; social presence modulates non-social learning rather than constituting social learning per se - learning_mode: MEDIUM confidence -- classified as non-social learning moderated by social context; could be argued that the social observation context makes this "learning in a social context" - model_mb_mf: HIGH confidence -- clearly model-free RL - social_param: MEDIUM confidence -- tau_CK and f are not inherently social parameters; they are standard RL parameters that differ across social context conditions
- **cannot_find:** - Exact mean fitted parameter values (only 95% HDI intervals reported for group-level parameters) - Pre-data simulation details (wc rule 3) - Parameter recovery analysis (wc rule 5) - Model recovery analysis (wc rule 6) - Preregistration status
- **other_notes:** - This is an EEG study (Communications Biology, 2025), not fMRI -- no brain coordinates expected. - The paper is a strong example of integrating behavioral, computational, and neural (EEG) approaches to study how social context modulates instrumental learning. - The social presence manipulation is evaluative (confederate observes performance), consistent with social facilitation/inhibition paradigms. - The study contributes to understanding social facilitation at the computational level but the learning itself is non-social. - Data and code are openly available.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target+context
- spec_neural = shared
- tax_domain_A_influence_transmission
- tax_domain_E_self_in_social_context
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_decay
- tax_param_perseveration
- tax_param_social_bonus
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_MB_MF_hybrid
- tax_rr_model_family = MB_MF_hybrid
- tax_rr_param_perseveration
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = social_approval_reward
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_social_approval_reward
- tax_rr_topic_social_info_use
- tax_topic_social_approval_reward
- tax_topic_social_info_use
