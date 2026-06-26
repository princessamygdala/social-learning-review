# Li et al. (2024)

- **study_id:** `ac804d19bfcd535f0_s3`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Li, S., Huang, Y., Xu, C., Wu, J., & Qu, C. (2024). Asymmetric adaption in social learning: Understanding the dilemma of competition and cooperation. *Behavioral Sciences*, *14*(8), 721. https://doi.org/10.3390/bs14080721
- **citation_short:** Li et al. (2024)
- **doi:** 10.3390/bs14080721
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** CenterforStudiesofPsychologicalApplication,GuangdongKeyLaboratoryofMentalHealthandCognitive; LaboratoryofBrain,CognitionandEducationSciences,MinistryofEducation,SchoolofPsychology,; FacultyofEducation,NortheastNormalUniversity,Changchun130024,China;lisiying@nenu; DepartmentofExperimentalPsychology,GhentUniversity,9000Ghent,Belgium;yulong; SchoolofPsychology,FujianNormalUniversity,Fuzhou350117,China;wuj@fjnu; etheunderlyingcognitivemechanismsofinformation; University,Guangzhou510631,China;2016022547@m; etheiropponents’behaviors; emails: yulong.huang@ugent.be, 2016022547@m.scnu.edu.cn, chenqu@sc
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning / competition learning — how individuals learn and adapt their competitive vs. cooperative behavior in response to opponents' competitiveness levels, behavioral patterns, and social categorization (human vs. computer) in a Chicken Game.
- **study_focus_short:** Cooperation learning / competition learning
- **learning_mode_description:** - Learning mode: Learning from opponent's competitive/cooperative choices about opponent's competitiveness in a fluctuating environment with phase shifts   - Learning from:     - Source type (social): other (opponent — human or computer)     - Source content (social): action/policy (competitive or cooperative choice)   - Learning about:     - Target type (social): other (opponent)     - Target content (social): state (behavioral tendency / competitiveness level)
- **task_description:** Participants played a repeated Chicken Game against four simulated opponents (2 human, 2 computer) over 6 blocks in 3 phases: Phase 1 (neutral 50%), Phase 2 (high 70% / low 30% differentiation), Phase 3 (return to 50%). This tested adaptation to fluctuating opponent competitiveness.
- **task_paradigm:** Coordination game
- **players:** Single agent (participant), multi-target (4 simulated opponents: 2 human, 2 computer; competitiveness shifting across phases)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Human face photographs, computer images, car icons, numerical point feedback
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Significant main effects of Competition (F(1,28) = 15.649, ηp² = 0.359) and Phase (F(2,56) = 6.948, ηp² = 0.199) - Significant Competition x Phase interaction (F(2,56) = 9.882, ηp² = 0.261) - Significant three-way Sociality x Competition x Phase interaction (F(2,56) = 3.248, ηp² = 0.104) - Model_3P (pattern-level) best fitting (vs. Model_3B: d = -0.78; vs. Model_3BPC: d = -8.65) - Higher learning rate for highly competitive vs. less competitive opponents (d = 0.511) - Participants adapted to HP in Phase 2 (HHP Phase 1 vs. 2: d = 0.783) but did not readjust in Phase 3 - Faster RT against human opponents (F(1,28) = 7.575, ηp² = 0.213)
- **effect_size:** ηp² = 0.359 (Competition); ηp² = 0.199 (Phase); ηp² = 0.261 (Competition x Phase); ηp² = 0.104 (three-way); d = 0.511 (αP1 > αP2); d = 0.783 (HHP Phase 1 vs. 2); ηp² = 0.213 (RT Sociality)
- **learning_from:** Other (opponent); opponent's competitive/cooperative choice in fluctuating context
- **learning_about:** Other (opponent); opponent's behavioral pattern / competitiveness level  ---  ### ALGORITHMIC LEVEL  **Experiment 1 — Winning model**: Model_1B: Rescorla-Wagner with 2 learning rates for opponent behavior (αB1 for competition feedback, αB2 for cooperation feedback; 1 β). P(t+1) = P(t) + αB * PE(t); softmax choice rule.  **Experiment 2 — Winning model**: Model_2B: Same as Model_1B — Rescorla-Wagner with 2 learning rates for opponent behavior (αB1 = 0.09, αB2 = 0.20; β = 0.21).  **Experiment 3 — Winning model**: Model_3P: Rescorla-Wagner with 2 learning rates for opponent pattern (αP1 = 0.13 for highly competitive, αP2 = 0.06 for less competitive; β = 0.05).
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Model_3P: Rescorla-Wagner with 2 learning rates for opponent pattern (αP1 = 0.13 for highly competitive, αP2 = 0.06 for less competitive; β = 0.05).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Experiment 1: - Model_1B: RW, 2 LRs (behavior), 3 params, AIC = 63.05 - Model_1P: RW, 2 LRs (pattern), 3 params, AIC = 65.05 - Model_1BP: RW, 4 LRs (behavior x pattern), 5 params, AIC = 66.55  Experiment 2: - Model_2B: RW, 2 LRs (behavior), 3 params, AIC = 121.58 - Model_2P: RW, 2 LRs (pattern), 3 params, AIC = 125.14 - Model_2C: RW, 2 LRs (categorization), 3 params, AIC = 124.01 - Model_2BP: RW, 4 LRs (behavior x pattern), 5 params, AIC = 128.18 - Model_2BC: RW, 4 LRs (behavior x categorization), 5 params, AIC = 127.93 - Model_2PC: RW, 4 LRs (pattern x categorization), 5 params, AIC = 123.50 - Model_2BPC: RW, 8 LRs (behavior x pattern x categorization), 9 params, AIC = 127.94  Experiment 3: - Model_3B: RW, 2 LRs (behavior), 3 params, AIC = 159.58 - Model_3P: RW, 2 LRs (pattern), 3 params, AIC = 157.41 - Model_3C: RW, 2 LRs (categorization), 3 params, AIC = 158.72 - Model_3BP: RW, 4 LRs, 5 params, AIC = 161.69 - Model_3BC: RW, 4 LRs, 5 params, AIC = 162.66 - Model_3PC: RW, 4 LRs, 5 params, AIC = 161.22 - Model_3BPC: RW, 8 LRs, 9 params, AIC = 168.80
- **model_mb_mf:** MF
- **model_params:** - Exp 1 (Model_1B): αB1 = 0.058 (learning rate for opponent competition choice), αB2 = 0.212 (learning rate for opponent cooperation choice) [S], β = 0.23 (inverse temperature) - Exp 2 (Model_2B): αB1 = 0.09 (competition feedback LR), αB2 = 0.20 (cooperation feedback LR) [S], β = 0.21 - Exp 3 (Model_3P): αP1 = 0.13 (highly competitive pattern LR) [S], αP2 = 0.06 (less competitive pattern LR) [S], β = 0.05
- **social_param:** αB1 and αB2 — asymmetric learning rates for opponent's competitive vs. cooperative behavioral choices (Exp 1 & 2); αP1 and αP2 — asymmetric learning rates for highly vs. less competitive opponent behavioral patterns (Exp 3). All parameters are inherently social as they capture learning from a social agent's behavior.
- **social_param_name:** Exp 1
- **social_param_value:** 0.058
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (Akaike Information Criterion), supplemented by paired t-tests on AIC values between models
- **how_model_fit:** individual-level-fit (MLE per participant)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Exp 1: N = 29 (aged 19.38 +/- 1.68, 17 females); Exp 2: N = 29 (1 excluded from 30; aged 20.86 +/- 1.10, 17 females); Exp 3: N = 29 (aged 20.50 +/- 2.25, 16 females). Total N = 87 across 3 independent experiments. All Chinese university students.
- **population_category:** undergraduates
- **population_age_range:** M=19.38 (SD=1.68)
- **ecological_validity:** Low-to-moderate. The Chicken Game is an abstract laboratory task with simulated (deceptive) opponents. Authors acknowledge deception may compromise ecological validity. No real social interaction. However, the game captures core elements of real competition-cooperation dilemmas.
- **eligibility_flag:** 
- **concerns:** - Model comparison done via paired t-tests on AIC values rather than formal BMS or cross-validation — unusual and potentially problematic - No parameter recovery or model recovery analyses reported - No simulation of models before fitting - No posterior predictive checks / model validation - Supplement referenced but not available locally — may contain additional model details - All samples are Chinese university students, limiting generalizability - The winning model differs across experiments (behavior-level in Exp 1-2, pattern-level in Exp 3), which may reflect task design differences rather than a coherent account
- **limitations_reported:** Limited sample and controlled laboratory setting may not capture real-world complexity; use of deception (participants believed they were playing against humans) may compromise ecological validity; limited range of competition probabilities tested (only 70% and 30%); only one type of game tested (Chicken Game); no neuroimaging or psychophysiological measures
- **limitations_categorized:** limited ecological validity; sample size; limited generalizability; task simplicity; deception; no neuroimaging
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `wc_3` (simulate): LOW — no simulation mentioned in main text; supplement not accessible to verify - `wc_5` (parameter recovery): LOW — not reported - `wc_6` (model recovery): LOW — not reported - `wc_8` (model validation): LOW — no posterior predictive checks - `model_params` fitted values for Exp 1: MEDIUM — αB1 = 0.06 and αB2 = 0.21 reported in Table 1 but SEM given, not SD
- **cannot_find:** Supplement not accessible locally (referenced at MDPI URL). Could not verify whether simulation, parameter recovery, or model recovery are reported there. Formula details for expected value calculation are in main text (Equations 1-6).
- **other_notes:** The paper is published in *Behavioral Sciences* (MDPI), an open-access journal. The winning model shifts from behavior-level (Exp 1, 2) to pattern-level (Exp 3), which the authors interpret as reflecting the different demands of stable vs. fluctuating environments. The supplement is referenced for "more detail" on models but is not available locally — flagging this but the main text provides adequate model equations and parameter tables.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_action_observation
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = cooperation
- tax_rr_secondary_topic = competition
- tax_rr_topic_competition
- tax_rr_topic_cooperation
- tax_topic_competition
- tax_topic_cooperation
