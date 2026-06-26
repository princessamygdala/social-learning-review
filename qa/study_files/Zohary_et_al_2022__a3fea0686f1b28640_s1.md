# Zohary et al. (2022)

- **study_id:** `a3fea0686f1b28640_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Zohary, E., Harari, D., Ullman, S., Ben-Zion, I., Doron, R., Attias, S., Porat, Y., Sklar, A. Y., & McKyton, A. (2022). Gaze following requires early visual experience. *Proceedings of the National Academy of Sciences*, *119*(20), e2117184119. https://doi.org/10.1073/pnas.2117184119
- **citation_short:** Zohary et al. (2022)
- **doi:** 10.1073/pnas.2117184119
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Psychology
- **affiliations_raw:** University,NewYork,NY;receivedOctober15,2021;acceptedMarch3,2022; mited to humans; macaque monkeys also respond faster to; Ethiopian patients spontaneouslylearntoextract; lability andlikelihoodofhisfutureactions; lable,evenwhensufficientimagereso-; labilityofinternalself-; mitedduetoreduced; ethepaper; emails: udiz@mail.huji.ac.ilorshimon.ullman
- **code_url:** 

## Computational level
- **study_focus:** Gaze following / unsupervised visual learning of gaze direction; examining whether early visual experience is required for acquiring automatic eye gaze following, using computational modeling of developmental learning processes.
- **study_focus_short:** Gaze following / unsupervised visual learning of gaze direction
- **learning_mode_description:** - Learning mode: Unsupervised learning of gaze direction from self-generated internal teaching signals (mover events) during observation of others' object manipulation   - Learning from:     - Source type (social): other (observed actor)     - Source content (social): action/policy (hand-object contact events / mover events; head orientation; eye position)   - Learning about:     - Target type (social): other (observed actor)     - Target content (social): state (mental state; gaze direction / attentional focus)
- **task_description:** Participants (Ethiopian children with late-treated congenital bilateral cataracts, early-treated cataract patients, and controls) performed a gaze-cueing task where they touched a face's nose, then a gaze cue (eye or head shift) appeared, followed 300 ms later by a balloon on either the compatible or incompatible side; participants touched the balloon as quickly as possible and reaction time was measured.
- **task_paradigm:** Gaze-cueing task
- **players:** Multi-group comparison: Single agent (participant), with stimuli depicting single social agent (actor). Groups: late-treated cataract patients (n=15 for cueing; n=9-10 for eye-tracking), early-treated cataract patients (n=11), controls (n=46 for cueing; n=31 for eye-tracking).
- **n_players:** network (5+)
- **partner_type:** human (recorded)
- **stimuli:** Face images (frontal view of actor), eye position shifts, head orientation shifts, balloons as targets, blurred versions of stimuli for controls; natural images of faces and people in action for eye-tracking experiments.
- **method:** behavioural
- **method_full:** behavioural (reaction time gaze-cueing task + eye tracking + computational modeling)
- **main_result:** - Main Results:   - Significant group x experiment interaction in gaze cueing (F[2,137] = 13.1, p < 0.0001)   - Late-treated patients showed head gaze cueing effect (M = 60 ms, t[13] = 4.2) but NO eye gaze cueing effect (M = 1.5 ms, t[14] = 0.2, p = 0.84)   - Controls showed both head (M = 42 ms) and eye (M = 52 ms) gaze cueing effects   - Early-treated showed both head (M = 30 ms) and eye (M = 40 ms) gaze cueing effects   - Computational model: Under extreme blur (0.4 cpd), mover events detectable with >60% precision; gaze direction prediction from head orientation was possible but not from eye position   - Face representations trained under high blur (0.8 cpd) discriminated head orientation (88%) but not eye position (51%, chance level)   - After further training at higher resolution (3.3 cpd), eye position discrimination improved to 72%
- **effect_size:** - Eye cueing: controls vs late-treated t[59] = 7.6; early vs late-treated t[24] = 5.2 - Head cueing effect across groups: controls M = 42 ms; early-treated M = 30 ms; late-treated M = 60 ms - Eye cueing effect: controls M = 52 ms; early-treated M = 40 ms; late-treated M = 1.5 ms - Model head orientation discrimination: 88% (SEM = 3%) at 0.8 cpd - Model eye position discrimination: 51% at 0.8 cpd; 54% at 3.3 cpd (no retraining); 72% at 3.3 cpd (with retraining)
- **learning_from:** Other (observed actor); hand-object contact events (mover events), head orientation, eye position cues. Source: other.
- **learning_about:** Other's gaze direction / attentional focus (where the observed person is looking). Target: other.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Unsupervised self-teaching model (Ullman et al., 2012): mover event detection -> face-gaze direction association via ResNet-50 deep CNN; no RL or parametric cognitive model fitted to human behavioral data.
- **model_family:** No formal model
- **model_class:** Other
- **all_models_tested:** [{"name": "Unsupervised mover-event self-teaching model (Ullman et al. 2012) with ResNet-50", "family": "Deep CNN with self-supervision", "n_params": "~23M (ResNet-50 architecture)", "metric": "Angular error (gaze prediction) / classification accuracy (head/eye discrimination)"}]
- **model_mb_mf:** N/A (not RL)
- **model_params:** No cognitive model parameters fitted to human behavior. The computational model uses: - ResNet-50 architecture parameters (~23M) - Gaussian blur cutoff frequencies: 0.4, 0.8, 1.7, 3.3, 15.7, 17.6 cpd - Mover event detection precision/recall - SVM binary classifier for left/right discrimination - No social parameters in the traditional sense; the "mover event" serves as an internal teaching signal
- **social_param:** The "mover event" — an internal self-teaching signal generated when observing another person's hand making contact with an object, which serves as supervision for learning gaze direction. This is inherently social (requires observing others' actions).
- **social_param_name:** The "mover event"
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Classification accuracy (left/right head/eye orientation discrimination); angular error in gaze direction prediction (degrees)
- **how_model_fit:** simulate-and-compare (model predictions compared qualitatively to behavioral results of patient groups; no formal fitting to human RT data)
- **data_type_fit_to:** N/A — the model was not formally fit to human behavioral data. Model outputs (gaze prediction accuracy, head/eye discrimination) were compared qualitatively to behavioral cueing effects.  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Gaze-cueing experiment: N = 72 (15 late-treated Ethiopian children, age 12.6 +/- 3.7 y; 11 early-treated Israeli children, age 10.1 +/- 3.3 y; 46 controls, age 8.8 +/- 2.3 y). Eye-tracking gazed-object experiment: N = 40 (9 late-treated, 31 controls). Faces/people-in-action eye-tracking: N = 20 (9 late-treated, 11 controls). 3 preoperative patients tested additionally.
- **population_category:** children
- **population_age_range:** 
- **ecological_validity:** Moderate ecological limitations. The gaze-cueing task uses computer-displayed face stimuli with apparent motion gaze shifts rather than live social interaction. The free-viewing eye-tracking task uses static natural images of people in action, which is somewhat more ecologically valid. The computational model uses video sequences of people manipulating objects, a relatively naturalistic input. However, all testing was laboratory-based with screen stimuli.
- **eligibility_flag:** FLAG: This paper does NOT use a computational model in the standard sense for the systematic review. It uses a computer vision deep learning model (ResNet-50) to simulate developmental perceptual learning, not a cognitive/computational model fitted to human behavioral data. There is no formal model-fitting to trial-by-trial behavior, no prediction error learning, no Bayesian updating. The "learning" studied is perceptual/developmental visual learning of gaze cues, not social learning in the sense of updating beliefs or values from social information over trials. The computational model is a vision model, not a social learning model. Additionally, there is no learning over time in the behavioral task itself — the cueing task measures an already-established (or absent) automatic gaze-following response, not learning within the experiment. Recommend flagging as: "computational model is a vision/perception model, not a cognitive model of social learning; no trial-by-trial learning in the behavioral task.
- **concerns:** - The computational model is a deep CNN for visual perception, not a computational model of social learning in the cognitive science sense - No formal model-fitting to human behavioral data; comparison is qualitative - Small and heterogeneous patient samples with variable time since surgery - Sample size limited by rarity of condition; statistical power concerns especially for late-treated group - Selection bias: children with better acuity were preferentially tested - Controls were younger than patient groups - Nystagmus in late-treated patients may affect eye-tracking measures - No trial-by-trial learning occurs in the behavioral paradigm; it measures pre-existing automatic responses
- **limitations_reported:** Our sample size was severely limited because of the rareness of the condition (untreated isolated congenital bilateral cataracts), and our inclusion criteria"; the early-treated group had longer visual experience than the late-treated group so cannot completely rule out that eye gaze following may develop with sufficiently extended visual experience; "It is difficult to distinguish between two alternatives: 1) that the internal guiding mechanism is only available at an early stage in development, or 2) that the internal guiding mechanism still exists, but due to reduced motivation or other factors, it is no longer automatically utilized"; selection process skewed patients' distribution of postoperative acuity toward higher acuity; explicit training procedure for eye gaze direction does not immediately generalize to automatic gaze-following behavior.
- **limitations_categorized:** sample size; limited generalizability; confounding variables (age, visual experience duration); selection bias; ambiguity in mechanism (critical period vs. motivation); limited ecological validity
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** No
- **wc_rule3:** Partial
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Partial
- **wc_rule10:** Yes
- **wc_score:** 3.0
- **wc_total:** 3.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `eligibility_flag`: LOW confidence — this paper uses a computer vision model (ResNet-50) rather than a cognitive computational model of social learning; no trial-by-trial learning in the behavioral paradigm - `model_family`: MEDIUM — categorized as deep CNN / self-supervised learning; this is a vision model, not a standard cognitive model family - `model_class`: MEDIUM — categorized as unsupervised perceptual learning; atypical for systematic review scope - `learning_mode`: MEDIUM — the "learning" is developmental (occurring over months/years of visual experience), not within the experimental task - `study_focus`: MEDIUM — gaze following is social, but the computational approach is vision/perception-focused
- **cannot_find:** - No cognitive model parameters (alpha, beta, etc.) — the model is a deep neural network, not a parametric cognitive model - No trial-by-trial model fitting to behavioral data - No effect sizes in standard format (Cohen's d, r, eta-squared) — only t-statistics, F-statistics, and means reported - No MNI coordinates (no neuroimaging) - No supplement file found to check for additional modeling or statistical details
- **other_notes:** This paper is at the boundary of the review's inclusion criteria. It studies gaze following, which is a social perception skill, and uses a computational model — but the model is a deep learning vision model (ResNet-50 trained on face identification) used to simulate developmental visual learning, not a cognitive/computational model of social learning fitted to human data. The behavioral task measures pre-existing gaze-following capacity, not learning within the experiment. The "learning" relevant to the paper occurs developmentally (over childhood) through unsupervised self-teaching mechanisms, not through trial-by-trial updating. The paper is published in PNAS (2022) and is methodologically rigorous within its domain (developmental vision science and computer vision), but it may not fit the core scope of a systematic review on computational models of social learning. Supplement not found — noted that SI Appendix is referenced extensively in the paper but no separate supplement file was available in the papers folder.  ---  ### SUMMARY ASSESSMENT  This paper by Zohary et al. (2022) examines whether early visual experience is necessary for developing automatic gaze following, using both behavioral experiments with cataract patients and a computational vision model (ResNet-50 with self-supervised mover-event teaching signals). The key finding is that late-treated cataract patients show head-based but not eye-based gaze following, and the computational model replicates this pattern under simulated blur conditions.
- **re_extract_flag:** false (full text was accessible)

## Taxonomy / categorization (active codes only)
- pop_children
- rr_pop_children
- rr_tax_mod_action_observation
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_model_bayesian
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_precision
- tax_popclass_developmental
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = no_model
- tax_rr_model_no_model
- tax_rr_param_learning_rate
- tax_rr_primary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_topic_mentalizing
