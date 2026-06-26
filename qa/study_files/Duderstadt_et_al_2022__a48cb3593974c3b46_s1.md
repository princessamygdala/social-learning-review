# Duderstadt et al. (2022)

- **study_id:** `a48cb3593974c3b46_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Duderstadt, V. H., Mojzisch, A., & Germar, M. (2022). Social norm learning from non-human agents can induce a persistent perceptual bias: A diffusion model approach. *Acta Psychologica*, *229*, 103691. https://doi.org/10.1016/j.actpsy.2022.103691
- **citation_short:** Duderstadt et al. (2022)
- **doi:** 10.1016/j.actpsy.2022.103691
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Psychology
- **affiliations_raw:** University of Hildesheim, Universita¨tsplatz 1, 31134 Hildesheim, Germany; University of Hildesheim, Department of Psychology, Germany; lable at ScienceDirect; lableonline3August2022; emails: mojzisch@uni-hildesheim.de, dudersta@uni-hildesheim.de, germar@uni-hildesheim.de
- **code_url:** https://osf.io/8y35q/

## Computational level
- **study_focus:** Social norm learning (persistent social influence on perceptual decision-making from human vs. non-human agents)
- **study_focus_short:** Social norm learning
- **learning_mode_description:** - Learning mode: Learning from the perceptual judgments of human or non-human agents about a social norm that persistently biases one's own perceptual decision-making   - Learning from:     - Source type (social): group (4 human participants or 4 non-human algorithms)     - Source content (social): action/policy (color judgments — "orange" or "blue" responses)   - Learning about:     - Target type (non-social): world (dominant color of ambiguous stimulus)     - Target content (non-social): stimulus (perceptual decision about color dominance)
- **task_description:** Participants judged whether a bi-colored square (blue and orange pixels near 50/50 ratio) was dominated by orange or blue across three phases: a baseline (alone), a learning phase (with bogus feedback from 4 human participants or 4 algorithms), and an extinction phase (alone again). The social norm was manipulated by having the agents predominantly respond "orange" or "blue.
- **task_paradigm:** Conformity / Asch-style
- **players:** Single agent (participant), multi-target (4 simulated human participants or 4 simulated non-human algorithms)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Bi-colored squares (128x128 pixels, orange and blue, proportions: 48.5%, 49.5%, 50.5%, 51.5% orange), human-like icons or algorithm/code images for agent depiction
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Social norm x phase interaction on response probabilities (F(2.00, 407.49) = 27.26, p < .001, eta-squared-G = .022), qualified by source x norm x phase interaction (F(2.00, 407.49) = 5.12, p = .006, eta-squared-G = .004) - Learning phase: non-human agents induced norm conformity (F(1, 96) = 15.94, p < .001, eta-squared-G = .095); human agents did not (F(1, 108) = 0.05, p = .822, eta-squared-G < .001) - Extinction phase: norm conformity present for both human (F(1, 108) = 15.60, p < .001, eta-squared-G = .076) and non-human agents (F(1, 96) = 35.58, p < .001, eta-squared-G = .177) - Social norm x phase interaction on drift rates (F(1.90, 367.93) = 21.11, p < .001, eta-squared-G = .018) — persistent perceptual bias for both agent types - Learning phase drift rate: norm effect for non-human agents (F(1, 92) = 18.01, p < .001, eta-squared-G = .097) but not human agents (F(1, 102) = 0.92, p = .340, eta-squared-G = .004) - Extinction phase drift rate: norm effect for human agents (F(1, 102) = 8.19, p = .005, eta-squared-G = .029) and non-human agents (F(1, 92) = 37.37, p < .001, eta-squared-G = .150) - Norm-congruent judgmental bias (starting point) in extinction phase for human agents only (t(92.59) = -3.22, p = .002, d = 0.639) - Participants rated non-human agents as more competent than themselves (t(148.58) = -2.44, p = .016, d = 0.348); human agents rated equally competent as self - Participants felt closer to human agents than non-human agents (t(205.99) = 2.64, p = .009, d = 0.365)
- **effect_size:** eta-squared-G = .022 (norm x phase on responses); eta-squared-G = .004 (source x norm x phase on responses); eta-squared-G = .018 (norm x phase on drift rates); d = 0.639 (norm-congruent judgmental bias, human agents, extinction); d = 0.348 (competence difference, non-human agents); d = 0.365 (closeness, human vs non-human); sensitivity analysis: minimum detectable f = 0.17 (eta-squared = .03, d = 0.34)
- **learning_from:** Group (4 human participants or 4 non-human algorithms); bogus color judgment responses displayed after each trial
- **learning_about:** World; dominant color of ambiguous perceptual stimulus (social norm about color perception)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Diffusion Decision Model (DDM; 4 drift rates by proportion level, 1 relative starting point zr, 1 threshold separation a, 1 non-decision time t0, 1 inter-trial variability st0; inter-trial variabilities sv and szr fixed at 0)
- **model_family:** Drift-diffusion
- **model_class:** Evidence accumulation
- **all_models_tested:** [{"name": "DDM (full)", "family": "Drift-diffusion", "n_params": 8, "metric": "Kolmogorov-Smirnov"}] - Note: Only one DDM specification was fitted (no competing models). Parameters were estimated per participant using fast-dm with KS optimization.
- **model_mb_mf:** N/A (not RL; evidence accumulation model)
- **model_params:** - $\nu$ (drift rate) — estimated separately for each of 4 proportions of orange pixels per phase; represents rate of evidence accumulation. Positive values = more orange evidence. [Key dependent variable, not fitted as free parameter in the traditional sense but estimated per condition] - $z_r$ (relative starting point) — prior bias toward one response; 0.5 = unbiased. Values > 0.5 indicate bias toward "orange." Estimated once per phase per participant. - $a$ (threshold separation) — distance between decision boundaries; amount of information needed to reach a decision - $t_0$ (non-decision time) — time for stimulus encoding and response execution - $st_0$ (inter-trial variability of t0) - $sv$ — fixed at 0 - $sz_r$ — fixed at 0  Mean fitted values: Not reported as individual parameter means across conditions in the paper (drift rates and starting points reported as condition means in Results section figures/text — see Main Results above).
- **social_param:** $\nu$ (drift rate) [S] — the key social parameter: social norm exposure shifts drift rate in the norm-congruent direction, reflecting a perceptual bias induced by social influence. $z_r$ (relative starting point) [S] — shifts in starting point reflecting judgmental bias from social norm exposure.
- **social_param_name:** $\nu$
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Kolmogorov-Smirnov (KS) optimization criterion for parameter estimation; Monte Carlo simulation to determine critical value for model fit (p_crit < .0028 for poor fit). No formal model comparison between competing models — only one DDM specification was used.
- **how_model_fit:** individual-level-fit (parameters estimated separately for each participant using fast-dm)
- **data_type_fit_to:** choice behavior and response times (simultaneously via DDM)

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 208 (from initial N = 234; 26 excluded: 8 suspicious, 11 technical issues, 3 data-use refusal, 4 outliers); 81 female, 124 male; M_age = 25.8 years, SD_age = 4.7 years. Additional 10 excluded from DDM analyses due to poor model fit.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-to-moderate. Online study via Prolific increases ecological validity over lab settings for computer-mediated interaction, but the task (judging color dominance of pixel squares) is artificial. The non-human agents were described simply as "algorithms" with minimal characterization, limiting generalizability to more anthropomorphic AI agents. Asynchronous presentation of agent responses rather than real-time interaction.
- **eligibility_flag:** The "social agent" is partly an automated system (algorithms in the non-human condition) — flagged per instructions. Additionally, this paper uses a diffusion model as an analysis tool for disentangling cognitive mechanisms (perceptual vs. judgmental bias) rather than as a learning model per se. The DDM does not model the learning process over time; it characterizes decision-making within each phase. Borderline: learning occurs across phases (baseline to learning to extinction), but the computational model does not capture trial-by-trial updating. Flag: borderline learning-vs-decision-making case; DDM used as measurement model, not a learning model. Pure DDM (no learning component) — borderline eligibility (decision-making, not learning over time).
- **concerns:** - The DDM is used as a measurement/analysis tool, not as a model of the learning process itself. There is no trial-by-trial learning model (e.g., no Rescorla-Wagner or Bayesian updating model of how the social norm is acquired). - Only one model specification tested — no competing models compared. - The three-way interaction (source x norm x phase) was significant for response probabilities but not for drift rates or starting points, limiting conclusions about differential mechanisms. - Between-subjects design for agent type means individual differences could confound comparisons. - The original design included an additional between-subjects factor (objective feedback) that was dropped from the analysis as non-significant — this was not pre-registered. - 10 additional participants excluded from DDM analyses for poor model fit (on top of 26 already excluded).
- **limitations_reported:** Two limitations of our study need to be put forth. First, we only used one type of non-human agents (i.e., computer algorithms), which is very low in human likeness"; "Second, we used only one type of task (i.e., a perceptual decision-making task) because we aimed to explore whether non-human agents can induce a perceptual bias similar to human agents"; results "cannot easily be generalized to all types of non-human agents"; differences between human and non-human agents "should be interpreted with caution, since the overall source of social influence x social norm x phase interaction only reached significance for the response probabilities but not for the drift rates and the starting points
- **limitations_categorized:** Limited generalizability (single agent type); task simplicity (single perceptual task); limited ecological validity; statistical power concerns for three-way interaction on DDM parameters
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `eligibility_flag` (MEDIUM): Borderline case — DDM is a measurement model, not a learning model. Social norm learning occurs but is not computationally modeled trial-by-trial. - `model_family` (HIGH): DDM is clearly stated, but its use here is as an analysis tool rather than a learning model. - `preregistered` (MEDIUM): No explicit mention of pre-registration in the paper text; OSF link provided for materials/data but not described as a pre-registration. - `social_param` (MEDIUM): Drift rate and starting point are DDM parameters that *reflect* social influence effects, but they are not social parameters in the typical sense of a social learning model (e.g., social learning rate).
- **cannot_find:** - No supplement available (none found in papers folder) - No trial-by-trial learning model or learning rate parameters - No mean fitted parameter values reported per condition in tabular form (only graphical and ANOVA results) - No pre-registration statement
- **other_notes:** - This paper is primarily a social psychology study using DDM as an analytical tool to decompose social influence into perceptual bias (drift rate) vs. judgmental bias (starting point). It is not a computational modeling study in the typical sense for this review. - The finding that non-human agents induced stronger conformity than human agents during the learning phase is counterintuitive and attributed to perceived competence differences and psychological reactance. - Data and materials available at OSF: https://osf.io/8y35q/ - The paper discusses implications for reinforcement learning accounts of social conformity (citing Klucharev et al., 2009) but does not itself implement an RL model. - The authors discuss the "extended social reinforcement account" (Germar & Mojzisch, 2019) as the theoretical framework most consistent with their results, suggesting social influence operates via reinforcement learning mechanisms.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_instructed
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- tax_domain_A_influence_transmission
- tax_mod_instructed
- tax_model_drift_diffusion
- tax_param_social_bonus
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_drift_diffusion
- tax_rr_model_family = drift_diffusion
- tax_rr_param_PE_signal
- tax_rr_primary_topic = norm_conformity
- tax_rr_topic_norm_conformity
- tax_topic_norm_conformity
