# Rosenblau et al. (2021)

- **study_id:** `a8cdfbc3ac27cf4e3_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Rosenblau, G., Korn, C. W., Dutton, A., Lee, D., & Pelphrey, K. A. (2021). Neurocognitive mechanisms of social inferences in typical and autistic adolescents. *Biological Psychiatry: Cognitive Neuroscience and Neuroimaging*, *6*(8), 782–791. https://doi.org/10.1016/j.bpsc.2020.07.002
- **citation_short:** Rosenblau et al. (2021)
- **doi:** 10.1016/j.bpsc.2020.07.002
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ether participants in the magnetic resonance study relied on preference structures during learning; ETHODS:Typicallydevelopingadolescents(n=26)andadolescentswithautismspectrumdisorder(ASD)(n=20); ethersocial provideamodelforsocialinferencesofadolescentswithASD; ethan mains unclear whether adolescents represent social knowl-; ether with neuroimaging may; ETHODSANDMATERIALS; ether this
- **code_url:** 

## Computational level
- **study_focus:** Learning others' preferences; social inference learning; preference similarity-based social learning in typical vs. autistic adolescents
- **study_focus_short:** Learning others' preferences · social inference learning
- **learning_mode_description:** - Learning mode: Learning from trial-by-trial feedback about a peer's actual preferences to infer that peer's preferences for upcoming items, using preference similarity structures and population averages.   - Learning from:     - Source type (social): other (peer)     - Source content (social): outcome (peer's actual preference rating as feedback)   - Learning about:     - Target type (social): other (peer)     - Target content (social): state (mental state; preferences)
- **task_description:** Adolescents in the fMRI scanner rated how much 3 peers from their age group liked various items (activities, fashion, food) on a 10-point scale, receiving trial-by-trial feedback about the peer's actual preference rating after each prediction. In a separate online survey, 99 adolescents rated their own preferences for the same items, establishing population preference structures.
- **task_paradigm:** Impression formation task
- **players:** Single agent (participant), multi-target (3 peers; sequential profiles). Two groups: TD adolescents (n=26) and adolescents with ASD (n=20).
- **n_players:** network (5+)
- **partner_type:** unclear
- **stimuli:** Pictures of everyday items (activities, fashion, food; 120 items total), numeric preference ratings (1–10 Likert scale), trial-by-trial numeric feedback
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - TD adolescents best described by Similarity Combination model (BIC and AIC weight = 1); ASD group best described by No-Learning model (BIC) or Combination model (AIC) - TD adolescents made more generalized descriptions of peers post-task: more predefined categories (χ² = 22.6, p < .001) and personality traits (χ² = 3.52, p = .004) mentioned - No group difference in average unsigned PE magnitude (median TD = 2.49, median ASD = 2.49; χ² = 0.07, p = .790) - In ASD group, IQ predicted PE magnitude (ρ = −0.571, p = .02); no such relationship in TD (Fisher's r-to-z = 2.82, p = .002) - Nonlinear age–PE relationship in TD group (age²: β = −0.003, r² = .257, p = .004) - Similarity Comb model evidence correlated with social skills across groups (r = .43, p_FDR = .048) and in ASD only (r = .62, p_FDR = .034) - Model-derived PEs (Similarity Comb) encoded in right caudate/putamen in TD (peak z = 3.84) - Own preferences encoded more strongly in angular gyrus/precuneus in ASD > TD (peak z = 3.53) - Model-free PEs correlated with MPFC activity in TD only (peak z = 3.5)
- **effect_size:** - IQ–PE correlation in ASD: ρ = −0.571 - Fisher's r-to-z (IQ–PE group difference) = 2.82 - Age² effect on PE in TD: r² = .257 - Similarity Comb BIC–SRS correlation across groups: r = .43 - Similarity Comb BIC–SRS correlation in ASD: r = .62 - Posterior predictive check split-half parameter correlations (TD): r(α) = 0.51, r(γ) = 0.80 - Posterior predictive check split-half parameter correlations (ASD): r(slope) = 0.48, r(intercept) = 0.45
- **learning_from:** Other (peer); trial-by-trial feedback about peer's actual preference rating for items
- **learning_about:** Other (peer); peer's preferences for everyday items (activities, fashion, food)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** - TD group: Similarity Combination model (2 free params: α [learning rate], γ [trade-off between RL + similarity and population mean preferences]); ER_{t+1} = γ[ER_t + α·PE_t·r(i,I)] + (1−γ)·MP_{t+1} - ASD group (BIC): No-Learning model (2 free params: β₀ [intercept], β₁ [slope]); ER = β₀ + β₁·OP
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "No-Learning", "family": "Linear regression", "n_params": 2, "metric": "BIC/AIC"},   {"name": "RL-Ratings", "family": "Rescorla-Wagner", "n_params": 1, "metric": "BIC/AIC"},   {"name": "Combination (Comb)", "family": "RW + own preferences", "n_params": 2, "metric": "BIC/AIC"},   {"name": "Simple Prior", "family": "Linear regression", "n_params": 2, "metric": "BIC/AIC"},   {"name": "Combination Simple Prior", "family": "RW + population mean", "n_params": 2, "metric": "BIC/AIC"},   {"name": "Similarity RL", "family": "Similarity-weighted RW", "n_params": 1, "metric": "BIC/AIC"},   {"name": "Similarity Combination", "family": "Similarity-weighted RW + population mean", "n_params": 2, "metric": "BIC/AIC"},   {"name": "RL ratings decay", "family": "RW with decay", "n_params": 2, "metric": "BIC/AIC"},   {"name": "Comb decay", "family": "RW + own preferences with decay", "n_params": 3, "metric": "BIC/AIC"},   {"name": "Simple Prior decay", "family": "RW + population mean with decay", "n_params": 3, "metric": "BIC/AIC"} ]
- **model_mb_mf:** MB (the Similarity Combination model uses a structured similarity matrix from population preferences — model-based); MF for RL-Ratings; N/A for No-Learning (not RL)
- **model_params:** - Similarity Combination model (TD winning):   - α (learning rate): scales PE updating (range 0–1); mean fitted value not explicitly reported in text but distribution shown in Figure 3B   - γ (trade-off parameter): weight between similarity-scaled RL component and population mean preferences (range 0–1) [S — trade-off between social knowledge sources]   - r(i, I): preference similarity — correlation between population preferences for current item i and all subsequent items I (fixed, derived from survey; not a free parameter) [S]   - MP (mean population preference): average preference rating from 99-adolescent survey (fixed) [S] - No-Learning model (ASD winning by BIC):   - β₀ (intercept): intercept of linear transformation from own to other's preferences   - β₁ (slope): slope of linear transformation from own to other's preferences
- **social_param:** - γ (trade-off parameter) [S]: controls reliance on similarity-weighted PE learning vs. average population preferences — quantifies how much participant uses social knowledge (peer population structure) vs. individual feedback-based learning - r(i, I) (preference similarity) [S]: correlation structure derived from peer population survey — captures shared social preference structure - MP (mean population preference) [S]: average preference from the adolescent population, representing prior social knowledge
- **social_param_name:** r
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (primary), AIC, AIC weights (relative likelihood)
- **how_model_fit:** individual-level-fit (nonlinear Nelder-Mead simplex search minimizing sum of squared errors per participant)
- **data_type_fit_to:** choice behavior (preference ratings)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — two GLMs: GLM1 (model-free PE as parametric regressor) and GLM2 (model-derived PE and model-predicted ratings as parametric regressors)
- **contrast:** - GLM1: Model-free PE parametric modulation during feedback phase (TD: MPFC; peak z = 3.5) - GLM1: Own preferences parametric modulation during rating phase (ASD > TD: angular gyrus/precuneus) - GLM2: Model-derived PE (Similarity Comb) parametric modulation during feedback phase (TD: caudate/putamen; peak z = 3.84) - GLM2: Own preferences parametric modulation during rating phase (ASD > TD: angular gyrus; peak z = 3.53)
- **key_regions:** Model-based PE (Similarity Comb) in right caudate and putamen (TD); model-free PE in MPFC/frontal pole (TD); own preference encoding in angular gyrus extending into precuneus (ASD > TD)
- **key_regions_abbrev:** caudate, putamen, mPFC, precuneus
- **coordinates_peak:** Model-free PE (TD, GLM1): Frontal Pole: 22, 48, 30 Frontal Pole: 10, 48, 42 Frontal Pole: 26, 34, 24 Medial Prefrontal Cortex: 18, 34, 23 Medial Prefrontal Cortex: 16, 38, 23 Medial Prefrontal Cortex: 10, 54, 14  Own preferences ASD > TD (GLM2): Angular Gyrus (R): 24, −54, 42 Angular Gyrus (R): 42, −46, 56 Angular Gyrus (R): 32, −52, 50 Angular Gyrus (R): 28, −56, 50 Angular Gyrus (R): 46, −46, 56 Angular Gyrus (R): 46, −54, 44  Model-derived PE from Similarity Comb, TD (GLM2): Caudate (R): 22, 10, 14 Caudate (R): 18, 12, 10 Putamen (R): 24, 6, 2 Putamen (R): 22, 0, 10
- **analysis_type:** whole-brain (family-wise cluster corrected at z = 2.3, p < .001)  ---  ## QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 46 fMRI (26 TD [11 female; age 9–18, M = 13.7 ± 2.5] + 20 ASD [12 female; age 10–20, M = 14.8 ± 2.8; 4 excluded from original 24]); N = 99 online survey (55 female; age 11–18, M = 15.7 ± 1.4)
- **population_category:** clinical
- **population_age_range:** 9–18
- **ecological_validity:** Moderate — task uses real preference items (food, fashion, activities) relevant to adolescents and feedback from real peers from the same age group. However, learning is constrained to a structured item-rating paradigm in the scanner with no real-time social interaction. Three distinct peer profiles increase generalizability but participants never interact directly with peers.
- **eligibility_flag:** 
- **concerns:** - The ASD and TD groups yield different winning models (No-Learning vs. Similarity Comb), making direct neural comparison complex — the model-based GLM uses different model-derived regressors for each group - BIC and AIC disagree on the winning model for the ASD group (No-Learning vs. Comb), indicating ambiguity - Sample sizes are modest (n = 20 ASD, n = 26 TD) for an fMRI study with a clinical population - Large age range (9–20 years) spans significant developmental periods; nonlinear age effects are found in TD but this reduces power for group comparisons - Data from 24/26 TD participants were previously published in Rosenblau et al. (2018) — potential overlap/reuse concern (flagged as acknowledged by authors) - No formal exceedance probability or protected exceedance probability reported for model comparison — only group-level BF, AIC weights
- **limitations_reported:** Large age range may have precluded detecting systematic group differences in brain regions that undergo significant development during adolescence, such as the prefrontal cortex; study lacks a representative sample of ASD preference profiles to rule out that adolescents with ASD rely on representations about peers with ASD; could not investigate whether participants represent preference similarities with a multivariate approach (e.g., RSA) because feedback changes the representation of items; study did not assess whether learning strategies generalize to online social interactions; second-person neuroscience approach needed for ecological validity
- **limitations_categorized:** limited age range control; limited generalizability (no ASD-specific preference profiles); task simplicity (no multivariate neural analysis possible due to feedback); limited ecological validity (no real-time social interaction); sample size
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
- **wc_rule10:** Partial
- **wc_score:** 9.5
- **wc_total:** 9.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - winning_model (ASD): MEDIUM confidence — BIC and AIC disagree (No-Learning vs. Comb); authors present both but emphasize No-Learning based on BIC and parameter interpretation - model_mb_mf: MEDIUM confidence — Similarity Comb classified as MB because it uses a structured similarity matrix, but could be considered a hybrid; the similarity structure is fixed/precomputed rather than learned online - mean fitted parameter values: LOW confidence — exact mean fitted values for α and γ not reported numerically in text; distributions shown in Figure 3B only - wc_guidelines rule 10: MEDIUM — no explicit data/code sharing statement found
- **cannot_find:** - Exact mean fitted parameter values (α, γ) for the Similarity Comb model in TD group (only distributions shown in figure) - Exact mean fitted parameter values (β₀, β₁) for the No-Learning model in ASD group (only distributions shown in figure) - Data or code sharing statement
- **other_notes:** - 24/26 TD participants were previously reported in Rosenblau, Korn, & Pelphrey (2018, J Neurosci) — the current study extends the model space with similarity-based models. Flag for potential overlap with that earlier paper if it appears in the corpus. - This paper was posted as a preprint on bioRxiv (doi: 10.1101/850552) prior to journal publication. - The online survey sample (N=99) is used to derive population preference structures (mean preferences and similarity matrices) but is not itself modeled — it provides fixed inputs to the computational models. - All coordinates are in MNI space. Whole-brain FWE cluster correction at z = 2.3, p < .001.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_autism
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_autism
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_clinical
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = mentalizing
- tax_rr_secondary_topic = trait_impression
- tax_rr_topic_mentalizing
- tax_rr_topic_trait_impression
- tax_topic_mentalizing
- tax_topic_trait_impression
