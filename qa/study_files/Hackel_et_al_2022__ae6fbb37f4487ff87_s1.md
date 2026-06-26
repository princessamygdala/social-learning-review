# Hackel et al. (2022)

- **study_id:** `ae6fbb37f4487ff87_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hackel, L. M., Mende-Siedlecki, P., Loken, S., & Amodio, D. M. (2022). Context-dependent learning in social interaction: Trait impressions support flexible social choices. *Journal of Personality and Social Psychology: Attitudes and Social Cognition, 123*(4), 655–675. https://doi.org/10.1037/pspa0000296
- **citation_short:** Hackel et al. (2022)
- **doi:** 10.1037/pspa0000296
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Psychology
- **affiliations_raw:** ethislearningtonovelsituations,sincetheycannot trial-and-errorfeedbackininteractionsremainsunstudied; ethodology,writingoforiginal WashingtonPl,NewYork,NY10003,UnitedStates; DepartmentofPsychologicalandBrainSciences,UniversityofDelaware; Department of Psychology, University of Southern California,; DepartmentofPsychology,UniversityofSouthernCalifornia; Department ofPsychology,UniversityofAmsterdam; ethisknowledgetomakeflexiblesocialdecisions; DepartmentofPsychology,NewYorkUniversity,6; emails: .eduordavid.amodio@nyu.edu
- **code_url:** https://osf.io/496rn/

## Computational level
- **study_focus:** Context-dependent trait inference learning; how people learn context-specific trait impressions (vs. reward associations) through interactive feedback across domains, and how this supports flexible cross-context social decision-making.
- **study_focus_short:** Context-dependent trait inference learning
- **learning_mode_description:** - Learning mode: Learning from feedback about others' domain-specific competence and reward value across contexts to make context-appropriate partner choices.   - Learning from:     - Source type (social): other (ostensible prior players)     - Source content (social): outcome (competence proportion + absolute reward points as feedback)   - Learning about:     - Target type (social): other (ostensible prior players)     - Target content (social): state (mental state; trait-level competence) + outcome (reward value)
- **task_description:** Participants played a "hiring" game, choosing one of four ostensible prior players to answer math or verbal GRE questions across repeated trials. Feedback indicated both the absolute reward (points earned) and the player's competence (proportion of available points earned), allowing independent learning of reward values and trait-level competence in each context.
- **task_paradigm:** Impression formation task
- **players:** Single agent (participant), multi-target (4 ostensible prior players)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Avatars (gender/race held constant), GRE context labels (math/verbal), point feedback (earned/out of)
- **method:** behavioural
- **method_full:** behavioural (Studies 1-4; all behavioural, no neuroimaging)
- **main_result:** - Study 1 Learning: Competence feedback reinforced choices globally (b = .45, SE = .04, z = 11.91); Competence x Context interaction (b = .27, SE = .04, z = 7.49); competence within same context (b = .72, SE = .05, z = 13.42); competence in different context (b = .18, SE = .05, z = 3.62); no reward effect (b = .02, SE = .04, z = .65); trait > reward (chi-sq = 68.50) - Study 1 Computational Model: Competence same context (beta = 1.68, SE = .11, z = 15.00); competence different context (beta = .69, SE = .13, z = 5.28); difference z = 4.88; reward same context (beta = -.08, SE = .10, z = -.83, ns); reward different context (beta = .14, SE = .10, z = 1.40, ns); trait > reward z = 14.63 - Study 1 Test Phase: Relevant competence (b = 1.78, SE = .18, z = 9.83); irrelevant competence (b = .58, SE = .12, z = 4.76); context-dependent > global (chi-sq = 30.38); no reward effects (relevant b = .07, ns; irrelevant b = -.02, ns) - Study 2 replicates Study 1 pattern - Study 3: Generalization to novel contexts -- math competence x similarity to math (b = .37, SE = .08, z = 4.37); verbal competence x similarity to verbal (b = .10, SE = .03, z = 2.96); double dissociation (chi-sq = 18.20); no reward generalization - Study 4 Test Phase: Relevant competence (b = .95, SE = .10, z = 9.27); irrelevant competence (b = .33, SE = .08, z = 4.00); context-dependent > global (chi-sq = 22.70); weak reward effect in relevant context (b = .14, SE = .05, z = 2.51); context-dependence of competence > rewards (chi-sq = 13.82) - Study 4 Social Preferences: Verbal prioritization differs by scenario type (F(2,168) = 10.42, eta-sq-p = .11); empathy scenario verbal prioritization (d = .43); social problem-solving (d = .29); no reward generalization to social scenarios (F(2,168) = .38, eta-sq-p = .005, ns)  ---  ### (6) Winning model
- **effect_size:** 
- **learning_from:** other's performance feedback (competence proportion and reward points)
- **learning_about:** other's context-specific trait competence and reward value  ---  ### (4) Computational problem  How does a learner form context-dependent trait impressions of social partners through interactive feedback, and how do these impressions -- as opposed to reward associations -- guide flexible cross-context social decision-making? (Prediction / evaluation)  ---  ### (5) Results with effect sizes
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Hybrid reward-trait RL with context-specific values: separate Q (reward) and C (competence) values per context, single learning rate alpha, softmax with 4 separate choice weights (beta_Q_relevant, beta_Q_irrelevant, beta_C_relevant, beta_C_irrelevant). "RW hybrid (1 alpha; 4 betas: beta_C_rel, beta_C_irrel, beta_Q_rel, beta_Q_irrel)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Hybrid reward-trait RL (context-specific)", "family": "Rescorla-Wagner", "n_params": 5, "metric": "Wald tests on parameters"}]  ---  ### (8) Model comparison
- **model_mb_mf:** MF (model-free; incremental value updating via prediction errors, though authors discuss possible model-based interpretation of trait learning)  ---  ### (7) All models tested  Only one computational model is described. No formal model comparison with alternative models is reported. The paper uses a single hybrid reward-trait RL model alongside regression analyses as a complementary approach.
- **model_params:** - alpha: learning rate (shared for reward and competence updating) - beta_Q_relevant [S context-dependent]: choice weight for reward value in relevant context - beta_Q_irrelevant [S context-dependent]: choice weight for reward value in irrelevant context - beta_C_relevant [S context-dependent]: choice weight for competence in relevant context - beta_C_irrelevant [S context-dependent]: choice weight for competence in irrelevant context  Mean fitted values: Study 1: beta_C_relevant = 1.68, beta_C_irrelevant = .69, beta_Q_relevant = -.08, beta_Q_irrelevant = .14; Study 2: beta_C_relevant = 1.57, beta_C_irrelevant = .73, beta_Q_relevant = .11, beta_Q_irrelevant = .29. Alpha values not reported in main text.
- **social_param:** beta_C_relevant and beta_C_irrelevant -- choice weights for context-specific trait competence, capturing how much trait impressions (vs. rewards) drive partner choice within and across domains.  ---  ### (9) Neuroimaging
- **social_param_name:** beta_C_relevant and beta_C_irrelevant
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** No formal model comparison (only 1 computational model tested). Parameters tested against zero using Wald tests. Linear contrasts of coefficients used to compare trait vs. reward choice weights.
- **how_model_fit:** group-level-fit (hierarchical model fitting population distribution from all subjects, analogous to mixed-effects regression; Daw, 2011)
- **data_type_fit_to:** choice behavior

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (purely behavioural studies)
- **coordinates_peak:** N/A  ---  ### (10) Analysis type
- **analysis_type:** N/A (no neuroimaging)
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** - Study 1: N = 50 (10 males, 40 females; M_age = 18.94, SD = .91; NYU undergraduates) - Study 2: N = 50 (17 males, 33 females; M_age = 19.14, SD = 1.70; U Delaware undergraduates) - Study 3: N = 51 (22 males, 29 females; M_age = 19.86, SD = 1.50; NYU undergraduates) - Study 4: N = 85 (23 males, 62 females; M_age = 19.56, SD = 2.05; NYU undergraduates) - Total N = 236
- **population_category:** undergraduates
- **population_age_range:** 
- **ecological_validity:** The task uses an abstract "hiring" game with avatar-represented players and GRE-like framing. Interactions are simulated (no real-time social interaction); feedback is pre-programmed. Studies 3-4 extend to social support scenarios (empathy, social problem-solving), increasing ecological relevance. However, the binary choice structure and controlled feedback substantially simplify real-world social learning.  ---  ### (13) Eligibility flag
- **eligibility_flag:** 
- **concerns:** - Only one computational model tested; no formal model comparison or alternative model architectures explored - Alpha (learning rate) value not reported in main text; may be in supplement (not accessible) - Supplement referenced extensively (Tables S1-S10) but not available for verification - Hierarchical fitting approach used due to counterbalancing constraints (cannot fit individual subjects), limiting individual-level parameter recovery - All samples are undergraduate students from 2 US universities, limiting generalizability - No parameter recovery or model recovery analyses reported - Social interaction is entirely simulated -- participants never interact with real people
- **limitations_reported:** Authors acknowledge: reward learning may be impeded by rapid context alternations (Studies 1-3); existing accounts of model-based learning are silent on how trait knowledge may be used or generalized in a context-dependent manner; task uses economically framed feedback rather than naturalistic social interaction; the learning mechanisms studied are domain-general rather than unique to social interaction; global trait impressions (halo effects) may reflect lay beliefs about trait correlations rather than true generalization
- **limitations_categorized:** limited ecological validity; task simplicity; limited generalizability; domain-general vs. social-specific mechanism ambiguity; no formal model comparison
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
- **wc_rule10:** Yes
- **wc_score:** 4.5
- **wc_total:** 4.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - alpha parameter value: LOW (not reported in main text; supplement not accessible) - model_mb_mf: MEDIUM (classified as MF based on incremental PE updating, but authors discuss trait learning as potentially model-based) - All supplementary tables (S1-S10): cannot verify
- **cannot_find:** - Alpha learning rate fitted values - Full parameter distributions - Supplement tables S1-S10  ---  ### (15) WC checklist  1. Design a good experiment: **Yes** (task independently manipulates reward value and trait competence across contexts; well-designed to test targeted processes) 2. Design good models: **No** (only 1 computational model tested; no competing model architectures) 3. Simulate, simulate, simulate: **No** (no simulation of model before fitting described in main text) 4. Fit the parameters: **Yes** (hierarchical model fitting using population-level parameters; Daw 2011 approach) 5. Check parameter recovery: **No** (no parameter recovery described) 6. Check model recovery: **No** (no model recovery / confusion matrix; only 1 model) 7. Fit real data and compare models: **No** (only 1 model; no formal model comparison) 8. Validate the winning model: **Partial** (regression analyses provide complementary validation of computational model findings, but no formal posterior predictive check) 9. Analyze the winning model: **Yes** (choice weights analyzed, compared via Wald tests and linear contrasts) 10. Report results transparently: **Yes** (data shared on OSF: https://osf.io/496rn/)  ---  ### (16) Preregistered?
- **other_notes:** Supplement not accessible (referenced as https://doi.org/10.1037/pspa0000296.supp). Paper contains a published correction noting a typo ("Computational Mode of Learning" should be "Computational Model of Learning"). The paper explicitly cites Hackel et al. (2015) which used a similar task with fMRI -- this earlier paper may also be in the review corpus and should be checked for overlap (different study, different data). The computational model is relatively simple (standard RW with context-specific values) but the theoretical contribution lies in demonstrating trait-based learning dominates over reward-based learning across social contexts.
- **re_extract_flag:** false (full text accessible; supplement not accessible but flagged)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_mod_active_interaction
- tax_mod_experiential
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
