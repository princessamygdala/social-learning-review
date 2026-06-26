# Saulin (2022)

- **study_id:** `a461a7be9cf637fef_s1`
- **on_website:** NO — DROPPED (verify below)
- **why_not_on_website:** (no eligibility flag recorded — likely duplicate/superseded version; confirm)

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Saulin, A. C. (2022). *Sustainability of empathy as driver for prosocial behavior and social closeness: insights from computational modelling and functional magnetic resonance imaging* [Doctoral dissertation, Julius-Maximilians-Universität Würzburg].
- **doi:** Not reported for the dissertation itself. Individual published studies: Study 3: https://doi.org/10.1016/j.neuroimage.2021.118827; Study 4: https://doi.org/10.1080/17470919.2022.2115550
- **publication_type:** thesis
- **field_of_study:** Neuroscience
- **affiliations_raw:** ethical standards of the institutional and/or national research committee and with the; lab in Greifswald and went above and beyond to help whenever I needed it; ethodological insights and knowledge have been a true inspiration; laboratory and the fMRI scanner, helped me solve; ether, and Yuqing, our very competent; mitted on: …………………………………………………………; laborators, especially Prof; School of Life Sciences,
- **code_url:** https://github.com/AnneSaulin/complex

## Computational level
- **study_focus:** Empathy-related social closeness learning; formation and sustainability of empathy-driven social closeness via reinforcement learning acquisition-extinction paradigm.
- **study_focus_short:** Empathy-related social closeness learning
- **learning_mode_description:** - Learning mode: Learning from observing another's painful vs. non-painful stimulation about one's own social closeness toward that person   - Learning from:     - Source type (social): other (interaction partner/confederate)     - Source content (social): outcome (observed pain vs. non-pain of other)   - Learning about:     - Target type (social): other (interaction partner)     - Target content (social): state (social closeness / relational evaluation)
- **task_description:** Participants observed a confederate receiving painful stimulation (reinforced trial) or non-painful stimulation (non-reinforced trial) with varying probability across acquisition (80%) and extinction (20%) blocks, and rated their social closeness to that person on a continuous scale after each observation. Confidence: HIGH.
- **task_paradigm:** Dictator game
- **players:** Single agent (participant), dyadic (female confederate partner; 2 confederates for treatment/control). Confidence: HIGH.
- **n_players:** dyadic (2)
- **partner_type:** confederate
- **stimuli:** Colored flash symbols indicating painful vs. non-painful stimulation of partner, continuous rating scales for closeness and emotion. Confidence: HIGH.
- **method:** fMRI (Study 1a), behavioural (Study 1b replication), behavioural (Study 1c control/reciprocity).
- **main_result:** - Empathy-related social closeness increased during acquisition and persisted during extinction (no significant decline; T(45) = -.96, P = .34 for fMRI study) - Winning model: individual recalibration model with EP > 99%, EF = 97% (fMRI study); replicated in behavioral study - Recalibration parameter omega was larger in extinction vs. acquisition block (T(45) = 2.753, P = .009) - Reciprocity-related social closeness declined during extinction (3-way interaction: chi-squared = 120.69, P < .001, beta = -.53) - Neural recalibration linked to bilateral STS/TPJ (left peak: x = -66, y = -26, z = 0; right peak: x = 60, y = -16, z = 10) and left IFG/AI (peak: x = -32, y = 16, z = 18) - Trait empathic concern modulated IFG/AI-closeness link across blocks (4-way interaction: chi-squared = 3.95, P = .047)
- **effect_size:** - Condition main effect on closeness (fMRI): beta = .09, SE = .02, chi-squared = 18.50 - Block main effect (fMRI): beta = .14, SE = .02, chi-squared = 47.41 - Condition x block interaction (fMRI): beta = -.15, SE = .03, chi-squared = 26.87 - Recalibration omega difference acq vs ext: T(45) = 2.753, P = .009, CI = [.054, .345]
- **learning_from:** Other's painful vs. non-painful stimulation (social; observed outcomes for interaction partner).
- **learning_about:** Own social closeness toward the other person (social; relational evaluation/closeness).  ### ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Rescorla-Wagner with individual recalibration parameter (omega): delta_t = |R_t - omega| - V_{t-1}; V_t = V_{t-1} + alpha * delta_t. 2 free parameters: alpha (learning rate), omega (recalibration). EP > 99%, EF = 97%.
- **model_family:** Rescorla-Wagner
- **model_class:** Prediction error learning
- **all_models_tested:** - {"name": "Basic RW model", "family": "Rescorla-Wagner", "n_params": 1, "metric": "LAME/BMS EP"} - {"name": "Differential learning rate model", "family": "Rescorla-Wagner", "n_params": 2, "metric": "LAME/BMS EP"} - {"name": "Individual recalibration model", "family": "Rescorla-Wagner", "n_params": 2, "metric": "LAME/BMS EP"}
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate, bounded 0-1): how strongly recent feedback influences learning. Mean fitted value not reported. - omega [S] (recalibration parameter, bounded 0-1): recalibrates feedback value; larger omega = smaller PE for reinforced trials, larger PE for non-reinforced trials. Larger in extinction than acquisition (T(45) = 2.753, P = .009).
- **social_param:** omega (recalibration parameter) -- recalibrates the value of observed social feedback (pain vs. non-pain), enabling sustained empathy-based closeness even under reduced reinforcement.
- **social_param_name:** omega
- **social_param_value:** 2.753
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Bayesian Model Selection (exceedance probability, expected model frequency) via LAME (Laplace approximation to model evidence) fed into random-effects BMS (mbb-vb-toolbox).
- **how_model_fit:** individual-level-fit (parameters optimized per participant by minimizing negative log posterior probability using fmincon with random starting points)
- **data_type_fit_to:** self-report ratings (trial-by-trial continuous closeness ratings)  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors); parametric modulator coding trial type (pain=1, no-pain=0) at emotion rating, feedback, and closeness phases. Second-level regressions with individual omega values as covariate.
- **contrast:** - PM trial type (pain > no-pain) during emotion rating phase: IFG/AI (x = 38, y = 28, z = -4, P(FWE-cluster) = .033, k = 143), bilateral TPJ (left: x = -52, y = -52, z = 20, T = 6.21; right: x = 62, y = -48, z = 22, T = 4.74) - PM trial type (treatment > control) x omega regression during emotion rating: bilateral STS/TPJ (left: x = -66, y = -26, z = 0, T = 5.62, k = 517; right: x = 60, y = -16, z = 10, T = 6.56, k = 471), left IFG/AI (x = -32, y = 16, z = 18, T = 4.73, k = 269)
- **key_regions:** Recalibration of empathy-related feedback signal linked to bilateral STS/TPJ and left IFG/AI. Pain vs. no-pain processing in right AI/IFG and bilateral TPJ. Trait empathic concern modulated IFG/AI-closeness relationship across acquisition and extinction.
- **coordinates_peak:** - Right AI/IFG (pain > no-pain): 38, 28, -4 - Left TPJ (pain > no-pain): -52, -52, 20 - Right TPJ (pain > no-pain): 62, -48, 22 - Left STS/TPJ (omega x treatment > control): -66, -26, 0 - Right STS/TPJ (omega x treatment > control): 60, -16, 10 - Left IFG/AI (omega x treatment > control): -32, 16, 18 - Right occipital pole (pain > no-pain): 16, -92, 8
- **analysis_type:** whole-brain (P < .001 uncorrected cluster-forming, FWE cluster-corrected)  ### QUALITY

## Quality
- **sample_size:** Study 1a (fMRI): N = 46 (51 recruited, 5 excluded); Study 1b (behavioral replication): N = 27 (28 recruited, 1 excluded); Study 1c (behavioral control/reciprocity): N = 27 (28 recruited, 1 excluded). All female, mean age comparable across studies (F(2,106) = .987, P = .376). Ages 18-35 approximately.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Lab-based paradigm with confederates posing as naive participants; empathy induced via observation of another's pain stimulation (electrical/mechanical); closeness measured via continuous slider rating. Low ecological validity: artificial pain paradigm, strangers only, female-only sample, short time frame. Some ecological relevance in that it models repeated exposure to another's suffering.
- **eligibility_flag:** 
- **concerns:** - Dissertation with 4 studies; only Study 1 clearly involves computational modelling of social learning over time. Studies 2-4 use DDM to decompose decision processes rather than model learning. - Female-only sample limits generalizability. - Confederate design may introduce demand characteristics. - Pain stimulation paradigm is artificial; empathy operationalized narrowly as empathy-for-pain. - Supplement not accessible separately; cannot verify additional coordinate tables or parameter recovery analyses. - Studies 3 and 4 are published separately -- potential double-counting risk. - No parameter recovery or model recovery reported for RL models. - Standard deviation of 0.4 assumed for likelihood function in RL model fitting (not estimated from data).
- **limitations_reported:** Female-only sample limits generalizability to male and gender-mixed contexts; sustainability of reciprocity-related behavior only assessed behaviorally (no fMRI for reciprocity condition); studies focused on empathy towards strangers, findings may not apply to established relationships; non-reinforced trials in reciprocity context may activate negative reciprocity rather than simply not activating positive reciprocity; univariate neuroimaging analyses only, multivariate approaches may be more sensitive.
- **limitations_categorized:** limited generalizability (female-only sample); limited ecological validity; task simplicity; no multivariate neuroimaging analysis; potential confound in reciprocity control condition; no parameter recovery; no model recovery.
- **preregistered:** Not reported
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

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** model_params mean fitted values (not reported for alpha); supplement accessibility (no separate supplement file); parameter recovery (not performed); model recovery (not performed). All MEDIUM-LOW confidence.
- **cannot_find:** Mean fitted values for alpha learning rate in winning model; exact model fit statistics (e.g., mean negative log posterior) per model; individual-level parameter distributions for all models.
- **other_notes:** This is a cumulative dissertation (Dr. rer. nat.) from Julius-Maximilians-Universität Würzburg (2022). The dissertation provides an integrated framework for understanding empathy sustainability via computational modeling and fMRI. The RW recalibration model in Study 1 is the most novel computational contribution. The DDM analyses in Studies 2-4 extend prior work on social decision decomposition but do not model learning dynamics per se. The dissertation's general discussion provides useful synthesis of how different computational mechanisms (recalibration vs. initial bias vs. decision efficiency) map onto different aspects of empathy sustainability.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- _(taxonomy layer not generated for dropped studies)_
