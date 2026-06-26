# Burke et al. (2016)

- **study_id:** `aa792de35f80feb74_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Burke, C. J., Baddeley, M., Tobler, P. N., & Schultz, W. (2016). Partial adaptation of obtained and observed value signals preserves information about gains and losses. *The Journal of Neuroscience*, *36*(39), 10016-10025. https://doi.org/10.1523/JNEUROSCI.0487-16.2016
- **citation_short:** Burke et al. (2016)
- **doi:** 10.1523/JNEUROSCI.0487-16.2016
- **publication_type:** peer-reviewed journal
- **year:** 2016.0
- **field_of_study:** Psychology
- **affiliations_raw:** DepartmentofEconomics,UniversityofZurich, ThisisanOpenAccessarticledistributedunderthetermsoftheCreativeCommonsAttributionLicense; DepartmentofPhysiology,DevelopmentandNeuroscience,UniversityofCambridge,CambridgeCB23DY,UnitedKingdom,2LaboratoryforSocialand; DepartmentofEconomics,UniversityofZurich,8006Zurich,Switzerland,and3UniversityCollegeLondon,LondonWC1E7HB,; ethankAnthonyDickinsonandRaymundoBaez-Mendozaforhelpful highestsensitivity; lableonlinethroughtheJNeurosciAuthorOpenChoiceoption; mitsunrestricteduse,distributionandreproductioninany; etheirresponsestooutcomesforefficientcoding,they;
- **code_url:** http://mbb-team.github.io/VBA-

## Computational level
- **study_focus:** Observational learning; adaptive coding of obtained and observed outcome values across gain and loss contexts.
- **study_focus_short:** Observational learning
- **learning_mode_description:** - Learning mode: Learning from own and observed (confederate) reward/punishment outcomes about stimulus-outcome associations across gain and loss contexts   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (reward/punishment feedback; +10, 0, -10 points)     - Source type (social): other (confederate)       - Source content (social): outcome (observed reward/punishment feedback)   - Learning about:     - Target type (non-social): world       - Target content (non-social): stimulus (stimulus-outcome contingencies of abstract fractals)
- **task_description:** Participants performed a social 2-armed bandit task alternating between gain blocks (+10/0 points) and loss blocks (0/-10 points), choosing between two abstract fractal stimuli to maximize points. On each trial, participants first observed a confederate make a choice and receive an outcome on the same stimuli before making their own choice.
- **task_paradigm:** Two-armed bandit
- **players:** Single agent (participant), dyadic (gender-matched confederate; computer-controlled but presented as real)
- **n_players:** dyadic (2)
- **partner_type:** confederate
- **stimuli:** Abstract fractal stimuli, numerical point outcomes (+10, 0, -10), confederate photograph
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Relative (context-dependent) learning model outperformed absolute value learning model (BIC comparison: T = 3.05, p < 0.01; exceedance probability XP = 1.0)   - Partial adaptive coding of obtained outcomes in putamen (peak 24, 8, 14; classification accuracy 85%) and vmPFC (peak 4, 34, -22; accuracy 75%)   - Partial adaptive coding of observed outcomes in left TPJ/pSTS (peak -54, -44, 6; accuracy 85%) and left IFG (peak -44, 20, 14; accuracy 84%)   - No evidence for full adaptive coding or absolute value coding in multivariate patterns   - Univariate analysis confirmed partial adaptive coding in ventral striatum for obtained outcomes and IFG/STS for observed outcomes   - Univariate absolute value coding in posterior vmPFC (obtained) and ventral IFG/TPJ (observed)   - Significant main effect of model in vmPFC (F = 75.97, p < 0.001) and putamen (F = 72.41, p < 0.001): partial adaptation classifier outperformed full and absolute models
- **effect_size:** - Partial adaptation vs full/absolute in vmPFC: F = 75.97, p < 0.001; Tukey HSD p < 0.001 - Partial adaptation vs full/absolute in putamen: F = 72.41, p < 0.001; Tukey HSD p < 0.001 - Partial adaptation vs full/absolute in TPJ: F = 66.4, p < 0.001; Tukey HSD p < 0.001 - Partial adaptation vs full/absolute in IFG: F = 57.3, p < 0.001; Tukey HSD p < 0.001 - Behavioral model comparison: T = 3.05 (relative > absolute model BIC) - Note: No Cohen's d, r, eta-squared, or beta values reported; only F and t statistics with p-values
- **learning_from:** Self (own reward outcomes) and other (confederate's observed outcomes); reward/punishment feedback in gain/loss contexts
- **learning_about:** World; stimulus-outcome contingencies (which fractal is better in each block)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Relative Q-learning with context-dependent prediction errors (alpha, alpha_2 [contextual LR], beta)
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Absolute value Q-learning", "family": "Q-learning", "n_params": 2, "metric": "BIC"}, {"name": "Relative value Q-learning (contextual)", "family": "Q-learning with contextual adaptation", "n_params": 3, "metric": "BIC"}]
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate for option values Q): fitted values not reported - alpha_2 (learning rate for block context value V) [S - context-dependent]: fitted values not reported - beta (softmax inverse temperature): fitted values not reported  Model equations: - Absolute model: Q_{t+1}(b,c) = Q_t(b,c) + alpha * delta_C,t; where delta_C,t = R_C,t - Q(b,c) - Relative model: delta_C,t = R_C,t - V(b) - Q(b,c); V_{t+1}(b) = V_t(b) + alpha_2 * delta_V; where delta_V = R_t - V_t - Decision: P(b,x) = (1 + exp(beta * (Q(b,y) - Q(b,x))))^{-1}
- **social_param:** alpha_2 (contextual learning rate) - governs how quickly the reference point (block context value V) is updated, enabling context-dependent evaluation that applies to both self and observed outcomes. Note: this parameter is not exclusively social but enables the adaptive coding that extends to social observation.
- **social_param_name:** alpha_2
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC, exceedance probability (using mbb-vb-toolbox / VBA toolbox)
- **how_model_fit:** individual-level-fit (MLE using MATLAB fmincon, negative log-likelihood minimized per participant)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** MVPA (multivariate pattern analysis / searchlight decoding) + univariate GLM (conjunction and contrast analyses)
- **contrast:** - Model 1: Good vs bad outcomes (cross-validated across gain/loss blocks) - identifies outcome-encoding regions - Model 2: Gain vs loss block decoding - identifies block-specific effects (nuisance) - Model 3: Full adaptation test - train G10 vs L-10, test L0 vs G0 (and vice versa) - Model 4: Partial adaptation test - train G0 vs L-10, test G10 vs L0 (and vice versa) - Model 5: Absolute value coding - SVR on G10, (G0+L0), L-10 - Univariate partial adaptation: G10 > L-10 inclusive masked by L0 > G0 - Univariate full adaptation: conjunction G10 > G0 and L0 > L-10, exclusive masked by G10 vs L0 and G0 vs L-10 differences - Univariate absolute coding: G10 > G0 = L0 > L-10, exclusive masked by L0 vs G0 differences
- **key_regions:** Partial adaptive coding of obtained outcomes in bilateral putamen and vmPFC; partial adaptive coding of observed outcomes in left TPJ/pSTS and left IFG; univariate partial adaptation in ventral striatum (obtained) and IFG/STS (observed); absolute value coding in posterior vmPFC (obtained) and ventral IFG/TPJ (observed, inverse pattern).
- **key_regions_abbrev:** VS, putamen, striatum, vmPFC, mPFC, TPJ, STS, AI, IFG
- **coordinates_peak:** Obtained outcomes (MVPA partial adaptation): - Bilateral putamen: 24, 8, 14 - vmPFC: 4, 34, -22  Observed outcomes (MVPA partial adaptation): - Left TPJ/pSTS: -54, -44, 6 - Left IFG: -44, 20, 14  Univariate partial adaptation (obtained): - Ventral striatum: 12, 6, -9  Univariate absolute value coding (obtained): - Posterior vmPFC: 9, 30, -9
- **analysis_type:** both (whole-brain searchlight MVPA with inclusive masking; whole-brain univariate with conjunction/exclusive masking; ROI analyses on identified clusters)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 21 (23 recruited, 2 excluded for excessive head motion; 11 female; mean age 25.3 years, range 18-38)
- **population_category:** children
- **population_age_range:** 18–38
- **ecological_validity:** Low-moderate. Abstract fractal stimuli and point outcomes in a laboratory fMRI task. Confederate was computer-controlled but participants believed they were playing with a real person. No real social interaction; observation was one-directional. Gain/loss blocks clearly separated rather than intermixed.
- **eligibility_flag:** 
- **concerns:** - Confederate behavior was computer-controlled, not a real social agent (deception paradigm) - Small sample size (N = 21) - No parameter recovery or model recovery analyses reported - No fitted parameter values reported for the winning model - Effect sizes beyond F-statistics and classification accuracies not reported (no Cohen's d, eta-squared, etc.) - Data previously analyzed in Burke et al. (2010) for different questions - potential partial overlap in dataset - The behavioral models were fit only to non-social (own choice) trials; no computational model was fit to observational learning behavior specifically
- **limitations_reported:** The time-frame over which adaptation occurs remains unknown and may be dependent on a number of external factors"; participants received training before the experiment which "could have facilitated steady-state levels of (partial) adaptation"; "we cannot rule out that observing punishments was rewarding to participants" (social comparison effects)
- **limitations_categorized:** temporal dynamics unknown; practice effects; social comparison confound; limited ecological validity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Partial
- **wc_rule10:** Partial
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: LOW confidence - no fitted mean values reported for any parameter (alpha, alpha_2, beta) - social_param: MEDIUM confidence - alpha_2 is not exclusively social; it governs contextual adaptation for both self and observed outcomes - effect_size: MEDIUM confidence - only F-statistics and classification accuracies reported; no standardized effect sizes (d, r, eta-squared) - learning_mode target: MEDIUM confidence - participants learn stimulus-outcome associations (world), but the social observation component involves learning from another's outcomes which could also inform about the other's choice quality
- **cannot_find:** - Fitted parameter values for winning model (alpha, alpha_2, beta means) - Standardized effect sizes (Cohen's d, eta-squared, beta weights) - Data/code sharing information - Supplement not available (no supplement file found in papers folder)
- **other_notes:** - This paper reanalyzes data from Burke et al. (2010) with different methods (MVPA) and different questions (degree of adaptive coding). The earlier paper used model-based fMRI to identify neural correlates of prediction errors during observational learning. Flag for potential dataset overlap if Burke et al. (2010) is also in the review corpus. - The paper is primarily about neural coding efficiency (partial vs full adaptation) rather than social learning per se, though it uses a social observational learning paradigm. The computational models are standard Q-learning variants applied to non-social choice data; the social observation component is analyzed only at the neural level via MVPA. - The paper bridges behavioral economics (reference dependence, prospect theory) with computational neuroscience of value coding.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+context
- spec_neural = dedicated
- spec_source = social
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_PE_signal
- tax_rr_primary_topic = social_info_use
- tax_rr_topic_social_info_use
- tax_topic_social_info_use
