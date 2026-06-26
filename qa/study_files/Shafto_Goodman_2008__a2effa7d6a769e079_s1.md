# Shafto & Goodman (2008)

- **study_id:** `a2effa7d6a769e079_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Shafto, P., & Goodman, N. (2008). Teaching games: Statistical sampling assumptions for learning in pedagogical situations. In B. C. Love, K. McRae, & V. M. Sloutsky (Eds.), *Proceedings of the 30th Annual Conference of the Cognitive Science Society* (pp. 1632–1637). Cognitive Science Society.
- **citation_short:** Shafto & Goodman (2008)
- **doi:** Not reported in the paper text. [flagged in cannot_find]
- **publication_type:** conference proceedings (peer-reviewed)
- **year:** 2008.0
- **field_of_study:** Psychology
- **affiliations_raw:** etheproblemofpedagogicalrea- necessarilybeasolutiontothesystemofequationsdefining; etheexamplesthatwillmost modelascapturingtheoutcomeofarecursivementalreason-; mittoanotheragentforthepur- from positive examples alone; label points inside and/or outside the rectangle; schools, teachers impart their knowl-; labeled examples chosen by; ethatconcepttoalearnerby; UniversityofLouisville; emails: p.shafto@louisville.edu, ndg@mit.edu
- **code_url:** 

## Computational level
- **study_focus:** Pedagogical learning / learning from teaching examples — how learners use knowledge that a teacher is purposefully sampling examples to make stronger concept inferences
- **study_focus_short:** Pedagogical learning / learning from teaching examples
- **learning_mode_description:** - Learning mode: Learning from a teacher's purposefully chosen examples about the teacher's intended concept (rectangle)     - Learning from:       - Source type (social): other (teacher)       - Source content (social): action/policy (choice of labeled examples — positive/negative points)     - Learning about:       - Target type (non-social): world (geometric concept — rectangle location/size)       - Target content (non-social): state (world state; concept boundaries)
- **task_description:** In the "rectangle game," a teacher thinks of a rectangle on a board and chooses labeled points (inside = positive, outside = negative) to communicate the concept to a learner, who must infer which rectangle the teacher had in mind. Participants played both teacher and learner roles across trials with varying rectangle sizes and positions.
- **task_paradigm:** Pedagogical learning
- **players:** Single agent (participant) alternating roles as teacher and learner; dyadic (teacher-learner pair, though the "other" agent is implicit/pre-specified in the learning task)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Rectangles on a 2D board, positive (green circle) and negative (red X) point labels
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Teaching task: Positive examples strongly clustered at rectangle corners, not randomly distributed (chi-squared(8) = 645.05, p < 0.0001)   - Teaching task: Negative examples clustered near rectangle boundaries, not randomly distributed (chi-squared(14) = 1268.82, p < 0.0001)   - Teaching task: Strong correlation between pedagogical model predictions and human teaching data for positive examples (r = 0.98)   - Teaching task: Strong correlation between pedagogical model predictions and human teaching data for negative examples (r = 0.86)   - Learning task: Learner inferences consistent with pedagogical sampling for positive examples (r = 0.90) and negative examples (r = 0.87)   - Experiment 2 (control): When data not pedagogically sampled, pedagogical effects disappeared (positive r = 0.27; negative r = 0.23)
- **effect_size:** - r = 0.98 (teaching, positive examples, model-human correlation)   - r = 0.86 (teaching, negative examples, model-human correlation)   - r = 0.90 (learning, positive examples, model-human correlation)   - r = 0.87 (learning, negative examples, model-human correlation)   - r = 0.27 (Exp 2, positive examples, model-human correlation)   - r = 0.23 (Exp 2, negative examples, model-human correlation)
- **learning_from:** other (teacher); teacher's purposefully chosen labeled examples (positive/negative points)
- **learning_about:** world; rectangle concept (location and size of a hidden rectangle)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Bayesian pedagogical sampling model (rational teacher-learner; Luce decision rule with steepness alpha; fixed-point iteration of coupled Eqs. 1 & 2)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - [{"name": "Weak sampling (uniform random)", "family": "Bayesian", "n_params": 0, "metric": "qualitative comparison (correlation)"}]   - [{"name": "Strong sampling (random from true concept)", "family": "Bayesian", "n_params": 0, "metric": "qualitative comparison (correlation)"}]   - [{"name": "Pedagogical sampling", "family": "Bayesian", "n_params": 1, "metric": "qualitative comparison (correlation)"}]
- **model_mb_mf:** Bayesian
- **model_params:** - α (steepness/greediness parameter in Luce decision rule governing teacher's example selection; controls how strongly teacher favors optimal examples; when α = 0 recovers weak sampling; as α grows large teacher chooses best examples)   - p(h) prior over hypotheses (uniform; assumed known)   - Fitted values not reported.
- **social_param:** α — steepness parameter governing how "helpful" (pedagogically optimal) the teacher's example selection is; captures the social assumption that the teacher is acting rationally to help the learner
- **social_param_name:** α
- **social_param_value:** 0
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Qualitative comparison (correlation between model predictions and human data); no formal BIC/AIC comparison reported
- **how_model_fit:** simulate-and-compare (model predictions computed via fixed-point iteration and compared to aggregate human data via correlation)
- **data_type_fit_to:** choice behavior (example placement by teachers; rectangle inferences by learners)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Experiment 1: N = 18 (University of Louisville undergraduates); Experiment 2: N = 29 (University of Louisville undergraduates). Total N = 47.
- **population_category:** undergraduates
- **population_age_range:** 
- **ecological_validity:** Low — abstract geometric concept learning task (rectangle game) with no real social interaction; teacher and learner roles are played by the same participant or against pre-specified examples; limited naturalistic social dynamics.
- **eligibility_flag:** FLAGGED — Borderline on "learning over time" criterion. Each trial involves a single inference from 1-3 examples rather than iterative learning across trials. The model describes rational inference (Bayesian belief updating given examples) rather than trial-by-trial learning with prediction errors or parameter updating over time. This is closer to one-shot inference/concept learning than to learning that unfolds over time. Also: the "social agent" (teacher) is either the participant themselves or implicit — there is no real interactive social partner in the learning condition.
- **concerns:** - No formal model comparison (BIC/AIC/BMS) — models compared only via correlation with aggregate data   - Alpha parameter value not reported; no parameter fitting details   - No individual-level analysis; all results at aggregate level   - The learning task uses pre-chosen examples, not examples from another participant — the "social" aspect is assumed rather than interactive   - Conference proceedings paper (6 pages) — limited methodological detail   - Hypothesis space discretized to 6x6 grid — may introduce boundary artifacts (authors acknowledge this)   - Fixed order of teaching then learning tasks may create demand characteristics
- **limitations_reported:** Authors note: the model's predictions for negative examples in the learning task "does not capture peoples inferences with the strength that people show"; modeling pedagogical reasoning in richer domains is "a significant challenge"; interesting questions arise "when the teacher is uncertain or incorrect about the learner's prior" but are "beyond the scope of this paper
- **limitations_categorized:** limited ecological validity; task simplicity; model misfit for negative examples; limited generalizability to richer domains; no exploration of prior misspecification
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Partial
- **wc_rule10:** No
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - doi: LOW — not reported in paper text   - model_params (fitted values): LOW — alpha value not reported   - how_model_fit: MEDIUM — described as "fixed-point iteration" and correlation comparison, but no formal fitting procedure   - model_comparison_metric: MEDIUM — only correlations used, no formal information criterion   - eligibility_flag: MEDIUM — borderline on temporal learning criterion
- **cannot_find:** - DOI (not in paper text)   - Exact fitted alpha parameter value   - Individual-level model fits   - Formal model comparison statistics (BIC/AIC)   - Supplement (no supplement file found for this conference paper)
- **other_notes:** This is a short (6-page) conference proceedings paper from CogSci 2008. The pedagogical sampling model was later developed into a full journal article (Shafto, Goodman, & Griffiths, 2014, Psychological Review). This paper represents an early formalization of how Bayesian models can capture teaching/learning as coupled inference between rational agents. The model is elegant but the empirical validation is primarily qualitative (correlation-based). No supplement exists — this is typical for CogSci proceedings papers.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_pedagogical_sampling
- spec_context = social
- spec_depth = parametric
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
