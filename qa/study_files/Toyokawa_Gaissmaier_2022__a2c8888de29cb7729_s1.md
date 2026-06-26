# Toyokawa & Gaissmaier (2022)

- **study_id:** `a2c8888de29cb7729_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Toyokawa, W., & Gaissmaier, W. (2022). Conformist social learning leads to self-organised prevention against adverse bias in risky decision making. *eLife*, *11*, e75308. https://doi.org/10.7554/eLife.75308
- **citation_short:** Toyokawa & Gaissmaier (2022)
- **doi:** 10.7554/eLife.75308
- **publication_type:** peer-reviewed journal (elife)
- **year:** 2022.0
- **field_of_study:** Psychology
- **affiliations_raw:** mity on risk taking, demonstrating that social influence can produce an adaptive risk- seeking; Department of Psychology, University of Konstanz, Konstanz, Germany; 2Centre; mited information that is not accurate enough to find the best option; mitigated people’s tendency to be risk-a verse when risk-t aking; University of Konstanz,, Konstanz,; mpirical evidence (Toyokawa et al; mits unrestricted use and; University of California,
- **code_url:** https://github.com/WataruToyokawa/ToyokawaGaissmaier2021

## Computational level
- **study_focus:** Social influence learning / conformist social learning in risky decision making. How frequency-based copying (conformist social learning) rescues groups from suboptimal risk aversion emerging through individual trial-and-error learning (the "hot stove effect").
- **study_focus_short:** Social influence learning / conformist social learning in risky decision making
- **learning_mode_description:** - Learning mode: Learning from the group's choice frequencies about which option to choose in a risky decision environment   - Learning from:     - Source type (social): group (other participants' choices)       - Source content (social): action/policy (frequency distribution of others' choices)     - Also learning from:       - Source type (non-social): self       - Source content (non-social): outcome (own payoff from chosen option)   - Learning about:     - Target type (non-social): world (option values / reward contingencies)       - Target content (non-social): outcome (expected payoff of each option)  ---  ### 4. Computational Problem  How can a group of reinforcement learners overcome suboptimal risk aversion (the "hot stove effect") that emerges from adaptive information sampling, through conformist frequency-based social influence? (Prediction / evaluation)
- **task_description:** Participants performed a multi-armed bandit task (2-arm or 4-arm variants) where one option provided constant (safe) payoffs and the other(s) provided stochastic (risky) payoffs. In the group condition, participants could observe how many others chose each option on the previous trial (frequency information only, not payoffs). Four task variants were used across conditions (1-risky-1-safe positive RP, 1-risky-3-safe positive RP, 2-risky-2-safe positive RP, 1-risky-1-safe negative RP). 70 trials per task.
- **task_paradigm:** Multi-armed bandit
- **players:** Multi-agent (groups of 2–8), symmetric; also single agent (individual condition for comparison). Specifically: group condition N=400 across groups of 2–8; individual condition N=185.
- **n_players:** network (5+)
- **partner_type:** human (live)
- **stimuli:** Abstract choice options (colored buttons/slots), monetary point outcomes (skewed Bernoulli payoff distributions).
- **method:** online / behavioural
- **method_full:** Behavioural (online)
- **main_result:** - Main Results:   - Bayesian model comparison: Decision-biasing social learning model preferred over asocial RL and value-shaping model (exceedance probability reported via BMS; exact exceedance probability values shown in Figure 6—figure supplement 2 but not numerically reported in text)   - Copying weight σ positively predicted risk taking in group condition across all four tasks (GLMM: β = 1.4 [95% CI: 0.5, 2.3] for 1-risky-1-safe positive RP; β = 1.9 [0.8, 3.0] for 1-risky-3-safe; β = 2.2 [0.4, 4.0] for 2-risky-2-safe; β = 3.8 [2.2, 5.3] for negative RP)   - Susceptibility to hot stove effect α(β+1) negatively predicted risk taking in positive RP tasks (GLMM: β = −0.9 [−1.3, −0.4] for 1-risky-1-safe; β = −1.0 [−1.5, −0.5] for 1-risky-3-safe; β = −0.9 [−1.3, −0.6] for 2-risky-2-safe)   - Group × α(β+1) interaction: positive in positive RP tasks (β = 0.6 [0.0, 1.1] for 1-risky-1-safe; β = 0.4 [0.0, 0.9] for 1-risky-3-safe), negative in negative RP task (β = −1.1 [−1.9, −0.3])   - Conformity exponent θ: mean posterior > 1 for all four tasks (range 1.4–1.8), confirming conformist copying   - Copying weight σ was modest (mean 4%–18% across tasks), insufficient for complete "collective rescue" but consistent with partial mitigation of risk aversion
- **effect_size:** MEDIUM — only GLMM β coefficients with Bayesian CIs reported; no standardized effect sizes (Cohen's d, r², η²)
- **learning_from:** 
- **learning_about:** 
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Decision-biasing conformist social RL: P_{i,t} = (1 − σ) × softmax(β, Q) + σ × conformist_frequency(θ, N), with Rescorla-Wagner Q-value updating (2 individual params: α, β; 2 social params: σ [S], θ [S])
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 
- **model_mb_mf:** MF
- **model_params:** - α: learning rate, mean 0.10–0.48 across tasks (individual/group conditions) - β: inverse temperature, mean 1.5–4.5 across tasks - σ [S]: copying weight (social influence weight), mean 0.08–0.12 across tasks - θ [S]: conformity exponent, mean 1.4–1.8 across tasks
- **social_param:** σ (copying weight) — weight given to social frequency information vs. individual RL; θ (conformity exponent) — degree of nonlinear conformist bias toward majority choice  ---  ### 7. All Models Tested  1. {"name": "Asocial RL (Rescorla-Wagner + softmax)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "WAIC/BMS"} 2. {"name": "Decision-biasing social RL", "family": "Rescorla-Wagner + conformist social influence", "n_params": 4, "metric": "WAIC/BMS"} 3. {"name": "Value-shaping social RL", "family": "Rescorla-Wagner + value bonus from social frequency", "n_params": 4, "metric": "WAIC/BMS"}  Additionally, a differential equation population dynamics model was developed for theoretical analysis (not fit to individual data; used for qualitative understanding of collective dynamics).  ---
- **social_param_name:** σ
- **social_param_value:** 2
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** MEDIUM — BMS exceedance probabilities shown in figure supplement but not numerically stated in text
- **how_model_fit:** Individual-level fit via hierarchical Bayesian method (HBM) using Hamiltonian Monte Carlo (CmdStan 2.25.0); 6+ parallel chains; Gelman-Rubin Rhat < 1.01; effective samples > 500.
- **data_type_fit_to:** Choice behavior  ---  ### 9. Neuroimaging

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** 
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 585 (after exclusions; 619 recruited). Group condition: n = 400 (123 for 1-risky-1-safe +RP, 97 for 1-risky-3-safe, 87 for 2-risky-2-safe, 93 for negative RP). Individual condition: n = 185 (45, 51, 64, 25 for respective tasks). Mean age = 35.2 (18–74). 294 women, 277 men, 1 other, 47 unspecified.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate. Online multi-armed bandit task with abstract options and monetary incentives. Social information limited to frequency cues (how many chose each option). No face-to-face interaction, no communication, no normative pressure. Authors note that real-world social learning likely involves richer information and stronger conformity pressures. The stationary environment may have reduced reliance on social learning.  ---  ### 12. Eligibility Flag  null (fully eligible: computational modeling, human behavioral data, social learning context, learning over time across 70 trials)
- **eligibility_flag:** 
- **concerns:** - The study combines agent-based simulations, differential equation modeling, and behavioral experiments — the simulations use a much wider parameter space than what was observed in participants. The "collective rescue" was not strongly observed in the empirical data due to low copying weights (σ = 4–18%) and low susceptibility to the hot stove effect in most participants. - No direct demonstration that group performance exceeded individual performance in the experiment; the evidence relies on computational model predictions calibrated to fit parameters rather than raw behavioral differences. - Group sizes varied (2–8) and were not experimentally controlled precisely due to the online "waiting lobby" design. - Exact BMS exceedance probabilities for model comparison are shown only in a figure supplement, not reported numerically in text.  ---  ### 14. Wilson & Collins Checklist  1. **Design a good experiment:** Yes — task specifically designed to elicit hot stove effect and test conformist social learning across multiple bandit configurations 2. **Design good models:** Yes — three competing models (asocial RL, decision-biasing, value-shaping) plus theoretical differential equation model 3. **Simulate, simulate, simulate:** Yes — extensive agent-based simulations across parameter spaces before fitting to data 4. **Fit the parameters:** Yes — hierarchical Bayesian fitting with HMC (CmdStan) 5. **Check parameter recovery:** Yes — two parameter recovery tests reported (Figure 6—figure supplement 3); correlation > 0.5 for all individual parameters; 30/32 global parameters recovered within 95% CIs 6. **Check model recovery:** Yes — model recovery confirmed by simulation (Figure 6—figure supplement 2) 7. **Fit real data and compare models:** Yes — BMS with WAIC on real data, decision-biasing model preferred 8. **Validate the winning model:** Yes — post-hoc simulations (100,000 replications) with calibrated parameters compared to experimental data patterns (Figure 6) 9. **Analyze the winning model:** Yes — individual parameters analyzed via GLMM; relationships between σ, θ, α(β+1) and risk-taking behavior examined 10. **Report results transparently:** Yes — code and data available on GitHub; preprinted February 2021
- **limitations_reported:** - Weak reliance on social learning (σ < 20%) prevented strong positive feedback and full collective rescue in the experiment; "the weak average reliance on social learning hindered the strong collective rescue effect" - Low learning rates (α ≤ 0.2) in most participants meant low susceptibility to the hot stove effect, limiting the potential benefit of collective rescue - Stationary environment may have reduced reliance on social learning; future work should use "restless" bandit tasks to elicit higher learning rates and heavier reliance on social learning - No normative motivation for conformity in the experimental design - Social information limited to frequency cues; real-world settings may involve richer information (payoffs, communication) - Group sizes could not be precisely controlled due to online waiting lobby design
- **limitations_categorized:** Limited ecological validity; task simplicity (stationary environment); weak experimental manipulation (low social influence observed); limited generalizability (abstract task, no normative pressure); sample composition limitations (uncontrolled group sizes)  ---  ### Flagged Fields
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
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
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
- rr_tax_mod_social_info_search
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_social_info_search
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_social_bonus
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_norm_conformity
- tax_rr_topic_social_info_use
- tax_topic_norm_conformity
- tax_topic_social_info_use
