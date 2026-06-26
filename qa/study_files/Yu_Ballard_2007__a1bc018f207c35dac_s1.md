# Yu & Ballard (2007)

- **study_id:** `a1bc018f207c35dac_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Yu, C., & Ballard, D. H. (2007). A unified model of early word learning: Integrating statistical and social cues. *Neurocomputing*, *70*(10–12), 2149–2165.
- **citation_short:** Yu & Ballard (2007)
- **doi:** 10.1016/j.neucom.2006.01.034
- **publication_type:** peer-reviewed journal
- **year:** 2007.0
- **field_of_study:** Psychology
- **affiliations_raw:** DepartmentofPsychologicalandBrainSciences,andCognitiveScienceProgram,IndianaUniversity,Bloomington,IN47405,USA; DepartmentofComputerScience,TheUniversityof their environment, and then they associate it with some; DepartmentofComputerScience,UniversityofRochester,Rochester,NY14627,USA; labelsbasedoncross-situationalobservation; labelwiththeirexperienceatthetime; mith[45]arguedthatwordlearning; lableonline25January2007; labelisused; emails: chenyu@indiana.edu, dana@cs.rochester.edu
- **code_url:** 

## Computational level
- **study_focus:** Word learning / cross-situational word-referent mapping with social cues (joint attention and prosody)
- **study_focus_short:** Word learning / cross-situational word-referent mapping with social cues
- **learning_mode_description:** - Learning mode: Learning from cross-situational co-occurrences of words and visual referents, augmented by social cues (joint attention, prosody), to discover word-meaning mappings   - Learning from:     - Source type (social): other (caregiver/mother)     - Source content (social): action/policy (speech, gaze direction, prosodic emphasis)   - Learning about:     - Target type (non-social): world (word-referent mappings)     - Target content (non-social): stimulus (association between lexical labels and visual objects)
- **task_description:** A computational model receives transcribed speech and coded visual context from naturalistic mother-infant toy-play interactions (CHILDES database). The model uses an EM algorithm to estimate word-referent association probabilities across multiple learning situations, with optional weighting by joint-attention and prosodic cues.
- **task_paradigm:** Pedagogical learning
- **players:** N/A -- no human participants; simulated learner applied to two mother-infant dyad recordings (di06 and me03 from CHILDES)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Transcribed speech utterances and coded visual referents (toy objects) from naturalistic mother-infant interaction videos
- **method:** behavioural
- **method_full:** Computational simulation (no behavioral experiment, no neuroimaging)
- **main_result:** - Pure statistical learning: precision = 75%, recall = 58% - Statistical + prosodic cues: precision = 78%, recall = 58% - Statistical + joint-attention cues: precision = 80%, recall = 73% - Statistical + both cues: precision = 83%, recall = 77% - Random baseline: precision = 5.3%, recall = 15.2% - No formal effect sizes (Cohen's d, beta, etc.) reported; results are model accuracy metrics only
- **effect_size:** No standard effect sizes reported (no inferential statistics on human data)
- **learning_from:** Other (caregiver); co-occurring speech and visual referents in naturalistic interaction
- **learning_about:** World; word-referent mappings (which words map to which objects)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** EM algorithm for word-referent association probabilities (based on Brown et al., 1994, machine translation model), with weighted social cue integration (joint attention weight = 3, prosody weight = 3)
- **model_family:** Bayesian
- **model_class:** Other
- **all_models_tested:** 1. Pure statistical EM model (no social cue weighting) -- parameters: association probabilities p(m|w), epsilon constant; metric: precision/recall 2. Statistical EM + prosodic cues (word weighting w_p) -- adds prosodic spotlight weights; metric: precision/recall 3. Statistical EM + joint-attention cues (referent weighting w_v) -- adds attention spotlight weights; metric: precision/recall 4. Statistical EM + both cues (w_p and w_v) -- combined; metric: precision/recall
- **model_mb_mf:** N/A (not RL; statistical association model)
- **model_params:** - p(m_m | w_n): association probability for each word-meaning pair - epsilon: small constant in likelihood function - w_v(j): weight for visual objects (= 3 if attended, 1 otherwise) - w_p(i): weight for words (= 3 if prosodically highlighted, 1 otherwise) - No parameters fit to human data; weights are predetermined
- **social_param:** w_v (joint-attention spotlight weight) [S]; w_p (prosodic spotlight weight) [S] -- both set to 3 for highlighted items, encoding social cues from caregiver
- **social_param_name:** w_v
- **social_param_value:** 3
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Precision and recall of word-referent mapping accuracy (no formal statistical model comparison like BIC/AIC)
- **how_model_fit:** Simulate-and-compare (model run on corpus data; performance evaluated by accuracy of recovered word-referent mappings against ground truth)
- **data_type_fit_to:** N/A -- model not fit to human behavioral data; evaluated against coded ground-truth word-referent mappings  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging)  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N/A for human participants. Model tested on 2 mother-infant interaction video clips from CHILDES (subject di06: 20 months, 336 vocabulary, 281 utterances; subject me03: 20 months, 225 vocabulary, 321 utterances)
- **population_category:** non-human
- **population_age_range:** 
- **ecological_validity:** Uses naturalistic mother-infant interaction data from CHILDES, which is a strength. However, the "learner" is a computational model, not a human participant. The data are limited to two toy-play sessions. The model assumes pre-segmented words and pre-identified objects, which simplifies the real learning problem.
- **eligibility_flag:** 
- **concerns:** - No human behavioral data: the model is not fit to or validated against human learning data - Model weights (w_v = 3, w_p = 3) are predetermined, not empirically derived - Only 2 video clips used; extremely limited data - Assumes perfect word segmentation and object identification (unrealistic for infants) - No statistical tests comparing the four model variants - Published in a computational/engineering journal (Neurocomputing), not a behavioral science journal
- **limitations_reported:** The current unified model does not encode any syntactic properties of the language, which definitely play a significant role in word learning, especially in the later stage; the weighing mechanism to encode social cues in statistical word learning is straightforward and rather simple, which serves as a first step; the study does not investigate the dependencies of cues because the mother is able to use multimodal cues simultaneously
- **limitations_categorized:** Task simplicity; limited ecological validity; no syntactic constraints modeled; simplistic social cue integration; no formal model comparison statistics; no human behavioral validation
- **preregistered:** No
- **wc_rule1:** No
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Partial
- **wc_rule10:** No
- **wc_score:** 1.0
- **wc_total:** 1.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** Human behavioral data; formal effect sizes; preregistration information; model fitting to human responses; neuroimaging data
- **other_notes:** This is a computational modeling paper from the machine learning / computational cognitive science tradition. It proposes a model of how word learning *could* work by integrating statistical and social cues, tested on naturalistic corpus data. It does not collect behavioral data from human participants or fit models to human behavioral responses. It should be **flagged as ineligible** for the systematic review criterion "Uses human behavioral data" -- the model is applied to coded transcripts, not to behavioral measurements from learners.
- **re_extract_flag:** false (full text was accessible and read completely)

## Taxonomy / categorization (active codes only)
- pop_children
- rr_pop_children
- rr_tax_mod_action_observation
- rr_tax_mod_pedagogical_sampling
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- tax_domain_B_inference_modelling_others
- tax_domain_H_language_communication
- tax_mod_action_observation
- tax_mod_pedagogical_sampling
- tax_popclass_developmental
- tax_rr_domain = H_language_communication
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_H_language_communication
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = language_word_learning
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_language_word_learning
- tax_rr_topic_mentalizing
- tax_topic_language_word_learning
- tax_topic_mentalizing
