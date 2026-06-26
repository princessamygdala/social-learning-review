# Ho et al. (2017)

- **study_id:** `a4aea460e9fdfae26_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Ho, M. K., Littman, M. L., Cushman, F., & Austerweil, J. L. (2017). Effectively learning from pedagogical demonstrations. In G. Gunzelmann, A. Howes, T. Tenbrink, & E. J. Davelaar (Eds.), *Proceedings of the 39th Annual Conference of the Cognitive Science Society*. Austin, TX: Cognitive Science Society.
- **citation_short:** Ho et al. (2017)
- **doi:** Not reported in the paper. No DOI provided.
- **publication_type:** conference proceedings (peer-reviewed)
- **year:** 2017.0
- **field_of_study:** Computer science / AI
- **affiliations_raw:** DepartmentofCognitive,Linguistic,andPsychologicalSciences,190ThayerStreet; DepartmentofPsychology,UniversityofWisconsin-Madison,1202WJohnsonStreet; dept at ty- ementsofplanning(Puterman,1994; Sutton&Barto,1998); DepartmentofComputerScience,BrownUniversity,115WatermanStreet; DepartmentofPsychology,1484WilliamJamesHall,33KirklandSt; etheirbeliefsinaccordancewithBayesianinference:; eTheoryofMind; emails: cushman@fas.harvard.edu, ho@brown.edu, austerweil@wisc.edu
- **code_url:** https://github.com/markkho/demonstration-teach-learn

## Computational level
- **study_focus:** Observational learning / learning from pedagogical demonstration. How observers learn task structure from demonstrations that may or may not be produced with communicative (teaching) intent, modeled via recursive Theory of Mind and cognitive hierarchy.
- **study_focus_short:** Observational learning / learning from pedagogical demonstration
- **learning_mode_description:** - Learning mode: Learning from a demonstrator's actions about the reward structure (which colors are safe vs. dangerous) of a gridworld task   - Learning from:     - Source type (social): other (demonstrator/partner)     - Source content (social): action/policy (observed demonstration trajectories)   - Learning about:     - Target type (non-social): world (task reward structure)     - Target content (non-social): state (which colors are safe vs. dangerous -- reward function)
- **task_description:** Participants observed a partner navigating a gridworld where the agent moved to a yellow goal tile worth 10 points while avoiding colored tiles that could be safe (0 points) or dangerous (-2 points). Observers judged which colors were safe or dangerous based on the demonstration, with conditions varying whether the demonstration was produced with communicative intent and whether the observer was told about that intent.
- **task_paradigm:** Observational learning task
- **players:** Single agent (observer/participant), dyadic (demonstrator partner from prior study)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Gridworld with colored tiles (orange, purple, cyan), animated demonstration trajectories, binary safe/dangerous judgments, confidence scale (0-100)
- **method:** online / behavioural
- **method_full:** Behavioural (online, MTurk)
- **main_result:** - Main Results:   - Main effect of demonstrator instructions (showing vs. doing) on accuracy (b = 0.40, SE = 0.11, z = 3.63); showing demonstrations increased accuracy by 1.5 times (odds ratio = 1.49)   - Main effect of observer instructions (showing vs. doing interpretation) on accuracy (b = 0.13, SE = 0.07, z = 1.97); interpreting as showing increased accuracy by 1.14 times (odds ratio = 1.14)   - Main effect of demonstrator instructions on confidence (b = 3.34, SE = 0.93, t(57.2) = 3.59)   - Main effect of observer instructions on confidence (b = 3.57, SE = 0.87, t(1790.8) = 4.08)   - Likelihood-ratio test for showing model: 7/8 reward functions rejected null in showing condition (all chi-squared(29) > 42.5)
- **effect_size:** Odds ratios: OR = 1.49 (demonstrator showing effect on accuracy), OR = 1.14 (observer showing interpretation effect on accuracy). Regression coefficients reported above. No Cohen's d or r-squared reported.
- **learning_from:** Other (demonstrator); observed demonstration trajectories in gridworld
- **learning_about:** World; reward structure (which tile colors are safe vs. dangerous)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Observer-Belief MDP (OBMDP) showing model with nested doing model. Sophisticated observer who reasons about demonstrator's communicative intent via Bayesian inference over showing policies. Parameters: gamma_Do = .99, tau_Do = 3.0, gamma_Show = .9, tau_Show = 1.0 (showing agent); naive observer uses nested doing params. Softmax policy over Q-values in joint belief-ground state space.
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - Doing agent (MDP with softmax policy): family = MDP, n_params = 2 (gamma_Do, tau_Do), metric = likelihood-ratio test - Showing agent (OBMDP): family = Observer-Belief MDP, n_params = 4 (gamma_Do, tau_Do, gamma_Show, tau_Show), metric = likelihood-ratio test - Naive observer (Bayesian inference over doing models): family = Bayesian inverse planning, n_params = 2 (nested doing params), metric = qualitative comparison - Sophisticated observer (Bayesian inference over showing models): family = Bayesian inverse planning, n_params = 4 (nested showing params), metric = qualitative comparison
- **model_mb_mf:** MB (model-based; planning in belief space with full transition model)
- **model_params:** - gamma_Do (doing discount factor) = .99 - tau_Do (doing temperature) = .08 (doing agent) / 3.0 (nested in showing agent) - gamma_Show (showing discount factor) = .9 - tau_Show (showing temperature) = 1.0 - kappa (k; weight on communicative reward in R_Show) [S] -- value not reported - Prior over MDPs (uniform over 8 reward functions)
- **social_param:** kappa (k) [S] -- controls the degree of demonstrator's motivation to show/teach, weighting observer belief changes in the reward function (Equation 3). This is the key social parameter that balances communicative goals against task rewards.
- **social_param_name:** kappa
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Likelihood-ratio test (comparing showing OBMDP model vs. null doing-only model with tau_Do = 1000)
- **how_model_fit:** Parameters were hand-set (chosen to produce trajectories qualitatively comparable to human demonstrations), not fitted via MLE/Bayesian estimation. Model predictions compared qualitatively and via likelihood-ratio test on demonstrator data.
- **data_type_fit_to:** Choice behavior (demonstrator trajectories; observer safe/dangerous judgments)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A -- no neuroimaging
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Experiment (observer study): 2 MTurkers per each of 464 demonstrations x 2 observer conditions. Exact total N not explicitly stated but implied ~1856 participant-observations. Original demonstrator data from Ho et al. (2016): N = 29 per condition (doing and showing). Confidence: MEDIUM (exact observer N not clearly stated).
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low ecological validity. Gridworld task is abstract and artificial. Demonstrations are pre-recorded animated trajectories shown to online participants, not live social interaction. The "partner" framing is minimal -- participants are told they are observing a partner but there is no real interaction.
- **eligibility_flag:** Borderline eligibility. The paper models learning from demonstration using computational models (Bayesian inverse planning, MDPs) and uses human behavioral data. However, the learning is arguably one-shot inference (observe one demonstration, then judge reward function) rather than learning over time with trial-by-trial updating. The observer sees a single demonstration trajectory and makes a judgment -- there is no multi-trial learning process. Flag: "Borderline: learning may be one-shot inference from a single demonstration rather than learning over time. The demonstrator model involves sequential planning, but the observer's task is a single inference episode.
- **concerns:** - Model parameters were hand-tuned, not fitted to individual participants (tau_Do, gamma_Do, etc. were "chosen to produce trajectories qualitatively comparable to human demonstrations") - No formal model fitting to observer data -- model predictions compared qualitatively to human accuracy/confidence patterns - The value of kappa (k), the key social parameter, is never reported - Sample size for the observer experiment is not clearly stated - Borderline one-shot inference rather than learning over time - No parameter recovery or model recovery analyses - Demonstrations from a prior study (Ho et al., 2016) were reused, not newly collected
- **limitations_reported:** The authors note: uncertainty in the observer's uncertainty could influence demonstrator behavior that cannot be explained by the current model; the model's belief space transitions are deterministic and known with certainty, which is unrealistic; the experiment did not test time course predictions of naive vs. sophisticated observer inferences; important differences might arise in more complex domains with longer time horizons.
- **limitations_categorized:** Model simplification assumptions; limited ecological validity; task simplicity; no temporal dynamics tested; deterministic belief transitions unrealistic; no interactive teaching/learning modeled
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 6.0
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `citation` (MEDIUM): Year inferred as 2017 from context; not explicitly stated in text - `sample_size` (MEDIUM): Exact N for observer experiment not clearly reported; inferred from design description - `kappa value` (LOW): The key social parameter kappa (k) is defined in Equation 3 but its fitted/chosen value is never reported - `model_params` (MEDIUM): Parameters were hand-set, not fitted; tau_Do differs between doing agent (.08) and nested doing model in showing agent (3.0), which is noted but may cause confusion - `eligibility_flag` (MEDIUM): Borderline one-shot inference vs. learning over time
- **cannot_find:** - Exact total N for the observer experiment - Value of kappa (k) parameter - Year of publication (inferred) - DOI - No supplement available
- **other_notes:** This is a CogSci conference proceedings paper (6 pages), not a full journal article. The paper builds on Ho et al. (2016, NeurIPS) and references an in-prep manuscript (Ho, Littman, Cushman, & Austerweil, in prep). The modeling framework is primarily theoretical/computational -- the "experiment" tests model predictions but does not fit the model to individual participant data. Code is available at https://github.com/markkho/demonstration-teach-learn. No supplement exists for this paper.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_pedagogical_sampling
- spec_context = social
- spec_depth = structural
- spec_locus = source+target
- spec_source = social
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_pedagogical_sampling
- tax_model_MB
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_temperature
- tax_rr_primary_topic = pedagogical_reasoning
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_pedagogical_reasoning
- tax_social_nonsocial_comparison
- tax_topic_mentalizing
- tax_topic_pedagogical_reasoning
