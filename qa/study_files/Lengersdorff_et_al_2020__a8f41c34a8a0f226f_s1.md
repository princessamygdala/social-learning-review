# Lengersdorff et al. (2020)

- **study_id:** `a8f41c34a8a0f226f_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lengersdorff, L. L., Wagner, I. C., Lockwood, P. L., & Lamm, C. (2020). When implicit prosociality trumps selfishness: The neural valuation system underpins more optimal choices when learning to avoid harm to others than to oneself. *The Journal of Neuroscience*, *40*(38), 7286-7299. https://doi.org/10.1523/JNEUROSCI.0842-20.2020
- **citation_short:** Lengersdorff et al. (2020)
- **doi:** 10.1523/JNEUROSCI.0842-20.2020
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** UniversityofVienna,Vienna,1010,Austria,2DepartmentofExperimentalPsychology,UniversityofOxford,Oxford,OX13PH,UnitedKingdom,; Mittmann,AndréLüttig,SophiaShea,andLeonieBrögforassistanceduring personalharmaversion”hasbeenproposedasthebasisofproso-; ether humans are as good at learning to avoid others’ harm (prosocial learning) as they; CentreforHumanBrainHealth,UniversityofBirmingham,Birmingham,B152TT,UnitedKingdom; DepartmentofCognition,Emotion,andMethodsinPsychology,FacultyofPsychology,; ethe Datareportedherewereacquiredaspartofalongitudinalprojectinves-; ethe ful learningsignal,indicatingtheimm
- **code_url:** https://osf.io/h9txe/

## Computational level
- **study_focus:** Prosocial learning / harm avoidance learning (self vs. other)
- **study_focus_short:** Prosocial learning / harm avoidance learning (self vs. other)
- **learning_mode_description:** - Learning mode: Learning from one's own choice outcomes (painful/non-painful stimulation) about which symbols minimize harm to self or other   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (painful vs. non-painful electrical stimulation feedback)   - Learning about:     - Target type (social): other (confederate) [in Other condition]; Target type (non-social): self [in Self condition]     - Target content (social): action/policy (which symbol minimizes harm to the other); Target content (non-social): action/policy (which symbol minimizes harm to self)
- **task_description:** Participants chose between two abstract symbols that differed in their probability of delivering painful electrical stimulation (30% vs. 70%) either to themselves (Self condition) or to a confederate (Other condition), completing three blocks of 16 trials per condition. Feedback was provided via color-coded arrows indicating whether painful or non-painful stimulation would be delivered.
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), dyadic (male confederate)
- **n_players:** dyadic (2)
- **partner_type:** confederate
- **stimuli:** Abstract symbols (pairs), color-coded arrow feedback (red = pain, blue = no pain), photographs of confederate with neutral/painful facial expressions, electrical stimulation
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Participants made significantly more optimal choices during prosocial (Other) than self-relevant (Self) learning (condition effect: beta = 0.099, chi-squared = 5.78, p = 0.016) - Computational modeling revealed higher inverse temperature (value sensitivity) during prosocial vs. self-relevant learning (mu_beta_Other - mu_beta_Self 95% HDI = [0.03, 0.29]) - Value sensitivity fully mediated the effect of condition on optimal choices (indirect effect = 0.059, 95% BCa-CI = [0.044, 0.077]; direct effect non-significant p = 0.666) - Difference in value sensitivity correlated with emotional contagion trait (standardized beta = 0.43, p < 0.001) and negatively with proximal responsivity (standardized beta = -0.36, p = 0.008); overall R-squared = 0.183, F(5,81) = 3.62, p = 0.005 - Individual differences in prosocial vs. self-relevant value sensitivity correlated with VMPFC valuation-related activity differences (r = 0.476, p < 0.001 for behavioral correlation) - VMPFC showed increased functional connectivity with rTPJ during prosocial vs. self-relevant choices
- **effect_size:** See above (inline with main results). Key: condition effect beta = 0.099; mediation indirect effect = 0.059; emotional contagion standardized beta = 0.43; proximal responsivity standardized beta = -0.36; R-squared = 0.183; posterior predictive check correlations r = 0.757 (self), r = 0.796 (other).
- **learning_from:** Self; own choice outcomes (painful vs. non-painful stimulation feedback delivered to self or other as consequence of own choices)
- **learning_about:** Other (confederate) — which action/symbol minimizes harm to the other; Self — which action/symbol minimizes harm to oneself  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** RW with outcome-specific learning rates (alpha+, alpha-) and condition-specific inverse temperatures (beta_Self, beta_Other) — Model M4.2
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - M0: RW with single learning rate alpha, single beta (n_params = 2; metric: Bayes factor via mixture model) - M1: RW with outcome-specific learning rates alpha+, alpha- and single beta (n_params = 3; metric: BF M1 vs M0 > 1000) - M2.1: M1 + random effect of condition on alpha+ (n_params = ~4; BF vs M1 = 8.88) - M2.2: M1 + random + fixed effect of condition on alpha+ (n_params = ~4; BF vs M1 = 9.35) - M3.1: M1 + random effect of condition on alpha- (n_params = ~4; BF vs M1 = 0.32) - M3.2: M1 + random + fixed effect of condition on alpha- (n_params = ~4; BF vs M1 = 0.25) - M4.1: M1 + random effect of condition on beta (n_params = ~4; BF vs M1 = 37.67) - **M4.2** (WINNING): M1 + random + fixed effect of condition on beta (n_params = 4 free: alpha+, alpha-, beta_Self, beta_Other; BF vs M1 = 294.67) - M5.1: M4.2 + random effect of condition on alpha+ (BF vs M4.2 = 1.34) - M5.2: M4.2 + random + fixed effect of condition on alpha+ (BF vs M4.2 = 0.92) - M6.1: M4.2 + random effect of condition on alpha- (BF vs M4.2 = 0.28) - M6.2: M4.2 + random + fixed effect of condition on alpha- (BF vs M4.2 = 0.23)
- **model_mb_mf:** MF
- **model_params:** - alpha+ (learning rate for positive outcomes / no pain): posterior mean (logit) = -0.53, transformed mean = 0.37, 95% HDI [0.26, 0.49] - alpha- (learning rate for negative outcomes / pain): posterior mean (logit) = -1.83, transformed mean = 0.14, 95% HDI [0.10, 0.18] - beta_Self [S] (inverse temperature, self-relevant): posterior mean (log) = 1.54, transformed mean = 4.73, 95% HDI [3.27, 6.33] - beta_Other [S] (inverse temperature, prosocial): posterior mean (log) = 1.70, transformed mean = 5.53, 95% HDI [3.82, 7.39] - mu_beta_Other - mu_beta_Self [S]: posterior mean (log) = 0.16, transformed mean difference = 0.80, 95% HDI [0.03, 0.29] on log scale, [0.11, 1.54] transformed
- **social_param:** beta_Other (inverse temperature for prosocial/Other condition) — captures value sensitivity when making choices affecting another person. Higher beta_Other vs beta_Self indicates participants were more sensitive to value differences during prosocial choices.
- **social_param_name:** beta_Self
- **social_param_value:** 4.73
- **social_param_sd:** 
- **social_param_range:** 3.27–6.33
- **model_comparison_metric:** Bayes factors (via mixture estimation model; Kamary et al., 2014)
- **how_model_fit:** Individual-level fit (hierarchical Bayesian modeling with MCMC via STAN; population-level hyperparameters with individual-level parameters drawn from group distributions)
- **data_type_fit_to:** Choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors from computational model) + PPI (generalized psychophysiological interaction)
- **contrast:** - Parametric modulation by DeltaValue (chosen - unchosen value) during choice phase: VMPFC, precuneus, MTG - Correlation of [DeltaValue_Other - DeltaValue_Self] with [beta_Other - beta_Self]: VMPFC, precuneus, left angular gyrus - gPPI: VMPFC connectivity Other > Self during choice: rTPJ (right middle temporal gyrus/angular gyrus) - Positive > Negative outcomes: ventral striatum, VMPFC - Negative > Positive outcomes: bilateral AI, AMCC, supramarginal gyrus - (Negative - Positive)_Self > (Negative - Positive)_Other: bilateral AI, AMCC (stronger self-relevant aversive responses)
- **key_regions:** Value difference signal in VMPFC/sgACC and precuneus; individual differences in prosocial value sensitivity correlated with VMPFC and precuneus activation; VMPFC-rTPJ connectivity increased during prosocial choices; negative outcomes engaged bilateral AI and AMCC more strongly for self vs. other.
- **key_regions_abbrev:** vmPFC, mPFC, ACC, sgACC, TPJ, AI, precuneus
- **coordinates_peak:** - L/R precuneus (DeltaValue): 4, -52, 18 - L/R superior frontal gyrus, medial orbital / VMPFC (DeltaValue): 0, 58, -6 - L middle temporal gyrus (DeltaValue): -62, -32, 2 - R superior temporal gyrus (DeltaValue): 60, -26, 2 - R fusiform gyrus (DeltaValue): 36, -52, -4 - L hippocampus (DeltaValue): -20, -16, -20 - L angular gyrus (DeltaValue): -46, -70, 24 - L/R olfactory cortex (DeltaValue): 0, 8, -14 - L superior temporal gyrus (DeltaValue): -34, -22, 2 - R postcentral gyrus (DeltaValue): 48, -24, 62 - L/R precuneus (correlation beta_diff x value_diff): 6, -54, 24 - L/R superior frontal gyrus, medial orbital / VMPFC (correlation): 2, 52, -10 - L angular gyrus (correlation): -40, -64, 24 - R middle temporal gyrus / rTPJ (gPPI Other > Self): 46, -64, 20
- **analysis_type:** whole-brain (cluster-level FWE-corrected, cluster-defining threshold p < 0.001, cluster p < 0.05 FWE)  ---  ## QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 96 (all male, ages 18-35); 5 excluded from fMRI analyses for excessive head motion; 9 missing questionnaire data (empathy analyses on N = 87); 6 reported doubts about confederate (after second session, 2 weeks later)
- **population_category:** healthy adults
- **population_age_range:** 18–35
- **ecological_validity:** Moderate. Uses pain (electrical stimulation) as ecologically meaningful aversive outcome rather than monetary losses, increasing relevance to real harm avoidance. However, learning occurs via abstract symbol-outcome contingencies in a scanner, confederate interaction is deceptive, and the participant's choices for self vs. other are non-conflicting (no trade-off between self and other harm). Only male participants tested.
- **eligibility_flag:** 
- **concerns:** - Male-only sample limits generalizability - Confederate deception: 6/96 participants doubted the confederate was real (assessed only 2 weeks later at second session); no assessment at time of first session - Prosocial vs. self-relevant conditions were non-conflicting (optimal for other did not preclude optimal for self), limiting ecological validity - Reputational motives cannot be disentangled from prosocial motives (confederate knew participant's choices) - Data collected as part of a larger violent video game study; present data from first session only (before any manipulation) - Inverse temperature difference could also reflect exploration/exploitation differences rather than pure value sensitivity
- **limitations_reported:** Only males tested, limiting conclusions to this population; 6 participants doubted confederate after second session with no information on timing of doubts; confederate knew outcomes so reputational motives cannot be excluded; findings cannot determine whether prosocial advantage is specific to physical harm vs. financial loss contexts; task did not involve conflict between self- and other-harm; further studies needed to disentangle selfish and prosocial motives via manipulation of social observation
- **limitations_categorized:** Limited generalizability (male-only sample); deception credibility concerns; confound of reputational motives; task simplicity (no self-other conflict); limited ecological validity; domain specificity unclear (pain vs. financial loss)
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
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - wc_3 (MEDIUM): Posterior predictive checks were conducted post-fitting, but no explicit pre-data simulation described - wc_5 (HIGH): No parameter recovery — explicitly absent - wc_6 (HIGH): No model recovery — explicitly absent - Exact n_params for hierarchical models is ambiguous because of random/fixed effect structure (MEDIUM)
- **cannot_find:** - Supplement not available (no supplement file found; paper references "Extended Data" figures 4-1 and 4-2 which appear to be online supplements) - Exact number of free parameters per model is somewhat ambiguous due to hierarchical random effects structure - No preregistration statement found
- **other_notes:** The paper is part of a larger longitudinal study on violent video games; only first-session data (before any game training manipulation) are analyzed here. Code and data available on OSF. The "Extended Data" figures referenced in the paper (Fig. 4-1, 4-2) likely contain additional outcome-phase and prediction-error brain activation tables that were not accessible in the .txt extraction. Patricia Lockwood is a co-author on this paper.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_source = social
- spec_target = partly
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_temperature
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = moral_harm
- tax_rr_topic_moral_harm
- tax_rr_topic_prosocial_altruism
- tax_social_nonsocial_comparison
- tax_topic_moral_harm
- tax_topic_prosocial_altruism
