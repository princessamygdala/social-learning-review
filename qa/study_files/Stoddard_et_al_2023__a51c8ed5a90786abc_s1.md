# Stoddard et al. (2023)

- **study_id:** `a51c8ed5a90786abc_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Stoddard, J., Haller, S. P., Costa, V., Brotman, M. A., & Jones, M. (2023). A computational model reveals learning dynamics during interpretation bias training with clinical applications. *Biological Psychiatry: Cognitive Neuroscience and Neuroimaging*, *8*(10), 1033–1040. https://doi.org/10.1016/j.bpsc.2023.03.013
- **citation_short:** Stoddard et al. (2023)
- **doi:** 10.1016/j.bpsc.2023.03.013
- **publication_type:** peer-reviewed journal---
- **year:** 2023.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** ETHODS: A predominantly clinical sample comprised 71 youths (age range, 8–22 years) representing broad; etheoriessuggestthatthesebiasesmaintainapath- individualsareencouragedtochangetheiremotionalvalence; ethatisamenabletoacloseexaminationofits with feedback and to discriminate between differing facial; ethesecontributions amount of training trials people typically require to shift their; label of an ambiguous facial expression from negative to
- **code_url:** 

## Computational level
- **study_focus:** Interpretation bias learning — learning to shift categorical judgments of ambiguous face emotions from negative (angry) to positive (happy) through reinforcement feedback, and its association with affective psychopathology (irritability, anxiety) in youth.
- **study_focus_short:** Interpretation bias learning
- **learning_mode_description:** - Learning mode: Learning from corrective feedback on one's own categorical judgments of ambiguous face emotions to update stimulus-valence associations   - Learning from:     - Source type (non-social): self (own judgments + external feedback)     - Source content (non-social): outcome (corrective feedback: "Right!/Wrong!")   - Learning about:     - Target type (social): other (face emotion stimuli — social stimuli depicting emotional expressions)     - Target content (social): stimulus (categorical valence of ambiguous facial expressions — happy vs. angry)
- **task_description:** Youths made forced-choice happy/angry judgments of 15 morphed facial expressions on a continuum from happy to angry; after an initial assessment block, they received corrective feedback across six training blocks encouraging categorization of ambiguous faces as "happy," followed by a post-training assessment block without feedback.
- **task_paradigm:** Categorization task
- **players:** Single agent (participant), no interactive partner (stimuli are static morphed face images).
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Morphed face emotion stimuli (composite happy-angry morph continuum from Karolinska Directed Emotional Faces), binary corrective feedback ("Right!/Wrong! That face was happy/angry.")
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Model predicted posttraining indifference point associated with actual posttraining indifference point (r_60 = 0.62, p < .01)   - Age negatively associated with generalization (r_61 = −0.32, p = .01)   - Negative affectivity (shared variance of anxiety + irritability) negatively associated with learning rate (β = −0.11, SE = 0.052, p < .05)   - Anxiety positively associated with learning rate after partialing out negative affectivity (β = 0.16, SE = 0.053, p < .01)   - Parent-reported irritability positively associated with learning rate after partialing out negative affectivity (β = 0.14, SE = 0.068, p < .05)   - Self-reported irritability positively associated with learning rate after partialing out negative affectivity (β = 0.13, SE = 0.060, p < .05)   - Overall regression R² for learning rate model = 0.18; F(4,49) = 2.8, p < .05   - Overall regression R² for generalization model = 0.11; F(4,49) = 1.6, n.s.   - Two-class Gaussian mixture model best fit (BIC = 518.9, entropy = 0.948, Lo-Mendell-Rubin p = .0003): high-generalization group (n = 20, mean σ = 13.88, mean ε_eff_thr = 0.14) vs. variable-learning group (n = 43, mean σ = 3.40, mean ε_eff_thr = 0.22)   - High-generalization group younger than variable-learning group (mean age 13.3 vs. 15.3 years, t_47.6 = 2.67, p = .011)
- **effect_size:** - Main Results:   - Model predicted posttraining indifference point associated with actual posttraining indifference point (r_60 = 0.62, p < .01)   - Age negatively associated with generalization (r_61 = −0.32, p = .01)   - Negative affectivity (shared variance of anxiety + irritability) negatively associated with learning rate (β = −0.11, SE = 0.052, p < .05)   - Anxiety positively associated with learning rate after partialing out negative affectivity (β = 0.16, SE = 0.053, p < .01)   - Parent-reported irritability positively associated with learning rate after partialing out negative affectivity (β = 0.14, SE = 0.068, p < .05)   - Self-reported irritability positively associated with learning rate after partialing out negative affectivity (β = 0.13, SE = 0.060, p < .05)   - Overall regression R² for learning rate model = 0.18; F(4,49) = 2.8, p < .05   - Overall regression R² for generalization model = 0.11; F(4,49) = 1.6, n.s.   - Two-class Gaussian mixture model best fit (BIC = 518.9, entropy = 0.948, Lo-Mendell-Rubin p = .0003): high-generalization group (n = 20, mean σ = 13.88, mean ε_eff_thr = 0.14) vs. variable-learning group (n = 43, mean σ = 3.40, mean ε_eff_thr = 0.22)   - High-generalization group younger than variable-learning group (mean age 13.3 vs. 15.3 years, t_47.6 = 2.67, p = .011)
- **learning_from:** Self; own categorical judgments and corrective feedback from task ("Right!/Wrong!").
- **learning_about:** Social stimuli — categorical valence (happy vs. angry) of ambiguous facial expressions.---  ## ALGORITHMIC LEVEL
- **outcome_modality:** face_expression

## Algorithmic level
- **winning_model:** ALCOVE (attention learning covering map) — modified for IBT: 7 free parameters (ε_eff_max, σ, θ, g_A, g_H, s, p). Connectionist model with Gaussian similarity-based generalization, Rescorla-Wagner error-driven weight updates, and modified Softmax choice rule with asymmetric guessing parameters.
- **model_family:** Connectionist (SUSTAIN/ALCOVE)
- **model_class:** PE learning
- **all_models_tested:** Variant testing in development sample (n = 28): 1. Softmax only (no guessing) — Sum -LL = 1915.4, 5 params 2. Softmax + symmetric guessing (g) — Sum -LL = 1885.6, 6 params; χ²(28) = 59.7, p < .001 vs. model 1 3. Softmax + asymmetric guessing (g_A, g_H) — Sum -LL = 1863.5, 7 params; χ²(28) = 44.2, p = .006 vs. model 2 (WINNING) 4. Logistic initial weights variant — Sum -LL = 1871.0, 7 params; χ²(0) = 15.2, p < .001 worse than linear initial weights
- **model_mb_mf:** N/A (not RL in the traditional MB/MF sense; this is a category learning model with error-driven weight updating)
- **model_params:** - ε_eff_max: Maximum effective learning rate (mean = 0.21, median = 0.10; recovery r = 0.76) - σ: Generalization (standard deviation of Gaussian activation profile, in morph units; mean = 6.73, median = 5.04; recovery r = 0.76) - θ: Inverse temperature (mean = 4.49, median = 2.72; recovery r = 0.45) - g_A: Guessing parameter for angry end (mean = 0.060, median = 0.038; recovery r = 0.77) - g_H: Guessing parameter for happy end (mean = 0.053, median = 0.018; recovery r = 0.88) - s: Initial weight matrix slope (mean = 0.30, median = 0.18; recovery r = 0.59) - p: Initial weight matrix indifference point (mean = 7.63, median = 7.89; recovery r = 0.66)  (HIGH — all from Table 2)
- **social_param:** MEDIUM — no parameter is explicitly social; σ governs generalization across face morphs but is not inherently social
- **social_param_name:** MEDIUM
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Log-likelihood ratio test (χ² on sum of log-likelihoods), BIC for mixture model class selection.
- **how_model_fit:** Individual-level fit; maximum likelihood estimation via fmincon in MATLAB with 500 random starts per participant.
- **data_type_fit_to:** Choice behavior (binary happy/angry categorical judgments, trial-by-trial).---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A — no neuroimaging in this study.
- **key_regions:** N/A — no neuroimaging.
- **coordinates_peak:** N/A — no neuroimaging.
- **analysis_type:** N/A (no neuroimaging)---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 71 total recruited; N = 63 with acceptable data for computational modeling (8 excluded for poor performance); of 63, N = 54 had symptom dimension scores for regression analyses. Age range 8–22 years, mean 14.68 (SD 3.23); 44% female. Clinical sample: 21 DMDD, 16 ADHD, 9 anxiety disorders, 17 no major psychopathology. Development/validation sample: N = 28 youths with DMDD.
- **population_category:** clinical
- **population_age_range:** 8–22
- **ecological_validity:** Low — artificial lab task with morphed composite face stimuli on a single happy-angry continuum; forced binary choice; corrective feedback is experimenter-determined rather than naturally occurring social feedback. Single training session only. Participants had completed an fMRI task with similar stimuli days before, which may have affected engagement.
- **eligibility_flag:** MEDIUM — borderline social learning; the task uses social stimuli (face emotions) but the learning process itself is category learning from computer-generated feedback, not learning from or about social agents
- **concerns:** - The "social" component is limited to the stimuli being face emotions; there is no social interaction, social agent, or learning about another person's mental states/traits/behavior - Modest sample size (N = 63 for modeling, N = 54 for regressions) - Parameter recovery for inverse temperature θ is relatively poor (r = 0.45) - No cross-validation or out-of-sample prediction beyond the held-out block 8 - Prior fMRI session with same stimuli may have affected task engagement - Development and test samples differ (DMDD-only vs. mixed clinical)
- **limitations_reported:** Limitations of this experiment are the modestly sized sample of children and adolescents who have known difficulty with general task engagement"; "these participants completed a functional magnetic resonance imaging task using these stimuli a few days before this experiment, which may have affected engagement"; "this study may be vulnerable to type II error in detecting associations between model-based measures of learning and psychopathology"; "another limitation of the current model build is the requirement of learning to segregate cognitive processes to determine expected valence apart from other sources affecting response probabilities modeled by the choice rule"; "this work assesses only concurrent clinical associations and not the associations between learning dynamics and clinical response to IBT."
- **limitations_categorized:** Sample size; task engagement concerns; potential type II error; model simplification (does not integrate reaction times); cross-sectional design (no longitudinal treatment outcome data); prior exposure to stimuli.
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.5
- **wc_total:** 8.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_anxiety
- pop_children
- rr_pop_adolescents
- rr_pop_anxiety
- rr_pop_children
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MB
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_clinical
- tax_popclass_developmental
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_connectionist_category
- tax_rr_model_family = connectionist_category
- tax_rr_param_learning_rate
- tax_rr_primary_topic = emotion_inference
- tax_rr_topic_emotion_inference
- tax_topic_emotion_inference
