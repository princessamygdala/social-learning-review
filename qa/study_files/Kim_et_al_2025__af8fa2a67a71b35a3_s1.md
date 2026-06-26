# Kim et al. (2025)

- **study_id:** `af8fa2a67a71b35a3_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Kim, Y., Kim, K. I., & Kim, H. (2025). Social observation differentially affects prosocial learning of selfish and prosocial people. *Frontiers in Psychology*, *16*, 1440302. https://doi.org/10.3389/fpsyg.2025.1440302
- **citation_short:** Kim et al. (2025)
- **doi:** 10.3389/fpsyg.2025.1440302
- **publication_type:** peer-reviewed journal (frontiers in psychology, open access)
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** ether, these findings indicate that individuals strive to be perceived raise a critical question: Does the limited effect of social observation; Laboratory of Social and Decision Neuroscience, School of Psychology, Korea University, Seoul,; mitted, who were already more prosocial showed no significant changes in prosociality,; ether individuals with intrinsic prosocial tendencies also exhibit a; University of Campania Luigi Vanvitelli, Italy; University of Indonesia, Indonesia; mitted which does not comply with; centered tendencies,; emails: hackjinkim@korea.ac.kr
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning — how social observation (audience effect) differentially modulates reinforcement learning for self- vs. other-regarding rewards depending on individuals' intrinsic prosocial tendencies.
- **study_focus_short:** Prosocial learning
- **learning_mode_description:** - Learning mode: Learning from reward outcomes (self- and other-regarding) about stimulus-reward associations under social observation   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (binary reward feedback — point/no point)   - Learning about:     - Target type (social): other (anonymous next participant) **and** Target type (non-social): self     - Target content (non-social): stimulus (fractal image reward probabilities)     - Note: The "other" reward condition involves learning stimulus-reward associations where rewards benefit another person, making the target socially relevant even though the content learned is stimulus values.
- **task_description:** Participants performed a two-armed bandit task (Prosocial Reinforcement Learning Task) under "self" and "other" reward conditions across three blocks; in the second block, participants in the observation group were told another participant was watching their screen in real time via Gather.town.
- **task_paradigm:** Two-armed bandit
- **players:** Single agent (participant), single anonymous target (next participant as "other" reward recipient); 2 between-subject groups (Observation vs. Control) × 2 post-hoc groups (Selfish vs. Prosocial).
- **n_players:** single agent (1)
- **partner_type:** human (live)
- **stimuli:** Fractal images (pairs matched for similarity and preference), binary reward feedback (point/no point; 70/30 probability with reversals).
- **method:** online / behavioural
- **method_full:** Behavioural (online, via Gather.town + psyToolKit)
- **main_result:** - 4-way interaction (Observation × PLS group × Block × Reward) on learning rates: F(2, 196) = 3.616, p = 0.029 - OBS-Selfish group, Block 1→2: α_other increased (t(31) = −4.918, p < .001, adjusted p < .001); α_self decreased (t(31) = 2.790, p = .009, adjusted p = .044) - PLS change (Block 1→2) larger in OBS-Selfish vs. CON-Selfish: t(63) = 2.499, p = .015 - OBS-Prosocial group: marginal increase in α_self (t(16) = −2.532, p = .022, adjusted p = .053); no significant change in α_other - Posterior predictive check: r = 0.72 between actual and predicted HRP - PLS correlated with HRP difference: r(100) = 0.31, p < .001 - PLS correlated with RT difference: r(100) = −0.251, p = .011 - PLS marginal correlation with SVO survey: r(100) = 0.185, p = .063 - Effect sizes: η²_p = 0.103 (from prior study used for power analysis; partial eta-squared for own 4-way interaction not explicitly reported — **flagged**)
- **effect_size:** - 4-way interaction (Observation × PLS group × Block × Reward) on learning rates: F(2, 196) = 3.616, p = 0.029 - OBS-Selfish group, Block 1→2: α_other increased (t(31) = −4.918, p < .001, adjusted p < .001); α_self decreased (t(31) = 2.790, p = .009, adjusted p = .044) - PLS change (Block 1→2) larger in OBS-Selfish vs. CON-Selfish: t(63) = 2.499, p = .015 - OBS-Prosocial group: marginal increase in α_self (t(16) = −2.532, p = .022, adjusted p = .053); no significant change in α_other - Posterior predictive check: r = 0.72 between actual and predicted HRP - PLS correlated with HRP difference: r(100) = 0.31, p < .001 - PLS correlated with RT difference: r(100) = −0.251, p = .011 - PLS marginal correlation with SVO survey: r(100) = 0.185, p = .063 - Effect sizes: η²_p = 0.103 (from prior study used for power analysis; partial eta-squared for own 4-way interaction not explicitly reported — **flagged**)
- **learning_from:** Self; own reward outcomes (binary feedback on chosen fractal) in self- and other-reward conditions.
- **learning_about:** Stimulus-reward associations (fractal image values) for self-reward and other-reward (anonymous next participant).  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Rescorla-Wagner with separate parameters per reward condition: M2 (α_self, α_other, τ_self, τ_other) — 4 free parameters. Softmax action selection: P(t,a) = 1 / (1 + exp(−τ(V(t,a) − V(t,b)))); value update: V(t+1,a) = V(t,a) + α(R(t) − V(t,a))·C(t,a).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. M0 — Null model (random choice, P = 0.5), 0 params 2. M1 — Shared parameters across reward conditions (α, τ), 2 params 3. M2 — Separate parameters per reward condition (α_self, α_other, τ_self, τ_other), 4 params [WINNER]
- **model_mb_mf:** MF (model-free)
- **model_params:** - α_self: learning rate for self-reward condition - α_other: learning rate for other-reward condition [S] - τ_self: inverse temperature for self-reward condition - τ_other: inverse temperature for other-reward condition [S] - Mean fitted values: not reported as group-level means (only individual-level fitting described; distributions shown in figures but exact means not stated in text — **flagged**)
- **social_param:** α_other (learning rate for other-regarding rewards); τ_other (inverse temperature for other-regarding rewards). The difference PLS = α_other − α_self indexes prosocial learning sensitivity.
- **social_param_name:** α_other
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion). Winning model (M2) vs. M1: ΔBIC = 125.56 (Block 1), 133.71 (Block 2), 143.04 (Block 3). Winning model vs. M0: ΔBIC = 654.5 (Block 1), 714.97 (Block 2), 687.27 (Block 3).
- **how_model_fit:** Individual-level fit (maximum likelihood estimation per participant per block)
- **data_type_fit_to:** Choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging)  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 102 (after exclusions from 112 recruited; 49 OBS, 53 CON; 69 females total; mean age = 23.5 years, range 18–30). OBS group: 32 Selfish, 17 Prosocial. CON group: 33 Selfish, 20 Prosocial.
- **population_category:** healthy adults
- **population_age_range:** 18–30
- **ecological_validity:** Online experiment using Gather.town metaverse platform increases ecological validity of the social observation manipulation relative to lab settings; however, the "other" recipient is anonymous and never interacted with, and the task uses abstract fractal stimuli with small stakes (~$6.70 compensation), limiting real-world generalizability.
- **eligibility_flag:** 
- **concerns:** - Effect size (η²_p) for the key 4-way interaction not explicitly reported — only F and p given - Asymmetric group sizes (Selfish ~64% vs. Prosocial ~36%) based on post-hoc median split of PLS - Post-hoc grouping (Selfish/Prosocial) based on Block 1 performance introduces circularity risk - No parameter recovery or model recovery analyses reported - Fitted parameter means not reported in text or supplement - Inverse temperature showed no relationship with learning indices, raising questions about its interpretability
- **limitations_reported:** the differential social observation effect was solely evident in learning rates"; "our experimental setting did not show any relationship between inverse temperature and other learning indices"; "the collection of cases for each selfish and prosocial learning tendency group was asymmetric — almost 64% of the participants exhibited higher learning rates for the 'self' than 'other' reward conditions"; caution about interpreting learning rate parameters in RL paradigms (citing Zhang et al., 2020)
- **limitations_categorized:** Limited generalizability of effects (only learning rates, not inverse temperatures); asymmetric group sizes; task simplicity; parameter interpretability concerns  ---  ## WILSON & COLLINS (2019) CHECKLIST  1. **Design a good experiment**: Yes — PRLT with self/other conditions, observation manipulation, control group 2. **Design good models**: Partial — 3 models tested (null, shared, separate params) but limited model space; no alternative learning architectures (e.g., asymmetric learning rates for positive/negative PE) 3. **Simulate, simulate, simulate**: Partial — Simulated predicted HRP across parameter combinations (Fig 2C-D) but no full parameter/model recovery simulation prior to fitting 4. **Fit the parameters**: Yes — MLE individual-level fitting 5. **Check parameter recovery**: No — no parameter recovery analysis 6. **Check model recovery**: No — no confusion matrix or model recovery 7. **Fit real data and compare models**: Yes — BIC comparison across 3 models 8. **Validate the winning model**: Yes — posterior predictive check (r = 0.72 between actual and predicted HRP) 9. **Analyze the winning model**: Yes — α parameters used as dependent variables in factorial ANOVA; PLS derived from parameters 10. **Report results transparently**: Partial — data said to be in supplementary material; no code repository mentioned  ---  ## FLAGGED FIELDS  - `effect_size`: Partial eta-squared for the key 4-way interaction not reported- `model_params` mean fitted values: Not reported in text or supplement (HIGH confidence they are missing) - `preregistered`: Not reported in paper (HIGH confidence it is simply not mentioned) - Inverse temperature interpretation: Authors acknowledge τ showed no meaningful variance — concern about model specification  ## CANNOT_FIND - Mean fitted parameter values (α, τ) by group and block - Effect size (η²_p or similar) for the 4-way ANOVA interaction - Preregistration status - Code/data repository link  ## OTHER NOTES - The PLS (Prosocial Learning Sensitivity = α_other − α_self) metric and the Selfish/Prosocial grouping are based on Block 1 (pre-observation) parameters, which is methodologically reasonable but introduces some circularity since Block 1 α values are also part of the repeated-measures ANOVA. - Task design follows Lockwood et al. (2016) and Sul et al. (2015) prosocial RL paradigm. - The supplement contains only similarity ratings (Table S1) and supplementary figures (Figs S1-S3) for HRP, RT, and inverse temperature analyses — no additional model details, no coordinate tables, no additional model specifications.  ## RE_EXTRACT_FLAG: false
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** yes
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_multiplayer_live
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
- tax_rr_param_temperature
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = social_approval_reward
- tax_rr_topic_prosocial_altruism
- tax_rr_topic_social_approval_reward
- tax_topic_prosocial_altruism
- tax_topic_social_approval_reward
