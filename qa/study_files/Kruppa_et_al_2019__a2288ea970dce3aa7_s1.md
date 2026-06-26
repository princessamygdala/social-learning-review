# Kruppa et al. (2019)

- **study_id:** `a2288ea970dce3aa7_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Kruppa, J. A., Gossen, A., Oberwelland Weiß, E., Kohls, G., Großheinrich, N., Cholemkery, H., Freitag, C. M., Karges, W., Wölfle, E., Sinzig, J., Fink, G. R., Herpertz-Dahlmann, B., Konrad, K., & Schulte-Rüther, M. (2019). Neural modulation of social reinforcement learning by intranasal oxytocin in male adults with high-functioning autism spectrum disorder: A randomized trial. *Neuropsychopharmaco
- **citation_short:** Kruppa et al. (2019)
- **doi:** 10.1038/s41386-018-0258-7
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofChildandAdolescentPsychiatry,Psychosomatics,andPsychotherapy,UniversityHospitalRWTHAachen,Aachen,Germany;2JARA-BrainInstituteII,Molecular; DivisionofEndocrinologyandDiabetes,UniversityHospitalRWTHAachen,Aachen,Germany;6DepartmentofChildandAdolescentPsychiatryandPsychotherapy,; DepartmentofChildandAdolescentPsychiatry,Psychosomatics,andPsychotherapy,UniversityHospitalFrankfurt,GoetheUniversity,FrankfurtamMain,; Center,Jülich,Germany;3InstituteofNeuroscienceandMedicine(INM-3),JülichResearchCenter,; center inGermany), randomized double-blind,placebo-controlled cross-over trial; Depart
- **code_url:** 

## Computational level
- **study_focus:** Social reinforcement learning — how intranasal oxytocin modulates learning from social versus non-social reinforcing feedback and associated reward prediction error (RPE) signals in the nucleus accumbens in adults with ASD versus healthy controls.
- **study_focus_short:** Social reinforcement learning
- **learning_mode_description:** - Learning mode: Learning stimulus–category associations from probabilistic reinforcing feedback in social versus non-social contexts   - Learning from:     - Source type (social in NS condition; non-social in NN/SN conditions): other (video of person giving thumbs-up/smiling) or world (colored fractal with check/cross)     - Source content (non-social): outcome (positive reinforcement vs. neutral feedback)       - In NS condition: social outcome (social approval via smile/thumbs-up)   - Learning about:     - Target type (social in SN condition; non-social in NN/NS conditions): other (video of person with neutral expression) or world (colored fractal)     - Target content (non-social): stimulus (category membership of learning target — A vs. B)
- **task_description:** Participants viewed a learning target (face video or fractal video) and indicated by button press whether it belonged to category A or B, then received probabilistic (75%) reinforcing feedback that was either social (person smiling and giving thumbs-up) or non-social (fractal with green checkmark). Three conditions varied the social nature of target and feedback: SN (social target, non-social feedback), NS (non-social target, social feedback), NN (non-social target, non-social feedback).
- **task_paradigm:** Social conditioning
- **players:** Single agent (participant), no interactive partner. Two groups: ASD (n=15) and healthy controls (n=24). Within-subjects crossover for oxytocin vs. placebo.
- **n_players:** network (5+)
- **partner_type:** human (recorded)
- **stimuli:** Video clips of male/female faces (neutral expression for targets; smiling with thumbs-up for social feedback), colored fractal videos (non-social targets/feedback), probabilistic reinforcement (75% contingency).
- **method:** fMRI / pharmacological
- **method_full:** fMRI (pharmacological fMRI with intranasal oxytocin, randomized double-blind placebo-controlled crossover)
- **main_result:** - Main Results:   - ASD showed enhanced learning with social targets under OXT vs. PLC: SN 81.20% vs. NN 72.07% (treatment x task interaction: $\eta_p^2$ = .20)   - ASD showed enhanced learning with social feedback under OXT in second interval: NS 81.00% vs. NN 71.29% ($\eta_p^2$ = .44 for interval 2)   - ASD showed enhanced learning with social targets under OXT in second interval: SN 87.09% vs. NN 71.29% ($\eta_p^2$ = .44)   - OXT enhanced RPE–NAcc correlation for social feedback in ASD: NS 3.48 vs. NN −1.12 ($\eta_p^2$ = .73)   - HC showed RPE–NAcc correlation for social feedback under PLC: NS 2.90 vs. NN −1.14 ($\eta_p^2$ = .26)   - Group x social target x treatment interaction in NAcc: [−8 8 −10], Z = 4.02 ($\eta_p^2$ = .24 for ASD OXT social target)   - HC showed reduced RPE–NAcc correlation for social targets under OXT: SN −0.70 vs. NN 2.72 ($\eta_p^2$ = .27)   - Negative correlation between NAcc activation and Reward Dependence (TCI-140 RD) in ASD under OXT: [−12 12 −6], Z = 3.27
- **effect_size:** $\eta_p^2$ = .20 (treatment x task in ASD); $\eta_p^2$ = .44 (task x treatment x interval, interval 2, ASD); $\eta_p^2$ = .73 (RPE–NAcc for social feedback in ASD under OXT); $\eta_p^2$ = .26 (RPE–NAcc for social feedback in HC under PLC); $\eta_p^2$ = .24 (RPE–NAcc for social target in ASD under OXT); $\eta_p^2$ = .27 (RPE–NAcc for non-social > social target in HC under OXT); $\eta_p^2$ = .11 (overall SN task OXT > PLC across groups); $\eta_p^2$ = .08 (treatment x task x interval across groups)
- **learning_from:** Source: world/other; reinforcing probabilistic feedback — social (video of person smiling/thumbs-up) or non-social (fractal with checkmark/cross)
- **learning_about:** Target: other/world; category membership (A vs. B) of social targets (face videos) or non-social targets (fractal videos)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Q-learning with softmax decision function (1 free parameter: $\alpha$ learning rate; $\beta$ fixed)
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Q-learning with softmax", "family": "Q-learning", "n_params": 1, "metric": "MLE"}]
- **model_mb_mf:** MF
- **model_params:** - $\alpha$ (learning rate): free parameter, estimated per subject via MLE. Represents the extent to which RPE is used to update the value of an option. 0 ≤ $\alpha$ ≤ 1. Mean fitted values not reported. - $\beta$ (inverse temperature): fixed (value not specified). Represents exploration–exploitation balance. - Q-values: initially set to zero for all stimulus–response combinations. - Reward coding: +1 for positive reinforcement, 0 for neutral feedback.
- **social_param:** None explicitly — the model has no dedicated social parameter. Social modulation is tested at the task-condition level (social vs. non-social feedback/target), not within the model itself.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** MLE (maximum likelihood estimation). No formal model comparison reported — only one model was fitted.
- **how_model_fit:** individual-level-fit (MLE per subject to estimate $\alpha$; $\beta$ fixed)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — feedback events parametrically modulated by trial-wise individual RPE values; target phase parametrically modulated by Q-values. Second-level flexible factorial ANOVA.
- **contrast:** - RPE correlation with brain activation during feedback phase across all groups/conditions > baseline (whole-brain) - Group x social feedback x treatment interaction in NAcc ROI: [ASD OXT (NS > NN)] vs. [HC OXT (NS > NN)] - Group x social target x treatment interaction in NAcc ROI: [ASD OXT (SN > NN)] vs. [HC OXT (SN > NN)] - Brain–behavior correlation: OXT_NS > PLC_NS with TCI-140 RD in ASD (NAcc ROI)
- **key_regions:** RPE signal correlated with broad network including precuneus, occipital cortex, angular gyrus, cingulate, medial OFC, nucleus accumbens, putamen, thalamus, cerebellum. OXT modulated RPE–NAcc coupling selectively for social feedback and social targets in ASD. No amygdala effects.
- **key_regions_abbrev:** NAcc, putamen, OFC, ACC, amygdala, precuneus, cerebellum, thalamus
- **coordinates_peak:** - Precuneus L: −4, −58, 18 - Mid occipital L: −42, −72, 34 - Angular gyrus R: 48, −70, 34 - Precuneus R: 6, −56, 18 - Mid occipital R: 24, −92, 8 - Sup occipital R: 14, −94, 22 - Mid cingulum L: −6, −34, 38 - Mid cingulum R: 2, −36, 42 - Medial OFC L: −6, 50, −8 - Calcarine R: 8, −82, 8 - Accumbens R: 10, 6, −8 - Putamen R: 22, 8, −8 - Lingual L: −10, −74, −4 - Putamen L: −16, 2, −10 - Frontal superior L: −18, 30, 52 - Temporal inferior L: −52, −48, −8 - Frontal inf orb L: −36, 36, −12 - Mid OFC L: −42, 48, 0 - Cerebellum 9 L: −4, −52, −44 - Cerebellum crus1 L: −42, −68, −32 - Thalamus R: 4, −12, −2  ROI interaction peaks: - Left NAcc (group x social feedback x treatment): −8, 10, −10 (Z = 3.40) - Left NAcc (group x social target x treatment): −8, 8, −10 (Z = 4.02) - Left NAcc (brain–behavior, RD correlation): −12, 12, −6 (Z = 3.27)
- **analysis_type:** both (whole-brain at p < .05 cluster-corrected, p < .001 voxel level; ROI analysis of NAcc and amygdala at p < .05 FWE-corrected for ROI)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 39 (24 HC, 15 ASD); all male; aged 18–26 years. Originally randomized: N = 60 (35 HC, 25 ASD); 21 excluded for various reasons (dropout, brain abnormality, technical problems, guessing treatment, poor performance, medication).
- **population_category:** mixed
- **population_age_range:** 18–26
- **ecological_validity:** Low — laboratory-based probabilistic categorization task with artificial stimuli (fractal patterns) and video-recorded social feedback (pre-recorded faces); no real social interaction. No fully social condition (social target + social feedback) was included due to time constraints. Only male, high-functioning ASD with normal language and no psychotropic medication, limiting generalizability.
- **eligibility_flag:** 
- **concerns:** - Only 1 model tested (Q-learning); no model comparison or alternative models. $\beta$ was fixed rather than estimated, reducing model flexibility. - Small sample size, especially ASD group (n=15). - No parameter recovery or model recovery reported. - Mean fitted $\alpha$ values not reported. - No fully social condition (SS: social target + social feedback) due to time constraints. - All male, high-functioning ASD only — limited generalizability. - Dosage was 20 IU rather than intended 26 IU due to procedural error. - Multiple comparisons across three task conditions, two treatment conditions, two groups, and three intervals.
- **limitations_reported:** Average severity of deficits in reciprocal social behavior was moderate; all participants were male and very high functioning with respect to cognitive abilities — findings only apply to this subgroup; generalization to the broader ASD population should be tested in future studies; replication with larger samples including women and individuals with lower functioning ASD warranted; focus on children and adolescents needed; more research into comorbid conditions necessary (e.g., ADHD, social anxiety); future studies should include fully social conditions (social feedback and target); no fully social condition included due to time constraints.
- **limitations_categorized:** limited generalizability; sample size; gender bias (male only); restricted clinical severity; task simplicity (no fully social condition); no developmental range; comorbidity not addressed.
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 3.5
- **wc_total:** 3.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM — $\beta$ described as fixed but exact value not reported; mean fitted $\alpha$ values not reported - social_param: HIGH — explicitly no social parameter in the model; social modulation tested at task-condition level only - winning_model: MEDIUM — only model tested, not "winning" via comparison
- **cannot_find:** - Mean fitted $\alpha$ values (not reported in main text or supplement) - Exact fixed value of $\beta$ (not reported) - Formula for Q-learning (equations referenced in supplement but extracted text shows placeholders — "where rt reflects..." without visible equations due to text extraction limitations)
- **other_notes:** - The computational model is relatively simple — standard Q-learning with one free parameter used primarily to generate trial-by-trial RPE regressors for the fMRI analysis, rather than as a modeling exercise in its own right. - The study is a randomized controlled trial (crossover design) primarily testing pharmacological (oxytocin) modulation of social reinforcement learning in ASD. - The supplement contains a full whole-brain activation table (Table S2) with MNI coordinates. - No amygdala effects were found for any contrast of interest. - The paper focuses on the interaction between oxytocin and social context (feedback type / target type) rather than individual differences in learning rate.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pharma_oxytocin
- pop_autism
- pop_healthy_adults
- rr_pharma_oxytocin
- rr_pop_autism
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = partly
- spec_depth = general
- spec_locus = source+target
- spec_neural = shared
- spec_source = partly
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_temperature
- tax_popclass_clinical
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_social_nonsocial_comparison
- tax_topic_social_approval_reward
