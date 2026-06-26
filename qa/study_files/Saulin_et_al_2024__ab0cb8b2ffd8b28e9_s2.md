# Saulin et al. (2024)

- **study_id:** `ab0cb8b2ffd8b28e9_s2`
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
- **study_focus:** Reciprocity learning / social closeness learning — investigating whether reciprocity-related social closeness (learned from partner helping behavior) shows the same resistance to extinction as empathy-related closeness.
- **study_focus_short:** Reciprocity learning / social closeness learning
- **learning_mode_description:** - Learning mode: Learning from another person's helping decisions about one's own felt closeness to that person   - Learning from:     - Source type (social): other (stranger/confederate)     - Source content (social): action/policy (decision to help or not help)   - Learning about:     - Target type (social): other (stranger/confederate)     - Target content (social): state (felt social closeness to the other)
- **task_description:** Participants observed whether a partner ostensibly decided to sacrifice monetary reward to spare them from pain (help) or not, across acquisition (80% help) and extinction (20% help) blocks, rating emotion and closeness each trial.
- **task_paradigm:** Empathy / pain task
- **players:** Single agent (participant), dyadic (female stranger confederate as helper); within-subject treatment vs control conditions.
- **n_players:** dyadic (2)
- **partner_type:** confederate
- **stimuli:** Visual display of partner's ostensible decision screen and help/no-help outcome, continuous slider scales for emotion and closeness ratings.
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Reciprocity-related social closeness increased in acquisition but decayed in extinction (significant 3-way interaction condition x trial number x block: chi2=120.70, p<0.001) - Treatment acquisition slope: beta=0.02, 95% CI=[0.01, 0.03]; treatment extinction slope: beta=-0.05, 95% CI=[-0.06, -0.04] - Basic model and individual calibration model were equally likely to explain data (basic EP=0.54, individual calibration EP=0.38; basic EF=0.40, calibration EF=0.36) - No recalibration advantage — reciprocity-related closeness does not resist extinction
- **effect_size:** Condition x block interaction: beta=-1.130, SE=0.048; condition x trial number x block: beta=-0.530, SE=0.048
- **learning_from:** Other's helping behavior (social; other's action/decision)
- **learning_about:** Own felt social closeness to the other person (social; affective state toward other)
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Basic Rescorla-Wagner model (1 learning rate alpha) — note: no clear single winner; basic model and individual calibration model were comparably supported.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Same 3 models as empathy studies (basic, differential, individual calibration)
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate): single learning rate
- **social_param:** N/A — no social-specific parameter distinguished the winning model for reciprocity
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** LAME / Bayesian model selection (EP, EF)
- **how_model_fit:** individual-level-fit
- **data_type_fit_to:** self-report ratings (trial-by-trial social closeness ratings)

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging)
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=27 (all female); age 23.07 (SD=3.35); 1 excluded from original recruitment
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate. Same lab-based paradigm with ostensible helping decisions by confederate; no real social interaction.
- **eligibility_flag:** 
- **concerns:** Same as Study 1 regarding female-only sample and lab-based paradigm; no clear winning model (basic and calibration models comparably supported); no neuroimaging.
- **limitations_reported:** The present findings may not directly translate to male participants. Future studies are required to show if our results generalize to male participants"; "for reciprocity, different parameters may be optimal with respect to the formation and stability of social closeness. That said, future studies should test the longevity of reciprocity-related social closeness using a paradigm optimized for reciprocity.
- **limitations_categorized:** Limited generalizability (female-only sample); task simplicity
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
- **ctx_joint_setting:** yes

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
- spec_depth = general
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_domain_F_affective_moral
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = reciprocity
- tax_rr_secondary_topic = empathy_vicarious
- tax_rr_topic_empathy_vicarious
- tax_rr_topic_reciprocity
- tax_topic_empathy_vicarious
- tax_topic_reciprocity
