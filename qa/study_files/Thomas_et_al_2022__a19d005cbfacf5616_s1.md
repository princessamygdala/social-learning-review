# Thomas et al. (2022)

- **study_id:** `a19d005cbfacf5616_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Thomas, L., Lockwood, P. L., Garvert, M. M., & Balsters, J. H. (2022). Contagion of temporal discounting value preferences in neurotypical and autistic adults. *Journal of Autism and Developmental Disorders*, *52*, 700–713. https://doi.org/10.1007/s10803-021-04962-5
- **citation_short:** Thomas et al. (2022)
- **doi:** 10.1007/s10803-021-04962-5
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Psychology
- **affiliations_raw:** Department of Experimental Psychology, University well as the participant’s degree of uncertainty in their initial; Department of Psychology, Royal Holloway, University information about the credibility of external sources of; Centre for Integrative Neuroimaging, Department accounts) have also been employed to explain behaviours; Centre for Human Brain Health, School generate precise internal prior beliefs about the world (both; Department of Psychology, Max Planck Institute for Human the width) of priors; University of Oxford, in autism spectrum conditions (ASC); University of Birmingham, Bir
- **code_url:** 

## Computational level
- **study_focus:** Social influence / contagion of value preferences — whether learning the temporal discounting preferences of another person shifts one's own discount rate, and whether this contagion is modulated by autistic traits.
- **study_focus_short:** Social influence / contagion of value preferences
- **learning_mode_description:** - Learning mode: Learning from another person's temporal discounting choices (via explicit feedback) about one's own value preferences (discount rate shifts toward the other)   - Learning from:     - Source type (social): other (simulated agent with distinct discount rate)     - Source content (social): action/policy (the other agent's temporal discounting choices, conveyed via trial-by-trial feedback)   - Learning about:     - Target type (non-social): self (own discount rate / value preferences)     - Target content (non-social): state (own internal value representation — discount rate k)
- **task_description:** Participants made temporal discounting choices (small-immediate vs. larger-delayed monetary rewards) for themselves across interleaved Self and Other blocks; in Other blocks they predicted two simulated agents' choices (one more patient, one more impulsive than the participant) and received trial-by-trial accuracy feedback. Contagion was measured as the shift in the participant's own discount rate after learning each other's preferences.
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), multi-target (2 simulated agents: 1 more patient, 1 more impulsive)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Monetary reward pairs (£1–20, immediate vs. delayed by 1 day to 3 months), trial-by-trial correct/incorrect feedback during Other blocks
- **method:** online / behavioural
- **method_full:** behavioural (online questionnaires + lab-based computerised task)
- **main_result:** - Study 1 (N=48 NT): Significant contagion for patient others (W(47) = 1005, d = 0.62, BF10 = 284.98) and impulsive others (d = 0.31, BF10 = 1.10) - Study 2 (N=98 NT): Significant contagion for patient others (d = 0.37, BF10 = 41.76); not significant for impulsive others (d = 0.13, BF01 = 4.10) - Study 3 (N=12 ASC vs N=12 matched NT): Equivalence supported — contagion similar across groups (BF equivalence: impulsive = 4.96, patient = 9.13); accuracy equivalent (BF equivalence: impulsive = 18.66, patient = 16.00) - AQ subscales did not predict contagion in collapsed NT samples (impulsive model: R² = 0.8%, F(7,131) = 0.84, BF01 = 184.26; patient model: R² = 6.9%, F(7,131) = 2.46, BF10 = 0.40, no individual predictors significant)
- **effect_size:** d = 0.62 (Study 1, patient contagion); d = 0.31 (Study 1, impulsive contagion); d = 0.37 (Study 2, patient contagion); d = 0.13 (Study 2, impulsive contagion); BF equivalence tests for ASC vs NT reported above
- **learning_from:** Other (simulated agent's temporal discounting choices, via explicit feedback); source: other
- **learning_about:** Self (own discount rate / value preference); target: self  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Bayesian belief updating of log k (discount rate) with KL divergence as contagion measure. Log-hyperbolic discounting model: V = M / (1 + kD); softmax choice rule: P_LL = 1 / (1 + exp(-β(V_LL - V_SS))); trial-by-trial Bayesian update of uniform prior over log k and log β.
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** Only one computational model is reported (Bayesian belief updating of the log-hyperbolic discounting model). The paper compares the DKL contagion measure against a simpler "shift" measure (from Garvert et al., 2015) and finds DKL produces larger Bayes factors, but this is a comparison of outcome measures, not competing generative models. [{"name": "Bayesian belief updating (log-hyperbolic + softmax)", "family": "Bayesian belief updating", "n_params": 2, "metric": "N/A — single model"}]
- **model_mb_mf:** Bayesian
- **model_params:** - log k: discount rate (range -4 to 0); updated trial-by-trial via Bayesian posterior. Higher values = steeper discounting (more impulsive). [S] — the other agent's log k is set at participant's log k ± 1, making the social manipulation operate through this parameter. - log β: inverse temperature / choice noise (range -1 to 1); fixed at 1 for Other blocks, starts at 0.3 for Self blocks. - DKL (Kullback-Leibler divergence): derived measure quantifying shift in posterior distribution between blocks (not a fitted parameter per se, but the key dependent variable measuring contagion).  Mean fitted values: Study 1 mean log k = -2.17 (SD = 0.84), mean log β = -0.13 (SD = 0.27); Study 2 mean log k = -1.68 (SD = 0.67), mean log β = -0.19 (SD = 0.35); Study 3 mean log k = -2.28 (SD = 0.78), mean log β = -0.08 (SD = 0.52).
- **social_param:** The social manipulation operates through log k — the other agent's discount rate is set at ±1 of the participant's own log k. Contagion is measured as the KL divergence of the participant's posterior log k distribution toward the other's.
- **social_param_name:** The social manipulation operates through log k
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** -4–0
- **model_comparison_metric:** Bayes factors (comparing DKL measure vs. shift measure, not formal model comparison)
- **how_model_fit:** individual-level-fit (Bayesian posterior updated trial-by-trial per participant)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study only)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Study 1: N=48 NT (after 1 exclusion; 23 female, mean age 23.81); Study 2: N=98 NT (after 2 exclusions; 59 female, mean age 21.41); Study 3: N=12 ASC (after 2 exclusions; 8 female, mean age 22.33) matched with N=12 NT subset from Study 2.
- **population_category:** clinical
- **population_age_range:** M=23.81
- **ecological_validity:** Limited — hypothetical monetary choices in a lab/online setting with simulated (not real) social agents; explicit trial-by-trial feedback on accuracy is not representative of naturalistic social influence. Participants were told agents were real previous participants (deception). University samples limit generalizability.
- **eligibility_flag:** 
- **concerns:** - Only one computational model tested — no formal model comparison with alternative models (e.g., Rescorla-Wagner, simple heuristic). The "model comparison" is between two outcome measures (DKL vs. shift), not between generative models. - Study 3 sample very small (N=12 ASC), limiting power for detecting group differences despite equivalence testing. - Simulated agents (not real other participants) — social element is somewhat artificial. - DKL is a derived measure from the posterior distributions, not a formal model parameter — contagion is measured post hoc rather than embedded in the generative model.
- **limitations_reported:** It is difficult to link individual differences in questionnaires with task data due to differences in variability"; "Behavioural tasks produce replicable results because between-subject variability is low, which results in low reliability for measuring individual differences"; "The lack of a significant group difference may reflect under sampling of the autistic population (N = 12)"; "Much of the data was collected from a university population" limiting generalizability.
- **limitations_categorized:** reliability of individual differences measures; sample size (ASC group); limited generalizability (university sample); task simplicity
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
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_comparison_metric: LOW — no formal model comparison conducted; BF comparison is between measures, not models - wc_2 (good models): enforced No — single model - wc_7 (compare models): enforced No — single model - preregistered: MEDIUM — not mentioned in paper
- **cannot_find:** Formal model comparison (only one model); data/code availability statement; preregistration status
- **other_notes:** This paper has 3 studies but they all use the same task paradigm (temporal discounting contagion) with different samples (Study 1: NT Oxford; Study 2: NT Royal Holloway; Study 3: ASC Royal Holloway). The studies are presented as a single unified analysis pipeline. For the review, this could be treated as one paper with three sub-studies, but the core computational model and task are identical across all three — only the sample differs. The paper is co-authored by Patricia Lockwood (one of the authors of this review). The Bayesian belief updating here is used to estimate discount rates trial-by-trial rather than as a learning model per se — contagion is measured as a shift in the posterior distribution, not as a prediction-error-driven update within the model itself.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_autism
- pop_healthy_adults
- rr_pop_autism
- rr_pop_healthy_adults
- rr_tax_mod_mentalizing_inference
- rr_tax_mod_social_info_search
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_mod_mentalizing_inference
- tax_mod_social_info_search
- tax_model_bayesian
- tax_param_social_bonus
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = norm_conformity
- tax_rr_topic_norm_conformity
- tax_rr_topic_social_info_use
- tax_topic_norm_conformity
- tax_topic_social_info_use
