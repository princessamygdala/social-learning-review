# Buades-Rotger et al. (2023)

- **study_id:** `afb81d7b37c8d463a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Buades-Rotger, M., Smeijers, D., Gallardo-Pujol, D., Kramer, U. M., & Brazil, I. A. (2023). Aggressive and psychopathic traits are linked to the acquisition of stable but imprecise hostile expectations. *Translational Psychiatry*, *13*, 197. https://doi.org/10.1038/s41398-023-02497-0
- **citation_short:** Buades-Rotger et al. (2023)
- **doi:** 10.1038/s41398-023-02497-0
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** etherspecificcomponentsofHEXlearningcanpredictantisocialthought,conduct,andpersonality; DepartmentofClinicalPsychologyandPsychobiology,UniversityofBarcelona,Barcelona,Spain; ether the propensity to as aversive environments may encourage the development of a; University,DondersInstituteforBrain,CognitionandBehaviour,Nijmegen,TheNetherlands; mitantsindepth,in step towards bridging computational quantities and real-world; CenterofBrain,BehaviorandMetabolism(CBBM),UniversityofLübeck,Lübeck,Germany; DivisionDiagnostics,Research,andEducation,ForensicPsychiatricCenter; DepartmentofPsychology,Universi
- **code_url:** 

## Computational level
- **study_focus:** Hostile expectation learning -- how individuals acquire hostile expectations about others' behavior through reinforcement learning, and how aggressive and psychopathic traits relate to specific computational components of this learning process.
- **study_focus_short:** Hostile expectation learning -- how individuals acquire hostile expectations
- **learning_mode_description:** - Learning mode: Learning from social opponent's actions (gun vs. phone) about the likelihood of hostile outcomes in an interpersonal conflict context   - Learning from:     - Source type (social): other (opponent/stranger)     - Source content (social): action/policy (drawing gun vs. phone)   - Learning about:     - Target type (social): other (opponent/stranger)     - Target content (social): state (mental state; hostile intent / threat level)
- **task_description:** Participants completed an online Go-NoGo shooting task where they viewed one of two opponents and had to predict whether the opponent would draw a gun or phone, choosing to shoot or withhold accordingly; gun probability (0.8 or 0.2) switched across blocks, and environmental threat was manipulated by including point-loss penalties in high-threat blocks.
- **task_paradigm:** Go/no-go
- **players:** Single agent (participant), multi-target (2 opponents; 1 policeman background)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Male avatar opponents, gun/phone outcomes, binary feedback (shot by opponent or policeman for wrong responses), point-loss threat cue
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Shoot decisions higher under high vs. low gun probability x high threat (F(1,268) = 10.94, p < .001, BF > 100; interaction)   - 2-level HGF best-fitting model; simulated-observed shoot correlation (r = 0.879)   - Parameter recovery: mean trajectory correlations r = 0.896 (mu), r = 0.997 (sigma), r = 0.933 (epsilon)   - High threat increased volatility omega (t(240) = 6.49, BF > 100), mean belief mu (t(240) = 6.49, BF > 100), uncertainty sigma (t(240) = 6.55, BF > 100), prediction error epsilon (t(240) = 12.25, BF > 100)   - SEM aggression model (high threat): omega (B = -0.240, p = .014), mu (B = 0.723, p = .001), sigma (B = 0.446, p < .001), epsilon (B = 0.777, p = .001); model fit: chi-sq(17) = 11.846, p = .809, CFI = 1, RMSEA < .001, SRMR = .024, PPP = .720   - SEM psychopathy model (high threat): omega (B = -0.235, p = .044), mu (B = 0.633, p = .010), sigma (B = 0.393, p = .007), epsilon (B = 0.571, p = .036); model fit: chi-sq(17) = 16.157, p = .513, CFI = 1, RMSEA < .001, SRMR = .024, PPP = .546   - No significant associations in low threat blocks for either aggression or psychopathy models   - Latent HEX factor correlated with aggression (r = 0.201, BF = 7.72) and psychopathy (r = 0.178, BF = 3.25)
- **effect_size:** - Main Results:   - Shoot decisions higher under high vs. low gun probability x high threat (F(1,268) = 10.94, p < .001, BF > 100; interaction)   - 2-level HGF best-fitting model; simulated-observed shoot correlation (r = 0.879)   - Parameter recovery: mean trajectory correlations r = 0.896 (mu), r = 0.997 (sigma), r = 0.933 (epsilon)   - High threat increased volatility omega (t(240) = 6.49, BF > 100), mean belief mu (t(240) = 6.49, BF > 100), uncertainty sigma (t(240) = 6.55, BF > 100), prediction error epsilon (t(240) = 12.25, BF > 100)   - SEM aggression model (high threat): omega (B = -0.240, p = .014), mu (B = 0.723, p = .001), sigma (B = 0.446, p < .001), epsilon (B = 0.777, p = .001); model fit: chi-sq(17) = 11.846, p = .809, CFI = 1, RMSEA < .001, SRMR = .024, PPP = .720   - SEM psychopathy model (high threat): omega (B = -0.235, p = .044), mu (B = 0.633, p = .010), sigma (B = 0.393, p = .007), epsilon (B = 0.571, p = .036); model fit: chi-sq(17) = 16.157, p = .513, CFI = 1, RMSEA < .001, SRMR = .024, PPP = .546   - No significant associations in low threat blocks for either aggression or psychopathy models   - Latent HEX factor correlated with aggression (r = 0.201, BF = 7.72) and psychopathy (r = 0.178, BF = 3.25)
- **learning_from:** other (opponent); hostile vs. non-hostile action outcomes (gun/phone)
- **learning_about:** other (opponent); probability of hostile behavior / hostile intent  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** 2-level Hierarchical Gaussian Filter (HGF) for binary outcomes (5 free parameters: omega, mu, sigma, epsilon, zeta)
- **model_family:** HGF
- **model_class:** PE learning / Belief updating
- **all_models_tested:** - {"name": "Rescorla-Wagner", "family": "Rescorla-Wagner", "n_params": "not specified (fewer than HGF)", "metric": "BMS exceedance probability"} - {"name": "K1 Sutton model", "family": "Sutton K1", "n_params": "not specified", "metric": "BMS exceedance probability"} - {"name": "Kalman Filter", "family": "Kalman Filter", "n_params": "not specified", "metric": "BMS exceedance probability"} - {"name": "3-level HGF", "family": "Hierarchical Gaussian Filter", "n_params": "more than 2-level HGF", "metric": "BMS exceedance probability"} - {"name": "2-level HGF (WINNER)", "family": "Hierarchical Gaussian Filter", "n_params": 5, "metric": "BMS exceedance probability"}
- **model_mb_mf:** Bayesian
- **model_params:** - omega (volatility): speed of belief updates as changes occur [S - social context: beliefs about hostile opponent behavior]. Mean fitted value not reported as single number (differs by condition; high threat: -8.28 women, -8.30 men approx.) - mu (mean belief): average expected likelihood of hostile outcomes [S]. Mean approx. 0.028-0.034 - sigma (uncertainty): accuracy/inaccuracy surrounding the belief [S]. Mean approx. 0.036-0.037 - epsilon (precision-weighted prediction error): discrepancy between expected and actual outcome [S]. Mean approx. -0.00032 to -0.00037 - zeta (exploration readiness): propensity to switch responses/deviate from current belief level. Mean approx. 8.97-9.27
- **social_param:** All primary parameters (omega, mu, sigma, epsilon) are social in context -- they capture beliefs about an opponent's hostile behavior. No parameter explicitly separates social from non-social learning.
- **social_param_name:** mu
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Bayesian Model Selection (BMS exceedance probability), as implemented in SPM12
- **how_model_fit:** individual-level-fit (Variational Bayes via HGF toolbox/TAPAS, with default priors; winning model refit with wider priors from Brazil et al. 2017)
- **data_type_fit_to:** choice behavior (shoot/withhold binary decisions)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A (no neuroimaging)  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 256 (questionnaire data; 69% women, age = 23.39 +/- 7.23); N = 269 for HEX task after excluding >25% missing trials; N = 241 after excluding computational outliers (+/- 2 SD); N = 188 for SEM analyses (complete HGF + self-report data)
- **population_category:** clinical
- **population_age_range:** 
- **ecological_validity:** Limited -- online shooting task with avatar opponents is an artificial proxy for real interpersonal conflict; HIBT uses superimposed rather than morphed facial expressions; self-report measures affected by social desirability; community/student sample not comparable to clinical/forensic populations.
- **eligibility_flag:** 
- **concerns:** Cross-sectional design limits causal inference; predominantly female community sample (69% women) limits generalizability to clinical/forensic populations; gender subgroup analyses underpowered (64 men vs. 124 women); exact n_params for non-winning models not reported; post-hoc power analyses acknowledged as unreliable by authors themselves; opponents in the task are automated (not real social agents), though the social framing is explicit.
- **limitations_reported:** The generalizability of our findings is nonetheless curtailed by the use of a predominantly female community sample, which is not readily comparable to clinical or forensic populations, and of self-reports, which are notoriously affected by social desirability"; "our behavioural measures may also suffer from a lack of ecological validity"; "the HIBT paradigm, as its superimposed face images are less realistic than morphed expressions"; "the HIBT does not allow to disentangle bias from accuracy"; "we used a cross-sectional design and thus it is unclear how HEX are maintained across the lifespan
- **limitations_categorized:** limited generalizability; sample composition (predominantly female, community); limited ecological validity; self-report bias (social desirability); task simplicity; cross-sectional design; measurement confounds (bias vs. accuracy in HIBT)
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
- **wc_rule10:** Yes
- **wc_score:** 9
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - all_models_tested n_params: MEDIUM confidence -- exact number of free parameters for RW, K1, Kalman Filter, and 3-level HGF not explicitly reported; paper notes HGF family had more parameters than other models - model_params fitted values: MEDIUM -- mean values reported only by gender in supplement Table S2, not as overall sample means - social_param: MEDIUM -- all parameters operate in a social task context but none is explicitly labeled "social" by the authors
- **cannot_find:** Exact number of free parameters for each non-winning model; overall sample mean fitted parameter values (only gender-split means available in supplement)
- **other_notes:** The "social agent" (opponent) is automated, not a real person -- participants were told they were predicting a man's behavior but outcomes were probabilistically determined. The paper also includes a Hostile Interpretation Bias Task (HIBT) that is not computationally modeled and thus not the focus of extraction. SEM analyses used both frequentist (lavaan) and Bayesian (blavaan) estimation with converging results. Alternative SEM models (correlated aggression/psychopathy factors; single antisocial factor) had substantially worse fit. The paper is also available as a preprint (PsyArXiv: 10.31234/osf.io/2ydsz) -- potential duplicate flag if preprint is separately included.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_psychopathy
- rr_pop_healthy_adults
- rr_pop_psychopathy
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = general
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_HGF
- tax_model_bayesian
- tax_param_precision
- tax_param_social_weight
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_F_affective_moral
- tax_rr_model_HGF
- tax_rr_model_family = HGF
- tax_rr_param_PE_signal
- tax_rr_param_precision
- tax_rr_primary_topic = reputation_learning
- tax_rr_secondary_topic = threat_fear
- tax_rr_topic_reputation_learning
- tax_rr_topic_threat_fear
- tax_topic_reputation_learning
- tax_topic_threat_fear
