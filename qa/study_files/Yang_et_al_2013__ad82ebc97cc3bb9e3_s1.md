# Yang et al. (2013)

- **study_id:** `ad82ebc97cc3bb9e3_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Yang, D. J., Bushnell, E. W., Buchanan, D. W., & Sobel, D. M. (2013). Infants' use of contextual cues in the generalization of effective actions from imitation. *Journal of Experimental Child Psychology, 116*, 510–531. https://doi.org/10.1016/j.jecp.2012.09.013
- **citation_short:** Yang et al. (2013)
- **doi:** 10.1016/j.jecp.2012.09.013
- **publication_type:** peer-reviewed journal
- **year:** 2013.0
- **field_of_study:** Developmental psychology
- **affiliations_raw:** DepartmentofCognitive,Linguistic,andPsychologicalSciences(CLPS),BrownUniversity,Providence,RI02912,USA; mitationalsoallowschildrentheopportunitytolearntheefficacyofobjectsandactionstoward; mitatemultistepactivities(Bauer&Hertsgaard,1993;Herbert&Hayne,2000),tool-; ethenpresentthreeexperiments,manipulatinghowlikelyitisthatobjects; etheyjustreproducingtheaction,ordotheyalsonoteitsconsequencesand; ethatknowledgetotheefficacyofnovelkettles(whichmightbeactivated; DepartmentofPsychology,TuftsUniversity,Medford,MA02155,USA; ethatwhenwespeakofaninfant’slearningorunderstandingana; emails: dave_sobel@bro
- **code_url:** 

## Computational level
- **study_focus:** Imitation learning / observational learning — generalization of action efficacy from social demonstration, modeled as rational categorization (Bayesian Dirichlet process).
- **study_focus_short:** Imitation learning / observational learning
- **learning_mode_description:** - Learning mode: Learning from an adult demonstrator's effective actions on objects about whether those actions generalize to novel objects via rational categorization.   - Learning from:     - Source type (social): other (adult demonstrator)     - Source content (social): action/policy (demonstrated effective vs. ineffective actions on objects)   - Learning about:     - Target type (non-social): world (novel objects / object category membership)     - Target content (non-social): action/policy (efficacy of actions on novel category members)
- **task_description:** An adult experimenter demonstrated effective and ineffective actions (pressing a button or pulling a handle) on toy objects to 15-month-old infants. Infants then interacted with a novel test toy affording both actions, and their preferential touching/manipulation of the effective handle was measured across conditions varying the perceptual similarity of demonstration and test objects.
- **task_paradigm:** Observational learning task
- **players:** Single agent (infant participant), single demonstrator (adult experimenter)
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Physical toy objects (bunny set, cow set, pyramid), mechanical handles (push-button, pull-lever), novel sound effects as outcomes
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Experiment 1: Infants touched the effective handle longer than the ineffective handle (d = 4.23) and manipulated it longer (d = 4.50)   - Experiment 2: Infants showed no preference for effective handle when test toy differed from demonstration toys (touching: t(15) = -0.10, n.s.; manipulating: t(15) = -0.42, n.s.)   - Experiment 1 vs. 2 interaction: Significant Experiment x Handle interaction for touching (F(1,30) = 4.55, η² = .05) and manipulating (F(1,30) = 4.35, η² = .08)   - Experiment 3 varied condition: Infants first touched effective handle significantly more often (binomial p = .01, φ = 0.27) and first manipulated it more often (binomial p = .03, φ = 0.26)   - Experiment 3 same condition: No preference for effective handle (n.s.)   - Computational model: RMC with pedagogical assumptions placed all three same-appearance objects in one category 80% of trials; varied-appearance demonstration objects led to 52% same-category assignment for test object vs. 41% when demonstration objects shared appearance
- **effect_size:** d = 4.23 (Exp 1 touching); d = 4.50 (Exp 1 manipulating); η² = .05 (Exp 1 vs 2 touching interaction); η² = .08 (Exp 1 vs 2 manipulating interaction); φ = 0.27 (Exp 3 varied first touch); φ = 0.26 (Exp 3 varied first manipulation)
- **learning_from:** Other (adult demonstrator); observed effective/ineffective actions on objects
- **learning_about:** World (object category membership and action efficacy generalizability)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Rational Model of Categorization (RMC) with hierarchical learning of β and pedagogical assumption (Dirichlet process; 2 params: α, β)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "RMC with hierarchical β learning + pedagogical assumption", "family": "Bayesian (Dirichlet process)", "n_params": 2, "metric": "qualitative fit to experimental conditions"},   {"name": "Fully rational Dirichlet process (no pedagogical assumption, Gibbs sampling)", "family": "Bayesian (Dirichlet process)", "n_params": 2, "metric": "qualitative fit"},   {"name": "Modified Dirichlet process without hierarchical learning (β fixed at 1)", "family": "Bayesian (Dirichlet process)", "n_params": 1, "metric": "qualitative fit"} ]
- **model_mb_mf:** Bayesian
- **model_params:** - α (coupling parameter): tendency for objects to be placed in the same category; set to 1 - β (feature homogeneity parameter) [S]: captures how much the model prefers that categories have homogeneous features; learned hierarchically from data; proposed from Exponential(1) prior
- **social_param:** β (feature homogeneity): learned from the pedagogical demonstration context — when demonstration objects are varied, β is learned to be weak (permitting broader categorization and thus generalization of socially demonstrated efficacy)
- **social_param_name:** β
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Qualitative fit (ordinal prediction matching across experimental conditions); no formal quantitative metric (e.g., BIC/AIC) reported
- **how_model_fit:** simulate-and-compare (Monte Carlo simulation, 10,000 samples)
- **data_type_fit_to:** choice behavior (qualitative pattern matching to proportion of infants choosing effective handle first)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** Experiment 1: N = 16 (9 girls, 7 boys; mean age = 14.69 months); Experiment 2: N = 16 (9 girls, 7 boys; mean age = 15.03 months); Experiment 3: N = 48 (28 girls, 20 boys; mean age = 14.94 months; 24 per condition). Total N = 80.
- **population_category:** healthy adults
- **population_age_range:** M=14.69
- **ecological_validity:** Lab-based imitation task with physical toys; fairly naturalistic object-manipulation context for infants, though structured demonstration procedure limits ecological validity. Objects are custom-built experimental toys, not everyday objects.
- **eligibility_flag:** Borderline — the computational model is applied post hoc to qualitatively capture ordinal patterns across conditions. It is not formally fit to individual-level behavioral data (no parameter estimation from data, no quantitative model comparison). The model is a Bayesian categorization model, not a trial-by-trial learning model. Participants are 15-month-old infants, which is unusual for the review corpus. The "learning over time" criterion is marginal — infants observe a few demonstrations and then act once on a test object, which is closer to one-shot generalization than iterative learning. FLAG: borderline computational modeling (qualitative fit only); borderline learning-over-time (few-shot demonstration, single test trial).
- **concerns:** - The computational model is not formally fit to data — it produces qualitative ordinal predictions that match the pattern of results, but no quantitative fit metrics (BIC, AIC, log-likelihood) are reported - Cohen's d values of 4.23 and 4.50 in Experiment 1 are implausibly large, likely calculated incorrectly (possibly using SE rather than SD in the denominator, or a non-standard formula) - No parameter recovery or model recovery performed - Model is demonstrated on aggregate experimental conditions, not fit to individual participant data - α is fixed at 1, not estimated; β is learned hierarchically but its fitted values are not reported - Small sample sizes (N = 16 per experiment for Experiments 1 and 2)
- **limitations_reported:** Cannot determine whether generalization is an object-centered categorical process or an action-centered encoding process; model does not provide precise quantitative fit; features in the model are treated as equally weighted, which may not reflect infant cognition; developmental mechanisms underlying the 12-to-15-month transition in generalization ability are not addressed
- **limitations_categorized:** Model ambiguity (multiple theoretical interpretations); limited quantitative model fit; simplistic feature representation; developmental mechanism unspecified; small sample sizes
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `effect_size`: MEDIUM — Cohen's d values (4.23, 4.50) are implausibly large; likely computational error in the original paper - `model_params`: MEDIUM — α is fixed, β is learned but fitted values not reported - `model_comparison_metric`: LOW — no formal quantitative comparison metric used; only qualitative ordinal fit - `eligibility_flag`: MEDIUM — borderline on computational modeling criterion (qualitative fit only) and learning-over-time criterion (few-shot demonstration) - `winning_model`: MEDIUM — "winning" is based on qualitative match, not formal model comparison
- **cannot_find:** - Exact fitted values of β parameter - Formal quantitative model comparison metrics (BIC, AIC, etc.) - Individual-level model fit statistics - Data or code availability
- **other_notes:** This paper uses a Bayesian rational model of categorization (RMC, based on Anderson 1990 and Sanborn et al. 2010) to explain infant imitation/generalization data. The model is applied at the level of experimental conditions rather than individual participants. The "social" component is in the pedagogical assumption (that infants assume the demonstrator is showing objects for a reason, i.e., they belong to the same category) — this assumption is what makes the model work. Without it, the fully rational Dirichlet process model fails to capture the data. No supplement was found for this paper.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_children
- rr_pop_children
- rr_tax_mod_action_observation
- rr_tax_mod_pedagogical_sampling
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_pedagogical_sampling
- tax_model_bayesian
- tax_popclass_developmental
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_social_weight
- tax_rr_primary_topic = imitation_emulation
- tax_rr_secondary_topic = pedagogical_reasoning
- tax_rr_topic_imitation_emulation
- tax_rr_topic_pedagogical_reasoning
- tax_topic_imitation_emulation
- tax_topic_pedagogical_reasoning
