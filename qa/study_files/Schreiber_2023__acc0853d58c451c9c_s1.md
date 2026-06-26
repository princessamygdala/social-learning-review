# Schreiber (2023)

- **study_id:** `acc0853d58c451c9c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Schreiber, A. M. (2023). *The role of neurocomputational decision processes in affect-based impulsivity in borderline personality* [Doctoral dissertation, University of North Carolina at Chapel Hill]. University of North Carolina at Chapel Hill.
- **citation_short:** Schreiber (2023)
- **doi:** Not reported in the text.
- **publication_type:** thesis
- **year:** 2023.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** mitted to the faculty at the University of North Carolina at Chapel Hill in; laborating a Decision Neuroscience account of affect-based impulsivity; Laboratory, who provided support as I worked on this project; lab manager Hannah Evans for her involvement in this; lab mate throughout my graduate training; mitations of research conducted to-date; College of Arts and Sciences; mittee, Drs
- **code_url:** 

## Computational level
- **study_focus:** Affect-based impulsivity in borderline personality; how negative affect shifts the balance of Pavlovian and goal-directed decision systems, with social cues acting as Pavlovian influences on decision-making.
- **study_focus_short:** Affect-based impulsivity in borderline personality
- **learning_mode_description:** - Learning mode: Learning from reward outcomes on a social decision-tree task about which action sequences maximize social influence points, with social cues (avatars) acting as Pavlovian influences on choice and vigor.   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (social influence points received after each action)     - Source type (social): world       - Source content (social): stimulus (social cues -- avatars and social action labels act as Pavlovian cues that bias approach)   - Learning about:     - Target type (non-social): world       - Target content (non-social): action/policy (optimal action sequences through the decision tree)     - Target type (social): world       - Target content (social): action/policy (whether to choose social vs. nonsocial actions; value of social vs. nonsocial action sequences)
- **task_description:** Participants navigate a Social Decision Tree Task (SDTT) where they are placed in a fictional town and must maximize "social influence points" by choosing 6 actions per epoch (40 epochs), selecting between social and nonsocial actions at each step, with reward feedback after each choice. An incidental affect induction (positive, negative, or neutral) precedes the task; Study 2 adds a vigor component requiring repeated key presses.
- **task_paradigm:** Affective decision task
- **players:** Single agent (participant), multi-target (fictional townspeople avatars)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Avatars of fictional townspeople, social action labels (e.g., "Grocery shop with Aniyah"), nonsocial action labels, affective images from IAPS with mood-congruent music, social influence points as feedback.
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - SARSA was the preferred cRL model of behavior (EP = 0.993 in Study 1) - Participants exhibited a Pavlovian bias toward social actions (z = 9.25, p < .001) and sensitivity to immediate value (z = 46.70, p < .001) - Negative affect induction amplified multiplicative effect of immediate x future value on vigor (t = 2.07, p = .038) - Negative urgency heightened sensitivity to immediate value and blunted future value influence on choice (z = 2.05, p = .040) - Negative urgency amplified vigorous pursuit of immediate rewards late in epoch (t = -2.46, p = .014) - BPD symptoms heightened sensitivity to immediate value late in epoch (z = 2.67, p = .008) - BPD symptoms heightened discounting of future value when planning social-then-nonsocial sequences (t_Study1 = -2.75, p = .006; t_Study2 = -2.32, p = .024) - Negative urgency and BPD symptoms predicted affect-dependent alterations for negative and neutral (but not positive) affect inductions - Among high BPD individuals, decreases in valence in response to negative affect induction heightened bias toward immediately valuable social actions (z = 2.64, p = .008)
- **effect_size:** - SARSA model: EP = 0.993 (Study 1), EP = 0.995 (Study 2) - SARSA-el SS: EP = 0.983 (Study 1), EP = 0.48 (Study 2) - Social action bias: z = 9.25 - Immediate value on choice: z = 46.70 - Negative urgency x immediate x future value on choice: z = 2.05 - Negative urgency x immediate value x future value x move on vigor: t = -2.46 - BPD x immediate value x move on choice: z = 2.67 - BPD x discounting (social t, nonsocial t+1, early learning, Study 1): t = -2.75 - Negative urgency and BPD correlation: r = 0.73
- **learning_from:** Self; reward outcomes (social influence points) on chosen actions in SDTT; social cues (avatars) serve as Pavlovian stimulus influences
- **learning_about:** World; optimal action sequences in the decision tree; relative value of social vs. nonsocial actions  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** SARSA-el SS: V(a_t, s_t) = V(a_t, s_t) + α[r + γ·V(a_{t+1}, s_{t+1}) - V(a_t, s_t)], with 8 γ discount parameters (social/nonsocial at t x social/nonsocial at t+1 x early/late in learning), 1 α (learning rate), 1 β (softmax temperature). Study 2 adds λ (effort discounting).
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Qlearn", "family": "Q-learning (model-free)", "n_params": 2, "metric": "BMS EP"},   {"name": "SARSA", "family": "SARSA (partial MB)", "n_params": 3, "metric": "BMS EP"},   {"name": "Discount", "family": "Tree search (model-based)", "n_params": 2, "metric": "BMS EP"},   {"name": "Learned Discount", "family": "Tree search + learning (model-based)", "n_params": 3, "metric": "BMS EP"},   {"name": "Pruning", "family": "Tree search with pruning (model-based)", "n_params": 3, "metric": "BMS EP"},   {"name": "Learned Pruning", "family": "Tree search + learning with pruning (model-based)", "n_params": 4, "metric": "BMS EP"},   {"name": "lp (mixed)", "family": "Dual-controller (mixed MB/MF)", "n_params": 5, "metric": "BMS EP"},   {"name": "Learned lp (mixed)", "family": "Dual-controller + learning (mixed MB/MF)", "n_params": 6, "metric": "BMS EP"},   {"name": "SARSA-el", "family": "SARSA (early/late γ)", "n_params": 4, "metric": "BMS EP"},   {"name": "SARSA-S", "family": "SARSA (social/nonsocial at t)", "n_params": 4, "metric": "BMS EP"},   {"name": "SARSA-futS", "family": "SARSA (social/nonsocial at t+1)", "n_params": 4, "metric": "BMS EP"},   {"name": "SARSA-SS", "family": "SARSA (social at t and t+1)", "n_params": 6, "metric": "BMS EP"},   {"name": "SARSA-el S", "family": "SARSA (early/late x social at t)", "n_params": 6, "metric": "BMS EP"},   {"name": "SARSA-el futS", "family": "SARSA (early/late x social at t+1)", "n_params": 6, "metric": "BMS EP"},   {"name": "SARSA-el SS", "family": "SARSA (early/late x social at t x social at t+1)", "n_params": 10, "metric": "BMS EP"},   {"name": "SARSA-bias", "family": "SARSA + social bias", "n_params": 4, "metric": "BMS EP"},   {"name": "SARSA-el bias", "family": "SARSA (early/late) + social bias", "n_params": 5, "metric": "BMS EP"} ]
- **model_mb_mf:** Hybrid (partial model-based -- one-step lookahead, not full tree search; authors characterize SARSA as "partial model-based")
- **model_params:** - α (learning rate): governs speed of value updating - β (softmax inverse temperature): governs choice stochasticity - γ_SS_early [S]: discount parameter when both current and next action are social, early in learning - γ_NSNS_early: discount parameter when both current and next action are nonsocial, early in learning - γ_SNS_early [S]: discount parameter when current action is social and next is nonsocial, early in learning - γ_NSS_early [S]: discount parameter when current action is nonsocial and next is social, early in learning - γ_SS_late [S]: discount parameter when both current and next action are social, late in learning - γ_NSNS_late: discount parameter when both current and next action are nonsocial, late in learning - γ_SNS_late [S]: discount parameter when current action is social and next is nonsocial, late in learning - γ_NSS_late [S]: discount parameter when current action is nonsocial and next is social, late in learning - λ (effort discounting, Study 2 only): sensitivity to number of key presses required - Mean fitted values not reported in the text (descriptive statistics referenced in Tables 6 and 7 but not directly readable from the .txt extraction).
- **social_param:** γ discount parameters conditioned on social vs. nonsocial action type at trial t and t+1 [S] -- these capture how the social nature of the current and planned next action modulates discounting of future value; higher discounting for social actions reflects Pavlovian bias toward immediately valuable social actions.
- **social_param_name:** γ_SS_early
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Bayesian Model Selection (BMS) exceedance probability (EP)
- **how_model_fit:** individual-level-fit (using VBA Toolbox in MATLAB, Bayesian estimation at individual level within mixed-effects framework)
- **data_type_fit_to:** choice behavior (Study 1 and Study 2)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study only; no neuroimaging)
- **key_regions:** N/A (behavioural study only; neural account is theoretical -- proposes mPFC for goal-directed, mesolimbic DA / NAcc for Pavlovian, but these were not tested empirically)
- **coordinates_peak:** N/A -- no neuroimaging data collected
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Study 1: N = 388 (after excluding 16; 217 female, 163 male, 8 nonbinary; mean age 38, SD = 13, range 18-84; 127 positive, 134 negative, 127 neutral affect induction); Study 2: N = 77 (after excluding 4; 49 female, 26 male, 2 nonbinary; mean age 38, SD = 13, range 19-77; 39 neutral, 38 negative affect induction). cRL analyses restricted to R^2 > 0.6: Study 1 N = 350, Study 2 N = 63.
- **population_category:** clinical
- **population_age_range:** 18–84
- **ecological_validity:** Online Prolific community sample with dimensional personality measures rather than clinical BPD sample. Task uses a fictional scenario (moving to a new town, earning "social influence points") with avatar-based social interactions, which is relatively abstract. Affect inductions used validated IAPS images + music. The social component is simulated (no real social interaction), limiting ecological validity for interpersonal processes in BPD. However, the dimensional approach is theoretically well-justified and the task cleverly dissociates Pavlovian vs. goal-directed influences.
- **eligibility_flag:** FLAG: thesis; borderline social learning (social cues present as Pavlovian stimuli but no genuine social interaction or learning from others' behavior); learning does occur over time (40 epochs of trial-and-error learning).
- **concerns:** - The social element of the task is limited to social cues (avatars, action labels) rather than genuine social interaction; whether this qualifies as "social learning" vs. "learning with social cues" is debatable. - SARSA-el SS won model comparison in Study 1 (EP = 0.983) but was equivocal in Study 2 (EP = 0.48 vs. SARSA-el EP = 0.41); the same model was used in Study 2 for comparability rather than because it was clearly best. - Many effects were observed in only one study (Study 1 or Study 2 but not both), raising concerns about replicability. - Community sample with self-report BPD measures; no clinical diagnosis. - No parameter recovery or model recovery analyses reported. - Mean fitted parameter values not accessible from the text extraction (Tables 6-7 referenced but not readable). - No formal simulation of the winning model prior to fitting (simulation was done for task design validation, not for model validation per Wilson & Collins guidelines). - The number of statistical tests is very large with no correction for multiple comparisons.
- **limitations_reported:** Community sample relied on self-report measures of personality and psychopathology rather than clinical diagnosis; cannot make inferences about clinical BPD sample; three affect inductions did not produce statistically similar increases in arousal (positive induction did not change arousal, neutral induction decreased arousal); best-fitting model was SARSA rather than the expected mixed MB/MF model, so discounting of future value was not explained by pruning as predicted; differences in task design from prior decision-tree tasks (fixed 6-move epoch, no pre-planning of full action sequence) may account for the preference for SARSA over full model-based models.
- **limitations_categorized:** limited generalizability; limited ecological validity; self-report measures only; no clinical sample; affect manipulation not perfectly controlled; unexpected model selection outcome; task simplicity; no parameter recovery; no model recovery; multiple comparisons not corrected.
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
- **flagged_fields:** - doi: LOW -- not found in the extracted text; likely available through ProQuest but not stated in the dissertation itself. - winning model formula: MEDIUM -- formula described in text but the .txt extraction renders mathematical symbols as (cid:X) codes, making exact formula reconstruction approximate. - model_params mean fitted values: LOW -- Tables 6-7 referenced but not readable from .txt extraction. - social learning classification: MEDIUM -- task includes social cues but no genuine social interaction. - effect_size: MEDIUM -- many test statistics reported but formal effect sizes (Cohen's d, etc.) not computed; z-values and t-values reported.
- **cannot_find:** - DOI (likely exists via ProQuest but not stated in text) - Mean fitted parameter values (referenced in Tables 6-7 but not readable from .txt) - Formal effect sizes (Cohen's d, r, etc.) -- only z-values and t-values reported - Preregistration status
- **other_notes:** This is a dissertation with 2 studies that should be treated as a single paper with 2 studies (same paradigm, Study 2 adds vigor measure). The dissertation also includes extensive secondary analyses (positive urgency, Big 5 personality, affective instability, sex, stress exposure) and RT analyses in appendices. The theoretical model proposes specific neural mechanisms (glucocorticoids sensitizing NAcc shell, NE impairing mPFC) but these were not tested empirically -- they are future directions. The task (SDTT) is a novel social variant of the Huys et al. (2012) decision-tree task.
- **re_extract_flag:** false (full text was accessible, though mathematical formulas are garbled in .txt extraction due to cid encoding of special characters)

## Taxonomy / categorization (active codes only)
- pop_bpd
- pop_healthy_adults
- rr_pop_bpd
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = general
- spec_locus = source+target
- spec_source = social
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MB_MF_hybrid
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_MB_MF_balance
- tax_rr_param_decay
- tax_rr_primary_topic = self_other_boundary
- tax_rr_topic_self_other_boundary
- tax_topic_self_other_boundary
