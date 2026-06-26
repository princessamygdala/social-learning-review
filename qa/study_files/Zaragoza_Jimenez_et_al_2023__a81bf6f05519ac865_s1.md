# Zaragoza-Jimenez et al. (2023)

- **study_id:** `a81bf6f05519ac865_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Zaragoza-Jimenez, N., Niehaus, H., Thome, I., Vogelbacher, C., Ende, G., Kamp-Becker, I., Endres, D., & Jansen, A. (2023). Modeling face recognition in the predictive coding framework: A combined computational modeling and functional imaging study. *Cortex*, *168*, 203--225. https://doi.org/10.1016/j.cortex.2023.05.021
- **citation_short:** Zaragoza-Jimenez et al. (2023)
- **doi:** 10.1016/j.cortex.2023.05.021
- **publication_type:** peer-reviewed journal (registered report)
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofNeuroimaging,CentralInstituteofMentalHealth(CIMH),MedicalFacultyMannheim,Universityof; DepartmentofChildandAdolescentPsychiatry,PsychosomaticsandPsychotherapy,UniversityofMarburg,; CenterforMind,Brain,andBehavior(CMBB),UniversityofMarburgandJustusLiebigUniversityGiessen,; LaboratoryforMultimodalNeuroimaging,DepartmentofPsychiatry,UniversityofMarburg,Germany; DepartmentofPsychiatry,UniversityofMarburgRudolf-Bultmann-Straße8,35039Marburg,Germany; Lab,DepartmentofPsychology,UniversityofMarburg,Germany; FacultyofMedicine,UniversityofMarburg,Germany; etheyaremorestronglyassoci-; emails:
- **code_url:** https://osf.io/tye24/

## Computational level
- **study_focus:** Face identity learning / perceptual learning of faces (replication of Apps & Tsakiris, 2013, using predictive coding framework to model how unfamiliar faces become familiar through repeated exposure, combining computational modeling with fMRI)
- **study_focus_short:** Face identity learning / perceptual learning of faces
- **learning_mode_description:** - Learning mode: Learning from repeated visual exposure to face stimuli about the familiarity/identity of faces, modulated by contextual familiarity   - Learning from:     - Source type (non-social): world     - Source content (non-social): stimulus (visual face presentations and contextual history of recent faces)   - Learning about:     - Target type (social): other (face identities of other people)     - Target content (social): stimulus (facial identity familiarity)
- **task_description:** Participants were repeatedly shown 24 computer-generated face identities from different viewpoints (front, 30 degrees left, 30 degrees right) and had to indicate via a two-option forced choice whether they had seen that person before, with 15 identities repeated up to 12 times and 9 shown only once. Contextual familiarity (average familiarity of recently presented faces) and stimulus familiarity (number of prior presentations) were systematically varied across 189 trials.
- **task_paradigm:** Face-identity learning task
- **players:** Single agent (participant), multi-target (24 computer-generated face identities)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Computer-generated faces (FaceGen software), color images, three viewpoints (front, 30 degrees left, 30 degrees right), binary forced-choice response ("yes"/"no" recognition), text feedback
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Behavioral learning effect: significant increase in "yes" responses from first three to last three presentations (t(30) = 15.697, d = 3.297, BF10 >= 100) - View-independent and context-dependent model (winning model) confirmed at group level with ABF10 = 9999.50 (posterior model probability > 99.999%) - Right FFA activity covaried with view-independent prediction error (delta): t-value = 4.99 (p < .05 svc) - Right FFA activity also covaried with view-independent familiarity (VI) and total familiarity (Ft) - No significant association between right pSTS and contextual familiarity (Ct) -- Hypothesis 2 not replicated - Left FFA prediction error association not replicated (p = .11) - Whole-brain analysis for delta: left superior frontal gyrus medial (t = 6.44), left caudate (t = 6.56), right amygdala (t = 6.65), right FFA (t = 4.99 svc)
- **effect_size:** - Behavioral learning effect: d = 3.297 - ABF10 = 9999.50 for winning model (view-independent and context-dependent) - Right FFA delta modulation: t = 4.99 (svc) - CLES = 0.32 for novel-face habituation control test
- **learning_from:** World; repeated visual presentations of face stimuli and contextual history of recent face familiarity
- **learning_about:** Other (face identities); facial identity familiarity  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** View-independent and context-dependent predictive coding model: Ft = VI_i,t * Ct; VI updated by prediction error delta = l - VI_i,n-1 with learning rate alpha; Ct updated by contextual PE epsilon = Ct-1 - VI_i,t with learning rate sigma; response via softmax with beta. (4 params: beta, l, alpha, sigma)
- **model_family:** Bayesian
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "View-independent and context-dependent (Model 1, winning)", "family": "Predictive coding / RW-like", "n_params": 4, "metric": "BIC/ABF10"},   {"name": "View-dependent (Model 2)", "family": "Predictive coding / RW-like", "n_params": 3, "metric": "BIC/ABF10"},   {"name": "View-dependent and context-dependent (Model 3)", "family": "Predictive coding / RW-like", "n_params": 4, "metric": "BIC/ABF10"},   {"name": "View-independent (Model 4)", "family": "Predictive coding / RW-like", "n_params": 3, "metric": "BIC/ABF10"},   {"name": "View-dependent and view-independent (Model 5)", "family": "Predictive coding / RW-like", "n_params": 5, "metric": "BIC/ABF10"},   {"name": "View-dependent, view-independent, and context-dependent (Model 6)", "family": "Predictive coding / RW-like", "n_params": 6, "metric": "BIC/ABF10"},   {"name": "Random answer probability (baseline)", "family": "Null/random", "n_params": 0, "metric": "BIC/ABF10"} ]
- **model_mb_mf:** N/A (not RL in the traditional MB/MF sense; predictive coding perceptual learning model)
- **model_params:** - β (beta): stochasticity/inverse temperature parameter, sensitivity of response to total familiarity; bounds (0.1, 20), step 0.01 - l (lambda): maximum view-independent familiarity; bounds (0, 2), step 0.01 - α (alpha): view-independent learning rate; bounds (0, 1), step 0.01 - σ (sigma): contextual learning rate; bounds (0, 1), step 0.01  Note: No mean fitted parameter values reported in the paper or supplement.
- **social_param:** None explicitly designated as social. The contextual familiarity parameter (sigma) captures how recent exposure to familiar faces modulates current face processing, but this is not explicitly a "social" parameter per the authors' framing -- it is a perceptual context parameter.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC-based approximate Bayesian model selection; approximate Bayes Factor (ABF10) derived from posterior model odds via BIC sums
- **how_model_fit:** individual-level-fit (maximum likelihood estimation per subject using L-BFGS-B with basin-hopping)
- **data_type_fit_to:** choice behavior (binary yes/no face recognition responses)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) with ROI analysis and whole-brain analysis
- **contrast:** - Face localizer: conjunction "faces > houses" AND "faces > scrambled" (to identify ROIs: OFA, FFA, pSTS, PPA) - Face identity learning task: faces > baseline (without parametric modulator) - Parametric modulators from winning model: (1) total familiarity Ft, (2) view-independent familiarity VI, (3) view-independent prediction error delta, (4) contextual familiarity Ct, (5) contextual prediction error epsilon - Whole-brain analysis for delta: p < .05 FWE corrected at voxel level + small volume correction with face localizer conjunction mask
- **key_regions:** Right FFA associated with multiple winning model parameters (prediction error delta, view-independent familiarity VI, total familiarity Ft); no significant STS association with contextual familiarity (failed replication); whole-brain delta effects in left superior frontal gyrus, left caudate, right amygdala, and right FFA.
- **key_regions_abbrev:** caudate, STS, AI, amygdala, SFG
- **coordinates_peak:** Face localizer (conjunction faces > houses AND faces > scrambled): - Left OFA: -42, -84, -10 - Right OFA: 48, -74, -6 - Left FFA: -42, -46, -18 - Right FFA: 42, -46, -16 - Left pSTS: -58, -54, 8 - Right pSTS: 46, -54, 14 - Left PPA: -22, -46, -8 - Right PPA: 24, -46, -10  Face identity learning task (faces > baseline): - Left OFA: -40, -82, -8 - Right OFA: 42, -78, -6 - Left FFA: -36, -44, -20 - Right FFA: 36, -40, -16 - Left pSTS: -52, -46, 14 - Right pSTS: 46, -40, 14  Parametric modulator delta (view-independent PE), p < .05 FWE / svc: - Left superior frontal gyrus medial: -6, 34, 44 - Left caudate: -20, 8, 4 - Right amygdala: 20, -4, -14 - Right FFA: 42, -50, -16
- **analysis_type:** both (ROI-based primary analysis using individually-defined face localizer ROIs + exploratory whole-brain analysis)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 34 enrolled; N = 31 in final behavioral/modeling analysis (11 male, 20 female; mean age 23.7 +/- 2.6 years; 1 excluded for low recognition, 2 for poor MRI quality); N = 28 in fMRI analysis (3 additional excluded for aberrant parametric modulator values)
- **population_category:** healthy adults
- **population_age_range:** M=23.7
- **ecological_validity:** Low -- uses computer-generated faces (FaceGen) rather than real faces; task is a simple repeated recognition paradigm with no real social interaction; stimuli rated to be neutral on trait dimensions, reducing ecological variation; laboratory fMRI setting.
- **eligibility_flag:** Borderline -- the paper uses computational modeling and human behavioral data with learning over time, but the "social" element is debatable. Participants learn to recognize computer-generated face identities, which is relevant to social perception but the learning process itself does not involve social interaction, social feedback, or learning about social attributes. The faces are not real people and there is no social agent. The "social" agent is effectively absent -- this is perceptual learning of face stimuli. FLAG: borderline social context; no social interaction or social feedback; perceptual face identity learning rather than social learning per se.
- **concerns:** - Mean fitted parameter values for the winning model are not reported in either main text or supplement -- only parameter bounds and step sizes given - The winning model only fitted 12/31 subjects best at individual level (view-dependent + context model fitted 13/31); group-level superiority driven by summed BIC, not individual-level consistency - Computational model parameters partly covary across trials (r > .94 between Ft, Ct, and VI), making it impossible to attribute unique neural contributions to specific parameters - Power for STS effect was only .37 (post-hoc), substantially lower than the .90 target - 3 subjects excluded from fMRI analysis post-hoc due to "absurdly high" regression weights from near-constant parametric modulator values - This is a replication study of Apps & Tsakiris (2013); the computational models are not novel - Faces are computer-generated and not real social agents
- **limitations_reported:** the computational parameters partly covary across trials and therefore one cannot conclude that single-parameter based significances reflect a unique contribution of that parameter"; actual power for the STS was .37, lower than for the FFA; winning model only fitted 12 of 31 subjects best at the individual level; localization of STS differed from the original study which may explain non-replication of Hypothesis 2; contextual familiarity formula was modified from the original for numerical stability
- **limitations_categorized:** parameter collinearity; low statistical power for subanalyses; poor individual-level model fit; non-replication of key finding; methodological modifications from original study; limited ecological validity
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** Partial
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `model_params` (MEDIUM): No mean fitted parameter values reported; only bounds and step sizes given. Cannot determine typical values. - `social_param` (MEDIUM): No parameter explicitly designated as social by the authors. Contextual familiarity rate (sigma) is the closest candidate but reflects perceptual context, not social information per se. - `eligibility_flag` (MEDIUM): Borderline social context -- face identity learning is relevant to social cognition but the task itself involves no social interaction, social agent, or social feedback. - `learning_mode` (MEDIUM): Source classified as non-social (world) because stimuli are computer-generated faces with no social agent involvement; target classified as social because faces represent other people's identities, though there is no actual social interaction.
- **cannot_find:** - Mean fitted parameter values for winning model (not reported in main text or supplement) - Individual-level BIC values are shown in Appendix H boxplots but exact values not tabulated - Effect sizes for the ROI-based t-tests of parametric modulators beyond what is shown in Fig. 7 and supplement Appendix F
- **other_notes:** This is a Registered Report specifically designed as a direct replication of Apps & Tsakiris (2013). The computational models were developed by the original authors, not the current authors. The paper partially replicated the original: Hypothesis 1 (winning model) was strongly confirmed; Hypothesis 3 (FFA-prediction error) was confirmed for right FFA only; Hypothesis 2 (STS-contextual familiarity) was not replicated. Data and code publicly available at https://osf.io/tye24/.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = general
- spec_locus = source+context
- spec_neural = dedicated
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_model_MB
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = trait_impression
- tax_rr_topic_trait_impression
- tax_topic_trait_impression
