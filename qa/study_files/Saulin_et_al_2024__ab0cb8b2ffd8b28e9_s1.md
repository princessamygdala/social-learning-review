# Saulin et al. (2024)

- **study_id:** `ab0cb8b2ffd8b28e9_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Saulin, A., Ting, C.-C., Engelmann, J. B., & Hein, G. (2024). Connected in bad times and in good times: Empathy induces stable social closeness. *The Journal of Neuroscience*, *44*(23), e1108232024. https://doi.org/10.1523/JNEUROSCI.1108-23.2024
- **citation_short:** Saulin et al. (2024)
- **doi:** 10.1523/JNEUROSCI.1108-23.2024
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofPsychiatry,CenterofMentalHealth,PsychosomaticandPsychotherapy,TranslationalSocialNeuroscienceUnit,UniversityHospital; UniversityofAmsterdam,Amsterdam1001,TheNetherlands,and5BehavioralandExperimentalEconomics,TheTinbergenInstitute,; ethathasbeenshowntoinciteempathyisobserv- whether the observed behavioral and computational results are; DepartmentofPsychology,UniversitätHamburg,Hamburg20246,Germany,3CenterforResearchin; ethatthisfeedbackrecalibrationisspecifictolearningofempathy-relatedsocialclose-; UniversityofAmsterdam,Amsterdam1001,TheNetherlands,4AmsterdamBrainand; ethankthestude
- **code_url:** http://mbb-team.github.io/VBA-toolbox/

## Computational level
- **study_focus:** Empathy learning / social closeness learning — investigating how empathy-related social closeness is formed through observing another's pain and whether it resists extinction when pain stimulation decreases.
- **study_focus_short:** Empathy learning / social closeness learning
- **learning_mode_description:** - Learning mode: Learning from observing another person's pain/nonpain about one's own felt closeness to that person   - Learning from:     - Source type (social): other (stranger/confederate)     - Source content (social): outcome (pain vs nonpain stimulation observed)   - Learning about:     - Target type (social): other (stranger/confederate)     - Target content (social): state (felt social closeness to the other)
- **task_description:** Participants observed a stranger (confederate) receive painful or nonpainful stimulation across acquisition (80% pain) and extinction (20% pain) blocks, rating their emotional reaction and felt social closeness to the other person on each trial.
- **task_paradigm:** Empathy / pain task
- **players:** Single agent (participant), dyadic (female stranger confederate as pain recipient); within-subject treatment vs control conditions with two different confederates.
- **n_players:** dyadic (2)
- **partner_type:** confederate
- **stimuli:** Visual flash symbols representing painful vs nonpainful stimulation of partner, continuous slider scales for emotion and closeness ratings.
- **method:** fMRI / behavioural
- **method_full:** fMRI (Study 1), behavioural (Study 2)
- **main_result:** - Empathy-related social closeness increased in acquisition block and resisted extinction (no significant decline from Block 1 to Block 2 in treatment condition; t(45)=-0.96, p=0.344, log(BF)=-1.40 for fMRI study; t(26)=1.29, p=0.208, log(BF)=-0.85 for replication) - Individual calibration model was winning model with EP>99% and EF=97% in fMRI study, replicated in behavioral study (EP=1, EF=0.89) - Recalibration parameter omega was larger in extinction than acquisition block (fMRI: T(45)=2.753, p=0.009, CI=[0.054, 0.345]) - Neural recalibration related to activation in left IFG/aIns (x=-32, y=16, z=18, t(44)=4.73, p=0.001, k=269) and bilateral STS/TPJ (left: x=-66, y=-26, z=0, t(44)=5.62, p<0.001, k=517; right: x=60, y=-16, z=10, t(44)=6.56, p<0.001, k=471) - IFG/aIns beta x trial type interaction on closeness ratings: chi2=5.64, p=0.018, beta=-0.18, SE=0.07 - STS/TPJ beta x trial type interaction on closeness ratings: chi2=6.43, p=0.011, beta=-0.08, SE=0.03
- **effect_size:** See effect sizes inline above. Key: condition effect on closeness beta=0.087, SE=0.020; block effect beta=0.140, SE=0.020; condition x block interaction beta=-0.149, SE=0.030. Trait empathy predicted emotion ratings: beta=0.53, SE=0.15.  ---  ### ALGORITHMIC LEVEL
- **learning_from:** Other's pain/nonpain stimulation (social; observed outcomes for another person)
- **learning_about:** Own felt social closeness to the other person (social; affective state toward other)
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Rescorla-Wagner with individual calibration (recalibration parameter omega; 1 LR alpha, 1 omega) - delta_t = |R_t - omega| - SocialCloseness_{t-1} - SocialCloseness_t = SocialCloseness_{t-1} + alpha x delta_t - R=1 for reinforced (pain), R=0 for nonreinforced (nonpain)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Model Space I: 1. {"name": "Basic model", "family": "Rescorla-Wagner", "n_params": 1, "metric": "LAME/BMS EP"} 2. {"name": "Differential model", "family": "Rescorla-Wagner (dual LR)", "n_params": 2, "metric": "LAME/BMS EP"} 3. {"name": "Individual calibration model", "family": "Rescorla-Wagner + recalibration", "n_params": 2, "metric": "LAME/BMS EP"}  Model Space II (exploratory, winning model from Space I as baseline): 4. {"name": "General recalibration (1 omega)", "family": "RW + recalibration", "n_params": 2, "metric": "LAME/BMS EP"} 5. {"name": "Condition-specific recalibration", "family": "RW + recalibration", "n_params": 3, "metric": "LAME/BMS EP"} 6. {"name": "Block-specific recalibration", "family": "RW + recalibration", "n_params": 3, "metric": "LAME/BMS EP"} 7. {"name": "Condition- and block-specific recalibration", "family": "RW + recalibration", "n_params": 5, "metric": "LAME/BMS EP"}
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate): single learning rate for updating social closeness. Mean fitted values not reported in main text. - omega [S] (recalibration parameter): recalibrates the outcome value of reinforced/nonreinforced trials; larger omega means nonreinforced trials more likely to produce positive PE and sustain closeness. Mean fitted values not reported in main text (median and spread in Extended Data Fig. 3-3, not accessible).
- **social_param:** omega — recalibration parameter that adjusts the subjective value of observing another's pain vs nonpain, enabling sustained social closeness during extinction; captures the extent to which empathy-related feedback signals are recalibrated across learning contexts.
- **social_param_name:** omega
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Laplace approximation to model evidence (LAME) fed into Bayesian model selection (random effects); exceedance probability (EP) and expected model frequency (EF).
- **how_model_fit:** individual-level-fit (parameters optimized per participant using fmincon with nLPP minimization)
- **data_type_fit_to:** self-report ratings (trial-by-trial social closeness ratings on continuous scale)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — trial type parametric modulator + second-level regression with individual omega parameter as covariate
- **contrast:** - PM trial type (pain > nonpain) during emotion rating phase: IFG/aIns, bilateral TPJ - PM trial type during closeness rating phase: dmPFC, ventral striatum, dorsal striatum, IFG - Treatment vs control PM contrast (emotion rating phase): no significant results - Treatment vs control PM contrast (closeness rating phase): lateral PFC, precentral sulcus - Regression of omega on treatment vs control PM (emotion rating phase): left IFG/aIns, bilateral STS/TPJ - Regression of omega on treatment vs control PM (closeness rating phase): precuneus, SMG/AG, IFG - Regression of omega on treatment vs control PM (feedback phase): supramarginal gyrus
- **key_regions:** Empathy-related recalibration of social closeness in left IFG/aIns and bilateral STS/TPJ; pain > nonpain sensitivity in right IFG/aIns and bilateral TPJ; closeness-related pain sensitivity in dmPFC, ventral and dorsal striatum, IFG.
- **key_regions_abbrev:** dStr, striatum, mPFC, dmPFC, TPJ, STS, AI, IFG
- **coordinates_peak:** Emotion rating phase (PM trial type pain > nonpain): - Right IFG/aIns: 38, 28, -4 - Left TPJ: -52, -52, 20 - Right TPJ: 62, -48, 22 - Right occipital pole: 16, -92, 8  Closeness rating phase (PM trial type pain > nonpain): - Right dmPFC: 18, 54, 32 - Right ventral striatum: 8, 12, 4 - Right ventral striatum (2nd cluster): 30, 2, -8 - IFG: 42, 28, -12  Omega regression (emotion rating phase, treatment vs control): - Left IFG/aIns: -32, 16, 18 - Left STS/TPJ: -66, -26, 0 - Right STS/TPJ: 60, -16, 10  Omega regression (closeness rating phase): - Precuneus: -4, -56, 56 - Left SMG/AG: -52, -52, 44 - Left IFG: -38, 40, 0  Omega regression (feedback phase): - Left SMG: -56, -28, 32
- **analysis_type:** whole-brain (FWE cluster-corrected at p<0.05 with cluster-forming threshold p<0.001 uncorrected)  ---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N=107 total recruited (all female); N=46 analyzed for fMRI study; N=27 analyzed for behavioral replication study; N=27 analyzed for reciprocity control study. Ages: fMRI 24.06 (SD=4.52), replication 22.89 (SD=3.36), reciprocity 23.07 (SD=3.35). 7 excluded total (5 fMRI, 1 replication, 1 reciprocity) due to lack of variance in ratings (4), falling asleep (2), technical problems (1).
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate. Lab-based paradigm with confederates acting as pain recipients; social closeness measured via continuous slider scale; pain stimulation was real but the other person's experience was partly ostensible; no real social interaction or ongoing relationship; only female participants and confederates tested.
- **eligibility_flag:** 
- **concerns:** - All female sample limits generalizability to males - Confederate-based paradigm with deception (participants believed stimulation was real for partner) - Mean fitted parameter values for alpha and omega not reported in main text (relegated to Extended Data figures which are not accessible in this extraction) - Same acquisition/extinction parameters used across empathy and reciprocity studies, but authors acknowledge these may not be optimal for reciprocity - Social closeness measured on abstract sliding scale, not naturalistic social behavior
- **limitations_reported:** The present findings may not directly translate to male participants. Future studies are required to show if our results generalize to male participants"; "for reciprocity, different parameters may be optimal with respect to the formation and stability of social closeness. That said, future studies should test the longevity of reciprocity-related social closeness using a paradigm optimized for reciprocity.
- **limitations_categorized:** Limited generalizability (female-only sample); task simplicity (parameters not optimized across conditions); limited ecological validity
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM — parameter mean fitted values not reported in main text, only in Extended Data figures - omega individual values: MEDIUM — distribution shown in Extended Data Fig. 3-3 (not accessible) - effect_size for some neural analyses: HIGH — directly reported with t-values and cluster sizes
- **cannot_find:** - Mean fitted values for alpha and omega parameters (reported only in Extended Data figures not accessible here) - Full model space II Bayesian model comparison results (in Extended Data)
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = empathy_vicarious
- tax_rr_topic_empathy_vicarious
- tax_topic_empathy_vicarious
