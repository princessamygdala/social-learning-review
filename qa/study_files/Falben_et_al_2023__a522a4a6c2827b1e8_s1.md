# Falben et al. (2023)

- **study_id:** `a522a4a6c2827b1e8_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Falben, J. K., Golubickis, M., Tsamadi, D., Persson, L. M., & Macrae, C. N. (2023). The power of the unexpected: Prediction errors enhance stereotype-based learning. *Cognition*, *235*, 105386. https://doi.org/10.1016/j.cognition.2023.105386
- **citation_short:** Falben et al. (2023)
- **doi:** 10.1016/j.cognition.2023.105386
- **publication_type:** peer-reviewed journal---
- **year:** 2023.0
- **field_of_study:** Psychology
- **affiliations_raw:** Department of Psychology, University of Warwick, Coventry, CV4 7AL, England, UK; Department of Psychology, University of Warwick, Coventry, England, UK; School of Psychology, University of Aberdeen, Aberdeen, Scotland, UK; mpirical support to this viewpoint, laboratory and field; mit their educational and occu-; lableonline9February2023; mitra Tsamadia, Linn M; lable at ScienceDirect; emails: johanna.falben@warwick.ac.uk
- **code_url:** https://osf.io/9ajcz/

## Computational level
- **study_focus:** Stereotype-based learning — how pre-existing gender stereotypes influence reinforcement learning of person-related knowledge via prediction errors.
- **study_focus_short:** Stereotype-based learning
- **learning_mode_description:** - Learning mode: Learning from probabilistic feedback about stereotype-consistent vs. stereotype-inconsistent individuals to update expectations about which person in a gendered pairing is correct.   - Learning from:     - Source type (non-social): world       - Feedback is binary correct/incorrect delivered by the task environment     - Source content (non-social): outcome       - Probabilistic reward feedback (correct/incorrect) on each trial   - Learning about:     - Target type (social): other (gendered individuals — stereotype vs. counter-stereotype)     - Target content (social): stimulus       - Which face (male or female) in each pair is more likely to be correct, given stereotype-related context (ballet/boxing pastime)
- **task_description:** Participants completed a probabilistic selection task in which three pairs of male-female faces were presented; participants learned which face in each pair was more likely to be correct based on probabilistic feedback (80/20, 70/30, 60/40), with stereotype-related context provided (one person in each pair was said to prefer ballet or boxing).
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), multi-target (6 face stimuli in 3 pairs per block, across 2 blocks: stereotype-confirming and stereotype-disconfirming).
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Grayscale face photographs (male and female, from Chicago Face Database), binary textual and auditory feedback (correct/incorrect).
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Pre-existing stereotype bias in initial expected reward values: best-fitting model set Q = 0.6 for stereotypes, Q = 0.4 for counter-stereotypes (DIC = 32,765 for dual-LR stereotype-bias model vs. 32,771 for no-bias)   - Faster negative learning rates for counter-stereotypes vs. stereotypes across both ballet (pBayes < 0.001, BF10 > 1000) and boxing (pBayes = 0.009, BF10 = 113) conditions   - Faster positive learning rates for counter-stereotypes vs. stereotypes across both pastimes (pBayes = 0.016, BF10 = 62)   - Greater threshold separation (response caution) for counter-stereotypes vs. stereotypes (pBayes = 0.013, BF10 = 76)   - Faster non-decision time for stereotypes vs. counter-stereotypes (pBayes < 0.001, BF10 > 1000)   - Drift rate scaling larger for stereotypes in ballet (pBayes < 0.001, BF10 > 1000) but for counter-stereotypes in boxing (pBayes = 0.200, BF10 = 4)   - Decision times faster for stereotypes than counter-stereotypes (b = −0.042, SE = 0.005, t = −8.14)
- **effect_size:** - BF10 > 1000 (negative PE learning rate: counter-stereotype > stereotype, both pastimes combined) - BF10 = 62 (positive PE learning rate: counter-stereotype > stereotype, both pastimes combined) - BF10 = 76 (threshold separation: counter-stereotype > stereotype) - BF10 > 1000 (non-decision time: stereotype < counter-stereotype) - BF10 > 1000 (drift rate scaling, ballet: stereotype > counter-stereotype) - BF10 = 4 (drift rate scaling, boxing: counter-stereotype > stereotype) - b = −0.042 (decision time main effect of Correct Target)
- **learning_from:** World; probabilistic correct/incorrect feedback on face selections.
- **learning_about:** Other (social); which gendered individual (stereotype-consistent vs. counter-stereotype) is correct in each pair.---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** RL-DDM with dual learning rates (η−, η+), stereotype-biased initial Q-values (Q_stereo = 0.6, Q_counter = 0.4), threshold separation (a) by stereotype condition, drift rate scaling (v) by Pastime × Correct Target, non-decision time (t0) by Correct Target.
- **model_family:** Drift-diffusion
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Model 1 (stereotype bias, single LR)", "family": "RL-DDM", "n_params": "not specified (fewer than dual)", "metric": "DIC = 32,785"},   {"name": "Model 1 (stereotype bias, dual LR)", "family": "RL-DDM", "n_params": "not specified", "metric": "DIC = 32,765 (best)"},   {"name": "Model 2 (no bias, single LR)", "family": "RL-DDM", "n_params": "not specified", "metric": "DIC = 32,788"},   {"name": "Model 2 (no bias, dual LR)", "family": "RL-DDM", "n_params": "not specified", "metric": "DIC = 32,771"},   {"name": "Model 3 (counter-stereotype bias, single LR)", "family": "RL-DDM", "n_params": "not specified", "metric": "DIC = 32,792"},   {"name": "Model 3 (counter-stereotype bias, dual LR)", "family": "RL-DDM", "n_params": "not specified", "metric": "DIC = 32,777"} ]
- **model_mb_mf:** MF (model-free; delta-rule RL with no forward/transition model).
- **model_params:** - η− (negative learning rate) [S]: learning rate for negative prediction errors; varied by Pastime × Correct Target. Fitted values: Ballet/Stereotype = 0.01, Ballet/Counter-stereotype = 0.21, Boxing/Stereotype = 0.03, Boxing/Counter-stereotype = 0.21 - η+ (positive learning rate) [S]: learning rate for positive prediction errors; varied by Pastime × Correct Target. Fitted values: Ballet/Stereotype = 0.12, Ballet/Counter-stereotype = 0.19, Boxing/Stereotype = 0.03, Boxing/Counter-stereotype = 0.10 - a (threshold separation) [S]: evidence threshold for response; varied by Correct Target. Fitted values: Stereotype = 1.85, Counter-stereotype = 1.89 - v (drift rate scaling) [S]: sensitivity to feedback / evidence accumulation rate; varied by Pastime × Correct Target. Fitted values: Ballet/Stereotype = 2.88, Ballet/Counter-stereotype = 1.03, Boxing/Stereotype = 1.11, Boxing/Counter-stereotype = 1.22 - t0 (non-decision time) [S]: non-decisional processing time; varied by Correct Target. Fitted values: Stereotype = 0.13, Counter-stereotype = 0.15 - Q (initial expected value): fixed, not estimated — Q = 0.6 for stereotype conditions, Q = 0.4 for counter-stereotype conditions (HIGH — all values from supplement Table S1 and main text)
- **social_param:** η− and η+ (negative and positive learning rates) varied by stereotype condition, capturing differential learning speed for stereotype-consistent vs. counter-stereotype individuals. Initial Q-values (0.6 vs. 0.4) capture pre-existing stereotype bias. All parameters except Q varied by stereotype condition.
- **social_param_name:** η−
- **social_param_value:** 0.01
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** DIC (Deviance Information Criterion).
- **how_model_fit:** Individual-level-fit via simultaneous hierarchical Bayesian estimation (MCMC with 10,000 samples, 5,000 burn-in, across 3 chains).
- **data_type_fit_to:** Choice behavior and response times (simultaneously).---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A — behavioural study only.
- **key_regions:** N/A — no neuroimaging.
- **coordinates_peak:** N/A — no neuroimaging.
- **analysis_type:** N/A---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 60 (47 females, 12 males, 1 other; Mage = 24.30, SD = 3.51); 6 excluded for failure to learn, leaving N = 54 for analysis. Ages 18–36 (inferred from young adult range). Online recruitment via Prolific Academic.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low ecological validity — laboratory probabilistic selection task with binary face pairs and probabilistic feedback. Gender stereotypes induced via pastime labels (ballet/boxing) rather than naturally occurring. Online administration increases some ecological validity but task structure is highly artificial.
- **eligibility_flag:** 
- **concerns:** - Drift rate scaling parameter recovery was poor for stereotype-consistent conditions (ballet/female, boxing/male) due to correlation with learning rates — authors note v should be interpreted with caution. - Exact number of free parameters per model not explicitly stated. - Only gender stereotypes tested (ballet/boxing); generalizability to other stereotype domains unknown. - No neural data to link computational parameters to brain mechanisms. (MEDIUM-HIGH)
- **limitations_reported:** Updating stereotypes in everyday life does not share the characteristics of probabilistic selection tasks in which people must actively choose which of two competing alternatives is most likely to be correct over multiple trials"; "A basic limitation of the PST RL-DDM model is that it can only address binary decision-making, thereby potentially underestimating the nuanced ways in which stereotypes bias learning"; subtyping may preserve superordinate stereotypes despite counter-stereotype learning; only gender-related pastimes tested; no neural data collected.
- **limitations_categorized:** Limited ecological validity; task simplicity (binary decisions only); limited generalizability (single stereotype domain); no neural data; potential subtyping confound.
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.5
- **wc_total:** 8.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `model_params` n_params: MEDIUM — exact count of free parameters per model not explicitly stated; inferred from parameter descriptions - `wc_guidelines` Rule 3: MEDIUM — posterior predictive check was done post-fitting; unclear if simulations preceded data collection - `sample_size` age range: MEDIUM — "young adults aged 20–30" refers to face stimuli, not participants; participant age range not explicitly stated beyond M and SD
- **cannot_find:** - Exact number of free parameters for each of the 6 models (not tabulated) - Participant age range (only M = 24.30, SD = 3.51 reported)
- **other_notes:** - This is a single-study paper (1 experiment).  - The paper explicitly discusses future neural work (suggesting VS, TPJ, mPFC, ACC as regions of interest) but collected no neural data itself. - Code and data shared on OSF. - The RL-DDM framework combines Rescorla-Wagner updating with drift diffusion decision process — the "winning model" uses the delta learning rule: Q_chosen(t) = Q_chosen(t-1) + η[feedback(t-1) − Q_chosen(t-1)], with separate η− and η+ and biased starting Q-values.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_target = social
- tax_domain_D_group_structure_identity
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MB_MF_hybrid
- tax_model_drift_diffusion
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_valence_asymmetry
- tax_popclass_healthy
- tax_rr_domain = D_group_structure_identity
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_drift_diffusion
- tax_rr_model_family = drift_diffusion
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = stereotype_updating
- tax_rr_topic_stereotype_updating
- tax_topic_stereotype_updating
