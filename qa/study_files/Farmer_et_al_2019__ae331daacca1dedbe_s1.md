# Farmer et al. (2019)

- **study_id:** `ae331daacca1dedbe_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Farmer, H., Hertz, U., & Hamilton, A. F. de C. (2019). The neural basis of shared preference learning. *Social Cognitive and Affective Neuroscience*, *14*(10), 1061–1072. https://doi.org/10.1093/scan/nsz076
- **citation_short:** Farmer et al. (2019)
- **doi:** 10.1093/scan/nsz076
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** mitsunrestrictedreuse,distribution,andreproductioninanymedium,providedtheoriginalworkisproperlycited; InstituteofCognitiveNeuroscience,UniversityCollegeLondon,London,WC1N3AZ,UK2Departmentof; UniversityofBath,Bath,BA27AY,UKand3DepartmentofCognitiveSciences,UniversityofHaifa,; DepartmentofPsychology,10West,UniversityofBath,Bath,BA27AY,UK; etheneuralprocessesthatunderlielearningabout; etheexpectationofafutureoutcome(orreward); etheir ofthelearningrateandthePE,i; ethesamepainting75%ofthetimeand; emails: h.farmer@bath.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Shared preference learning — learning about the similarity of others' aesthetic preferences to one's own, and how the brain tracks preference similarity via consistency versus direct similarity mechanisms.
- **study_focus_short:** Shared preference learning
- **learning_mode_description:** - Learning mode: Learning from observing another agent's aesthetic choices about that agent's preference similarity/consistency relative to self.   - Learning from:     - Source type (social): other (two computer agents posing as prior participants)     - Source content (social): action/policy (agents' painting preference choices)   - Learning about:     - Target type (social): other (each agent individually)     - Target content (social): state (mental state; preference similarity/consistency to self)
- **task_description:** Participants chose which of two paintings they preferred, then observed the choices of two agents — a similar agent (ASim; 75% agreement) and a different agent (ADiff; 25% agreement) — across 80 trials in an fMRI scanner. After every 20 trials, participants rated each agent on similarity, likeability, and trustworthiness.
- **task_paradigm:** Social influence task
- **players:** Single agent (participant), multi-target (2 computer agents: ASim, ADiff)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract and landscape paintings (paired), agent faces (from KDEF database), binary preference choices, 10-point rating scales
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Participants rated ASim as more similar, likeable, and trustworthy than ADiff (similarity: η²p = 0.58; liking: η²p = 0.58; trust: η²p = 0.31)   - Significant interaction between agent and session for similarity ratings (η²p = 0.25), indicating learning over time   - No brain areas tracked accumulated similarity (AS) from the similarity model   - dmPFC (bilateral superior medial frontal gyrus) tracked accumulated consistency (AC) from the consistency model   - Bilateral caudate nucleus tracked positive consistency prediction errors (PE_Con)   - Right angular gyrus, right STS, right SFS, and precuneus tracked negative consistency PE (i.e., increased activity for inconsistent agent choices)   - Occipital cortex (bilateral lateral occipital cortex, lingual gyrus) tracked negative similarity PE (unexpected dissimilarity)   - ADiff > ASim contrast: right inferior frontal sulcus (z = 3.86) and right fusiform gyrus (z = 3.51)
- **effect_size:** - Similarity ratings main effect of agent: η²p = 0.58 - Liking ratings main effect of agent: η²p = 0.58 - Trust ratings main effect of agent: η²p = 0.31 - Agent × session interaction for similarity: η²p = 0.25 - Neural effects reported as z-scores at peak voxels (see coordinates)
- **learning_from:** Other (two agents); agents' painting preference choices (agree/disagree with participant)
- **learning_about:** Other (each agent); preference similarity/consistency to self  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Consistency RL model (fixed λ = 0.5; AC and PE_Con tracked per agent). The consistency model outperformed the similarity model in terms of brain areas showing significant tracking — dmPFC tracked AC, caudate tracked positive PE_Con, and mentalising network tracked negative PE_Con. The similarity model only captured occipital cortex responses to unexpected dissimilarity.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Similarity RL model", "family": "Rescorla-Wagner", "n_params": 1, "metric": "model-based fMRI (neural fit comparison)"},   {"name": "Consistency RL model", "family": "Rescorla-Wagner", "n_params": 1, "metric": "model-based fMRI (neural fit comparison)"} ]
- **model_mb_mf:** MF
- **model_params:** - λ (learning rate) = 0.5 (fixed a priori, not fitted) - AS (accumulated similarity; initial value = 0) — similarity model - PE_Sim (similarity prediction error) — similarity model - AC (accumulated consistency; initial value = 0) [S] — consistency model - PE_Con (consistency prediction error) [S] — consistency model
- **social_param:** AC (accumulated consistency) — tracks the consistency of each agent's preference similarity to the participant across trials, representing a person-specific model of the other. PE_Con (consistency prediction error) — signals whether an agent's choice is consistent or inconsistent with their established pattern of similarity to the participant.
- **social_param_name:** AC
- **social_param_value:** 0
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Model-based fMRI comparison (brain areas tracked by each model's parametric regressors; no formal behavioral model comparison metric — models were not fit to behavioral data but compared by neural evidence)
- **how_model_fit:** params-calculated-independently (learning rate fixed at 0.5; model parameters calculated from task structure without fitting to behavioral responses)
- **data_type_fit_to:** neural activity (parametric modulators in GLM)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors)
- **contrast:** - ADiff > ASim outcome screen: rIFS (z = 3.86), rFG (z = 3.51) - Negative PE_Sim conjunction (ASim ∩ ADiff): bilateral LOC, lingual gyrus (z = 3.79–4.06) - Positive AC conjunction (ASim ∩ ADiff): bilateral smFG/dmPFC (z = 3.17–3.37) - Positive PE_Con conjunction (ASim ∩ ADiff): bilateral caudate nucleus (z = 3.90–4.54) - Negative PE_Con conjunction (ASim ∩ ADiff): rAG (z = 4.22), rSFS (z = 4.20), rSTS (z = 3.19–3.85), precuneus (z = 3.72), rMTG (z = 3.46)
- **key_regions:** Accumulated consistency (AC) tracked in dmPFC (bilateral smFG); positive consistency PE in bilateral caudate nucleus; negative consistency PE (inconsistency signal) in right AG, right STS, right SFS, precuneus, right MTG (mentalising network); similarity PE (dissimilarity signal) in bilateral lateral occipital cortex and lingual gyrus; agent identity (ADiff > ASim) in right IFS and right fusiform gyrus.
- **key_regions_abbrev:** caudate, mPFC, dmPFC, ACC, STS, precuneus, FFA
- **coordinates_peak:** Table 1 — Main effect of similarity (ADiff > ASim): Right inferior frontal sulcus (BA44): 38, 10, 34 Right fusiform gyrus (BA18): 14, -82, -10 Right lateral occipital gyrus (BA19): 30, -82, -14  Table 2 — Similarity GLM, Negative PE_Sim conjunction: Left lateral occipital gyrus (BA18): -28, -94, 16 Right lateral occipital gyrus (BA37): 32, -54, -16 Right lateral occipital gyrus (BA18): 24, -90, 18 Right middle occipital gyrus (BA19): 36, -80, 22 Left lingual gyrus (BA17): -6, -78, 8 Right lateral occipital gyrus (BA19): 28, -82, -16 Left lateral occipital gyrus (BA37): -28, -60, -16 Left fusiform gyrus (BA37): -26, -48, -14  Table 3 — Consistency GLM: Positive AC conjunction (ASim ∩ ADiff): Right superior medial frontal gyrus (BA9): 8, 56, 34 Left superior medial frontal gyrus (BA10): -2, 54, 24 Right superior medial frontal gyrus (BA10): 6, 56, 22  Positive PE_Con conjunction: Left corpus callosum: -12, -6, 28 Right caudate nucleus: 16, -6, 28 Left corpus callosum: -4, 14, 12  Negative PE_Con conjunction: Right angular gyrus (BA40): 56, -46, 50 Right intraparietal sulcus (BA40): 32, -50, 40 Right superior frontal sulcus (BA10): 34, 50, 10 Right superior temporal sulcus (BA37): 60, -58, 16 Right superior temporal sulcus (BA41): 44, -42, 20 Right superior temporal sulcus (BA39): 42, -54, 16 Right precuneus (BA39): 10, -56, 48 Right middle temporal gyrus (BA21): 60, -20, -16 Right superior temporal sulcus (BA21): 62, -28, -10  Supplement Table S1 — Factorial GLM (Disagree > Agree): Left lateral occipital gyrus (BA18): -30, -92, 22 Left cuneus (BA18): -12, -88, 16 Right lateral occipital gyrus (BA37): 32, -54, -16 Right fusiform gyrus (BA19): 30, -64, -14 Right fusiform gyrus (BA37): 28, -46, -14 Left lingual gyrus (BA17): -6, -78, 8 Left lingual gyrus (BA18): -8, -70, -2 Right occipital superior gyrus (BA18): 24, -92, 16 Right middle occipital gyrus (BA19): 36, -80, 22 Right lateral occipital gyrus (BA19): 28, -82, -16 Left lateral occipital gyrus (BA37): -28, -60, -16 Left fusiform gyrus (BA37): -26, -48, -14  Consistent > Inconsistent: Left corpus callosum: -2, 14, 10 Right corpus callosum: 16, -6, 28  Inconsistent > Consistent: Right superior temporal sulcus (BA37): 62, -58, 12 Right supramarginal gyrus (BA40): 58, -42, 46 Right intraparietal sulcus (BA7): 28, -50, 42 Right superior frontal sulcus (BA10): 34, 50, 10 Right precuneus: 8, -58, 48 Right middle temporal gyrus (BA20): 62, -24, -14 Right middle temporal gyrus (BA21): 64, -18, -8
- **analysis_type:** whole-brain  ---  ## QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 25 (mean age 25.1 ± 5.7 years; 11 male); n = 18 for behavioral ratings analysis (7 excluded due to data recording issues); all 25 used for fMRI analysis.
- **population_category:** healthy adults
- **population_age_range:** M=25.1
- **ecological_validity:** Low-moderate. The task uses abstract aesthetic preference judgments (painting choices) rather than real social interactions. Agents were computer-controlled rather than real people, and participants were told agents were previous participants. No real consequences for preference similarity/dissimilarity. However, the implicit learning paradigm is more naturalistic than explicit instruction.
- **eligibility_flag:** 
- **concerns:** - Learning rate was fixed at 0.5 for all participants rather than fitted to individual behavioral data; no trial-by-trial behavioral measure of learning was collected. - Models were not compared via formal model comparison (BIC, AIC, etc.) on behavioral data; comparison was based solely on which model's parametric regressors showed significant neural activations. - No parameter recovery or model recovery analyses. - Seven participants' rating data were lost due to technical issues. - Relatively small sample (N = 25). - Cluster-correction threshold was p < 0.001 uncorrected with Monte Carlo simulation for cluster extent, which has been criticized in the literature.
- **limitations_reported:** The task did not allow collection of trial-by-trial behavioural data showing what participants had learnt about the agents, because the authors wanted participants to learn implicitly rather than making explicit predictions; a learning rate of 0.5 was approximated and used in the RL models rather than fitted, raising the possibility of a weak fit between the model learning rate and participants' actual learning rate; however, the main predictions related to the direction of tracked PEs and accumulated preferences, which are less likely to be affected by this approximation.
- **limitations_categorized:** no trial-by-trial behavioral measure; fixed (not fitted) learning rate; no parameter recovery; no formal model comparison on behavior; small sample size
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_comparison_metric: MEDIUM — no formal behavioral model comparison; models compared by neural evidence only - winning_model: MEDIUM — "winning" determined by which model produced more significant neural activations, not by formal model fit statistics - model_params (learning rate): HIGH — explicitly stated as fixed at 0.5 - how_model_fit: HIGH — explicitly stated that parameters were not fit to behavioral data
- **cannot_find:** - Formal model comparison metric (BIC, AIC, etc.) — not applicable as models were not fit to behavioral data - Data/code availability statement - Effect sizes for neural contrasts beyond z-scores at peak voxels
- **other_notes:** - This paper takes an unusual approach: rather than fitting RL models to behavioral data, it fixes the learning rate and uses the model-derived trial-by-trial parameters as parametric regressors in fMRI GLMs. The "comparison" between similarity and consistency models is based on which model's regressors produce significant brain activations, not on behavioral model fit. - The consistency model is preferred because it produces significant activations in reward (caudate) and social cognition (dmPFC, STS, AG, precuneus) regions, while the similarity model only captures occipital cortex responses. - The supplement contains an alternative factorial GLM analysis (Table S1) that corroborates the consistency model findings, plus a dmPFC literature comparison (Table S2, Figure S1).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_primary_topic = trait_impression
- tax_rr_topic_trait_impression
- tax_topic_trait_impression
