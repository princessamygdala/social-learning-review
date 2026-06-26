# Kim et al. (2025)

- **study_id:** `ad869b3b0665cb6ac_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Kim, Y., Kim, K. I., & Kim, H. (2025). Social observation differentially affects prosocial learning of selfish and prosocial people. *Frontiers in Psychology*, *16*, 1440302. https://doi.org/10.3389/fpsyg.2025.1440302
- **citation_short:** Kim et al. (2025)
- **doi:** 10.3389/fpsyg.2025.1440302
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** ether, these findings indicate that individuals strive to be perceived raise a critical question: Does the limited effect of social observation; Laboratory of Social and Decision Neuroscience, School of Psychology, Korea University, Seoul,; mitted, who were already more prosocial showed no significant changes in prosociality,; ether individuals with intrinsic prosocial tendencies also exhibit a; University of Campania Luigi Vanvitelli, Italy; University of Indonesia, Indonesia; mitted which does not comply with; centered tendencies,; emails: hackjinkim@korea.ac.kr
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning under social observation; interaction between audience effects and individual differences in prosocial learning sensitivity on reinforcement learning for self- vs. other-regarding rewards.
- **study_focus_short:** Prosocial learning under social observation
- **learning_mode_description:** - Learning mode: Learning from reward outcomes (self- and other-regarding) about stimulus-reward contingencies under social observation   - Learning from:     - Source type (non-social): self       - The participant's own choices generate outcomes     - Source content (non-social): outcome (binary reward: point given or not)   - Learning about:     - Target type (social): other (anonymous next participant) AND (non-social): self       - Joint is NOT applicable; these are separate reward conditions (self vs. other)     - Target content (non-social for self-condition; social for other-condition): stimulus-reward associations (which fractal image has higher reward probability, for self-benefit or other-benefit)
- **task_description:** In each block, participants chose between pairs of fractal images in a two-armed bandit task under "self" (earn reward for self) and "other" (earn reward for next anonymous participant) reward conditions, with reward probabilities reversing mid-block. Before the second of three blocks, participants in the observation group were told another participant was watching their screen in real-time.
- **task_paradigm:** Two-armed bandit
- **players:** Single agent (participant), single anonymous target (next participant as reward recipient); between-subjects manipulation of observation (observer present vs. control).
- **n_players:** single agent (1)
- **partner_type:** human (live)
- **stimuli:** Abstract fractal images (6 pairs), binary reward feedback (point given or not), "Screen Sharing" cue with red dot icon for observation manipulation.
- **method:** online / behavioural
- **method_full:** Behavioural / online (conducted on Gather.town metaverse platform using psyToolKit)
- **main_result:** - Main Results:   - Significant four-way interaction (Observation x PLS group x Block x Reward) on learning rates (F(2, 196) = 3.616, p = 0.029, eta-squared not reported for four-way)   - OBS-Selfish group: increased alpha for "other" from Block 1 to Block 2 (t(31) = -4.918, p < 0.001) and decreased alpha for "self" (t(31) = 2.790, p = 0.009)   - PLS change from Block 1 to Block 2 significantly larger in OBS-Selfish vs. CON-Selfish (t(63) = 2.499, p = 0.015)   - OBS-Prosocial group: marginal increase in alpha for "self" from Block 1 to Block 2 (t(16) = -2.532, p = 0.022, adjusted p = 0.053), no significant change in alpha for "other"   - No significant OBS vs CON difference in prosocial group for self learning rate changes (t(35) = 1.338, p = 0.190; bootstrap p = 0.172)   - PLS marginally correlated with SVO survey scores (r(100) = 0.185, p = 0.063)   - Posterior predictive check: r = 0.72 between actual and predicted HRP
- **effect_size:** - Interaction effect from power analysis reference: eta-p-squared = 0.103 (from Jung et al., 2018, used for power analysis, not from this study's four-way interaction) - PLS correlation with HRP difference: r(100) = 0.31, p < 0.001 - PLS correlation with RT difference: r(100) = -0.251, p = 0.011 - PLS correlation with SVO: r(100) = 0.185, p = 0.063 - Note: Effect sizes (Cohen's d, eta-squared) for the key four-way interaction and post-hoc tests are not explicitly reported beyond F and t statistics.
- **learning_from:** Self; own choice outcomes (binary reward feedback — point given or not given for chosen fractal image)
- **learning_about:** Self (self-reward condition: which fractal yields higher reward for self) and Other (other-reward condition: which fractal yields higher reward for anonymous next participant)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** RW with separate parameters per reward condition (M2: alpha_self, alpha_other, tau_self, tau_other; 4 free parameters)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "M0 (Null)", "family": "Random choice", "n_params": 0, "metric": "BIC"} - {"name": "M1 (shared parameters)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"} - {"name": "M2 (separate parameters)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BIC"}
- **model_mb_mf:** MF
- **model_params:** - alpha_self: learning rate for self-reward condition (mean fitted values not reported as single numbers; used as individual difference variable) - alpha_other: learning rate for other-reward condition [S] (social parameter — indexes learning sensitivity for other-regarding rewards) - tau_self: inverse temperature for self-reward condition - tau_other: inverse temperature for other-reward condition [S]
- **social_param:** alpha_other — learning rate for other-regarding reward condition; indexes sensitivity to prediction errors when learning for the benefit of an anonymous other person. PLS (Prosocial Learning Sensitivity) = alpha_other - alpha_self, derived measure capturing relative prosocial vs. selfish learning tendency. [S]
- **social_param_name:** alpha_other
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion). Winning model M2 preferred over M1 across all blocks (Block 1: delta-BIC = 125.56; Block 2: delta-BIC = 133.71; Block 3: delta-BIC = 143.04). M2 preferred over null M0 (Block 1: delta-BIC = 654.5; Block 2: delta-BIC = 714.97; Block 3: delta-BIC = 687.27).
- **how_model_fit:** Individual-level fit (maximum likelihood estimation per participant per block)
- **data_type_fit_to:** Choice behavior (trial-by-trial binary choices between fractal images)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** N = 102 (after exclusions from 112 recruited; 49 OBS group, 53 CON group; 69 females total in original sample, mean age = 23.5 years, range 18-30). Selfish subgroup: 65 participants (32 OBS, 33 CON); Prosocial subgroup: 37 participants (17 OBS, 20 CON).
- **population_category:** healthy adults
- **population_age_range:** 18–30
- **ecological_validity:** Online experiment conducted on Gather.town metaverse platform enhances ecological plausibility of social observation manipulation compared to lab-based eye-cue paradigms; however, the task itself is a standard abstract two-armed bandit with fractal images, limiting naturalistic social interaction. The "other" recipient is anonymous and unknown, reducing social richness.
- **eligibility_flag:** 
- **concerns:** (1) The prosocial subgroup is substantially smaller (n = 37) than the selfish subgroup (n = 65), creating asymmetric group sizes that limit statistical power for prosocial group analyses. (2) The key four-way interaction effect size (partial eta-squared) is not reported. (3) The categorization of participants into "selfish" vs. "prosocial" groups is based on a median-split-like approach using Block 1 learning rates, which is a post-hoc data-driven categorization rather than an independent measure. (4) The PLS measure only marginally correlated with the SVO survey (p = 0.063), raising questions about construct validity. (5) No effect sizes (Cohen's d) reported for the critical post-hoc comparisons. (6) Inverse temperature parameters showed no relationship with learning indices or self/other differences, contrary to prior literature.
- **limitations_reported:** The differential social observation effect was solely evident in learning rates"; "our experimental setting did not show any relationship between inverse temperature and other learning indices or the difference between self- and other-regarding learnings"; "the collection of cases for each selfish and prosocial learning tendency group was asymmetric. Almost 64% of the participants exhibited higher learning rates for the 'self' than 'other' reward conditions"; caution advised when interpreting learning rate parameters in RL paradigms in social psychological experiments (citing Zhang et al., 2020).
- **limitations_categorized:** Limited generalizability (effect only in one parameter); task simplicity; unbalanced group sizes; construct validity concerns; parameter interpretability caution.
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** yes
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM — effect sizes for the key four-way interaction and post-hoc tests (Cohen's d, partial eta-squared) are not explicitly reported; only F and t statistics with p-values provided - social_param: HIGH — directly stated - model_params (mean fitted values): LOW — individual mean fitted parameter values across groups/blocks are not reported as summary statistics in text; they are shown graphically in figures but exact values not given - wc_guidelines Rule 10: MEDIUM — paper states data are "included in the article/Supplementary material" but no repository link provided
- **cannot_find:** - Exact mean fitted parameter values for alpha_self, alpha_other, tau_self, tau_other by group and block (shown in figures only) - Effect size measures (Cohen's d, partial eta-squared) for the four-way interaction and post-hoc comparisons - Exact SVO scale used and its scores
- **other_notes:** This study builds directly on the prosocial learning task paradigm from Lockwood et al. (2016) and Sul et al. (2015). The PLS measure (alpha_other - alpha_self) is the key derived social parameter. The online metaverse platform (Gather.town) is a notable methodological feature for studying social observation effects. The study is purely behavioral with no neuroimaging component.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_E_self_in_social_context
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = social_approval_reward
- tax_rr_topic_prosocial_altruism
- tax_rr_topic_social_approval_reward
- tax_topic_prosocial_altruism
- tax_topic_social_approval_reward
