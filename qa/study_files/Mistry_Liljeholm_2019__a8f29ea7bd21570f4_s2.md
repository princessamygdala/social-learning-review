# Mistry & Liljeholm (2019)

- **study_id:** `a8f29ea7bd21570f4_s2`
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
- **study_focus:** Social conformity learning; transfer of social valence to concomitant stimuli (conditioned reinforcement)
- **study_focus_short:** Social conformity learning
- **learning_mode_description:** - Learning mode: Learning the value of target gamblers through observation of their conformity/dissent behavior, then transferring that learned value to novel choice contexts   - Learning from:     - Source type (social): other (target gamblers)     - Source content (social): action/policy (conforming vs. dissenting decisions relative to group majority)   - Learning about:     - Target type (social): other (target gamblers)     - Target content (social): state (mental state; likability/value of the target gambler)
- **task_description:** Participants observed named target gamblers making conforming or dissenting decisions relative to a group majority across trials, then chose between novel slot options endorsed by different target gamblers and rated their likability.
- **task_paradigm:** Conformity / Asch-style
- **players:** Single agent (participant), multi-target (6 target gamblers: 3 conforming, 3 dissenting; plus 6 non-specific previous gamblers as group)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Numbered slot machine options on game board, distinctly colored and named target gambler avatars, gray icons for non-specific previous gamblers, hypothetical monetary rewards, likability rating scale (0–10)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Main effect of social decision on likability ratings (ηp² = 0.40)   - Conforming gamblers rated above neutral midpoint (d = 0.92, 95% CI [0.50, 1.37])   - Dissenting gamblers rated below neutral midpoint (d = 0.54, 95% CI [0.15, 0.93])   - Preference for conforming-endorsed options when cumulative reward matched: 69% (d = 0.50, 95% CI [0.12, 0.90])   - Main effect of social decision on gambling choices (ηp² = 0.24)   - Chose lower-gain conformer-endorsed option, small difference (d = 0.91, 95% CI [0.38, 1.44])   - Chose lower-gain conformer-endorsed option, large difference (d = 1.07, 95% CI [0.53, 1.62])   - Social model AICc better than non-social model (d = 1.05, 95% CI [0.67, 1.43])   - Discrimination between conforming/dissenting gamblers (d = 2.76, 95% CI [2.05, 3.46])   - Preference for higher cumulative gain gambler on matched-social trials (d = 0.42, 95% CI [0.04, 0.80])
- **effect_size:** - Main Results:   - Main effect of social decision on likability ratings (ηp² = 0.40)   - Conforming gamblers rated above neutral midpoint (d = 0.92, 95% CI [0.50, 1.37])   - Dissenting gamblers rated below neutral midpoint (d = 0.54, 95% CI [0.15, 0.93])   - Preference for conforming-endorsed options when cumulative reward matched: 69% (d = 0.50, 95% CI [0.12, 0.90])   - Main effect of social decision on gambling choices (ηp² = 0.24)   - Chose lower-gain conformer-endorsed option, small difference (d = 0.91, 95% CI [0.38, 1.44])   - Chose lower-gain conformer-endorsed option, large difference (d = 1.07, 95% CI [0.53, 1.62])   - Social model AICc better than non-social model (d = 1.05, 95% CI [0.67, 1.43])   - Discrimination between conforming/dissenting gamblers (d = 2.76, 95% CI [2.05, 3.46])   - Preference for higher cumulative gain gambler on matched-social trials (d = 0.42, 95% CI [0.04, 0.80])
- **learning_from:** Others (target gamblers); their conforming/dissenting actions relative to group majority
- **learning_about:** Others (target gamblers); their likability/value as conditioned by conformity history  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Social RW learning + EV: ΔV(s) = α[R(s') − V(s)], R(s') = m(s') + w * c(s'), with softmax (3 free params: α, w, τ)
- **model_family:** Utility / EV
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Non-social RW + EV model", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AICc"}, {"name": "Social RW + EV model (conformity as surrogate reward)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AICc"}]
- **model_mb_mf:** MF
- **model_params:** - α: learning rate (mean = 0.23 ± 0.35) - w: value of conformity (mean = 0.49 ± 0.44) [S] - τ: softmax temperature (mean = 20.93 ± 28.76)
- **social_param:** w — reflects individual differences in the value of social conformity; scales the contribution of group majority alignment to the reward signal used to update target gambler values via prediction error learning
- **social_param_name:** w
- **social_param_value:** 0.49
- **social_param_sd:** 0.44
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
- **sample_size:** N = 30 (23 females, mean age = 20.26 ± 2.01)
- **population_category:** healthy adults
- **population_age_range:** M=20.26
- **ecological_validity:** Lab-based task with hypothetical monetary rewards and computer-generated social agents; limited ecological validity. However, transfer of social valence to novel stimuli demonstrates a form of conditioned reinforcement that may generalize to real-world social influence. Ostensible peers were fictitious.
- **eligibility_flag:** 
- **concerns:** Monetary rewards hypothetical; target gamblers computer-generated; participants did not directly experience conformity/dissent themselves — they observed it in others, which tests a specific (vicarious) form of conformity valence transfer; the non-social model has only 2 params vs 3 for the social model, which may bias AICc comparison (though AICc penalizes complexity).
- **limitations_reported:** Use of hypothetical rather than real monetary pay-offs limits generalizability; cannot determine whether conformity reflects hedonic valence, informational inference, uncertainty aversion, or cognitive dissonance; likeability ratings and gambling decisions based on behavior of ostensible others rather than participant's own conforming/dissenting decisions — stronger negative affect might emerge if participant's own decisions conflicted with group; purely behavioral study with no neural data
- **limitations_categorized:** limited ecological validity; hypothetical rewards; confound between hedonic and informational accounts; vicarious rather than direct conformity experience; no neural measures
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
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_mod_action_observation
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = utility_EV
- tax_rr_model_utility_EV
- tax_rr_param_learning_rate
- tax_rr_param_social_bonus
- tax_rr_primary_topic = norm_conformity
- tax_rr_topic_norm_conformity
- tax_topic_norm_conformity
