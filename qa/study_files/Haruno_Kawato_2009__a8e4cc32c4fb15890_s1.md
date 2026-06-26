# Haruno & Kawato (2009)

- **study_id:** `a8e4cc32c4fb15890_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Haruno, M., & Kawato, M. (2009). Activity in the superior temporal sulcus highlights learning competence in an interaction game. *The Journal of Neuroscience*, *29*(14), 4542-4547.
- **citation_short:** Haruno & Kawato (2009)
- **doi:** 10.1523/JNEUROSCI.2707-08.2009
- **publication_type:** peer-reviewed journal
- **year:** 2009.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** etheory(Camerer,2003)andmotorcontrol(Harunoet; Laboratories,Kyoto619-0288,Japan; Laboratories,; MitsuoKawato; ethankK; ethods; emails: mharuno@atr.jp
- **code_url:** 

## Computational level
- **study_focus:** Interactive reinforcement learning; individual differences in learning competence during a prisoner's dilemma game with computer agents -- specifically whether subjects use mentalizing (model-based prediction of opponent strategy) versus simple action-reward association.
- **study_focus_short:** Interactive reinforcement learning
- **learning_mode_description:** - Learning mode: Learning from opponent's actions (contingent on own previous behavior) about optimal cooperative/defection strategy   - Learning from:     - Source type (social): other (computer agent representing social partner)     - Source content (social): action/policy (agent's cooperation/defection contingent on subject's previous action)   - Learning about:     - Target type (social): other (agent's strategy)       - Also: Target type (non-social): world (action-reward contingencies)     - Target content (non-social): outcome (monetary reward)
- **task_description:** Subjects played a repeated prisoner's dilemma game against two computer agents in an fMRI scanner: agent A (tit-for-tat, repeats subject's previous action) and agent B (stochastic cooperator, 70% cooperation probability regardless of subject's behavior). Subjects chose to cooperate or defect on each trial to maximize monetary reward.
- **task_paradigm:** Prisoner's dilemma
- **players:** Single agent (participant), multi-target (2 computer agents: tit-for-tat agent A, stochastic agent B)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Neutral human faces (different for each agent, randomized across subjects), binary choice (cooperate/defect), monetary outcomes
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Group I (learned optimally for both agents) showed significantly greater STS activity correlated with reward prediction than Group II (learned only for agent B), for both agent A and agent B (p < 0.001, uncorrected, cluster > 10 voxels)   - STS activity in Group I increased over learning (later > earlier trials; p < 0.05, t test at peak voxel)   - Individual STS activity predicted learning performance (average reward) in Group I: agent A (r, p = 0.024) and agent B (r, p = 0.025); not significant in Group II   - Reward for agent A significantly larger in Group I than II (p = 0.000064, t test)   - Reward-related brain structures (striatum, prefrontal, ACC, posterior cortices) similarly recruited by both groups   - Effect sizes: not reported as Cohen's d, r, eta-squared, or beta; only p-values and T-maps provided
- **effect_size:** - Main Results:   - Group I (learned optimally for both agents) showed significantly greater STS activity correlated with reward prediction than Group II (learned only for agent B), for both agent A and agent B (p < 0.001, uncorrected, cluster > 10 voxels)   - STS activity in Group I increased over learning (later > earlier trials; p < 0.05, t test at peak voxel)   - Individual STS activity predicted learning performance (average reward) in Group I: agent A (r, p = 0.024) and agent B (r, p = 0.025); not significant in Group II   - Reward for agent A significantly larger in Group I than II (p = 0.000064, t test)   - Reward-related brain structures (striatum, prefrontal, ACC, posterior cortices) similarly recruited by both groups   - Effect sizes: not reported as Cohen's d, r, eta-squared, or beta; only p-values and T-maps provided
- **learning_from:** Other (computer agent's action/strategy); source: other agent's cooperation/defection behavior
- **learning_about:** Action-reward associations; optimal behavioral strategy (cooperate/defect) for each agent; target: other (agent's strategy) and world (reward outcomes)  ---  ### 3. ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Q-learning Model I: Q_t(ag, a^s_{t-1}, a^s_t) with learning rate alpha_t determined by recursive least squares. Considers agent identity, subject's previous action, and current action.
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** - Model I: Q-learning with previous action -- Q_t(ag, a^s_{t-1}, a^s_t); considers agent identity, subject's previous and current action. Learning rate via recursive least squares. Also includes penalty term (kappa = 5.0) for incorrect action prediction.   - n_params: 1 (learning rate alpha, determined by recursive least squares; kappa fixed at 5.0)   - metric: % choice explained (behavioral prediction accuracy) - Model II: Simpler Q-learning without previous action -- Q_t(ag, a^s_t); does not consider subject's previous action.   - n_params: 1 (learning rate alpha)   - metric: % choice explained
- **model_mb_mf:** Model I is effectively model-based for Group I subjects (incorporates previous action to predict opponent strategy, consistent with mentalizing); model-free for Group II and agent B contexts. Hybrid interpretation: MB (for Group I agent A) / MF (baseline).
- **model_params:** - alpha_t: learning rate, determined by recursive least-square procedure (initial value = 100). Not a fixed fitted value -- adapts trial-by-trial. - kappa (fixed = 5.0): penalty parameter applied when model cannot predict subject's action correctly - Mean accuracy (Model I): Group I agent A = 0.87 (SD 0.11), agent B = 0.93 (SD 0.10); Group II agent A = 0.67 (SD 0.19), agent B = 0.87 (SD 0.13)
- **social_param:** No explicitly social parameter. The inclusion of a^s_{t-1} (subject's previous action) implicitly captures mentalizing about the opponent's strategy for agent A, but it is not a dedicated social parameter.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Percentage of subject choices correctly predicted (% choice explained); comparison via t test on prediction accuracy between models
- **how_model_fit:** individual-level-fit (recursive least-squares for each subject)
- **data_type_fit_to:** choice behavior  ---  ### 4. IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) -- reward prediction (RP) from Q-learning model used as parametric modulator at agent presentation event in GLM
- **contrast:** - Group I > Group II: correlation of BOLD with RP, for agent A and agent B separately - Common activation (Groups I and II): correlation of BOLD with RP - Group II > Group III: caudate nucleus correlation with RP (moderate threshold p < 0.005)
- **key_regions:** STS showed differential activity between Group I and Group II for both agents A and B; reward-related structures (dorsolateral PFC, ventral PFC, ACC, parietal cortex, striatum) commonly activated in both groups.
- **key_regions_abbrev:** striatum, lPFC, ACC, STS, parietal
- **coordinates_peak:** - Right STS (agent A): 48, -30, 0 - Right STS (agent B): 48, -32, 2  (Common activation regions coordinates not individually reported with MNI coordinates beyond Z-slice illustrations at Z = 42 and Z = 12)
- **analysis_type:** whole-brain (group contrast at p < 0.001 uncorrected, cluster > 10), with subsequent ROI-based signal extraction from peak voxels using MarsBar. Classification: both (whole-brain for discovery, ROI for signal extraction/correlation).  ---  ### 5. QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 32 (21 males, 11 females; ages 23-30, mean 25.3, SD 2.51). Group I: n = 12 (8M, 4F); Group II: n = 12 (8M, 4F); Group III: n = 8 (5M, 3F). All postgraduate students.
- **population_category:** healthy adults
- **population_age_range:** 23–30
- **ecological_validity:** Low -- subjects played against computer agents (not humans) in a simplified prisoner's dilemma with known payoff structure. Authors acknowledge this limitation but argue the neural mechanism is common to human and nonhuman agent interaction.
- **eligibility_flag:** 
- **concerns:** - Small sample size (n = 12 per group for key comparisons) - Computer agents rather than human opponents -- limits social ecological validity - Uncorrected statistical thresholds (p < 0.001 uncorrected) for whole-brain analyses - No formal model comparison metric (BIC/AIC) -- only % choice explained compared via t test - Learning rate determined by recursive least squares rather than standard MLE/Bayesian fitting - Effect sizes not reported in standard formats (no Cohen's d, r-values for correlations, etc.) - Group assignment based on behavioral performance, then neural differences examined -- circular analysis risk for agent A (but mitigated by agent B replication) - kappa parameter fixed rather than fitted; sensitivity analysis limited
- **limitations_reported:** Authors note: future experiment incorporating explicit modeling of mentalizing and reward processing might help extend results; computer agents used rather than humans; STS location slightly anterior to typical "theory of mind" area.
- **limitations_categorized:** limited ecological validity; task simplicity; no explicit mentalizing model; sample size; limited generalizability
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - effect_size: LOW -- no standard effect sizes reported; only p-values and T-maps - model_params (fitted values): MEDIUM -- learning rate is adaptive (recursive least squares), not a single fitted value; only accuracy reported - social_param: MEDIUM -- no explicitly social parameter; social component is implicit in task structure - model_mb_mf: MEDIUM -- authors interpret Group I as using model-based strategy but the Q-learning model itself is technically model-free; the previous-action conditioning approximates model-based reasoning - coordinates_peak (common regions): LOW -- exact MNI coordinates for common activation regions (PFC, ACC, striatum, parietal) not individually reported
- **cannot_find:** - Standard effect sizes (Cohen's d, r, beta, etc.) for main findings - Exact MNI coordinates for common activation regions beyond STS - Formal model comparison statistics (BIC, AIC, etc.) - Exact fitted learning rate values per group
- **other_notes:** This is a Brief Communication (6 pages). The paper's key contribution is showing STS differentiates good vs. poor learners in an interactive game, suggesting mentalizing-related processes support reinforcement learning competence. No supplement found or referenced. The Q-learning model is relatively simple; the paper's emphasis is on the neural individual differences rather than sophisticated computational modeling. The authors also tested a variant including the agent's previous action -- Q_t(ag, a^{ag}_{t-1}, a^s_t) -- and found comparable results to Model I.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = structural
- spec_locus = target
- spec_neural = dedicated
- spec_source = social
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = strategic_reasoning
- tax_rr_secondary_topic = cooperation
- tax_rr_topic_cooperation
- tax_rr_topic_strategic_reasoning
- tax_topic_cooperation
- tax_topic_strategic_reasoning
