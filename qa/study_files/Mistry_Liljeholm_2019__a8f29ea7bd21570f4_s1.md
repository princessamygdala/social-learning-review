# Mistry & Liljeholm (2019)

- **study_id:** `a8f29ea7bd21570f4_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Mistry, P., & Liljeholm, M. (2019). The expression and transfer of valence associated with social conformity. *Scientific Reports*, *9*, 2154. https://doi.org/10.1038/s41598-019-38560-4
- **citation_short:** Mistry & Liljeholm (2019)
- **doi:** 10.1038/s41598-019-38560-4
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Psychology
- **affiliations_raw:** Department of cognitive Sciences, University of california, irvine, USA; lable options on each trial, we examined the affective properties of; mity, consistent with the hypothesized value of social alignment; ether conformity also occurs in the face of conspicuous loss; mity, it is problematic to conclude that con-; lable slot options, highlighted on the game; mity has been demonstrated across; mity and dissent; emails: m.liljeholm@uci.edu
- **code_url:** 

## Computational level
- **study_focus:** Social conformity learning; value of majority alignment
- **study_focus_short:** Social conformity learning; value of majority alignment
- **learning_mode_description:** - Learning mode: Learning about the intrinsic value of conforming with a group majority via trade-off against monetary reward   - Learning from:     - Source type (social): group (ostensible previous gamblers)     - Source content (social): action/policy (majority endorsement of a slot option)   - Learning about:     - Target type (non-social): world (gambling option values)     - Target content (non-social): outcome (expected value integrating social conformity as surrogate reward)
- **task_description:** Participants chose between two slot machine options differing in reward probability, while a panel of ostensible previous gamblers indicated majority endorsement of one option; no trial-by-trial monetary feedback was given during the gambling phase.
- **task_paradigm:** Conformity / Asch-style
- **players:** Single agent (participant), multi-target (6 ostensible previous gamblers as group)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Numbered slot machine options on a game board, avatar icons representing previous gamblers, hypothetical monetary rewards ($1 or $0)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Main effect of social decision on proportion of choices favoring lower-EV option (ηp² = 0.20)   - Main effect of pay-off difference on proportion of choices favoring lower-EV option (ηp² = 0.38)   - Participants chose lower-EV option more when endorsed by majority, large pay-off difference (d = 0.53, 95% CI [0.02, 1.05])   - Participants chose lower-EV option more when endorsed by majority, small pay-off difference (d = 0.85, 95% CI [0.33, 1.38])   - Social model AICc better than non-social model (d = 0.60, 95% CI [0.08, 1.12])   - Conformity preference on equal-EV trials: 66% (d = 0.49, 95% CI [0.11, 0.88])
- **effect_size:** - Main Results:   - Main effect of social decision on proportion of choices favoring lower-EV option (ηp² = 0.20)   - Main effect of pay-off difference on proportion of choices favoring lower-EV option (ηp² = 0.38)   - Participants chose lower-EV option more when endorsed by majority, large pay-off difference (d = 0.53, 95% CI [0.02, 1.05])   - Participants chose lower-EV option more when endorsed by majority, small pay-off difference (d = 0.85, 95% CI [0.33, 1.38])   - Social model AICc better than non-social model (d = 0.60, 95% CI [0.08, 1.12])   - Conformity preference on equal-EV trials: 66% (d = 0.49, 95% CI [0.11, 0.88])
- **learning_from:** Group (ostensible previous gamblers); majority endorsement of slot options
- **learning_about:** World; value of gambling options integrating conformity as surrogate reward  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Social expected value model: R(s') = m(s') + w * c(s'), with softmax (2 free params: w, τ)
- **model_family:** Utility / EV
- **model_class:** Utility maximization
- **all_models_tested:** [{"name": "Non-social EV model", "family": "Utility/value function", "n_params": 1, "metric": "AICc"}, {"name": "Social EV model (conformity as surrogate reward)", "family": "Utility/value function", "n_params": 2, "metric": "AICc"}]
- **model_mb_mf:** MB
- **model_params:** - w: value of conformity (mean = 0.39 ± 0.38) [S] - τ: softmax temperature (mean = 7.33 ± 13.10)
- **social_param:** w — reflects individual differences in the value of conforming with the group majority; scales the influence of group majority size on the reward function
- **social_param_name:** w
- **social_param_value:** 0.39
- **social_param_sd:** 0.38
- **social_param_range:** 
- **model_comparison_metric:** AICc (corrected Akaike information criterion)
- **how_model_fit:** individual-level-fit (minimizing negative log-likelihood per individual using MATLAB fminsearchbnd)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 30 (19 females, mean age = 20.70 ± 2.56)
- **population_category:** healthy adults
- **population_age_range:** M=20.70
- **ecological_validity:** Lab-based gambling task with hypothetical monetary rewards and computer-generated "previous gambler" decisions; limited ecological validity as conformity measured via abstract slot machine choices rather than real social interaction. Ostensible peers were fictitious.
- **eligibility_flag:** Experiment 1 does not involve learning over time — participants' knowledge of reward probabilities was trained to criterion before the gambling phase and no updating occurred during the gambling phase. The conformity parameter w is a static preference, not a learned value. FLAG: borderline learning-vs-decision-making; may be better characterized as value-based decision-making with social influence rather than social learning over time.
- **concerns:** Monetary rewards were hypothetical; ostensible previous gamblers were computer-generated (deception); no trial-by-trial feedback during gambling phase means no learning occurred during the critical phase — this is a decision-making task with pre-trained knowledge, not a learning task per se. The model has no learning rate — it is a static expected value computation.
- **limitations_reported:** Use of hypothetical rather than real monetary pay-offs limits generalizability to real-world economic decisions; cannot determine whether conformity reflects hedonic valence, informational inference, uncertainty aversion, or cognitive dissonance; majority size varied only from 5 to 6, insufficient to assess linearity of majority-size influence; purely behavioral — no neural data to confirm reward-based interpretation
- **limitations_categorized:** limited ecological validity; hypothetical rewards; confound between hedonic and informational accounts; limited parameter space for majority size; no neural measures
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
- **wc_rule10:** Yes
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - Experiment 1 eligibility: MEDIUM confidence — the task is arguably static decision-making rather than learning over time (no learning rate parameter, no trial-by-trial updating) - model_family for Exp 1: MEDIUM — labeled "utility/value function" but the paper calls it "expected value model"; there is no standard RL family since no learning occurs - learning_mode source/target social classification: MEDIUM — conformity source is social (group) but what is learned about (option value) could be classified as non-social
- **cannot_find:** - No exact model formulae beyond Equations 1-3 in the main text (which were extracted) - No parameter recovery or model recovery analyses reported - No preregistration statement found - No neural data or coordinates (behavioral study)
- **other_notes:** The paper includes two additional exploratory/pilot studies (mentioned in text and Supplementary Figure 1) that are not fully reported — these are not extracted as separate studies. A related courtroom study (Mistry & Liljeholm, 2018, CogSci proceedings) is cited but is a separate publication. The supplement contains only a supplementary figure with behavioral results from the exploratory studies — no additional model details or coordinates.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MB
- tax_model_utility
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = utility_EV
- tax_rr_model_utility_EV
- tax_rr_param_social_bonus
- tax_rr_param_temperature
- tax_rr_primary_topic = norm_conformity
- tax_rr_topic_norm_conformity
- tax_topic_norm_conformity
