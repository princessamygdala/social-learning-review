# Kim et al. (2021)

- **study_id:** `acb15cc5b7a80075c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Kim, J., Lee, S. W., Yoon, S., Park, H., & Jeong, B. (2021). Neurocomputational mechanism of controllability inference under a multi-agent setting. *PLoS Computational Biology*, *17*(11), e1009549. https://doi.org/10.1371/journal.pcbi.1009549
- **citation_short:** Kim et al. (2021)
- **doi:** 10.1371/journal.pcbi.1009549
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofBioandBrainEngineering,KoreaAdvancedInstituteofScienceTechnology(KAIST),; InstituteofTechnology,Pasadena,California,UnitedStatesofAmerica,3 KAISTInstitutefor; InstituteofScienceTechnology(KAIST),Daejeon,RepublicofKorea,7 KAISTCenterfor; SchoolofMedicalScienceandEngineering,KoreaAdvancedInstituteforScienceand; labilityperceptionsignificantlyinfluencesmotivatedbehaviorandemotionand; lability,andthisgeneralizedrolerequirestheTPJinadditiontothestriatumof; ethoughtheirownactionsaswellasthingstheycannotchangethroughtheirbehav-; lableifouractionandoutcomearecorrelatedinwhichthecorrelation
- **code_url:** https://github.com/kjj11033/relative_

## Computational level
- **study_focus:** Controllability inference learning — how agents infer their own controllability over outcomes in a multi-agent setting by integrating self and other action-outcome contingencies via Bayesian inference.
- **study_focus_short:** Controllability inference learning
- **learning_mode_description:** - Learning mode: Learning from both one's own and another agent's action-outcome contingencies to infer who controls the shared outcome   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (reward/loss from shared task)     - Source type (social): other (partner/artificial agent)       - Source content (social): outcome (other's action-outcome contingency)   - Learning about:     - Target type (social): self (relative to other)       - Target content (social): state (mental state; controllability belief — who is the causal controller)
- **task_description:** Two participants (actually participant vs. artificial RL agent) simultaneously make binary choices; only one person's choice determines the shared outcome (reward or loss, 80/20 probability). The controller switches every 20-30 trials, and participants must infer who currently controls the outcome using both their own and the other's action-outcome history.
- **task_paradigm:** Joint action / coordination
- **players:** Single agent (participant), dyadic (artificial RL agent presented as another participant)
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract two-alternative choice options, binary feedback (reward/loss), other's choice display
- **method:** fMRI / behavioural
- **method_full:** fMRI (N=30) + behavioural (N=103)
- **main_result:** - Correlated own action-outcome increased perceived controllability (beta = 1.48, t = 11.91) - Correlated other's action-outcome decreased perceived controllability (beta = -1.78, t = -15.04) - Reward biased controllability perception toward self (d = 0.901) - Perceived controllability increased optimal choices (d = 0.481) - Positive bias (bias_pos) significantly > 0 (d = 0.441); negative bias (bias_neg) significantly < 0 (d = -0.495) - Controllability-dependent value utilization parameter tau significantly > 0 (d = 0.854) - Positive bias correlated with illusion of control (r_partial = 0.39) and choice optimality in second half of self-controllable blocks (r_partial = 0.26) - Low positive bias and high negative bias associated with daily guilt (r_partial = 0.27 for bias_neg with guilt; r_partial = -0.25 for bias_pos with guilt) - TPJ and striatum covaried with log-controllability ratio (LCR): left TPJ [-50, -22, 26], Z = 4.37, cluster FWE p = 0.032; right striatum [18, 8, -6], Z = 4.82, cluster FWE p < 0.001 - vmPFC encoded value difference: [0, 52, -12], Z = 5.18, cluster FWE p < 0.001 - vmPFC value signal amplified by predicted controllability: [-2, 34, -14], Z = 4.01, SVC p = 0.012
- **effect_size:** - Reward vs loss controllability perception: d = 0.901 - Perceived controllability on optimal choice: d = 0.481 - Positive bias (bias_pos): d = 0.441 - Negative bias (bias_neg): d = -0.495 - Value utilization (tau): d = 0.854 - Positive bias vs illusion of control: r_partial = 0.39 - Positive bias vs choice optimality (2nd half): r_partial = 0.26 - Negative bias vs guilt: r_partial = 0.27 - Positive bias vs guilt: r_partial = -0.25 - Controllability signal timing striatum: d = 0.702 - Controllability signal timing TPJ: d = 0.486 - vmPFC interaction vs tau: r_partial = 0.38
- **learning_from:** Self and other's action-outcome contingency (both agents' choices and shared outcomes)
- **learning_about:** Self; controllability state (who is the causal controller of the shared outcome)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Multi-Agent Bayesian Controllability (MABC) with reward biases and controllability-guided value utilization (Model 12). Posterior controllability = [exp(bias) * self-likelihood * prior_self] / [exp(bias) * self-likelihood * prior_self + other-likelihood * prior_other]; likelihoods learned via Rescorla-Wagner rule ($\alpha_{self}$, $\alpha_{other}$); value utilization modulated by predicted controllability ($\tau$); drift parameter ($\theta$). 7 free parameters: $\alpha_{self}$, $\alpha_{other}$, $\beta_0$, $\beta_{con}$, bias_{pos}, bias_{neg}, $\tau$, $\theta$.
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** 31 computational models compared. The paper describes model space in S2A Fig. Key models include: - Model 4: Single-agent controllability (self-only, no other-likelihood) - Model 12 (winning): MABC with bias + controllability-induced value utilization (PEP = 1) - Various combinations of: multi-agent vs single-agent, with/without bias, with/without controllability-dependent value utilization, with/without drift  [{"name": "MABC + bias + controllability-value utilization (Model 12)", "family": "Bayesian belief updating + RW", "n_params": 8, "metric": "PEP = 1"}]  Note: Full list of 31 models described in supplementary S2A Fig (not accessible as separate supplement file).
- **model_mb_mf:** Bayesian (not standard RL; Bayesian inference over controllability state with RW likelihood learning)
- **model_params:** - $\alpha_{self}$: learning rate for self action-outcome contingency - $\alpha_{other}$ [S]: learning rate for other's action-outcome contingency - $\beta_0$: baseline inverse temperature for outcome-related choices - $\beta_{con}$: inverse temperature for causality choices - bias_{pos} [S]: reward-driven bias amplifying self-likelihood relative to other-likelihood after reward (mean significantly > 0, d = 0.441) - bias_{neg} [S]: loss-driven bias on self-likelihood relative to other-likelihood after loss (mean significantly < 0, d = -0.495) - $\tau$: controllability-dependent value utilization modulation parameter (mean significantly > 0, d = 0.854) - $\theta$: drift parameter linking trial-to-trial controllability inference to prediction
- **social_param:** bias_{pos} and bias_{neg} — outcome-valence-dependent biases that differentially weight self-likelihood versus other-likelihood in multi-agent controllability inference. $\alpha_{other}$ — learning rate for other's action-outcome contingency.
- **social_param_name:** $\alpha_{other}$
- **social_param_value:** 0.441
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Protected exceedance probability (PEP) from random-effects Bayesian model selection (RFX-BMS) using negative variational free energy (Laplace approximation of log model evidence).
- **how_model_fit:** individual-level-fit (variational Bayesian scheme via TAPAS toolbox; MAP estimation with quasi-Newton optimization)
- **data_type_fit_to:** choice behavior (both outcome-related choices and causality choices jointly)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — GLM with parametric modulators derived from winning MABC model (LCR, VD, predicted controllability, RPE, and interactions)
- **contrast:** - GLM1: Log-controllability ratio (LCR) at 1s post-outcome (multi-agent controllability inference signal) - GLM1: Value difference (VD) at cue onset - GLM1: Predicted controllability x VD interaction at cue onset (controllability-dependent value utilization) - GLM1: Self reward prediction error at outcome onset - GLM2: Single-agent LCR at 1s post-outcome (for Bayesian model selection vs GLM1) - GLM3: Self-likelihood and other-likelihood as parametric modulators at 1s post-outcome
- **key_regions:** Multi-agent controllability inference in left TPJ and right striatum; value utilization in vmPFC; controllability-amplified value signal in vmPFC; other-likelihood detection in right MTG; self-likelihood in vmPFC, ventral striatum, hippocampus. Granger causality from TPJ to striatum. Mediation: reward -> TPJ/striatum -> vmPFC (next trial).
- **key_regions_abbrev:** VS, striatum, vmPFC, mPFC, TPJ, hippocampus
- **coordinates_peak:** GLM1 — LCR (multi-agent controllability): - Left TPJ: -50, -22, 26 (Z = 4.37, cluster FWE p = 0.032) - Right striatum: 18, 8, -6 (Z = 4.82, cluster FWE p < 0.001)  GLM1 — Value difference (VD) at cue: - vmPFC: 0, 52, -12 (Z = 5.18, cluster FWE p < 0.001)  GLM1 — Predicted controllability x VD interaction: - vmPFC: -2, 34, -14 (Z = 4.01, SVC p = 0.012)  GLM3 — Negative other-likelihood: - Right MTG: 56, -22, -8 (Z = 4.53, cluster FWE p = 0.035)  GLM3 — Self-likelihood: - vmPFC, ventral striatum, hippocampus (coordinates reported in S3 Table and S6 Fig — supplement not separately accessible; flagged)
- **analysis_type:** both (whole-brain with cluster-level FWE correction + ROI/SVC for vmPFC interaction)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 103 (behavioural; 32 females, mean age 23.8 +/- 2.7 years); N = 30 (fMRI subsample; 8 females, mean age 24.0 +/- 2.7 years)
- **population_category:** healthy adults
- **population_age_range:** M=23.8
- **ecological_validity:** Limited — participants believed they played with a real partner but actually interacted with an artificial RL agent; binary choice task with simple reward/loss outcomes; controllability structure (only one person controls) is simplified relative to real-world multi-agent settings where cooperative or partial control is common.
- **eligibility_flag:** 
- **concerns:** - Participants interacted with an artificial RL agent, not a real person (deception paradigm; flagged as automated social agent) - Both task sets started with a self-controllable block, potentially creating order effects (acknowledged by authors) - fMRI subsample relatively small (N=30) - Granger causality analysis has limitations for inferring effective connectivity (acknowledged by authors) - Supplement tables (S1, S2, S3) referenced for full coordinates and model parameters but supplement file not separately available as text — some coordinate details from S3 Table and S6 Fig could not be verified
- **limitations_reported:** Task assumes only one person controls outcome, whereas real-world situations involve cooperative or no-control scenarios; both task sets started with self-controllable block creating potential blocking effect; Granger causality does not establish effective connectivity; model may be unrealistic with large numbers of agents (>10) because it assumes simultaneous updating of all agents' contingencies; study design does not distinguish whether guilt arises from causing loss to other vs. to self.
- **limitations_categorized:** task simplicity; limited ecological validity; order effects; limited generalizability (model scalability); method limitations (Granger causality); design confound (guilt attribution ambiguity)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9.5
- **wc_total:** 9.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - coordinates_peak (self-likelihood regions): MEDIUM confidence — vmPFC, ventral striatum, hippocampus coordinates referenced in S3 Table/S6 Fig but supplement not accessible as separate text file; main text mentions these regions but does not provide exact coordinates - all_models_tested: MEDIUM confidence — full list of 31 models described in supplementary S2A Fig; only key models described in main text - n_params for winning model: MEDIUM confidence — text describes 8 free parameters ($\alpha_{self}$, $\alpha_{other}$, $\beta_0$, $\beta_{con}$, bias_{pos}, bias_{neg}, $\tau$, $\theta$) but supplement table may clarify if any are fixed
- **cannot_find:** - Exact coordinates for self-likelihood regions (vmPFC, ventral striatum, hippocampus from GLM3) — in S3 Table/S6 Fig, supplement not separately accessible - Full list of all 31 model names/specifications — in S2A Fig, supplement not separately accessible - Mean fitted parameter values for all parameters — S1 Table (DOCX supplement) referenced but not accessible - Prior distributions for model parameters — referenced in S1 Table
- **other_notes:** - The "other" agent is actually an artificial RL agent (learning rate = 0.3, inverse temperature = 1.5, Rescorla-Wagner rule) — participants were deceived into believing they played with another person. This should be flagged as an automated social agent. - Data and code publicly available on GitHub. - The MABC model generalizes to >2 agents (described in S1 Text). - Neural Bayesian model selection between multi-agent (MABC) and single-agent controllability models showed PEP = 1 for MABC in both TPJ and striatum, validating the multi-agent account at the neural level. - Mediation analyses showed reward -> TPJ/striatum activity -> vmPFC activity (next trial), linking controllability inference to value utilization. - Individual differences in bias parameters related to guilt proneness (TOSCA-3 scores).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = partly
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_bayesian
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_social_weight
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = self_other_boundary
- tax_rr_secondary_topic = social_uncertainty
- tax_rr_topic_self_other_boundary
- tax_rr_topic_social_uncertainty
- tax_topic_self_other_boundary
- tax_topic_social_uncertainty
