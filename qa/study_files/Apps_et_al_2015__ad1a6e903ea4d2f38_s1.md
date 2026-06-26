# Apps et al. (2015)

- **study_id:** `ad1a6e903ea4d2f38_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Apps, M. A. J., Lesage, E., & Ramnani, N. (2015). Vicarious reinforcement learning signals when instructing others. *The Journal of Neuroscience*, *35*(7), 2904–2913. https://doi.org/10.1523/JNEUROSCI.3669-14.2015
- **citation_short:** Apps et al. (2015)
- **doi:** 10.1523/JNEUROSCI.3669-14.2015
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** UniversityofOxford,OxfordOX12JD,UnitedKingdom,3DepartmentofPsychology,RoyalHolloway,UniversityofLondon,SurreyTW200EX,United; DepartmentofClinicalNeuroscience,UniversityofOxford,OxfordOX19DU,UnitedKingdom,2DepartmentofExperimentalPsychology,; ethescannerwascovered,suchthatthiscuewasshownonlytotheteacherinsidethescanner; ethankAriLin- computationalprinciplesthatitinstantiatesparallelthoseofthe; InstituteonDrugAbuse,NationalInstitutesofHealth,Baltimore,; lableonlinethroughtheJNeurosciAuthorOpenChoiceoption; mitsunrestricteduse,distributionandreproductionin; DepartmentofClinicalNeurosciencesLevel6
- **code_url:** 

## Computational level
- **study_focus:** Observational/vicarious learning during teaching — examining whether the brain of a teacher processes reinforcement learning signals (prediction errors) when monitoring and instructing a student's learning.
- **study_focus_short:** Observational/vicarious learning during teaching
- **learning_mode_description:** - Learning mode: Teacher vicariously tracks a student's associative learning to provide instructive feedback   - Learning from:     - Source type (social): other (student/confederate)       - Source content (social): action/policy (student's response choices)     - Source type (non-social): world       - Source content (non-social): outcome (correct/incorrect association known by teacher)   - Learning about:     - Target type (social): other (student)       - Target content (social): state (mental state; student's prediction/knowledge state)
- **task_description:** Participants (teachers) had pre-learned arbitrary stimulus-response associations and then monitored a student's (confederate's) trial-and-error learning of the same associations inside an fMRI scanner, providing positive or negative feedback on each trial. The student's responses were actually pre-programmed computer-controlled replays of a pilot participant.
- **task_paradigm:** Observational learning task
- **players:** Single agent (teacher/participant in scanner), dyadic (confederate student outside scanner; actually computer-controlled)
- **n_players:** dyadic (2)
- **partner_type:** confederate
- **stimuli:** Abstract colored shape instruction cues (10 cues), four motor response options, pound coin (correct) or crossed-out pound coin (incorrect) feedback images
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - ACCg (anterior cingulate gyrus) activity covaried with the PE parameter from the R-W model at time of student's response (MNI 2, 30, 12; Z = 3.17, p < 0.005 SVC)   - ACCg PE signal was better explained by signed PE than unsigned PE or simple error detection parameter (p < 0.01 uncorrected)   - VmPFC activity covaried with student's predicted value parameter (MNI -14, 32, -10; Z = 5.06, p < 0.05 FDR)   - Right short insular gyrus activity covaried with student's predicted value parameter (MNI 48, -4, -2; Z = 4.08, p < 0.05 FDR)   - Teacher's valuation (actual value) covaried with activity in superior frontal sulcus (MNI -20, 32, 46; Z = 5.06, p < 0.05 FDR) and posterior cingulate cortex (MNI -14, -52, 32; Z = 5.57, p < 0.05 FDR)   - No effect sizes reported as Cohen's d, r, or similar standardized metrics; results reported as Z-statistics and p-values from parametric modulation GLM analyses
- **effect_size:** - Main Results:   - ACCg (anterior cingulate gyrus) activity covaried with the PE parameter from the R-W model at time of student's response (MNI 2, 30, 12; Z = 3.17, p < 0.005 SVC)   - ACCg PE signal was better explained by signed PE than unsigned PE or simple error detection parameter (p < 0.01 uncorrected)   - VmPFC activity covaried with student's predicted value parameter (MNI -14, 32, -10; Z = 5.06, p < 0.05 FDR)   - Right short insular gyrus activity covaried with student's predicted value parameter (MNI 48, -4, -2; Z = 4.08, p < 0.05 FDR)   - Teacher's valuation (actual value) covaried with activity in superior frontal sulcus (MNI -20, 32, 46; Z = 5.06, p < 0.05 FDR) and posterior cingulate cortex (MNI -14, -52, 32; Z = 5.57, p < 0.05 FDR)   - No effect sizes reported as Cohen's d, r, or similar standardized metrics; results reported as Z-statistics and p-values from parametric modulation GLM analyses
- **learning_from:** Other (student's observable responses/actions) and own expert knowledge of correct associations (world). Source: other + world.
- **learning_about:** Other's learning state — student's predictions and prediction errors about stimulus-response associations. Target: other (student's mental state/knowledge).  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** cognitive_only

## Algorithmic level
- **winning_model:** Rescorla-Wagner (1 learning rate alpha; 1 asymptotic value lambda; 1 inverse temperature beta) — fitted to student's behavior, used as parametric regressors in teacher's fMRI analysis
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Rescorla-Wagner with softmax", "family": "Rescorla-Wagner", "n_params": 3, "metric": "maximum likelihood (grid search)"}] - Note: Only one model was tested. The authors explicitly state that model comparison could not be meaningfully applied because all subjects observed the same (computer-controlled) student behavior.
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate): fitted value = 0.95 (range 0–1, step 0.05) - lambda (asymptotic value of correct action): fitted value = 1 (range 0–5, step 0.1; 0 for incorrect response) - beta (inverse temperature/stochasticity): fitted value = 2.3–2.7 (range 0–5, step 0.1; varied across feedback conditions) - Initial associative strength: lambda/4 (set given equiprobability of 4 actions)
- **social_param:** No explicitly designated social parameter. The model was a standard R-W model fitted to the student's behavior; the "social" aspect is that the teacher's brain activity was regressed against the model's PE, predicted value, and actual value parameters — treating the teacher as vicariously computing these signals for the student.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Maximum likelihood (grid search); no formal model comparison conducted (only 1 model tested)
- **how_model_fit:** Individual-level-fit (grid search over parameter space using maximum likelihood on student's choice data given teacher's feedback; however, since student behavior was identical across all teachers, parameter variation only arose from teacher feedback errors)
- **data_type_fit_to:** Choice behavior (student's action selections)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors from R-W model used as first-order parametric modulators in GLM)
- **contrast:** - PE parameter (signed) as parametric modulator of student response event > baseline (ACCg) - Signed PE > unsigned PE (ACCg, p < 0.01 uncorrected) - Signed PE > error detection parameter (ACCg, p < 0.01 uncorrected) - Student predicted value (Va) as parametric modulator > baseline (VmPFC, right insula) - Actual value (lambda) as parametric modulator > baseline (superior frontal sulcus, PCC)
- **key_regions:** Vicarious prediction error in anterior cingulate gyrus (ACCg, areas 24a'/24b'); student's predicted value in vmPFC (BA 32) and right short insular gyrus (putatively area Idg); teacher's valuation (actual value) in superior frontal sulcus (BA 8/9/9-46) and posterior cingulate cortex (BA 23). At reduced threshold: VTA and head of caudate covaried with PE.
- **key_regions_abbrev:** caudate, vmPFC, mPFC, ACC, PCC, insula, SFG, VTA
- **coordinates_peak:** - ACCg (PE): 2, 30, 12 - VmPFC (student predicted value): -14, 32, -10 - Right short insular gyrus (student predicted value): 48, -4, -2 - Superior frontal sulcus (actual value): -20, 32, 46 - Posterior cingulate cortex (actual value): -14, -52, 32 - Outcome event PE (subthreshold): cerebellar lobule VI: -20, -38, 34; VmPFC: 10, 54, 12; hippocampus: 36, -12, -20; left temporal pole: -56, -10, -24 - Individual differences (subthreshold): bilateral superior frontal sulcus: 26, 0, 42 and -34, -2, 40; PCC: -14, -22, 34; intraparietal sulcus: -44, -38, 50
- **analysis_type:** Both (ACCg analyzed with SVC using 80% probability anatomical mask; whole-brain analyses with FDR correction)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 15 (16 scanned, 1 excluded for incomplete session; ages 18–32; 10 female)
- **population_category:** healthy adults
- **population_age_range:** 18–32
- **ecological_validity:** Low-moderate. The student was actually a computer replaying pre-programmed responses, eliminating genuine social interaction. The teaching context (arbitrary stimulus-response associations) is abstract and does not capture the richness of real-world teaching. However, the cover story was maintained (no participants detected the deception).
- **eligibility_flag:** 
- **concerns:** - Very small sample size (N = 15) limits statistical power and generalizability - Only one computational model tested; no model comparison possible due to design (all teachers observed same student behavior) - Student behavior was computer-controlled, not a real interacting partner — limits ecological validity of "teaching" - The R-W model was fit to the student's behavior and then used to examine the teacher's brain; the teacher's own computational process is inferred, not directly modeled - Several key neuroimaging results (VTA, caudate, outcome-event PE regions) reported only at uncorrected thresholds - Individual differences analysis underpowered (N = 15) and reported at uncorrected threshold - Parameters fitted via grid search rather than optimization; potential for imprecise parameter estimates
- **limitations_reported:** Authors acknowledge: the task design was suboptimal for comparing processing of one's own versus others' actions; the study cannot determine whether ACCg PE signals reflect fictive PEs; results on individual differences should be interpreted with caution given the low sample size and uncorrected thresholds; model comparison could not be meaningfully applied to a single subject's data.
- **limitations_categorized:** Task simplicity; limited ecological validity; sample size; no model comparison; suboptimal task design for some contrasts; uncorrected thresholds for secondary analyses
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size: LOW — No standardized effect sizes (Cohen's d, r, etc.) reported; only Z-statistics and p-values from GLM analyses - social_param: MEDIUM — No explicitly designated social parameter; the social aspect is in the application of a standard model to vicarious processing - model_comparison_metric: MEDIUM — Only maximum likelihood reported; no formal model comparison conducted - individual differences results: LOW — Reported at uncorrected threshold with small N
- **cannot_find:** - Standardized effect sizes (d, r, eta-squared, etc.) — not reported in the paper - Supplement not available (no supplement found in papers folder) - Data/code sharing information — not mentioned
- **other_notes:** - This is a single-study paper - The computational model is applied to the student's behavior but the key neuroscience question is about the teacher's brain — an interesting design where the model serves as a lens for interpreting vicarious neural signals - The paper is an early contribution to understanding the neural basis of teaching from a computational reinforcement learning perspective - Supplement not accessible (not found in papers folder); noted but no fields left blank solely due to this — the main text contains sufficient detail for extraction
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_mentalizing_inference
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_neural = dedicated
- spec_source = partly
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_mentalizing_inference
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_social_bonus
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_primary_topic = pedagogical_reasoning
- tax_rr_topic_pedagogical_reasoning
- tax_topic_pedagogical_reasoning
