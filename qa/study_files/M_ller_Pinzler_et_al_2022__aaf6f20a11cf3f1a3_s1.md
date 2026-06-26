# Müller-Pinzler et al. (2022)

- **study_id:** `aaf6f20a11cf3f1a3_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Müller-Pinzler, L., Czekalla, N., Mayer, A. V., Schröder, A., Stolz, D. S., Paulus, F. M., & Krach, S. (2022). Neurocomputational mechanisms of affected beliefs. *Communications Biology*, *5*, 1241. https://doi.org/10.1038/s42003-022-04165-3
- **citation_short:** Müller-Pinzler et al. (2022)
- **doi:** 10.1038/s42003-022-04165-3
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofPsychiatryandPsychotherapy,SocialNeuroscienceLab,UniversityofLübeck,RatzeburgerAllee160,D-23538Lübeck,Germany; etherwiththefunctionalconnectivitydynamicsoftheanteriorinsulawithinthisnetwork,; etheoreticallymorevalidconstructsto; emails: laura.muellerpinzler@uni-luebeck.de
- **code_url:** https://github.com/gamlj/gamljin

## Computational level
- **study_focus:** Self-efficacy belief formation; how affective states (embarrassment and pride) bias valence-specific prediction error learning during self-efficacy belief updating.
- **study_focus_short:** Self-efficacy belief formation
- **learning_mode_description:** - Learning mode: Learning from manipulated performance feedback about one's own (and another person's) estimation abilities   - Learning from:     - Source type (non-social): world (experimenter-generated feedback)       - Source content (non-social): outcome (performance percentile feedback)   - Learning about:     - Target type (social): self (own abilities) and other (confederate's abilities)       - Target content (social): state (mental state; self-efficacy beliefs about own and other's estimation ability)
- **task_description:** Participants alternated between estimating properties themselves (Self) and observing a confederate estimate (Other), receiving manipulated performance feedback (percentile ranking) after each trial. Across High and Low Ability conditions, participants rated their expected performance before each trial, enabling measurement of trial-by-trial belief updating about self- and other-efficacy.
- **task_paradigm:** Self-evaluation / self-esteem task
- **players:** Single agent (participant), dyadic (confederate as observation target)
- **n_players:** dyadic (2)
- **partner_type:** confederate
- **stimuli:** Estimation questions (heights, weights, distances), percentile performance feedback, emotion rating scales (embarrassment, pride, happiness, stress/arousal)
- **method:** fMRI / behavioural
- **method_full:** fMRI + behavioural (separate sample) + pupillometry
- **main_result:** - Negativity bias in self-efficacy belief formation: higher learning rates for negative vs. positive PEs when learning about self (d = −0.425), not present for other - Valence Learning Bias negatively correlated with embarrassment (ρ = −0.24, p = .043) and positively with pride (ρ = 0.55, p < .001) - Combined regression: pride (β = 0.56, p < .001) and embarrassment (β = −0.22, p = .025) independently predicted Valence Learning Bias (R² = .41, f² = 0.64) - Pupil dilation scaled with PE surprise (β = 0.067, p = .032) and PE valence (β = −0.113, p = .017), with individual modulation by embarrassment and learning bias - Self-related PE valence positively associated with NAcc/VS, mPFC, angular gyrus activation - Individual differences in Valence Learning Bias, embarrassment, and pride modulated PE valence tracking in bilateral dAI, vAI, amygdala, mPFC, and VTA/SN (all p < .05 FWE within ROIs) - PPI: right dAI showed stronger functional connectivity with bilateral amygdala, mPFC, and VTA/SN for more negative PEs during Self vs. Other
- **effect_size:** - Agent × PE Sign interaction: F(1,67) = 21.47, partial η² = 0.243 - Negativity bias (Self): d = −0.425 - Combined affect regression on Valence Learning Bias: R² = .41, f² = 0.64 - Winning model R² = 0.46 ± 0.28 (M ± SD) for trial-by-trial prediction
- **learning_from:** World; manipulated performance percentile feedback on estimation task. Source: world (experimenter-generated feedback).
- **learning_about:** Self; own cognitive estimation abilities (self-efficacy beliefs). Also other (confederate's abilities). Target: self and other.  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Extended Valence Model (Model 8; adapted RW with 4 LRs: α_Self/PE+, α_Self/PE−, α_Other/PE+, α_Other/PE−; 1 weighting factor w for normal decay at scale extremes; 4 initial belief parameters)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Mean Model (M0)", "family": "Descriptive (mean)", "n_params": 4, "metric": "PSIS-LOO = -2644.4"},   {"name": "Unity Model Self=Other (M1)", "family": "RW", "n_params": 5, "metric": "PSIS-LOO = -1801.3"},   {"name": "Context Model Self=Other (M2)", "family": "RW", "n_params": 6, "metric": "PSIS-LOO = -1681.2"},   {"name": "Valence Model Self=Other (M3)", "family": "RW", "n_params": 6, "metric": "PSIS-LOO = -1679.3"},   {"name": "Unity Model Self≠Other (M4)", "family": "RW", "n_params": 6, "metric": "PSIS-LOO = -1621.2"},   {"name": "Context Model Self≠Other (M5)", "family": "RW", "n_params": 8, "metric": "PSIS-LOO = -1599.9"},   {"name": "Valence Model Self≠Other (M6)", "family": "RW", "n_params": 8, "metric": "PSIS-LOO = -1346.4"},   {"name": "Extended Valence Model linear (M7)", "family": "RW + linear decay", "n_params": 9, "metric": "PSIS-LOO = -1251.4"},   {"name": "Extended Valence Model normal (M8) [WINNER]", "family": "RW + normal decay", "n_params": 9, "metric": "PSIS-LOO = -1208.3"} ]
- **model_mb_mf:** MF
- **model_params:** - α_Self/PE+ : learning rate for positive PEs, self condition (M = 0.25, SD = 0.13) - α_Self/PE− : learning rate for negative PEs, self condition (M = 0.35, SD = 0.20) [S] - α_Other/PE+ : learning rate for positive PEs, other condition (M = 0.27, SD = 0.16) - α_Other/PE− : learning rate for negative PEs, other condition (M = 0.24, SD = 0.15) - w : weighting factor for normal decay of learning rates toward feedback scale extremes - SV1, SV2, SV3, SV4 : four initial belief (starting value) parameters for each condition
- **social_param:** The distinction between α_Self and α_Other learning rates captures agent-specific (self vs. social other) learning biases. The Valence Learning Bias = (α_Self/PE+ − α_Self/PE−) / (α_Self/PE+ + α_Self/PE−) is the key derived social parameter indexing self-specific negativity bias in belief updating.
- **social_param_name:** 
- **social_param_value:** 0.35
- **social_param_sd:** 0.20
- **social_param_range:** 
- **model_comparison_metric:** PSIS-LOO (Pareto smoothed importance sampling leave-one-out cross-validation); Bayesian model selection (BMS) with protected exceedance probability (pxp > .999, BOR < .001)
- **how_model_fit:** individual-level-fit (Bayesian MCMC via RStan; posterior mean as point estimate per participant)
- **data_type_fit_to:** choice behavior (performance expectation ratings)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors: PE valence [signed PE] and PE surprise [unsigned PE] as parametric modulators on feedback regressors) + PPI (psychophysiological interaction for dAI functional connectivity)
- **contrast:** - PE Surprise (unsigned PE): Self and Other — mPFC, insula/temporal pole activation (p < .05 FWE whole brain) - PE Valence (signed PE) for Self: NAcc/VS, mPFC, bilateral angular gyrus/superior parietal lobule, precentral gyrus (p < .05 FWE whole brain) - Self > Other PE Valence: bilateral NAcc/VS (left: t(38) = 5.77; right: t(38) = 5.23) - Valence Learning Bias × PE Valence (Self): bilateral dAI, vAI, amygdala, mPFC, VTA/SN (p < .05 FWE within ROIs) - Embarrassment × PE Valence (Self): right dAI, bilateral amygdala, VTA/SN (p < .05 FWE within ROIs) - PPI right dAI × PE Valence (Self > Other): bilateral amygdala, mPFC, VTA/SN (p < .05 FWE within ROIs)
- **key_regions:** Self-related PE valence in NAcc/VS and mPFC; individual differences in learning bias and affect modulate PE valence tracking in bilateral dAI, vAI, amygdala, mPFC, and VTA/SN; functional connectivity of dAI with amygdala, VTA/SN, and mPFC scales with negative PE valence during self-efficacy belief formation.
- **key_regions_abbrev:** NAcc, mPFC, ACC, AI, amygdala, VTA
- **coordinates_peak:** PE Valence Self: - Superior/Middle Frontal Gyrus (L): −15, 29, 53 - Superior Parietal Lobule/Lateral Occipital Cortex (L): −36, −58, 56 - Caudate/Accumbens (L): −9, 20, −1 - Caudate/Accumbens (R): 12, 17, −1 - Superior Lateral Occipital Gyrus/Angular Gyrus (R): 48, −61, 41 - Postcentral Gyrus/Superior Parietal Lobule (L): −45, −34, 56  PE Valence Self > Other: - Accumbens (L): −9, 26, −1 - Caudate/Accumbens (R): 12, 17, −4  PE Surprise Self: - Paracingulate Gyrus/Superior Frontal Gyrus (R/L): 12, −6, 50 - Temporal Pole/Frontal Orbital Cortex (L): −39, 17, −22  Agent × PE Sign interaction: - Angular Gyrus/Lateral Occipital Cortex (R): 48, −58, 41 - Angular Gyrus/Superior Parietal Lobule (L): −42, −55, 44 - Putamen/Pallidum (R): 18, 5, −10 - Caudate/Accumbens (R): 12, 20, −1 - Caudate/Accumbens (L): −9, 20, −1 - Precentral Gyrus (L): −18, −19, 53 - Posterior Cingulate Gyrus/Precuneus (R/L): −15, −43, 32  PPI Right dAI (Self > Other): - Amygdala (R): 33, −1, −31 - Amygdala (L): −27, −4, −25 - Amygdala (L): −24, 2, −13 - VTA/SN (R/L): −18, −16, −13 - mPFC (R/L): −9, 35, 53  PPI Left dAI (Self > Other): - Amygdala (L): −30, −4, −22 - VTA/SN (R/L): −9, −13, −13
- **analysis_type:** both (whole-brain FWE corrected for main PE effects; ROI-based FWE corrected for individual difference covariates in predefined ROIs: bilateral dAI, vAI, amygdala, mPFC, VTA/SN)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 69 total (39 fMRI [26 females, ages 18–28, M = 22.3, SD = 2.65] + 30 behavioural [24 females, ages 18–32, M = 23.3, SD = 3.97]); pupillometry n = 36 (3 excluded for data quality from fMRI sample)
- **population_category:** healthy adults
- **population_age_range:** 18–28
- **ecological_validity:** Lab-based task with manipulated (not veridical) performance feedback; confederate paradigm rather than genuine social interaction; conceptually novel estimation task limits generalization to real-world self-efficacy domains; however, emotion ratings and pupillometry add ecological richness to measurement of affective processes.
- **eligibility_flag:** 
- **concerns:** Individual difference analyses (learning bias × neural activity) are correlational and cross-sectional — directionality of affect-learning relationship cannot be established. The sample is predominantly female (72% across combined sample). Code available only upon request, not openly shared. The behavioral sample used two real participants rather than a confederate, introducing a design inconsistency across subsamples.
- **limitations_reported:** The directionality of the effects remains to be determined"; individual difference results require replication in larger, more diverse samples; cannot determine whether affect causes learning bias or vice versa; the study focused on a conceptually novel task environment and generalizability to established self-efficacy domains is unclear; stress and social context manipulations were not included; the pupil data could only be analyzed for the Self condition due to baseline offset differences between Agent conditions.
- **limitations_categorized:** limited causal inference; limited generalizability; sample size; limited ecological validity; task simplicity; measurement limitations (pupil data restricted to one condition)
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
- **wc_rule10:** Partial
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM — mean fitted values for α parameters reported in text for group-level comparisons; w parameter fitted values not reported; starting value (SV) means not reported - social_param: MEDIUM — the self/other distinction in learning rates is the social parameter but is not explicitly labeled as a "social parameter" by the authors - ecological_validity: MEDIUM — inferred from task description
- **cannot_find:** - Mean fitted value for w (weighting) parameter - Mean fitted starting values (SV1–SV4) - Exact parameter estimates for the covariate × PE valence interactions in the fMRI ROI analyses (reported as significant at p < .05 FWE within ROIs but specific t/β values for each ROI not given in main text; partial information in Supplementary Note 5)
- **other_notes:** This paper uses the LOOP task previously validated in Müller-Pinzler et al. (2019, Scientific Reports) and Czekalla et al. (2021, Scientific Reports). The "social" element is somewhat indirect — the confederate/other participant serves as a comparison condition rather than as a social interaction partner. The primary learning is about one's own abilities from non-social (experimenter-generated) feedback, but the self-evaluative nature of the beliefs and the social comparison context (self vs. other) make it social learning about the self. The paper provides a strong multi-modal approach combining computational modeling, fMRI, and pupillometry. The supplement contains detailed coordinate tables (Supplementary Tables 5–8) and parameter correlation tables (Supplementary Table 3).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_target = social
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = self_belief_confidence
- tax_rr_secondary_topic = self_esteem
- tax_rr_topic_self_belief_confidence
- tax_rr_topic_self_esteem
- tax_social_nonsocial_comparison
- tax_topic_self_belief_confidence
- tax_topic_self_esteem
