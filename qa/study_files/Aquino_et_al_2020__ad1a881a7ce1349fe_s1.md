# Aquino et al. (2020)

- **study_id:** `ad1a881a7ce1349fe_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Aquino, T. G., Minxha, J., Dunne, S., Ross, I. B., Mamelak, A. N., Rutishauser, U., & O'Doherty, J. P. (2020). Value-related neuronal responses in the human amygdala during observational learning. *The Journal of Neuroscience*, *40*(24), 4761–4772. https://doi.org/10.1523/JNEUROSCI.2897-19.2020
- **citation_short:** Aquino et al. (2020)
- **doi:** 10.1523/JNEUROSCI.2897-19.2020
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Institutes of Health Grants R01DA040011 and R01MH111425 amygdala as well as elsewhere in the brain, which tracks the; DepartmentofNeurosurgery,Cedars-SinaiMedicalCenter,Pasadena,CA90048,and3DepartmentofNeurosurgery,HuntingtonMemorial; ether human amygdala neurons are involved inthe computations necessary to implement learningthrough observation; DivisionofBiologyandBiologicalEngineering,CaliforniaInstituteofTechnology,Pasadena,CA91125,; depthelectrodesperformedanobservationallearning(OL)task; ethefirstdraftofthepaper;T; Hospital,Pasadena,CA91105; ethods(Minxhaetal; emails: Correspondenceshould
- **code_url:** 

## Computational level
- **study_focus:** Observational learning — investigating whether human amygdala neurons encode reinforcement learning variables (expected values, outcomes, prediction errors) during learning through observation of another agent's experiences.
- **study_focus_short:** Observational learning
- **learning_mode_description:** - Learning mode: Learning the value of stimuli by observing outcomes experienced by another agent interacting with those stimuli (vicarious/observational reinforcement learning)   - Learning from:     - Source type (social): other (observed agent in pre-recorded video)     - Source content (non-social): outcome (reward points received by observed agent)   - Learning about:     - Target type (non-social): world (stimulus/bandit reward value)     - Target content (non-social): stimulus (expected value of bandits/stimuli)
- **task_description:** Neurosurgical patients performed a multi-armed bandit task with 288 trials across interleaved experiential and observational blocks; in observational blocks, participants watched a pre-recorded video of another person experiencing outcomes from bandits (whose rewards were not added to the participant's total), then made binary choices between bandits to test learned values.
- **task_paradigm:** Multi-armed bandit
- **players:** Single agent (neurosurgical patient), single observed target (pre-recorded video of another person)
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Colored one-armed bandits (slot machines), point outcomes drawn from normal distributions (truncated at -50 and 150), pre-recorded video of another player's head watching bandit outcomes
- **method:** other
- **method_full:** Single-neuron electrophysiology (intracranial recordings from amygdala via hybrid depth electrodes)
- **main_result:** - Counterfactual RL model with single learning rate best explained behavior (protected exceedance probability = 99.9% over split-LR counterfactual model) - No significant difference between experiential and observational choice accuracy (p = 0.66, two-sample t-test; overall proportion correct = 0.776 +/- 0.038) - 9.4% of amygdala neurons sensitive to experiential EV (p < 0.006, permutation test) - 8.9% of amygdala neurons sensitive to observational EV (p < 0.002, permutation test) - 10.8% of amygdala neurons sensitive to experiential outcomes (p < 0.002, permutation test) - Trial type (experiential vs. observational) decoded from amygdala population at 86.1% accuracy (p < 0.002) - Experiential EV decoded at 36.4% (p < 0.002); observational EV decoding not significant (p < 0.08) - Experiential outcome decoded at 39.3% (p < 0.002); observational outcome decoded at 33.1% (p < 0.026) - Cross-condition generalization decoding failed in both directions, and Pearson correlations between experiential and observational sensitivities were non-significant (EV: r = 0.10, p = 0.14; outcome: r = 0.02, p = 0.77), suggesting distinct neuronal populations for observational vs. experiential value coding
- **effect_size:** - Experiential EV unit proportion: 9.4% (19/202 neurons) - Observational EV unit proportion: 8.9% (18/202 neurons) - Experiential outcome unit proportion: 10.8% (22/202 neurons) - Observational outcome unit proportion: 4.9% (10/202 neurons) - Trial type decoding accuracy: 86.1% - Experiential EV decoding accuracy: 36.4% - Observational outcome decoding accuracy: 33.1% - EV cross-condition sensitivity correlation: r = 0.10 - Outcome cross-condition sensitivity correlation: r = 0.02
- **learning_from:** Other (observed agent); reward outcomes experienced by observed agent on bandits
- **learning_about:** World; expected value of stimuli (bandits)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RL counterfactual (single $\alpha$, 1 $\beta$): both played and unplayed bandits updated on each trial in opposite directions. $V_{chosen}^{t+1} = V_{chosen}^t + \alpha \delta_t$; $V_{unchosen}^{t+1} = V_{unchosen}^t - \alpha \delta_t$; $\delta_t = R_t - V_i^t$
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "RL (no split)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "Protected exceedance probability (HBI)"},   {"name": "RL (split)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "Protected exceedance probability (HBI)"},   {"name": "RL (counterfactual)", "family": "Rescorla-Wagner (counterfactual)", "n_params": 2, "metric": "Protected exceedance probability (HBI)"},   {"name": "HMM", "family": "Hidden Markov Model", "n_params": 3, "metric": "Protected exceedance probability (HBI)"} ]
- **model_mb_mf:** MF
- **model_params:** - $\alpha$ (learning rate, single for experiential and observational): mean = 0.31 +/- 0.06, constrained (0, 1) - $\beta$ (softmax inverse temperature): mean = 0.17 +/- 0.35, constrained (0, 10)
- **social_param:** None — the winning model uses a single learning rate for both experiential and observational trials; no separate social parameter. The model comparison explicitly showed the single-LR counterfactual model outperformed the split-LR version (99.9% protected exceedance probability), suggesting no distinct social learning rate is needed.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Protected exceedance probability via Hierarchical Bayesian Inference (HBI; Piray et al., 2019), which simultaneously performs hierarchical model fitting and model comparison, accounting for the possibility that none of the compared models is supported by the data.
- **how_model_fit:** individual-level-fit (hierarchical Bayesian inference framework providing individualized model parameters for each subject)
- **data_type_fit_to:** choice behavior (binary choices in free-choice trials)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (single-neuron electrophysiology, not fMRI)
- **contrast:** - Single-neuron encoding: Kruskal-Wallis test of spike counts binned in time windows vs. quantiles of EV, outcome, RPE, and trial type - Population decoding: Maximum Pearson correlation classifier on pseudopopulation of 202 amygdala neurons, decoding EV (pre-outcome), outcome (post-outcome), RPE (post-outcome), and trial type (whole trial) - Cross-condition generalization: Train decoder on experiential, test on observational (and vice versa) for EV and outcome
- **key_regions:** Amygdala — single-neuron recordings revealed distinct subsets of neurons encoding expected value during both observational and experiential learning; outcome signals decodable from amygdala population in both conditions; no evidence of lateralization or subnuclei specialization (BL, CM, remaining nuclei). Cross-condition generalization analysis showed distinct (non-overlapping) neuronal populations for observational vs. experiential value coding.
- **key_regions_abbrev:** AI, amygdala
- **coordinates_peak:** unavailable — single-neuron recordings from amygdala via implanted depth electrodes; electrode locations registered to CIT168 template brain in MNI152 coordinates, but no peak MNI coordinates reported for specific effects. Subnuclei breakdown: 117 units in basolateral (BL), 39 in corticomedial (CM), 46 in remaining nuclei.
- **analysis_type:** N/A (single-neuron electrophysiology, not neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 12 patients (4 female), neurosurgical epilepsy patients with depth electrodes; 4 patients performed 2 sessions, others 1 session; 14 analyzed sessions (1 pilot excluded, 1 discarded for technical error); 202 single units isolated from amygdala (135 right, 67 left)
- **population_category:** clinical
- **population_age_range:** 
- **ecological_validity:** Low ecological validity — observational learning from a pre-recorded video of a stranger's head (not live interaction); Pavlovian paradigm with instrumental choice trials only to test contingency learning; performed in hospital setting with neurosurgical epilepsy patients; authors note the design does not control for social vs. non-social component of OL (the observed agent could be replaced by a computer).
- **eligibility_flag:** 
- **concerns:** - Very small sample size (N = 12 patients, 14 sessions) — typical of intracranial single-neuron studies but limits generalizability - Epilepsy patient population may not be representative of healthy cognition - The pre-recorded video agent is passive (not a live social partner), limiting social dimension - Design does not disentangle social vs. non-social components of observational learning (acknowledged by authors) - Blocked design (experiential vs. observational blocks) confounds trial type decoding with block-level differences - Observed agent rewards not added to participant total — no interdependence between agents - RPE was not significantly encoded or decoded in amygdala, despite being a core RL variable - Low inverse temperature parameter ($\beta$ = 0.17) suggests noisy decision-making
- **limitations_reported:** Our design does not control for the social versus non-social learning component of OL"; "One important caveat is that proportions of sensitive amygdala neurons for value related variables have been lower in the present study than in the monkey literature"; "Unlike in animal studies, our participants performed the task for ~1 h with no training, whereas training in animals is typically weeks to even months"; "Our recording electrodes were chronically implanted and could not be moved to search for responsive neurons"; blocked design could partially explain trial type discrimination; the study did not assess whether OL signals are specific to observing a human agent
- **limitations_categorized:** Limited ecological validity; small sample size; clinical population generalizability; task simplicity; blocked design confound; no social vs. non-social control; limited recording coverage; species comparison limitations
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - coordinates_peak: LOW — electrodes registered to MNI152 via CIT168 template, but no specific MNI coordinates reported for effects; only subnuclei breakdown provided - social_param: MEDIUM — no social parameter in winning model; this is a substantive finding (single LR outperforms split LR) rather than missing data - ecological_validity: MEDIUM — inferred from task design description - $\beta$ parameter mean (0.17 +/- 0.35): MEDIUM — the large SE relative to mean suggests high variability; the low value suggests near-random choice behavior in some participants
- **cannot_find:** - Supplement: No supplement found with `_Supplements` suffix in the papers folder - Exact protected exceedance probability value for the winning RL (counterfactual) model in the 4-model comparison (only stated as having "largest" probability; the 99.9% value is from a subsequent pairwise comparison of counterfactual single-LR vs. counterfactual split-LR) - Individual session parameter fits (only group means reported) - Effect sizes for neural encoding (only proportion of significant neurons and p-values from permutation tests)
- **other_notes:** - This is a single-neuron electrophysiology study, not fMRI — rare and valuable for understanding computation at the neuronal level - Key finding: observational and experiential value coding recruit distinct (non-overlapping) amygdala neuron populations, suggesting separable but parallel RL computations - The counterfactual RL model (updating both seen and unseen bandits) was the winning model — this is notable as it implies participants inferred anti-correlated reward structures - Authors explicitly note the study cannot determine whether OL signals are socially specific or would also arise when observing a non-human agent - Supplement not accessible (not found in papers folder)
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_addiction
- pop_healthy_adults
- rr_pop_addiction
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = partly
- spec_depth = general
- spec_locus = source
- spec_neural = shared
- spec_source = social
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = imitation_emulation
- tax_rr_topic_imitation_emulation
- tax_topic_imitation_emulation
