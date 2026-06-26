# Becker et al. (2019)

- **study_id:** `a0cdccddf2144a383_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Becker, M. P. I., Voegler, R., Peterburs, J., Hofmann, D., Bellebaum, C., & Straube, T. (2019). Reward prediction error signaling during reinforcement learning in social anxiety disorder is altered by social observation. *bioRxiv*. https://doi.org/10.1101/821512
- **citation_short:** Becker et al. (2019)
- **doi:** 10.1101/821512
- **publication_type:** preprint
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Institute of Medical Psychology and Systems Neuroscience, University of Münster, Von-Esmarch-; Department of Biological Psychology, Institute for Experimental Psychology, Heinrich-Heine-; ETHOD: 48 adult participants (24 diagnosed with SAD and 24 age-, gender-, and education-; University, Universitätsstraße 1, 40225 Düsseldorf, Germany; Institute of Medical Psychology and Systems Neurosciences; University of Muenster, Germany; lable under; emails: beckermi@uni-muenster.de
- **code_url:** 

## Computational level
- **study_focus:** Social observation effects on reinforcement learning in social anxiety disorder; how social scrutiny alters prediction error signaling during probabilistic feedback learning - Confidence: HIGH
- **study_focus_short:** Social observation effects on reinforcement learning in social anxiety disorder
- **learning_mode_description:** - Learning mode: Learning from probabilistic monetary feedback (wins/losses) about stimulus-reward associations, with social observation modulating the learning process   - Learning from:     - Source type (non-social): world       - Source content (non-social): outcome (probabilistic monetary feedback — win/loss)   - Learning about:     - Target type (non-social): world       - Target content (non-social): stimulus (stimulus-reward contingencies for Japanese Hiragana character pairs)   - Social modulation: Social observation (being watched via video camera by an evaluator) modulates the learning process but is not the source or target of learning itself - Confidence: HIGH
- **task_description:** Participants completed a probabilistic feedback-learning task (adapted from Frank et al., 2004) in which they chose between pairs of Japanese Hiragana characters and received monetary win/loss feedback (20 Eurocent). They completed the task under two conditions: social observation (video camera with evaluator watching) and a non-social control condition. - Confidence: HIGH
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), no interactive partner; observer is passive (does not provide feedback or interact) - Format: "Single agent (participant), passive observer (evaluator via video camera)" - Confidence: HIGH
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Japanese Hiragana character pairs (AB, CD, EF), symbolic feedback (triangle/circle for win/loss), monetary outcomes (±20 Eurocent) - Confidence: HIGH
- **method:** fMRI
- **method_full:** fMRI - Confidence: HIGH
- **main_result:** - Main Results:   - No group differences in overall learning accuracy (all F < 2.046)   - Significant 3-way interaction of feedback valence x group x condition on transfer of learning (F[1.00, 46.00] = 6.456, p < .05): HC learned better from negative feedback under observation; SAD showed reduced learning from negative feedback under observation   - Learning rates in the observation condition predicted LSAS social anxiety severity (beta = -.257, p < .05), but learning rates in the control condition did not (beta = -.064, p = .67)   - RPE-related activation in DMPFC (Area 9) was elevated in SAD relative to HC, especially under observation (peak: -4, 32, 36; FWE-corrected)   - Lentiform nucleus showed stronger RPE coupling in SAD than HC (peak: 12, 8, -2; FWE-corrected)   - VS showed interaction of RPE and group (peak: -10, 9, -2; FWE-corrected)   - DCM: RPE-modulated connectivity from VS to Area 9 was most pronounced in SAD under observation (Log Bayes Factor = 7.75 favoring RPE magnitude model over valence-only model)   - SAD reported more subjective discomfort about negative feedback under observation (M = 5.88 vs 4.38) and higher arousal (M = 5.08 vs 3.67) - Confidence: HIGH
- **effect_size:** MEDIUM — key neural effect sizes (Cohen's d, eta-squared) not reported; only significance maps and F-statistics for behavioral analyses
- **learning_from:** World; probabilistic monetary feedback (win/loss outcomes on chosen stimulus) - Confidence: HIGH
- **learning_about:** World; stimulus-reward contingencies (which Hiragana character in a pair is more likely to yield a win) - Confidence: HIGH  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Q-learning (single learning rate alpha per pair per condition; 1 inverse temperature beta per condition) - Formula: Q_chosen(t+1) = Q_chosen(t) + alpha * PE(t), where PE(t) = R(t) - Q_chosen(t); choice via softmax with inverse temperature beta - Confidence: HIGH
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** Only one computational model described — a standard Q-learning algorithm (Daw, 2009). No formal model comparison among alternative RL models reported. - [{"name": "Q-learning", "family": "Q-learning/Rescorla-Wagner", "n_params": "alpha per pair per condition + beta per condition (up to 8 total: 6 alpha + 2 beta)", "metric": "N/A — no model comparison"}] - Confidence: HIGH
- **model_mb_mf:** MF - Confidence: HIGH
- **model_params:** cannot_find — mean fitted learning rates and inverse temperatures not reported
- **social_param:** MEDIUM — learning rate under observation not explicitly labeled as social parameter by authors
- **social_param_name:** MEDIUM
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A — no formal comparison among alternative computational models. DCM model comparison used Log Bayes Factor (LBF = 7.75) for RPE-modulated vs. valence-only connectivity models. - Confidence: HIGH
- **how_model_fit:** MEDIUM — fitting procedure not explicitly described (assumed MLE via softmax likelihood)
- **data_type_fit_to:** Choice behavior - Confidence: HIGH  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors) + DCM - GLM with RPE as parametric modulator on feedback events; DCM with PEB for effective connectivity - Confidence: HIGH
- **contrast:** - Main effect of RPE (parametric modulator) across groups and conditions → RL network (NAcc, putamen, GP, vmPFC, amygdala, lateral OFC) - RPE x Group (SAD > HC) → DMPFC Area 9 (peak: -4, 32, 36) - RPE x Group → lentiform nucleus/ventral pallidum (peak: 12, 8, -2) - RPE x Group → VS (peak: -10, 9, -2) - RPE x Observation x Group → Area 9 of DMPFC (SAD showed stronger RPE coupling under observation) - DCM: RPE-modulated effective connectivity VS → Area 9, observation x group interaction - Confidence: HIGH
- **key_regions:** Social observation amplified RPE coupling in DMPFC Area 9 in SAD; lentiform nucleus/ventral pallidum showed stronger RPE coupling in SAD; VS showed RPE x group interaction; DCM revealed RPE-modulated directed connectivity from VS to DMPFC Area 9 preferentially in SAD under observation. - Confidence: HIGH
- **key_regions_abbrev:** mPFC, dmPFC
- **coordinates_peak:** - DMPFC Area 9: -4, 32, 36 - Lentiform nucleus/ventral pallidum: 12, 8, -2 - Ventral striatum: -10, 9, -2 - Confidence: HIGH
- **analysis_type:** ROI (masks from Brainnetome Atlas and Reinforcement Learning Atlas with FWER-correction via PALM permutation testing with TFCE) - Confidence: HIGH  ---  ### QUALITY
- **analysis_type_clean:** ROI
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 48 (24 SAD, 24 HC); SAD: mean age 25.42 +/- 2.78, 14 females; HC: mean age 24.46 +/- 4.17, 16 females. Groups matched on age, gender, education. - Confidence: HIGH
- **population_category:** clinical
- **population_age_range:** M=25.42
- **ecological_validity:** Moderate. The social observation manipulation (video camera with evaluator) creates a meaningful social-evaluative context relevant to SAD, but the probabilistic learning task itself is abstract (Japanese Hiragana characters, monetary feedback) with limited ecological validity for real-world social interactions. - Confidence: HIGH
- **eligibility_flag:** MEDIUM — borderline social learning; social observation modulates non-social RL rather than constituting social learning per se  ### CANNOT_FIND - Mean fitted parameter values for learning rates (alpha) and inverse temperatures (beta) - Explicit description of parameter estimation method (MLE, MAP, or hierarchical Bayesian) - Supplement (no supplement file found for this paper) - Effect sizes for neural contrasts (only FWE-corrected TFCE maps reported) - Whether data or code are publicly shared  ### OTHER NOTES - This is a bioRxiv preprint (posted October 30, 2019). Should check whether a peer-reviewed version has been published. - Almost all participants (all except one) also participated in an EEG study by Voegler et al. (2019) — potential overlap/duplicate data concern for behavioral results. - The DCM analysis (VS to DMPFC connectivity modulated by RPE) is a secondary analysis using effective connectivity, not the primary RL model. - The paper's primary contribution is showing that social observation context alters RPE-related neural signaling in SAD, particularly in DMPFC Area 9, rather than discovering a novel social learning mechanism. - No supplement was found; supplement is referenced in the text (Supplementary Figures 1 and 2) but no separate supplement file is available. Flagging: "Supplement not accessible."  ### RE_EXTRACT_FLAG: false  ---  ### SELF-CRITIQUE CHECK  1. Re-read output: Complete. 2. Eligibility flag is appropriately set — this is borderline social learning (social modulation of non-social RL). The computational modeling criterion is met (Q-learning), human behavioral data is used, and learning occurs over time (360 trials). The social component is contextual (observation) rather than the learning target or source being social. 3. Coordinates confirmed from text: DMPFC Area 9 (-4, 32, 36), lentiform nucleus (12, 8, -2), VS (-10, 9, -2). 4. WC scores are consistent: only 1 model tested → Rule 2 = No, Rule 7 = No. No simulation → Rule 3 = No. No parameter/model recovery → Rules 5, 6 = No. 5. No data fabricated; blank fields flagged in cannot_find.
- **concerns:** - No formal model comparison among alternative RL models (e.g., separate positive/negative learning rates, Bayesian models) - No parameter recovery or model recovery reported - No simulation of model before fitting - Fitted parameter values (learning rates, inverse temperatures) not reported - Preprint (not peer-reviewed as of the version posted Oct 2019) - 2 SAD patients on SSRI medication; 6 receiving psychotherapy - Learning is fundamentally non-social; observation is a contextual modulator - Effect sizes for neural findings not reported beyond significance maps - Confidence: HIGH
- **limitations_reported:** The first limitation is the number of 24 participants in each group"; "the SAD group comprised two subjects currently treated with antidepressive medication (SSRI) as well as six subjects who received psychotherapy"; authors note it is "not entirely clear if this might influence brain activation related to RL" though medication effects were not statistically significant; power calculations based on published studies suggest N=24 per group is sufficient. - Confidence: HIGH
- **limitations_categorized:** Sample size; medication confound; psychotherapy confound - Confidence: HIGH
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 3.0
- **wc_total:** 3.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_anxiety
- pop_healthy_adults
- rr_pop_anxiety
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source
- spec_neural = dedicated
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_topic_social_approval_reward
