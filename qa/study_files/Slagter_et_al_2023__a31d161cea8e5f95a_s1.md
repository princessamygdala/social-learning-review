# Slagter et al. (2023)

- **study_id:** `a31d161cea8e5f95a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Slagter, S. K., van Duijvenvoorde, A. C. K., & van den Bos, W. (2023). Adolescents seek social information under uncertainty. *Journal of Experimental Psychology: General*, *152*(3), 890–905. https://doi.org/10.1037/xge0001299
- **citation_short:** Slagter et al. (2023)
- **doi:** 10.1037/xge0001299
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Psychology
- **affiliations_raw:** mitted to download or to forward/distribute the text or part of it without the consent of the author(s); university, we inform ourselves forms, adolescents have gained access to the behavior and opin-; University of Amsterdam, Secretariat, Singel 425, 1012 WP Amsterdam, The Netherlands; CenterforAdaptiveRationality,MaxPlanckInstituteforHumanDevelopment,Berlin,Germany; DepartmentofDevelopmentalPsychology,InstituteofPsychology,UniversityofAmsterdam; ethataddressestheactiveroleadolescentsmayhaveingaininginformationabout; ether, these results provide novel insights into the dynamics of peer; ether
- **code_url:** https://osf.io/wutf8/

## Computational level
- **study_focus:** Social information search — when and how much adolescents actively seek social information (peer choices) before making decisions under risk and ambiguity.
- **study_focus_short:** Social information search
- **learning_mode_description:** - Learning mode: Learning from classmates' revealed choices about one's own choice preference under uncertainty   - Learning from:     - Source type (social): group (classmates)     - Source content (social): action/policy (classmates' choices between safe and risky options)   - Learning about:     - Target type (non-social): self     - Target content (non-social): action/policy (own choice preference for risky vs. safe option)
- **task_description:** Adolescents chose between a safe option (5 points) and a risky gamble (variable reward and probability) in a gambling task. In the social version, before deciding, they could voluntarily reveal classmates' real choices for that trial by clicking boxes on a social board.
- **task_paradigm:** Risky decision-making
- **players:** Single agent (participant), multi-target (classmates; class size M = 20.58 in Exp 1; fixed board of 20 in Exp 2)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Gambling vases with green/black marbles (risk: full distribution shown; ambiguity: sample of marbles shown), social board of boxes revealing classmates' choices (blue = safe, yellow = risky)
- **method:** online / behavioural
- **method_full:** Behavioural (in-school tablets for Exp 1; online for Exp 2)
- **main_result:** - Experiment 1:   - Search initiation increased with choice difficulty (b = 0.18, SE = 0.06, OR 95% CI [1.07, 1.34])   - Search initiation increased with higher reward at stake (b = -0.44, SE = 0.06, OR 95% CI [0.57, 0.73])   - Search length increased with incongruent social information (b = 0.13, SE = 0.02, RR 95% CI [1.09, 1.19])   - Participants more likely to change initial choice with higher incongruent information (b = 0.58, SE = 0.06, 95% CI [0.46, 0.70])   - Ambiguity attitude did not predict search initiation or length - Experiment 2:   - Ambiguity increased search initiation vs. risk (b = 0.27, SE = 0.10, OR 95% CI [1.08, 1.59])   - Choice difficulty predicted search initiation (b = 0.24, SE = 0.06, 95% CI [1.12, 1.44])   - Reward predicted search initiation (b = -0.28, SE = 0.06, OR 95% CI [0.68, 0.85])   - Two-step sequential model with ambiguity + reward outperformed all other models (BIC = 15676.33 vs. next best 15920.26)   - Initiation threshold (d_M = 0.035) much smaller than decision threshold (k_M = 0.418)   - IUS did not predict search initiation or length
- **effect_size:** 
- **learning_from:** Group (classmates); classmates' choices between safe and risky options (social actions/policies)
- **learning_about:** Self; own choice preference (risk vs. safe) under uncertainty  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Two-step sequential sampling model with ambiguity (a) and reward (p) parameters: 2 thresholds (d for initiation, k for continuation), weighting parameter (h), sensitivity (s), ambiguity reduction (a), reward scaling (p). 5 free parameters.
- **model_family:** Bayesian
- **model_class:** Evidence accumulation
- **all_models_tested:** 1. At-chance model — 0 params — BIC (search+choice) = 21282.39 2. One-step sequential, simple — 2 params (d, h) — BIC = 33982.96 3. One-step sequential + ambiguity — 3 params (d, h, a) — BIC = 29496.63 4. One-step sequential + ambiguity + reward — 4 params (d, h, a, p) — BIC = 27598.95 5. Two-step sequential, simple — 3 params (d, k, h) — BIC = 17506.74 6. Two-step sequential + ambiguity — 4 params (d, k, h, a) — BIC = 15920.26 7. **Two-step sequential + ambiguity + reward** — 5 params (d, k, h, a, p) — **BIC = 15676.33** (WINNER)  Post-hoc extension with separate h for risky/safe info: BIC = 10400.98 (search process only; not directly comparable to above as different outcome).
- **model_mb_mf:** N/A (not RL; this is a sequential sampling / evidence accumulation model)
- **model_params:** - d: initiation threshold (mean = 0.035) [S] — threshold for deciding to seek social information - k: decision/continuation threshold (mean = 0.418) [S] — threshold for stopping social information search - h: weighting parameter [S] — sensitivity to social information (how much each revealed peer choice updates preference) - s: sensitivity parameter (estimated from solo data) — sensitivity to differences in expected utility - a: ambiguity parameter — reduction in choice sensitivity under ambiguity - p: reward scaling parameter — scales effect of reward on initiation threshold
- **social_param:** h (weighting parameter) — determines how much each piece of revealed social information (a classmate's choice) updates the participant's choice preference. Also d and k are social in that they govern the search for social information specifically.
- **social_param_name:** h
- **social_param_value:** 0.035
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (summed across participants)
- **how_model_fit:** Individual-level fit (MLE per participant, L-BFGS-B optimization with 50 random starting points)
- **data_type_fit_to:** Choice behavior and search behavior (both search initiation, search length, and final choice)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Experiment 1: N = 175 (of 193 recruited; 55% female; ages 11-19, M = 15.09, SD = 1.63). Experiment 2: N = 92 (of 409 recruited; 60% female; ages 11-14, M = 13.31, SD = 1.06). N = 87 for computational modeling in Exp 2 (5 excluded due to incomplete solo data).
- **population_category:** adolescents
- **population_age_range:** 11–19
- **ecological_validity:** HIGH for a social learning study — uses real classmates' choices rather than fictitious peers. Conducted in school settings (Exp 1) and online (Exp 2). However, the gambling task is still a laboratory abstraction of real-world risky decision-making. The authors note this limitation and suggest extending to other risk domains and more real-life decisions.
- **eligibility_flag:** 
- **concerns:** - Experiment 2 had significant attrition (409 recruited, only 92 completed) due to COVID-19 school closures, plus 3-month gap between sessions (vs. 3 weeks in Exp 1) - The congruency manipulation in Exp 1 was constructed (65-85% congruent/incongruent), so not purely naturalistic - Computational models only applied to Experiment 2; Experiment 1 uses only descriptive hurdle models - The "social" aspect of the models is in the search process — the actual preference update via h is relatively simple (additive) - No parameter recovery reported in main text; supplement referenced but not accessible - The winning model parameters (d, k, h, a, p) include both social and non-social elements — the social learning component (h) is not isolated from other decision components
- **limitations_reported:** Large individual differences in search not explained by tolerance for uncertainty measures; cannot make claims about specificity of findings for adolescents vs. adults (no adult comparison group); age analyses exploratory and should be interpreted with caution; domain-specific paradigm (gambling) may not generalize; cannot disentangle informational vs. normative motives for conformity; subsample did not search at all; discrepancy in search frequency between Exp 1 (in-school) and Exp 2 (online); small effect of reward on search length may lack adequate power in Exp 2.
- **limitations_categorized:** Limited generalizability; no adult comparison group; task simplicity; limited ecological validity; individual differences unexplained; sample size (Exp 2 attrition); online vs. in-person confound; cannot disentangle motivational mechanisms.
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Partial
- **wc_rule6:** Partial
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - wc_3 (simulate): MEDIUM — referenced in supplement but cannot verify   - wc_5 (parameter recovery): MEDIUM — referenced in supplement A5 but not accessible   - wc_6 (model recovery): MEDIUM — referenced in supplement A5 but not accessible   - model_params fitted values: MEDIUM — only d_M and k_M reported for winning model; h, a, p mean fitted values not reported in main text   - effect_size: MEDIUM — no standardized effect sizes (d, r-squared, eta-squared) reported; only regression coefficients with ORs/RRs and CIs  ### OTHER NOTES  - This paper is primarily about social *information search* rather than social *learning* per se — the "learning" component is the sequential updating of choice preference based on observed peer choices, which is modeled via the weighting parameter h in the sequential sampling framework. - The hurdle model in Experiment 1 is a statistical (descriptive) model, not a computational model of social learning — only Experiment 2's sequential sampling models qualify as computational models. - The paper bridges nonsocial information search literature (evidence accumulation models) with social influence research — a relatively novel contribution. - Post-hoc model with separate h for risky vs. safe social information improved fit further (BIC = 10400.98 for search process), suggesting asymmetric weighting of social information, though this was not the primary model comparison. - Data and code available at OSF: https://osf.io/wutf8/ - re_extract_flag: false
- **cannot_find:** Supplement not accessible (referenced as online supplemental materials at doi.org/10.1037/xge0001299.supp) — parameter recovery details (WC Rule 5), model recovery details (WC Rule 6), and detailed model fitting procedures are in supplement. Exact formula for how s is estimated from solo data is in Supplement B2. No effect sizes beyond regression coefficients (no Cohen's d, eta-squared).
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- rr_pop_adolescents
- rr_tax_mod_social_info_search
- spec_context = partly
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_G_uncertainty_volatility
- tax_mod_social_info_search
- tax_model_drift_diffusion
- tax_popclass_developmental
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = exploration_exploitation
- tax_rr_topic_exploration_exploitation
- tax_rr_topic_social_info_use
- tax_social_nonsocial_comparison
- tax_topic_exploration_exploitation
- tax_topic_social_info_use
