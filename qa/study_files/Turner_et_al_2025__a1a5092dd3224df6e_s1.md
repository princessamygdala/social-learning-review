# Turner et al. (2025)

- **study_id:** `a1a5092dd3224df6e_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Turner, G., Gunschera, L. J., Subrahmanya, S., Salecha, A., Eichstaedt, J. C., Palminteri, S., & Orben, A. (2025). A computational model of reward learning and habits on social media. [Preprint].
- **citation_short:** Turner et al. (2025)
- **doi:** Not available (preprint; preregistration at https://osf.io/jybhx; code at https://osf.io/fmuks)
- **publication_type:** preprint
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Reward learning and habit formation on social media (Twitter/X). Whether posting behavior is driven by goal-directed reinforcement learning, habits, or a hybrid of both.
- **study_focus_short:** Reward learning and habit formation on social media (Twitter/X)
- **learning_mode_description:** - Learning mode: Learning from social media rewards (Likes) about optimal posting frequency, integrating goal-directed RL and habitual perseveration   - Learning from:     - Source type (social): group (followers providing Likes)     - Source content (social): outcome (number of Likes received on posts)   - Learning about:     - Target type (non-social): self     - Target content (non-social): action/policy (posting latency / frequency)
- **task_description:** Users post on Twitter/X and receive Likes as social feedback. The model characterizes how the latency between successive posts is modulated by the history of Likes received (goal-directed RL component) and by the history of previous posting latencies (habitual component). This is naturalistic social media data, not a laboratory task.
- **task_paradigm:** Social media posting task
- **players:** Single agent (participant), multi-target (followers on Twitter/X providing Likes)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Real-world Twitter posting data; rewards operationalized as number of Likes per post; also tested with Retweets and Likes+Retweets combined
- **method:** online / behavioural
- **method_full:** behavioural (online / computational modeling of naturalistic social media data)
- **main_result:** - Model comparison: RLH1 (hybrid RL-habit, single learning rate) was the winning model in the confirmatory sample (mean AICw = 0.290), outperforming pure RL, pure habit, and baseline models - Model falsification: Empirical data showed significant RL behavioral signature (b = -0.031 [SE = 0.002], p < 0.001), falsifying non-RL models - Posting latency negatively predicted habit weight (b = -0.022 [SE = 0.005], p < 0.001) - Posting latency positively predicted action learning rate (b = 0.047 [SE = 0.005], p < 0.001) - Posting latency did not predict reward learning rate (b = 0.006 [SE = 0.006], p = 0.343) - Age positively predicted habit weight (b = 0.001 [SE = 0.001], p = 0.015) - Males had higher habit weight than females (t(1182) = -1.96, p = 0.050) - No significant relationship between wellbeing (AHI) and any model parameter
- **effect_size:** - Habit weight ~ posting latency: b = -0.022 [SE = 0.005] - Action learning rate ~ posting latency: b = 0.047 [SE = 0.005] - Habit weight ~ age: b = 0.001 [SE = 0.001] - Habit weight ~ gender: t(1182) = -1.96 - RL signature (empirical): b = -0.031 [SE = 0.002] - Note: standardized effect sizes (Cohen's d, r, etc.) not reported
- **learning_from:** group (Twitter followers); social reward outcomes (Likes on posts)
- **learning_about:** self; own posting behavior/policy (posting latency)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** RLH1: Hybrid RL-Habit model (single learning rate). Policy_t = omega_h * Policy[H]_t + (1 - omega_h) * Policy[G]_t, where Policy[H] is habitual (action TD learning) and Policy[G] = C / R-hat (goal-directed RL). 4 free parameters: alpha_r (reward LR), alpha_a (action LR), C (vigour cost), omega_h (habit weight).
- **model_family:** MB/MF hybrid
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Fixed Policy (FP)", "family": "Baseline", "n_params": 1, "metric": "AICw = 0.085"} 2. {"name": "Changing Policy (CP)", "family": "Baseline", "n_params": 3, "metric": "AICw = 0.152"} 3. {"name": "Habitual Policy (HP)", "family": "Habit (TD action learning)", "n_params": 1, "metric": "AICw = 0.061"} 4. {"name": "RL1 (single LR)", "family": "Reinforcement learning", "n_params": 2, "metric": "AICw = 0.042"} 5. {"name": "RL2 (double LR)", "family": "Reinforcement learning", "n_params": 3, "metric": "AICw = 0.088"} 6. {"name": "RLH1 (RL-habit, single LR)", "family": "Hybrid RL-habit", "n_params": 4, "metric": "AICw = 0.290"} 7. {"name": "RLH2 (RL-habit, double LR)", "family": "Hybrid RL-habit", "n_params": 5, "metric": "AICw = 0.283"}  Also compared against Lindstrom et al. (2021) RL model; both RLH models outperformed it.
- **model_mb_mf:** MF (model-free RL component) + habit hybrid. The paper explicitly defines the RL component as model-free and the habit as value-free perseveration. Best described as: MF / habit hybrid.
- **model_params:** - alpha_r (reward learning rate): controls recency-weighting of reward prediction errors. Confirmatory median = 0.032 (RLH1) - C (vigour cost constant): scales relationship between expected reward and posting latency. Confirmatory median = 1.424 (RLH1) - alpha_a (action learning rate) [S]: controls recency-weighting of action prediction errors in habitual system. Confirmatory median = 0.136 (RLH1) - omega_h (habit weight) [S]: relative weight of habitual vs goal-directed controller, 0 = fully goal-directed, 1 = fully habitual. Confirmatory median = 0.944 (RLH1)
- **social_param:** omega_h (habit weight) — governs the balance between habitual (perseverative) and goal-directed (reward-maximizing) posting behavior; relates to individual differences in age, gender, and posting frequency. Also alpha_a (action learning rate) — indexes consistency/predictability of posting behavior over time.
- **social_param_name:** alpha_a
- **social_param_value:** 0.136
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AICw (Akaike Information Criterion weights), individual-level MLE. Also used Bayesian model comparison (BMS) via VBA package. Model falsification used as complementary absolute criterion.
- **how_model_fit:** individual-level-fit (MLE using R 'optim' function, with minimum n_params * 10 random start values)
- **data_type_fit_to:** choice behavior (posting latencies as continuous variable)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 2,696 total Twitter users (discovery sample: N = 1,138 [706 female]; confirmatory sample: N = 1,558 [998 female]); ages 13-99 (mean = 36, SD = 14 in both samples); 684,943 posts total; minimum 80 posts per user
- **population_category:** adolescents
- **population_age_range:** 13–99
- **ecological_validity:** HIGH. Uses real-world naturalistic social media posting data from Twitter/X, not a laboratory task. However, the sample is a convenience sample drawn from users of the Authentic Happiness website who volunteered Twitter handles, introducing self-selection bias. Rewards (Likes) are treated as instantaneous when they actually accrue over time. The model assumes all posts are equivalent actions and that rewards follow a ratio schedule (reward independent of posting latency), which is a simplification.
- **eligibility_flag:** 
- **concerns:** - No standardized effect sizes (Cohen's d, r-squared, etc.) reported for individual difference analyses; only unstandardized regression coefficients - The supplement file in the papers folder is mismatched — it belongs to Lindstrom et al. (2021), not to this Turner et al. paper. The actual supplementary material appears to be embedded in the main text file (from section 1073 onward) - The winning model's habit weight median is very high (0.944), suggesting the habitual component dominates for most users, with RL having relatively little influence on average - Data cannot be shared due to privacy considerations - Cross-sectional correlations only; no causal inference possible - Convenience sample from Authentic Happiness website users; not representative - Model assumes ratio schedule (Likes independent of posting latency), which may not hold in practice - The gender effect on habit weight is borderline significant (p = 0.050)
- **limitations_reported:** Both our model and dataset are simplifications of a complex process"; model considers only two generative processes (habitual and model-free RL) whereas in reality many more cognitive processes govern posting (e.g., model-based RL, social learning); model assumes rewards delivered on ratio schedule such that Likes do not depend on posting latency; model assumes all posts are the same action; related model parameters to individual differences only via cross-sectional correlations; future research needed for causal pathways via longitudinal modelling or experimental intervention
- **limitations_categorized:** model simplicity; limited ecological validity (ratio schedule assumption); task simplicity (all posts treated as same action); limited generalizability (cross-sectional only; convenience sample); no causal inference
- **preregistered:** Yes
- **wc_rule1:** Partial
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 9.0
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - doi: LOW confidence — no DOI found in document; appears to be a preprint - publication_type: MEDIUM confidence — format consistent with preprint but no explicit statement of where submitted/posted (no "bioRxiv" or "PsyArXiv" header visible) - effect_size: MEDIUM confidence — only unstandardized regression coefficients reported; no standardized effect sizes - learning_mode source type: MEDIUM confidence — Likes come from followers (social/group) but could also be conceptualized as "world" (platform-mediated feedback)
- **cannot_find:** DOI; journal or preprint server name; standardized effect sizes
- **other_notes:** The supplementary file `A computational model of reward learning and habits on social media _Supplements.txt` in the papers folder is actually the supplement for Lindstrom et al. (2021) "A computational reward learning account of social media engagement" (Nature Communications), NOT for this Turner et al. paper. The actual supplement for Turner et al. is embedded within the main .txt file starting at approximately line 1073. This is an important discrepancy to note. The paper is notable for being one of the first to model multiple cognitive systems (goal-directed + habitual) in real-world social media data, adapting models from the animal operant conditioning literature. The preregistered split-sample design (discovery + confirmatory) is a methodological strength.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_perseveration
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_MB_MF_hybrid
- tax_rr_model_family = MB_MF_hybrid
- tax_rr_param_MB_MF_balance
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_topic_social_approval_reward
