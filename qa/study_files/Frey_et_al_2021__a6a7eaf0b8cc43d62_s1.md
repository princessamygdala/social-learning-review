# Frey et al. (2021)

- **study_id:** `a6a7eaf0b8cc43d62_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Frey, A.-L., Frank, M. J., & McCabe, C. (2021). Social reinforcement learning as a predictor of real-life experiences in individuals with high and low depressive symptomatology. Psychological Medicine, 51, 408-415.
- **citation_short:** Frey et al. (2021)
- **doi:** 10.1017/S0033291719003222
- **publication_type:** peer-reviewed journal
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** mitsnon-commercialre-use, have been related to increased expectancies of negative peerevaluation (Caouette and Guyer,; UniversityPressmustbeobtainedfor Inaddition,depressedsubjectsdemonstratedecreasesinthequalityofinterpersonalinter-; SchoolofPsychologyandClinicalLanguageSciences,UniversityofReading,Reading,UKand2Departmentof; InstituteforBrainScience,BrownUniversity,Providence,; ethisarticle:FreyA-L,FrankMJ,McCabeC; University Press; ethods; emails: c.mccabe@reading.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** social reinforcement learning; depression
- **study_focus_short:** social reinforcement learning; depression
- **learning_mode_description:** Learning from social feedback (like/neutral/dislike from ostensible co-participants) about which stimulus-action pairs yield positive vs negative outcomes
- **task_description:** Participants chose between pairs of party decoration items and received positive (like), neutral, or negative (dislike) social feedback ostensibly from two co-participants, or monetary outcomes (win/nothing/lose 5p) in a non-social condition; items had probabilistic outcome contingencies (75%/25%).
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), multi-target (2 ostensible co-participants providing feedback)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Party decoration images; social feedback (thumbs up/horizontal/down icons); monetary feedback (coin/circle/crossed-out coin)
- **method:** online / behavioural
- **method_full:** behavioural (part online, part in-lab)
- **main_result:** - HD participants showed significantly lower learning rates than LD subjects in social condition (U = 1277, p = 0.040)   - No group differences in non-social learning parameters   - Reduced social learning rates predicted more time in unpleasant social situations (beta = -0.45, p = 0.046), controlling for BDI   - Higher outcome valuation (d) predicted more time in unpleasant social situations (beta = 0.31, p = 0.016)   - Social anhedonia predicted less time in pleasant social situations (beta = -0.49, p < 0.001)   - HD showed heightened negative feedback expectancy biases across conditions (F(1,88) = 5.33, p = 0.023)   - Overall regression predicting unpleasant social time: L(6) = 16.21, p = 0.013, R2 = 0.19   - Regression predicting pleasant social time: L(5) = 18.06, p = 0.003, R2 = 0.22
- **effect_size:** R2 = 0.19 (unpleasant social situations regression); R2 = 0.22 (pleasant social situations regression); R2 = 0.31 (time spent with friends regression); beta = -0.45 (LR -> unpleasant social); beta = 0.31 (d -> unpleasant social); beta = -0.49 (RSAS -> pleasant social)
- **learning_from:** Other (two ostensible co-participants); social approval/disapproval feedback (like/neutral/dislike)
- **learning_about:** World; stimulus-action-outcome contingencies (which items yield positive vs negative feedback)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Q16: Q-learning with 1 alpha, d (outcome valuation), omega (memory decay), tau (temperature)
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Q16 (social winning)", "family": "Q-learning", "n_params": 4, "metric": "AICw"}, {"name": "Q5 (non-social winning)", "family": "Q-learning", "n_params": 4, "metric": "AICw"}, {"name": "Other Q-learning variants (2-7 params)", "family": "Q-learning", "n_params": "2-7", "metric": "AICw"}]   - Note: Full model list (with formulas) is in online Supplementary Table S1, which is not accessible.
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate): single LR (alpha_G = alpha_L); HD social mean significantly lower than LD (U = 1277, p = 0.040) [fitted values not reported in main text]   - d (outcome valuation): impact of rewards/punishments relative to initial expectation   - omega (memory decay): forgetting during rating periods [social condition only]   - tau (temperature): exploration vs exploitation   - w (choice/sticky bias): tendency to repeat choices [non-social condition only]
- **social_param:** alpha [S]: learning rate in the social condition, significantly lower in HD than LD participants; d [S]: outcome valuation parameter in social condition (predicted time in unpleasant social situations)
- **social_param_name:** alpha [S]
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC weights (Akaike Information Criterion weights)
- **how_model_fit:** individual-level-fit (maximum likelihood estimation)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 92 (HD = 40, LD = 52; tested at university: 50, online: 42); ages 18-45; 72 female, 20 male. One LD participant excluded from task analyses.
- **population_category:** clinical
- **population_age_range:** 18–45
- **ecological_validity:** Moderate-high for linking lab to real life; the study uniquely connects task-based social learning parameters to self-reported everyday social experiences. However, social feedback was computer-generated (not truly from co-participants), and the party decoration task is artificial. Real-life measures were retrospective self-report, not experience sampling.
- **eligibility_flag:** FALSE
- **concerns:** Social feedback was deceptive (computer-generated, not from real people); no neuroimaging; supplement not accessible (model details, parameter recovery, simulation results all in supplement); mean fitted parameter values not reported in main text; the non-social condition used a different winning model than the social condition, complicating direct comparison; regression analyses used rank-transformed data due to non-normality; the paper notes that parameter-related findings for pleasant social situations were "not robust" across alternative models.
- **limitations_reported:** Excluding HD individuals based on medication use could have led to a mix of treatment-resistant and newly diagnosed participants; online vs in-lab testing environments may have differed despite controlling for location; cross-sectional design precludes causal inference about whether early social learning impairments predict later social withdrawal; authors note results from similarly well-fitting model for pleasant social situations were "somewhat different" indicating parameter-related findings are not robust and should be interpreted with caution.
- **limitations_categorized:** sample heterogeneity; testing environment variability; cross-sectional design; limited robustness of parameter-level findings; no causal inference
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - all_models_tested (LOW): Full list of models in Supplementary Table S1, not accessible; only winning models named in main text   - model_params (MEDIUM): Fitted mean parameter values not reported in main text; only group comparison statistics given   - wc_rule3 (MEDIUM): Simulation mentioned but details in inaccessible supplement   - wc_rule5 (MEDIUM): Parameter recovery mentioned but details in inaccessible supplement   - wc_rule8 (MEDIUM): Validation mentioned alongside simulation/recovery but unclear if formal posterior predictive check performed
- **cannot_find:** Full model list and formulas (in Supplementary Table S1); mean fitted parameter values; model simulation details; parameter recovery results; exact formulas for all tested models; whether code/data are shared
- **other_notes:** Supplement not accessible -- referenced extensively for model details (Supplementary Table S1), model validation, and additional analyses. The paper finds a specific social learning deficit in depression (not present for non-social learning), and uniquely links task-derived computational parameters to real-life social experience measures. The social and non-social conditions had different winning models (Q16 vs Q5), with the social condition including a memory decay parameter and the non-social including a sticky choice bias parameter.
- **re_extract_flag:** true (supplement not accessible; model details incomplete)

## Taxonomy / categorization (active codes only)
- pop_depression
- pop_healthy_adults
- rr_pop_depression
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = parametric
- spec_locus = target
- spec_source = social
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_decay
- tax_param_learning_rate
- tax_param_social_weight
- tax_param_temperature
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_social_nonsocial_comparison
- tax_topic_social_approval_reward
