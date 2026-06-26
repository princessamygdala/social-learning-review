# Kleberg et al. (2023)

- **study_id:** `a058c75e2ab740b1d_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lundin Kleberg, J., Willfors, C., Björlin Avdic, H., Riby, D., Galazka, M. A., Guath, M., Nordgren, A., & Strannegård, C. (2023). Social feedback enhances learning in Williams syndrome. *Scientific Reports*, *13*, 164. https://doi.org/10.1038/s41598-022-26055-8
- **citation_short:** Kleberg et al. (2023)
- **doi:** 10.1038/s41598-022-26055-8
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Laboratory Medicine, Institute of Biomedicine, University of Gothenburg, Gothenburg, Sweden; Department of Clinical Genetics, Karolinska University Hospital, Stockholm, Sweden; Centre for Psychiatry Research, Karolinska Institute, Stockholm, Sweden; Department of Applied IT, University of Gothenburg, Gothenburg, Sweden; Department of Psychology, Stockholm University, Stockholm, Sweden; Department of Psychology, Uppsala University, Uppsala,; Department of Psychology, Centre for Developmental; University of Gothenburg, Gothenburg, Sweden; emails: johan.lundin.kleberg@su.se
- **code_url:** 

## Computational level
- **study_focus:** Social reinforcement learning -- effects of social versus non-social feedback on probabilistic reward learning in Williams syndrome, intellectual disability, and typically developing controls.
- **study_focus_short:** Social reinforcement learning -- effects of social versus non-social feedback
- **learning_mode_description:** - Learning mode: Learning from social or non-social feedback about stimulus-reward contingencies in a probabilistic reinforcement learning task.   - Learning from:     - Source type (social in social condition; non-social in non-social condition): world (task feedback)       - Social condition: animated smiling face (social reward)       - Non-social condition: animated pile of gold coins (non-social reward)     - Source content (non-social): outcome (win/loss feedback)   - Learning about:     - Target type (non-social): world (stimulus-reward associations)     - Target content (non-social): stimulus (which of two stimuli has higher reward probability)
- **task_description:** Participants completed two rounds (social, non-social feedback; counterbalanced) of a 75-trial probabilistic reward learning task in which they chose between two stimuli with reward probabilities of 2/3 and 1/3. Correct choices were followed by either an animated smiling face (social condition) or animated gold coins (non-social condition), while incorrect choices always produced an animated "X" with "you lost!" text.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), no interactive partner. Three groups: Williams syndrome (n=25), intellectual disability of other etiology (n=24), typically developing controls (n=56).
- **n_players:** network (5+)
- **partner_type:** none
- **stimuli:** Abstract stimuli (colored balloons), animated smiling face (social feedback from ADFES), animated gold coins (non-social feedback), animated X (loss feedback).
- **method:** online / behavioural
- **method_full:** behavioural / online (majority online via Pavlovia; 12 participants in-lab)
- **main_result:** - Main Results:   - Social feedback increased correct choices in WS (p.correct social > non-social; d = 0.58, p = 0.024)   - Social feedback increased choice consistency in WS (p.consistent social > non-social; d = 0.55, p = 0.003)   - No significant effects of social feedback condition in TD or ID groups on choice behavior   - WS group showed lower loss/reward weight (d parameter) in social vs non-social condition (d = -0.44, p = 0.027), indicating shift toward reward sensitivity   - Group x condition interaction on d parameter (chi-squared = 10.85, p = 0.004, f-squared = 0.031)   - Group x condition interaction on p.correct (chi-squared = 10.18, p = 0.006, f-squared = 0.03)   - Group x condition interaction on p.consistent (chi-squared = 21.97, p < 0.001, f-squared = 0.03)   - Strong negative correlation between p.correct and d in social condition in WS (rs = -0.88, p < 0.001)   - Learning rate higher in WS and ID than TD (alpha: group effect chi-squared = 20.71, p < 0.001, f-squared = 0.13)   - Loss/reward weight higher in WS and ID than TD (d: group effect chi-squared = 23.62, p < 0.001, f-squared = 0.16)
- **effect_size:** - Main Results:   - Social feedback increased correct choices in WS (p.correct social > non-social; d = 0.58, p = 0.024)   - Social feedback increased choice consistency in WS (p.consistent social > non-social; d = 0.55, p = 0.003)   - No significant effects of social feedback condition in TD or ID groups on choice behavior   - WS group showed lower loss/reward weight (d parameter) in social vs non-social condition (d = -0.44, p = 0.027), indicating shift toward reward sensitivity   - Group x condition interaction on d parameter (chi-squared = 10.85, p = 0.004, f-squared = 0.031)   - Group x condition interaction on p.correct (chi-squared = 10.18, p = 0.006, f-squared = 0.03)   - Group x condition interaction on p.consistent (chi-squared = 21.97, p < 0.001, f-squared = 0.03)   - Strong negative correlation between p.correct and d in social condition in WS (rs = -0.88, p < 0.001)   - Learning rate higher in WS and ID than TD (alpha: group effect chi-squared = 20.71, p < 0.001, f-squared = 0.13)   - Loss/reward weight higher in WS and ID than TD (d: group effect chi-squared = 23.62, p < 0.001, f-squared = 0.16)
- **learning_from:** World; social feedback (animated smiling face) or non-social feedback (animated gold coins) for correct choices; loss feedback (animated X) for incorrect choices.
- **learning_about:** World; which of two stimuli has higher reward probability (stimulus-reward contingencies).  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Fictitious update RL + reward/punishment sensitivity (Model 5: alpha, beta, d); V(c)_{t+1} = V(c)_t + alpha(r_t - V(c)_t); V(nc)_{t+1} = V(nc)_t + alpha(1 - r_t - V(nc)_t); r = 1-d (win), r = -d (loss); softmax with beta.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Model 1: Basic RL", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AIC (Akaike weights)"},   {"name": "Model 2: Separate learning rates RL", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC (Akaike weights)"},   {"name": "Model 3: RL + reward/punishment sensitivity", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC (Akaike weights)"},   {"name": "Model 4: Fictitious update RL", "family": "Rescorla-Wagner (fictitious update)", "n_params": 2, "metric": "AIC (Akaike weights)"},   {"name": "Model 5: Fictitious update RL + reward/punishment sensitivity (WINNING)", "family": "Rescorla-Wagner (fictitious update)", "n_params": 3, "metric": "AIC (Akaike weights)"},   {"name": "Model 6: Choice Kernel", "family": "Choice kernel", "n_params": 2, "metric": "AIC (Akaike weights)"},   {"name": "Model 7: Alternating choices", "family": "Non-learning (deterministic alternation)", "n_params": 0, "metric": "AIC (Akaike weights)"},   {"name": "Model 8: Random responding", "family": "Non-learning (random)", "n_params": 0, "metric": "AIC (Akaike weights)"} ]
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate, range 0-1): degree of value updating after each outcome. Mean fitted values: WS social = 0.69 (SD=0.31), WS non-social = 0.79 (SD=0.19); ID social = 0.69 (SD=0.30), ID non-social = 0.71 (SD=0.23); TD social = 0.52 (SD=0.33), TD non-social = 0.46 (SD=0.32). - beta (exploitation/exploration balance, range 0 to infinity): determines choice determinism via softmax. Mean fitted values: WS social = 2.88 (SD=1.20), WS non-social = 2.76 (SD=0.88); ID social = 2.44 (SD=1.27), ID non-social = 2.03 (SD=1.23); TD social = 2.26 (SD=1.07), TD non-social = 2.50 (SD=1.15). - d (loss/reward weight, range 0-1) [S]: relative subjective value of losses vs rewards. d > 0.5 = higher weight to losses; d < 0.5 = higher weight to rewards. Mean fitted values: WS social = 0.69 (SD=0.28), WS non-social = 0.80 (SD=0.23); ID social = 0.63 (SD=0.33), ID non-social = 0.67 (SD=0.26); TD social = 0.48 (SD=0.28), TD non-social = 0.41 (SD=0.25).
- **social_param:** d (loss/reward weight) [S] -- the relative subjective value of losses versus rewards. Social feedback specifically reduced d in the WS group (shifting balance toward reward sensitivity), mediating the beneficial effect of social feedback on learning performance.
- **social_param_name:** d
- **social_param_value:** 0.69
- **social_param_sd:** 0.28
- **social_param_range:** 0–1
- **model_comparison_metric:** AIC (Akaike Information Criterion), transformed to Akaike weights.
- **how_model_fit:** individual-level-fit (maximum likelihood estimation with empirical Gaussian priors from stage 1; repeated 50 times with random starting points to avoid local minima)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 105 total (WS: n=25, ages 7-51, M=24.12, SD=12.26; ID: n=24, ages 6-51, M=19.72, SD=12.51; TD: n=56, ages 6-50, M=27.82, SD=15.88). WS IQ M=56.88 (SD=10.54). TD estimated IQ M=102.5 (SD=10.49). Some participants excluded from individual conditions due to data rejection criteria.
- **population_category:** mixed
- **population_age_range:** 7–51
- **ecological_validity:** Low-to-moderate. Lab-based probabilistic learning task with abstract stimuli (balloons). Social feedback was a brief animated smiling face, not a live social interaction. Majority of data collected online, reducing experimental control but increasing ecological reach for rare populations.
- **eligibility_flag:** 
- **concerns:** - The social manipulation is in the feedback modality (social face vs. gold coins), not in a genuinely interactive social context. The "social" element is a smiling face animation, not a real social partner. - Small sample sizes for WS and ID groups limit power for within-group and between-condition analyses. - Online data collection limits control over testing environment (though lab vs. online comparison showed similar results). - The d parameter is described as "social" but it is not inherently social -- it indexes loss/reward balance, and social feedback modulated it in WS only. - Model 5 was used for all groups even though Model 1 fit slightly better for TD in the non-social condition.
- **limitations_reported:** Sample size in the WS and ID groups was small; study data were largely collected online with lack of exact control over settings; small sample size in the ID group did not allow formal statistical comparisons between included conditions (22q11 deletion syndrome, Fragile X, Coffin-Siris, Sotos syndrome).
- **limitations_categorized:** sample size; limited experimental control (online data collection); limited generalizability (cannot compare syndromes within ID group)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 9.5
- **wc_total:** 9.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - learning_mode: MEDIUM -- the "social" element is feedback modality (smiling face), not a social source per se. The source is arguably the task/world delivering feedback in social vs. non-social form. Categorized source type as conditional on condition. - social_param: MEDIUM -- d is not inherently a social parameter; it is a general loss/reward weight parameter that was differentially affected by social feedback in the WS group only. - model_family: HIGH -- clearly a Rescorla-Wagner delta-rule model with fictitious updating. - All choice behavior and model parameter values: HIGH -- directly reported in tables.
- **cannot_find:** - No preregistration statement found in paper or supplement. - No code/data sharing repository link (data available "upon reasonable request" only).
- **other_notes:** - This paper is primarily a clinical/developmental study comparing WS, ID, and TD populations on reinforcement learning, with the social manipulation being feedback type (social face vs. non-social coins). The social context is in the reward signal, not in agent interaction. - The supplement contains detailed model descriptions, model comparison (AIC weights), model recovery (confusion matrix), and parameter recovery analyses -- all checked and extracted above. - The paper provides a thorough Wilson & Collins-aligned modeling pipeline, notably including both parameter recovery and model recovery, which is uncommon.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_autism
- pop_healthy_adults
- rr_pop_autism
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_social_nonsocial_comparison
- tax_topic_social_approval_reward
