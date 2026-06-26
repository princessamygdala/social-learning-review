# Peng et al. (2024)

- **study_id:** `a0241e9efa127ca2c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Peng, M., Duan, Q., Yang, X., Tang, R., Zhang, L., Zhang, H., & Li, X. (2024). The influence of social feedback on reward learning in the Iowa gambling task. *Frontiers in Psychology*, *15*, 1292808.
- **citation_short:** Peng et al. (2024)
- **doi:** 10.3389/fpsyg.2024.1292808
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Psychology
- **affiliations_raw:** University College Dublin, Ireland 1 Key Laboratory of Adolescent Cyberpsychology and Behavior (CCNU), Ministry of Education, Wuhan,; laboratory and field studies have shown that humans been used as feedback for positive or correct evaluations, while × has; mitation, and adaptation; thus, it plays feedback, the researchers added a control condition that included; School of Psychology, University of Birmingham, Birmingham, United Kingdom, 5 Institute for; mitted, provided the original choice, they would also receive feedback from an online peer; School of Psychology, Central China Normal Univer
- **code_url:** 

## Computational level
- **study_focus:** social feedback on reward learning; social learning strategies
- **study_focus_short:** social feedback on reward learning; social learning strategies
- **learning_mode_description:** - Learning mode: Learning from a fictitious peer's approval/disapproval feedback about environmental reward contingencies (deck values) in a gambling task.   - Learning from:     - Source type (social): other (fictitious online peer — novice or expert)       - Source content (social): outcomes (thumbs up/down approval/disapproval)     - Source type (non-social): self (own monetary outcomes)       - Source content (non-social): outcomes (monetary gain/loss)   - Learning about:     - Target type (non-social): world (deck reward contingencies)       - Target content (non-social): stimulus (which decks are good vs. bad)
- **task_description:** Participants completed a modified Iowa Gambling Task (120 trials), choosing among four decks yielding monetary gains/losses. In social feedback conditions, after each monetary outcome, participants received approval (thumbs up) or disapproval (thumbs down) from a fictitious online peer whose identity (novice/expert) and feedback type (random/effective) were manipulated between subjects.
- **task_paradigm:** Iowa gambling task
- **players:** Single agent (participant), single target (fictitious computer-simulated peer); 5 between-subjects groups (1 non-social, 4 social: novice-random, novice-effective, expert-random, expert-effective)
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Four card decks (labeled D, F, J, K); monetary gain/loss outcomes; thumbs up/down pictures as social feedback
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Significant block effect on chosen rate of good decks in non-social group (F(3,111) = 15.31, p < .001, $\eta_p^2$ = 0.29) - In social feedback: significant main effect of identity (F(1,149) = 4.18, p = .043, $\eta_p^2$ = 0.03) and feedback type (F(1,149) = 11.73, p < .001, $\eta_p^2$ = 0.07) on chosen rate of good decks - ORL model best fit across all 5 groups (lowest LOOIC) - All four social feedback groups had lower $A_{rew}$ and $A_{pun}$ than non-social group (HDIs away from zero) - Expert-effective group had significantly higher K ($\eta_p^2$ = 0.43 for identity x type interaction), $\beta_F$ ($\eta_p^2$ = 0.04), and $\beta_P$ ($\eta_p^2$ = 0.04) than expert-random and non-social groups - $A_{rew}$: significant identity x type interaction (F(1,153) = 65.89, p < .001, $\eta_p^2$ = 0.31) - $A_{pun}$: significant main effect of identity (F(1,153) = 8.87, p = .003, $\eta_p^2$ = 0.06)
- **effect_size:** - Block effect on good deck ratio (non-social): $\eta_p^2$ = 0.29 - Identity main effect on good deck ratio: $\eta_p^2$ = 0.03 - Feedback type main effect on good deck ratio: $\eta_p^2$ = 0.07 - Block effect on good deck ratio (social): $\eta_p^2$ = 0.12 - Identity x type interaction on $A_{rew}$: $\eta_p^2$ = 0.31; novice vs expert in effective: $\eta_p^2$ = 0.46 - Identity main effect on $A_{pun}$: $\eta_p^2$ = 0.06 - Identity x type interaction on K: $\eta_p^2$ = 0.43; expert effective > random: $\eta_p^2$ = 0.39 - Feedback type main effect on $\beta_F$: $\eta_p^2$ = 0.04; identity x type on $\beta_F$: $\eta_p^2$ = 0.04 - Identity x type interaction on $\beta_P$: $\eta_p^2$ = 0.04; expert effective > random: $\eta_p^2$ = 0.07
- **learning_from:** Other (fictitious peer's approval/disapproval) + self (own monetary gain/loss outcomes)
- **learning_about:** World; deck reward contingencies (which decks are good vs. bad)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** ORL (5 params: $A_{rew}$, $A_{pun}$, K, $\beta_F$, $\beta_P$)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** ```json [   {"name": "PVL-Delta", "family": "Prospect Valence Learning (RW delta rule)", "n_params": 4, "metric": "LOOIC"},   {"name": "VPP (Value-Plus-Perseverance)", "family": "PVL + perseverance", "n_params": 8, "metric": "LOOIC"},   {"name": "ORL (Outcome-Representation Learning) [winning]", "family": "RW + outcome frequency + perseverance", "n_params": 5, "metric": "LOOIC"} ] ```
- **model_mb_mf:** MF
- **model_params:** - $A_{rew}$ (0 < $A_{rew}$ < 1): learning rate for reward (positive) outcomes. Expert-effective: 0.15 +/- 0.10; expert-random: 0.27 +/- 0.07; novice-effective: 0.35 +/- 0.06; novice-random: 0.27 +/- 0.08 - $A_{pun}$ (0 < $A_{pun}$ < 1): learning rate for punishment (negative) outcomes. Expert-effective: 0.18 +/- 0.12; expert-random: 0.13 +/- 0.08; novice-effective: 0.24 +/- 0.19; novice-random: 0.21 +/- 0.15 - K: decay/forgetfulness parameter (higher = more recent options considered). Expert-effective: 2.45 +/- 0.47; expert-random: 0.95 +/- 0.35; novice-effective: 0.73 +/- 0.37; novice-random: 0.54 +/- 0.36 - $\beta_F$ ($-\infty$ < $\beta_F$ < $+\infty$): weight of outcome frequency on value. Expert-effective: 2.04 +/- 0.64; expert-random: 1.39 +/- 0.92; novice-effective: 1.72 +/- 0.85; novice-random: 1.69 +/- 0.84 - $\beta_P$ ($-\infty$ < $\beta_P$ < $+\infty$): deck perseverance weight. Expert-effective: 7.03 +/- 11.95; expert-random: 0.36 +/- 4.06; novice-effective: -0.49 +/- 2.20; novice-random: -0.84 +/- 2.44
- **social_param:** None explicitly social -- the model was fit to monetary outcomes only and does not incorporate social feedback as a parameter. Social feedback effects are inferred by comparing parameter values across groups. The authors note this as a limitation.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** LOOIC (Leave-One-Out Information Criterion)
- **how_model_fit:** group-level-fit (hierarchical Bayesian modeling via hBayesDM package, 20,000 iterations)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A -- no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=192 total (39 non-social [25F, mean age 20.6 +/- 2.6]; 153 social [109F, mean age 20.1 +/- 2.1] divided into 4 groups: novice-random, novice-effective, expert-random, expert-effective)
- **population_category:** healthy adults
- **population_age_range:** M=20.6
- **ecological_validity:** Low-moderate; social feedback was from a fictitious computer-simulated peer (thumbs up/down), not a real person; feedback was constant/non-adaptive throughout the experiment, limiting ecological validity; the IGT is a well-established decision-making paradigm but the social manipulation is artificial.
- **eligibility_flag:** 
- **concerns:** The computational model (ORL) does not incorporate social feedback -- social effects are inferred purely from between-group parameter comparisons. The feedback ratio imbalance between random (80% positive for all choices) and effective (80% contingent) groups means the effective group received fewer positive social feedbacks overall, confounding valence exposure with feedback type. The pseudo-social feedback is constant/non-adaptive, limiting generalizability to real social interactions. The non-social group (N=39) is substantially smaller than each social subgroup. Sex ratio is unbalanced (predominantly female). No individual-level model fitting reported -- only hierarchical group-level.
- **limitations_reported:** The ORL model did not incorporate social feedback; future research could design models incorporating social feedback to reveal how people integrate them; the ratio of positive/negative feedback was 80:20 in all social groups but actual positive feedback rate differed between effective and random groups due to task performance; pseudo-social feedback was constant throughout the experiment, potentially limiting credibility; sex ratio was unbalanced with more women than men; the study did not consider subjective feelings or individual differences.
- **limitations_categorized:** model misspecification (social feedback not modeled); stimulus confound (unequal feedback frequencies); limited ecological validity; unbalanced sex ratio; no individual differences measured
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - social_param (MEDIUM): No explicitly social parameter in the model; social effects inferred from between-group comparisons only - non-social group sample size (MEDIUM): N=39 vs. N~38 per social subgroup -- not explicitly flagged by authors but limits power for between-group comparisons - model_params (HIGH): mean +/- SD reported in Table 4 for social groups; non-social group parameter values not reported in a comparable table (only HDI differences)
- **cannot_find:** Mean fitted parameter values for the non-social feedback group (only HDI differences with social groups reported, not the raw non-social group means); exact LOOIC values per group are reported (Table 2) but no delta-LOOIC or SE.
- **other_notes:** The ORL model was originally developed by Haines et al. (2018) specifically for the IGT. The study's key contribution is demonstrating that social feedback modulates internal cognitive parameters of reward learning (not just behavioral outcomes), but the model itself does not formally incorporate social information -- this is a notable gap the authors themselves acknowledge. The study uses Social Learning Strategies (SLS) framework from Laland (2004) to interpret "who" (expert vs. novice) and "what" (effective vs. random) strategies. Data fitted using hBayesDM R package with hierarchical Bayesian approach.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = general
- spec_locus = source+target
- spec_source = social
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_decay
- tax_param_perseveration
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_decay
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_info_use
- tax_rr_topic_social_info_use
- tax_social_nonsocial_comparison
- tax_topic_social_info_use
