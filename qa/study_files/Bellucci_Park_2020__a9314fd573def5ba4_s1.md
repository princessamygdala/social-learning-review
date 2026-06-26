# Bellucci & Park (2020)

- **study_id:** `a9314fd573def5ba4_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Bellucci, G., & Park, S. Q. (2020). Honesty biases trustworthiness impressions. *Journal of Experimental Psychology: General, 149*(8), 1567--1586. http://dx.doi.org/10.1037/xge0000730
- **citation_short:** Bellucci & Park (2020)
- **doi:** 10.1037/xge0000730
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** University of Lübeck, and Department of Decision Neuroscience and theexperiments; UniversityofLübeckandGermanInstituteofHumanNutrition(DIfE),Nuthetal,Germany; Institute of Human Nutrition (DIfE), Nuthetal, Ger- data analysis; lable (DOI: http:// Theauthorsdeclarenocompetinginterests; ethe vicediscounting,andmore-knowledgeableindividuals(e; DepartmentofPsychologyI, conceivedoftheidea; ethertotakeordiscountpiecesofadvice; Institute for Biological; emails: gbellucc@gmail.com
- **code_url:** 

## Computational level
- **study_focus:** Trust learning / reputation learning -- how honest reputation biases trustworthiness belief updating and impairs social learning about changes in others' trustworthiness.
- **study_focus_short:** Trust learning / reputation learning -- how honest reputation biases
- **learning_mode_description:** - Learning mode: Learning from adviser's honest/dishonest advice about the adviser's trustworthiness (reputation), which guides trust decisions   - Learning from:     - Source type (social): other (adviser)     - Source content (social): action/policy (truthful vs. untruthful advice-giving behavior)   - Learning about:     - Target type (social): other (adviser)     - Target content (social): state (mental state; character trait -- honesty/trustworthiness)
- **task_description:** In the Take Advice Game (TAG), participants (advisees) received advice from computer-programmed advisers about which of two hidden cards had the higher number; advisers varied in honesty (75% vs. 25% truthful), and their honesty reversed across blocks. After the TAG, participants played a one-shot Trust Game with each adviser.
- **task_paradigm:** Trust game
- **players:** Single agent (participant as advisee/investor), multi-target (2 advisers; computer-programmed)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Abstract card numbers (1-9 except 5), Greeble avatars representing advisers, binary feedback (win/lose), monetary outcomes
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Participants took more advice from initially honest than initially dishonest advisers in Block 1 (d = 0.57; BF10 = 14.39) - Significant Adviser x Block interaction on advice-taking behavior (eta_p^2 = 0.12; BF10 = 10.06) - Trust in the initially dishonest adviser increased when honesty reversed (d = 0.52; BF10 = 7.29), but trust in the initially honest adviser did not decrease (d = 0.17; BF10 = 0.28) - Winning model: honesty learning rate (alpha) significantly higher than dishonesty learning rate (gamma) for the initially honest adviser (d = 0.52; BF10 = 7.43) - No significant difference between learning rates for the initially dishonest adviser (d = 0.14; BF10 = 0.25) - Truthful advice from the initially honest adviser valued more than from the initially dishonest adviser (d = 0.49; BF10 = 5.38) - Initially honest adviser received more money in the TG (d = 0.39; BF10 = 1.57)
- **effect_size:** - Adviser x Block interaction: eta_p^2 = 0.12, BF10 = 10.06 - Block 1 honest vs. dishonest advice-taking: d = 0.57, BF10 = 14.39 - Dishonest adviser trust increase Block 1 to 2: d = 0.52, BF10 = 7.29 - Honesty vs. dishonesty learning rate for initially honest adviser: d = 0.52, BF10 = 7.43 - Truthful advice from honest vs. dishonest adviser: d = 0.49, BF10 = 5.38 - TG investment honest vs. dishonest: d = 0.39, BF10 = 1.57
- **learning_from:** Other (adviser); adviser's truthful or untruthful advice (social information about honesty)
- **learning_about:** Other (adviser); adviser's trustworthiness/honesty (reputation)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RW with 2 social learning rates (alpha_honest, gamma_dishonest; 1 beta) -- separate learning rates for truthful and untruthful social information, independent of reward
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "RL with 2 learning rates (honesty/dishonesty), social information only", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC/AIC"}] -- Paper states 12 models were tested (varying nonsocial information, social information, or both), detailed in Supplementary Methods (Table S2). Supplement not accessible.
- **model_mb_mf:** MF
- **model_params:** - alpha (honesty learning rate) [S]: weighting of truthful social information; mean fitted value for initially honest adviser = 0.25; for initially dishonest adviser = 0.08 - gamma (dishonesty learning rate) [S]: weighting of untruthful social information; mean fitted value for initially honest adviser = 0.10; for initially dishonest adviser = 0.13 - beta (inverse temperature): participant-specific softmax parameter; mean not reported
- **social_param:** alpha (honesty learning rate) -- learning rate for integrating truthful advice from adviser; gamma (dishonesty learning rate) -- learning rate for integrating untruthful advice from adviser. The asymmetry between alpha and gamma for honest advisers explains the reputation-induced learning impairment.
- **social_param_name:** alpha
- **social_param_value:** 0.25
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC, AIC (Bayesian model comparison; group-level summed BIC/AIC)
- **how_model_fit:** individual-level-fit (MLE; maximized likelihood of model given participants' advice-taking behavior)
- **data_type_fit_to:** choice behavior (advice-taking decisions: trust/distrust)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Experiment 3: N = 33 (23 females; mean age 22.27 +/- 3.13). [Experiment 1: N = 28 (18F; mean age 21.43 +/- 3.47); Experiment 2: N = 28 (18F; mean age 24.54 +/- 4.0)]
- **population_category:** healthy adults
- **population_age_range:** M=22.27
- **ecological_validity:** Novel TAG paradigm designed to be more ecological than standard advice-taking tasks: adviser has no incentive to give good advice, and advice informativeness is decorrelated from reward. Advisers are computer-programmed (not real humans), which reduces ecological validity. Card-number task is abstract but mirrors real-life scenarios where advisees cannot verify advice quality before deciding.
- **eligibility_flag:** Experiments 1 and 2 do not use computational modeling and would not independently qualify. Experiment 3 meets all inclusion criteria. The "social agent" is an automated/computer-programmed adviser -- flagged. Overall paper is eligible based on Experiment 3.
- **concerns:** - Advisers were computer-programmed, not real social partners (flagged in eligibility) - 12 computational models were tested but details are in the supplement (Table S2), which is not accessible -- only the winning model equation is provided in the main text - No parameter recovery or model recovery reported in the main text - No simulation of the models reported in the main text (may be in supplement) - Softmax inverse temperature (beta) mean fitted value not reported - Full model comparison table (all 12 models) is in Table S2 of the supplement, not accessible
- **limitations_reported:** Authors do not have a dedicated limitations section. From the discussion: the positivity bias may have gone overlooked in previous studies because participants in those tasks are often provided with some information about the task structure; future studies are needed to investigate whether and how this learning impairment for partners with a good reputation can be overcome; the study uses uninformed decision-makers, which may not generalize to informed contexts.
- **limitations_categorized:** limited ecological validity; automated social agents; task simplicity; limited generalizability; no explicit limitations section
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.0
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - all_models_tested: LOW -- only winning model described in main text; 12 models referenced but details in supplement Table S2, which is not accessible - model_params (beta mean): MEDIUM -- beta is a free parameter but mean fitted value not reported - wc_guidelines rules 3, 5, 6: MEDIUM -- these may be addressed in the supplement but cannot verify from main text alone - winning_model formula: HIGH -- equation 3 is explicitly provided
- **cannot_find:** - Full list and specifications of all 12 computational models (in supplement Table S2, not accessible) - Mean fitted value of inverse temperature beta - Whether parameter recovery or model recovery was performed (may be in supplement) - Whether model simulations were conducted prior to fitting (may be in supplement)
- **other_notes:** - Supplement not accessible as a file (referenced at http://dx.doi.org/10.1037/xge0000730.supp). Supplement reportedly contains: computational model details for all 12 models (Table S2), additional regression tables (Table S1), task figures (Figure S1-S3). - The paper contains 3 experiments but only Experiment 3 includes computational modeling. Experiments 1 and 2 provide behavioral evidence that honest reputation generalizes to trust behavior and persists without feedback. - The winning model (Equation 3) updates trust value based on whether the adviser's advice was truthful (It = 1) or untruthful (It = 0), using separate learning rates for each. This is combined with a softmax decision rule (Equation 4). - Data publicly available at OSF: http://dx.doi.org/10.17605/OSF.IO/5KVWC
- **re_extract_flag:** true -- Supplement not accessible; 12 model details, parameter recovery, model recovery, and simulation information may be in supplement. Re-extraction recommended when supplement becomes available.

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = reputation_learning
- tax_rr_secondary_topic = trust
- tax_rr_topic_reputation_learning
- tax_rr_topic_trust
- tax_topic_reputation_learning
- tax_topic_trust
