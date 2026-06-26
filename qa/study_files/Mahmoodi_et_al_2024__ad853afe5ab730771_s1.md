# Mahmoodi et al. (2024)

- **study_id:** `ad853afe5ab730771_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Mahmoodi, A., Luo, S., Harbison, C., Piray, P., & Rushworth, M. F. S. (2024). Human hippocampus and dorsomedial prefrontal cortex infer and update latent causes during social interaction. *Neuron*, *112*(22), 3796–3809. https://doi.org/10.1016/j.neuron.2024.09.001
- **citation_short:** Mahmoodi et al. (2024)
- **doi:** 10.1016/j.neuron.2024.09.001
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** CentreforIntegrativeNeuroimaging,DepartmentofExperimentalPsychology,UniversityofOxford,Oxford,UK; ethanwedoforthoseindividualswebelieve dataanalysisandcomputationalmodelingindicatedthatpartic-; etheirestimateasafunctionofinferredresponsibilitybutsparedtheirabilitytoinferresponsibility; DepartmentofPsychology,UniversityofSouthernCalifornia,LosAngeles,CA,USA; etheinferenceofitscause(theresponsiblecharacter)fromhippocampal; mittentlyaskedtoratetheperformanceofoneofthetwocharacters; ethattheybelievedwasachievedbyapairofcharac-; mPiray,2,4andMatthewF; emails: ali.mahmoodi1367@gmail.com
- **code_url:** https://github.com/alimahmoodia/

## Computational level
- **study_focus:** Latent social cause inference — inferring which individual is responsible for jointly achieved outcomes and updating estimates of individuals' abilities accordingly.
- **study_focus_short:** Latent social cause inference
- **learning_mode_description:** - Learning mode: Inferring which character caused a jointly achieved outcome and updating ability estimates asymmetrically based on inferred responsibility.   - Learning from:     - Source type (non-social): world       - Source content (non-social): outcome (jointly achieved performance score)   - Learning about:     - Target type (social): other (fictional characters working in pairs)       - Target content (social): state (mental state; ability/competence of each character)
- **task_description:** Participants observed outcomes achieved by pairs of fictional characters working together, then indicated which character was more responsible for each outcome. Participants intermittently rated each character's ability, allowing tracking of how estimates updated asymmetrically based on inferred responsibility.
- **task_paradigm:** Impression formation task
- **players:** Single agent (participant), multi-target (3 fictional characters forming 3 possible pairs)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Face images (from Radboud and Basel face databases), numerical performance outcomes displayed as bar on a score frame
- **method:** fMRI / TMS / behavioural
- **method_full:** fMRI, cTBS (TMS), behavioural
- **main_result:** - Main Results:   - Difference in unsigned |PE| between characters predicted choice of responsible character (B = −1.62, SE = 0.13)   - Negative interaction between outcome and |PE| on rating (B = −0.32, SE = 0.03)   - Positive interaction between PE and responsibility on rating update (B = 0.58, SE = 0.05)   - HMMKF model best fit to trial-by-trial choice (protected exceedance probability = 0.87)   - Left hippocampus decoded most likely responsible character at outcome presentation (searchlight MVPA, Z = 2.48, cluster-corrected p < 0.05)   - Hippocampus RSA: activity pattern correlated with 3D ability space (RHC: W = 398, p = 0.035)   - Hippocampus encoded probability of responsibility (p) at first character presentation (LHC: p_FDR = 0.003; RHC: p_FDR = 0.011)   - dmPFC: positive interaction of probability and PE for best character (p_FDR = 0.010); negative interaction for worst character (p_FDR = 0.005)   - dmPFC-hippocampus PPI: functional connectivity increased as function of |PE| (LHC: p_FDR = 0.003)   - dmPFC cTBS impaired asymmetric update: interaction of PE x responsibility on rating update significantly lower in dmPFC vs vertex condition (V = 148, p = 0.032)   - dmPFC cTBS reduced rating difference between best and worst characters (B = −0.07, SE = 0.02)   - dmPFC cTBS did not impair inference (choice guided by |PE| difference: no difference between conditions, BF_10 = 0.3)
- **effect_size:** - Main Results:   - Difference in unsigned |PE| between characters predicted choice of responsible character (B = −1.62, SE = 0.13)   - Negative interaction between outcome and |PE| on rating (B = −0.32, SE = 0.03)   - Positive interaction between PE and responsibility on rating update (B = 0.58, SE = 0.05)   - HMMKF model best fit to trial-by-trial choice (protected exceedance probability = 0.87)   - Left hippocampus decoded most likely responsible character at outcome presentation (searchlight MVPA, Z = 2.48, cluster-corrected p < 0.05)   - Hippocampus RSA: activity pattern correlated with 3D ability space (RHC: W = 398, p = 0.035)   - Hippocampus encoded probability of responsibility (p) at first character presentation (LHC: p_FDR = 0.003; RHC: p_FDR = 0.011)   - dmPFC: positive interaction of probability and PE for best character (p_FDR = 0.010); negative interaction for worst character (p_FDR = 0.005)   - dmPFC-hippocampus PPI: functional connectivity increased as function of |PE| (LHC: p_FDR = 0.003)   - dmPFC cTBS impaired asymmetric update: interaction of PE x responsibility on rating update significantly lower in dmPFC vs vertex condition (V = 148, p = 0.032)   - dmPFC cTBS reduced rating difference between best and worst characters (B = −0.07, SE = 0.02)   - dmPFC cTBS did not impair inference (choice guided by |PE| difference: no difference between conditions, BF_10 = 0.3)
- **learning_from:** World; jointly achieved performance outcome (numerical score)
- **learning_about:** Other (fictional characters); ability/competence (latent cause of outcomes)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** HMMKF (Hidden Markov Model + Kalman Filter; 2 free params: β (softmax temperature), μ (HMM transition probability); process noise φ and observation noise υ fixed at 0.0001)
- **model_family:** Bayesian
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Bayesian learner", "family": "Bayesian estimation (online EM)", "n_params": 0, "metric": "protected exceedance probability"} - {"name": "Kalman Filter (KF)", "family": "Kalman filter", "n_params": 1, "metric": "protected exceedance probability"} - {"name": "HMMKF", "family": "Hidden Markov Model + Kalman filter", "n_params": 2, "metric": "protected exceedance probability"}
- **model_mb_mf:** MB (model-based; uses internal generative model with latent states and Bayesian inference)
- **model_params:** - β (softmax inverse temperature): fitted per participant, prior mean x = 0, prior variance = 6.25; β = exp(x) to ensure positive values - μ (HMM transition probability, bounded 0.5–1.0): probability that latent responsibility variable z remains the same across trials [S] - φ (process noise): fixed at 0.0001 - υ (observation noise): fixed at 0.0001 - Note: Fitted parameter values not reported as group means in the main text; individual fitted values shown in Figure S2 (supplement not accessible).
- **social_param:** μ (HMM transition probability) [S] — governs how stable the latent social cause assignment (which character is responsible) is across trials; together with the responsibility inference (z), this parameter makes the model assign outcomes asymmetrically to characters rather than updating both equally.
- **social_param_name:** μ
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Protected exceedance probability (random-effects Bayesian model selection via VBA toolbox)
- **how_model_fit:** individual-level-fit (MAP estimation using CBM toolbox, fitted to each participant's trial-by-trial choice data)
- **data_type_fit_to:** choice behavior (trial-by-trial choice of responsible character)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors from HMMKF PE estimates) / MVPA (searchlight SVM decoding) / RSA / PPI
- **contrast:** - PE of first character at first character presentation (GLM1): dmPFC (peak Z = −3.65, MNI: −4, 48, 36), vmPFC (peak Z = −3.86, MNI: −4, 60, −8), OFC/AI (peak Z = −4.24, MNI: −30, 20, −12) - Searchlight MVPA decoding of most likely responsible character at outcome time: left hippocampus (Z = 2.48, cluster-corrected) - PE of chosen vs unchosen character at decision time (GLM2): dmPFC encoded PE of chosen character (Figure S6) - PPI: dmPFC-hippocampus connectivity modulated by |PE| at first character presentation - cTBS disruption of dmPFC: impaired asymmetric update but not inference
- **key_regions:** Latent cause inference (which character is responsible) decoded from left hippocampus at outcome presentation; hippocampus maintained map of 3D character ability space (RSA); dmPFC updated character ability estimates asymmetrically based on inferred responsibility (PE x probability interaction); vmPFC and OFC/AI encoded PE but did not show inference-dependent update; dmPFC-hippocampus functional coupling increased with |PE|; cTBS of dmPFC impaired responsibility-dependent update but spared inference.
- **key_regions_abbrev:** vmPFC, mPFC, dmPFC, OFC, AI, hippocampus
- **coordinates_peak:** - dmPFC (PE of first character, GLM1): -4, 48, 36 - vmPFC (PE of first character, GLM1): -4, 60, -8 - OFC/AI (PE of first character, GLM1): -30, 20, -12 - Left hippocampus (searchlight MVPA, character decoding at outcome): coordinates from cluster-corrected map (exact peak coordinates not reported as x,y,z in main text; Z = 2.48) - dmPFC cTBS target site: -2, 48, 38 (from fMRI Experiment 1 results) - Vertex control site: 0, -34, 72
- **analysis_type:** both (whole-brain searchlight MVPA with cluster correction + ROI-based analyses for hippocampus RSA, time-course analyses in dmPFC/vmPFC/OFC/AI ROIs)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** Experiment 1 (fMRI): N = 33 (from 37 recruited; 4 excluded for head motion; mean age = 24.55 +/- 5.68, 18 female). Experiment 4 (cTBS): N = 19 (from 20 recruited; 1 excluded for motor threshold; mean age = 20.84 +/- 2.29, 10 female). Experiments 2 and 3: described in supplementary (not accessible).
- **population_category:** healthy adults
- **population_age_range:** M=24.55
- **ecological_validity:** Moderate lab constraints. Task uses fictional characters with faces performing an abstract collaborative task with numerical outcomes. No real social interaction. However, the task captures a naturalistic problem (credit assignment in groups), and Experiment 3 showed the inference process is spontaneous even without explicit responsibility judgments.
- **eligibility_flag:** 
- **concerns:** (1) Supplement (Figures S1–S7, Tables S1–S5) not accessible as a separate file — the main text references these extensively for parameter recovery (Figure S2), additional experiments (Experiments 2 and 3 in Figure S1), coordinate tables (Table S1), and cTBS details (Tables S4, S5). Some details therefore could not be verified. (2) Fitted parameter mean values for the HMMKF model are shown in Figure S2 but not reported numerically in the main text. (3) Left hippocampus MVPA cluster peak coordinates (x, y, z) not explicitly reported as numbers in the main text (only Z-statistic given). (4) Process noise (φ) and observation noise (υ) were fixed at 0.0001 — the authors state results did not depend on these values but no formal sensitivity analysis is reported.
- **limitations_reported:** The authors acknowledge that their approach assumes a known, finite number of latent causes, whereas in other situations there may be an infinite capacity prior requiring additional mechanisms; they recognize that additional mechanisms are likely needed when the number of latent causes is unknown; the study focuses on a situation where participants single out one individual as responsible, which may not generalize to all forms of collaborative credit assignment.
- **limitations_categorized:** Task simplicity (fixed number of latent causes); limited generalizability (single-agent responsibility assignment only); limited ecological validity (fictional characters, no real social interaction)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Partial
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
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
- **flagged_fields:** - `model_params` (MEDIUM): Fitted mean parameter values not numerically reported in main text; shown in Figure S2 (supplement not accessible) - `coordinates_peak` for hippocampus MVPA (MEDIUM): Exact peak MNI coordinates not stated as numbers in main text; only Z-statistic and cluster correction reported - `wc_guidelines rule 5` (MEDIUM): Parameter recovery stated as done (Figure S2) but supplement not accessible for verification - All other fields: HIGH confidence
- **cannot_find:** - Supplement not available as separate file (Figures S1–S7, Tables S1–S5 referenced extensively but not accessible) - Exact hippocampus MVPA peak coordinates (x, y, z) not numerically stated in main text - Group mean fitted values for β and μ parameters - Full coordinate table (Table S1 referenced but not accessible) - Details of Experiments 2 and 3 (described only in supplement)
- **other_notes:** This paper reports 4 experiments. Experiment 1 (fMRI, N=33) is the primary study with computational modeling and neuroimaging. Experiment 4 (cTBS, N=19) provides causal evidence for dmPFC's role in updating. Experiments 2 and 3 are described in the supplement (not accessible) and replicate findings in non-social context and without explicit responsibility judgments, respectively. The HMMKF model is novel — it combines a Hidden Markov Model for latent cause inference with a Kalman Filter for ability updating, using Rao-Blackwellized particle filtering. The paper makes a strong distinction between inference (hippocampus) and update (dmPFC) as complementary but dissociable processes. Supplement not accessible — noted in concerns. No supplement file found in the papers folder.
- **re_extract_flag:** false (full text accessible; supplement not available but main text is complete)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = self_other_boundary
- tax_rr_secondary_topic = trait_impression
- tax_rr_topic_self_other_boundary
- tax_rr_topic_trait_impression
- tax_topic_self_other_boundary
- tax_topic_trait_impression
