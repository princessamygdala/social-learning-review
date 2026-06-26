# Buehler et al. (2025)

- **study_id:** `afd0df0cd14192101_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Buehler, R., Potocar, L., Mikus, N., & Silani, G. (2025). Autistic traits relate to reduced reward sensitivity in learning from point-light displays (PLDs). *Royal Society Open Science*, *12*, 241349. https://doi.org/10.1098/rsos.241349
- **citation_short:** Buehler et al. (2025)
- **doi:** 10.1098/rsos.241349
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department of Clinical and Health Psychology, and 2Department of Cognition, Emotion, and; ethods in Psychology, University of Vienna, Vienna, Austria; Department of Psychology, University of Oslo, Oslo, Norway; University Library user; lable online at; emails: raimund.buehler@univie.ac.at
- **code_url:** https://github.com/raimund-buehler/RALT_final.nosync

## Computational level
- **study_focus:** Social reinforcement learning; individual differences in autistic traits relating to reward sensitivity vs. learning rate parameters when learning from social (facial point-light displays) vs. non-social (symbol point-light displays) feedback.
- **study_focus_short:** Social reinforcement learning
- **learning_mode_description:** - Learning mode: Learning from probabilistic social/non-social PLD feedback about correct categorization of stimuli   - Learning from:     - Source type (social in social condition; non-social in non-social condition): world (task feedback)       - Social condition: facial PLDs depicting happy/angry expressions       - Non-social condition: check marks/crosses from PLDs     - Source content (non-social): outcome (binary reward/no-reward feedback)   - Learning about:     - Target type (non-social): world (stimulus-category associations)     - Target content (non-social): action/policy (correct categorization of numbers into groups A/B)
- **task_description:** Participants categorized random two-digit numbers into arbitrary groups (A or B) and received probabilistic feedback (85/15 contingency) via point-light displays -- happy/angry facial PLDs in social blocks and check mark/cross PLDs in non-social blocks. They completed 4 blocks of 6 trials each (2 social, 2 non-social, interleaved), totaling 96 trials.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), no social partner (feedback is automated PLD stimuli)
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Point-light displays (PLDs) depicting facial emotional expressions (happy/angry) for social condition; check marks and crosses for non-social condition; two-digit numbers as classification stimuli
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Trial number significantly predicted correct responses (OR = 1.10, 95% CI [1.06, 1.14]) - No significant main effect of block type on performance (OR = 0.81, 95% CI [0.61, 1.09]) - No significant AQ x block type interaction on performance (OR = 1.03, 95% CI [0.97, 1.10]) - Higher AQ predicted reduced reward sensitivity in win domain (rho_win: OR = 0.79, 95% CI [0.64, 0.98]; permutation p = 0.003) - Simple slope: AQ effect on rho_win significant in social blocks (OR = 0.95, 95% CI [0.90, 0.999]) but not non-social blocks (OR = 0.96, 95% CI [0.91, 1.01]); however, interaction was not significant (p = 0.74) - AQ positively associated with theta_loss (beta = 0.148, r = 0.27) but model assumptions violated - No AQ effects on alpha_win, alpha_loss, or rho_loss
- **effect_size:** OR = 0.79 (AQ on rho_win); r = 0.27 (AQ on theta_loss); OR = 1.10 (trial number on correct responses)
- **learning_from:** World; probabilistic reward feedback (social: facial emotion PLDs; non-social: symbol PLDs)
- **learning_about:** World; stimulus-category associations (correct categorization of numbers)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Rescorla-Wagner (separate alpha and rho for win/loss x social/non-social; 1 theta per condition domain; 6 params per participant total)  RPE(t) = rho * Outcome(t) - P_A(t) P_A(t+1) = P_A(t) + alpha * RPE(t) P(Choice_A, t+1) = 1 / (1 + exp(-theta * (P_A - P_B)))
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Only one model tested (Rescorla-Wagner with rho, alpha, theta). No model comparison performed.
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate) [0, 1]: estimated separately for win and loss domains. Captures weighting of prediction errors. - rho (reward sensitivity) [0, 1]: estimated separately for win and loss domains. Scales the outcome to capture internal reward value. [S] in social condition. - theta (inverse temperature) [1, 50]: captures explore/exploit trade-off. Estimated separately for win/loss. - Parameters estimated separately for social and non-social conditions, resulting in 6 parameters per participant. - Mean fitted values not reported in text (distributions shown in Figure 4 histograms only).
- **social_param:** rho (reward sensitivity) -- in the social condition, captures the internal value assigned to social PLD feedback (facial emotion expressions). Higher AQ associated with lower rho_win in social blocks.
- **social_param_name:** rho
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 0–1
- **model_comparison_metric:** N/A -- only one model tested. Model fit assessed visually (predicted vs. observed learning curves, Figure 2b,c).
- **how_model_fit:** individual-level-fit (MLE using scipy minimize with TNC method, with elastic net regularization lambda=0.01)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only; authors suggest future fMRI with FFA, ventral striatum, vmPFC)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 63 (from 74 recruited; 36 female, 27 male; mean age = 26.51, SD = 6.76, range up to 63 years)
- **population_category:** healthy adults
- **population_age_range:** M=26.51
- **ecological_validity:** Low-to-moderate. PLDs are abstract and low-level, deliberately stripped of naturalistic facial features to control for visual confounds. The social feedback (facial emotion PLDs) is far from naturalistic social interaction. Task is a standard probabilistic categorization task. Authors note debriefing suggested participants found social PLDs "particularly challenging." No real social interaction.
- **eligibility_flag:** 
- **concerns:** - Only one model tested -- no model comparison, making it impossible to evaluate whether this specification is superior to alternatives (e.g., model with single learning rate, model without rho, dual-learning-rate model). - Very short task: only 96 trials total (24 per condition), which may limit parameter recovery. - The "social" condition involves automated PLD feedback, not interaction with a social agent -- the social element is in the stimulus modality (facial expression) rather than in the social structure of the task. - AQ x block type interaction was not significant, so the social-specificity claim rests on simple slopes analysis, which the authors appropriately caveat. - Mean fitted parameter values not reported numerically, only in histograms. - Assumptions for theta_loss LMM were violated per supplement QQplots. - No formal model fit metric reported (e.g., BIC, AIC, log-likelihood); only visual inspection of predicted vs. observed.
- **limitations_reported:** Observed differences in parameter values did not reflect in raw learning performance; potential confound of working memory capacity not measured; sample consisted of neurotypical individuals without ASD diagnosis, limiting generalizability to clinical population; compensatory cognitive strategies may have masked emotion recognition differences; facial PLDs conveyed less emotional information via eyes than mouth; abstract visual stimuli may have increased difficulty differentially across AQ groups.
- **limitations_categorized:** Limited ecological validity; no clinical sample; potential working memory confound; task simplicity; limited generalizability; stimulus validity concerns; no model comparison; short task length
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 4.5
- **wc_total:** 4.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params (MEDIUM): Mean fitted values not reported numerically, only shown in histograms - model_comparison_metric (LOW): No model comparison performed at all - winning_model (MEDIUM): Called "winning" but is the only model tested - ecological_validity (MEDIUM): Judgment based on task description
- **cannot_find:** - Mean fitted parameter values (numeric) -- only shown in figures - Formal model fit statistics (AIC, BIC, log-likelihood) - Any alternative models tested
- **other_notes:** The paper was preregistered as part of a larger project (originally included eye tracking). The supplement documents deviations from the preregistered analysis plan. The "social" nature of this task is primarily in the feedback modality (facial PLDs) rather than in social interaction structure -- the social agent is effectively an automated display. This is worth flagging for the systematic review taxonomy. Data and code are openly available.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_autism
- pop_healthy_adults
- rr_pop_autism
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = target
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_social_weight
- tax_param_temperature
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_social_nonsocial_comparison
- tax_topic_social_approval_reward
