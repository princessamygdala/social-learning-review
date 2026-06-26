# Wunderlich et al. (2011)

- **study_id:** `a3f938d0a85d88449_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Wunderlich, K., Beierholm, U. R., Bossaerts, P., & O'Doherty, J. P. (2011). The human prefrontal cortex mediates integration of potential causes behind observed outcomes. *Journal of Neurophysiology*, 106(3), 1558–1569. https://doi.org/10.1152/jn.01051.2010
- **citation_short:** Wunderlich et al. (2011)
- **doi:** 10.1152/jn.01051.2010
- **publication_type:** peer-reviewed journal
- **year:** 2011.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Division of Humanities and Social Sciences, California Institute of Technology, Pasadena, CA; College Institute of Neuroscience and School of Psychology, Trinity College, Dublin, Ireland; lable evidences than by a model in which attention is selectively gated; ether during the performance of a hierarchical reversal learning; Centre for Neuroimaging, UCL, London, UK; Institute of Technology, Pasadena, CA; mited cognitive resources; Centre for Neuroimaging; emails: kwunder@fil.ion.ucl.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Hierarchical causal inference during reversal learning — how humans integrate evidence across multiple stimulus dimensions (causal theories) when learning which dimension and which feature within that dimension is currently rewarded.
- **study_focus_short:** Hierarchical causal inference during reversal learning
- **learning_mode_description:** - Learning mode: Learning from one's own reward outcomes about which stimulus dimension (color vs. motion) and which feature within that dimension is causally linked to reward, by integrating evidence across multiple potential causal explanations.   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (monetary reward/loss feedback)   - Learning about:     - Target type (non-social): world (stimulus-reward contingencies)     - Target content (non-social): state (which dimension is relevant and which feature is correct — causal structure of the environment)
- **task_description:** Participants chose between two compound stimuli (each with a color and a motion feature) in a probabilistic hierarchical reversal learning task; the correct feature (rewarded at 80%) and the relevant dimension switched over time, requiring participants to track both which dimension was causal and which feature within that dimension was correct.
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), no social targets.
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Colored rectangles (red/green) and moving dot sequences (left/right motion), combined into compound stimuli; binary monetary outcomes (+$0.25 / -$0.25).
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Integration model fit behavior better than attention-gating model in all 16 subjects; 13/16 showed strong evidence (log BF > 3) (BF range: 0.78–20.67) - Bayesian model comparison at population level: exceedance probability ≈ 1.0 for integration model (posterior probability = 0.94 vs. 0.06) - Likelihood ratio test: χ²(df=1) = 500.5, p << 0.00001 - vmPFC activity correlated with integration model stimulus value (Z = 4.71, cluster = 1069 voxels, FWE corrected) - Neurometric model comparison in vmPFC: integration model exceedance probability = 0.98 (Dirichlet α = 13.34 vs. 4.66) - Within-dimension certainty correlated with anterior mPFC (Z = 3.83) - Within-dimension uncertainty correlated with dmPFC, bilateral dlPFC, frontal poles, parietal cortex (peak Z = 5.3, right MFG) - Correlation of integration model likelihood with earnings (r = 0.50, p < 0.05) - Correlation of learning rate with switch proportion (r = 0.83, p = 0.0002)
- **effect_size:** - BF(integration > attention): range 0.78–20.67 across subjects - Population BMS: exceedance probability = 1.0 (integration), 0.0 (attention-gating) - χ²(df=1) = 500.5 (likelihood ratio test, integration vs. attention-gating) - r = 0.50 (model likelihood vs. earnings) - r = 0.83 (learning rate vs. switch proportion) - r = 0.86 (log likelihood of integration model vs. experienced switch ratio) - r = 0.55 (average across-dimensional certainty vs. switch ratio) - vmPFC stimulus value: Z = 4.71 (peak) - Neurometric BMS exceedance probability = 0.98 (integration model in vmPFC)
- **learning_from:** Self; own reward/loss outcomes on chosen stimulus.
- **learning_about:** World; which stimulus dimension (color vs. motion) is causally relevant and which feature within that dimension is correct.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Two-layer RL integration model: feature values updated via RW prediction error (V_i(t+1) = V_i(t) + α^i × δ(t), δ(t) = r(t) − V_i(t)); dimensional weight updated via second-layer PE (W_color(t+1) = W_color(t) + α^e × δ_color(t), δ_color(t) = r_t(V_i(t) − V_j(t)) − W_color(t)); choice value computed as weighted integration: V_UP = V_i1 × w_color + V_j1 × (1 − w_color), where w_color = σ(2κW_color); softmax choice rule with inverse temperature β. 4 parameters: α^i (within-dimension LR), α^e (across-dimension LR), β (softmax temperature), κ (integration steepness).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "RL Integration (winning)", "family": "Two-layer hierarchical RL", "n_params": 4, "metric": "BIC"},   {"name": "RL Attention-gating", "family": "Two-layer hierarchical RL", "n_params": 3, "metric": "BIC"},   {"name": "Bayesian", "family": "Bayesian belief updating", "n_params": 1, "metric": "BIC"},   {"name": "RL Stimuli (compound)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"},   {"name": "RL 1-Layer", "family": "Rescorla-Wagner (single-layer)", "n_params": 2, "metric": "BIC"},   {"name": "RL 4-options", "family": "Rescorla-Wagner (compound stimulus)", "n_params": 2, "metric": "BIC"} ]
- **model_mb_mf:** MF (model-free RL with hierarchical structure; learning is prediction-error based, not model-based planning)
- **model_params:** - α^i: within-dimension learning rate (learning rate for feature values V_color, V_motion); no group mean reported - α^e: across-dimension learning rate (learning rate for dimensional weight W); no group mean reported - β: softmax inverse temperature; no group mean reported - κ: integration steepness parameter (controls how sharply dimensional weights translate to choice weights via sigmoid transformation w = σ(2κW)); no group mean reported; fitted function shown in Figure S3
- **social_param:** None — this is a non-social task.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC; Bayes Factors (approximated from BIC differences); Bayesian Model Selection (Stephan et al., 2009) with exceedance probabilities; likelihood ratio test (nested models).
- **how_model_fit:** individual-level-fit (maximum likelihood per subject)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — trial-by-trial model-derived value signals used as parametric modulators in GLM; separate GLMs for integration and attention-gating models; Bayesian model comparison of GLMs.
- **contrast:** - Stimulus value (integration model): max(V_UP, V_DOWN) — vmPFC (Z = 4.71, p < 0.05 FWE cluster-corrected) - Within-dimension certainty (integration model): max(V_red, V_green) averaged with max(V_right, V_left) — anterior mPFC (Z = 3.83) - Within-dimension uncertainty (negative certainty): dmPFC, bilateral dlPFC, frontal poles, bilateral parietal cortex (peak Z = 5.3) - Neurometric model comparison: integration vs. attention-gating GLMs in vmPFC — exceedance probability = 0.98 for integration - Reversal error contrast (supplementary): right DLPFC, bilateral parietal, DMPFC
- **key_regions:** Stimulus value in vmPFC (BA 10/32); within-dimension certainty in anterior mPFC (BA 10); within-dimension uncertainty in right MFG/dlPFC (BA 8), bilateral frontal poles (BA 10), dmPFC (BA 8), bilateral inferior parietal lobules (BA 40). Reversal error in right DLPFC, bilateral parietal cortex, DMPFC (supplementary analysis).
- **key_regions_abbrev:** vmPFC, mPFC, dmPFC, dlPFC, AI, parietal
- **coordinates_peak:** Max Stimulus Value (integration model): vmPFC (BA 10, 32): 0, 48, -3 Precuneus (BA 7): 0, -39, 54 Left inf. temporal gyrus (BA 19, 37): -54, -63, -6 Right circ. insular sulcus (BA 21): 45, -3, -18 Right angular gyrus (BA 19, 39): 42, -78, 27 Left angular gyrus (BA 19, 39): -48, -66, 30 Left inf. temporal sulcus (BA 20): -60, -12, -27 Right inf. temporal sulcus (BA 21): 63, -54, -3 Parahippocampal gyrus (BA 36): 24, -45, -15  Within-dimension certainty: Anterior mPFC (BA 10): -3, 57, 3  Within-dimension uncertainty: Right middle frontal gyrus (BA 8): 51, 15, 45 Right frontal pole (BA 10): 33, 51, 15 Dorsomedial PFC (BA 8): 3, 21, 48 Right inf. parietal lobule (BA 40): 48, -48, 51 Left frontal pole (BA 10): -42, 45, 12 Left middle frontal gyrus (BA 9): -48, 24, 36 Left inf. parietal lobule (BA 40): -42, -51, 54  Reversal error (supplementary): Right DLPFC: 45, 36, 39 Right parietal cortex: 33, -51, 45 Left parietal cortex: -36, -48, 42 DMPFC: 3, 24, 51
- **analysis_type:** whole-brain (all activations reported at p < 0.05 FWE cluster-level correction, with height threshold p < 0.001; neurometric comparison used 12mm sphere ROI in vmPFC for Bayesian model comparison) — both  ---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 16 (6 female; ages 18–28; Caltech student population)
- **population_category:** healthy adults
- **population_age_range:** 18–28
- **ecological_validity:** Low — abstract laboratory task with colored rectangles and moving dots; probabilistic hierarchical reversal learning; no social interaction; monetary incentive structure is artificial. The task captures causal inference under uncertainty but uses abstract, non-naturalistic stimuli.
- **eligibility_flag:** FLAG — This paper does NOT involve social learning. Learning occurs in a non-social context (individual learning about abstract stimulus-reward contingencies). No social agent, no social information, no social context. The task is a probabilistic hierarchical reversal learning task (variant of Wisconsin Card Sorting Task) with no social component whatsoever. Flagged as: "No social learning context — individual learning about stimulus dimensions and reward contingencies.
- **concerns:** - No social component: this is a purely non-social learning task. Its inclusion in a social learning review is questionable unless used as a non-social comparator. - Small sample size (N = 16). - No parameter recovery or model recovery analyses reported. - No simulation studies described. - Mean fitted parameter values not reported (only integration steepness function shown in Figure S3). - Adaptive switching rule (contingency changes only after 3 correct responses) introduces a confound between learning speed and task progression. - Response times not significantly different between correct/incorrect trials, suggesting limited RT sensitivity.
- **limitations_reported:** Authors acknowledge: the study cannot fully rule out stochastic switching between dimensions on a trial-by-trial basis as alternative to integration; the null result for across-dimensional certainty in neural data limits interpretation; with many more than two dimensions, subjects might revert to attention-gating due to cognitive constraints; the task design is not optimized for trial-based reversal analysis (as in Cools et al.); cannot rule out that attention plays a role in value computation alongside integration; updating may proceed via RL rather than full Bayesian updating, and the study cannot fully adjudicate this.
- **limitations_categorized:** limited ecological validity; small sample size; cannot rule out alternative strategies; task design limitations; limited generalizability to higher-dimensional problems; model identifiability concerns
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
- **wc_rule10:** No
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `model_params`: MEDIUM — individual fitted parameter means not reported in text; only the shape of the κ transformation function is shown in Fig. S3 - `model_mb_mf`: MEDIUM — classified as MF because updating is PE-based, but the two-layer hierarchical structure with dimensional weights has model-based-like qualities - `eligibility_flag`: HIGH — clearly no social context - `social_param`: HIGH — none; non-social task
- **cannot_find:** - Mean fitted values for α^i, α^e, β, κ (not reported in text or supplement) - Individual subject parameter estimates (not tabulated) - Exact number of trials per subject (only mean = 294, sd = 62)
- **other_notes:** This paper investigates hierarchical causal inference during learning — specifically whether humans integrate evidence across multiple potential causal dimensions (Bayesian marginalization) or selectively attend to one dimension (attention-gating). While computationally sophisticated and relevant to learning and inference, the task is entirely non-social. The paper may be relevant to a systematic review of computational models of social learning only as a non-social comparator or as foundational work on hierarchical inference that has been applied in social contexts by later studies (e.g., Hampton et al., 2008 is cited as extending similar approaches to social decision-making). The paper was published in Journal of Neurophysiology in 2011, with the doi suggesting it was first available online June 22, 2011.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = general
- spec_locus = source
- spec_neural = dedicated
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = G_uncertainty_volatility
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = volatility
- tax_rr_topic_volatility
- tax_topic_volatility
