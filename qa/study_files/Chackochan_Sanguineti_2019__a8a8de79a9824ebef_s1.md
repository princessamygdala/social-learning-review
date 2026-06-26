# Chackochan & Sanguineti (2019)

- **study_id:** `a8a8de79a9824ebef_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Chackochan, V. T., & Sanguineti, V. (2019). Incomplete information about the partner affects the development of collaborative strategies in joint action. *PLoS Computational Biology*, *15*(12), e1006385. https://doi.org/10.1371/journal.pcbi.1006385
- **citation_short:** Chackochan & Sanguineti (2019)
- **doi:** 10.1371/journal.pcbi.1006385
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Psychology
- **affiliations_raw:** DepartmentofInformatics,Bioengineering,RoboticsandSystemsEngineering,UniversityofGenoa,; laborationisachieved(lessinformation,slowerlearning),butalsotheactualcollaboration; laborativestrategiesinjoint connectedthroughavirtualspring,butcannotseeeachother; laborations,butthelearnedcollaborationstrategydependsonthereliabilityof; laborationbeaffectedifinformationabouttheirpartnerwereunreliableor; laborativestrategieswithincompleteinformationaboutthepartner; etheory,weshowthatsubjectpairs(dyads)arecapableofdeveloping; laborativestrategiesinjointactionareshapedbythetrade-off; emails: vittorio.sangui
- **code_url:** 

## Computational level
- **study_focus:** Joint action learning / collaboration learning — how dyads develop collaborative movement strategies when information about the partner is incomplete, using a motor version of a battle-of-sexes game.
- **study_focus_short:** Joint action learning / collaboration learning
- **learning_mode_description:** - Learning mode: Learning to coordinate movement trajectories with a mechanically coupled partner under varying information conditions   - Learning from:     - Source type (social): other (partner in dyad)       - If joint: **joint** (interaction forces are jointly produced)     - Source content (social): action/policy (partner's motor commands inferred through haptic/visual coupling)       - If joint: **joint** (interaction forces are jointly generated)   - Learning about:     - Target type (social): other (partner in dyad)     - Target content (social): action/policy (partner's control strategy / motor plan)
- **task_description:** Two participants (a dyad) were mechanically connected via a virtual spring and performed reaching movements from the same start to the same target, but through different via-points. They could not see or communicate with each other; information about the partner was manipulated across three groups (haptic only, visuo-haptic, partner visible), and participants learned to collaborate over 120 training trials to minimize interaction forces while reaching their own via-point.
- **task_paradigm:** Joint action / coordination
- **players:** Multi-agent (dyad), symmetric (Player 1 and Player 2 with equivalent but conflicting goals)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Haptic interface cursors, via-point circles on screen, interaction force display (VH group) or partner cursor display (PV group), numerical score feedback (0–100)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - All dyads converged to stable collaboration strategies over training (significant Time effect on score: F(2,24) = 51, P < 10⁻⁴) - Dyads with more partner information (PV group) converged faster and closer to optimal Nash equilibrium strategies (significant Group effect on score: F(2,12) = 12, P = 0.0015) - Less information led to leader-follower role alternation (sub-optimal no-partner strategy); more information led to synchronous behavior (Nash-like; significant Group effect on ΔLI at VP2: F(2,12) = 5.84, P = 0.016) - Fictitious play model with Bayesian state estimation reproduced experimental patterns across all three information conditions
- **effect_size:** - Score: Time effect F(2,24) = 51, Group effect F(2,12) = 12 - Interaction force: Time effect F(2,24) = 37.4 - Min distance from partner VP (Player 1): Time F(2,24) = 40, Group F(2,12) = 7.8, Group×Time F(4,24) = 5.21 - Min distance from partner VP (Player 2): Time F(2,24) = 36.4, Group F(2,12) = 8.9, Group×Time F(4,24) = 4.32 - ΔLI at VP2: Group F(2,12) = 5.84; H vs VH t(7.75) = 2.63, P = 0.03; H vs PV t(7.31) = 3.29, P = 0.01 - (Note: only F-statistics and t-values reported; no standardized effect sizes such as Cohen's d, η², or r² were provided)
- **learning_from:** Other (partner); joint interaction forces and (depending on group) partner cursor position. Source: other / joint.
- **learning_about:** Other (partner); partner's motor control strategy/actions. Target: other.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Differential game theory (Nash equilibrium) + Bayesian state estimation (Kalman filter) + fictitious play learning. Linear-quadratic differential game with quadratic cost functionals; state observer extended to estimate partner's control input; iterative fictitious play updates partner model trial-by-trial. Key parameters: spring stiffness k = 150 N/m, mass m = 2 kg, activation time constant τ = 40 ms, effort weight r = 1, sensory noise variances σ²_x = 1.72 mm², σ²_xd = 352 mm²/s², σ²_f = 2² N² (H) or 0.05² N² (VH/PV), Aᵤ = 1, Σε = 1 N².
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "Nash equilibrium (optimal non-cooperative)", "family": "Differential game theory (LQ)", "n_params": "~10 (physical + noise params; no free cognitive params except r)", "metric": "qualitative comparison to empirical data"},   {"name": "No-partner strategy (LQG independent)", "family": "Optimal control (LQG)", "n_params": "same physical params", "metric": "qualitative comparison to empirical data"},   {"name": "Fictitious play with Bayesian estimation (H condition)", "family": "Game theory + Kalman filter", "n_params": "same + sensory noise σ²_f = 4 N²", "metric": "qualitative comparison"},   {"name": "Fictitious play with Bayesian estimation (VH condition)", "family": "Game theory + Kalman filter", "n_params": "same + sensory noise σ²_f = 0.0025 N²", "metric": "qualitative comparison"},   {"name": "Fictitious play with Bayesian estimation (PV condition)", "family": "Game theory + Kalman filter", "n_params": "same + partner position visible", "metric": "qualitative comparison"} ]
- **model_mb_mf:** MB (model-based — uses forward model of dyad dynamics + Kalman state estimation)
- **model_params:** - k = 150 N/m (spring stiffness) - m = 2 kg (point mass per player) - b = 10 N·s/m (viscous damping) - τ = 40 ms (muscle activation time constant) - r = 1 (effort-accuracy trade-off weight; only free parameter) - σ²_x = 1.72 mm² (position sensory noise) - σ²_xd = 352 mm²/s² (velocity sensory noise) - σ²_f = 4 N² (force sensory noise, H group) / 0.0025 N² (VH group) [S] — the key social parameter; determines reliability of partner information - Aᵤ = 1 (partner input smoothness prior) - Σε = 1 N² (partner input noise prior) - Σu = 1 N² (motor noise variance) - Qᵢ(t): state cost matrices (derived from task weights wₚ, wᵥ, wᵥₚ, w_f) - Rᵢ(t): effort cost matrices (scaled by r) - Lᵢ(t): feedback controller gains (computed, not fitted) - Kᵢ(t): Kalman gains (computed, not fitted)
- **social_param:** σ²_f (force sensory noise variance) [S] — determines the reliability of haptic information about the partner's actions; lower values mean more reliable partner information, leading to Nash-like (synchronous) collaboration; higher values lead to sub-optimal leader-follower strategies. Also, the partner model portion of the Kalman filter (Aᵤ, Σε) governs the prior belief about partner's control input smoothness.
- **social_param_name:** σ²_f = 4 N²
- **social_param_value:** 4
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Qualitative comparison of simulated vs empirical trajectories, interaction forces, minimum via-point distances, and leadership indices across the three information conditions. No formal quantitative model comparison metric (e.g., BIC, AIC) was used.
- **how_model_fit:** simulate-and-compare (model parameters were set from physical measurements or biologically motivated values; the model was simulated and qualitatively compared to empirical data patterns; no parameter fitting to behavioral data)
- **data_type_fit_to:** choice behavior (movement trajectories, interaction forces, leadership indices — qualitative comparison only)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging). Authors speculatively discuss cerebellum (internal model of dynamics) and superior temporal sulcus (action observation) but provide no neural data.
- **coordinates_peak:** N/A — no neuroimaging conducted
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 30 (15 dyads; 5 dyads per group: H group 25 ± 5 y, 9M + 1F; VH group 24 ± 3 y, 8M + 2F; PV group 24 ± 3 y, 6M + 4F). All right-handed, naive to task, no neurological or motor impairment.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate-to-low. The task uses a motor version of the battle-of-sexes game with haptic robots, which is a laboratory abstraction. However, the physical coupling through a virtual spring and the conflicting goals do capture core features of real-world joint physical coordination (e.g., carrying objects together, dancing). The lack of verbal communication and visual contact is a strong laboratory constraint.
- **eligibility_flag:** 
- **concerns:** - Very small sample size (5 dyads per group, N = 10 participants per group) - No formal quantitative model fitting or model comparison — model parameters were set a priori from physical/biological constraints, and comparison to data was purely qualitative - No statistical quantification of model-data fit (e.g., R², RMSE) - No standardized effect sizes reported (only F-statistics and raw p-values) - The model's only free parameter (r = 1) was not fitted to data - Bonferroni correction applied inconsistently (mentioned for some but not all comparisons)
- **limitations_reported:** Each experimental group involved a total of ten participants, i.e. five dyads. Dyads performance was quite consistent within each group. Nevertheless, due to the limited sample size, the generalizability of the above findings must be taken cautiously."; "To keep the model simple, as in related studies we only included a large, additive Gaussian noise term. This may have underestimated the between-trial variability."; "our implementation of fictitious play only uses the most recent estimate of partner's input. This is less robust than estimating the distribution of partner inputs over multiple repetitions"; "the cost functional used in simulation can be considered as functionally equivalent to the score function used in the experiments" (acknowledging differences between model cost and experimental score)
- **limitations_categorized:** sample size; model simplicity (additive vs. multiplicative noise); limited generalizability; simplified learning rule (single-trial partner estimate vs. distribution); model-task mismatch (quadratic cost vs. sigmoid score)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM — only F-statistics and t-values reported; no standardized effect sizes (Cohen's d, η², etc.) - model_comparison_metric: LOW — no formal quantitative comparison; purely qualitative - how_model_fit: MEDIUM — described as simulate-and-compare, but no formal fitting procedure - data_type_fit_to: MEDIUM — qualitative comparison only, not formal model fitting
- **cannot_find:** - Standardized effect sizes (Cohen's d, η², r²) — not reported in paper - Formal model comparison statistics (BIC, AIC, log-likelihood) — not used - Code availability — model is fully specified mathematically but code sharing not explicitly mentioned - Parameter recovery or model recovery analyses — not performed
- **other_notes:** This paper takes a motor control / game theory approach to social learning, which is somewhat unusual for the computational psychiatry / social neuroscience literature that dominates this review. The computational model is fully specified (differential game theory + Kalman filter + fictitious play) but is used for generating theoretical predictions rather than being formally fit to data. The key insight is that the reliability of information about the partner (operationalized through sensory noise variance) determines whether dyads converge to optimal Nash equilibrium strategies (synchronous) or sub-optimal leader-follower strategies. The paper was published in PLoS Computational Biology.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_model_MB
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_primary_topic = cooperation
- tax_rr_topic_cooperation
- tax_topic_cooperation
