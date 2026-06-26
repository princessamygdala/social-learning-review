# Charpentier et al. (2024)

- **study_id:** `afd5b711e4d35db97_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Charpentier, C. J., Wu, Q., Min, S., Ding, W., Cockburn, J., & O'Doherty, J. P. (2024). Heterogeneity in strategy use during arbitration between experiential and observational learning. *Nature Communications*, *15*, 4436. https://doi.org/10.1038/s41467-024-48548-y
- **citation_short:** Charpentier et al. (2024)
- **doi:** 10.1038/s41467-024-48548-y
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** ethertheweightattributedtoeachstrategybeforemakingadeci- Methodsfordetails)performedanoveltaskonlinedesignedtosepa-; mitation–thetendencytorepeatotherpeople’s anxietyarelikelytobesensitivetothecomputationalheterogeneityin; ether and how people may engage dynamic howparticipantssolvethistask,andthatindividualscanbereliably; DivisionofHumanitiesandSocialSciences,CaliforniaInstituteofTechnology,Pasadena,CA,USA; lable in the dynamically arbitrate between model-free and model-based; DepartmentofPsychology&BrainandBehaviorInstitute,; etheleadinguidingbehaviorwhentheirpredic-; UniversityofMaryland,Co
- **code_url:** https://github.com/ccharpen/OL_EL_

## Computational level
- **study_focus:** Observational learning; arbitration between experiential and observational learning; individual differences in social learning strategy use
- **study_focus_short:** Observational learning
- **learning_mode_description:** - Learning mode: Arbitrating between learning from direct experience of reward outcomes (experiential learning) and learning from observing another agent's choices (observational learning), with the balance between strategies driven by the reliability/uncertainty of each information source.   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (reward obtained from chosen token)     - Source type (social): other (partner/observed agent)       - Source content (social): action/policy (partner's box choice, from which token goal is inferred)   - Learning about:     - Target type (non-social): world       - Target content (non-social): state (which token is currently more valuable/rewarding)
- **task_description:** Participants observe another agent choose between two boxes (each yielding different tokens) and then choose between two tokens themselves, receiving a reward outcome. The task manipulates uncertainty in both the box-to-token transition probabilities (OL uncertainty) and the token reward probabilities (EL uncertainty), including reversals, across 8 blocks of 20 trials.
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant), single observed agent (simulated partner whose actions were replayed)
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract fractals (boxes), colored tokens (blue/orange), monetary reward outcomes (0–99 points)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Both EL and OL strategies were significantly used (Study 1: EL β = 0.357, SE = 0.051, P < 0.001; OL β = 0.216, SE = 0.026, P < 0.001; Study 2: EL β = 0.519, SE = 0.025, P < 0.001; OL β = 0.241, SE = 0.012, P < 0.001) - Significant interaction between EL and OL uncertainty trial types on strategy preference (Study 1: η²p = 0.005; Study 2: η²p = 0.003) - No single winning model: participants classified into 5 groups (Baseline ~17–20%, EL-only ~5–17%, OL-only ~19–32%, Fixed mixture ~11–33%, Dynamic arbitration ~21–27%) - Dynamic arbitration group showed steepest learning curves and most extreme uncertainty-driven modulation of strategy - Groups differed on transdiagnostic symptom dimensions: Baseline group showed high autistic traits/low trait anxiety; Dynamic arbitration group showed low autistic traits/high trait anxiety (interaction: F(28,3948) = 2.38, P < 0.001, η²p = 0.017)
- **effect_size:** - Learning accuracy above chance: Study 1 d = 0.94; Study 2 d = 1.25 - OL uncertainty on strategy: Study 1 η²p = 0.038; Study 2 η²p = 0.044 - EL uncertainty on strategy: Study 1 η²p = 0.045; Study 2 η²p = 0.077 - Group × effect type interaction: Study 1 η²p = 0.450; Study 2 η²p = 0.376 - Dynamic arbitration vs Fixed mixture arbitration index: Study 1 d = 1.70; Study 2 d = 0.836 - Baseline vs DynArb autistic traits difference: d = 0.642 - Factor × group interaction on symptoms: η²p = 0.017
- **learning_from:** Self (own reward outcomes from chosen tokens) and other (observed partner's box choices); source: self + other
- **learning_about:** World (which token is currently more valuable/rewarding); target: world  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** No single winning model across all participants. Five models compared; participants classified by best-fitting individual model. Dynamic arbitration model: ω_OL>EL(t) = σ(R_OL(t) − R_EL(t) + δ_OL>EL), where reliability is computed from unsigned prediction errors; P(or) = ω_OL>EL * P_obs(or) + (1 − ω_OL>EL) * P_exp(or). (6 params: α_exp, β_exp, μ, α_obs, β_obs, δ_OL>EL)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Baseline", "family": "Heuristic (color bias, L/R bias, sticky action, action imitation)", "n_params": 4, "metric": "AIC, OOS accuracy, model frequency (hierarchical Bayesian)"},   {"name": "Experiential Learning (EL)", "family": "Rescorla-Wagner with magnitude boost", "n_params": 3, "metric": "AIC, OOS accuracy, model frequency"},   {"name": "Observational Learning (OL)", "family": "Rescorla-Wagner (transition learning)", "n_params": 2, "metric": "AIC, OOS accuracy, model frequency"},   {"name": "Fixed Mixture", "family": "Weighted combination of EL + OL with fixed ω", "n_params": 6, "metric": "AIC, OOS accuracy, model frequency"},   {"name": "Dynamic Arbitration", "family": "Reliability-weighted mixture of EL + OL", "n_params": 6, "metric": "AIC, OOS accuracy, model frequency"} ]
- **model_mb_mf:** MF (EL component is model-free reward learning; OL component learns transition probabilities but in a cached manner; arbitration is based on prediction errors, not planning)
- **model_params:** - EL model: α_exp (experiential learning rate), β_exp (inverse temperature), μ (magnitude boosting effect) - OL model: α_obs (observational learning rate) [S], β_obs (observational inverse temperature) [S] - Fixed mixture: α_exp, β_exp, μ, α_obs [S], β_obs [S], ω_OL>EL [S] (fixed weight for OL over EL) - Dynamic arbitration: α_exp, β_exp, μ, α_obs [S], β_obs [S], δ_OL>EL [S] (bias parameter for OL over EL in arbitration) - Baseline: color bias, left-right bias, sticky action bias, action imitation bias [S] - Mean fitted values not reported in main text.
- **social_param:** - α_obs: observational learning rate governing how quickly the agent updates beliefs about box-token transition probabilities from observing the partner's choices [S] - ω_OL>EL / δ_OL>EL: weight/bias parameter governing reliance on observational vs experiential learning [S]
- **social_param_name:** - α_obs
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC, out-of-sample predictive accuracy (leave-one-block-out cross-validation), hierarchical Bayesian model frequency (via cbm toolbox), individual model responsibility values
- **how_model_fit:** individual-level-fit (individual fits followed by hierarchical Bayesian fitting via cbm toolbox with Laplace approximation)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Study 1: N = 128 (126 after exclusion for missing trials; 56 females, 71 males, 1 non-binary; mean age = 32.84 ± 10.90 SD). Study 2: N = 493 (290 females, 199 males, 4 non-binary; mean age = 28.48 ± 9.90 SD). Pooled sample for factor analysis: N = 568 after careless responding exclusion.
- **population_category:** healthy adults
- **population_age_range:** M=32.84
- **ecological_validity:** Low-moderate. Online task with simulated partner (replayed actions from an RL model, not a real person). Abstract fractals and tokens; no face-to-face social interaction. Participants were told the partner was a real person whose actions were replayed. The online setting improves sample size but reduces experimental control.
- **eligibility_flag:** 
- **concerns:** - The "other agent" was simulated by an RL model with high consistency (β = 10, LR = 0.8), not a real person — participants were told it was a replay of another participant's choices. This limits the social richness of the observational learning. - Pooling two studies for the factor analysis may introduce study-specific confounds, though study was controlled for as a covariate. - The uncertainty manipulation was asymmetric across EL and OL by design (OL uncertainty blocks lasted longer), though trial-level definitions mitigated this. - Mean fitted parameter values are not reported.
- **limitations_reported:** Pooling two datasets for the factor analysis is a limitation warranting replication in future large-scale studies; OL and EL strategies may not be matched in complexity, working memory demands, or cognitive processes; uncertainty conditions were asymmetric across strategies by design; trial-level uncertainty definition was based on immediately preceding trials and could involve more sophisticated definitions over longer timescales; other factors than uncertainty (e.g., partner expertise, cooperative vs competitive context, stakes) could drive arbitration; the interpretability of behavior in the baseline non-learner group is limited as more than one strategy was included and strategies aren't necessarily reflective of underlying cognitive mechanisms; no assessment of whether other reliability computations might perform better
- **limitations_categorized:** Limited generalizability (pooled samples); task simplicity (asymmetric uncertainty manipulation); limited ecological validity (simulated partner); limited model space (other arbitration implementations not tested); interpretability of non-learner group; task complexity mismatch between strategies
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
- **wc_rule10:** Yes
- **wc_score:** 10
- **wc_total:** 10.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params mean fitted values: LOW — not reported in main text or accessible supplement; "Formula not available for mean parameter values" - model_mb_mf: MEDIUM — classified as MF but the OL component involves learning transition probabilities (which has model-based features); the paper does not explicitly label the models as MB or MF in the EL/OL context - learning_about target type: MEDIUM — classified as "world" (which token is valuable) but could also be argued as learning about self (own reward contingencies); the paper frames it as learning which token is currently valuable
- **cannot_find:** - Mean fitted parameter values for each model - Supplement not accessible (only online version referenced at doi link; no supplement .txt file found in papers folder)
- **other_notes:** - This paper has two independent studies (Study 1 and Study 2) but they use the same task and models — the second study is a replication. They should be treated as a single extraction row (one paper, one task paradigm, replicated across two samples). - Supplement referenced extensively (Figs. S1–S9, Tables S1–S5) but not available in the papers folder. The main text contains sufficient detail for model equations and behavioral analyses, but mean fitted parameter values and some supplementary analyses are missing. - The paper is exemplary in its Wilson & Collins adherence — all 10 guidelines are met. - Code and data are publicly available on GitHub. - The "social agent" is automated (RL-generated choices replayed), which should be flagged per CLAUDE.md instructions, though the paper still clearly qualifies as studying observational learning in a social context.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_social_info_search
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_social_info_search
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = imitation_emulation
- tax_rr_topic_imitation_emulation
- tax_rr_topic_social_info_use
- tax_topic_imitation_emulation
- tax_topic_social_info_use
