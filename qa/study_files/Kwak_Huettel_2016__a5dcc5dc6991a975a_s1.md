# Kwak & Huettel (2016)

- **study_id:** `a5dcc5dc6991a975a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Kwak, Y., & Huettel, S. A. (2016). Prosocial reward learning in children and adolescents. *Frontiers in Psychology*, *7*, 1539. https://doi.org/10.3389/fpsyg.2016.01539
- **citation_short:** Kwak & Huettel (2016)
- **doi:** 10.3389/fpsyg.2016.01539
- **publication_type:** peer-reviewed journal
- **year:** 2016.0
- **field_of_study:** Developmental psychology
- **affiliations_raw:** DepartmentofPsychologicalandBrainSciences,UniversityofMassachusetts,Amherst,MA,USA,2CenterforCognitive; section: Adolescenceiscommonlycharacterizedasaperiodofpoordecisionmakingmanifestedinrisky,; University,Durham,NC,USA,3DukeCenterforInterdisciplinaryDecisionSciences,DukeUniversity,; mittedto irrational, and often self-destructive choices (Blakemore and Robbins, 2012); DepartmentofPsychologyandNeuroscience,DukeUniversity,Durham,NC,USA; UniversityofAmsterdam,Netherlands; ethisend,adolescentsaremotivated; sectionofthejournal; emails: scott.huettel@duke.edu
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning — developmental differences in how children/adolescents versus adults learn reward contingencies for self and charity in a dynamic social gambling task.
- **study_focus_short:** Prosocial learning
- **learning_mode_description:** - Learning mode: Learning from one's own monetary outcomes (for self and for a charity) about the reward contingencies of card decks that affect both self and others.   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (monetary reward for self)     - Source type (social): other (charity)       - Source content (social): outcome (monetary reward for charity)   - Learning about:     - Target type (non-social): world (deck reward contingencies for self)       - Target content (non-social): outcome (expected value of decks for self)     - Target type (social): world (deck reward contingencies for charity)       - Target content (social): outcome (expected value of decks for charity)
- **task_description:** Participants chose among four card decks over 100 trials, each associated with different gain/loss structures for both self and a charity ("Make a Wish!" foundation), in a 2x2 design (self gain/loss x charity gain/loss). After each choice, monetary outcomes for self and charity were displayed, and participants had to learn the reward contingencies over time.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), single target (charity). Cross-sectional comparison: children/adolescents (N=75, ages 8-16) versus adults (N=102, ages 18-36; previously collected sample).
- **n_players:** network (5+)
- **partner_type:** unclear
- **stimuli:** Abstract card decks (4 decks), monetary outcomes for self and charity.
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Children/adolescents used the WL (self-win, charity-lose) strategy significantly less than adults, indicating greater prosocial sensitivity (age-group-by-strategy-type interaction: F(3,525) = 2.83, p = 0.038) - Significant age-group-by-block interaction in learning index (F(6.34,1109.01) = 5.55, p < 0.0001), with adults showing steeper learning curves - Children/adolescents had marginally lower alpha (self vs. charity weighting parameter; t(94) = 1.88, p = 0.064), indicating relatively greater charity sensitivity - Children/adolescents reported significantly higher altruism on HOQ (t(160) = -3.09, p = 0.002) - Significant age-group-by-domain interaction in happiness ratings (F(1,175) = 47.95, p < 0.0001): children/adolescents happier winning for charity; adults happier winning for self
- **effect_size:** - Age-LI_self correlation within children/adolescents: r = 0.41 - Age-WW strategy correlation within children/adolescents: r = 0.37 - WL strategy-LI_difference correlation: r = -0.24 - Age-model performance correlation within children/adolescents: r = 0.46 - Age-charity mission influence correlation: r = 0.328
- **learning_from:** Self and other (charity); monetary reward outcomes for both self and charity from card deck choices.
- **learning_about:** World; reward contingencies of card decks affecting self and charity payoffs.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Reinforcement learning with dual reward streams: V_ij = alpha * Q_S_ij + (1-alpha) * Q_C_ij; Q updated via separate learning rates lambda_S and lambda_C; softmax choice rule with inverse temperature beta. (4 parameters: alpha, lambda_S, lambda_C, beta)
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Dual-stream RL (self/charity)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "maximum log likelihood"}] Note: Only one model was tested/reported.
- **model_mb_mf:** MF
- **model_params:** - alpha [S]: Self vs. charity reward sensitivity weighting (alpha=1 purely selfish, alpha=0 purely charitable). Adults M=0.51 (SD=0.34); Children/adolescents M=0.38 (SD=0.34) - lambda_S: Learning rate for self rewards. Adults M=0.29 (SD=0.36); Children/adolescents M=0.39 (SD=0.39) - lambda_C [S]: Learning rate for charity rewards. Adults M=0.28 (SD=0.37); Children/adolescents M=0.25 (SD=0.34) - beta: Inverse temperature (greediness) parameter. Fitted values not reported.
- **social_param:** alpha — weighting parameter controlling relative sensitivity to self vs. charity rewards (alpha=1 purely selfish, alpha=0 purely charitable); lambda_C — learning rate for charity reward prediction errors.
- **social_param_name:** alpha
- **social_param_value:** 0.51
- **social_param_sd:** 0.34
- **social_param_range:** 
- **model_comparison_metric:** Maximum log likelihood (no formal model comparison conducted — only one model tested)
- **how_model_fit:** individual-level-fit (MLE via MATLAB fmincon constrained optimization, fitted individually per subject)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=177 total (children/adolescents: N=75, 32 males, 43 females, ages 8-16, M=12, SD=3; adults: N=102, 44 men, 58 women, ages 18-36, M=23, SD=4). No Knowledge group excluded from RL analyses: adults N=60, children/adolescents N=35.
- **population_category:** mixed
- **population_age_range:** 8–16
- **ecological_validity:** Lab-based card gambling task with charitable donation framing; more dynamic than one-shot games but still abstract. Charity target ("Make a Wish!") may not generalize to other social targets. Implicit learning paradigm offers advantage over explicit self-report measures.
- **eligibility_flag:** 
- **concerns:** Only one RL model tested — no formal model comparison. Beta parameter fitted values not reported. Adult data from a previously collected, separately published sample (Kwak et al., 2014) — potential overlap/reuse. Wide age range (8-16) in developmental sample limits developmental stage specificity. No parameter recovery or model recovery reported.
- **limitations_reported:** Some participants (in both age groups) failed to choose positive reward decks consistently (No Knowledge group), which may or may not reflect absence of successful learning; wide age range of children and adolescents used, and future research should narrow the timing of developmental transitions; prosocial behavior observed could have been influenced by preferences specific to the chosen charitable foundation ("Make a Wish!"); children and adolescents might give more socially desirable responses, though the implicit RL measure would be more resistant to this than explicit measures.
- **limitations_categorized:** Task comprehension variability; limited developmental stage specificity; limited generalizability (charity-specific); social desirability bias
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - beta fitted values: LOW — not reported in paper or supplement - model_comparison_metric: MEDIUM — only MLE mentioned, no formal comparison since single model - learning_mode target classification: MEDIUM — deck contingencies coded as "world" targets since they represent environment features, though the charity outcomes are social in nature
- **cannot_find:** - Fitted beta parameter values (not reported) - Formal model comparison (only one model tested) - Any simulation or recovery analyses - Data/code sharing information
- **other_notes:** The adult sample (N=102) was previously published in Kwak et al. (2014, PLoS ONE). This paper extends that work to a developmental sample. The model is identical to the one used in the 2014 paper. If the Kwak et al. (2014) paper is also in the extraction corpus, this should be flagged as a partial data reuse (adult sample).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_children
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_children
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- spec_target = partly
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_topic_prosocial_altruism
