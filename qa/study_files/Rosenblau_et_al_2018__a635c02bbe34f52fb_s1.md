# Rosenblau et al. (2018)

- **study_id:** `a635c02bbe34f52fb_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Rosenblau, G., Korn, C. W., & Pelphrey, K. A. (2018). A computational account of optimizing social predictions reveals that adolescents are conservative learners in social contexts. *The Journal of Neuroscience*, *38*(4), 974–988.
- **citation_short:** Rosenblau et al. (2018)
- **doi:** 10.1523/JNEUROSCI.1044-17.2017
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Center,YaleUniversity,NewHaven,Connecticut06520,and3InstituteforSystemsNeuroscience,UniversityMedicalCenter; ethank Institute,GeorgeWashingtonUniversityandChildren’sNationalHealthSystem,2115GStreetNW,Washington,DC; Institute,GeorgeWashingtonUniversityandChildren’sNationalHealthSystem,Washington,DC20052,; etheirinferencesovertime,wepittedsimplereinforcementlearningmodels; InstituteofMentalHealthGrantR01MH100028; etheirpredictionsofothers’preferences; etheirpredictionsbased; ethesuitabilityof; emails: grosenblau@gwu.edu
- **code_url:** 

## Computational level
- **study_focus:** Preference inference learning / mentalizing learning — How adolescents and adults learn to predict others' preferences from trial-by-trial feedback, and how this develops across adolescence.
- **study_focus_short:** Preference inference learning / mentalizing learning
- **learning_mode_description:** - Learning mode: Learning from feedback about another person's actual preferences to predict that person's future preferences   - Learning from:     - Source type (social): other (peer)     - Source content (social): outcome (other's actual preference rating as feedback)   - Learning about:     - Target type (social): other (peer)     - Target content (social): state (mental state; preferences)
- **task_description:** Participants predicted the preferences of three peers (from their own age group) for activity, fashion, and food items on a 10-point Likert scale, then received trial-by-trial feedback showing the peer's actual rating. After the fMRI task, participants rated their own preferences for the same and additional items.
- **task_paradigm:** Impression formation task
- **players:** Single agent (participant), multi-target (3 peers from own age group)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Pictures of activity, fashion, and food items; 10-point Likert scale ratings; short vignettes introducing each peer
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Adolescents had higher mean absolute PEs than adults (t(43) = -4.037, p = 2.19 × 10⁻⁴)- Combination model best described behavior in both groups (fixed-effect log-group BF > 3 over next-best model; random-effect exceedance probability > 0.9 for combination model family)- γ parameter (OP vs RL weighting) did not differ between groups (Mann-Whitney U = 234, N₁ = 21, N₂ = 24, p = 0.682)- Adolescents had lower learning rates α than adults (t(43) = -4.22, p = 2.44 × 10⁻³ Bonferroni corrected)- Quadratic relationship between age and learning rate in adolescents (B = 0.016, SE = 0.006, t = 2.743, F(2,16) = 5.097, p = 0.014, r² = 0.252)- mPFC activity correlated more with estimated ratings in adults vs adolescents (whole-brain cluster, peak z = 3.77 at [2, 46, 16])- Fusiform cortex activity correlated more with PEs in adolescents vs adults (whole-brain cluster, 2369 voxels, peak z = 4.02 at [28, -92, -6])- PE neural encoding scaled with SRS social traits in adolescents: mPFC cluster (peak z = 6.69 at [-2, 40, 30]), lateral occipital/fusiform clusters
- **effect_size:** - Adolescents had higher mean absolute PEs than adults (t(43) = -4.037, p = 2.19 × 10⁻⁴)- Combination model best described behavior in both groups (fixed-effect log-group BF > 3 over next-best model; random-effect exceedance probability > 0.9 for combination model family)- γ parameter (OP vs RL weighting) did not differ between groups (Mann-Whitney U = 234, N₁ = 21, N₂ = 24, p = 0.682)- Adolescents had lower learning rates α than adults (t(43) = -4.22, p = 2.44 × 10⁻³ Bonferroni corrected)- Quadratic relationship between age and learning rate in adolescents (B = 0.016, SE = 0.006, t = 2.743, F(2,16) = 5.097, p = 0.014, r² = 0.252)- mPFC activity correlated more with estimated ratings in adults vs adolescents (whole-brain cluster, peak z = 3.77 at [2, 46, 16])- Fusiform cortex activity correlated more with PEs in adolescents vs adults (whole-brain cluster, 2369 voxels, peak z = 4.02 at [28, -92, -6])- PE neural encoding scaled with SRS social traits in adolescents: mPFC cluster (peak z = 6.69 at [-2, 40, 30]), lateral occipital/fusiform clusters
- **learning_from:** Other (peer); feedback about peer's actual preference rating for items
- **learning_about:** Other (peer); peer's preferences (mental states)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Combination model (Model 3): ER_{t+1} = γ × (ER_t + α × PE_t) + (1 − γ) × OP_{t+1}; 2 free parameters (α, γ)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. Model 1 (No-learning): linear regression of OP → ER; 2 params (b₀, b₁); BIC 2. Model 2 (RL ratings): Rescorla-Wagner; 1 param (α); BIC 3. Model 3 (Combination): RL + OP weighting; 2 params (α, γ); BIC — **WINNER (adults)** 4. Model 4 (RL-self-other-diff): RL on self-other difference; 1 param (α_DIFF); BIC 5. Model 5 (RL ratings α-cat): RL with category-specific α; 3 params; BIC 6. Model 6 (Combination-α-cat): Combination with category-specific α; 4 params; BIC 7. Model 7 (Combination-γ-cat): Combination with category-specific γ; 4 params; BIC 8. Model 8 (Combination-α-γ-cat): Combination with category-specific α and γ; 6 params; BIC 9. Model 9 (Decay RL ratings): RL + decay; 2 params (α, d); BIC 10. Model 10 (Decay combination): Combination + decay; 3 params (α, γ, d); BIC 11. Model 11 (Combination-α-person): Combination with person-specific α; 4 params (α₁, α₂, α₃, γ); BIC 12. Model 12 (Combination-γ-person): Combination with person-specific γ; 4 params (α, γ₁, γ₂, γ₃); BIC — **best fixed-effect in adolescents (but not conclusively better than Model 3 in random-effects)** 13. Model 13 (Combination-α-γ-person): Combination with person-specific α and γ; 6 params; BIC
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): free parameter weighting PE update. Adults mean higher than adolescents (t(43) = -4.22, p = 2.44 × 10⁻³). [S] — social learning rate- γ (weighting parameter): trade-off between RL-based estimate and own preference. No group difference (U = 234, p = 0.682). [S] — social anchoring/egocentric bias parameter
- **social_param:** γ — formalizes the weighted combination of RL-based social feedback and own preference (egocentric anchoring) when predicting others' preferences. α — social learning rate for updating predictions about others based on PE.
- **social_param_name:** α
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (fixed-effects: log-group Bayes Factor summed across participants; random-effects: Bayesian Model Selection via SPM12 spm_BMS, protected exceedance probabilities)
- **how_model_fit:** Individual-level fit (nonlinear Nelder-Mead simplex search via MATLAB fminsearch, minimizing sum of squared errors per participant)
- **data_type_fit_to:** Choice behavior (preference ratings on 10-point Likert scale)---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors: model-estimated ratings and PEs entered as trial-by-trial parametric modulators in GLM)
- **contrast:** - Estimated ratings (combination model) × brain activity during rating phase: Adults > Adolescents — mPFC cluster (peak z = 3.77) - Estimated PEs (combination model) × brain activity during feedback phase: Adolescents > Adults — bilateral fusiform cortex (peak z = 4.02) - PE encoding × SRS social traits in adolescents — mPFC, lateral occipital, fusiform - PE encoding × age² in adolescents — fusiform, precentral, lateral occipital, cerebellum
- **key_regions:** Social prediction (estimated ratings) in mPFC for adults; PE encoding in bilateral fusiform cortex for adolescents; PE–social traits correlation in mPFC and fusiform; PE encoding in caudate, putamen, thalamus for adolescents alone; developmental (age²) modulation of PE in fusiform and precentral cortex.
- **key_regions_abbrev:** caudate, putamen, mPFC, AI, FFA, thalamus
- **coordinates_peak:** *Ratings adults > adolescents:* - mPFC: 2, 46, 16 (L/R) - mPFC: -10, 44, 14 - mPFC: 4, 54, -10 - mPFC: 6, 48, -6 - mPFC: -6, 38, 14 - mPFC: -4, 62, -6  *Ratings — Adults alone:* - mPFC: 2, 48, 12 (L/R) - mPFC: 4, 48, 6 - mPFC: 6, 48, -6 - mPFC: 2, 38, 8 - mPFC: 6, 48, -2 - mPFC: 4, 58, 2  *PE Adolescents > Adults:* - Occipital fusiform gyrus: 28, -92, -6 (R) - Occipital fusiform: 36, -82, -16 - Occipital fusiform: -12, -90, -8 (L) - Occipital fusiform: -18, -86, -10 - Occipital fusiform: -22, -86, -12 - Occipital pole: 18, -92, -8 (R)  *PE — Adolescents alone:* - Caudate: -16, -6, 20 (L) - Caudate: -14, 0, 18 - Putamen: -22, -2, 10 (L) - Thalamus: -14, -18, 18 (L) - Thalamus: 16, -22, 12 (R) - Caudate: 24, 10, 16 (R) - Occipital fusiform cortex: -18, -84, -10 (L) - Inferior temporal gyrus: 58, -44, -14 (R) - Temporal fusiform cortex: 38, -36, -22 (R) - Temporal fusiform gyrus: -44, -42, -14 - Inferior temporal gyrus: -52, -52, -14  *PE × SRS (linear) in adolescents (Table 5):* - Lateral occipital cortex: 40, -76, -14 (R) - Occipital pole: -2, -92, 8 (L) - mPFC: -2, 40, 30 (L/R) - Superior frontal gyrus: 6, 26, 62 - Occipital pole: -20, -98, -10 (L) - Temporal occipital fusiform cortex: -46, -58, -18 (L)  *PE × Age² in adolescents (Table 5):* - Occipital fusiform cortex: -18, -86, -10 (L) - Precentral gyrus: -40, 4, 26 (L) - Lateral occipital cortex: 48, -76, -4 (R) - Cerebellum CrusII: 6, -84, -24 (R)
- **analysis_type:** Whole-brain (FWE corrected at p < 0.001, cluster-defining threshold z = 2.3)---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 45 (21 adults, 12 female, age 28.4 ± 4.0, range 23–36; 24 adolescents after exclusions from original 28, 10 female, age 13.5 ± 2.2, range 10–17). SRS available for N = 21 adolescents.
- **population_category:** mixed
- **population_age_range:** 23–36
- **ecological_validity:** Moderate — participants rated preferences of real peers from their age group using real preference profiles, approximating naturalistic social inference. However, interaction was one-directional (no reciprocal exchange), and the task was constrained to item-level preference ratings on a Likert scale in a scanner environment.
- **eligibility_flag:** 
- **concerns:** - Relatively small sample sizes (N = 21 adults, N = 24 adolescents) for developmental fMRI - Cross-sectional design limits causal inference about developmental trajectories - Model comparison limited to RL variants; no Bayesian belief updating or mentalizing-specific models tested - No parameter recovery or model recovery analyses reported - No simulation prior to fitting reported - Group differences in head motion (controlled as covariate but still a concern) - Recruited from Yale University area — limited demographic diversity - Own preferences collected AFTER scanning task (to avoid priming), but this means the combination model uses post-hoc OP data
- **limitations_reported:** We acknowledge the relatively small sample size of adolescents and adults, who were recruited from the Yale University area"; "We also acknowledge the possibility of untested models to account for social learning about other persons' preferences"; "While the sample sizes and the model selection strategies are typical for most current studies, future studies should replicate and further fine-tune the behavioral and neural models of social learning in larger and more diverse samples." [HIGH — direct quotes from Discussion]
- **limitations_categorized:** Sample size; limited generalizability (recruitment from single university area); limited model space; task simplicity  ---  ### WC GUIDELINES  1. Design a good experiment: **Yes** — task specifically engages social prediction learning with trial-by-trial feedback2. Design good models: **Yes** — 13 models compared representing competing hypotheses (no-learning, pure RL, combination, extensions with category/person-specific params, decay)3. Simulate, simulate, simulate: **Partial** — noise simulations conducted to test robustness of parameter estimates, and simulations using nonsocial RL to test profile difficulty; but no systematic simulation of model behavior before fitting4. Fit the parameters: **Yes** — MLE via Nelder-Mead simplex, minimizing sum of squared errors5. Check parameter recovery: **No** — no formal parameter recovery reported6. Check model recovery: **No** — no confusion matrix or systematic model recovery7. Fit real data and compare models: **Yes** — both fixed-effects (log-group BF) and random-effects (BMS exceedance probabilities)8. Validate the winning model: **Partial** — noise robustness checks and behavioral control analyses performed; no formal posterior predictive check9. Analyze the winning model: **Yes** — parameter estimates analyzed for group differences, age effects, SRS correlations; parameters used as neural regressors10. Report results transparently: **Partial** — stimuli available by contacting author; no mention of public data/code repository
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - wc_3 (simulate): MEDIUM — noise robustness simulations present but no full model simulation prior to fitting - wc_8 (validate): MEDIUM — robustness checks but no formal posterior predictive check - wc_10 (transparency): MEDIUM — no public data/code sharing mentioned
- **cannot_find:** Supplement not found (no supplement file located; no indication in paper that a separate supplement exists). Mean fitted parameter values for α and γ are not reported as group-specific numerical means (only group comparison statistics are given).
- **other_notes:** The combination model is a Rescorla-Wagner variant augmented with an egocentric prior (own preference). This is a developmental study comparing adolescents and adults. The paper finds that adolescents are more conservative learners (lower α) but equally egocentric (same γ) as adults. The quadratic age effect on learning rates suggests mid-adolescence as a unique period. The paper includes 13 models total in an extended comparison, which is thorough for the field. One study only (no multi-study structure).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- rr_pop_adolescents
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
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_topic_mentalizing
