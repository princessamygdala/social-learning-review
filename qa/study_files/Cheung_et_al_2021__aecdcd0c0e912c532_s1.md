# Cheung et al. (2021)

- **study_id:** `aecdcd0c0e912c532_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Cheung, R. W., Hartley, C., & Monaghan, P. (2021). Caregivers use gesture contingently to support word learning. *Developmental Science*, *24*(4), e13098. https://doi.org/10.1111/desc.13098
- **citation_short:** Cheung et al. (2021)
- **doi:** 10.1111/desc.13098
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Psychology
- **affiliations_raw:** etherlands Children learn words in environments where there is considerable variability, both; mits use, distribution and reproduction in any medium,; Department of cues to support word- referent mappings; University of Amsterdam, Amsterdam,; University, Lancaster, LA1 4YF, UK; University, Lancaster, UK; College, Lancaster; mith & Yu, 2008); emails: r.w.cheung@lancaster.ac.uk
- **code_url:** http://osf.io/6frcw/

## Computational level
- **study_focus:** Word learning under referential uncertainty; how caregiver gestural cues are adapted to environmental ambiguity to support cross-situational word-referent mapping.
- **study_focus_short:** Word learning under referential uncertainty
- **learning_mode_description:** - Learning mode: Learning novel word-object mappings from caregiver gestural and verbal cues under varying referential uncertainty   - Learning from:     - Source type (social): other (caregiver)     - Source content (social): action/policy (gestural cues, verbal labels)   - Learning about:     - Target type (non-social): world (novel objects)     - Target content (non-social): stimulus (word-object mappings)
- **task_description:** Caregiver-child dyads (children aged 18-24 months) participated in a word-learning task where caregivers taught three novel word-object pairs under conditions of varying referential uncertainty (1, 2, or 6 objects present). Children were then tested on their learning of the word-object mappings in a 3-alternative forced choice test.
- **task_paradigm:** Pedagogical learning
- **players:** Multi-agent (caregiver-child dyad), asymmetric (caregiver teaches, child learns)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Novel objects (9 differently shaped/colored items), novel words (darg, noop, terb), visual displays with 1/2/6 objects
- **method:** behavioural
- **method_full:** Behavioural + computational modelling
- **main_result:** - Computational model: Gesture cue had stronger facilitative effect on learning under referential uncertainty (2- and 6-object conditions) vs. no uncertainty (1-object); interaction of objects x gesture on training time (chi-squared(2) = 14.23, p < .001) - Computational model: Two-object condition yielded highest test accuracy, suggesting some referential ambiguity benefits learning (one vs. two objects: z = 16.20, p < .001) - Behavioural: Caregivers used more deictic gestures in 2-object (t(90.24) = 2.32, p = .023) and 6-object (t(91.79) = 3.08, p = .003) conditions vs. 1-object condition - Behavioural: Children performed more accurately in 2-object than 1-object condition (Wald = 4.36, p = .037) - Caregiver deictic gesture did not predict child test accuracy after controlling for condition (Wald = 0.10, p = .749)
- **effect_size:** LOW confidence — No standardized effect sizes (d, eta-squared, r) reported; only unstandardized estimates and test statistics available
- **learning_from:** Other (caregiver); gestural cues and verbal labels during training
- **learning_about:** World; novel word-object mappings  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Multimodal Integration Model (MIM) — neural network with backpropagation through time; 80-unit auditory input, 80-unit visual input, 100-unit integrative layer (self-connected), 100-unit semantic output; learning rate = 0.01; gesture implemented as doubling activation of target object location.
- **model_family:** Connectionist (SUSTAIN/ALCOVE)
- **model_class:** Other
- **all_models_tested:** Only one computational model tested (the MIM). Statistical models (LME, GEE) were used for analysis but are not competing computational models of learning. No formal model comparison between alternative learning architectures was performed.
- **model_mb_mf:** N/A (not RL)
- **model_params:** - Learning rate: 0.01 - Initial weights: randomised in range [-0.1, 0.1] - Gesture cue: doubling of target object location activation (varied at 0%, 33%, 67%, 100% availability) - Number of objects: 1, 2, or 6 - Training: 100,000 trials maximum; 100 word-object mappings - 5 time steps per trial - Architecture: 80 auditory input units, 80 visual input units, 100 integrative units (self-connected), 100 semantic output units
- **social_param:** MEDIUM confidence — gesture cue availability is the social parameter but it is implemented as a simple attentional modulation, not a social inference parameter  ### CANNOT FIND - Standardized effect sizes (d, eta-squared, r-squared) - Formal model comparison metrics (BIC, AIC, etc.) between competing computational models - No supplement was found for this paper  ### OTHER NOTES This paper sits at the boundary of the review's inclusion criteria. The computational model (MIM) is a connectionist neural network for cross-situational word learning, not a model of social learning per se. The social element is that learning occurs from caregiver cues (gesture), but the model represents gesture only as enhanced visual activation, not as a social signal requiring mentalizing or social inference. Th
- **social_param_name:** MEDIUM confidence
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** No model comparison between alternative computational models. Log-likelihood ratio tests used for nested LME model building (statistical, not computational model comparison).
- **how_model_fit:** simulate-and-compare (model simulations compared qualitatively to behavioural results; no parameter fitting to individual participants)
- **data_type_fit_to:** The computational model was not fit to behavioural data; it was used to generate predictions that were then tested behaviourally. Behavioural data: choice behavior (3AFC accuracy) and caregiver gesture counts.  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 47 caregiver-child dyads completed training (M age = 20.5 months, SD = 1.7; 27 male); N = 27 dyads completed testing (M age = 20.8 months, SD = 1.6; 13 male). Computational model: 120 simulation runs (10 pattern versions x 4 gesture conditions x 3 object conditions).
- **population_category:** healthy adults
- **population_age_range:** 18–24
- **ecological_validity:** Moderate. Caregivers were instructed to teach as if in an everyday setting, but objects were out of reach and could not be handled, reducing naturalistic interaction. Novel objects and words used rather than real-world items. Mid-to-high SES sample limits generalizability. Authors note the constrained setup may have reduced gesture production, particularly by children.
- **eligibility_flag:** MEDIUM confidence — borderline case for inclusion; learning occurs over time and from a social source (caregiver), but computational model does not capture social cognition per se
- **concerns:** - Only one computational model tested; no competing models compared - The MIM is not fit to individual behavioural data; predictions are qualitative comparisons between simulation and experiment - No standardized effect sizes reported (Cohen's d, eta-squared, etc.) - High attrition from training to testing (47 to 27 dyads) - Objects constrained to be out of reach, potentially limiting ecological validity - Mid-to-high SES sample only - No parameter recovery, model recovery, or formal model validation
- **limitations_reported:** Caution should be exercised when generalising our conclusions across different SES backgrounds"; findings may not extend to populations with developmental delay; objects were out of reach, potentially reducing gesture; children may have been at a stage where verbal input is weighted more heavily than gesture input; high dropout from training to testing reduced power for GEE analysis; child fussiness may have been caused by objects being out of reach; did not test incremental increases in referential uncertainty; no eye-tracking to measure attention precisely.
- **limitations_categorized:** Limited generalizability (SES); limited generalizability (developmental populations); limited ecological validity (constrained object interaction); sample size (attrition); task simplicity (no incremental ambiguity conditions); no attention measurement.
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** Partial
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_children
- rr_pop_children
- rr_tax_mod_action_observation
- rr_tax_mod_pedagogical_sampling
- spec_context = social
- spec_depth = general
- spec_locus = source+target+context
- spec_source = social
- tax_domain_H_language_communication
- tax_mod_action_observation
- tax_mod_pedagogical_sampling
- tax_popclass_developmental
- tax_rr_domain = H_language_communication
- tax_rr_domain_H_language_communication
- tax_rr_model_connectionist_category
- tax_rr_model_family = connectionist_category
- tax_rr_param_learning_rate
- tax_rr_primary_topic = language_word_learning
- tax_rr_topic_language_word_learning
- tax_topic_language_word_learning
