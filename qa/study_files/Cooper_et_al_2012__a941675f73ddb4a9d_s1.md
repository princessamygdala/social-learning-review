# Cooper et al. (2012)

- **study_id:** `a941675f73ddb4a9d_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Cooper, J. C., Dunne, S., Furey, T., & O'Doherty, J. P. (2012). Human dorsal striatum encodes prediction errors during observational learning of instrumental actions. *Journal of Cognitive Neuroscience*, *24*(1), 106–118. https://doi.org/10.1162/jocn_a_00114
- **citation_short:** Cooper et al. (2012)
- **doi:** 10.1162/jocn_a_00114
- **publication_type:** peer-reviewed journal
- **year:** 2012.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Division of the Humanities and Social Sciences, California Institute of; College Dublin student population; lable in PMC 2013 February 20; Institute of Technology; College Dublin; ETHODS; emails: jcooper@caltech.edu
- **code_url:** 

## Computational level
- **study_focus:** Observational learning — whether dorsal striatum encodes reward prediction errors during observational instrumental learning (learning action-reward associations by watching another person) as it does during experiential instrumental learning.
- **study_focus_short:** Observational learning
- **learning_mode_description:** - Learning mode: Learning instrumental action-reward associations by observing another person's choices and outcomes, and also by direct experience.   - Learning from:     - Source type (social): other (confederate)       - Observed condition: participant watches confederate perform instrumental task     - Source content (social): outcome (reward/neutral outcome delivered to confederate)   - Learning about:     - Target type (non-social): world (slot machine action-reward contingencies)     - Target content (non-social): action/policy (which arm of slot machine yields higher reward probability)  Note: The experiential condition involves learning from one's own outcomes (source type: non-social, self; source content: non-social, outcome) about the same target. The key novel finding concerns the observational condition.
- **task_description:** Participants were scanned with fMRI while observing a confederate via live video performing an instrumental two-armed slot machine task for liquid juice rewards (Observed condition) and while performing a similar instrumental task themselves for their own rewards (Experienced condition). Test trials assessed observational learning by having participants choose on the confederate's slot machines without feedback.
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant), single observed agent (confederate outside scanner); non-interactive — participant observes but does not interact with confederate.
- **n_players:** single agent (1)
- **partner_type:** confederate
- **stimuli:** Two-armed slot machine cues (color-coded by condition), liquid juice rewards (blackcurrant) vs. tasteless neutral solution, visual outcome signals (green/gray squares), live video feed of confederate.
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Right dorsal caudate positively correlated with observational instrumental prediction errors (Z = 3.94, p < .05 corrected for dorsal striatal volume) - Right nucleus accumbens positively correlated with experiential instrumental prediction errors (Z = 3.19, p < .05 corrected for striatal volume) - Left dorsal putamen positively correlated with experiential instrumental prediction errors (Z = 3.87, p = .055 corrected) - Bayesian model comparison: 99.67% exceedance probability that dorsal caudate activation reflected RL prediction errors vs. static outcome response during observational instrumental trials - Dorsal caudate showed main effect of instrumental > noninstrumental (F(1, 63) = 12.65, p < .005) but no experience/observation main effect or interaction - Left ventral putamen correlated with experiential noninstrumental prediction errors (Z = 3.24, p < .05 corrected) - No ventral striatal activation for observational prediction errors in either instrumental or noninstrumental conditions - RL model fit Experienced instrumental choices better than baseline (BIC = 968.26 vs. 1039.72) and Test instrumental choices better than baseline (BIC = 508.58 vs. 512.93)
- **effect_size:** - Observational instrumental PE in R dorsal caudate: Z = 3.94 (20 voxels) - Experiential instrumental PE in R NAcc: Z = 3.19 (16 voxels) - Experiential instrumental PE in L dorsal putamen: Z = 3.87 (14 voxels) - Experiential noninstrumental PE in L ventral putamen: Z = 3.24 (13 voxels) - Bayesian exceedance probability for RL vs. baseline in dorsal caudate (observed instrumental): 99.67% - Cue liking ANOVA: F(7, 98) = 15.25, p < .001 - Reward vs. neutral outcome liking: t(14) = 5.29, p < .001
- **learning_from:** Other (confederate); observed confederate's instrumental choices and reward outcomes on slot machine task. Also self (own outcomes in experiential condition).
- **learning_about:** World; action-reward contingencies (which slot machine arm yields higher reward probability).  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** SARSA RL model for instrumental trials (α_exp = 0.38, α_obs = 0.26, β fitted); Rescorla-Wagner for noninstrumental trials (α_exp = 0.18, α_obs = 0.53, β fitted). Group-level pooled learning rates. V(a) ← V(a) + α(O_t - V(a)); softmax action selection for instrumental trials.
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "SARSA RL model", "family": "SARSA/Rescorla-Wagner", "n_params": 2, "metric": "BIC"},   {"name": "Baseline (equal probabilities)", "family": "Null", "n_params": 0, "metric": "BIC"},   {"name": "Saturated model", "family": "Saturated", "n_params": "one per trial", "metric": "BIC"},   {"name": "Last-action imitation", "family": "Heuristic", "n_params": 1, "metric": "BIC"},   {"name": "Last-outcome imitation", "family": "Heuristic", "n_params": 1, "metric": "BIC"} ]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate, experiential instrumental) = 0.38- α (learning rate, observational instrumental) = 0.26- α (learning rate, experiential noninstrumental) = 0.18- α (learning rate, observational noninstrumental) = 0.53(note: model fit was nonsignificant for this condition) - β (softmax inverse temperature / choice stochasticity) — fitted but value not reported- V(a) — action value, updated via δ_t = O_t - V(a); V(a) ← V(a) + α × δ_t - Initial values set to 0 for all actions
- **social_param:** Separate observational learning rate (α_obs) — learning rate applied when computing prediction errors from observed (confederate's) outcomes rather than directly experienced outcomes. α_obs = 0.26 for instrumental, 0.53 for noninstrumental.
- **social_param_name:** Separate observational learning rate
- **social_param_value:** 0.26
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion); also Bayesian model selection (exceedance probability) for neural model comparison.
- **how_model_fit:** group-level-fit (single pooled learning rate for entire group, MLE)
- **data_type_fit_to:** choice behavior (instrumental trials); response times (noninstrumental trials)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — trial-by-trial prediction errors from RL model used as parametric modulators at outcome onset; chosen values as parametric modulators at cue onset.
- **contrast:** - Observed instrumental prediction error > baseline (dorsal caudate: Z = 3.94) - Experienced instrumental prediction error > baseline (NAcc: Z = 3.19; dorsal putamen: Z = 3.87) - Experienced noninstrumental prediction error > baseline (ventral putamen: Z = 3.24) - 2 × 2 ANOVA on dorsal caudate betas: instrumental > noninstrumental (F(1,63) = 12.65, p < .005) - Bayesian model comparison: RL PE model vs. static outcome model (exceedance prob. = 99.67%)
- **key_regions:** Observational instrumental prediction errors in right dorsal caudate; experiential instrumental prediction errors in right nucleus accumbens and left dorsal putamen; experiential noninstrumental prediction errors in left ventral putamen. No ventral striatal activation for observational prediction errors.
- **key_regions_abbrev:** VS, NAcc, caudate, putamen, ACC
- **coordinates_peak:** - Right dorsal caudate (observed instrumental PE): 21, 17, 7 - Left dorsal caudate (observed instrumental PE, subthreshold): -15, 14, 7 - Right nucleus accumbens (experienced instrumental PE): 9, 11, -4 - Left dorsal putamen (experienced instrumental PE): -24, -1, 10 - Left ventral putamen (experienced noninstrumental PE): -21, 5, -4
- **analysis_type:** ROI (dorsal and ventral striatal ROIs, hand-drawn, divided at z = 0; also whole-brain at p < .001 with no significant results) — both  ---  ## QUALITY
- **analysis_type_clean:** ROI
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 16 (10 women, 6 men; M age = 22.19 years; 19 scanned, 1 excluded for head motion, 2 excluded for no evidence of learning)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate ecological constraints. Confederate was a real person viewed via live video, enhancing social presence. However, task used abstract slot machines with liquid juice rewards in a scanner environment. Confederate's responses were actually computer-controlled (unknown to participant). Non-interactive observation only.
- **eligibility_flag:** 
- **concerns:** Small sample size (N = 16). Group-level pooled learning rate rather than individual-level parameter estimation limits ability to examine individual differences. The confederate's choices were computer-controlled (not genuine), which participants were not told. The noninstrumental observational condition showed no significant behavioral learning, limiting interpretability of that condition. β parameter value not reported. No parameter recovery or model recovery analyses.
- **limitations_reported:** Participants did not exhibit strong behavioral evidence of learning in the noninstrumental observed condition; the high observed noninstrumental learning rate should be interpreted with caution; the lack of relationship between learning performance and dorsal caudate activation should be qualified by relatively low variation in learning performance after screening out nonlearners; the ventral striatal null finding for observational PE may relate to differences in sensory involvement and subjective reward between experienced and observed outcomes; task variations (liquid vs. monetary rewards, separate vs. shared cue sets) may affect observational learning computations; the study did not find prediction error activation in dorsomedial PFC, possibly due to incentive domain, task design, or task demands.
- **limitations_categorized:** limited ecological validity; sample size; no parameter recovery; task simplicity; limited generalizability; condition-specific learning failure; group-level parameter estimation
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - β (softmax parameter): value not reported in paper — LOW confidence on exact fitted value - α_obs noninstrumental = 0.53: authors note model fit was nonsignificant, interpret with caution — MEDIUM - Supplement: referenced at external URL (www.odohertylab.org/supplementary/), not available as local file; only contains Figure S1 (RT distributions) — MEDIUM
- **cannot_find:** - Exact fitted β (inverse temperature) value — not reported - Full model equations in formal notation (described in text but no separate equation display preserved in .txt conversion) - Supplement not available locally (hosted externally); likely contains only Figure S1
- **other_notes:** The paper is from 2012 (relatively early model-based fMRI study of observational learning). It focuses on dorsal vs. ventral striatum dissociation for instrumental vs. noninstrumental learning across experienced and observed conditions. The SARSA model is standard model-free RL with action selection; the Rescorla-Wagner variant is used for noninstrumental (no-choice) trials. The confederate was actually computer-controlled, creating a deception element. The study uses a within-subjects 2x2 design (experienced/observed x instrumental/noninstrumental). No supplement file found locally; paper references supplementary Figure S1 at an external URL.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = partly
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = imitation_emulation
- tax_rr_topic_imitation_emulation
- tax_topic_imitation_emulation
