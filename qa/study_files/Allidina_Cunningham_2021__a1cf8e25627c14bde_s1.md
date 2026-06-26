# Allidina & Cunningham (2021)

- **study_id:** `a1cf8e25627c14bde_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Allidina, S., & Cunningham, W. A. (2021). Avoidance begets avoidance: A computational account of negative stereotype persistence. *Journal of Experimental Psychology: General*, *150*(10), 2078–2099. https://doi.org/10.1037/xge0001037
- **citation_short:** Allidina & Cunningham (2021)
- **doi:** 10.1037/xge0001037
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Psychology
- **affiliations_raw:** mitedtothespecificinteractionpartner,however,butare objects provides a vital starting point for understanding attitudes; ethatavoidancedirectlyreinforcesitself,suchthatinitialavoidanceofgroupmembers; labforhelpfulcommentsonearlierversionsofthisarticle; DepartmentofPsychology,UniversityofToronto,St; etheprobabilityofavoidingthatper-; Department of Psychology, Uni-; ethgirypocsitnemucodsihT; lablewithwhichto; emails: suraiya.allidina@mail.utoronto.ca, cunningham@psych.utoronto.ca
- **code_url:** 

## Computational level
- **study_focus:** Stereotype persistence through avoidance learning; how approach/avoidance behaviors in social group learning lead to self-reinforcing avoidance and ignorance-based maintenance of inaccurate stereotypes.
- **study_focus_short:** Stereotype persistence through avoidance learning
- **learning_mode_description:** - Learning mode: Learning from one's own approach/avoidance outcomes about novel social group members' cooperativeness   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (monetary reward/loss from alien cooperation/defection)   - Learning about:     - Target type (social): group (novel alien species as social group proxy)     - Target content (social): state (group cooperativeness / trait inference about group)
- **task_description:** Participants played a repeated game in which they chose to approach or avoid alien characters belonging to two visually distinct species. When approached, aliens probabilistically gave (+1 point) or took (-1 point) money. One group initially cooperated at 80-90% and the other at 10-20%, with group compositions changing over time so groups converge. In some studies, feedback was contingent on approach; in others, full feedback was provided regardless.
- **task_paradigm:** Approach-avoidance
- **players:** Single agent (participant), multi-target (two alien groups with multiple individual members per group)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Alien faces (color-coded species: green, blue, yellow), binary monetary outcomes (+1/-1 points)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Studies 1-2: Participants continued approaching initially cooperative group more than initially uncooperative group even for equal-rate new members (b = -1.07, chi-squared(1) = 618.92, R-squared = .145 [Study 1])   - Study 3: Group membership predicted approach to new equal-rate members (b = -0.52, chi-squared(1) = 121.63, R-squared = .074)   - Study 3: Changes in one group affected approach to other group (b = 0.13, chi-squared(1) = 14.82)   - Study 5: Three-way interaction of group x feedback x switch condition (b = 0.17, chi-squared(1) = 5.43, R-squared = .232)   - Studies 1-5: Model with avoidance reinforcement parameter fit better than null model (DIC comparison; 95% HDI of avoidance parameter excluded 0 in Studies 1-3, 5)   - Studies 1-5: Avoidance reinforcement affected behavior but not explicit beliefs (null model best predicted explicit ratings by AIC/BIC)
- **effect_size:** - Main Results:   - Studies 1-2: Participants continued approaching initially cooperative group more than initially uncooperative group even for equal-rate new members (b = -1.07, chi-squared(1) = 618.92, R-squared = .145 [Study 1])   - Study 3: Group membership predicted approach to new equal-rate members (b = -0.52, chi-squared(1) = 121.63, R-squared = .074)   - Study 3: Changes in one group affected approach to other group (b = 0.13, chi-squared(1) = 14.82)   - Study 5: Three-way interaction of group x feedback x switch condition (b = 0.17, chi-squared(1) = 5.43, R-squared = .232)   - Studies 1-5: Model with avoidance reinforcement parameter fit better than null model (DIC comparison; 95% HDI of avoidance parameter excluded 0 in Studies 1-3, 5)   - Studies 1-5: Avoidance reinforcement affected behavior but not explicit beliefs (null model best predicted explicit ratings by AIC/BIC)
- **learning_from:** Self; own monetary outcomes from approaching aliens (reward/loss feedback)
- **learning_about:** Group (novel alien species); group-level cooperativeness/trait  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Rescorla-Wagner with avoidance reinforcement (1 alpha, 1 beta, 1 starting value, 1 avoidance parameter h); V(t+1) = V(t) + alpha*h when avoided and V(t) < 0
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** - {"name": "No avoidance parameter (null)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "DIC"} - {"name": "One avoidance parameter (both groups)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "DIC"} - {"name": "Two avoidance parameters (separate per group)", "family": "Rescorla-Wagner", "n_params": 5, "metric": "DIC"}  (In Studies 4-5, full feedback condition also included a model with forgetting parameter kappa.)
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate): Studies 1-5 fitted values range 0.04-0.13 - beta (inverse temperature): Studies 1-5 fitted values range 4.26-5.83 - Starting value (initial belief about cooperation): Studies 1-5 fitted values range 0.16-0.31 - h (avoidance reinforcement parameter) [S]: Studies 1-5 fitted values range -0.06 to -0.25 for bad group; 95% HDI excludes 0 in Studies 1-3, 5 - kappa (avoidance update modifier in full feedback condition, Studies 4-5): governs degree of value updating after avoidance when feedback is provided
- **social_param:** h (avoidance reinforcement parameter) — governs the degree to which value representations of a social group are negatively updated after avoidance; a negative value indicates self-reinforcing avoidance (avoiding makes the group seem more negative)
- **social_param_name:** h
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** -0.06–-0.25
- **model_comparison_metric:** DIC (deviance information criterion); also 95% HDI estimation approach; AIC/BIC for predicting explicit ratings
- **how_model_fit:** individual-level-fit (hierarchical Bayesian parameter estimation via JAGS, 3 chains x 200,000 samples, 20,000 burn-in)
- **data_type_fit_to:** choice behavior (approach/avoid decisions)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Study 1: N=88 (36F, 52M; Mage=36.7); Study 2: N=100 (54F, 46M; Mage=39.1); Study 3: N=299 (149F, 150M; Mage=36.8); Study 4: N=173 (78F, 94M, 1 unspecified; Mage=36.1); Study 5: N=405 (200F, 201M, 1 other, 3 unspecified; Mage=35.2). Total N=1,065. All recruited from MTurk.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low ecological validity — uses abstract alien species rather than real social groups; binary approach/avoid decisions with point outcomes; no real social interaction. Authors acknowledge the paradigm is necessarily simple to isolate processes of interest and that generalization to real-world intergroup contexts with cultural stereotypes, power differentials, and complex social behaviors remains to be tested.
- **eligibility_flag:** 
- **concerns:** - No explicit limitations section in the paper - Five studies all use MTurk samples; generalizability to in-person social interactions unclear - Alien groups are a simplified proxy for real social groups; no real social content - The avoidance reinforcement parameter 95% HDI included 0 in Study 4 (mixed evidence) - Model comparison used DIC which has known limitations; no formal model recovery analysis reported (only parameter recovery) - Choice perseveration alternative tested but only mentioned in footnote - Supplement referenced (https://doi.org/10.1037/xge0001037.supp) but not available as a file in the papers folder
- **limitations_reported:** The social world is very complex and our behavioral paradigm is necessarily simple to isolate the processes of interest"; "to better generalize these processes to the real world, it will be necessary to consider a variety of more complex factors such as different numbers and types of groups, varied behaviors that go beyond a simple approach/avoid or positive/negative dichotomy, and historical and systemic power differentials between groups"; "another critical way in which these processes may differ in the social and nonsocial domains is the reciprocal nature of impression formation"; authors acknowledge they "cannot conclusively distinguish" whether avoidance reinforcement operates at the level of stimulus-response associations vs explicit representations
- **limitations_categorized:** limited ecological validity; task simplicity; limited generalizability; cannot distinguish mechanism level (implicit vs explicit); no real social interaction
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `wc_guidelines` rule 3: MEDIUM confidence — parameter recovery is mentioned as being in supplement (Figure 2), but simulation before fitting is not explicitly described in main text - `wc_guidelines` rule 8: MEDIUM confidence — model validation is indirect (predicting ratings from model values) rather than formal posterior predictive check - Supplement not available in papers folder — some details may be missing
- **cannot_find:** - Exact formula for choice perseveration model variant (mentioned in footnote 2 only) - Full supplement content (parameter recovery figures, additional analyses referenced) - Whether data/code are publicly shared
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_social_info_search
- spec_context = partly
- spec_depth = parametric
- spec_locus = target
- spec_target = social
- tax_domain_D_group_structure_identity
- tax_mod_experiential
- tax_mod_social_info_search
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = D_group_structure_identity
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = stereotype_updating
- tax_rr_secondary_topic = intergroup_bias
- tax_rr_topic_intergroup_bias
- tax_rr_topic_stereotype_updating
- tax_topic_intergroup_bias
- tax_topic_stereotype_updating
