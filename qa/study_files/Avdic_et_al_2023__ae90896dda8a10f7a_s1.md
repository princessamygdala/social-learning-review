# Avdic et al. (2023)

- **study_id:** `ae90896dda8a10f7a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Björlin Avdic, H., Strannegård, C., Engberg, H., Willfors, C., Nordgren, I., Frisén, L., Lindén Hirschberg, A., Guath, M., Nordgren, A., & Lundin Kleberg, J. (2023). Reduced effects of social feedback on learning in Turner syndrome. *Scientific Reports*, *13*, 15858. https://doi.org/10.1038/s41598-023-42628-7
- **citation_short:** Avdic et al. (2023)
- **doi:** 10.1038/s41598-023-42628-7
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Centre for Psychiatry Research, Department of Clinical Neuroscience, Karolinska Institutet & Stockholm; Department of Laboratory Medicine, Institute of Biomedicine, University of Gothenburg, Gothenburg,; Department of Clinical Genetics and Genomics, Sahlgrenska University Hospital, Gothenburg,; lable through social cues is more reliable than what can be achieved through other; Department of Clinical Genetics, Karolinska University Hospital, Stockholm, Sweden; Center for Molecular Medicine, Karolinska Institutet, Stockholm, Sweden; Department of Applied IT, University of Gothenburg, Gothenburg,
- **code_url:** 

## Computational level
- **study_focus:** Social reinforcement learning — examining how social feedback (facial expressions) vs. non-social feedback (gold coins) affects probabilistic reinforcement learning in Turner syndrome vs. controls.
- **study_focus_short:** Social reinforcement learning
- **learning_mode_description:** - Learning mode: Learning from social/non-social feedback about stimulus-reward contingencies in a probabilistic two-armed bandit task   - Learning from:     - Source type (non-social): world       - Social condition adds a social feedback overlay but the underlying reward structure is from the task environment     - Source content (non-social): outcome       - Social condition: source content (social): outcome (smiling face as reward feedback)       - Non-social condition: source content (non-social): outcome (gold coins as reward feedback)   - Learning about:     - Target type (non-social): world     - Target content (non-social): stimulus (which of two stimuli has higher reward probability)
- **task_description:** Participants chose between two stimuli (balloons) across 75 trials, where one stimulus had a 2/3 probability and the other a 1/3 probability of winning a point. Correct choices were followed by either social feedback (animated smiling face) or non-social feedback (animated gold coins), while incorrect choices were followed by an "X" animation in both conditions.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), no social partner (feedback is pre-programmed; social stimulus is a static face animation, not an interactive agent).
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Abstract stimuli (colored balloons), social feedback (animated smiling woman's face), non-social feedback (animated gold coins), loss feedback (animated letter "X").
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Social feedback led to lower %correct in controls compared to non-social feedback (group × condition interaction: b = 5.17, t = 2.23) - Controls showed higher %correct in non-social vs. social condition (b = 5.01, t = 3.45) - No effect of condition on %correct in Turner syndrome group (b = −0.16, t = 0.13) - β (exploitation-exploration) was higher in non-social than social condition in controls (b = 0.56, t = 2.89) — social feedback shifted controls toward exploration - No effect of condition on β in Turner syndrome group (b = −0.07, t = 0.27) - Group × condition interaction on β (b = 0.61, t = 2.16) - Turner syndrome group showed higher %switch-lose in non-social vs. social condition (b = 8.26, t = 2.80) - No condition effect on α in either group
- **effect_size:** - Group comparison (demographics): age d = 0.39; WAIS Vocabulary d = 0.41 - Affective rating of non-social feedback: d = −0.53 (controls rated higher) - Group × condition interaction on %correct: b = 5.17 - Group × condition interaction on β: b = 0.61 - Group × condition interaction on %switch-lose: b = −7.57 - Note: Most effects reported as regression coefficients (b) and t-statistics from LMMs; no Cohen's d for main experimental effects.
- **learning_from:** World; reward/loss outcome feedback delivered via social (smiling face) or non-social (gold coins) cues.
- **learning_about:** World; which of two stimuli has a higher probability of reward.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Rescorla-Wagner (single update; 2 params: α, β)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Model 1 — Standard RW (single update)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AIC (Akaike weights)"} - {"name": "Model 2 — RW with separate α for pos/neg outcomes", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC (Akaike weights)"} - {"name": "Model 3 — RW dual update (chosen + unchosen)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AIC (Akaike weights)"} - {"name": "Model 4 — RW dual update + loss/reward weight d", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC (Akaike weights)"} - {"name": "Model 5 — Alternating switch (probability 1)", "family": "Heuristic", "n_params": 0, "metric": "AIC (Akaike weights)"} - {"name": "Model 6 — Random choice (p = 0.5)", "family": "Null/random", "n_params": 0, "metric": "AIC (Akaike weights)"}
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): governs degree to which prediction error updates value. Range [0, 1]. Control social Md = 0.61 (MAD = 0.41); Control non-social Md = 0.61 (MAD = 0.37); TS social Md = 0.63 (MAD = 0.38); TS non-social Md = 0.76 (MAD = 0.28). - β (inverse temperature / exploitation-exploration): governs choice determinism. Range [0, ∞). Higher = more exploitative. Control non-social > social (b = 0.56); TS no condition difference.
- **social_param:** No explicitly social parameter in the model. The social manipulation is at the task design level (social vs. non-social feedback condition), not parameterized within the model.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (Akaike weights)
- **how_model_fit:** individual-level-fit (MLE with Gaussian priors; repeated 50 times with random starting points per participant per condition)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** N = 72 (35 Turner syndrome, 37 controls); ages range approximately 18–53 (TS M = 33.83, SD = 10.80; Control M = 38.10, SD = 15.05). 7 TS participants completed only one condition. WAIS Vocabulary available for subset (n = 26 TS, n = 18 controls).
- **population_category:** healthy adults
- **population_age_range:** M=33.83 (SD=10.80)
- **ecological_validity:** Online data collection (Pavlovia) from home, which increases ecological validity of setting but reduces experimental control. Task uses abstract stimuli (balloons) with a single static social cue (smiling face animation) — limited ecological validity for real-world social learning. Social feedback is not interactive or contingent on a real social partner. Authors note they could not observe participants during the task.
- **eligibility_flag:** 
- **concerns:** - The social manipulation is at the feedback level only (face vs. coins); the learning problem itself is non-social (stimulus-reward contingency). This is borderline for "learning in a social context" — the social element is feedback modality, not the learning target. - Model 1 (standard RW) was selected for both groups/conditions to "facilitate comparison" even though Model 4 had best fit for the TS non-social condition — this may mask group differences. - Control group partially overlaps with Kleberg et al. (2023) sample. - No reported effect sizes (Cohen's d or similar) for main experimental effects — only regression coefficients from LMMs. - Online data collection with limited quality control. - α analyzed non-parametrically (Wilcoxon) rather than in the LMM framework.
- **limitations_reported:** Large within-group variability; no qualitative information about participants' experiences or interpretation of the task was collected; no psychiatric or medical assessment including medication history was possible due to online data collection; unable to directly observe participants during the task or monitor environment; social feedback used only for wins (not losses); relatively small sample size may explain null findings; control group partly overlapping with another study.
- **limitations_categorized:** sample size; limited ecological validity; online data collection limitations; no psychiatric assessment; incomplete experimental design (social feedback only for wins); potential sample overlap with prior study; high within-group variability.
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
- **wc_rule10:** Partial
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - learning_mode: MEDIUM — the social element is in the feedback modality, not in the learning target; classification of source as "world" with social overlay is an interpretation - social_param: HIGH — paper explicitly states no social parameter in the model - effect_size: MEDIUM — main experimental effects reported only as regression coefficients, not standardized effect sizes - wc_guidelines rule 3: MEDIUM — simulations done but unclear if conducted prior to data collection
- **cannot_find:** - Exact mean fitted values of α and β per group/condition (only medians and MADs reported for α; β reported only as regression coefficients from LMM, not raw descriptives) - Standardized effect sizes (Cohen's d) for main experimental findings
- **other_notes:** This paper is methodologically linked to Kleberg et al. (2023) "Social feedback enhances learning in Williams syndrome" — same task, partially overlapping control group. Should be flagged as potential partial overlap. The supplement confirms all modeling details and provides parameter recovery and model validation information.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = general
- spec_locus = source+target
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_temperature
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_temperature
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_social_nonsocial_comparison
- tax_topic_social_approval_reward
