# Müller-Pinzler et al. (2022)

- **study_id:** `aa9af9e1a3bf50f6f_s1`
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
- **study_focus:** Self-efficacy belief formation; how affect (embarrassment, pride) biases valence-specific learning during the formation of self-efficacy beliefs via prediction errors.
- **study_focus_short:** Self-efficacy belief formation
- **learning_mode_description:** - Learning mode: Learning from manipulated performance feedback about one's own (and another person's) cognitive estimation abilities, with affective experience biasing valence-specific updating of self-efficacy beliefs.   - Learning from:     - Source type (non-social): self (own performance feedback) / (social): other (confederate's performance feedback)     - Source content (non-social): outcome (performance feedback percentile)   - Learning about:     - Target type (non-social): self (own ability belief) / (social): other (confederate's ability)     - Target content (non-social): state (self-efficacy belief / ability belief)  Note: The primary focus is on self-related belief formation. The "other" condition serves as a control. The learning itself is about forming beliefs about one's own abilities from performance feedback -- not inherently social in the source or target. However, the task is conducted in a social context (with a confederate present), the "other" condition involves observational learning about another person, and the key finding is that self-conscious emotions (embarrassment, pride -- which are social emotions requiring self-other evaluation) bias the learning process. The social component is the affective modulation and the self-other comparison context. (MEDIUM confidence on social classification)
- **task_description:** Participants completed the Learning Of Own Performance (LOOP) task, estimating properties (e.g., heights of buildings, weights of animals) and receiving manipulated performance feedback as percentile ranks, forming beliefs about their own and a confederate's cognitive estimation abilities across high and low ability conditions. After approximately every 20 trials, participants rated their current emotional state (embarrassment, pride, happiness, stress).
- **task_paradigm:** Self-evaluation / self-esteem task
- **players:** Single agent (participant), single target (confederate presented as another participant)
- **n_players:** single agent (1)
- **partner_type:** confederate
- **stimuli:** Estimation questions (properties of objects), manipulated percentile performance feedback, emotion rating scales
- **method:** fMRI / behavioural
- **method_full:** fMRI + pupillometry + behavioural
- **main_result:** - Main Results:   - Negativity bias in self-efficacy belief formation: higher learning rates for negative than positive PEs for Self (d = -0.425; mean alpha_Self/PE+ = 0.25, mean alpha_Self/PE- = 0.35)   - Agent x PE Sign interaction on learning rates (F(1,67) = 21.47, partial eta-squared = 0.243)   - Valence Learning Bias predicted by embarrassment (beta = -0.22) and pride (beta = 0.56) jointly (R-squared = 0.41, f-squared = 0.64)   - Valence Learning Bias correlated with self-esteem (rho = 0.33)   - Pupil dilation scaled with PE surprise (beta = 0.067) and PE valence (beta = -0.113)   - Embarrassment modulated pupil-PE valence association (beta = -0.0004)   - Neural PE valence tracking in dAI, vAI, amygdala, mPFC, VTA/SN modulated by Valence Learning Bias (all FWE-corrected within ROIs)   - Self-related PE valence associated with NAcc/VS, mPFC, bilateral angular gyrus activation   - Self > Other PE valence: NAcc/VS (right: t(38) = 5.23; left: t(38) = 5.77)   - Functional connectivity of right dAI with bilateral amygdala, mPFC, VTA/SN scaled with negative PE valence for Self > Other (FWE-corrected within ROIs)   - Independent effects of pride and embarrassment on neural PE valence tracking in amygdala (R-squared = 0.33), dAI (R-squared = 0.36), mPFC (R-squared = 0.36), VTA/SN (R-squared = 0.36)
- **effect_size:** - Main Results:   - Negativity bias in self-efficacy belief formation: higher learning rates for negative than positive PEs for Self (d = -0.425; mean alpha_Self/PE+ = 0.25, mean alpha_Self/PE- = 0.35)   - Agent x PE Sign interaction on learning rates (F(1,67) = 21.47, partial eta-squared = 0.243)   - Valence Learning Bias predicted by embarrassment (beta = -0.22) and pride (beta = 0.56) jointly (R-squared = 0.41, f-squared = 0.64)   - Valence Learning Bias correlated with self-esteem (rho = 0.33)   - Pupil dilation scaled with PE surprise (beta = 0.067) and PE valence (beta = -0.113)   - Embarrassment modulated pupil-PE valence association (beta = -0.0004)   - Neural PE valence tracking in dAI, vAI, amygdala, mPFC, VTA/SN modulated by Valence Learning Bias (all FWE-corrected within ROIs)   - Self-related PE valence associated with NAcc/VS, mPFC, bilateral angular gyrus activation   - Self > Other PE valence: NAcc/VS (right: t(38) = 5.23; left: t(38) = 5.77)   - Functional connectivity of right dAI with bilateral amygdala, mPFC, VTA/SN scaled with negative PE valence for Self > Other (FWE-corrected within ROIs)   - Independent effects of pride and embarrassment on neural PE valence tracking in amygdala (R-squared = 0.33), dAI (R-squared = 0.36), mPFC (R-squared = 0.36), VTA/SN (R-squared = 0.36)
- **learning_from:** Self and other; manipulated performance feedback (percentile ranks) generating prediction errors
- **learning_about:** Self (own cognitive estimation ability / self-efficacy belief) and other (confederate's estimation ability)---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Extended Valence Model (Model 8): RW with separate learning rates for positive and negative PEs for Self vs. Other, plus normal-distribution decay weighting factor w (alpha_Self/PE+, alpha_Self/PE-, alpha_Other/PE+, alpha_Other/PE-, w, 4 initial beliefs = 9 parameters)Update equation: EXP(t+1) = EXP(t) + alpha * PE(t) * (1 - w * ND), where ND = relative probability density of normal distribution for the feedback value, PE(t) = FB(t) - EXP(t)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Mean Model (M0)", "family": "descriptive", "n_params": 4, "metric": "PSIS-LOO = -2644.4"} 2. {"name": "Unity Model Self=Other (M1)", "family": "Rescorla-Wagner", "n_params": 5, "metric": "PSIS-LOO = -1801.3"} 3. {"name": "Context Model Self=Other (M2)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "PSIS-LOO = -1681.2"} 4. {"name": "Valence Model Self=Other (M3)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "PSIS-LOO = -1679.3"} 5. {"name": "Unity Model Self!=Other (M4)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "PSIS-LOO = -1621.2"} 6. {"name": "Context Model Self!=Other (M5)", "family": "Rescorla-Wagner", "n_params": 8, "metric": "PSIS-LOO = -1599.9"} 7. {"name": "Valence Model Self!=Other (M6)", "family": "Rescorla-Wagner", "n_params": 8, "metric": "PSIS-LOO = -1346.4"} 8. {"name": "ext. Valence Model linear (M7)", "family": "Rescorla-Wagner", "n_params": 9, "metric": "PSIS-LOO = -1251.4"} 9. {"name": "ext. Valence Model normal (M8) [WINNER]", "family": "Rescorla-Wagner", "n_params": 9, "metric": "PSIS-LOO = -1208.3"}
- **model_mb_mf:** MF
- **model_params:** - alpha_Self/PE+ [S]: learning rate for positive PEs for self (mean = 0.25, SD = 0.13) - alpha_Self/PE- [S]: learning rate for negative PEs for self (mean = 0.35, SD = 0.20) - alpha_Other/PE+: learning rate for positive PEs for other (mean = 0.27, SD = 0.16) - alpha_Other/PE-: learning rate for negative PEs for other (mean = 0.24, SD = 0.15) - w: weighting factor for normal-distribution decay of learning rates toward extreme feedback values - 4 x EXP_1 (initial beliefs): separate starting values for Self-High, Self-Low, Other-High, Other-Low - Derived: Valence Learning Bias = (alpha_Self/PE+ - alpha_Self/PE-) / (alpha_Self/PE+ + alpha_Self/PE-); mean = -0.12
- **social_param:** Valence Learning Bias [S] = normalized difference between self-related learning rates for positive vs. negative PEs, reflecting the degree to which self-efficacy belief updating is biased toward negative information. Separate alpha_Self vs. alpha_Other learning rates capture agent-specific learning.
- **social_param_name:** alpha_Self/PE+
- **social_param_value:** 0.25
- **social_param_sd:** 0.13
- **social_param_range:** 
- **model_comparison_metric:** PSIS-LOO (approximate leave-one-out cross-validation using Pareto smoothed importance sampling) + BMS (Bayesian model selection with protected exceedance probability pxp > .999, BOR < .001)
- **how_model_fit:** individual-level-fit (Bayesian MCMC sampling via RStan; 3 chains, 2400 post-burn-in samples per chain after 1000 burn-in, thinned by factor of 3)
- **data_type_fit_to:** choice behavior (performance expectation ratings)---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors: signed PE values as PE valence, unsigned PE values as PE surprise) + PPI (psychophysiological interaction for dAI functional connectivity)
- **contrast:** - PE surprise for Self: mPFC, L insula/temporal pole (FWE whole-brain) - PE surprise for Other: bilateral temporal pole, R angular gyrus, mPFC (FWE whole-brain) - PE valence for Self: NAcc/VS, mPFC, bilateral angular gyrus/SPL, precentral gyrus (FWE whole-brain) - Self > Other PE valence: bilateral NAcc/VS (FWE whole-brain) - Agent x PE Sign interaction: angular gyrus, bilateral NAcc/VS, PCC/precuneus, precentral gyrus (cluster-FWE) - Self > Other feedback: bilateral insula, ACC, thalamus (FWE whole-brain) - PPI right dAI (Self > Other, negative PE valence): bilateral amygdala, VTA/SN, mPFC (FWE within ROIs) - PPI left dAI (Self > Other, negative PE valence): L amygdala, VTA/SN (FWE within ROIs) - PE valence x Valence Learning Bias: bilateral dAI, vAI, amygdala, mPFC, VTA/SN (FWE within ROIs) - PE valence x embarrassment: R dAI, bilateral amygdala, VTA/SN (FWE within ROIs)
- **key_regions:** Self-related PE valence in NAcc/VS and mPFC; PE surprise in mPFC and insula/temporal pole; valence-specific biased learning tracked by dAI, vAI, amygdala, VTA/SN, mPFC; functional connectivity of dAI with amygdala, VTA/SN, mPFC scales with negative PE valence during self-efficacy belief formation.
- **key_regions_abbrev:** NAcc, mPFC, ACC, TP, insula, AI, amygdala, VTA
- **coordinates_peak:** PE Surprise - Self: - Paracingulate Gyrus/Superior Frontal Gyrus: 12, -6, 50 - Temporal Pole/Frontal Orbital Cortex (L): -39, 17, -22 - Superior Frontal Gyrus (R): 12, 20, 62 - Temporal Pole/Frontal Orbital Cortex (L): -30, 11, -28  PE Surprise - Other: - Temporal Pole/Frontal Orbital Cortex (L): -33, 17, -28 - Temporal Pole/Frontal Orbital Cortex (R): 39, 20, -28 - Angular Gyrus/Posterior Supramarginal Gyrus (R): 48, -46, 26 - Superior Frontal Gyrus/Frontal Pole (R/L): 6, 53, 26 - Frontal Pole/Superior Frontal Gyrus (R): 9, 47, 47 - Posterior Supramarginal Gyrus/Angular Gyrus (L): -51, -49, 17 - Temporal Pole (R): 48, 17, -31  PE Valence - Self: - Superior/Middle Frontal Gyrus (L): -15, 29, 53 - Superior Parietal Lobule/Superior Lateral Occipital Cortex (L): -36, -58, 56 - Angular Gyrus/Posterior Supramarginal Gyrus (L): -45, -55, 35 - Caudate/Accumbens (L): -9, 20, -1 - Caudate/Accumbens (R): 12, 17, -1 - Superior Lateral Occipital Gyrus/Angular Gyrus (R): 48, -61, 41 - Postcentral Gyrus/Superior Parietal Lobule (L): -45, -34, 56  Self > Other PE Valence: - Accumbens (L): -9, 26, -1 - Caudate/Accumbens (R): 12, 17, -4  Agent x PE Sign Interaction (Self > Other, Positive > Negative; cluster-FWE): - Angular Gyrus/Superior Lateral Occipital Cortex (R): 48, -58, 41 - Angular Gyrus/Superior Parietal Lobule (L): -42, -55, 44 - Putamen/Pallidum (R): 18, 5, -10 - Caudate/Accumbens (R): 12, 20, -1 - Caudate/Accumbens (L): -9, 20, -1 - Precentral Gyrus (L): -18, -19, 53 - Posterior Cingulate Gyrus/Precuneus (R/L): -15, -43, 32  PPI Right dAI (Self > Other, negative PE valence; FWE within ROIs): - Amygdala (R): 33, -1, -31 - Amygdala (L): -27, -4, -25 - VTA/SN (R/L): -18, -16, -13 - mPFC (R/L): -9, 35, 53  PPI Left dAI: - Amygdala (L): -30, -4, -22 - VTA/SN (R/L): -9, -13, -13
- **analysis_type:** both (whole-brain FWE for main contrasts; ROI analyses with FWE correction within predefined ROIs for covariate analyses)---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 69 total (39 fMRI [26 females, ages 18-28, M = 22.3, SD = 2.65] + 30 behavioural [24 females, ages 18-32, M = 23.3, SD = 3.97]); pupil data: n = 36 (3 excluded from fMRI sample for insufficient data quality). 48 initially recruited for fMRI, 9 excluded (6 did not believe cover story, 3 inattentive).
- **population_category:** healthy adults
- **population_age_range:** 18–28
- **ecological_validity:** Laboratory task with manipulated feedback and a confederate; estimation task is somewhat naturalistic but feedback is entirely fabricated and participants are deceived about the presence of another participant. Limited ecological validity -- real-world self-efficacy formation involves genuine performance outcomes and richer social contexts.
- **eligibility_flag:** 
- **concerns:** (1) The "social" component is somewhat indirect -- the main learning is about one's own abilities from performance feedback, with the social element being the presence of a confederate and the self-conscious emotions. The "other" condition is primarily a control rather than a social learning condition per se. (2) Deception-dependent paradigm (confederate). (3) Individual difference analyses are correlational -- directionality of affect-learning bias relationship cannot be established. (4) High proportion of female participants (~72%). (5) Code available only upon request, not openly shared.
- **limitations_reported:** the directionality of the effects remains to be determined"; "some of the key findings of the present study emerged at the level of individual differences" (correlational); the negativity bias was not universal -- "just under a third of the participants still showed a positive learning bias"; context-dependence of biases noted (may differ across tasks and stressful vs. non-stressful contexts); acknowledged that "it is not always straightforward to determine under which conditions a strategy is adaptive or whether the affective experience can ameliorate the individual's well-being"
- **limitations_categorized:** correlational design (directionality unclear); individual differences approach; limited generalizability (task-specific bias); ecological validity; sample composition
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - learning_mode social classification: MEDIUM -- the primary learning (self-efficacy from performance feedback) could be classified as non-social; the social element comes from the confederate context and self-conscious emotions. Classified as having social components but this is debatable. - w parameter mean fitted value: not reported in text (LOW) - Initial belief parameter mean fitted values: not reported individually (MEDIUM)
- **cannot_find:** - Mean fitted value for w parameter (decay weighting factor) - Mean fitted values for the 4 initial belief parameters (EXP_1) - Exact model formula in formal mathematical notation for the winning model (provided in Methods as equations 1-3, which I extracted above)
- **other_notes:** This paper builds on the authors' prior work with the LOOP task (Müller-Pinzler et al., 2019, Scientific Reports). The winning model (extended Valence Model with normal-distribution decay) is an extension of the Valence Model from prior publications. The paper provides a rich multi-modal dataset (fMRI, pupillometry, computational modeling, self-report affect) linking affect to biased self-efficacy belief formation. The key innovation is showing that self-conscious emotions (embarrassment, pride) are independently associated with valence-specific learning biases and their neural substrates.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- spec_target = social
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_instructed
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_valence_asymmetry
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
- tax_topic_self_belief_confidence
- tax_topic_self_esteem
