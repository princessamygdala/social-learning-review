# Westhoff et al. (2021)

- **study_id:** `a89f6aeb837399ffe_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Westhoff, B., Blankenstein, N. E., Schreuders, E., Crone, E. A., & van Duijvenvoorde, A. C. K. (2021). Increased ventromedial prefrontal cortex activity in adolescence benefits prosocial reinforcement learning. *Developmental Cognitive Neuroscience*, *52*, 101018. https://doi.org/10.1016/j.dcn.2021.101018
- **citation_short:** Westhoff et al. (2021)
- **doi:** 10.1016/j.dcn.2021.101018
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department of Clinical, Neuro and Developmental Psychology, Vrije Universiteit, Amsterdam, Netherlands; Institute of Psychology, Leiden University, Wassenaarseweg 52, 2333 AK Leiden, Netherlands; School of Social and Behavioural Sciences, Erasmus University Rotterdam, Netherlands; Institute for Brain and Cognition, Leiden, Netherlands; eth Schreudersa,b,d, Eveline; schools and local advertise-; lableonline2October2021; lable at ScienceDirect; emails: a.c.k.van.duijvenvoorde@fsw.leidenuniv.nl, b.westhoff@fsw.leidenuniv.nl
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning — developmental differences in learning to benefit others across adolescence, neural tracking of prediction errors for self vs. other.
- **study_focus_short:** Prosocial learning
- **learning_mode_description:** - Learning mode: Learning from one's own action outcomes to select reward-maximizing stimuli for self or for an unknown other   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (monetary reward feedback, +1 or −1 points)   - Learning about:     - Target type — **Self condition** (non-social): self; **Other condition** (social): other (unknown peer); **No One condition** (non-social): world (no beneficiary)     - Target content — **Self condition** (non-social): stimulus–reward associations (action/policy); **Other condition** (social): stimulus–reward associations that benefit another (action/policy); **No One condition** (non-social): stimulus–reward associations (action/policy)
- **task_description:** Participants performed a two-choice probabilistic reinforcement learning task (75/25 contingency) across three conditions (Self, Other, No One), choosing between two stimuli to earn monetary points for themselves, an unknown peer, or no one. Feedback (+1 or −1) was provided after each choice to enable learning of reward contingencies.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), single target (unknown same-age peer who cannot reciprocate); also Self and No One conditions.
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Common object pictures (e.g., chairs, apples, shoes), binary monetary feedback (+1/−1 points)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Performance improved linearly with age (GLMM main effect of Age, p = .001); age-related improvement was greater for Other than Self (GLMM Age × Condition, p = .005)- Learning rates decreased with age (RLMM, B = −0.04, p = .023); decrease was steeper for Other than Self (B = −0.02, p < .001)- Conjunction PE coding in vmPFC (Z = 5.33), ventral striatum (Z = 5.05, Z = 4.43), and sgACC (Z = 5.47) across all conditions- Self PE > Other PE in left ventral striatum (Z = 4.37, k = 9, SVC-FWE) — no age-related differences- Other PE > Self PE showed age-related increase in vmPFC (Z = 4.95, k = 45, p = .004 SVC-FWE)- Cognitive empathy related to better prosocial learning performance (r_s = 0.30, p = .01) and lower learning rates for Other (r_s = −0.26, p = .027), and greater Other > Self PE vmPFC activation (r_s = 0.31, p = .007)- β parameter increased with age (B = 2.9, p = .007), more strongly for Other than Self (B = 0.47, p < .001)
- **effect_size:** 
- **learning_from:** Self; own choice outcomes (monetary reward feedback)
- **learning_about:** Self condition: stimulus–reward associations for self; Other condition: stimulus–reward associations that benefit an unknown other; No One condition: stimulus–reward associations with no beneficiary  ---  ### 3. ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Rescorla-Wagner (1 α per condition, 1 β per condition); Q_{t+1}(i) = Q_t(i) + α × [R_t − Q_t(i)]; softmax action selection P(i) = exp(β × Q_{i,t}) / Σ_j exp(β × Q_{j,t})
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "1-learning-rate RW", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"} — **WINNER** 2. {"name": "2-learning-rate RW (gain/loss)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC"}
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): prior β(1.2, 1.2), constrained 0 < α < 1   - Self: mean = 0.28 [95% CI: 0.24–0.32]   - Other [S]: mean = 0.34 [95% CI: 0.29–0.39]   - No One: mean = 0.34 [95% CI: 0.29–0.39] - β (inverse temperature / decision noise): prior Gaussian(0, 10), unconstrained   - Self: mean = 8.81 [95% CI: 7.37–10.26]   - Other [S]: mean = 7.43 [95% CI: 5.92–8.94]   - No One: mean = 7.94 [95% CI: 6.52–9.37]
- **social_param:** Separate α and β fitted per condition — the Other condition α [S] and β [S] capture prosocial learning rate and decision noise. No explicit "social weight" parameter; the social vs. non-social distinction is implemented by fitting the same model separately to Self, Other, and No One conditions.
- **social_param_name:** Other
- **social_param_value:** 0.34
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (per participant, per condition). 1-LR model was superior for majority of participants (81.1% Self, 74.3% Other, 76.7% No One).
- **how_model_fit:** Individual-level fit (MAP estimation with weakly informative priors per participant per condition)
- **data_type_fit_to:** Choice behavior  ---  ### 4. IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors) — GLM with parametric modulators of expected value (at choice) and prediction error (at outcome) derived from the RL model.
- **contrast:** - Conjunction PE (Self ∩ Other ∩ No One): vmPFC [−9, 44, −11], Z = 5.33; VS [−9, 11, −11], Z = 5.05 and [12, 14, −8], Z = 4.43; sgACC [−6, 14, −8], Z = 5.47 - Self PE > Other PE: L ventral striatum [12, 11, −11], Z = 4.37 - Other PE > Self PE × Age (linear): vmPFC [−15, 50, 8], Z = 4.95, k = 45, p = .004 - Self PE + No One PE > Other PE (ROI, Table S4): VS [12, 8, −11], Z = 4.42; sgACC [9, 8, −11], Z = 3.75 - No One PE > Other PE (ROI): VS [12, 8, −11], Z = 3.36 - Whole-brain results for Self PE, Other PE, No One PE, and condition contrasts in supplement (Tables S2, S5)
- **key_regions:** Common PE coding in vmPFC, ventral striatum, and sgACC across conditions; Self-specific PE in ventral striatum; age-related increase in Other > Self PE coding in vmPFC; cognitive empathy correlated with vmPFC prosocial PE tracking.
- **key_regions_abbrev:** VS, striatum, vmPFC, mPFC, ACC, sgACC
- **coordinates_peak:** - Conjunction PE — vmPFC: −9, 44, −11 - Conjunction PE — L ventral striatum: −9, 11, −11 - Conjunction PE — R ventral striatum: 12, 14, −8 - Conjunction PE — L sgACC: −6, 14, −8 - Conjunction PE — R sgACC: 6, 17, −8 - Conjunction PE — sgACC: 9, 8, −14 - Self PE > Other PE — L ventral striatum: 12, 11, −11 - Other PE > Self PE × Age — vmPFC: −15, 50, 8 - Self+NoOne PE > Other PE — VS: 12, 8, −11 - Self+NoOne PE > Other PE — sgACC: 9, 8, −11 - Self PE > Other PE (whole-brain, Table S5): extensive regions including L occipital (−21, −88, 22), bilateral putamen, bilateral supramarginal gyrus, etc. - Conjunction whole-brain PE (Table S2): L precuneus (−6, −58, 16), L caudate (−6, 14, −8)
- **analysis_type:** Both (ROI with SVC-FWE correction for primary hypotheses; whole-brain exploratory in supplement)  ---  ### 5. QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 74 (39 female, 35 male); age range 9.03–21.77 years (M = 15.64, SD = 4.18); IQ M = 110.24, SD = 10.37. Two excluded from original 76 (psychiatric diagnosis, scanner discomfort). Four participants missing one run retained.
- **population_category:** healthy adults
- **population_age_range:** M=15.64 (SD=4.18)
- **ecological_validity:** Low-moderate. Lab-based probabilistic learning task with abstract stimuli; the "other" was an unknown, unseen peer with no reciprocity possible. No real social interaction. Monetary incentives were real, increasing ecological validity somewhat.
- **eligibility_flag:** 
- **concerns:** - The RL model was fit separately per condition rather than fitting a single model with condition-specific parameters, preventing direct statistical comparison of α parameters across conditions within the model - No explicit social parameter (e.g., social learning weight ω); social distinction is purely design-based (separate model fits) - Cross-sectional design limits developmental inferences - "Other" was never met; prosocial motivation may be weakly engaged - No One condition showed intermediate neural patterns that are difficult to interpret
- **limitations_reported:** - Prosocial learning was restricted to unknown others, and participants did not meet these others; - Future research should extend to other beneficiaries (e.g., friends, family); - The No One condition showed an intermediate neural pattern between Self and Others that is difficult to interpret; - Model used separate learning rates per condition following Lockwood et al. (2016), but did not compare whether different learning rates/betas are needed across conditions; - Cross-sectional design — longitudinal studies needed for true developmental trajectories; - Narrower age range (9–21) may have limited power to detect quadratic age effects
- **limitations_categorized:** - Limited ecological validity; restricted social context; no real social interaction; task simplicity; cross-sectional design limits generalizability; limited model comparison; narrow age range
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_children
- rr_pop_adolescents
- rr_pop_children
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = general
- spec_locus = source+target
- spec_neural = dedicated
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_developmental
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_social_nonsocial_comparison
- tax_topic_prosocial_altruism
