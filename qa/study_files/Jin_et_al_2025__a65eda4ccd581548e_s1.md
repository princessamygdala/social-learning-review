# Jin et al. (2025)

- **study_id:** `a65eda4ccd581548e_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Jin, Y., Zheng, D., Gu, R., Fan, Q., Dietz, M., Wang, C., Li, X., Chen, J., Hu, Y., & Zhou, Y. (2025). Substantial heritability underlies fairness norm adaptation capability and its neural basis. *Advanced Science*, *12*, 2411070. https://doi.org/10.1002/advs.202411070
- **citation_short:** Jin et al. (2025)
- **doi:** 10.1002/advs.202411070
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** LaboratoryofBehavioralScience CenterofFunctionallyIntegrativeNeuroscience; DepartmentofPsychology UniversityofChineseAcademyofSciences; DepartmentofEarlyChildhoodEducation InstituteofAutomation; UniversityofChineseAcademyofSciences Beijing100049,China; mitsuse,distributionand LaboratoryofMentalDisorders; InstituteofPsychology InstituteofClinicalMedicine; CenterforMentalDisorders&BeijingKey; Center ChineseAcademyofSciences; emails: zhouyuan@psych.ac.cn
- **code_url:** 

## Computational level
- **study_focus:** Norm learning / fairness norm adaptation -- investigating the heritability of the ability to learn and adapt fairness norms in an Ultimatum Game, and its neural and genetic (DRD2 dopaminergic) underpinnings.
- **study_focus_short:** Norm learning / fairness norm adaptation -- investigating the heritability of
- **learning_mode_description:** - Learning mode: Learning from encountered split ratios in an Ultimatum Game about what constitutes a fair offer (updating an internal fairness norm via prediction errors)   - Learning from:     - Source type (social): other (anonymous human proposers)     - Source content (non-social): outcome (monetary split ratio offered)   - Learning about:     - Target type (social): other (human proposers as a class)     - Target content (social): state (mental state; internal fairness norm -- what constitutes a fair proportion)
- **task_description:** Participants played as responders in a one-shot anonymous Ultimatum Game with 48 trials (24 human proposers, 24 computer proposers) while undergoing fMRI. On each trial, a proposer split money between themselves and the participant, who could accept or reject. Fairness levels ranged from 4% to 50% of the total.
- **task_paradigm:** Ultimatum game
- **players:** Single agent (participant as responder), multi-target (anonymous human proposers and computer proposers across 48 trials)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Alphanumeric codes denoting anonymous proposers, monetary split proposals with varying fairness ratios (4%--50%), binary accept/reject decisions
- **method:** fMRI
- **method_full:** fMRI (Study 1), longitudinal survey (Study 2, BDI-II 8 years later)
- **main_result:** - Higher acceptance rate for computer vs. human proposers (z = -8.13, p < .001) - Higher fairness sensitivity toward human than computer proposers (interaction z = 2.22, p = .027) - Acceptance rate increased over time only for human proposers (time x proposer type interaction: z = 2.78, p = .006) - Model-1 (learning for human proposers only) won model comparison (lowest LOOIC = 5090.3) - Heritability of learning rate: 36% (a^2 = .36, 95% CI [.13, .55]) - Heritability of initial fairness norm: 41% (a^2 = .41, 95% CI [.18, .59]) - Heritability of fairness sensitivity (human): 32% (a^2 = .32, 95% CI [.08, .53]) - Heritability of acceptance rate (human): 37% (a^2 = .37, 95% CI [.14, .56]) - SMA/mSFG PE encoding had significant phenotypic correlation with learning rate (r_ph = -.34, 95% CI [-.47, -.20], p < .0001) and significant genetic correlation (r_g = -.61, 95% CI [-1.00, -.61], p < .0001) - Anterior insula PE encoding had significant phenotypic correlation with learning rate (r_ph = -.27, 95% CI [-.41, -.12], p = .0002) but non-significant genetic correlation (r_g = -.36, p = .172) - DRD2 rs1800497 correlated with learning rate (F(1,137.86) = 3.77, p = .054) and SMA/mSFG activity (F(1,138.87) = 4.92, p = .028) - DRD2 rs2283265 correlated with learning rate (F(1,148.99) = 2.91, p = .090) and SMA/mSFG activity (F(1,147.85) = 6.85, p = .010) - SMA/mSFG mediated rs1800497 -> learning rate (Sobel z = 1.96, p = .050) - SMA/mSFG mediated rs2283265 -> learning rate (Sobel z = 2.23, p = .026) - Learning rate predicted depressive symptoms 8 years later (F(1,118) = 4.67, p = .033) - Phenotypic correlation between learning rate and BDI-II: r_ph = -.22, 95% CI [-.40, -.02], p = .023 - Marginally significant common genetic basis between learning rate and depression: r_g = -.41, 95% CI [-.80, .01], p = .050
- **effect_size:** See above; key effect sizes: heritability a^2 = .36 (learning rate), .41 (initial norm), .32 (fairness sensitivity), .37 (acceptance rate human); r_ph = -.34 (SMA/mSFG-learning rate); r_g = -.61 (SMA/mSFG-learning rate genetic); r_ph = -.27 (anterior insula-learning rate); r_ph = -.22 (learning rate-depression 8yr); predictive accuracy of winning model = 91.21%
- **learning_from:** Other (anonymous human proposers); monetary split ratios (fairness level of offers encountered over trials)
- **learning_about:** Social norm -- internal fairness norm (what proportion constitutes a fair offer from human proposers)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Rescorla-Wagner norm adaptation model (Model-1): learning for human proposers only, no learning for computer proposers, same initial fairness norm for both. 6 free parameters: alpha (learning rate for human proposers), beta_h (fairness sensitivity human), beta_c (fairness sensitivity computer), tau (inverse temperature), xi (lapse rate), fairnorm_0 (initial fairness norm). Fairness norm updates: fairnorm_h(t+1) = fairnorm_h(t) + alpha * (split_ratio(t) - fairnorm_h(t)); fairnorm_c = constant.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Model-1 (learning human only, same initial norm)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "LOOIC = 5090.3"},   {"name": "Model-2 (learning both, separate update, same LR, same initial norm)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "LOOIC = 5103.2"},   {"name": "Model-3 (learning both, together update, same LR, same initial norm)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "LOOIC = 5132.4"},   {"name": "Model-4 (learning both, separate update, different LR, same initial norm)", "family": "Rescorla-Wagner", "n_params": 7, "metric": "LOOIC = 5166.6"},   {"name": "Model-5 (learning both, together update, different LR, same initial norm)", "family": "Rescorla-Wagner", "n_params": 7, "metric": "LOOIC = 5226.2"},   {"name": "Model-6 (learning human only, different initial norm)", "family": "Rescorla-Wagner", "n_params": 7, "metric": "LOOIC = 5116.3"},   {"name": "Model-7 (learning both, separate update, same LR, different initial norm)", "family": "Rescorla-Wagner", "n_params": 7, "metric": "LOOIC = 5149.4"},   {"name": "Model-8 (learning both, separate update, different LR, different initial norm)", "family": "Rescorla-Wagner", "n_params": 8, "metric": "LOOIC = 5224.9"} ]
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate for human proposers) [S]: group mean = 0.29, 95% HDI [0.26, 0.31] - beta_h (fairness sensitivity, human proposers) [S]: group mean = 0.91, 95% HDI [0.90, 0.93] - beta_c (fairness sensitivity, computer proposers): group mean = 0.88, 95% HDI [0.86, 0.89] - tau (inverse temperature / choice randomness): group mean = 3.07, 95% HDI [2.87, 3.28] - xi (lapse rate): group mean = 0.025, 95% HDI [0.02, 0.03] - fairnorm_0 (initial fairness norm): estimated but group-level HDI not extracted from supplement text tables (tables did not parse clearly; values in Table S2-4)
- **social_param:** alpha (learning rate) -- speed of adapting internal fairness norm in response to social offers from human proposers; beta_h (fairness sensitivity toward human proposers) -- weighting of inequality aversion relative to monetary utility when facing human proposers.
- **social_param_name:** alpha
- **social_param_value:** 0.29
- **social_param_sd:** 
- **social_param_range:** 0.26–0.31
- **model_comparison_metric:** LOOIC (leave-one-out information criteria)
- **how_model_fit:** Individual-level fit (Hierarchical Bayesian estimation in RStan, simultaneously deriving group-level and individual-level estimates)
- **data_type_fit_to:** Choice behavior (binary accept/reject decisions)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors) -- PE from computational model entered as parametric regressor in first-level GLM at proposal display event
- **contrast:** - PE parametric regressor at proposal revelation (human proposer condition only) -- identifying regions modulated by norm prediction error - Voxel-wise univariate genetic modeling on PE contrast maps (PPM with >= 90% posterior probability of genetic influence)
- **key_regions:** Norm PE encoding in SMA/mSFG showed both phenotypic (r = -.34) and genetic (r = -.61) correlation with learning rate; right anterior insula showed phenotypic correlation (r = -.27) but not significant genetic correlation with learning rate. DRD2 polymorphisms modulated both learning rate and SMA/mSFG PE encoding. 18 ROIs from PPM included mPFC, sgACC, bilateral IFG, caudate, parahippocampus, precuneus, visual cortices, cerebellum.
- **key_regions_abbrev:** caudate, mPFC, ACC, sgACC, insula, AI, hippocampus, precuneus, IFG, cerebellum
- **coordinates_peak:** - mPFC (BA 9,10): -9, 48, 24 - SMA/mSFG (BA 6): -3, 12, 60 - sgACC (BA 25): 3, 24, -9 - Left Precentral Gyrus/IFG (BA 6,9): -45, -6, 36 - Right IFG (BA 47,45): 51, 18, -6 - Left Paracentral Lobule/Precentral Gyrus (BA 6): -21, -21, 69 - Right Anterior Insula (BA 13): 27, 24, -3 - Right ITG/MTG (BA 20,21): 69, -21, -18 - Right Fusiform Gyrus (BA 37): 36, -57, -21 - Left Parahippocampal Gyrus/Uncus (BA 34): -9, -9, -24 - Right Parahippocampal Gyrus (BA 28): 21, -15, -15 - Right Uncus (BA 28,36): 15, 6, -33 - Right Precuneus/SOG/SPL (BA 7,31,19): 27, -75, 51 - Left MOG (BA 19,18): -36, -93, 15 - Left MOG (BA 19): -33, -72, 36 - Right Caudate: 6, 3, 0 - Left Cerebellum Crus II & I: -33, -81, -36 - Right Cerebellum Crus II: 15, -90, -39
- **analysis_type:** Both (voxel-wise whole-brain genetic modeling via PPM, then ROI-based bivariate genetic modeling on extracted clusters)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** Study 1: N = 186 twins initially (93 pairs; 48 MZ, 45 DZ), 174 for fMRI (87 pairs; 44 MZ, 43 DZ) after motion exclusion; ages 16-26 (M = 20.27, SD = 2.36); 52% female. Study 2: N = 122 recalled 8 years later for BDI-II.
- **population_category:** adolescents
- **population_age_range:** 16–26
- **ecological_validity:** Low-moderate. The UG is a well-established but abstract economic game. Proposers were anonymous (alphanumeric codes, not names/photos), which limits ecological validity of social interaction. Computer proposer condition serves as a non-social control. The longitudinal 8-year follow-up adds external validity for real-world outcomes (depressive symptoms). Twin design strengthens genetic inferences but the sample is Chinese twins from a specific registry, limiting cross-cultural generalizability.
- **eligibility_flag:** 
- **concerns:** - Some key DRD2 effects on learning rate are only marginally significant (p = .054, .090), not fully significant at conventional thresholds - The mediation of DRD2 -> depression via learning rate is also only marginally significant (Sobel p = .087) - No independent replication sample was used - Self-report measures for psychiatric screening and depression outcome (BDI-II) - The additive genetic score for DRD2 is a simplified approach (sum of two SNPs) - Limited number of SNPs examined; no GWAS - Correlation between initial fairness norm and fairness sensitivity is very high (r = .87), raising questions about discriminant validity of these parameters
- **limitations_reported:** Our study examined the influence of a limited number of dopaminergic and serotonergic SNPs on the learning rate and the initial fairness norm, as well as the neural correlates of norm learning"; "We also utilized a relatively simple way to estimate the additive genetic effect, that is, to calculate the additive score of two DRD2 SNPs"; "the sample size is still limited compared to other behavioral studies (without fMRI) on the heritability of social norm and fairness appraisal"; "we used self-reported measures to acquire current/history of physical/psychiatric diagnoses, current psychiatric medications, family history of psychiatric diagnoses, neurological or metabolic illnesses, and head injuries"; "the self-reported measure of BDI-II might bring potential biases to the data"; "this study did not measure potential environmental factors that might interact with genetic predispositions to influence learning capabilities"; "this study did not employ an additional sample to formally test for the reproducibility of our findings from the genetic and fMRI analyses
- **limitations_categorized:** Limited genetic markers; simplified genetic scoring; sample size; self-report screening; self-report outcome measure; no gene-environment interaction measures; no replication sample
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
- **wc_rule10:** Partial
- **wc_score:** 9.0
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - fairnorm_0 group-level HDI: MEDIUM confidence -- supplement table text did not parse cleanly for the initial fairness norm parameter group-level estimate; the parameter exists and was estimated but exact group-level mean not extracted - model_recovery (WC Rule 6): MEDIUM confidence -- model recovery was performed for the winning model only (checking if simulated data reproduced behavioral patterns), but no formal confusion matrix across all 8 candidate models was reported - DRD2 effects on learning rate: HIGH confidence that they are marginal (p = .054, .090), accurately reported - The correlation between initial fairness norm and fairness sensitivity (r = .87) is HIGH confidence -- directly stated
- **cannot_find:** - Exact group-level mean fitted value for the initial fairness norm parameter (fairnorm_0) -- supplement tables did not parse from the .txt conversion clearly enough to extract this value - Code availability (not mentioned in the paper)
- **other_notes:** - This paper has two studies: Study 1 is the fMRI experiment with computational modeling (the core extraction); Study 2 is the 8-year longitudinal follow-up survey (BDI-II) which does not involve additional computational modeling or new learning tasks -- it is a follow-up measurement on the same twin cohort. Both studies should be treated as a single row since Study 2 is a follow-up on the same participants, not an independent study with separate modeling. - The computer proposer condition serves as a non-social control -- the winning model assumes no learning occurs for computer proposers. - Gene enrichment analysis of SMA/mSFG revealed high expression of dopaminergic synapses pathway genes, providing convergent evidence for DRD2-mediated norm adaptation. - The paper is primarily a behavior genetics study using computational modeling as a tool to decompose fairness decision processes; the fMRI is model-based parametric analysis.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pharma_dopamine
- pop_healthy_adults
- rr_pharma_dopamine
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = fairness_inequity
- tax_rr_secondary_topic = norm_conformity
- tax_rr_topic_fairness_inequity
- tax_rr_topic_norm_conformity
- tax_topic_fairness_inequity
- tax_topic_norm_conformity
