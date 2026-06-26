# Khalvati et al. (2019)

- **study_id:** `a26bb57d6400eea38_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Khalvati, K., Park, S. A., Mirbagheri, S., Philippe, R., Sestito, M., Dreher, J.-C., & Rao, R. P. N. (2019). Modeling other minds: Bayesian inference explains human choices in group decision-making. *Science Advances*, *5*(11), eaax8783. https://doi.org/10.1126/sciadv.aax8783
- **citation_short:** Khalvati et al. (2019)
- **doi:** 10.1126/sciadv.aax8783
- **publication_type:** peer-reviewed journal (preprint version read; published in science advances 2019)
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Center for Mind and Brain, University of California, Davis, Davis, observations, and a simulation of the future based on the current; Laboratory, Institut des Sciences Cognitives Marc actions for modeling human decisions within a group; School of Computer Science and Engineering, University of Washington, current choices; ethods and human behavior when the subject inter-; laboratory setting, we used the
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning / group decision making -- modeling the "mind of the group" to decide whether to contribute or free-ride in a Volunteer's Dilemma (binary Public Goods Game).
- **study_focus_short:** Cooperation learning / group decision making -- modeling the "mind of the
- **learning_mode_description:** - Learning mode: Learning from group contribution outcomes about the group's cooperativeness to decide whether to contribute or free-ride   - Learning from:     - Source type (social): group (anonymous group members)     - Source content (social): outcomes (total number of contributions revealed each round; SUCCESS/FAILURE)   - Learning about:     - Target type (social): group (average group member's cooperativeness)     - Target content (social): state (mental state; latent cooperativeness parameter theta)
- **task_description:** Participants played a binary Public Goods Game (Volunteer's Dilemma) in groups of 5 (actually computerized partners). Each round, participants chose to contribute (cost 1 MU) or free-ride; if at least k players contributed (k=2 or k=4), all players received a group reward of 2 MU, otherwise the round failed.
- **task_paradigm:** Public goods game
- **players:** Single agent (participant), multi-target (4 computerized partners simulating human players; groups of 5)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract economic game screens showing contribution/free-ride choice, total contributions, and SUCCESS/FAILURE outcome
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - POMDP model accuracy: 84% (SD=0.06); LOOCV accuracy: 77% (SD=0.08) - POMDP vs. Q-learning accuracy: one-tailed paired t-test, t=-6.75, df=29, CI difference=[-0.08, -0.01]; LOOCV: t=2.20, df=29, CI=[0.00, 0.09] - POMDP vs. two-factor descriptive model accuracy: t=-4.86, df=29, CI=[-0.10, -0.02]; LOOCV: t=-7.61, df=29, CI=[-0.38, -0.22] - POMDP SUCCESS prediction accuracy: 71% (SD=0.07) - Contribution rate k=4 (55%, SD=.31) vs. k=2 (33%, SD=.18): t=3.94, df=29 - I-POMDP model accuracy: 73% (SD=.12); POMDP vs. I-POMDP: t(28)=4.91, CI=[0.06, 0.14] (from supplement) - Effect sizes not reported as Cohen's d, r, or eta-squared; only accuracy percentages and t-statistics available
- **effect_size:** - POMDP model accuracy: 84% (SD=0.06); LOOCV accuracy: 77% (SD=0.08) - POMDP vs. Q-learning accuracy: one-tailed paired t-test, t=-6.75, df=29, CI difference=[-0.08, -0.01]; LOOCV: t=2.20, df=29, CI=[0.00, 0.09] - POMDP vs. two-factor descriptive model accuracy: t=-4.86, df=29, CI=[-0.10, -0.02]; LOOCV: t=-7.61, df=29, CI=[-0.38, -0.22] - POMDP SUCCESS prediction accuracy: 71% (SD=0.07) - Contribution rate k=4 (55%, SD=.31) vs. k=2 (33%, SD=.18): t=3.94, df=29 - I-POMDP model accuracy: 73% (SD=.12); POMDP vs. I-POMDP: t(28)=4.91, CI=[0.06, 0.14] (from supplement) - Effect sizes not reported as Cohen's d, r, or eta-squared; only accuracy percentages and t-statistics available
- **learning_from:** Group; total number of contributions and SUCCESS/FAILURE outcome each round (social)
- **learning_about:** Group; average cooperativeness (theta) of group members (social)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** POMDP with Bayesian belief updating (Beta-Binomial); 3 params: alpha_1 (prior contribution expectation), beta_1 (prior free-ride expectation), gamma (decay/discount factor)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** 1. POMDP (Bayesian belief updating + forward planning) -- 3 params (alpha_1, beta_1, gamma) -- metric: round-by-round accuracy + LOOCV 2. Q-learning (model-free RL) -- 5 params (lambda_0, lambda_1, G, p_2, p_4) -- metric: round-by-round accuracy + LOOCV 3. Linear two-factor descriptive model (logistic regression) -- 3 params (kappa_0, kappa_1, kappa_2) -- metric: round-by-round accuracy + LOOCV 4. Greedy strategy (always free-ride) -- 0 params -- analytical proof it is suboptimal 5. I-POMDP (interactive POMDP) -- 3 params (same as POMDP but applied per-agent) -- metric: accuracy (from supplement)
- **model_mb_mf:** MB (model-based)
- **model_params:** - alpha_1 [S]: prior expectation of contributions by group; mean fitted value: alpha_1/beta_1 ratio mostly 0.5-2; (alpha_1+beta_1)/2 mostly 40-120 - beta_1 [S]: prior expectation of free-rides by group - gamma [S]: decay/discount factor for prior belief; mean=0.93, median=0.97
- **social_param:** alpha_1 and beta_1 jointly encode the prior belief about the group's cooperativeness (social state); gamma controls how much weight is given to recent social observations vs. prior beliefs about the group.
- **social_param_name:** alpha_1
- **social_param_value:** 0.93
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Round-by-round prediction accuracy + leave-one-out cross-validation (LOOCV) accuracy; paired t-tests between models
- **how_model_fit:** individual-level-fit (grid search over parameter space per subject)
- **data_type_fit_to:** choice behavior (contribute vs. free-ride decisions)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=29 (30 recruited, 1 dropped due to anxiety); mean age 22.97 +/- 0.37; 14 women. Each played 12 sessions of 15 rounds (with feedback).
- **population_category:** healthy adults
- **population_age_range:** M=22.97
- **ecological_validity:** Low-moderate. Computerized partners simulated human behavior (subjects were deceived into believing they played with real humans). Binary contribute/free-ride decision is simplified relative to real-world volunteering dilemmas. Abstract monetary incentives. However, the group setting and anonymous actions mirror some real-world collective action scenarios (e.g., voting, blood donation).
- **eligibility_flag:** 
- **concerns:** - Partners were computerized (not real humans), though their behavior was calibrated from prior human data - Preprint version read (.txt); published version is in Science Advances 2019 -- content appears essentially the same based on supplement header - No neuroimaging data despite authors' affiliation with neuroscience labs - Effect sizes not reported in standard formats (Cohen's d, etc.) -- only accuracy percentages and t-statistics - Grid search fitting (integer alpha/beta 1-200, gamma 0.01-1.0) rather than continuous optimization; may miss optima
- **limitations_reported:** Authors acknowledge: model assumes subject estimates cooperativeness before choosing next action; model uses longer horizon than actual rounds which deviates from optimality but provides computational benefit; multi-level theory of mind limited to few levels in humans; incomplete understanding of task by some subjects may explain contribution patterns; model based on binary actions only (could be extended to discrete sets); anonymous players only (non-anonymous case would require joint probability distribution with significant computational cost).
- **limitations_categorized:** task simplicity; limited ecological validity; deception (computerized partners); limited generalizability (binary actions only); model assumptions (fixed horizon, integer parameter grid); no neuroimaging validation
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM -- no standard effect sizes (d, r, eta-squared) reported; only accuracy % and t-statistics - citation: MEDIUM -- extracted from preprint .txt but supplement confirms published version in Sci. Adv. 2019; DOI from supplement - wc_3 (simulate): MEDIUM -- posterior predictive check present in supplement but unclear if simulations preceded fitting - wc_10 (transparency): MEDIUM -- no explicit mention of data/code sharing in preprint text
- **cannot_find:** - Standard effect sizes (Cohen's d, r-squared, etc.) - Data/code availability statement - Preregistration status
- **other_notes:** - The paper file is the bioRxiv preprint (Oct 2018); the published version appeared in Science Advances, Nov 2019, with the slightly modified title "Modeling other minds: Bayesian inference explains human choices in group decision-making" - Potential duplicate check: preprint/published pair -- should be treated as one paper (use published version citation) - The supplement contains an I-POMDP comparison and posterior predictive check not in the main preprint text - All 3 POMDP parameters are social in nature (they all pertain to beliefs about the group)
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = cooperation
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_cooperation
- tax_rr_topic_mentalizing
- tax_topic_cooperation
- tax_topic_mentalizing
