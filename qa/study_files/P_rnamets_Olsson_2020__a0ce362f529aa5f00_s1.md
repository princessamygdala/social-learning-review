# Pärnamets & Olsson (2020)

- **study_id:** `a0ce362f529aa5f00_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Pärnamets, P., & Olsson, A. (2020). Integration of social cues and individual experiences during instrumental avoidance learning. *PLoS Computational Biology*, 16(9), e1008163. https://doi.org/10.1371/journal.pcbi.1008163
- **citation_short:** Pärnamets & Olsson (2020)
- **doi:** 10.1371/journal.pcbi.1008163
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Psychology
- **affiliations_raw:** mitsunrestricteduse,distribution,and Finally,wefoundnorelationbetweenautismquestionnairescoresandperformanceinour; University,UNITED modelthatindependentlylearnedtheprobabilitiesofoptionsbeingsafeandofpartners; DivisionofPsychology,DepartmentofClinicalNeuroscience,KarolinskaInstitutet,Stockholm,Sweden,; DepartmentofPsychology,NewYorkUniversity,NewYork,NewYork,UnitedStatesofAmerica; ethis,weusedaninstrumentalaversivelearningtaskwhereparticipants,; etheircuingstrategyorbecomeuntrustworthy; labilityStatement:Allcodeanddataare; lablefromOSFrepository:https://osf; emails: philip.parnamets@ki.se
- **code_url:** https://osf.io/8vwjy/

## Computational level
- **study_focus:** Social cue integration during instrumental avoidance learning; learning from gaze cues and emotional expressions of social partners to avoid aversive outcomes
- **study_focus_short:** Social cue integration during instrumental avoidance learning
- **learning_mode_description:** - Learning mode: Learning from social partners' gaze cues and own shock outcomes to avoid harmful options   - Learning from:     - Source type (social): other (social partner)       - Source content (social): action/policy (gaze cue direction + emotional expression)     - Source type (non-social): self       - Source content (non-social): outcome (shock/no-shock feedback)   - Learning about:     - Target type (non-social): world (choice option safety probabilities)       - Target content (non-social): state (probability of shock for each option)     - Target type (social): other (social partner reliability)       - Target content (social): state (mental state; trustworthiness/reliability of partner's advice)
- **task_description:** Participants made repeated forced choices between two fractal images differing in shock probability (P=.8 vs P=.2), while observing gaze cues from one of four social partners (2 predictive, 2 random; each with fearful or neutral expressions) presented across 12 blocks of 12 trials, with partners re-encountered across novel choice contexts.
- **task_paradigm:** Gaze-cueing task
- **players:** Single agent (participant), multi-target (4 social partners: 2 predictive, 2 random; each encountered 3 times across novel option contexts)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Greyscale fractal images (choice options), KDEF face images (4 female faces with neutral/fearful expressions and gaze cues), mild electric shocks
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Participants made more safe choices with predictive vs random partners (b = 0.67, SE = 0.10, 95% CrI = [0.48, 0.85]) - Interaction between partner reliability and emotional expression on safe choices (b = 0.51, SE = 0.14, 95% CrI = [0.23, 0.78]) - Participants transferred cached partner reliability to novel choice contexts (above-chance first-trial performance in blocks 2 and 3 with predictive partners) - Weak transfer model (Model 9) outperformed strong transfer model, suggesting participants cache partner reliability but do not let it influence initial option estimates - Response times faster for predictive partners (b_μ = -0.26, SE = 0.029, 95% CrI = [-0.32, -0.21]) - Small positive correlation between AQ scores and option-partner learning rate difference (r = 0.19, SE = 0.11, 95% CrI = [-0.04, 0.39]) - Partner reliability (b = 0.68, SE = 0.27, 95% CrI = [0.15, 1.21]) and number of shocks (b = -0.18, SE = 0.065, 95% CrI = [-0.31, -0.051]) predicted partner helpfulness rankings
- **effect_size:** b = 0.67 (reliability effect on safe choices); b = 0.51 (reliability × emotion interaction); r = 0.19 (AQ × learning rate difference); b = 0.68 (partner reliability on rankings)
- **learning_from:** Other (social partner gaze cues + emotional expressions) and self (shock outcomes). Source: other + self.
- **learning_about:** World (option safety probabilities) and other (partner reliability/trustworthiness). Target: world + other.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** RW with weak transfer, emotion bonus (Model 9): 4 LRs (α+,opt, α−,opt, α+,partner, α−,partner), ω (option-partner weighting), θ (fearful expression bonus), β (inverse temperature). 7 free parameters.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Model 1: Option only", "family": "RW", "n_params": 3, "metric": "LOO-CV ELPD = -4634"},   {"name": "Model 2: Gaze only", "family": "RW", "n_params": 3, "metric": "LOO-CV ELPD = -6219"},   {"name": "Model 3: Equal weighting, weak transfer", "family": "RW", "n_params": 5, "metric": "LOO-CV ELPD = -4239"},   {"name": "Model 4: Equal weighting, strong transfer", "family": "RW", "n_params": 5, "metric": "LOO-CV ELPD = -4340"},   {"name": "Model 5: Variable weighting, weak transfer", "family": "RW", "n_params": 6, "metric": "LOO-CV ELPD = -4172"},   {"name": "Model 6: Variable weighting, strong transfer", "family": "RW", "n_params": 6, "metric": "LOO-CV ELPD = -4318"},   {"name": "Model 7: Emotion weighting, weak transfer", "family": "RW", "n_params": 7, "metric": "LOO-CV ELPD = -4164"},   {"name": "Model 8: Emotion weighting, strong transfer", "family": "RW", "n_params": 7, "metric": "LOO-CV ELPD = -4329"},   {"name": "Model 9: Emotion bonus, weak transfer (WINNING)", "family": "RW", "n_params": 7, "metric": "LOO-CV ELPD = -4145"},   {"name": "Model 10: Emotion bonus, strong transfer", "family": "RW", "n_params": 7, "metric": "LOO-CV ELPD = -4277"},   {"name": "Model 11: Arbitration, weak transfer", "family": "RW + arbitration", "n_params": 6, "metric": "LOO-CV ELPD = -4188"},   {"name": "Model 12: Arbitration, strong transfer", "family": "RW + arbitration", "n_params": 6, "metric": "LOO-CV ELPD = -4306"},   {"name": "Model 13: Arbitration + emotion bonus, weak transfer", "family": "RW + arbitration", "n_params": 7, "metric": "LOO-CV ELPD = -4155"},   {"name": "Model 14: Arbitration + emotion bonus, strong transfer", "family": "RW + arbitration", "n_params": 7, "metric": "LOO-CV ELPD = -4266"},   {"name": "HGF (Hierarchical Gaussian Filter)", "family": "HGF", "n_params": "not specified", "metric": "AIC weights: Model 9 preferred for 80/81 participants, median AICw = 1.0"} ]  Additional model variants tested in supplement: models 1-6 with fewer learning rate
- **model_mb_mf:** MF
- **model_params:** - β (inverse temperature/gain): Mean = 0.25, 95% CrI = [0.23, 0.28] - ω (option-partner weighting): Mean = 0.68, 95% CrI = [0.62, 0.73] - α+,opt (positive option learning rate): Mean = 0.53, 95% CrI = [0.43, 0.63] - α−,opt (negative option learning rate): Mean = 0.19, 95% CrI = [0.13, 0.27] - α+,partner [S] (positive partner learning rate): Mean = 0.45, 95% CrI = [0.35, 0.56] - α−,partner [S] (negative partner learning rate): Mean = 0.33, 95% CrI = [0.26, 0.41] - θ [S] (emotion bonus for fearful expression): Mean = 0.069, 95% CrI = [0.039, 0.11]
- **social_param:** - α+,partner / α−,partner: Learning rates for updating partner reliability estimates (positive and negative PE respectively) - θ: Fixed bonus to advised option value when partner displays fearful expression - ω: Weighting between option-derived and partner-derived information (higher = more weight on own experience)
- **social_param_name:** α+,partner
- **social_param_value:** 0.45
- **social_param_sd:** 
- **social_param_range:** 0.35–0.56
- **model_comparison_metric:** LOO-CV (leave-one-out cross-validation) to estimate expected log predictive density (ELPD). Also AIC weights for HGF comparison.
- **how_model_fit:** individual-level-fit (hierarchical Bayesian; parameters fit hierarchically to each participant as deviations from population average using MCMC/NUTS in Stan)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study only)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 81 (40 naïve condition, 41 instructed condition); student population and local community at Karolinska Institutet
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Task uses gaze cues and emotional expressions as social information, which are naturalistic signals; however, partners are static images (KDEF database faces), not live agents; binary forced-choice with electric shock is a controlled lab paradigm; authors discuss ecological validity of transfer strategy via simulation of variable social environments
- **eligibility_flag:** 
- **concerns:** Model 9 and Model 13 are within 1 SE of each other in ELPD comparison and are strongly confused in model recovery simulations, raising uncertainty about which mechanism truly underlies behavior; emotion bonus parameter θ is small (mean = 0.069) and close to zero; AQ-related findings are exploratory with credible intervals overlapping zero; social partners are static images not real agents
- **limitations_reported:** Relative anonymity of partners limits ecological validity; could be improved by giving participants more information about partners (group belonging, status, trustworthiness); task could be ported to virtual reality for increased realism; social partners were either fully predictive or fully random — future work should explore varying levels of partner reliability; close comparison between Models 9 and 13 not fully settled; further experimentation needed targeting neural correlates; AQ findings exploratory and should be replicated; important to compare reward and punishment feedback within-subjects
- **limitations_categorized:** limited ecological validity; task simplicity (binary reliability); no neuroimaging; model identifiability (Models 9 vs 13 confused); limited social interaction (static images); exploratory individual difference findings; no within-subject feedback valence comparison
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - wc_5 (parameter recovery): MEDIUM confidence — model recovery was done but parameter recovery specifically not reported - concerns about model identifiability between Models 9 and 13: HIGH confidence (directly stated by authors) - AQ findings: authors themselves note these are exploratory
- **cannot_find:** Nothing missing — all fields extractable from paper and supplement. No neuroimaging data (behavioural study).
- **other_notes:** Paper provides extensive simulation analyses of ecological validity of weak vs strong transfer strategies. Open data and code on OSF. The HGF model (previously used in similar paradigms by Sevgi et al., 2020) was also tested and strongly disfavored. All model comparisons done hierarchically in Stan. The supplement contains thorough model comparison tables including entropy-based arbitration variants and learning rate variants.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_social_info_search
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_domain_F_affective_moral
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_social_info_search
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = threat_fear
- tax_rr_topic_social_info_use
- tax_rr_topic_threat_fear
- tax_topic_social_info_use
- tax_topic_threat_fear
