# Koban et al. (2017)

- **study_id:** `aed34e7341d5fced8_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Koban, L., Schneider, R., Ashar, Y. K., Andrews-Hanna, J. R., Landy, L., Moscovitch, D. A., Wager, T. D., & Arch, J. J. (2017). Social anxiety is characterized by biased learning about performance and the self. *Emotion*, *17*(8), 1144–1155. http://dx.doi.org/10.1037/emo0000296
- **citation_short:** Koban et al. (2017)
- **doi:** 10.1037/emo0000296
- **publication_type:** peer-reviewed journal
- **year:** 2017.0
- **field_of_study:** Cognitive science
- **affiliations_raw:** ethanktheconfederatesforperformingtheroleofthejudges,AlainaCarrfor ativelybiasedlearningfromsocialfeedbackplaysacriticalrolein; InstituteofCognitiveScienceandDepartmentofPsychology detrimental consequences not only for the social life of affected; UniversityofColoradoBoulder;RebeccaSchneider,Institute individuals, but also for their academic success, employment,; InstituteofCognitiveScienceandDepartmentofPsychology Brown, & Holle, 1996; Stein & Kean, 2000; Wittchen, Fuetsch,; UniversityofColoradoBoulder,345Muen- ratesocialfeedbackintotheirself-imagetoagreaterextentwhen; etheauthorsuseanovelexp
- **code_url:** 

## Computational level
- **study_focus:** Social self-esteem learning; biased affective updating from social performance feedback in social anxiety disorder vs. healthy controls.
- **study_focus_short:** Social self-esteem learning
- **learning_mode_description:** - Learning mode: Learning from judges' social performance feedback about one's own feelings toward the self (affective updating / state self-esteem)   - Learning from:     - Source type (social): other (judges/confederates)     - Source content (social): outcome (performance evaluation feedback on VAS)   - Learning about:     - Target type (social): self     - Target content (social): state (affective state; feelings about the self / state self-esteem)
- **task_description:** Participants delivered a speech in front of three confederate judges, then completed a social feedback task in which they rated their own performance on 58 dimensions, received the judges' ratings on the same dimensions, and rated how they felt about themselves and the judges after each trial. Follow-up self-evaluations were collected at 20 min and ~1 year.
- **task_paradigm:** Self-evaluation / self-esteem task
- **players:** Single agent (participant), multi-target (3 confederate judges)
- **n_players:** multi-target (3+)
- **partner_type:** confederate
- **stimuli:** Text-based evaluative statements (58 speech performance dimensions), VAS ratings from judges, VAS self-ratings
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Significant Valence x Rating Type x Group interaction on learning rates (F(1,54) = 16.25, partial η² = 0.23)   - Group x Valence interaction on self-directed affective updating (F(1,54) = 13.55, partial η² = 0.20)   - SAD had significantly higher negative learning rates than HCs for feelings about self (d = 0.93)   - Two-learning-rate model outperformed one-learning-rate model for Feeling_Self (BIC: -712.9 vs. -217.7; d = 1.74)   - Significant feedback valence x group interaction on performance self-ratings across T2 and T3 (F(1,31) = 10.83, partial η² = 0.26)   - Overall influence of judges' feedback on performance self-ratings (F(1,31) = 52.67, partial η² = 0.63)   - Positivity bias difference (α_Self_diff) negatively correlated with trait anxiety (STAI: partial r = -0.46), fear of negative evaluation (FNE: partial r = -0.48), rumination (RRQ: partial r = -0.37), and positively with self-compassion (SCS: partial r = 0.39)   - α_Self_diff negatively correlated with negative affect words in spontaneous thought (partial robust r = -0.37)
- **effect_size:** - Main Results:   - Significant Valence x Rating Type x Group interaction on learning rates (F(1,54) = 16.25, partial η² = 0.23)   - Group x Valence interaction on self-directed affective updating (F(1,54) = 13.55, partial η² = 0.20)   - SAD had significantly higher negative learning rates than HCs for feelings about self (d = 0.93)   - Two-learning-rate model outperformed one-learning-rate model for Feeling_Self (BIC: -712.9 vs. -217.7; d = 1.74)   - Significant feedback valence x group interaction on performance self-ratings across T2 and T3 (F(1,31) = 10.83, partial η² = 0.26)   - Overall influence of judges' feedback on performance self-ratings (F(1,31) = 52.67, partial η² = 0.63)   - Positivity bias difference (α_Self_diff) negatively correlated with trait anxiety (STAI: partial r = -0.46), fear of negative evaluation (FNE: partial r = -0.48), rumination (RRQ: partial r = -0.37), and positively with self-compassion (SCS: partial r = 0.39)   - α_Self_diff negatively correlated with negative affect words in spontaneous thought (partial robust r = -0.37)
- **learning_from:** Other (judges); social performance evaluation feedback
- **learning_about:** Self; feelings about the self (state self-esteem) and self-evaluated speech performance  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Rescorla-Wagner with 2 learning rates (α_pos, α_neg) + initial feeling state value; Feeling_Self(t) = Feeling_Self(t-1) + α * APE, where APE = V_Feedback(t) - Feeling_Self(t-1), separate α for positive vs. negative APE
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "1-learning-rate RW (Feeling_Self)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"}, {"name": "2-learning-rate RW (Feeling_Self)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC"}, {"name": "1-learning-rate RW (Feeling_Judges)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"}, {"name": "2-learning-rate RW (Feeling_Judges)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC"}]
- **model_mb_mf:** MF
- **model_params:** - α_SelfPos [S]: Learning rate for positive affective prediction errors (feelings about self). Mean fitted values: SAD = 0.22 (STE 0.07), HCs = 0.34 (STE 0.06) - α_SelfNeg [S]: Learning rate for negative affective prediction errors (feelings about self). Mean fitted values: SAD = 0.27 (STE 0.05), HCs = 0.06 (STE 0.04) - Initial Feeling_Self: Initial value of feeling about self (constrained 0-1) - α_JudgesPos: Learning rate for positive APE (feelings about judges) - α_JudgesNeg: Learning rate for negative APE (feelings about judges) - Initial Feeling_Judges: Initial value of feeling about judges (constrained 0-1)
- **social_param:** α_SelfPos and α_SelfNeg — learning rates for integrating positive vs. negative social performance feedback into feelings about the self. The difference (α_Self_diff = α_SelfPos - α_SelfNeg) indexes the positivity/negativity bias in social self-esteem updating.
- **social_param_name:** α_SelfPos
- **social_param_value:** 0.22
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC
- **how_model_fit:** individual-level-fit (Matlab Optimization toolbox, minimizing sum of squared errors)
- **data_type_fit_to:** self-report ratings (VAS ratings of feelings about self and judges)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 56 (21 SAD, 35 HC); ages 18–40; T3 follow-up: N = 33 (14 SAD, 19 HC after exclusion of 1 SAD outlier). Predominantly female in SAD group (19/21 female).
- **population_category:** mixed
- **population_age_range:** 18–40
- **ecological_validity:** Moderately ecologically valid — participants gave a real speech in front of live confederate judges and received authentic (selected) performance feedback. However, the laboratory setting and confederate judges reduce naturalistic social interaction. Feedback was algorithmically selected from real judge ratings to approximate a uniform distribution, which departs from natural feedback patterns.
- **eligibility_flag:** 
- **concerns:** Unbalanced gender distribution (19/21 females in SAD, 18/35 in HC) — authors controlled statistically but limited male SAD participants. Small SAD sample (n=21). Non-standardized follow-up interval (7-16 months). Cannot determine specificity to SAD vs. other internalizing disorders as no clinical comparison group was included. Feedback selection algorithm may have introduced artifacts. No supplement accessible for verification of additional model details.
- **limitations_reported:** We cannot make claims regarding the specificity of the present findings for SAD versus their generalizability across a wider range of psychological disorders"; "questionnaire measures related to anxiety and to ruminative and depressive tendencies were associated with a reduced positivity bias, which thus may be characteristic of anxiety and affective disorders more broadly"; "we cannot completely rule out some of its residual effects [regression to the mean]"; "the follow-up time period (T3) was nonstandardized (ranging between 7 and 16 months)"; "the present sample was not perfectly matched with regard to demographics and only included two male participants with diagnosed SAD
- **limitations_categorized:** limited generalizability; limited clinical specificity (no comparison clinical group); potential regression to the mean; non-standardized follow-up; sample size; gender imbalance
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `wc_guidelines` rule 3 (simulation): LOW — no mention of simulation anywhere in text - `wc_guidelines` rule 8 (validation): LOW — no posterior predictive check mentioned - Supplement not accessible (referenced at http://dx.doi.org/10.1037/emo0000296.supp) — supplement .txt file not found in papers folder
- **cannot_find:** - Supplement file: not available in papers folder. Referenced supplement contains Table S1 (evaluative items), Figures S2-S6 (example time courses, model comparisons, gender analyses). Could not verify additional model details or supplementary analyses. - Exact fitted parameter values for judge-directed learning rates (α_JudgesPos, α_JudgesNeg) — not reported in main text - Initial feeling state parameter values — not reported in main text
- **other_notes:** This is a behavioural-only study with no neuroimaging. The adapted Rescorla-Wagner model is applied to affective ratings (feelings about self/judges) rather than choice behavior — an interesting application of RL to self-esteem dynamics. The study also includes a separate multilevel GLM analysis of performance self-rating changes (T1 to T2/T3) that is not computational modeling per se but demonstrates enduring effects of the feedback bias. The paper's supplemental materials were referenced but the supplement file was not available in the papers folder.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_anxiety
- pop_healthy_adults
- rr_pop_anxiety
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = target
- spec_source = social
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_valence_asymmetry
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = self_esteem
- tax_rr_secondary_topic = social_approval_reward
- tax_rr_topic_self_esteem
- tax_rr_topic_social_approval_reward
- tax_topic_self_esteem
- tax_topic_social_approval_reward
