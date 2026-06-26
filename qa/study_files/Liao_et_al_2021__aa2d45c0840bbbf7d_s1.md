# Liao et al. (2021)

- **study_id:** `aa2d45c0840bbbf7d_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Liao, Z., Huang, L., & Luo, S. (2021). Intranasal oxytocin decreases self-oriented learning. *Psychopharmacology*, *238*, 461–474. https://doi.org/10.1007/s00213-020-05694-7
- **citation_short:** Liao et al. (2021)
- **doi:** 10.1007/s00213-020-05694-7
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Self-oriented reward learning — effect of intranasal oxytocin on learning to obtain rewards for self versus others, using reinforcement learning to model choice variability and learning rate.
- **study_focus_short:** Self-oriented reward learning
- **learning_mode_description:** 
- **task_description:** - **Study 1**: Participants chose between two abstract symbols on each trial; one symbol had 70% reward probability, the other 30%. They played under three conditions (self, other, no one) determining who received the monetary reward. (Lockwood et al. 2016 paradigm) - **Study 2**: Participants chose among four tables in an altered Iowa Gambling Task; each choice produced simultaneous gain/loss outcomes for self and a paired partner, in a 2×2 orthogonal design (self gain/loss × other gain/loss).
- **task_paradigm:** Iowa gambling task
- **players:** - **Study 1**: Single agent (participant), dyadic (same-gender stranger partner, present but in separate room) - **Study 2**: Single agent (participant), dyadic (assigned stranger partner)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** - **Study 1**: Abstract symbols (9 pairs from 52), binary reward feedback (points) - **Study 2**: Four colored rectangles (tables), monetary gain/loss outcomes (¥) for self and other displayed simultaneously
- **method:** pharmacological / behavioural
- **method_full:** behavioural (pharmacological: double-blind, placebo-controlled, between-subjects, intranasal oxytocin)
- **main_result:** Study 1: - IN-OT decreased self-oriented learning performance (self condition: PL M = 0.69 vs. OT M = 0.62; F(1,95) = 4.477, p = .037, η²p = .045) - IN-OT increased choice variability (β) in self condition (MD = 2.168, F(1,95) = 4.59, p = .035) - No significant OT effect on learning rate α (p = .15–.96) - No significant OT effect on other-oriented learning (F(1,95) = 0.740, p = .392, η²p = .008) - Mediation: OT → increased choice variability → decreased self-oriented learning (indirect effect 95% CI: [−0.0431, −0.0031]) - PL group condition effect on learning performance (F(2,96) = 8.143, p = .001, η²p = .145) - Bootstrap: TObs = 47, p < .001  Study 2: - IN-OT decreased self-oriented learning (LPS: MD = 13.732, p = .040) - OT effect on other-oriented learning not significant (MD = 7.682, p = .291, η²p = .011) - Self condition win-stay rate: marginally significant treatment effect (F(1,105) = 3.726, p = .056, η²p = .034) - Self model β: marginally significant treatment effect (PL M = 14.17, OT M = 18.94, F(1,105) = 3.918, p = .050, η²p = .036) - SVO moderation: IN-OT decreased LPS in self-oriented individuals (F(1,33) = 11.926, p = .002, η²p = .265) but not prosocial individuals (F(1,64) = 0.340, p = .562, η²p = .005) - SVO × treatment interaction (F(1,97) = 4.509, p = .036, η²p = .044) - IN-OT decreased α for self-rewards in self-oriented individuals (F(1,33) = 4.954, p = .033, η²p = .131) but not prosocial individuals
- **effect_size:** Study 1: - IN-OT decreased self-oriented learning performance (self condition: PL M = 0.69 vs. OT M = 0.62; F(1,95) = 4.477, p = .037, η²p = .045) - IN-OT increased choice variability (β) in self condition (MD = 2.168, F(1,95) = 4.59, p = .035) - No significant OT effect on learning rate α (p = .15–.96) - No significant OT effect on other-oriented learning (F(1,95) = 0.740, p = .392, η²p = .008) - Mediation: OT → increased choice variability → decreased self-oriented learning (indirect effect 95% CI: [−0.0431, −0.0031]) - PL group condition effect on learning performance (F(2,96) = 8.143, p = .001, η²p = .145) - Bootstrap: TObs = 47, p < .001  Study 2: - IN-OT decreased self-oriented learning (LPS: MD = 13.732, p = .040) - OT effect on other-oriented learning not significant (MD = 7.682, p = .291, η²p = .011) - Self condition win-stay rate: marginally significant treatment effect (F(1,105) = 3.726, p = .056, η²p = .034) - Self model β: marginally significant treatment effect (PL M = 14.17, OT M = 18.94, F(1,105) = 3.918, p = .050, η²p = .036) - SVO moderation: IN-OT decreased LPS in self-oriented individuals (F(1,33) = 11.926, p = .002, η²p = .265) but not prosocial individuals (F(1,64) = 0.340, p = .562, η²p = .005) - SVO × treatment interaction (F(1,97) = 4.509, p = .036, η²p = .044) - IN-OT decreased α for self-rewards in self-oriented individuals (F(1,33) = 4.954, p = .033, η²p = .131) but not prosocial individuals
- **learning_from:** Self; own choice outcomes (reward feedback — probabilistic in Study 1; gain/loss in Study 2)
- **learning_about:** World (stimulus-reward associations); self-oriented vs. other-oriented reward value of stimuli  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** - **Study 1**: Rescorla-Wagner with separate α per condition (α_self, α_other, α_noone; 1 β per condition). Formula: Q_{t+1}(a) = Q_t(a) + α × (R_t − Q_t(a)); softmax with inverse temperature β. - **Study 2**: Comprehensive model with weighted self/other values: Q_t(a) = θ × Q^S_t(a) + (1−θ) × Q^O_t(a), with separate learning rates α₁ (self-reward) and α₂ (other-reward), and a self-interest weighting parameter θ. Softmax with β.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Study 1: - [{"name": "RL model (α, β)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"}] - [{"name": "Null model (α fixed to 0, β free)", "family": "null/random", "n_params": 1, "metric": "BIC"}] - [{"name": "Fixed Alpha Model (α = 0, β free)", "family": "RW variant", "n_params": 1, "metric": "BIC"}] - [{"name": "Fixed Beta Model (α free, β = 1)", "family": "RW variant", "n_params": 1, "metric": "BIC"}]  Study 2: - [{"name": "Comprehensive model (α₁, α₂, θ, β)", "family": "Weighted dual RW", "n_params": 4, "metric": "BIC"}] - [{"name": "Self model (α, β; self-reward only)", "family": "RW", "n_params": 2, "metric": "BIC"}] - [{"name": "Other model (α, β; other-reward only)", "family": "RW", "n_params": 2, "metric": "BIC"}]
- **model_mb_mf:** MF (model-free RL)
- **model_params:** Study 1: - α (learning rate; bounded 0–1) — fitted per participant per condition (self, other, no one). No significant OT effect on α. - β (inverse temperature / choice variability) — fitted per participant per condition. OT group had higher β in self condition (MD = 2.168). Log-transformed for analysis. [Note: paper uses β as exploration/variability, where HIGHER β = MORE random, i.e., this is temperature, not inverse temperature.]  Study 2: - α₁ (learning rate for self-reward) [S] — IN-OT decreased α₁ in self-oriented individuals (OT: M = 0.05, PL: M = 0.12) - α₂ (learning rate for other-reward) [S] - θ (self-interest weight, 0–1) [S] — θ = 1 is completely self-oriented, θ = 0 is completely other-oriented - β (choice variability / inverse temperature)
- **social_param:** - θ (self-interest weight): weight given to self-reward vs. other-reward in the combined value function (Study 2) [S] - α₁ vs. α₂: separate learning rates for self vs. other rewards (Study 2) [S]
- **social_param_name:** α₁
- **social_param_value:** 0.05
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (summed across participants)
- **how_model_fit:** individual-level-fit (MLE per participant per condition)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A — no neuroimaging conducted
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** - Study 1: N = 100 recruited; N = 96 analyzed (49 PL, 47 OT; 50% female; age = 19.52 ± 1.92 years). 4 excluded (1 non-response, 3 menstrual cycle outliers). - Study 2: N = 107 recruited; N = 107 analyzed (54 PL, 53 OT; 57 male, 50 female; age = 19.58 ± 1.87 years). SVO analyses: N = 101 (6 unclassified dropped).
- **population_category:** healthy adults
- **population_age_range:** M=19.52 (SD=1.92)
- **ecological_validity:** Low-to-moderate. Lab-based probabilistic reward learning with abstract symbols (Study 1) and altered Iowa Gambling Task (Study 2). Partner present but in separate room, no face-to-face interaction. Self-other distinction created by task instructions only. Pharmacological manipulation (intranasal oxytocin) adds experimental control but is artificial.
- **eligibility_flag:** 
- **concerns:** - The β parameter is described inconsistently: the text says "A high parameter β would result in similar action probabilities regardless of the expected value of each action, indicating random behavior" — this means β is temperature (not inverse temperature), yet the softmax formula shows β in the exponent as typically used for inverse temperature. This is a notational concern. - Study 1 uses the Lockwood et al. (2016) task but the "social" element is minimal — participant plays for an unseen partner; no social observation or interaction. - Study 2 SVO subgroup analyses had unbalanced and small cell sizes (self-oriented: n = 19 OT, n = 16 PL). - No parameter recovery or model recovery analyses reported. - No simulation of synthetic data before fitting. - The "no one" condition is unusual — reward goes nowhere — and its psychological interpretation is ambiguous.
- **limitations_reported:** - "the interest of individuals was not assessed directly, no conclusion cannot be drawn at this time"; future studies combining neuroimaging and assessment of interests needed; - Effect of OT not assessed under other social contexts — future studies with different contexts needed to confirm context-independent effect; - "other" partner was unfamiliar (stranger) — effect of OT on prosocial behavior toward strangers is mixed; future studies could include familiarity factor; - Working memory not directly measured — cannot examine whether working memory interacts with conditions; - Proportions of individualists and prosocial individuals in PL and OT groups were unbalanced and limited; - More trials might be needed to better capture the learning process in Study 2's more demanding task
- **limitations_categorized:** limited ecological validity; no neuroimaging; small/unbalanced subgroups; no working memory assessment; limited social contexts tested; task simplicity (stranger partner, no real interaction); insufficient trial numbers  ---  ## WC GUIDELINES  1. **Design a good experiment**: Yes — task engages reward learning across self/other/no-one conditions; well-controlled pharmacological manipulation 2. **Design good models**: Partial — compared RL to null/fixed-parameter variants (Study 1) and comprehensive vs. self-only vs. other-only (Study 2), but models are closely related rather than representing competing hypotheses 3. **Simulate, simulate, simulate**: No — no simulation of models before fitting described 4. **Fit the parameters**: Yes — MLE fitting reported, individual-level 5. **Check parameter recovery**: No — no parameter recovery reported 6. **Check model recovery**: No — no confusion matrix or model recovery reported 7. **Fit real data and compare models**: Yes — BIC comparison across models 8. **Validate the winning model**: No — no posterior predictive check or model validation described 9. **Analyze the winning model**: Yes — extracted α and β parameters analyzed via ANOVA, mediation analysis 10. **Report results transparently**: Partial — no mention of shared data or code; but detailed statistical reporting
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
- **flagged_fields:** - β parameter interpretation: MEDIUM confidence — text and formula appear inconsistent regarding whether β is temperature or inverse temperature   - learning_mode classification: MEDIUM confidence — the "social" element is minimal in Study 1 (learning for an unseen other via instruction only, no social observation)   - Study 2 model formula: HIGH confidence — clearly stated in text (Q_t(a) = θ × Q^S_t(a) + (1−θ) × Q^O_t(a))   - Exact mean fitted parameter values for α and β across all conditions: MEDIUM confidence — some values reported in text (e.g., α for self-oriented individuals in Study 2), but full condition-level means for Study 1 not reported in main text or supplement
- **cannot_find:** - Full table of mean fitted parameter values (α, β) by condition × treatment for Study 1   - Full table of mean fitted parameter values (α₁, α₂, θ, β) by treatment for Study 2   - Exact BIC values (only shown in figures, not reported numerically)   - Effect sizes for BIC model comparisons
- **other_notes:** - Paper contains two studies with different tasks — Study 1 uses Lockwood et al. (2016) probabilistic learning task; Study 2 uses altered Iowa Gambling Task (Kwak et al. 2014).   - The "social" component is the beneficiary of reward (self vs. other vs. no one), not social observation or social interaction per se.   - OT effect found selectively for self-oriented learning, not other-oriented learning, in both studies.   - SVO moderation in Study 2 is notable: OT effect on self-oriented learning found only in dispositionally self-oriented individuals.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pharma_oxytocin
- pop_healthy_adults
- rr_pharma_oxytocin
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
- tax_param_temperature
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_temperature
- tax_rr_primary_topic = self_other_boundary
- tax_rr_secondary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_rr_topic_self_other_boundary
- tax_topic_prosocial_altruism
- tax_topic_self_other_boundary
