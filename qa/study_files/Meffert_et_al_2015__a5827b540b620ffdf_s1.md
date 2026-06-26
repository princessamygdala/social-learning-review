# Meffert et al. (2015)

- **study_id:** `a5827b540b620ffdf_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Meffert, H., Brislin, S. J., White, S. F., & Blair, J. R. (2015). Prediction errors to emotional expressions: the roles of the amygdala in social referencing. Social Cognitive and Affective Neuroscience, 10(4), 537-544.
- **citation_short:** Meffert et al. (2015)
- **doi:** 10.1093/scan/nsu085
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** SectionofAffectiveandCognitiveNeuroscience,NationalInstitutesofHealth,Bethesda,MD20892,and2ClinicalPsychologyProgram,Florida; InstituteofMentalHealth, wereexcludedbecauseoftheirbelowaveragebehavioralperformance; InstitutesofHealthundergrantnumber1-ZIA-MH002860-08; University, Tallahassee, FL32306; etheemotionalexpressionis; Instituteof; ETHODS
- **code_url:** 

## Computational level
- **study_focus:** Social referencing; observational valence learning from emotional expressions
- **study_focus_short:** Social referencing; observational valence learning from emotional expressions
- **learning_mode_description:** - Learning mode: Learning object valence from another person's emotional expression toward that object (social referencing)   - Learning from:     - Source type (social): other (Ekman face actors displaying expressions toward objects)     - Source content (social): reaction (emotional facial expressions: fearful, happy, neutral)   - Learning about:     - Target type (non-social): world (novel objects)     - Target content (non-social): stimulus (object valence — approach/avoid)
- **task_description:** Participants viewed novel objects followed by faces that turned toward the objects and displayed fearful, happy, or neutral expressions probabilistically (75% or 25% emotional); participants judged the gender of the face, then at the end of each run rated whether they would approach or avoid each object.
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant), multi-target (4 Ekman face actors; 8 novel objects across 4 runs)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Novel grey-scale objects (Tarr Lab), Ekman faces with manipulated gaze direction, fearful/happy/neutral expressions, binary approach/avoid rating
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Bilateral amygdala BOLD response positively modulated by PE for both fearful and happy expressions (SVC corrected) - Participants more likely to avoid fear-associated objects than happy-associated objects (t(22)=3.397, p=.003; fear avoidance M=0.63, happy avoidance M=0.34) - PE-modulated left amygdala response for happy expressions correlated with approach selections for happy objects (r=0.514, p=.012) - Left amygdala recruited during rating of happy objects (SVC) - Bilateral fusiform gyrus modulated by PE for both fearful and happy expressions (conjunction) - Striatum not significantly modulated by PE for either expression type - Stronger PE modulation for happy vs fearful expressions in bilateral middle occipital gyrus, lingual gyrus, and right premotor cortex
- **effect_size:** t(22)=3.397, d not reported; r=0.514 (amygdala PE-approach correlation); amygdala SVC clusters: right fear t=3.744, left fear t=3.248, left happy t=5.230/5.169, right happy t=3.374
- **learning_from:** Other (face actors); emotional expressions (fearful/happy/neutral) directed toward objects
- **learning_about:** World (novel objects); object valence (approach/avoid)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** face_expression

## Algorithmic level
- **winning_model:** Rescorla-Wagner (1 α = 0.474, group average; fixed across participants)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Rescorla-Wagner with single learning rate", "family": "Rescorla-Wagner", "n_params": 1, "metric": "R² (correlation of model-based EVs with behavioral approach/avoid ratings)"}]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): 0.474 (group average; computed by iterating 0.001–0.999 and maximizing R² between model EVs and behavioral ratings)
- **social_param:** None explicitly designated as social; the entire model captures learning from social signals (emotional expressions) but no parameter differentiates social from non-social
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** R² (correlation between model-based end-of-run EVs and participant-based end-of-run EVs from approach/avoid ratings)
- **how_model_fit:** params-calculated-independently (learning rate optimized per object per run by maximizing R² between model EVs and behavioral choice proportions, then averaged)
- **data_type_fit_to:** choice behavior (approach/avoid ratings)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors)
- **contrast:** - PE for fearful expressions > baseline (bilateral amygdala SVC; bilateral fusiform; right STS) - PE for happy expressions > baseline (bilateral amygdala SVC; bilateral fusiform; bilateral STS; bilateral premotor; bilateral vlPFC; dmPFC) - PE happy > PE fearful (bilateral middle occipital gyrus; bilateral lingual gyrus; right premotor) - Conjunction PE fear AND PE happy (bilateral fusiform) - EV for fear objects (bilateral middle temporal gyrus) - EV for happy objects (bilateral fusiform gyrus) - EV happy > EV fear (left fusiform; right lingual gyrus) - Happy object rating > baseline (left amygdala SVC)
- **key_regions:** Bilateral amygdala modulated by PE for both fearful and happy expressions; bilateral fusiform gyrus PE-modulated for both expressions; right STS for fear PE; bilateral STS, bilateral vlPFC, dmPFC for happy PE; left amygdala during happy object evaluation.
- **key_regions_abbrev:** mPFC, dmPFC, STS, amygdala, FFA
- **coordinates_peak:** PE for fearful expressions: - Right amygdala (SVC): 25.5, -7.5, -21.5 - Left amygdala (SVC): -22.5, -4.5, -18.5 - Right fusiform gyrus/inferior temporal gyrus (BA 37/19): 49.5, -64.5, -0.5 - Left fusiform gyrus (BA 37): -37.5, -46.5, -15.5 - Left inferior temporal gyrus (BA 37): -49.5, -70.5, 5.5 - Right superior temporal sulcus (BA 22): 52.5, -40.5, 5.5 - Right precentral gyrus (BA 4): 37.5, -16.5, 50.5  PE for happy expressions: - Left amygdala: -28.5, -4.5, -15.5 - Left amygdala: -16.5, -1.5, -9.5 - Right amygdala (SVC): 25.5, -1.5, -18.5 - Left fusiform gyrus/middle occipital gyrus (BA 37/18): -25.5, -79.5, 8.5 - Right fusiform gyrus/middle occipital gyrus (BA 37/18): 49.5, -64.5, 2.5 - Left superior temporal sulcus (BA 21): -52.5, -34.5, -0.5 - Right superior temporal sulcus (BA 41): 58.5, -43.5, 11.5 - Left precentral gyrus (BA 6): -40.5, -4.5, 50.5 - Right precentral gyrus (BA 6): 49.5, 1.5, 32.5 - Right postcentral gyrus (BA 1): 46.5, -16.5, 47.5 - Right inferior frontal gyrus (BA 44): 37.5, 10.5, 26.5 - Left inferior frontal gyrus (BA 44): -40.5, 10.5, 23.5 - Right dorsal medial PFC (BA 24): 7.5, -4.5, 47.5 - Left superior parietal lobe (BA 7): -28.5, -58.5, 47.5 - Right temporal pole (BA 38): 55.5, 4.5, -12.5  PE happy vs fear: - Left middle occipital gyrus/cuneus (BA 18/19): -13.5, -88.5, 8.5 - Right middle occipital gyrus/cuneus (BA 19): 25.5, -82.5, 17.5 - Left lingual gyrus (BA 18): -19.5, -70.5, -9.5 - Left lingual gyrus (BA 19): -7.5, -85.5, -3.5 - Right precentral/postcentral gyrus (BA 3/4): 40.5, -16.5, 56.5  EV for fear objects: - Left middle temporal gyrus (BA 21): -58.5, -43.5, -0.5 - Left middle temporal gyrus (BA 21): -49.5, -28.5, -0.5 - Right middle temporal gyrus (BA 37): 49.5, -61.5, -6.5  EV for happy objects: - Right fusiform gyrus (BA 37): 28.5, -55.5, -9.5 - Left fusiform gyrus (BA 37): -28.5, -52.5, -9.5  Happy object rating: - Left amygdala: -25.5, -4.5, -9.5
- **analysis_type:** both (whole-brain corrected at p<.005 with cluster extent 10 voxels at p<.05 map-wise; plus SVC/ROI for amygdala, caudate, nucleus accumbens)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N=23 (from 30 enrolled; 2 excluded for MRI preprocessing, 5 for below-average behavioral performance; 48% female; mean age 26.91 ± 4.69 years; mean IQ 118.96 ± 10.53)
- **population_category:** healthy adults
- **population_age_range:** M=26.91
- **ecological_validity:** Low-to-moderate; social referencing paradigm simulates naturalistic learning from others' expressions toward objects, but uses static Ekman faces (not real-time social partners), probabilistic rather than contingent feedback, and gender judgment as a cover task. Novel objects lack ecological relevance.
- **eligibility_flag:** 
- **concerns:** Learning rate was not individually fitted — a single group-average α (0.474) was used for all participants. The paper also mentions using α=0.65 based on prior literature for the fMRI model, which contradicts the reported 0.474. Only one model was tested (no model comparison). No formal model fitting procedure (MLE or Bayesian). No parameter recovery, model recovery, or posterior predictive checks. Coordinates are in Talairach space, not MNI. Ventral striatum null result may reflect signal dropout. Small sample (N=23). The association between PE-modulated amygdala activity and behavioral learning was only significant for happy (not fear) objects.
- **limitations_reported:** Learning could not be directly indexed on a trial-by-trial basis; data were modeled using an average learning rate set at 0.65 based on object rating after each run; no association found between fear learning and amygdala PE-modulated BOLD response, possibly reflecting crude avoidance measure, Type II error due to insufficient power, or overall stronger PE modulation for happy than fearful expressions.
- **limitations_categorized:** no trial-by-trial learning measure; fixed group-level learning rate; small sample size; possible Type II error; crude behavioral measure
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 2
- **wc_total:** 2.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params (MEDIUM): paper reports α=0.474 as the optimized group average, but discussion mentions using 0.65 — inconsistency - coordinates_peak (HIGH): coordinates reported in Talairach space, not MNI - social_param (MEDIUM): no explicitly designated social parameter; entire model is applied to social learning context - effect_size (LOW): Cohen's d or standardized effect sizes not reported for most contrasts; only t-values and r-values available
- **cannot_find:** Standardized effect sizes (Cohen's d, η²) for most contrasts; individual-level fitted learning rates; formal model comparison statistics; MNI coordinates (Talairach only); data/code sharing links
- **other_notes:** This study uses a single Rescorla-Wagner model with a group-average learning rate (not individually fitted). The computational modeling is relatively simple — the primary contribution is using model-derived PE and EV as parametric regressors in the fMRI analysis. Coordinates are in Talairach space throughout; conversion to MNI would be needed for the coordinate database. The paper mentions using α=0.65 in the Discussion (citing prior literature) which contradicts the Methods section's α=0.474. No supplement file found.
- **re_extract_flag:** FALSE

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_depth = general
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- tax_domain_B_inference_modelling_others
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = threat_fear
- tax_rr_secondary_topic = emotion_inference
- tax_rr_topic_emotion_inference
- tax_rr_topic_threat_fear
- tax_social_nonsocial_comparison
- tax_topic_emotion_inference
- tax_topic_threat_fear
