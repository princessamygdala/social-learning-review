# Siegel et al. (2018)

- **study_id:** `aa975564adbb29669_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Siegel, J. Z., Mathys, C., Rutledge, R. B., & Crockett, M. J. (2018). Beliefs about bad people are volatile. *Nature Human Behaviour*, *2*(10), 750-756. https://doi.org/10.1038/s41562-018-0425-1
- **citation_short:** Siegel et al. (2018)
- **doi:** 10.1038/s41562-018-0425-1
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** UCL Centre for Computational Psychiatry and Ageing Research, University College; ether people actually learn differently about agents inferred to; mits flexible updating of beliefs about potentially threatening; Department of Experimental Psychology, University of Oxford; Institute for Biomedical Engineering, University of; Centre for Neuroimaging, University College London; Department of Psychology, Yale University; ETH Zurich, Zurich, Switzerland; emails: mj.crockett@yale.edu
- **code_url:** https://osf.io/5s23d/

## Computational level
- **study_focus:** Moral inference / trait learning -- asymmetric Bayesian updating of beliefs about others' moral character, with greater volatility for beliefs about immoral agents.
- **study_focus_short:** Moral inference / trait learning -- asymmetric Bayesian updating of beliefs
- **learning_mode_description:** Learning from observing agents' moral choices (accept/reject money-for-shocks) about agents' moral character (harm aversion trait kappa). Asymmetric Bayesian updating with greater volatility for beliefs about immoral agents.
- **task_description:** Participants predicted sequences of choices made by two agents who decided whether to inflict painful electric shocks on a third party in exchange for money; one agent was "bad" (low harm aversion) and the other "good" (high harm aversion). After every third trial, participants rated their impression of each agent's moral character and their uncertainty about that impression.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (2 agents: 1 "good", 1 "bad")
- **n_players:** dyadic (2)
- **partner_type:** none
- **stimuli:** Binary choice outcomes (agent accepts/rejects money-for-shocks offers), text-based monetary and shock amounts, continuous character rating scales (nasty-nice), uncertainty rating scales
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Beliefs about bad agents were more volatile than beliefs about good agents across 6 studies (Study 1 omega: bad = -3.779, good = -4.212, P = 0.001; Study 2 omega: bad = -3.411, good = -3.877, P < 0.001) - Volatility asymmetry was significantly larger than ideal Bayesian observer (Study 2 delta-omega: participants = 0.446, Bayesian = 0.021, P < 0.001) - Participants entrusted good agents with twice as much money as bad agents in a trust game (Study 2: good = 7.15, bad = 3.36, P < 0.001; r = 0.653) - Asymmetry was specific to moral character (Study 4: morality delta-omega = 0.316, competence delta-omega = -0.060, P < 0.001) - Bad moral character destabilized beliefs about competence (Study 5 competence omega: bad = -4.224, good = -4.327, P = 0.002) - Bad agents' impressions were updated more following behavioral shift, especially improvement (Study 6: bad update = 18.951, good update = 14.928, P < 0.001; agent x shift interaction F(1,360) = 6.803, P = 0.009)
- **effect_size:** - Study 1 omega asymmetry: r = 0.519 (from Z = 3.212, N = 38) - Study 2 omega asymmetry: r = 0.535 (from Z = 6.830, N = 163) - Study 2 trust game: r = 0.667 (from Z = -8.522, N = 163) - Study 3 omega asymmetry: r = 0.628 (from Z = 7.296, N = 135) - Study 4 morality omega asymmetry: r = 0.404 (from Z = 4.219, N = 109) - Study 5 moral omega asymmetry: r = 0.369 (from Z = 5.079, N = 189) - Study 5 competence omega asymmetry: r = 0.220 (from Z = 3.030, N = 189) - Study 6 omega asymmetry (phase 1): r = 0.345 (from Z = 6.577, N = 364) - Study 6 agent x shift interaction: F(1,360) = 6.803, P = 0.009
- **learning_from:** other; observed moral choices of agents (whether they accept money for harming a victim)
- **learning_about:** other; agents' moral character (harm aversion trait, kappa)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** HGF (2-level reduced): x1 = binary choice prediction; x2 = belief about agent's kappa (Gaussian random walk with step size exp(omega)); decision model: V_harm = (1 - mu1_hat) * delta_m - mu1_hat * delta_s; P_harm = sigmoid(beta * V_harm). Two free parameters: omega (tonic volatility), beta (prediction noise).
- **model_family:** Bayesian
- **model_class:** PE learning / Belief updating
- **all_models_tested:** [   {"name": "HGF (2-level reduced)", "family": "Hierarchical Gaussian Filter / Bayesian belief updating", "n_params": 2, "metric": "LME + BMS (protected exceedance probability)"},   {"name": "1 learning rate Rescorla-Wagner", "family": "Rescorla-Wagner", "n_params": 2, "metric": "LME + BMS"},   {"name": "2 learning rate Rescorla-Wagner", "family": "Rescorla-Wagner", "n_params": 3, "metric": "LME + BMS"} ]
- **model_mb_mf:** Bayesian
- **model_params:** - omega (tonic volatility): governs the rate at which beliefs evolve over time (Gaussian random walk step size in log space). Key social parameter [S]. Fitted separately per agent per participant. Prior: mean = -4, variance = 1. Study 1 means: bad = -3.779, good = -4.212. Study 2 means: bad = -3.411, good = -3.877. - beta (prediction noise): sensitivity of predictions to relative utility of outcomes (softmax inverse temperature). Prior: mean = 1 (log space), variance = 1. - mu_2 (belief about agent's kappa): fixed prior mean = 0.5 (logit space), variance = 0. Trial-wise updated state, not freely estimated. - sigma_2 (belief uncertainty): fixed prior = 0.35 (log space), variance = 0. Trial-wise updated state.
- **social_param:** omega [S] -- tonic volatility of beliefs about agent's moral character (harm aversion). Higher omega = more volatile/uncertain beliefs = faster updating. The key finding is that omega is systematically higher for bad agents than good agents, indicating beliefs about immoral others are more volatile.
- **social_param_name:** omega
- **social_param_value:** -4
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Log-model evidence (LME) summed across studies; Bayesian Model Selection (BMS) with protected exceedance probability (random-effects procedure across all N = 1,419 participants). HGF achieved protected exceedance probability indistinguishable from 1 for both agents.
- **how_model_fit:** individual-level-fit (MAP estimation via BFGS optimization in HGF Toolbox, TAPAS)
- **data_type_fit_to:** choice behavior (trial-by-trial binary predictions of agent's choices)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Study 1: N = 38 (lab, Oxford; 1 excluded of 39). Study 2: N = 163 (AMT; 87 excluded of 253). Study 3: N = 135 (AMT; 27 excluded of 162). Study 4: N = 220 (109 morality, 111 competence; AMT; 60 excluded of 280). Study 5: N = 189 (AMT; 70 excluded of 259). Study 6: N = 364 (AMT; 44 excluded of 408; preregistered). Study 7 (supplement): N = 116 (AMT; 9 excluded of 125). Study 8 (supplement): N = 30 (AMT). Total across main studies 1-6: N = 1,109.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Limited. Agent behavior is computationally simulated rather than real. Moral transgression studied (accepting money for shocks) is relatively mild. Participants do not interact with agents but only observe pre-determined choice sequences. Online participants (Studies 2-8) with high exclusion rates (up to 34% in Study 2) may limit generalizability.
- **eligibility_flag:** 
- **concerns:** Very high exclusion rates, especially for online studies (34% in Study 2, 27% in Study 5). Agents are simulated, not real social partners. The paper contains 8 studies but main analyses focus on Studies 1-6. Studies 7-8 are supplementary validation studies. The HGF is fit separately per agent, so the omega asymmetry could partially reflect model misspecification rather than a true cognitive asymmetry (though authors address this by comparing to ideal Bayesian observer). Data and code available only "upon request" rather than openly shared.
- **limitations_reported:** Our paradigm has an important limitation: accepting money in exchange for shocks that are painful but not dangerous is a relatively mild moral transgression"; "it is unclear how these results will generalize to learning about more extreme transgressions, such as assault, rape, or murder"; authors note the need for future work to directly manipulate perceived threat while holding behavior constant.
- **limitations_categorized:** limited ecological validity; limited generalizability (mild transgressions only); task simplicity; no direct threat manipulation
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Partial
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** yes
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `preregistered`: MEDIUM -- only Study 6 was preregistered; coded as "Partial" - `wc_guidelines.rule_5`: MEDIUM -- partial parameter recovery (tested RW vs HGF recovery direction but no formal HGF parameter recovery) - `effect_size`: HIGH -- all effect sizes computed from reported Z-statistics and N using Rosenthal's r = Z/sqrt(N) - All other fields: HIGH confidence
- **cannot_find:** No fields left blank. All information extracted from full text + embedded supplements.
- **other_notes:** The paper contains 8 studies total (6 main + 2 supplementary). Studies 1-6 are the primary studies. Study 7 is a replication with different rating scale labels. Study 8 estimates prior expectations about agent behavior. The supplements are embedded in the same file as the main text. The HGF Toolbox (TAPAS) was used: https://tnu.ethz.ch/tapas. This is a single extraction row because all 6 main studies address the same learning mode with the same model -- they are replications and extensions rather than independent studies with different computational questions.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_depth = parametric
- spec_locus = target+context
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_HGF
- tax_model_bayesian
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_F_affective_moral
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = moral_harm
- tax_rr_secondary_topic = trait_impression
- tax_rr_topic_moral_harm
- tax_rr_topic_trait_impression
- tax_topic_moral_harm
- tax_topic_trait_impression
