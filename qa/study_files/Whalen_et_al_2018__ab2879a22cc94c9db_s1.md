# Whalen et al. (2018)

- **study_id:** `ab2879a22cc94c9db_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Whalen, A., Griffiths, T. L., & Buchsbaum, D. (2018). Sensitivity to shared information in social learning. *Cognitive Science, 42*(1), 168–187. https://doi.org/10.1111/cogs.12485
- **citation_short:** Whalen et al. (2018)
- **doi:** 10.1111/cogs.12485
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Psychology
- **affiliations_raw:** Department ofPsychology, University ofCalifornia, Berkeley; ether or not learners are sensitive to shared information; School of Biology, University of St Andrews, Harold; Departmentof Psychology,University of Toronto; MitchellBuilding, StAndrews, FifeKY169TH, UK; mpirical support (Asch, 1956; Efferson et al; Schoolof Biology,University ofSt Andrews; ether or not the; emails: awhalen@gmail.com
- **code_url:** 

## Computational level
- **study_focus:** Social information evaluation; sensitivity to statistical dependency among informants' testimony during social learning
- **study_focus_short:** Social information evaluation
- **learning_mode_description:** - Learning mode: Learning from multiple informants' testimony about the state of the world, evaluating testimony reliability based on shared vs. independent information sources   - Learning from:     - Source type (social): other (group of 3 informants)     - Source content (social): action/policy (testimony/judgment about state of the world)   - Learning about:     - Target type (non-social): world (which urn filled the bag)     - Target content (non-social): state (world state; true state of the environment)
- **task_description:** Participants observe a ball-and-urn scenario in which an experimenter secretly fills a bag from one of two urns with known ball proportions. Three informants each provide testimony about which urn was used; the participant then rates how likely each urn was used, given the informants' testimony and (in Exps 1-2) their own private ball observation.
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant), multi-target (3 informants providing testimony)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Cartoon images of urns/jars with colored balls, text-based vignettes describing informant testimony, 11-point rating scale
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Exp 1: Significant effect of condition on majority agreement ratings (F(2,120) = 7.749, p < .001). Independent vs. shared private data (d = 0.80); sequential vs. shared private data (d = 0.55); independent vs. sequential (d = 0.22, n.s.) - Exp 2: Significant effect of condition (F(5,395) = 20.13, p < .01). Independent vs. shared private data (d = 0.71); sequential vs. shared private data (d = 0.87); color whispering vs. shared data whispering (d = 1.02); sequential whispering vs. shared data whispering (d = 0.82) - Exp 3: Significant effect of condition (F(2,121) = 5.56, p < .01). Independent vs. sequential (d = 0.65); independent vs. shared private data (d = 0.66) - Probability matching Bayesian model fit: Exp 1 r = .91; Exp 2 r = .81; Exp 3 r = .94 - Maximizing Bayesian model fit: Exp 1 r = .83; Exp 2 r = .63; Exp 3 r = .83
- **effect_size:** See main_result above. Cohen's d values: 0.80, 0.55, 0.22 (Exp 1); 0.71, 0.87, 1.02, 0.82, 0.25, 0.53, 0.30, 0.52, 0.45 (Exp 2); 0.65, 0.66, 0.05 (Exp 3). Pearson's r for model fits: .83/.91 (Exp 1), .63/.81 (Exp 2), .83/.94 (Exp 3).
- **learning_from:** Other (group); informants' testimony about world state
- **learning_about:** World; true state of the environment (which urn was used)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Bayesian belief updating with probability matching (no free parameters; p(t_i = h|d_i) proportional to p(d_i|h)p(h))
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "Bayesian maximizing", "family": "Bayesian belief updating", "n_params": 0, "metric": "Pearson's r (model-data correlation)"},   {"name": "Bayesian probability matching", "family": "Bayesian belief updating", "n_params": 0, "metric": "Pearson's r (model-data correlation)"} ]
- **model_mb_mf:** Bayesian
- **model_params:** No free parameters. The model uses known task parameters: p (proportion of majority-colored balls in urn = 5/6 in Exp 1 or 9/10 in Exps 2-3), q (probability participant receives a majority-colored ball = 5/6 or 9/10). Informant testimony likelihood computed via Bayes' rule with marginalization over unobserved private data.
- **social_param:** No explicit social parameter. The model's "social" component is structural: the dependency structure between informants (independent, sequential, shared data) determines how informant likelihoods are computed, but this is encoded in the model architecture rather than a fitted parameter.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Pearson's r (correlation between model predictions and mean human ratings across conditions)
- **how_model_fit:** simulate-and-compare (model generates parameter-free predictions from task structure; these are compared to group-level human data)
- **data_type_fit_to:** self-report ratings (11-point scale of urn likelihood)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Exp 1: N = 123 (37 independent, 41 sequential, 45 shared data); Exp 2: N = 450 recruited, 401 after attention check exclusions (67 independent, 65 sequential, 64 shared data, 69 color whispering, 69 sequential whispering, 67 shared data whispering); Exp 3: N = 124 (41 independent, 41 sequential, 42 shared data). Total across experiments: N = 697 (648 analyzed). All recruited via Amazon Mechanical Turk.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low. Highly abstract ball-and-urn task with cartoon stimuli and text-based vignettes. Informants are fictional characters, not real social agents. No real social interaction. However, the dependency structures tested (shared information, sequential testimony, whispered information) do map onto real-world social information scenarios.
- **eligibility_flag:** Borderline — the task is a one-shot judgment (no learning over time/trials). Participants make a single rating per condition. There is no trial-by-trial learning or updating. The Bayesian model describes optimal inference given evidence, not a learning process that unfolds over time. This may not meet the "learning happens over time" inclusion criterion. FLAG: potential eligibility concern — one-shot inference, not iterative learning.
- **concerns:** (1) One-shot design with no repeated trials — participants make a single judgment, so there is no temporal learning process. (2) The Bayesian model has zero free parameters and is compared to human data only via correlation of condition means (3 or 6 data points), which is a very coarse comparison. (3) No individual-level model fitting. (4) Informants are fictional text-based characters, limiting social realism. (5) MTurk sample with $0.25 compensation raises data quality concerns. (6) Exp 1 and 3 had no attention checks.
- **limitations_reported:** The scenario presented in previous experiments on information cascades may not be sufficient to distinguish between how people use independent testimony over sequential testimony"; participants may have "a bias to assume individuals are more independent than they actually are, which could be rational if, for example, informants brought outside knowledge to the task"; deviation from model in Exp 2 where sequential testimony > color whispering may reflect conformity bias or lower sensitivity to sequential dependency.
- **limitations_categorized:** Limited ecological validity; task simplicity; limited social interaction; no individual-level model fitting; potential conformity bias confound; small effect sizes for some conditions
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** 
- **wc_rule5:** 
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - eligibility_flag (MEDIUM): One-shot inference task, not iterative learning over time — may not meet inclusion criterion - model_comparison_metric (MEDIUM): Only Pearson's r between model predictions and condition means used; no formal model comparison - social_param (HIGH): No fitted social parameter exists; dependency structure is architectural - wc_guidelines Rule 2 (MEDIUM): Scored Partial because only two variants of the same model family tested
- **cannot_find:** - No supplement available (none found) - No individual-level model fitting reported - No formal model comparison statistics (BIC, AIC, etc.) - No data/code sharing links
- **other_notes:** This paper is primarily about rational inference regarding the reliability of social information sources, not about learning over time. The Bayesian model is a normative/rational benchmark with zero free parameters, not a fitted computational model in the typical sense. The paper's contribution is demonstrating that humans are sensitive to statistical dependency structures among informants. Preliminary versions of Experiments 1 and 3 were presented at CogSci 2013 (Whalen, Buchsbaum, & Griffiths, 2013).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_instructed
- rr_tax_mod_social_info_search
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- tax_domain_A_influence_transmission
- tax_mod_instructed
- tax_mod_social_info_search
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = informational_cascade
- tax_rr_topic_informational_cascade
- tax_rr_topic_social_info_use
- tax_topic_informational_cascade
- tax_topic_social_info_use
