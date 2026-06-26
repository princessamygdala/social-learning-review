# Driessen et al. (2025)

- **study_id:** `a0c0a3b5b57e95b71_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Driessen, J. M. A., Diaconescu, A. O., Atanassova, D. V., Buitelaar, J. K., Kessels, R. P. C., Glennon, J. C., & Brazil, I. A. (2025). Dissecting how psychopathic traits are linked to learning in different contexts: A multilevel computational and electrophysiological approach. *Cognitive, Affective, & Behavioral Neuroscience, 25*, 1543–1562.
- **citation_short:** Driessen et al. (2025)
- **doi:** 10.3758/s13415-025-01295-z
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department of Cognitive Neuroscience, Donders Institute; School of Medicine, University College Dublin, Dublin,; Institute of Biomedical and Biomolecular Research,; Centre for Neuroinformatics at CAMH, University; Institute for Brain, Cognition and Behaviour,; etherlands variety of samples (Hill et al; University, Nijmegen, The Netherlands; Centre Pompestichting, Nijmegen,; emails: josi.driessen@donders.ru.nl
- **code_url:** 

## Computational level
- **study_focus:** Social learning from advice; learning to track volatility of social (advisor trustworthiness) and nonsocial (card-outcome contingencies) information, and how psychopathic traits modulate these processes.
- **study_focus_short:** Social learning from advice
- **learning_mode_description:** - Learning mode: Learning from social advice and nonsocial outcome history about environmental contingencies under volatility   - Learning from:     - Source type (social): other (advisor)       - Source content (social): action/policy (advice recommendation)     - Source type (non-social): world       - Source content (non-social): outcome (card-colour reward history)   - Learning about:     - Target type (social): other (advisor)       - Target content (social): state (mental state; trustworthiness/fidelity)     - Target type (non-social): world       - Target content (non-social): state (world state; card-colour reward probabilities and their volatility)
- **task_description:** Participants predicted the outcome of a binary card draw (blue vs. green) while receiving advice from a video-recorded advisor and observing their own reward history. Both the advisor's trustworthiness and the card-colour probabilities varied across stable and volatile phases. Participants also wagered points reflecting confidence.
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant), single social target (1 advisor via pre-recorded video)
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Binary card choices (blue/green), pre-recorded video clips of advisor holding up a card, monetary reward feedback (points), wager scale (1-10)
- **method:** EEG / behavioural
- **method_full:** EEG (behavioural + electrophysiological)
- **main_result:** - Main Results:   - Performance accuracy higher in stable vs. volatile social phases (d = 1.21, 95% CI [0.93, 1.48])   - Phase x source interaction on accuracy (eta-p-squared = 0.309, 95% CI [0.15, 0.44])   - Advice taken more in stable vs. volatile social phases (d = 0.654, 95% CI [0.42, 0.89])   - Coupling parameter kappa higher for nonsocial than social info (eta-p-squared = 0.335, 95% CI [0.18, 0.47])   - Social bias parameter zeta significantly > 0 indicating preference for social info (d = 0.779, 95% CI [0.54, 1.01])   - Antisocial traits negatively correlated with social kappa (rho = -0.235, 95% CI [-0.43, -0.02])   - SRP total negatively correlated with volatile social accuracy (rho = -0.235, 95% CI [-0.43, -0.03])   - SRP total negatively correlated with midfrontal theta power (rho = -0.385, 95% CI [-0.56, -0.15])   - Meta-volatility parameter theta_a (social) positively correlated with theta power (rho = 0.221, 95% CI [<0.001, 0.40])   - Theta power higher for incorrect vs. correct trials (d = -0.717, 95% CI [-0.96, -0.47])
- **effect_size:** - Main Results:   - Performance accuracy higher in stable vs. volatile social phases (d = 1.21, 95% CI [0.93, 1.48])   - Phase x source interaction on accuracy (eta-p-squared = 0.309, 95% CI [0.15, 0.44])   - Advice taken more in stable vs. volatile social phases (d = 0.654, 95% CI [0.42, 0.89])   - Coupling parameter kappa higher for nonsocial than social info (eta-p-squared = 0.335, 95% CI [0.18, 0.47])   - Social bias parameter zeta significantly > 0 indicating preference for social info (d = 0.779, 95% CI [0.54, 1.01])   - Antisocial traits negatively correlated with social kappa (rho = -0.235, 95% CI [-0.43, -0.02])   - SRP total negatively correlated with volatile social accuracy (rho = -0.235, 95% CI [-0.43, -0.03])   - SRP total negatively correlated with midfrontal theta power (rho = -0.385, 95% CI [-0.56, -0.15])   - Meta-volatility parameter theta_a (social) positively correlated with theta power (rho = 0.221, 95% CI [<0.001, 0.40])   - Theta power higher for incorrect vs. correct trials (d = -0.717, 95% CI [-0.96, -0.47])
- **learning_from:** Other (advisor's advice — social) and world (card-colour outcome history — nonsocial)
- **learning_about:** Other (advisor's trustworthiness) and world (card-colour reward probabilities and their volatility)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** 3-level HGF (kappa_a, kappa_c, theta_a, theta_c, zeta, beta)
- **model_family:** HGF
- **model_class:** PE learning / Belief updating
- **all_models_tested:** - {"name": "Rescorla-Wagner", "family": "Rescorla-Wagner", "n_params": "not specified", "metric": "BIC = 8792.53, LME = -4386.34"} - {"name": "Kalman Filter", "family": "Kalman Filter", "n_params": "not specified", "metric": "excluded — posteriors centered on priors for all subjects"} - {"name": "2-level HGF", "family": "Hierarchical Gaussian Filter", "n_params": "not specified (fewer than 3L)", "metric": "BIC = 914.48, LME = -449.47"} - {"name": "3-level HGF", "family": "Hierarchical Gaussian Filter", "n_params": 6, "metric": "BIC = 917.11, LME = -450.84"}
- **model_mb_mf:** Bayesian
- **model_params:** - kappa_a [S]: coupling between 2nd and 3rd hierarchy levels for social (advisor) information; mean fitted = 0.46 - kappa_c: coupling between 2nd and 3rd hierarchy levels for nonsocial (card) information; mean fitted = 0.62 - theta_a [S]: meta-volatility (variance of volatility) for social information - theta_c: meta-volatility for nonsocial information - zeta [S]: social bias parameter; weight of social vs. nonsocial source (prior mean = 1; zeta > 1 = bias towards advice) - beta: inverse decision temperature (belief-to-response mapping; set to vary but not analysed)
- **social_param:** zeta — weight of social relative to nonsocial information source; kappa_a — coupling strength for social information hierarchy (reduced with increasing antisocial traits)
- **social_param_name:** kappa_a
- **social_param_value:** 0.46
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC, Log Model Evidence (LME), Bayesian Model Selection (BMS)
- **how_model_fit:** individual-level-fit (HGF toolbox; model inversion per participant)
- **data_type_fit_to:** choice behavior (card choice + wager magnitude)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (EEG time-frequency analysis, not fMRI)
- **contrast:** - Midfrontal theta (4-8 Hz, 100-400 ms post-feedback) across stable vs. volatile phases and social vs. nonsocial sources - Theta power: incorrect vs. correct trials (d = -0.717)
- **key_regions:** Midfrontal theta (Fz, FCz, Cz) as marker of adaptive control; negatively correlated with psychopathic traits; positively correlated with social meta-volatility parameter (theta_a).
- **key_regions_abbrev:** AI
- **coordinates_peak:** N/A — EEG study with scalp electrodes (Fz, FCz, Cz), no MNI coordinates
- **analysis_type:** N/A (EEG, not neuroimaging; electrode-level analysis at Fz, FCz, Cz)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 86 (36 males; ages 18-35, M = 24.1, SD = 2.8); N = 80 for EEG analyses (6 excluded for electrode distortions). Community sample oversampled from extremes of SRP-SF distribution (selected from N = 1,519 screening database).
- **population_category:** clinical
- **population_age_range:** 18–35
- **ecological_validity:** Moderate. Task uses pre-recorded video advisor (not live interaction) in a binary card-prediction paradigm with monetary incentives. Social context is somewhat artificial — advice delivered via pre-recorded clips rather than real-time interaction. Authors acknowledge that task design may reflect reduced sensitivity to secondary rather than specifically social information.
- **eligibility_flag:** 
- **concerns:** - The 3-level HGF had slightly worse BIC/LME than the 2-level HGF (BIC 917.11 vs 914.48) but was selected based on theoretical hypotheses rather than strict model comparison — authors acknowledge models performed similarly. - The Kalman Filter could not be adequately fit and was excluded from formal comparison. - No correction for multiple comparisons applied to correlational analyses; authors note key findings (antisocial traits x kappa_a) were not significant in Bayesian CIs, calling for replication. - Task design confounds social vs. primary/secondary learning distinction (authors acknowledge this). - All participants completed same trial order (stable-first for social info), which may bias social preference finding. - Number of free parameters for RW and 2-level HGF not explicitly stated.
- **limitations_reported:** Community sample, unclear generalizability to clinical/forensic populations; fixed trial order with stable social info first may have inflated social preference; task design may reflect primary vs. secondary information processing rather than specifically social vs. nonsocial; planned comparisons without correction for multiple comparisons, with Bayesian analyses not always converging — findings should be considered exploratory.
- **limitations_categorized:** limited generalizability; task design confound (social vs. secondary information); no multiple comparison correction; fixed trial order; community sample only
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
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - n_params for RW and 2-level HGF: not explicitly stated (MEDIUM confidence based on model descriptions) - Model selection: 3-level HGF chosen despite marginally worse BIC than 2-level HGF — justified by theoretical hypotheses (HIGH confidence this is accurately reported) - Mean fitted values for theta_a, theta_c, zeta, beta: not reported in main text or supplement (MEDIUM)
- **cannot_find:** - Exact number of free parameters for RW and 2-level HGF models - Mean fitted values for theta_a, theta_c, zeta (distribution shown in figure only for zeta) - Formal equations for the HGF (authors refer to Diaconescu et al. 2014, 2020 for these)
- **other_notes:** The supplement (.txt extracted from .docx) contains individual-level BIC/LME values per participant (Table S6), Bayesian correlation tables (S1-S3, S7-S8), parameter recovery figures (S1-S2), and parameter interpretation table (S5). The paper uses a modified version of the Diaconescu et al. (2020) "Wager task." Authors explicitly note that findings may reflect primary vs. secondary information processing rather than social vs. nonsocial, which is an important caveat for the social learning classification.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_psychopathy
- rr_pop_healthy_adults
- rr_pop_psychopathy
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = partly
- spec_depth = general
- spec_locus = source+target+context
- spec_neural = shared
- spec_source = partly
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_mod_instructed
- tax_model_HGF
- tax_model_bayesian
- tax_param_social_weight
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = G_uncertainty_volatility
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_HGF
- tax_rr_model_family = HGF
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_uncertainty
- tax_rr_secondary_topic = advice_taking
- tax_rr_topic_advice_taking
- tax_rr_topic_social_uncertainty
- tax_topic_advice_taking
- tax_topic_social_uncertainty
