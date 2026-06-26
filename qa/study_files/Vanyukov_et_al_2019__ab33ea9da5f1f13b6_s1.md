# Vanyukov et al. (2019)

- **study_id:** `ab33ea9da5f1f13b6_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Vanyukov, P. M., Hallquist, M. N., Delgado, M. R., Szanto, K., & Dombrovski, A. Y. (2019). Neurocomputational mechanisms of adaptive learning in social exchanges. *Cognitive, Affective, & Behavioral Neuroscience*, *19*, 985–997. https://doi.org/10.3758/s13415-019-00697-0
- **citation_short:** Vanyukov et al. (2019)
- **doi:** 10.3758/s13415-019-00697-0
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofPsychiatry,UniversityofPittsburghSchoolof nals (Delgado, Frank, & Phelps, 2005; Fareri, Chang, &; etheoriesofsocialpreference(Camerer,2003),but ing signals would be more consistent with updating one’s; DepartmentofPsychology,PennsylvaniaStateUniversity,State were shown for social distance (e; centeredinstrumentalprocesscorrespondingtoreciprocalaltruism; DepartmentofPsychology,RutgersUniversity,Newark,NJ08901,; College,PA16802,USA friendvs; ethesecounterfactualoutcomes; labletoauthorizedusers; emails: dombax@upmc.edu
- **code_url:** 

## Computational level
- **study_focus:** Trust learning / cooperation learning — how people learn to cooperate or defect in iterated trust games through policy prediction errors incorporating counterfactual outcomes.
- **study_focus_short:** Trust learning / cooperation learning
- **learning_mode_description:** - Learning mode: Learning from one's own and counterfactual outcomes about the optimal policy (invest vs. keep) toward a trustee   - Learning from:     - Source type (non-social): self       - Content: outcomes (actual payoffs from invest/keep decisions)     - Source content (non-social): outcome       - Also incorporates counterfactual outcomes (would-be results of unchosen action)     - Source type (social): other (trustee)       - Content: action (trustee's share/keep decision, revealed on all trials including counterfactual)   - Learning about:     - Target type (social): other (trustee)     - Target content (non-social): action/policy (own optimal policy — invest vs. keep — toward the trustee)
- **task_description:** Participants played an iterated trust game with three fictional trustees (good, bad, neutral reputation) and a computer partner. On each trial, participants chose to invest $1.00 with the trustee (potentially receiving $1.50 if trustee shared, or $0 if trustee kept) or keep $1.00; crucially, the trustee's decision was revealed regardless of the participant's choice, providing counterfactual feedback. Trustees' cooperation rates changed across blocks (50%, then 25% or 88%, then reversed).
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (3 fictional trustees + 1 computer partner)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Faces (neutral male from NimStim), biographical text descriptions (good/bad/neutral reputation), binary monetary outcomes ($0, $1.00, $1.50)
- **method:** fMRI / behavioural
- **method_full:** fMRI (Study 3), behavioural (Studies 1 and 2)
- **main_result:** - Main Results:   - Policy RL model dominated alternatives in Bayesian model comparison (Study 1: exceedance probability = 0.986, BOR = 0.386; Study 2: ep = 1.0, BOR = 0.004; Study 3: ep = 1.0, BOR < 0.001)   - Counterfactual feedback on keep trials influenced next-trial investment: trustee share vs. keep increased subsequent investment (Study 1: b = 0.63, SE = 0.28; Study 2: b = 0.89, SE = 0.27; Study 3: b = 0.63, SE = 0.27)   - Policy-derived PE maps showed bilateral ventral and dorsal striatum activation (peak t(17) = 9.47 in left putamen)   - Policy PEs yielded greater striatal activation than alternative models: vs. actual rewards t(312) = -3.80; vs. regret t(312) = 4.58; vs. trustee-counterfactual t(312) = 4.01   - Previous trustee cooperation increased investment likelihood (Study 1: b = 0.57; Study 2: b = 0.89; Study 3: b = 0.53)   - Reputation effects decreased over time as reinforcement learning dominated (Trustee Type x Exchange Number interaction: Study 2 χ²(1) = 15.66; Study 3 χ²(1) = 31.80)
- **effect_size:** - Exceedance probability (policy model): Study 1 ep = 0.986; Study 2 ep = 1.0; Study 3 ep = 1.0 - Policy PE vs. actual rewards: t(312) = -3.80 - Policy PE vs. regret: t(312) = 4.58 - Policy PE vs. trustee-counterfactual: t(312) = 4.01 - Peak t in striatum for policy PE: t(17) = 9.47 - Model comparison χ² for model type predicting activation strength: χ²(3) = 26.24
- **learning_from:** Self and other; own investment outcomes and counterfactual outcomes of unchosen actions, plus trustee's share/keep decisions (revealed on all trials)
- **learning_about:** Other (trustee); own optimal policy (invest vs. keep) toward each trustee  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Q-learning policy model (θ learning rate, β temperature, κ_s subject bias, κ_t trustee bias); payoff matrix incorporates counterfactual outcomes of subject's unchosen action
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Actual-rewards model", "family": "Q-learning", "n_params": 4, "metric": "BMS exceedance probability"},   {"name": "Regret model", "family": "Q-learning", "n_params": 4, "metric": "BMS exceedance probability"},   {"name": "Trustee-counterfactual model", "family": "Q-learning", "n_params": 4, "metric": "BMS exceedance probability"},   {"name": "Policy model", "family": "Q-learning", "n_params": 4, "metric": "BMS exceedance probability"},   {"name": "Social value (SV) model", "family": "RL with social value parameter", "n_params": "unknown (described in supplement)", "metric": "BMS exceedance probability"} ]
- **model_mb_mf:** MF
- **model_params:** - θ (learning rate): governs update speed for Q(share); fitted values not reported in main text (in supplement) - β (temperature): softmax inverse temperature controlling choice stochasticity; fitted values not reported in main text - κ_s (subject-level bias): participant's general tendency to invest or keep; mean = 0.25 (SE = 0.03) as predictor of trustee-level bias - κ_t (trustee-level bias) [S]: condition-level parameter reflecting bias to invest/keep with a particular trustee, modelling reputation/social value effects; significantly different across trustee types (χ²(2) = 23.44)
- **social_param:** κ_t (trustee-level bias) [S] — captures the participant's bias to invest or keep with a particular trustee, modelling the effect of social reputation on cooperation independently of reinforcement learning.
- **social_param_name:** κ_t
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Bayesian model selection (BMS) with exceedance probability and Bayesian omnibus risk (BOR), implemented via VBA toolbox (variational Bayes approach)
- **how_model_fit:** individual-level-fit (VBA toolbox with uninformative Gaussian priors, M = 0, SD = 10)
- **data_type_fit_to:** choice behavior (binary invest/keep decisions)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — trial-wise PE estimates from VBA posterior convolved with HRF as parametric regressors in GLM (AFNI 3dDeconvolve/3dREMLfit)
- **contrast:** - Signed policy PE > baseline (whole-brain, p_voxelwise < .001, cluster-corrected p < .05): bilateral ventral and dorsal striatum, precuneus, frontal operculum/posterior insula, anterior/mid cingulate, posterior cingulate, lateral frontoparietal network - Policy PE beta coefficients > alternative model PE betas in a priori striatal ROI (Chase et al., 2015 meta-analytic mask): policy > actual rewards t(312) = -3.80; policy > regret t(312) = 4.58; policy > trustee-counterfactual t(312) = 4.01 - Model-free contrast: congruent (invest-return + keep-keep) vs. incongruent (keep-return + invest-keep) trials in ventral striatum (t_max = 4.52, k = 18 at p < 10^-4)
- **key_regions:** Policy prediction errors in bilateral ventral and dorsal striatum (putamen/lentiform nucleus); precuneus (BA7); anterior cingulate (BA24/32); inferior frontal gyrus (BA46); superior frontal gyrus (BA8); medial frontal gyrus (BA10); frontal operculum/posterior insula. Model-free analyses confirmed bilateral ventral striatum responses to congruent > incongruent trial outcomes.
- **key_regions_abbrev:** VS, putamen, dStr, striatum, ACC, insula, precuneus, IFG, SFG
- **coordinates_peak:** Left/right precuneus (BA7): -10, -52, 40 Left/right lentiform nucleus/putamen: -25, 9, 10 Left/right declive: -10, -69, -22 Right inferior frontal gyrus (BA46): 46, 29, 11 Left superior frontal gyrus (BA8): -32, 17, 55 Right middle frontal gyrus (BA8): 25, 34, 45 Left anterior cingulate (BA24/BA32): -3, 34, 16 Left medial frontal gyrus (BA10): -6, 65, 8 Right culmen: 29, -42, -27 Right postcentral gyrus (BA2): 64, -21, 29
- **analysis_type:** both (whole-brain for PE maps at p < .001 cluster-corrected; ROI using a priori meta-analytic PE mask from Chase et al., 2015 for model comparison beta extraction)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 69 total across 3 studies. Study 1 (behavioural only): n = 15 (older adults, M age = 70.11 years). Study 2 (scanner, behavioural results only reported here): n = 29 (younger adults, M age = 25.14 years, range 17–45). Study 3 (fMRI): n = 25 (older adults, same age range as Study 1); 3 excluded from fMRI (1 BOLD quality failure, 2 excessive motion), leaving n = 22 for neuroimaging. All free from psychiatric and organic brain disease.
- **population_category:** mixed
- **population_age_range:** 17–45
- **ecological_validity:** Low-moderate. Fictional trustees with predetermined cooperation schedules; no real social interaction. Counterfactual feedback (revealing trustee's decision on keep trials) is ecologically unusual. Blocked trustee design limits naturalistic social complexity. Reputation manipulations via brief biographies are artificial. Older adult sample (Studies 1 & 3) enhances generalizability across lifespan but limits comparability to typical young adult neuroimaging samples.
- **eligibility_flag:** 
- **concerns:** - Supplement not accessible — the paper references electronic supplementary material (parameter recovery details in Table S1/Fig S1, full PE maps for alternative models, social value model comparison, alternative implementations of trustee bias) but no supplement file was found in the papers folder. Parameter recovery and model identifiability details are therefore unverifiable from available materials. - Small fMRI sample (n = 22 after exclusions) limits statistical power for neuroimaging analyses. - Fictional trustees with no live interaction — cannot examine how participants represent impact of their actions on the counterpart. - Blocked trustee design prevents recovering unique baselines for trustees. - Age-related differences not systematically investigated despite two distinct age groups. - Fitted parameter values (θ, β) not reported in main text (stated to be in supplement).
- **limitations_reported:** One limitation of this study was the lack of a live trustee, which precluded us from examining how participants represented the impact of their own actions on the counterpart"; "reducing such strategic behavior in participants was necessary to closely examine trial-by-trial learning"; "Because the trials for each trustee had to be blocked rather than interleaved to enhance learning, we had to sacrifice the power to examine neural correlates of reputation and its putative interactions with PE signals"; "unique baselines for trustees could not be recovered, in contrast to studies with a mixed trial design"; "we also did not query participants whether they were consciously aware of the changes in reinforcement schedules"; "participants' exposure to counterfactual outcomes varied with their cooperation rate, raising questions about the robustness of our results vis-à-vis different strategies
- **limitations_categorized:** limited ecological validity; no real social interaction; task design constraints (blocked design); limited neural analysis power; no awareness check; differential counterfactual exposure across participants
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
- **wc_rule10:** No
- **wc_score:** 8.5
- **wc_total:** 8.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params (θ, β fitted values): MEDIUM — paper states fitted values are in supplement, which is not accessible - wc_guidelines rule 5 (parameter recovery): MEDIUM — reported summary statistics only (correlations > .4), details in inaccessible supplement - wc_guidelines rule 8 (validate winning model): MEDIUM — no formal posterior predictive check, but convergent model-free evidence provided - SV model n_params: LOW — described in supplement only, not in main text
- **cannot_find:** - Exact fitted mean values for θ (learning rate) and β (temperature) — stated to be in supplement - Full details of social value (SV) model architecture and parameters — described in supplement - Full PE maps for alternative models — in supplement - Alternative implementations of trustee-wise bias — in supplement
- **other_notes:** The paper contains 3 studies but all use the same task paradigm and are analysed together with the same models. Studies 1 and 2 are behavioural only; Study 3 is the fMRI study. The paper should be treated as a single study entry since the same computational models are applied across all three samples and the primary contribution is one unified analysis. The supplement is referenced extensively but was not available in the papers folder. The social value (SV) model from Fareri et al. (2015) was also tested but its key parameter was not significantly different from zero, so it is treated as a secondary analysis. The computer partner condition is ambiguous regarding social agency.
- **re_extract_flag:** false (full text available; supplement not accessible but main text extraction is complete)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_older_adults
- rr_pop_healthy_adults
- rr_pop_older_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_neural = shared
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_PE_signal
- tax_rr_param_perseveration
- tax_rr_primary_topic = trust
- tax_rr_secondary_topic = cooperation
- tax_rr_topic_cooperation
- tax_rr_topic_trust
- tax_social_nonsocial_comparison
- tax_topic_cooperation
- tax_topic_trust
