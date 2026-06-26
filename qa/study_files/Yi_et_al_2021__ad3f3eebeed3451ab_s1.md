# Yi et al. (2021)

- **study_id:** `ad3f3eebeed3451ab_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Yi, J., Pärnamets, P., & Olsson, A. (2021). The face value of feedback: facial behaviour is shaped by goals and punishments during interaction with dynamic faces. *Royal Society Open Science*, *8*, 202159. https://doi.org/10.1098/rsos.202159
- **citation_short:** Yi et al. (2021)
- **doi:** 10.1098/rsos.202159
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ethod based on online integration of electromyography (EMG) signals from the participants’; DepartmentofClinicalNeuroscience,DivisionofPsychology,KarolinskaInstitutet,Solna,Sweden; Department ofPsychology, NewYork University, NewYork, NY, USA; ethod to study learning and decision-making in facial; ethod based on online integration of; ethetemporaldimensionof; ethelargebodyofworkon; ethod,; emails: jonathan.yi@ki.se
- **code_url:** https://osf.io/f7edp/

## Computational level
- **study_focus:** Avoidance learning of facial expression selection during dyadic interaction with dynamic faces; learning to optimize goal-directed facial responses (smile/frown) to avoid aversive outcomes as a function of congruency and target expression.
- **study_focus_short:** Avoidance learning of facial expression selection during dyadic interaction
- **learning_mode_description:** - Learning mode: Learning from aversive feedback (electric shock) about which facial expression to produce toward a specific target interactant   - Learning from:     - Source type (non-social): world       - Reinforcement signal is electric shock (aversive stimulation), a non-social outcome     - Source content (non-social): outcome       - Binary outcome: shock vs. no shock   - Learning about:     - Target type (social): other (target interactant)       - Which facial response is correct for each specific target interactant     - Target content (social): action/policy       - Whether to copy or not copy the target interactant's facial expression
- **task_description:** Participants viewed dynamic videos of two target interactants forming smiles or frowns and learned through trial-and-error to produce the correct facial expression (measured via EMG biofeedback from corrugator supercilii and zygomaticus major) to avoid mild electric shock; contingencies reversed halfway through the 96-trial experiment.
- **task_paradigm:** Approach-avoidance
- **players:** Single agent (participant), multi-target (2 target interactants, sex-matched to participant)
- **n_players:** multi-target (3+)
- **partner_type:** human (live)
- **stimuli:** Dynamic face videos (ADFES), happy and angry expressions, EMG-based biofeedback, mild electric shock
- **method:** behavioural
- **method_full:** behavioural (EMG biofeedback)
- **main_result:** - Main effects of Congruency (B = 2.60, s.e. = 0.30, p < 0.001) and Expression (B = 1.37, s.e. = 0.12, p < 0.01) on correct responses - Congruency x Reversal interaction on correct responses (B = 0.57, s.e. = 0.21, p < 0.01) - Drift rate magnitude greater for congruent vs. incongruent trials (posterior difference M = 0.77, 95% CrI = [0.30, 1.24], >99.9% posterior mass positive) - Boundary separation greater for congruent vs. incongruent (M = 0.32, 95% CrI = [0.16, 0.49], >99.9% posterior positive) - Boundary separation lower for smiling vs. frowning target (M = -0.22, 95% CrI = [-0.38, -0.06], 99.6% posterior negative) - RL copy-bias parameter positive (M = 0.50, 95% CrI = [0.35, 0.66]) - Negative correlation between STAI-T and learning rate (r = -0.28, 95% CI = [-0.51, -0.01], p = 0.04)
- **effect_size:** - Congruency effect on CR: B = 2.60 (logistic mixed model) - Expression effect on CR: B = 1.37 - Drift rate congruency contrast: posterior M = 0.77, 95% CrI = [0.30, 1.24] - Boundary separation congruency contrast: posterior M = 0.32, 95% CrI = [0.16, 0.49] - Boundary separation expression contrast: posterior M = -0.22, 95% CrI = [-0.38, -0.06] - Copy-bias (zeta): M = 0.50, 95% CrI = [0.35, 0.66] - STAI-T and learning rate correlation: r = -0.28
- **learning_from:** World; aversive outcome (electric shock or no shock) contingent on facial expression choice. Source: world.
- **learning_about:** Other (target interactant); whether to copy or not copy their facial expression. Target: other.  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Q-learning with Rescorla-Wagner update rule, copy-bias (α, β, ζ); also DDM with drift rate, boundary separation, starting point bias varying by condition
- **model_family:** Drift-diffusion
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Q-learning with copy-bias (winning)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "model comparison (MCMC, details in electronic supplementary material Table 21)"},   {"name": "Q-learning without copy-bias", "family": "Rescorla-Wagner", "n_params": 2, "metric": "same"},   {"name": "Q-learning with prior bias (decaying)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "same"},   {"name": "Q-learning with expression-dependent learning rates", "family": "Rescorla-Wagner", "n_params": 4, "metric": "same"},   {"name": "Q-learning with expression-dependent copy-bias", "family": "Rescorla-Wagner", "n_params": 4, "metric": "same"},   {"name": "Hierarchical Wiener diffusion model", "family": "Drift diffusion", "n_params": "multiple (drift, boundary, bias varying by condition)", "metric": "Bayesian estimation (brms)"} ]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): constrained [0, 1]; population posterior shown in Figure 8c - β (temperature/inverse temperature): constrained (0, 2); population posterior shown in Figure 8b - ζ (copy-bias) [S]: unconstrained; M = 0.50, 95% CrI = [0.35, 0.66] — positive values indicate bias toward copying target interactant's expression - DDM parameters: V (drift rate), boundary separation, Z (starting point bias) — all varying by Expression x Congruency condition
- **social_param:** ζ (copy-bias): captures the tendency to copy (mimic) the facial expression of the target interactant; positive values indicate a bias toward facial mimicry
- **social_param_name:** ζ
- **social_param_value:** 0.50
- **social_param_sd:** 
- **social_param_range:** 0.35–0.66
- **model_comparison_metric:** Model comparison conducted via hierarchical Bayesian MCMC fitting in Stan; winning model "decisively outcompeted" alternative without bias term and prior-bias model; comparison was "inconclusive" against expression-dependent variants, so simpler model preferred for parsimony. Full comparison in electronic supplementary material, Table 21 (not accessible locally).
- **how_model_fit:** individual-level-fit (hierarchical Bayesian; individual parameters as deviations from population average)
- **data_type_fit_to:** choice behavior (correct response / copy vs. not-copy); response times (for DDM)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 58 (29 female; mean age = 26.4, SD = 4.3); recruited 71, 13 excluded due to low EMG signals
- **population_category:** healthy adults
- **population_age_range:** M=26.4
- **ecological_validity:** Novel EMG biofeedback method simulates real-time facial expression exchange, improving ecological validity over static face paradigms; however, paradigm is simplified to 2AFC and uses pre-recorded videos rather than truly interactive partners; participants interact with video stimuli, not live people
- **eligibility_flag:** 
- **concerns:** (1) The electronic supplementary material (hosted on figshare) containing the full model comparison table (Table S21), alternative model specifications, and DDM priors was not accessible in the local files; the "Supplements" file available is the review history, not the actual supplementary materials. (2) Exact model comparison metric values (e.g., LOOIC/WAIC/BIC differences) are not reported in the main text. (3) The modelling was described by the authors as "primarily exploratory and secondary to the main goal" of establishing the method. (4) No parameter recovery or model recovery reported. (5) Correlation between STAI-T and learning rate (r = -0.28) contradicts the mixed model finding of higher CR with higher STAI-T, which the authors acknowledge.
- **limitations_reported:** We limited our investigation to the exchange of two transient emotional expressions: smiles and frowns"; "The reality of social interaction is no doubt far more complex than our paradigm affords, and our experimental paradigm therefore suffers from a limited generalizability"; "it remains to be determined whether our method can be generalized to multiple-alternative forced choice (mAFC) tasks or tasks where participants can freely choose which facial expression to form"; "our study did not confirm whether the learning processes in this study were specific to facial expression recognition and mimicry or domain general in nature"; "the limited sample size of our study precluded us from drawing any general conclusions about these traits [individual differences]"; "since our analyses of individual difference measures might be underpowered, we are hesitant to draw any firm conclusion
- **limitations_categorized:** limited ecological validity; task simplicity (2AFC); limited generalizability; domain-specificity unclear; sample size (underpowered for individual differences); limited stimulus diversity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
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
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `all_models_tested`: MEDIUM confidence — alternative models described qualitatively in main text but full specifications are in inaccessible electronic supplementary material (pp. 9-10) - `model_comparison_metric`: LOW confidence — exact metric name (e.g., LOOIC, WAIC) not stated in main text; only "decisively outcompeted" and "inconclusive" language used; Table S21 not accessible - `wc_guidelines` Rule 3 (simulate): MEDIUM confidence — no simulation described in main text; could be in inaccessible supplement - `model_params` (fitted values for α and β): MEDIUM confidence — posterior distributions shown graphically (Figure 8b,c) but exact population mean values not reported numerically in text
- **cannot_find:** - Exact model comparison metric values (LOOIC, WAIC, BIC, or other) — referenced only as "Table 21" in electronic supplementary material (not accessible locally) - Exact fitted population mean values for α (learning rate) and β (temperature) — only shown as histograms in Figure 8 - Full specifications of alternative RL models — described as in electronic supplementary material pp. 9-10 (not accessible locally) - DDM prior specifications — referenced as in electronic supplementary material p. 8 (not accessible locally)
- **other_notes:** The locally available "Supplements" .txt file is actually the peer review history (reviewer comments, editorial decisions, and author responses), not the scientific supplementary material. The actual electronic supplementary material is hosted externally at figshare (https://doi.org/10.6084/m9.figshare.c.5506698). This means model comparison details, alternative model specifications, DDM priors, and several supplementary tables (S1-S21) referenced in the paper could not be verified. The paper presents two complementary modeling approaches (RL and DDM) but treats them as exploratory, secondary analyses.
- **re_extract_flag:** true (electronic supplementary material not accessible locally; model comparison details, alternative model specifications, and several supplementary tables could not be verified)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_MF
- tax_model_drift_diffusion
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_drift_diffusion
- tax_rr_model_family = drift_diffusion
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = threat_fear
- tax_rr_topic_threat_fear
- tax_topic_threat_fear
