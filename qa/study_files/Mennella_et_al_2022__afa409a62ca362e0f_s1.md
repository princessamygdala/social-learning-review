# Mennella et al. (2022)

- **study_id:** `afa409a62ca362e0f_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Mennella, R., Bavard, S., Mentec, I., & Grèzes, J. (2022). Spontaneous instrumental avoidance learning in social contexts. *Scientific Reports*, *12*, 17528. https://doi.org/10.1038/s41598-022-22334-6
- **citation_short:** Mennella et al. (2022)
- **doi:** 10.1038/s41598-022-22334-6
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Psychology
- **affiliations_raw:** Laboratoire des Interactions Cognition, Action, Émotion (LICAÉ), Université Paris Nanterre, 200 Avenue de La; Department of Cognitive Studies, École Normale Supérieure, PSL University, 29 Rue d’Ulm,; Department of Psychology, University of Hamburg, Von-Melle-Park 11, 20146 Hamburg,; ether their aversive motivational value suffices to drive instrumental; ether they can drive instrumental CS-avoidance learning; Laboratory (LNC2),; emails: julie.grezes@ens.psl.eu, rmennella@parisnanterre.fr
- **code_url:** 

## Computational level
- **study_focus:** Social threat avoidance learning -- instrumental CS-avoidance learning driven by the aversive motivational value of angry facial displays, without explicit instruction or monetary incentive.
- **study_focus_short:** Social threat avoidance learning -- instrumental CS-avoidance learning driven
- **learning_mode_description:** - Learning mode: Learning from social threat feedback (approach/avoidance outcomes with angry individuals) about which action maximizes spatial distance from a threatening individual.   - Learning from:     - Source type (social): other (angry individual in waiting room)     - Source content (social): outcome (approach vs. avoidance of angry individual; proximity feedback)   - Learning about:     - Target type (non-social): world (action-outcome contingencies in the environment)     - Target content (non-social): action/policy (which button press maximizes probability of avoiding the angry individual)
- **task_description:** Participants viewed a waiting room scene with two neutral individuals and chose to sit on one of two empty chairs via button press. After their choice, one individual changed expression to angry; one response option had an 80% probability of placing the participant far from (avoidance) the angry individual, with contingencies reversing every ~25 trials.
- **task_paradigm:** Approach-avoidance
- **players:** Single agent (participant), multi-target (10 face pairs; one angry individual per trial)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Photographs of faces (Radboud Faces Database), waiting room scenes, neutral and angry expressions, binary choice (left/right chair), visual analog scale for subjective evaluation
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Hit rate significantly above chance at group level (OR = 1.18, CI 1.14-1.23)   - Hyperbolic increase in hits across trials within blocks (OR = 1.51, CI 1.35-1.70)   - Response repetition increased after avoidance feedback (OR = 1.73, CI 1.56-1.93)   - Subjective value of feedback predicted response repetition (OR = 2.50, CI 2.09-2.98)   - Explicit strategy group showed better learning (OR = 1.25, CI 1.16-1.35)   - Counterfactual model fit better than simple model (Wilcoxon effect size = 0.37)   - Correlation between simulated and real hits: ρ = 0.82 (counterfactual model)   - Subjective value for approach scenarios correlated with learning rate α (ρ = -0.20) and w parameter (ρ = 0.33)   - Explicit strategy group had higher α (median 0.74 vs 0.50; Z = 3411, p = 0.003) and lower w (median 0.63 vs 0.78; Z = 5917, p = 0.001)
- **effect_size:** - Main Results:   - Hit rate significantly above chance at group level (OR = 1.18, CI 1.14-1.23)   - Hyperbolic increase in hits across trials within blocks (OR = 1.51, CI 1.35-1.70)   - Response repetition increased after avoidance feedback (OR = 1.73, CI 1.56-1.93)   - Subjective value of feedback predicted response repetition (OR = 2.50, CI 2.09-2.98)   - Explicit strategy group showed better learning (OR = 1.25, CI 1.16-1.35)   - Counterfactual model fit better than simple model (Wilcoxon effect size = 0.37)   - Correlation between simulated and real hits: ρ = 0.82 (counterfactual model)   - Subjective value for approach scenarios correlated with learning rate α (ρ = -0.20) and w parameter (ρ = 0.33)   - Explicit strategy group had higher α (median 0.74 vs 0.50; Z = 3411, p = 0.003) and lower w (median 0.63 vs 0.78; Z = 5917, p = 0.001)
- **learning_from:** Other (angry individual); social threat feedback (approach/avoidance outcome -- proximity to angry face)
- **learning_about:** World; action-outcome contingencies (which action maximizes spatial distance from threatening individual)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Counterfactual RL with perseverance (4 params: α, α_hab, β, w); Q(c) updated via δ = R - Q(c), unchosen updated via δ_u = (1-R) - Q(u); D = wH + (1-w)Q; softmax choice rule.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Random model", "family": "Random", "n_params": 0, "metric": "log-likelihood"} - {"name": "Simple RL with perseverance", "family": "Rescorla-Wagner", "n_params": 4, "metric": "log-likelihood"} - {"name": "Counterfactual RL with perseverance", "family": "Rescorla-Wagner", "n_params": 4, "metric": "log-likelihood"}
- **model_mb_mf:** MB/MF hybrid (counterfactual updating is model-based-like; perseverance component is model-free-like; authors note counterfactual learning has been compared to model-based learning)
- **model_params:** - α (learning rate): updates Q-value for chosen (and unchosen in counterfactual model). Median: 0.50 (non-explicit group), 0.74 (explicit group) [S -- learns from socially-valenced outcomes] - α_hab (perseverance learning rate): updates habit/perseverance value H. Median: 0.084 (non-explicit), 0.06 (explicit) - β (inverse temperature): governs choice stochasticity in softmax. Median: 1.50 (non-explicit), 1.84 (explicit) - w (weighting parameter): weight between perseverance (H) and instrumental (Q) value; w->1 = perseverance-driven, w->0 = goal-directed. Median: 0.78 (non-explicit), 0.63 (explicit) [S -- relates to sensitivity to social threat approach scenarios]
- **social_param:** α [S] -- learning rate for updating action values based on social threat feedback (approach/avoidance of angry individual); w [S] -- weighting between instrumental value and perseverance, correlated with subjective valuation of social threat approach scenarios (ρ = 0.33, p < 0.001).
- **social_param_name:** α [S]
- **social_param_value:** 0.33
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Log-likelihood; Friedman test followed by Wilcoxon paired tests (Bonferroni corrected); Spearman correlation between simulated and real hit proportions for model validation.
- **how_model_fit:** individual-level-fit (parameter optimization by minimizing negative log-likelihood using Matlab's fmincon, with prior distributions as regularization)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Main experiment: N = 214 (from 278 recruited; 140 female; mean age 34.9, SD 13.2, range 18-75; 60 explicit strategy, 154 non-explicit strategy). Pilot: N = 56 (from 62; 35 female; mean age 28.6, SD 10.7, range 18-61). Online via Prolific.
- **population_category:** healthy adults
- **population_age_range:** 18–75
- **ecological_validity:** The task uses a naturalistic waiting room scenario with realistic face photographs, and learning is spontaneous (no instruction about avoidance or threat), which enhances ecological validity. However, the task is "low-cost" avoidance (button press only, no physical effort or reward loss), limiting generalizability to real-world costly avoidance behaviors. Online administration reduces experimental control.
- **eligibility_flag:** 
- **concerns:** (1) The task is labeled "low-cost" avoidance with no cost to avoiding, limiting relevance to pathological avoidance; (2) A large proportion of participants (n=145/214) did not show significant above-chance learning on average hit proportion, though they still showed feedback-driven response repetition; (3) Subjective evaluation was collected post-hoc in a separate task, not trial-by-trial; (4) No parameter recovery or model recovery analyses reported; (5) No formal model comparison metric (BIC/AIC) -- comparison relies on log-likelihood and Wilcoxon tests; (6) Prior distributions used in fitting but no formal Bayesian framework.
- **limitations_reported:** Large proportion of individuals did not exhibit clear behavioral signs of learning on average throughout the task, limiting generalizability of conclusions concerning spontaneous avoidance learning; absence of strong correlations between affective/personality questionnaires and behavior or model parameters constrains generalizability to pathological social avoidance; task is "low-cost" avoidance requiring only a button press without physical effort or reward loss, limiting ecological validity for pathological avoidance which involves reward omission; cannot fully disentangle whether appetitive (reaching safety) or aversive (escaping threat) motivation drives learning; subjective value estimates collected post-hoc could not capture possible variation of subjective value throughout the main task.
- **limitations_categorized:** Limited generalizability; weak individual difference predictors; limited ecological validity; task simplicity; motivational ambiguity; measurement timing limitations
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_mb_mf: MEDIUM confidence -- authors describe counterfactual learning as akin to model-based learning but do not explicitly classify their model as MB/MF - social_param: MEDIUM confidence -- α and w are not explicitly labeled as "social" parameters by the authors, but they are the key parameters that capture learning from socially-valenced feedback - wc_guidelines rule 3: MEDIUM -- simulations were performed post-fitting for validation, but no pre-fitting simulation/identifiability analysis described
- **cannot_find:** No formal model comparison metric (BIC/AIC/LOOIC) -- only log-likelihood comparisons via non-parametric tests. No parameter recovery. No model recovery/confusion matrix. No pre-registration statement found.
- **other_notes:** This paper reports two studies (pilot N=56, main N=214) but the pilot is explicitly described as a preliminary version of the main experiment with largely replicating results and no subjective evaluation task. The main experiment is the primary study; the pilot serves as replication. Treated as one study (main experiment) with pilot as supporting evidence, consistent with the paper's own framing. Data and code publicly available on OSF. The paper is purely behavioral with no neuroimaging. The counterfactual RL model and the simple RL model have the same number of free parameters (4: α, α_hab, β, w), differing only in whether the unchosen option's value is updated.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_perseveration
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = threat_fear
- tax_rr_topic_threat_fear
- tax_topic_threat_fear
