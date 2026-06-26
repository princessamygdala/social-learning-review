# Zhang et al. (2025)

- **study_id:** `af12ee4644ba6ae69_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Zhang, Z.-H., Hu, K.-X., Shi, Y.-C., & Zhou, H.-Y. (2025). Aberrant predictive learning along the positive schizotypy–autistic traits continuum: Evidence from ambiguous social information processing. *Asian Journal of Psychiatry, 111*, 104666. https://doi.org/10.1016/j.ajp.2025.104666
- **citation_short:** Zhang et al. (2025)
- **doi:** 10.1016/j.ajp.2025.104666
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Laboratory of Mental Health and Psychological Crisis Intervention, Affiliated Mental Health Center (ECNU), School of Psychology and Cognitive Science,; School of Psychology and Cognitive Science, East China Normal University, 3663 North Zhongshan Road, Shanghai 200062, China; School of Psychology and Cognitive Science, East China Normal University, Shanghai, China; Center, Affiliated Mental Health Center of East China Normal University, Shanghai, China; etheless, findings are mixed; lable online 15 August 2025; University, Shanghai, China; lable at ScienceDirect; emails: hyzhou@psy.ecnu.edu.cn
- **code_url:** 

## Computational level
- **study_focus:** Social predictive learning; associative learning of gaze-emotion contingencies along the autism-schizophrenia continuum
- **study_focus_short:** Social predictive learning
- **learning_mode_description:** - Learning mode: Learning from gaze direction cues about the emotional valence of upcoming faces   - Learning from:     - Source type (social): other (face displaying gaze direction)     - Source content (social): stimulus (gaze direction as predictive cue)   - Learning about:     - Target type (social): other (face)     - Target content (social): state (emotional valence of facial expression)
- **task_description:** Participants view a gaze direction cue (left or right), predict whether the upcoming emotional face will be positive or negative, then judge the valence of the presented face (happy, angry, or ambiguous surprised). Cue-outcome associations reverse unpredictably across blocks, requiring learning and updating of predictions.
- **task_paradigm:** Volatility task (Behrens)
- **players:** Single agent (participant), no interactive partner
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Neutral face gaze direction cues (left/right), emotional faces (happy, angry, surprised) from Tsinghua Facial Expression Database; Chinese young adult faces
- **method:** online / behavioural
- **method_full:** Behavioural (online/lab, E-Prime 3.0)
- **main_result:** - Participants learned cue-outcome associations above chance (prediction accuracy M = .733 vs. 0.5; t(120) = 22.043, p < .001) - Prediction accuracy improved from first to last 10 trials within subblocks (F(1,119) = 112.171, p < .001, $\eta^2$ = .483) - Ambiguous face judgments biased by expectations (t(120) = 7.467, p < .001) - CAPE positive frequency negatively correlated with $\omega_2$ (belief update rate) (r = -.207, p = .023) - SPQ positive correlated with $\Pi_m$ (sensory memory precision) (r = .235, p = .010) and $\Pi_p$ (priming precision) (r = .191, p = .036) - PC2 (ASD-SSD oppositional dimension) correlated with $\Pi_m$ (r = .237, p = .009) and $\Pi_p$ (r = .220, p = .015) - CAPE positive frequency correlated with $\mu_3$ (environmental volatility) (r = .196, p = .031) and $\Pi_m$ (r = .188, p = .038) - No significant associations between autistic traits (AQ) and computational model parameters (except AQ Attention Switching with negative bias shift, r = .213, p = .019) - Expected emotions identified more accurately than unexpected (M = .973 vs. .951; t(120) = 5.156, p < .001)  ---  ### ALGORITHMIC LEVEL
- **effect_size:** - Participants learned cue-outcome associations above chance (prediction accuracy M = .733 vs. 0.5; t(120) = 22.043, p < .001) - Prediction accuracy improved from first to last 10 trials within subblocks (F(1,119) = 112.171, p < .001, $\eta^2$ = .483) - Ambiguous face judgments biased by expectations (t(120) = 7.467, p < .001) - CAPE positive frequency negatively correlated with $\omega_2$ (belief update rate) (r = -.207, p = .023) - SPQ positive correlated with $\Pi_m$ (sensory memory precision) (r = .235, p = .010) and $\Pi_p$ (priming precision) (r = .191, p = .036) - PC2 (ASD-SSD oppositional dimension) correlated with $\Pi_m$ (r = .237, p = .009) and $\Pi_p$ (r = .220, p = .015) - CAPE positive frequency correlated with $\mu_3$ (environmental volatility) (r = .196, p = .031) and $\Pi_m$ (r = .188, p = .038) - No significant associations between autistic traits (AQ) and computational model parameters (except AQ Attention Switching with negative bias shift, r = .213, p = .019) - Expected emotions identified more accurately than unexpected (M = .973 vs. .951; t(120) = 5.156, p < .001)  ---  ### ALGORITHMIC LEVEL
- **learning_from:** Other's gaze direction (social cue predicting emotional valence)
- **learning_about:** Emotional valence of others' facial expressions
- **outcome_modality:** face_expression

## Algorithmic level
- **winning_model:** HGF (3-level) + APM perceptual model (associative learning + priming + sensory memory); Model 8 (APM). Parameters: $\omega_2$ (second-level learning rate, M = -0.480, SD = 2.254), $\omega_3$ (third-level learning rate, M = -6.610, SD = 0.702), $\Pi_a$ (associative learning precision, M = 1.127, SD = 0.423) [S], $\Pi_m$ (sensory memory precision, M = 1.053, SD = 0.790), $\Pi_p$ (priming precision, M = 0.271, SD = 0.105), $\kappa_2$ (coupling strength, fixed = 1.0), $\zeta$ (inverse decision parameter, fixed = 1.0)
- **model_family:** HGF
- **model_class:** Belief updating
- **all_models_tested:** 1. Null (no perceptual influences) — family: HGF — n_params: contingency params only — metric: BIC + BMS 2. Model M (sensory memory) — family: HGF — BIC: 73387.60 3. Model P (priming) — family: HGF — BIC: 73340.09 4. Model MP (sensory memory + priming) — family: HGF — BIC: 70521.47 5. Model A (associative learning) — family: HGF — BIC: 65078.88 6. Model AM (associative learning + sensory memory) — family: HGF — BIC: 62220.13 7. Model AP (associative learning + priming) — family: HGF — BIC: 65289.28 8. Model APM (associative learning + priming + sensory memory) — family: HGF — BIC: 62587.31
- **model_mb_mf:** Bayesian (not RL; hierarchical Bayesian belief updating)
- **model_params:** - $\omega_2$: Second-level learning rate (speed of belief updating about cue-outcome association) — M = -0.480, SD = 2.254 - $\omega_3$: Third-level meta-volatility learning rate — M = -6.610, SD = 0.702 - $\kappa_2$: Coupling strength between levels 2 and 3 (fixed = 1.0) - $\Pi_a$ [S]: Precision of associative learning expectations on emotional perception — M = 1.127, SD = 0.423 - $\Pi_m$: Sensory memory precision — M = 1.053, SD = 0.790 - $\Pi_p$: Priming precision — M = 0.271, SD = 0.105 - $\Pi_s$: Disambiguation (sensory) precision (fixed = 1.50) - $\zeta$: Inverse decision parameter (fixed = 1.0) - $\mu_2$: Posterior mean 2nd level — M = -0.020, SD = 0.062 - $\mu_3$: Posterior mean 3rd level — M = -0.284, SD = 0.474
- **social_param:** $\Pi_a$ — precision of associative learning expectations, reflecting the weight of learned social cue-outcome associations (gaze-emotion) on perception of ambiguous social stimuli. Also $\omega_2$ — belief update rate for the social cue-emotion association.
- **social_param_name:** $\Pi_a$
- **social_param_value:** 1.127
- **social_param_sd:** 0.423
- **social_param_range:** 
- **model_comparison_metric:** Random-effects Bayesian Model Selection (BMS; exceedance probability); group-level BIC
- **how_model_fit:** Individual-level fit (HGF fitted per participant using TAPAS toolbox)
- **data_type_fit_to:** Choice behavior (prediction responses and perceptual judgment responses)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 121 (from initial 137; 16 excluded for careless responding); 43 males, 78 females; ages 17-25 (M = 20.59, SD = 1.96); healthy Chinese university students
- **population_category:** undergraduates
- **population_age_range:** 17–25
- **ecological_validity:** Limited. Task uses static face images with gaze cues in a computer-based paradigm. No real social interaction. Authors acknowledge the experimental context is "too simplified to fully simulate the complexity of real social interactions" and recommend future studies with naturalistic paradigms, VR, or behavioral observations.
- **eligibility_flag:** 
- **concerns:** - Non-clinical sample only; findings may not generalize to clinical ASD/SSD populations - AQ showed modest reliability (Cronbach's alpha = .758); AQ Attention to Detail subscale problematic (positive loading on PC2 when others were negative) - No corrections for multiple comparisons in exploratory correlational analyses - Correlation effect sizes between traits and model parameters are small (r = .19-.24) - No neural data despite discussing brain-level predictions - Task had high cue-outcome validity (70%), potentially reducing sensitivity to detect autistic trait effects
- **limitations_reported:** Homogeneous non-clinical sample limits generalizability to other age groups, clinical status, or cultural backgrounds; ecological validity limited as task too simplified to simulate real social interactions; no neuroimaging to examine brain-level processes despite hypothesized opposing neural patterns in ASD vs. SSD traits
- **limitations_categorized:** Limited generalizability; limited ecological validity; task simplicity; no neuroimaging data; sample homogeneity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.0
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - WC Rule 3 (simulate): LOW confidence -- no simulation described; could be in original Weilnhammer (2018) pipeline but not mentioned here   - WC Rule 8 (validate): MEDIUM -- behavioral correlations provide indirect validation but no formal posterior predictive check   - Effect sizes for trait-parameter correlations are all small (r ~ .19-.24): MEDIUM confidence these are robust
- **cannot_find:** - Exact number of free parameters per model (contingency model parameters shared across all 8 models; perceptual model parameters vary but exact count per model not stated)   - Data/code availability statement
- **other_notes:** This study adapts the Weilnhammer et al. (2018) paradigm from non-social (visual rotation) to social stimuli (gaze-emotion). The HGF model and prior parameters were adopted from the original study. Model 6 (AM) had the lowest group BIC (62220.13) but Model 8 (APM) won on BMS exceedance probability (xp = 1.00, p(r|y) = .649). The supplement contains the HGF prior parameters (Table S5), group BIC values (Table S6), and fitted parameter descriptive statistics (Table S7).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_autism
- pop_healthy_adults
- pop_schizophrenia
- rr_pop_autism
- rr_pop_healthy_adults
- rr_pop_schizophrenia
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_G_uncertainty_volatility
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
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_HGF
- tax_rr_model_family = HGF
- tax_rr_param_learning_rate
- tax_rr_param_precision
- tax_rr_primary_topic = emotion_inference
- tax_rr_secondary_topic = volatility
- tax_rr_topic_emotion_inference
- tax_rr_topic_volatility
- tax_social_nonsocial_comparison
- tax_topic_emotion_inference
- tax_topic_volatility
