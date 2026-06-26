# Frolichs et al. (2022)

- **study_id:** `abfd52709b54c4481_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Frolichs, K. M. M., Rosenblau, G., & Korn, C. W. (2022). Incorporating social knowledge structures into computational models. Nature Communications, 13, 6205. https://doi.org/10.1038/s41467-022-33418-2
- **citation_short:** Frolichs et al. (2022)
- **doi:** 10.1038/s41467-022-33418-2
- **publication_type:** thesis
- **year:** 2022
- **field_of_study:** Psychology
- **affiliations_raw:** InstituteforSystemsNeuroscience,UniversityMedicalCenterHamburg-Eppendorf,Hamburg,Germany; DepartmentofPsychologicalandBrainSciences,GeorgeWashingtonUniversity,; ethey experimentsandcomputationalmodels,wetestedhowwellboth; UniversityofHeidelberg,Heidelberg,Germany; ethatparticipantsefficientlycombinethe; SectionSocialNeuroscience,Departmentof; ethePEisthedifferencebetweenapre-; ethatvariantsofRWalgorithms,which; emails: Christoph.Korn@med.uni-heidelberg.de, Koen.Frolichs@med.uni-heidelberg.de
- **code_url:** https://github.com/dnhi-lab/PerLe

## Computational level
- **study_focus:** Trait inference / personality learning -- how humans learn about others' Big-5 personality traits using different knowledge structures (granularity levels and reference points).
- **study_focus_short:** Trait inference / personality learning -- how humans learn about others' Big-5
- **learning_mode_description:** - Learning mode: Learning from feedback about others' personality trait self-ratings to update beliefs about their personality   - Learning from:     - Source type (social): other (stranger profiles)     - Source content (social): outcome (trait self-rating feedback)   - Learning about:     - Target type (social): other (strangers)     - Target content (social): state (personality traits)
- **task_description:** Participants estimated how strangers had rated themselves on personality trait words (Likert 1-8), received immediate feedback (actual self-rating), and repeated this for 50-60 traits per profile across 4-5 profiles. Five experiments varied profile type (real vs. constructed), number of Big-5 factors (2 vs. 5), population (students vs. fashion models), and stimulus type (trait words vs. IPIP sentences).
- **task_paradigm:** Impression formation task
- **players:** Single agent (participant), multi-target (4-5 stranger profiles per experiment)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** German personality trait adjectives or IPIP sentences, numerical feedback (1-8 Likert scale)
- **method:** online / behavioural
- **method_full:** behavioural (online/lab, 5 experiments)
- **main_result:** - Experiment 1 (n=35): Model 5 (Fine Granularity & Population RP) was best fitting model. PE decreased over time (r(58) = -0.523, p < .001). GLM regressor for fine granularity significant (t(34) = -1.71, p = .048). - Experiment 2 (n=41, constructed profiles): Model 3 (Coarse Granularity & Population RP) was best fitting. Participants switched to coarser granularity when trait similarity information was absent. PE decrease over time (r(58) = -0.564, p < .001). - Experiment 3 (n=59): Model 5 (Fine Granularity & Population RP) best fitting with real profiles on 2 factors. PE decrease (r(58) = -0.42, p < .001). - Experiment 4 (n=29): Model 5-STE (Fine Granularity & Stereotypic RP) best fitting for fashion model profiles. Participants used stereotype-based reference points. Significant difference between student and fashion model RPs (t(59) = -9.71, p < .001). - Experiment 5 (n=28): Model 4 (Fine Granularity, no RP) best fitting on IPIP sentence items. PE decrease (r(48) = -0.311, p < .001). - Confusion matrices: all models >92.5% recovery across all experiments. - Parameter recovery: learning rate r >= .74; weighting parameter r >= .89; starting value r >= .51.
- **effect_size:** LOW -- only correlation coefficients and t-statistics reported; no standardized effect sizes for model comparison
- **learning_from:** Other's personality trait self-ratings (feedback); Source: other (stranger profiles)
- **learning_about:** Others' personality traits; Target: other (strangers)  ---  ### Algorithmic Level
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Varies by experiment: - Exp 1: RW Fine Granularity + Population RP (Model 5): P(t+1,All) = gamma * RP + (1-gamma) * (P(t,All) + alpha * PE * SIM); 3 params: alpha, gamma, starting value - Exp 2: RW Coarse Granularity + Population RP (Model 3): P(t+1,F) = gamma * RP + (1-gamma) * (P(t,F) + alpha * PE); 3 params - Exp 3: Model 5 (same as Exp 1) - Exp 4: Model 5-STE (Fine Granularity + Stereotypic RP): same formula as Model 5 but with stereotypic RP - Exp 5: RW Fine Granularity (Model 4): P(t+1,All) = P(t,All) + alpha * PE * SIM; 2 params: alpha, starting value
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. Model 1 - No Learning (linear regression on RP): P = RP * b1 + b0; 2 params; BIC 2. Model 2 - Coarse Granularity (RW by Big-5 factor): P(t+1,F) = P(t,F) + alpha * PE; 2 params (alpha, starting value); BIC 3. Model 3 - Coarse Granularity + Population RP: P(t+1,F) = gamma * RP + (1-gamma) * (P(t,F) + alpha * PE); 3 params (alpha, gamma, starting value); BIC 4. Model 4 - Fine Granularity (RW with similarity matrix): P(t+1,All) = P(t,All) + alpha * PE * SIM; 2 params (alpha, starting value); BIC 5. Model 5 - Fine Granularity + Population RP: P(t+1,All) = gamma * RP + (1-gamma) * (P(t,All) + alpha * PE * SIM); 3 params (alpha, gamma, starting value); BIC 6. Model 1-STE (Exp 4 only): No Learning with stereotypic RP; 2 params; BIC 7. Model 3-STE (Exp 4 only): Coarse + Stereotypic RP; 3 params; BIC 8. Model 5-STE (Exp 4 only): Fine + Stereotypic RP; 3 params; BIC 9. Model 1-SELF: No Learning with self-ratings as RP; 2 params; BIC 10. Model 3-SELF: Coarse + Self RP; 3 params; BIC 11. Model 5-SELF: Fine + Self RP; 3 params; BIC 12. Models 2-5 with split positive/negative learning rates (alpha+, alpha-); +1 param each; BIC
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate) [0-1] -- controls speed of updating - gamma (weighting parameter) [0-1] [S] -- weights reference point vs. trial-by-trial learning; higher gamma = more reliance on prior social knowledge (reference point) - starting value [1-8] -- initial estimate for each factor/trait - SIM (similarity matrix) [S] -- fixed correlation structure between personality trait items, derived from independent sample; scales PE generalization across traits - RP (reference point) [S] -- fixed population average personality trait ratings; represents prior social knowledge/stereotypes
- **social_param:** - gamma [S]: Weighting between prior social knowledge (reference point about population/stereotype) and trial-by-trial learning from feedback - SIM [S]: Personality trait similarity matrix enabling generalization across related traits during social learning - RP / STE [S]: Reference points representing prior social knowledge about a population (students) or stereotypic group (fashion models)
- **social_param_name:** gamma
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (fixed-effects: log-group Bayes factor; random-effects: posterior exceedance probability via SPM12 BMS)
- **how_model_fit:** individual-level-fit (Nelder-Mead simplex algorithm minimizing SSE per participant)
- **data_type_fit_to:** choice behavior (trait rating predictions)  ---  ### Implementation Level

## Implementation level
- **fmri_model_type:** none (Study 1 is behavioural only)
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### Quality
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Study 1 total across 5 experiments: N=193 (Exp 1: n=35; Exp 2: n=42 tested, 41 final; Exp 3: n=59; Exp 4: n=30 tested, 29 final; Exp 5: n=30 tested, 28 final). Experiments 4 and 5 tested on same sample. All ages 18-40.
- **population_category:** healthy adults
- **population_age_range:** 18–40
- **ecological_validity:** Lab-based task with numerical feedback on personality traits is relatively abstract. Participants learned about strangers from numerical self-ratings on Likert scales rather than from naturalistic social interactions. However, real personality profiles were used in most experiments. Authors acknowledge limited ecological validity: trait ratings used integer numbers rather than verbal feedback, and learning lacked action-based social interaction.
- **eligibility_flag:** 
- **concerns:** - Study 1 data are published as Frolichs et al. (2022, Nat Comms) -- duplicate risk - No correction for multiple comparisons in GLM analyses across regressors - GLM regressors are highly correlated (rho between 0.76 and 0.92), limiting interpretability - Effect sizes beyond correlation coefficients not reported for model comparison - Exp 4: best-performing model (No Learning) diverged from best-fitting model (Fine Granularity + Stereotypic RP), suggesting overfitting or suboptimal strategy use
- **limitations_reported:** Total trait items per profile was low (50-60); numerical feedback on integer scale rather than verbal feedback as in real life; learning about others based on passive feedback rather than active social interaction; only two extremes of granularity tested (coarse/fine) rather than intermediate levels; limited stimuli in Exp 5 (only 50 items, 10 per factor); high correlations between GLM regressors complicate interpretation.
- **limitations_categorized:** task simplicity; limited ecological validity; limited stimulus set; correlated regressors; no intermediate granularity levels tested
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
- **ctx_copresence:** unclear
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target+context
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = trait_impression
- tax_rr_topic_trait_impression
- tax_topic_trait_impression
