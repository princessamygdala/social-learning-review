# Cisler et al. (2019)

- **study_id:** `a20e877f71fab27e9_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Cisler, J. M., Esbensen, K., Sellnow, K., Ross, M., Weaver, S., Sartin-Tarm, A., Herringa, R. J., & Kilts, C. D. (2019). Differential roles of the salience network during prediction error encoding and facial emotion processing among female adolescent assault victims. *Biological Psychiatry: Cognitive Neuroscience and Neuroimaging, 4*(4), 371–380.
- **citation_short:** Cisler et al. (2019)
- **doi:** 10.1016/j.bpsc.2018.08.014
- **publication_type:** peer-reviewed journal---
- **year:** 2019.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** ETHODS: Adolescent girls (n = 30 girls who had previously been physicallyor sexually assaulted; n = 30 healthy; etheirrelativeroles inresponse toearly-lifetrauma
- **code_url:** 

## Computational level
- **study_focus:** Reinforcement learning and prediction error encoding in trauma-exposed adolescents; comparing salience network engagement during social vs. nonsocial RL tasks and facial emotion processing as a function of early-life assault exposure severity.
- **study_focus_short:** Reinforcement learning and prediction error encoding in trauma-exposed
- **learning_mode_description:** - Learning mode: Learning from reward outcomes about stimulus value in a three-armed bandit (social and nonsocial versions)   - Learning from:     - Source type (non-social in nonsocial task; social in social task): world (monetary outcomes delivered by mock people or houses)       - Social task: source is social (mock person returns money)     - Source content (non-social): outcome (monetary reward: $20 or $0)   - Learning about:     - Target type (social in social task; non-social in nonsocial task): other (mock people) / world (houses)     - Target content (non-social): stimulus value (probability of positive return)
- **task_description:** Participants completed two three-armed bandit RL tasks (one social with face stimuli, one nonsocial with house stimuli) where they chose among three options with differing reward probabilities (80%, 50%, 20%) that switched every 30 trials (90 trials total), plus a facial emotion processing task with neutral/fearful faces.
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), multi-target (3 mock people in social task; 3 houses in nonsocial task)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Neutral faces (social RL task), houses (nonsocial RL task), monetary outcomes ($20 or $0); fearful and neutral facial expressions (FEP task)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Assault-exposure severity x task (RL vs. FEP) interaction on SN activity (t = 3.56, p < .001, Bonferroni-corrected p = .007) - Weakened SN encoding of negative PEs with assault severity: main effect (t = −3.50, p < .001) - Social RL task: weakened SN encoding of negative PEs (t = −3.86, p < .001) - Nonsocial RL task: weakened SN encoding of negative PEs (t = −1.74, p = .09) - FEP: group x facial expression x duration interaction (t = 2.57, p = .011); greater SN response to overt fear in severe assault group (t = 2.09, p = .039) - CTQ corroborative: weakened SN PE encoding (t = −2.27, p = .026); greater SN FEP response (t = 2.18, p = .03) - SN vs. FS network opposing engagement during FEP (assault severity x network interaction: t(436) = 2.81, p = .005) - Strong negative relationship between SN and FS network during FEP (t(225) = −4.53, p < .001) - No relationship between PTSD symptom severity and SN PE encoding or FEP (all p > .6)
- **effect_size:** - Assault-exposure severity x task (RL vs. FEP) interaction on SN activity (t = 3.56, p < .001, Bonferroni-corrected p = .007) - Weakened SN encoding of negative PEs with assault severity: main effect (t = −3.50, p < .001) - Social RL task: weakened SN encoding of negative PEs (t = −3.86, p < .001) - Nonsocial RL task: weakened SN encoding of negative PEs (t = −1.74, p = .09) - FEP: group x facial expression x duration interaction (t = 2.57, p = .011); greater SN response to overt fear in severe assault group (t = 2.09, p = .039) - CTQ corroborative: weakened SN PE encoding (t = −2.27, p = .026); greater SN FEP response (t = 2.18, p = .03) - SN vs. FS network opposing engagement during FEP (assault severity x network interaction: t(436) = 2.81, p = .005) - Strong negative relationship between SN and FS network during FEP (t(225) = −4.53, p < .001) - No relationship between PTSD symptom severity and SN PE encoding or FEP (all p > .6)
- **learning_from:** World/other; monetary reward outcomes from chosen option (social: mock person's return; nonsocial: house outcome)
- **learning_about:** Stimulus value; expected reward probability of each option (social: trustworthiness/return probability of mock people; nonsocial: reward probability of houses)---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Risk-sensitive anticorrelated Rescorla-Wagner (A+RS+): V(t+1) = V(t) + δ × α, with separate learning rates for positive and negative PEs (risk-sensitive), updates unchosen options in opposite direction (anticorrelated). Softmax decision rule with exploration/exploitation parameter β.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "A−RS−", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AIC, log-likelihood"} 2. {"name": "A−RS+", "family": "Rescorla-Wagner (risk-sensitive)", "n_params": 3, "metric": "AIC, log-likelihood"} 3. {"name": "A+RS−", "family": "Rescorla-Wagner (anticorrelated)", "n_params": 2, "metric": "AIC, log-likelihood"} 4. {"name": "A+RS+", "family": "Rescorla-Wagner (risk-sensitive, anticorrelated)", "n_params": 3, "metric": "AIC, log-likelihood"}
- **model_mb_mf:** MF
- **model_params:** - α (learning rate, 0–1) — controls speed of value updating - For RS+ models: separate α_pos (learning rate for positive PEs) and α_neg (learning rate for negative PEs) [S — in social task context] - β (softmax exploration/exploitation parameter) - δ (prediction error = outcome − expected value) - Anticorrelation: unchosen option values updated in opposite direction
- **social_param:** No explicitly social parameter; however, separate tasks (social vs. nonsocial) use same model, and the paper examines differential neural encoding of PEs across social vs. nonsocial contexts.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC and log-likelihood
- **how_model_fit:** Group-level fit (mean sample parameters used for fMRI analyses) (HIGH — stated: "best-fitting model for the group were carried forward to the functional MRI analyses using mean sample parameters")
- **data_type_fit_to:** Choice behavior---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors) via ICA time-course regression — network time courses regressed onto design matrices with parametric modulation by signed PEs (outcome phase) and expected value V (anticipation and decision phases).
- **contrast:** - Signed PE parametric modulation of SN during RL outcome phase (social and nonsocial) - Expected value (V) parametric modulation during anticipation and decision phases - FEP: fear vs. neutral × overt vs. covert factorial - Assault severity × task (RL vs. FEP) interaction - SN vs. FS network engagement during FEP
- **key_regions:** Salience network (dACC, bilateral anterior insula) showed weakened negative PE encoding with assault severity, particularly during social RL; SN hyperactivity during emotion processing with assault severity; fusiform-striatum network (bilateral fusiform gyrus, caudate, nucleus accumbens) showed opposing pattern during FEP.
- **key_regions_abbrev:** NAcc, caudate, striatum, dACC, ACC, insula, AI, FFA
- **coordinates_peak:** Unavailable — not in main text or supplement. The study used ICA to identify networks rather than voxel-wise analyses, so peak coordinates for the salience network component are not reported as standard MNI coordinates in the main text. Supplement not accessible.
- **analysis_type:** N/A for standard voxel-wise analysis — ICA-based network analysis (component-level, not voxel-level). Could be considered whole-brain in the sense that ICA was applied to the entire brain volume.---  ### QUALITY
- **analysis_type_clean:** ROI
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 60 (30 assault-exposed girls, 30 healthy comparison girls); ages 11–17 years; imaging analyses based on N = 57 (3 excluded for motion/technical error).
- **population_category:** adolescents
- **population_age_range:** 11–17
- **ecological_validity:** Laboratory-based three-armed bandit task with monetary rewards; social condition uses static neutral face photos as "mock people" to invest in — limited ecological validity for real-world social learning. Facial emotion task uses standard face stimuli. All female adolescent sample limits generalizability.
- **eligibility_flag:** The paper uses computational modeling (Rescorla-Wagner), human behavioral data, and a social learning context (social RL task). However, the primary research question is about trauma/PTSD effects on neural encoding rather than social learning per se. The social RL task is one of multiple tasks. The paper does involve learning over time (90-trial bandit task with switching contingencies). Eligible but borderline — the focus is on trauma effects on salience network function, with social learning being one of several task conditions examined rather than the central computational question.
- **concerns:** - Mean fitted parameter values not reported in main text - Supplement not accessible — model details (exact formulas, parameter recovery, simulation details) may be there - PE regressors derived from group-level mean parameters rather than individual fits, which may reduce sensitivity - ICA approach means no standard peak MNI coordinates for specific brain regions - Social vs. nonsocial comparison is between-task, not within-task - Small sample (N = 60, imaging N = 57) - Heterogeneous comorbidity and medication use in assault group - Effect sizes reported only as t-statistics; no standardized effect sizes (d, r, η²)
- **limitations_reported:** Limited to adolescent girls, generalization to boys not warranted; possible heterogeneity due to site differences may have obscured effects; sample heterogeneous with respect to comorbidity and medication use; selected based on interpersonal traumas — unclear whether similar results expected for noninterpersonal traumas; FS network analyses were exploratory.
- **limitations_categorized:** Limited generalizability (sex-specific sample); multi-site heterogeneity; sample heterogeneity (comorbidity, medication); limited generalizability (trauma type); exploratory analyses
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
- **wc_rule10:** No
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- pop_ptsd_trauma
- rr_pop_adolescents
- rr_pop_healthy_adults
- rr_pop_ptsd_trauma
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_depth = general
- spec_locus = source+context
- spec_neural = shared
- spec_source = partly
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_param_temperature
- tax_popclass_clinical
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = threat_fear
- tax_rr_secondary_topic = emotion_inference
- tax_rr_topic_emotion_inference
- tax_rr_topic_threat_fear
- tax_social_nonsocial_comparison
- tax_topic_emotion_inference
- tax_topic_threat_fear
