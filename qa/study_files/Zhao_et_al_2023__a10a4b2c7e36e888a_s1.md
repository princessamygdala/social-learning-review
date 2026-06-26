# Zhao et al. (2023)

- **study_id:** `a10a4b2c7e36e888a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Zhao, H., Zhang, T., Cheng, T., Chen, C., Zhai, Y., Liang, X., Cheng, N., Long, Y., Li, Y., Wang, Z., & Lu, C. (2023). Neurocomputational mechanisms of young children's observational learning of delayed gratification. *Cerebral Cortex*, *33*(10), 6063–6076. https://doi.org/10.1093/cercor/bhac484
- **citation_short:** Zhao et al. (2023)
- **doi:** 10.1093/cercor/bhac484
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** LaboratoryofCognitiveNeuroscienceandLearning&IDG/McGovernInstituteforBrainResearch,BeijingNormalUniversity,No; etheymayhavelimitedopportunitiesfordirect Hypothesis II: In a high-uncertaintycontext,young children; InstituteofDevelopmentalPsychology,FacultyofPsychology,BeijingNormalUniversity,Beijing100875,China; DepartmentofPsychologicalScience,UniversityofCalifornia,Irvine,CA92697,UnitedStates,; CenterforChildDevelopment,SchoolofPsychology,CapitalNormalUniversity,Beijing100875,P; CenterforChildDevelopment,SchoolofPsychology,CapitalNormalUniversity,Beijing100048,P; LaboratoryofCognitiveNeurosci
- **code_url:** https://figshare.com/authors/Hui_Zhao/12504598

## Computational level
- **study_focus:** Observational learning of delayed gratification; children learn to delay gratification by observing adult models' choices, testing goal-inference vs. simple imitation strategies.
- **study_focus_short:** Observational learning of delayed gratification
- **learning_mode_description:** - Learning mode: Learning from an adult model's choices (LLR vs SSR) about the value of delayed rewards via goal inference   - Learning from:     - Source type (social): other (adult model — mother or stranger)     - Source content (social): action/policy (model's choice between SSR and LLR)   - Learning about:     - Target type (non-social): world (reward value of delayed vs. immediate options)     - Target content (non-social): outcome (subjective value of delayed reward)
- **task_description:** Children (age ~3) and an adult model (mother or stranger) take turns choosing between a smaller-sooner reward (1 sticker now) and a larger-later reward (2 or 6 stickers after the experiment); the adult model's choices are pre-scripted to create inconsistent trials (large prediction errors), and children's subsequent copying behavior is measured.
- **task_paradigm:** Observational learning task
- **players:** Single agent (child participant), dyadic (adult model: mother or stranger)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Stickers (varying quantities: 1 vs. 2 or 1 vs. 6), transparent plastic bags/buckets
- **method:** hyperscanning
- **method_full:** fNIRS hyperscanning
- **main_result:** - Observing mother's action significantly enhanced children's LLR choices in the low reward condition (F(1,45) = 4.900, η² = 0.094) - In the high reward condition, children made more LLR choices on no-learning trials than learning trials with both mother (F(1,45) = 5.080, η² = 0.098) and stranger (F(1,45) = 13.891, η² = 0.228) - Model 1 (goal-inference) had better BIC fit than Model 2 (imitation) for both mother-child pairs (BIC_sum = 502.790 vs. 546.050) and stranger-child pairs (BIC_sum = 449.465 vs. 556.179) - Model 1 prediction accuracy: 73.056% (mother-child, P < 0.001) and 77.778% (stranger-child, P < 0.001); Model 2 prediction accuracy not significant - Enhanced INS between model's right dlPFC (CH25) and child's left dlPFC (CH5) during inference phase for learning vs. no-learning of LLR choices (F(1,26) = 32.278, η² = 0.527) - Value decay parameter γ positively correlated with dlPFC INS (R² change = 0.099, F change(1,22) = 5.379, P = 0.030)
- **effect_size:** η² = 0.094 (learning effect, mother, low reward); η² = 0.098 (learning effect, mother, high reward); η² = 0.228 (learning effect, stranger, high reward); η² = 0.527 (learning × choice interaction in dlPFC INS); R² change = 0.099 (γ → INS regression)
- **learning_from:** Other (adult model — mother or stranger); model's action choices (SSR vs. LLR)
- **learning_about:** World; subjective reward value of delayed gratification (LLR)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Fictitious play model (goal-inference; 3 params: α learning rate, β temperature, γ value decay)
- **model_family:** Bayesian
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Model 1 (Goal-inference / Fictitious play)", "family": "Fictitious play", "n_params": 3, "metric": "BIC"},   {"name": "Model 2 (Imitation)", "family": "Rescorla-Wagner (imitation)", "n_params": 2, "metric": "BIC"} ]
- **model_mb_mf:** MF (model-free prediction error learning, though with goal-inference component)
- **model_params:** - α (learning rate): updates predicted choice probability of adult model based on PE. Mother-child: M = 0.181, SD = 0.161; Stranger-child: M = 0.235, SD = 0.254 - β (temperature/inverse temperature): softmax parameter governing choice stochasticity. Mother-child: M = 3.503, SD = 2.478; Stranger-child: M = 4.550, SD = 2.723 - γ (value decay parameter) [S]: discounts subjective value of LLR choice as function of delay — higher γ means more discounting. Mother-child: M = 39.419, SD = 29.848; Stranger-child: M = 27.216, SD = 28.964
- **social_param:** γ (value decay parameter) — indexes how much the child discounts the value of the delayed reward after inferring the adult model's goal; positively correlated with interpersonal neural synchronization in dlPFC.
- **social_param_name:** γ
- **social_param_value:** 39.419
- **social_param_sd:** 29.848
- **social_param_range:** 
- **model_comparison_metric:** BIC (summed across participant pairs within each adult model condition)
- **how_model_fit:** individual-level-fit (MAP estimation per participant pair using fmincon in MATLAB, with 10 random initial values)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** hyperscanning (fNIRS dual-brain wavelet transform coherence)
- **contrast:** - Learning × choice interaction in INS (Type 2: model's action execution × child's inference phase) — significant in right dlPFC (model, CH25) × left dlPFC (child, CH5) at 0.2–0.3 Hz (F(1,26) = 32.278, η² = 0.527) - Learning vs. no-learning for LLR choices: higher INS in learning trials (F(1,26) = 12.598, η² = 0.303) - Learning vs. no-learning for SSR choices: higher INS in no-learning trials (F(1,26) = 13.887, η² = 0.324) - Single-brain: learning × choice interaction in children's left dlPFC (CH5) during response phase at 0.05–0.06 Hz (F(1,26) = 27.814, η² = 0.490)
- **key_regions:** Interpersonal neural synchronization (INS) in bilateral dlPFC (model's right dlPFC CH25 and child's left dlPFC CH5) during inference phase associated with observational learning of delayed gratification; single-brain dlPFC activity (CH5) during response phase related to choice but not specifically to observational learning.
- **key_regions_abbrev:** dlPFC, AI
- **coordinates_peak:** MNI coordinates for key channels from Supplement Table S2: - CH5 (child left dlPFC): -55, 6, 45 (BA 6, dlPFC & Pre-Motor/Supplementary Motor Cortex) - CH25 (model right dlPFC): 53, 27, 38 (BA 44, dlPFC & Pars Opercularis/Pars Triangularis)  Note: These are optode channel positions, not activation peak coordinates — fNIRS does not produce peak voxel coordinates like fMRI.
- **analysis_type:** whole-brain (all 44 channels × all CH combinations examined with cluster-based permutation and FDR correction)  ---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 30 mother-child pairs and 30 stranger-child pairs with valid data (from original 62 recruited; 29 dropped due to headset refusal, probe pulling, or incomplete experiment; 3 dropped for data storage errors). Children: mean age = 3.4 years (SD = 0.38), 20 male. 12 stranger women also recruited.
- **population_category:** children
- **population_age_range:** 
- **ecological_validity:** Moderate ecological limitations: the adult model's choices were pre-scripted (randomized), which is not consistent with real-life adult preferences that would be consistent; stickers used as rewards; lab-based face-to-face interaction with fNIRS headsets; however, real social interaction (not virtual) with child's own mother or a stranger provides some ecological validity relative to computer-based tasks.
- **eligibility_flag:** 
- **concerns:** - Small sample size (N = 30 per condition); study was slightly underpowered per authors' own power analysis (target N = 33) - Limited number of trials per child (12 total; 6 per reward level) — raises concerns about reliability of individual-level parameter estimation, though parameter recovery was tested - Learning rate α could not be adequately recovered with only 6 trials (per supplement Table S4) - Pre-scripted adult model choices create artificial high-uncertainty context not representative of natural observational learning - fNIRS optode positions confirmed with only 2 adult female participants' MRI scans — child brain anatomy may differ - No explicit model recovery (confusion matrix between Model 1 and Model 2) reported — only parameter recovery for Model 1
- **limitations_reported:** Only tested in high-uncertainty/large PE context with randomly varying adult model choices, which is not consistent with real life where adult preferences are consistent — future research should confirm in ecologically more valid context with small PEs; dlPFC INS was enhanced both when children chose LLR by learning and when they chose SSR themselves, possibly reflecting shared value representation rather than shared choice representation — needs further examination; large number of children dropped from original sample due to difficulty keeping young children still and quiet during fNIRS scanning, resulting in sample slightly smaller than target and study slightly underpowered — results are preliminary and need replication in larger sample.
- **limitations_categorized:** Limited ecological validity; limited generalizability (high-uncertainty context only); sample size (underpowered); high attrition rate; task simplicity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 8.5
- **wc_total:** 8.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_mb_mf: MEDIUM confidence — Model 1 is described as a fictitious play model with PE-based updating (model-free), but the goal-inference component adds a model-based-like flavor; classified as MF because the learning rule is PE-driven without an explicit world model. - coordinates_peak: MEDIUM confidence — these are fNIRS channel positions (optode placements), not conventional fMRI peak activation coordinates. Derived from MRI scans of 2 adult participants only. - analysis_type: MEDIUM confidence — classified as whole-brain because all CH combinations were tested with cluster-based permutation + FDR, but fNIRS coverage is limited to frontal, temporal, and parietal cortex (not truly whole-brain). - model_params (supplement Table S3): MEDIUM confidence — the supplement .txt extraction of the parameter table had some formatting issues, but values cross-referenced with main text are consistent.
- **cannot_find:** - Exact formula notation is partially garbled in the .txt extraction due to PDF conversion issues with mathematical notation, but equations were reconstructable from context. - No explicit model recovery / confusion matrix between Model 1 and Model 2.
- **other_notes:** - This is an exploratory study (authors' own characterization). - Uses fNIRS hyperscanning (dual-brain) — a relatively rare method in computational modeling literature. - Study focuses on developmental population (3-year-olds), which is unusual for computational modeling studies. - The computational models are adapted from Hampton et al. (2008) and Hill et al. (2017) fictitious play framework. - Key finding: even 3-year-olds use goal-inference (not simple imitation) strategy during observational learning in high-uncertainty contexts. - Supplement provides full MNI coordinates for all 44 channels (Table S2), model parameters (Table S3), and parameter recovery results (Table S4).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_children
- rr_pop_children
- rr_tax_mod_action_observation
- rr_tax_mod_mentalizing_inference
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_mentalizing_inference
- tax_mod_multiplayer_live
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_decay
- tax_popclass_developmental
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_MB_MF_balance
- tax_rr_param_learning_rate
- tax_rr_primary_topic = imitation_emulation
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_imitation_emulation
- tax_rr_topic_mentalizing
- tax_topic_imitation_emulation
- tax_topic_mentalizing
