# Shafto et al. (2014)

- **study_id:** `ade766e02a2dd4206_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Shafto, P., Goodman, N. D., & Griffiths, T. L. (2014). A rational account of pedagogical reasoning: Teaching by, and learning from, examples. *Cognitive Psychology, 71*, 55-89.
- **citation_short:** Shafto et al. (2014)
- **doi:** 10.1016/j.cogpsych.2013.12.004
- **publication_type:** peer-reviewed journal
- **year:** 2014.0
- **field_of_study:** Psychology
- **affiliations_raw:** schools, teachers impart their knowledge to students about mathematics, science, and literature; ethisknowledgetoguideinferences(Topal,Gergely,Miklosi,Erdohegyi,&Csibra,2008); lableonline7March2014 plesforthepurposeofhelpingalearneracquiretheconcept; mittoanotheragentforthepurposeofteachingaconcept; etheexamplesthatwillmosthelpthelearnerinferthe; labilitytoengageinandtakeadvantageofexplicit; UniversityofCalifornia,Berkeley,UnitedStates; ethatdataaresampledbysomerelatively; emails: p.shafto@louisville.edu
- **code_url:** 

## Computational level
- **study_focus:** Pedagogical reasoning / concept learning in social teaching contexts -- how a knowledgeable teacher selects examples to help a learner acquire concepts, and how learners leverage knowledge of the teacher's helpful intent to make stronger inferences.
- **study_focus_short:** Pedagogical reasoning / concept learning in social teaching contexts -- how a
- **learning_mode_description:** - Learning mode: Learning concepts from pedagogically selected examples provided by a knowledgeable teacher   - Learning from:     - Source type (social): other (teacher)     - Source content (social): action/policy (example selection strategy)   - Learning about:     - Target type (non-social): world (concept structure)     - Target content (non-social): state (concept identity -- rule-based, prototype, or causal structure)
- **task_description:** In "teaching games," participants alternated between teacher and learner roles. As teachers, they knew the true concept (a rectangle region, a prototype distribution, or a causal structure) and selected examples to help a learner identify it. As learners, they observed examples ostensibly chosen by a teacher (or randomly) and inferred the concept.
- **task_paradigm:** Pedagogical learning
- **players:** Single agent (participant), dyadic (absent teacher or learner partner -- no live interaction; cover story of pedagogical partner)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Exp 1: points on a grid board labeled inside/outside a rectangle; Exp 2: line segments varying in length (prototype distribution); Exp 3: causal structures among three variables with noisy-or relations, interventions and outcomes
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Exp 1 Teaching: Teachers chose positive examples in corners of rectangle (M_corner = .87, M_non-corner = .13; t(17) = 6.55, p < .0001); negative examples near boundary (M_near = .97, M_middle = .03, M_far = 0; F(1,15) = 355.8, p < .0001)   - Exp 1 Learning: Pedagogical learners placed examples in corners significantly more than non-pedagogical learners (Teaching-Ped: t(17) = 7.96; Ped: t(25) = 5.86; Non-Ped: t(27) = 1.02, p = .32 ns)   - Exp 2 Teaching: Pedagogical model fit significantly better than strong sampling (chi-squared(1) = 69.04)   - Exp 2 Learning: Main effect of cover story on generalization variance (F(1,80) = 10.70, MSE = .196); main effect of sampling (F(1,80) = 6.41, MSE = .196)   - Exp 3 Teaching: Intervention choices highly non-random and strongly correlated with pedagogical model predictions (common effect: r = .96; causal chain: r = .94; common cause: r = .97)   - Exp 3 Learning (ambiguous cases): Teaching-Ped Learning showed predicted differences (t(88) = 2.22; t(58) = 4.21); interaction F(1,54) = 9.33
- **effect_size:** - Main Results:   - Exp 1 Teaching: Teachers chose positive examples in corners of rectangle (M_corner = .87, M_non-corner = .13; t(17) = 6.55, p < .0001); negative examples near boundary (M_near = .97, M_middle = .03, M_far = 0; F(1,15) = 355.8, p < .0001)   - Exp 1 Learning: Pedagogical learners placed examples in corners significantly more than non-pedagogical learners (Teaching-Ped: t(17) = 7.96; Ped: t(25) = 5.86; Non-Ped: t(27) = 1.02, p = .32 ns)   - Exp 2 Teaching: Pedagogical model fit significantly better than strong sampling (chi-squared(1) = 69.04)   - Exp 2 Learning: Main effect of cover story on generalization variance (F(1,80) = 10.70, MSE = .196); main effect of sampling (F(1,80) = 6.41, MSE = .196)   - Exp 3 Teaching: Intervention choices highly non-random and strongly correlated with pedagogical model predictions (common effect: r = .96; causal chain: r = .94; common cause: r = .97)   - Exp 3 Learning (ambiguous cases): Teaching-Ped Learning showed predicted differences (t(88) = 2.22; t(58) = 4.21); interaction F(1,54) = 9.33
- **learning_from:** other (teacher); pedagogically selected examples/interventions
- **learning_about:** world; concept identity (rectangle boundaries, prototype distribution, causal structure)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Bayesian pedagogical sampling model (recursive Bayesian inference with pedagogical likelihood; P_teacher(d|h) proportional to [P_learner(h|d)]^alpha; alpha fixed at 1; solved via fixed-point iteration)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "Pedagogical sampling model", "family": "Bayesian belief updating", "n_params": 1, "metric": "likelihood ratio test / qualitative fit"} - {"name": "Weak sampling (random)", "family": "Bayesian belief updating", "n_params": 0, "metric": "qualitative comparison"} - {"name": "Strong sampling", "family": "Bayesian belief updating", "n_params": 0, "metric": "likelihood ratio test"}
- **model_mb_mf:** Bayesian
- **model_params:** - alpha (teaching optimality parameter, fixed at 1) -- controls how strongly teacher maximizes learner's posterior; alpha = 1 corresponds to probability matching via Luce choice rule - Prior P(h) -- uniform over hypothesis space (fixed, not fitted) - Likelihood P(d|h) -- derived from generative model specific to each experiment (weak sampling for Exp 1, normal distribution for Exp 2, noisy-or Bayes net for Exp 3) - Exp 3 additional: causal transmission rate = .9, background rate = .05 (fixed from training)
- **social_param:** alpha -- teaching optimality parameter controlling how helpfully the teacher selects examples for the learner (when alpha -> infinity, teacher perfectly maximizes learner posterior; alpha = 0 reduces to random sampling)
- **social_param_name:** alpha
- **social_param_value:** 1
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Likelihood ratio test (Exp 2: chi-squared); correlation between model predictions and human data (Exp 3); qualitative fit comparison throughout
- **how_model_fit:** simulate-and-compare (model predictions generated from computational model and compared qualitatively and quantitatively to human data; no individual-level parameter fitting)
- **data_type_fit_to:** choice behavior (teacher example selections and learner concept inferences/ratings)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A -- no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Exp 1: N = 73 (18 Teaching-Ped Learning, 26 Ped Learning, 29 Non-Ped Learning); Exp 2: N = 28 (teaching task) + N = 84 (learning task); Exp 3: N = 86 (30 Teaching-Ped Learning, 30 Ped Learning, 26 Non-Ped Learning). All university undergraduates.
- **population_category:** undergraduates
- **population_age_range:** 
- **ecological_validity:** Low -- highly abstract laboratory tasks (rectangles on grids, line lengths, abstract causal variables). No real social interaction; teacher/learner partners were absent or hypothetical. Cover story framing rather than actual dyadic teaching.
- **eligibility_flag:** FLAGGED -- Borderline on inclusion criteria. This paper models pedagogical concept learning (social context: teacher-learner) but the "learning" is primarily one-shot concept inference from a fixed set of examples, not iterative learning over time with trial-by-trial updating. There is no temporal prediction error or sequential belief updating across trials. The social component is the framing (pedagogical vs. random sampling) rather than learning about a social agent or social environment. The computational model is a Bayesian inference model at the computational level, not a process-level learning model. Flag as: "borderline -- concept inference rather than learning over time; social context is pedagogical framing rather than social learning per se.
- **concerns:** - No individual-level model fitting -- all comparisons are at the group level (qualitative patterns, aggregate correlations) - The alpha parameter is fixed at 1, not estimated from data - No formal model comparison beyond likelihood ratio for Exp 2 and correlations for Exp 3 - Teacher and learner were never actually interacting -- pedagogical context was a cover story - Order effects (teaching first improving pedagogical learning) not fully explained - No parameter recovery, no model recovery
- **limitations_reported:** We have focused on cases of simple concept learning, cases that are much simpler than those that may be encountered in educational contexts"; "A critical issue for future work will be generalizing these results to more ecologically valid domains and where the problem of learning includes the possibility of encountering novel concepts"; recursive reasoning is "extremely demanding and the resource demands grow with the recursion depth" -- possible that participants use approximate or cached computations rather than full recursive reasoning.
- **limitations_categorized:** limited ecological validity; task simplicity; limited generalizability; no process-level account; no individual-level fitting
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 4.5
- **wc_total:** 4.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
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
- rr_tax_mod_pedagogical_sampling
- spec_context = social
- spec_depth = structural
- spec_locus = source
- spec_source = social
- tax_domain_B_inference_modelling_others
- tax_mod_pedagogical_sampling
- tax_model_bayesian
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_primary_topic = pedagogical_reasoning
- tax_rr_topic_pedagogical_reasoning
- tax_topic_pedagogical_reasoning
