# Lindstrom et al. (2021)

- **study_id:** `ac42c30ad279615ee_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lindstrom, B., Bellander, M., Schultner, D. T., Chang, A., Tobler, P. N., & Amodio, D. M. (2021). A computational reward learning account of social media engagement. *Nature Communications*, *12*, 1311. https://doi.org/10.1038/s41467-020-19607-x
- **citation_short:** Lindstrom et al. (2021)
- **doi:** 10.1038/s41467-020-19607-x
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Psychology
- **affiliations_raw:** ether, and how, reward learning mechanisms ternsthatwouldcharacterizeonlinebehaviorasanexpressionof; mpirical evidence for social also confirm, using an online experiment resembling common; DepartmentofPsychologicalandBrainSciences,BostonUniversity,Boston,MA,USA; DepartmentofPsychology,UniversityofAmsterdam,Amsterdam,TheNetherlands; ether reward learning mechanisms contribute to social media behavior; CenterforPsychiatryResearch,DepartmentofClinicalNeuroscience,; DepartmentofEconomics,UniversityofZürich,Zürich,Switzerland; mpirical evidence for social media engagement as reward-; emails: bjorn
- **code_url:** 

## Computational level
- **study_focus:** Social reward learning on social media -- how "likes" function as social rewards that drive posting behavior through reinforcement learning mechanisms.
- **study_focus_short:** Social reward learning on social media -- how "likes" function as social
- **learning_mode_description:** - Learning mode: Learning from social approval feedback (likes) about one's own posting behavior to maximize social reward rate.   - Learning from:     - Source type (social): group (anonymous online users providing likes)     - Source content (social): outcome (number of likes received per post)   - Learning about:     - Target type (non-social): self (own posting policy/response latency)     - Target content (non-social): action/policy (optimal timing/latency of posting)
- **task_description:** - *Studies 1-2*: Observational analysis of real social media posting behavior. Users post images on social media platforms (Instagram, fashion/gardening forums) and receive likes as social feedback; the time between successive posts (response latency) is the key dependent variable. - *Study 3*: Online experiment where participants post "memes" during a 25-minute session and receive manipulated numbers of likes (0-9 vs. 10-19) from ostensible other users, with reward rate shifted between session halves.
- **task_paradigm:** Social media (likes) task
- **players:** - Studies 1-2: Single agent (social media user), multi-target (anonymous group of followers/forum members providing likes) - Study 3: Single agent (participant), multi-target (ostensible online users providing likes)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** User-generated images (Instagram photos, clothing photos, garden photos, memes); social feedback in the form of "likes" (integer counts)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Studies 1-2: Social media posting behavior conforms to reward learning principles -- the R-bar L model explained behavior better than a no-learning model for ~70-77% of individuals across all four platforms   - Study 1 (Instagram): Model-based R-bar predicted post latency (beta = -0.18, SE = 0.003, t = -54.59, p < .0001); mean AIC_W = 0.70, exceedance probability = 1   - Study 2 (Men's fashion): beta = -0.08, SE = 0.016, t = -5.1, p < .0001; mean AIC_W = 0.77   - Study 2 (Women's fashion): beta = -0.16, SE = 0.02, t = -7.1, p < .001   - Study 2 (Gardening): beta = -0.18, SE = 0.02, t = -12.09, p < .001   - Quantitative law of effect: hyperbolic function R-squared = 0.43 (Study 1), 0.37 (Study 2)   - Granger causality: likes Granger-caused post latency in all datasets - Study 3 (Experiment): Higher reward rate caused shorter post latencies (beta = 0.109, SE = 0.044, z = 2.47, p = .013), corresponding to 10.9% difference - Four computational phenotype clusters identified via k-means clustering of model parameters across N = 4,168 users
- **effect_size:** - Study 1: beta = -0.18 (R-bar on tau_Post); ~18% latency reduction high vs low R-bar; AIC_W = 0.70 - Study 2: betas = -0.08, -0.16, -0.18 across three platforms; AIC_W = 0.77 (pooled) - Study 3: beta = 0.109 (~10.9% difference in posting latency between reward conditions) - Hyperbolic fits: R-squared = 0.43 (Instagram), 0.37 (Study 2 platforms)
- **learning_from:** Group (anonymous social media users); social reward outcomes (likes received on posts)
- **learning_about:** Self; own posting policy/response vigor (optimal timing between successive posts)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** R-bar L model -- policy gradient version of R-learning (3 params: alpha [learning rate], P [initial policy], C [effort cost sensitivity]). Formula: tau_Post(t) = e^(Policy(t) - alpha * R-bar(t)); delta(t) = R(t) - C/tau_Post(t) - R-bar(t) * tau_Post(t); Policy(t+1) = Policy(t) + alpha * Delta_tau_Post(t) * delta(t); R-bar(t+1) = R-bar(t) + alpha * delta(t)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "R-bar L model", "family": "Policy gradient RL (R-learning)", "n_params": 3, "metric": "AIC_W, BMS exceedance probability"} 2. {"name": "No learning model", "family": "Baseline (stable response rate)", "n_params": 1, "metric": "AIC_W, BMS exceedance probability"} 3. {"name": "R-bar L without effort cost (C)", "family": "Policy gradient RL", "n_params": 2, "metric": "AIC_W"} (Supplementary Note 6) 4. {"name": "R-bar L without R-bar parameter", "family": "Policy gradient RL", "n_params": 2, "metric": "AIC_W"} (Supplementary Note 6) 5. {"name": "R-bar L with fixed effort cost", "family": "Policy gradient RL", "n_params": 3, "metric": "AIC_W"} (Supplementary Note 6) 6. {"name": "R-bar L with increasing effort cost", "family": "Policy gradient RL", "n_params": 3, "metric": "AIC_W"} (Supplementary Note 6) 7. {"name": "Model without instrumental response policy", "family": "Non-instrumental", "n_params": "not specified", "metric": "AIC_W"} (Supplementary Note 6) 8. {"name": "Foraging theory model", "family": "Foraging/optimal foraging", "n_params": "not specified", "metric": "AIC_W"} (Supplementary Note 6)  Note: Models 3-8 are described in Supplementary Note 6 (supplement not accessible). Exact parameter counts for some alternatives cannot be confirmed.
- **model_mb_mf:** MF (model-free; the R-bar L model uses scalar prediction errors to update a policy without building an internal model of the environment)
- **model_params:** - alpha (learning rate; 0 < alpha <= 1): step size for all update equations (policy, R-bar) - P (initial response policy; 0 <= P <= infinity): sets starting tau_Post at t=1 - C (effort cost sensitivity; 0 < C <= infinity): user-specific subjective cost of posting; penalizes fast responding - [No parameter explicitly marked [S], but the entire model is applied to social reward (likes). C could be considered social-context-relevant as it reflects the effort cost of social media posting specifically.]  Mean fitted values: Not reported in the main text (median best-fitting parameters used for generative simulations but numeric values not provided in accessible text).
- **social_param:** No parameter is explicitly designated as a "social" parameter. The model treats likes as generic rewards. The effort cost parameter C is specific to the social media posting context but is not formally social in the RL framework.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC weights (AIC_W), Bayesian random effects model comparison (exceedance probability), Granger causality
- **how_model_fit:** individual-level-fit (parameters optimized for each individual user)
- **data_type_fit_to:** choice behavior (specifically, inter-post latencies / response timing)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** - Study 1: N_Users = 2,039; N_Obs = 851,946 (Instagram) - Study 2: N_Users = 2,127 (Men's fashion: 543; Women's fashion: 773; Gardening: 813); N_Obs = 190,721 - Study 3: N_Participants = 176; N_Posts = 2,206 - Total across Studies 1-2: N_Users = 4,168; N_Obs = 1,046,857
- **population_category:** unclear
- **population_age_range:** 
- **ecological_validity:** HIGH. Studies 1-2 use real-world social media data from actual platforms (Instagram, fashion forums, gardening forum) representing naturalistic behavior over extended time periods. Study 3 uses a lab-based online experiment designed to mimic social media but is less ecologically valid (25-minute session, posting memes for manipulated likes from ostensible users).
- **eligibility_flag:** 
- **concerns:** - No supplement accessible -- alternative models (Supplementary Notes 5-6) could not be fully verified for parameter counts and formulas. - Studies 1-2 are observational/correlational (cannot establish causation); Study 3 partially addresses this but is a simplified lab analogue. - Real social media data are anonymous -- no demographic information available for Studies 1-2. - Potential for fraudulent accounts / "fake likes" on Instagram (authors acknowledge this). - The social aspect of the reward (likes) is treated identically to non-social reward in the model -- the model does not distinguish social from non-social reward mechanisms. - Mean fitted parameter values not reported in main text.
- **limitations_reported:** The analysis focused on timing rather than content of posts, limiting understanding of what people learn to post; economic motives on Instagram could confound reward learning; no demographic characterization of users in Studies 1-2; cannot speak to neurobiological basis from behavioral data alone; the model does not incorporate relational considerations (reciprocity, network proximity); negative feedback (downvotes) not modeled; the experimental task (Study 3) simplified real social media; correlational nature of big data in Studies 1-2 necessitates caution regarding social comparison findings.
- **limitations_categorized:** limited ecological validity (Study 3); limited generalizability (no demographics); task simplicity (timing only, not content); confounds (economic motives); no neural data; model simplicity (no social-specific mechanisms, no negative feedback); correlational design (Studies 1-2)  ---  ## WC CHECKLIST  1. **Design a good experiment**: Yes -- Study 3 experimentally manipulates reward rate; Studies 1-2 use naturalistic data that engage the targeted reward learning process. 2. **Design good models**: Yes -- Multiple alternative models tested (R-bar L, no learning, variants without effort cost, without R-bar, with different cost structures, foraging model). 3. **Simulate, simulate, simulate**: Yes -- Extensive generative simulations conducted before/alongside fitting (simulated 1000 synthetic users, 250,000 data points; generative simulations from median parameters to reproduce observed effects). 4. **Fit the parameters**: Yes -- Individual-level MLE fitting for each user. 5. **Check parameter recovery**: Yes -- "model estimation and comparison procedure recovered the models with high probability" (Supplementary Fig. 2). 6. **Check model recovery**: Yes -- Granger causality method validated on simulated data from both learning and no-learning generative models; model comparison procedure tested on simulated data (Supplementary Fig. 2). 7. **Fit real data and compare models**: Yes -- AIC_W and Bayesian random effects model comparison across all datasets. 8. **Validate the winning model**: Yes -- Generative simulations from estimated parameters reproduce observed effects (posterior predictive-like check); multiple robustness checks (removing outliers, splitting data). 9. **Analyze the winning model**: Yes -- R-bar estimates used to predict behavior; individual difference profiles via k-means clustering of parameters; computational phenotyping. 10. **Report results transparently**: Yes -- Code available on OSF (osf.io/765py/); Study 1 data described in ref 30; Study 3 data on OSF; Study 2 data available on request.
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 10
- **wc_total:** 10.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `model_params` (mean fitted values): MEDIUM -- median best-fitting parameters used for simulations but numeric values not reported in accessible main text. Likely in supplement. - `all_models_tested` (n_params for alternatives): LOW -- Supplementary Note 6 not accessible; exact parameter counts for some alternative models unknown. - `social_param`: MEDIUM -- no parameter is explicitly social; the model applies generic RL to social rewards without a distinct social mechanism. - `learning_mode target_type`: MEDIUM -- classified target as "self / action-policy" (learning about own posting behavior), though this is in a social context. Could be debated.
- **cannot_find:** - Exact mean/median fitted parameter values for alpha, P, C (likely in supplement which is not accessible) - Exact parameter counts and formulas for all alternative models in Supplementary Note 6 - Whether study was preregistered
- **other_notes:** - Supplement not accessible (no supplement file found in the papers folder). The paper references extensive supplementary materials (Supplementary Notes 1-12, Supplementary Methods, Supplementary Figs 1-5, Supplementary Tables 1-7) which contain important details about alternative models, robustness checks, and parameter recovery. - This is a 3-study paper: Study 1 (Instagram observational), Study 2 (3 forum sites observational), Study 3 (online experiment). For the systematic review, this could be treated as one row (unified model across studies) or separated. The winning model and framework are identical across all studies; Study 3 provides experimental validation. - The model (R-bar L) is a policy gradient variant of R-learning from the animal learning literature (Niv et al., 2007), adapted to social media. It is notable for applying RL at timescales of days/weeks rather than seconds/minutes. - The "social" nature of the reward is the key claim, but the computational model itself is domain-general (identical to non-social RL). The social dimension lies in the reward source (likes from others) rather than in any social-specific computational mechanism.
- **re_extract_flag:** false (full text was accessible; supplement not found but main text is comprehensive)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_topic_social_approval_reward
