# Henco et al. (2020)

- **study_id:** `a80de13010a4dd07a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Henco, L., Brandi, M.-L., Lahnakoski, J. M., Diaconescu, A. O., Mathys, C., & Schilbach, L. (2020). Bayesian modelling captures inter-individual differences in social belief computations in the putamen and insula. *Cortex*, *131*, 221–236. https://doi.org/10.1016/j.cortex.2020.02.024
- **citation_short:** Henco et al. (2020)
- **doi:** 10.1016/j.cortex.2020.02.024
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** InstituteofSystemsNeuroscience,MedicalFaculty,HeinrichHeineUniversityDu¨sseldorf,Du¨sseldorf,Germany; InstituteofNeuroscienceandMedicine,Brain&Behaviour(INM-7),ResearchCentreJu¨lich,Ju¨lich,Germany; CentreforNeuroinformatics,CentreforAddictionandMentalHealth(CAMH),UniversityofToronto,; ethicalapprovaldonotpermitpublicarchivingorpeer-to-peersharingofindividualrawdata; ethereforenotavailabletoanyindividualoutsidetheauthorteamunderanycircumstances; DepartmentofPsychiatry,Ludwig-Maximilians-Universita€t,Munich,Germany; DepartmentofPsychiatry(UPK),UniversityofBasel,Basel,Switzerland; etheneuralmech
- **code_url:** https://osf.io/keztf/

## Computational level
- **study_focus:** Social inference learning — spontaneous (uninstructed) integration of social gaze cues into probabilistic learning and decision-making; individual differences in weighting social vs non-social information.
- **study_focus_short:** Social inference learning
- **learning_mode_description:** - Learning mode: Learning from gaze-based social advice and card colour outcomes to predict winning card probability   - Learning from:     - Source type (social): other (computer-generated face providing gaze cue)       - Source content (social): action/policy (gaze direction as implicit advice)     - Source type (non-social): world       - Source content (non-social): outcome (card colour feedback — correct/incorrect)   - Learning about:     - Target type (social): other (accuracy/reliability of the social cue)       - Target content (social): state (mental state; inferred trustworthiness/accuracy of advice)     - Target type (non-social): world       - Target content (non-social): state (winning probability of card colours)
- **task_description:** Participants chose one of two cards (green or blue) on each of 120 trials to maximise reward, while a computer-generated face shifted its gaze toward one card as implicit advice; winning probabilities of cards and gaze accuracy varied independently across stable and volatile phases.
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant), single social cue source (computer-generated face)
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Computer-generated face with gaze shifts, coloured cards (green/blue), binary feedback (correct/incorrect), reward values (1–9)
- **method:** fMRI
- **method_full:** fMRI (with simultaneous eye-tracking)
- **main_result:** - Bayesian model selection: Three-level HGF with combined response model was the winning model (XP = .937, PXP = .627) - Social weighting parameter ζ correlated with subjective report of gaze use (r_s(48) = .453, p = .001) - ζ correlated with proportion of advice-following trials (r_s(48) = .487, p < .001) - Main effect of task phase on advice-taking (F(2,96) = 57.05, η² = .543) - Main effect of covariate ζ on advice-taking (F(1,48) = 17.54, η² = .268) - Interaction ζ × task phase (F(2,96) = 6.832, η² = .125) - Predicted gaze accuracy (μ̂₁,gaze) during choice: activity in R inferior temporal gyrus (T = 7.9), R putamen/pallidum, bilateral parietal regions - Individual differences in social weighting (subjective report): differential activity in L/R putamen and L/R insula (T_peak = 4.78 L insula; T_peak = 4.65 R rectal gyrus/putamen) - Negative social PE during wrong choices: R insula (T = 5.51), R IFG, R rolandic operculum, L posterior-medial frontal gyrus - Non-social PE (|δ₁,card|) when advice correct: L insula, R middle cingulate cortex, bilateral posterior-medial frontal, ACC - Non-social uncertainty (−σ̂₁,card) during choice: R insula, R rolandic operculum
- **effect_size:** - ζ ~ subjective gaze use: r_s(48) = .453 - ζ ~ gaze helpful: r_s(48) = .292 - ζ ~ advice following: r_s(48) = .487 - Task phase main effect: η² = .543 - ζ main effect on advice-taking: η² = .268 - ζ × task phase interaction: η² = .125 - High vs volatile phase advice-taking: d = 1.04 - Low vs volatile phase: d = 0.41 - Low vs high phase: d = 1.179
- **learning_from:** Other (computer-generated face gaze cue) and world (card colour outcome feedback)
- **learning_about:** Other's advice reliability (social cue accuracy) and world (winning card probability)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** cognitive_only

## Algorithmic level
- **winning_model:** Three-level HGF with parallel social/non-social learning streams + response model combining log-volatility of both gaze and card with participant-specific decision noise β (Model 1: g(t) = β·exp(−½(μ̂₃,card + μ̂₃,gaze)); parameters: ω₂card, ω₂gaze, ω₃card, ω₃gaze, ζ, β)
- **model_family:** HGF
- **model_class:** PE learning / Belief updating
- **all_models_tested:** - {"name": "HGF + Response Model 1 (gaze+card volatility + β)", "family": "HGF", "n_params": 6, "metric": "LME → BMS (XP=.937, PXP=.627, EXP_P=.464)"} - {"name": "HGF + Response Model 2 (gaze volatility + β)", "family": "HGF", "n_params": 5, "metric": "LME → BMS (EXP_P=.098, PXP=.067)"} - {"name": "HGF + Response Model 3 (card volatility + β)", "family": "HGF", "n_params": 5, "metric": "LME → BMS (EXP_P=.077, PXP=.067)"} - {"name": "HGF + Response Model 4 (β only)", "family": "HGF", "n_params": 5, "metric": "LME → BMS (EXP_P=.031, PXP=.067)"} - {"name": "Sutton K1 + Response Model 4", "family": "Sutton K1", "n_params": ~4, "metric": "LME → BMS (EXP_P=.289, PXP=.105)"} - {"name": "Rescorla-Wagner + Response Model 4", "family": "Rescorla-Wagner", "n_params": ~3, "metric": "LME → BMS (EXP_P=.042, PXP=.067)"}
- **model_mb_mf:** Bayesian (hierarchical generative model — not standard RL)
- **model_params:** - ω₂card: evolution rate at level 2 for card (mean = −3.317, SD = 1.765) — governs how fast card contingency beliefs update - ω₂gaze: evolution rate at level 2 for gaze (mean = −3.193, SD = 1.931) — governs how fast gaze contingency beliefs update - ω₃card: evolution rate at level 3 for card volatility (mean = −5.889, SD = 0.326) - ω₃gaze: evolution rate at level 3 for gaze volatility (mean = −6.000, SD = 0.091) - ζ [S]: social cue weighting parameter — relative weight on precision of gaze vs card (mean = 1.402, SD = 0.776) - β: inverse decision temperature / decision noise (mean = −1.343, SD = 2.609)
- **social_param:** ζ (zeta) — weighting parameter representing the relative sensitivity to social (gaze) input compared to non-social (card) input; higher ζ means stronger reliance on social cue precision during decision-making.
- **social_param_name:** ζ
- **social_param_value:** 1.402
- **social_param_sd:** 0.776
- **social_param_range:** 
- **model_comparison_metric:** Log model evidence (LME) subjected to random-effects Bayesian Model Selection (BMS); reports exceedance probability (XP), protected exceedance probability (PXP), and expected posterior probability (EXP_P)
- **how_model_fit:** Individual-level fit (model inversion using quasi-Newton optimization per participant via TAPAS/HGF toolbox v4.1)
- **data_type_fit_to:** Choice behavior (binary: followed gaze advice or not)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors derived from HGF belief trajectories)
- **contrast:** - μ̂₁,gaze (predicted gaze accuracy) during choice > baseline → R ITG, R putamen/pallidum, bilateral parietal - μ̂₁,gaze × subjective gaze use (individual differences) → L/R putamen, L/R insula - μ̂₁,gaze × ζ (computational individual differences) → R inferior occipital gyrus - −σ̂₁,card (negative non-social uncertainty) during choice > baseline → R insula, R rolandic operculum - δ₁,gaze < 0 (negative social PE) during wrong choices > baseline → R insula (T=5.51), R IFG, R rolandic operculum, L posterior-medial frontal - |δ₁,card| (non-social PE) when advice correct > baseline → L insula, R middle cingulate, bilateral posterior-medial frontal, ACC - δ₁,gaze > 0 (positive social PE) during correct choices > baseline → R lingual gyrus, R middle occipital gyrus - Face fixation proportion during choice → R STG, R IPL, R angular gyrus (at p < .005)
- **key_regions:** Social belief accuracy (μ̂₁,gaze) tracked in R putamen and pallidum; individual differences in social weighting correlated with putamen and insula bilaterally; negative social PE in R anterior insula, R IFG, L posterior-medial frontal; non-social PE in bilateral insula, middle cingulate, ACC; non-social uncertainty in R insula; face fixations in R STG/IPL/angular gyrus.
- **key_regions_abbrev:** putamen, ACC, insula, AI, IFG
- **coordinates_peak:** Main text tables: - R Inferior Temporal Gyrus: 52, −60, −6 (μ̂₁,gaze, Table 2) - R Fusiform Gyrus: 40, −72, −18 (μ̂₁,gaze, Table 2) - L SupraMarginal Gyrus: −58, −24, 36 (μ̂₁,gaze, Table 2) - L Inferior Parietal Lobule: −54, −36, 50 (μ̂₁,gaze, Table 2) - R Precentral Gyrus: 58, 10, 30 (μ̂₁,gaze, Table 2) - L Precentral Gyrus: −34, −10, 58 (μ̂₁,gaze, Table 2) - R Superior Frontal Gyrus: 26, −6, 68 (μ̂₁,gaze, Table 2) - R Postcentral Gyrus: 54, −22, 34 (μ̂₁,gaze, Table 2) - R SupraMarginal Gyrus: 62, −16, 28 (μ̂₁,gaze, Table 2) - L Inferior Temporal Gyrus: −50, −68, −8 (μ̂₁,gaze, Table 2) - R Putamen: 18, 14, −10 (μ̂₁,gaze, Table 2) - R Pallidum: 22, 2, 0 (μ̂₁,gaze, Table 2) - R Superior Orbital Gyrus: 18, 22, −18 (μ̂₁,gaze, Table 2) - L Insula Lobe: −26, 12, −16 (μ̂₁,gaze × subjective report, Table 3) - L Putamen: −22, 16, 0 (μ̂₁,gaze × subjective report, Table 3) - R Rectal Gyrus: 20, 18, −12 (μ̂₁,gaze × subjective report, Table 3) - R Putamen: 30, 10, 0 (μ̂₁,gaze × subjective report, Table 3) - R Insula Lobe: 36, 6, 12 (−σ̂₁,card, Table 4) - R Rolandic Operculum: 46, −2, 14 (−σ̂₁,card, Table 4) - R Insula Lobe: 36, 6, 10 (negative social PE, Table 5) - R Rolandic Operculum: 52, 8, 4 (negative social PE, Table 5) - R Inferior Frontal Gyrus (p. Orbitalis): 36, 32, −4 (negative social PE, Table 5) - L Posterior-Medial Frontal Gyrus: 0, 4, 64 (negative social PE, Table 5) - R Lingual Gyrus: 14, −98, −8 (positive social PE, Table 6) - L Insula Lobe: −42, 14, −2 (|δ₁,card| advice correct, Table 7) - R Middle Cingulate Cortex: 8, 20, 38 (|δ₁,card| advice correct, Table 7) - L Posterior-Medial Frontal Gyrus: −4, 12, 48 (|δ₁,card| advice correct, Table 7) - R Inferior Frontal Gyrus (p. Orbitalis): 34, 24, −8 (|δ₁,card| advice correct, Table 7) - R Insula Lobe: 42, 18, −4 (|δ₁,card| advice correct, Table 7)  Supplement coordinates (Table A.4 — μ̂₁,gaze × ζ): - R Inferior Occipital Gyrus: 36, −74, −6 - L Postcentral Gyrus: −18, −32, 68  Supplement (Table A.6 — μ̂₁,gaze × subjective report in full GLM): - R Rectal Gyrus: 20, 16, −12 (subjective report) - R Putamen: 32, 10, 2 (subjective report) - R Insula Lobe: 38, 6, 12 (subjective report) - R Inferior Occipital Gyrus: 36, −74, −6 (ζ) - L Postcentral Gyrus: −18, −32, 68 (ζ)  Supplement (Table A.7 — negative |δ₁,card| all outcomes): - R Caudate Nucleus: 12, 16, −8 - R Amygdala: 26, 0, −14 - L Middle Occipital Gyrus: −32, −90, 18 - L Precuneus: −8, −58, 14 - L Inferior Temporal Gyrus: −36, −42, −16 - R Middle Cingulate Cortex: 4, −40, 32 - L Putamen: −20, 10, −6 - L Mid Orbital Gyrus: −2, 50, −8  Supplement (Table A.5 — face fixation): - R Superior Temporal Gyrus: 48, −46, 20 - R Inferior Parietal Lobule: 44, −62, 58 - R Angular Gyrus: 60, −60, 36
- **analysis_type:** whole-brain (cluster-forming threshold p < .001 uncorrected, cluster-level FWE correction p < .05)  ---  ## QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 50 (25 female; mean age 24.8 ± 5 years, range 18–48; from 55 recruited, 5 excluded); eye-tracking analysis: N = 44 (6 excluded for poor signal); individual differences fMRI analysis with questionnaire: N = 48 (2 missing questionnaire data)
- **population_category:** healthy adults
- **population_age_range:** 18–48
- **ecological_validity:** Task uses uninstructed social cue integration (participants not told to attend to gaze), which is more ecologically valid than explicit advice-following paradigms. However, the social agent is a computer-generated face (not a real person), interaction is non-reciprocal, and the task is a laboratory card-choice paradigm with no real social consequences.
- **eligibility_flag:** 
- **concerns:** - No non-social control condition (e.g., arrow instead of face gaze) — cannot fully dissociate social-specific from general cueing effects on putamen/insula - Computer-generated face as social agent limits ecological validity - Data not publicly shared (ethical restrictions); only code shared - 5 pilot participants had slightly different gaze schedule (volatile phase started 10 trials later) - One participant's GLM lacked CompCor regressors (structural scan lost) - Relatively conservative protected exceedance probability for winning model (PXP = .627, not strongly dominant)
- **limitations_reported:** We did not have a non-social control condition, for instance in form of an arrow pointing to one of the cards. Therefore, we cannot fully determine whether individual differences in social cue weighting associated with insula and putamen activity can be attributed to purely social or more general learning processes"; co-activation of putamen and insula has been found in non-social cueing tasks; social prediction errors did not activate mentalization regions (TPJ, dmPFC), possibly due to uninstructed nature reducing statistical power as subgroup of participants did not use social information.
- **limitations_categorized:** No non-social control condition; limited ecological validity (computer face); limited generalizability (cannot distinguish social vs general cueing); reduced statistical power (subgroup not using social cue); data not publicly available
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - PXP of winning model is .627, which is moderate (MEDIUM confidence that this is clearly the best model) - Sutton K1 and RW model n_params not explicitly stated — inferred from model descriptions (MEDIUM) - Social degree not explicitly rated in paper (extraction-specific field)
- **cannot_find:** - Exact formulas for Sutton K1 and Rescorla-Wagner perceptual models (referenced to prior publications) - Number of parameters for Sutton K1 and RW models (not explicitly listed)
- **other_notes:** This paper uses the same task as Sevgi et al. (2020) — flag for potential overlap but different sample and different research questions (Sevgi focused on autism traits). Code available at https://osf.io/keztf/. The TAPAS/HGF toolbox v4.1 was used. Eye-tracking data were collected simultaneously with fMRI. The paper is part of a special issue "Understanding Others" in Cortex.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = partly
- spec_depth = general
- spec_locus = source+context
- spec_neural = shared
- spec_source = partly
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_HGF
- tax_model_bayesian
- tax_param_precision
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_HGF
- tax_rr_model_family = HGF
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_social_info_use
- tax_social_nonsocial_comparison
- tax_topic_mentalizing
- tax_topic_social_info_use
