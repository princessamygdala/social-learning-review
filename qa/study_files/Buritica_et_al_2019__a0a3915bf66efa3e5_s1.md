# Buritica et al. (2019)

- **study_id:** `a0a3915bf66efa3e5_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Rodriguez Buritica, J. M., Heekeren, H. R., & van den Bos, W. (2019). The computational basis of following advice in adolescents. *Journal of Experimental Child Psychology*, *180*, 39–54. https://doi.org/10.1016/j.jecp.2018.11.019
- **citation_short:** Buritica et al. (2019)
- **doi:** 10.1016/j.jecp.2018.11.019
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofDevelopmentalPsychology,UniversityofAmsterdam,1012WXAmsterdam,TheNetherlands; CenterforAdaptiveRationality,MaxPlanckInstituteforHumanDevelopment,14195Berlin,Germany; CenterofLifespanPsychology,MaxPlanckInstituteforHumanDevelopment,14195Berlin,Germany; DepartmentofEducationandPsychology,FreieUniversitätBerlin,14195Berlin,Germany; ethanonthefeedbackpresentedduringthelearningepisodeofthetask; lable,whichraisesanotherimportantissue; lableonline2January2019; lableatScienceDirect; emails: buritica@zedat.fu-berlin.de
- **code_url:** 

## Computational level
- **study_focus:** Learning from advice; developmental differences in how peer advice, experience-based learning, and exploration interact across childhood, adolescence, and adulthood.
- **study_focus_short:** Learning from advice
- **learning_mode_description:** - Learning mode: Learning from peer advice and own experience about reward values of choice options   - Learning from:     - Source type (social): other (same-aged peer) — provides initial advice/recommendation     - Source content (social): action/policy (recommendation of a specific deck)   - Learning from:     - Source type (non-social): self — own reward outcomes from card deck selections     - Source content (non-social): outcome (monetary gains and losses)   - Learning about:     - Target type (non-social): world — reward structure of four card decks     - Target content (non-social): outcome (expected values of each deck)
- **task_description:** Participants played a four-armed bandit task (modified Iowa Gambling Task) with 210 trials, selecting one of four card decks associated with gains and losses. Before starting, they received a recommendation for one of the two good decks from a purported same-aged peer (actually experimenter-controlled), and then learned from their own experience.
- **task_paradigm:** Iowa gambling task
- **players:** Single agent (participant), single social source (anonymous same-aged peer advisor). Three age groups tested: children (8–10 years), adolescents (13–15 years), adults (18–22 years).
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Four card decks (abstract), monetary feedback (gains and losses)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Adolescents showed highest initial susceptibility to peer advice (quadratic age pattern in prior parameter θ; β_quadratic = .14, t = 2.30, p = .025) - Adults most consistently followed advice over time (recommended deck preference stable across trials) - Younger participants showed more exploratory behavior (linear age pattern in θ; β_linear = .05, t = 3.03, p = .003) - Children had higher learning rates for negative outcomes (emerging age pattern in α_loss; β_emerging = .28, t = 2.08, p = .041) - Adolescents chose bad decks below chance level while children and adults did not - Mixed-effects logistic regression: adolescents increasingly selected other good deck over recommended deck (β = −0.16, OR = 0.86) - R² = .143 (Tjur's D) for logistic regression model
- **effect_size:** - Prior parameter age effect: β_quadratic = .14, t = 2.30 - Exploration parameter age effect: β_linear = .05, t = 3.03 - Negative learning rate age effect: β_emerging = .28, t = 2.08 - Logistic regression R² = .143 (Tjur's D) - Working memory age effect: η²_p = .36 - Fluid intelligence age effect: η²_p = .37 - Bayes factor for best vs. second-best model: BF = 6494
- **learning_from:** Other (same-aged peer providing deck recommendation) + self (own reward outcomes from chosen decks)
- **learning_about:** World; expected reward values of four card decks  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Prior + Bonus Dual RL (α_pos, α_neg, θ, q [S], b [S]; 5 free parameters)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Basic RL (single LR)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"},   {"name": "Basic RL (dual LR)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC"},   {"name": "Bonus RL (single LR)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC"},   {"name": "Bonus RL (dual LR)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BIC"},   {"name": "Bonus + Decay RL (single LR)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BIC"},   {"name": "Bonus + Decay RL (dual LR)", "family": "Rescorla-Wagner", "n_params": 5, "metric": "BIC"},   {"name": "Prior RL (single LR)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC"},   {"name": "Prior RL (dual LR)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BIC"},   {"name": "Prior + Bonus RL (single LR)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BIC"},   {"name": "Prior + Bonus RL (dual LR)", "family": "Rescorla-Wagner", "n_params": 5, "metric": "BIC"} ]  Note: The paper states 9 models were tested. The list above reflects the model space described (basic, bonus, bonus+decay, prior, prior+bonus, each with single vs dual learning rates = 10 combinations; the paper says 9, likely because the basic single LR and one other share a count or the prior+bonus single LR was counted differently). The winning model is the Prior + Bonus Dual RL.
- **model_mb_mf:** MF
- **model_params:** - α_pos (learning rate for positive feedback; 0 < α < 1) — median values not reported separately per group in main text - α_neg (learning rate for negative feedback; 0 < α < 1) — children showed higher values (emerging age pattern) - θ (inverse temperature / choice sensitivity; softmax parameter) — linear age increase (less exploration in older groups) - q [S] (prior expectation for recommended deck; social influence on initial expectations) — quadratic age pattern, highest in adolescents - b [S] (constant bonus for recommended deck; social influence on ongoing choice) — significant > 0 for all age groups, no age differences  Note: Exact fitted median parameter values are shown in Fig. 3B but not reported numerically in the text. Supplement referenced but not accessible.
- **social_param:** - q (prior): captures social influence on initial expectations before sampling; the recommended deck receives an initial value of q × l (where l = 6.25, the expected payoff from random choice). Adolescents showed the highest prior. - b (bonus): captures ongoing social influence; adds a constant outcome bonus to the recommended deck across all trials. No age differences.
- **social_param_name:** q
- **social_param_value:** 6.25
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (summed across all participants; lower = better). Bayes factor between best and second-best model = 6494.
- **how_model_fit:** individual-level-fit (parameters individually estimated per participant, then BIC summed across participants)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 73 (25 adults aged 18–22, 24 adolescents aged 13–15, 24 children aged 8–10); effective N = 71 after exclusions (1 adult excluded for technical problems, 1 adolescent excluded for missing responses)
- **population_category:** mixed
- **population_age_range:** 18–22
- **ecological_validity:** Limited ecological validity — social information was a single recommendation from a purported anonymous peer, controlled by experimenter, rather than genuine peer interaction. Task is a lab-based modified Iowa Gambling Task. However, the advice manipulation was believable (no participant reported disbelief).
- **eligibility_flag:** 
- **concerns:** Social agent was simulated (advice controlled by experimenter); advice was always good, limiting generalizability to contexts with unreliable or bad advice; no measure of participants' beliefs about the advice source; exact median parameter values not reported numerically in text (only in figure); supplement referenced for model fitting procedure details and parameter recovery but supplement not accessible in current file set.
- **limitations_reported:** Social information was given once from an anonymous peer within each age group, and the recommendation was always good and controlled by the experimenter; reliability of advice may have affected perception of advice quality; no measure of participants' beliefs in others' advice was included; did not examine whether adolescents' sensitivity to advice depends on the identity of the source (peer vs. adult vs. computer); did not examine effects of peer popularity status on advice following; compared adolescents with prepubertal children and adults but did not account for pubertal hormone levels which may play a role in processing social information.
- **limitations_categorized:** Limited ecological validity; task simplicity (single advice episode); no manipulation of advice quality; no belief assessment measure; limited generalizability (anonymous peer only); no hormonal measures; cross-sectional design (age groups as proxy for development)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 9.0
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM confidence — exact median fitted values shown in Fig. 3B but not reported numerically in text; supplement not accessible - wc_guidelines Rule 5 (parameter recovery): MEDIUM — recovery analyses referenced in supplementary material but supplement not accessible to verify - wc_guidelines Rule 6 (model recovery): MEDIUM — model recovery referenced (Table S1) but supplement not accessible to verify - wc_guidelines Rule 8 (validate winning model): MEDIUM — qualitative simulations performed but unclear if formal posterior predictive check was done
- **cannot_find:** - Exact numerical median parameter estimates per age group (shown only in figure) - Supplementary material (model fitting procedure details, parameter recovery Fig. S2, model recovery Table S1, simulation Fig. S1) - Data/code sharing information
- **other_notes:** Supplement not accessible — referenced online at https://doi.org/10.1016/j.jecp.2018.11.019 but no supplement file found in the papers folder. The paper is a developmental study comparing three age groups; the core computational modeling and social learning components are sound. The social learning element is the peer advice (recommendation) that biases initial expectations and ongoing choice. The Bayes factor of 6494 strongly favors the Prior + Bonus Dual RL model over all alternatives.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_children
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_children
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- rr_tax_mod_social_info_search
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_instructed
- tax_mod_social_info_search
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_social_bonus
- tax_param_temperature
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_bonus
- tax_rr_primary_topic = advice_taking
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_advice_taking
- tax_rr_topic_social_info_use
- tax_topic_advice_taking
- tax_topic_social_info_use
