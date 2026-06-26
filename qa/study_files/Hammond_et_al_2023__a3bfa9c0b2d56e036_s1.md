# Hammond et al. (2023)

- **study_id:** `a3bfa9c0b2d56e036_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hammond, D., Xu, P., Ai, H., & Van Dam, N. T. (2023). Anxiety and depression related abnormalities in socio-affective learning. *Journal of Affective Disorders*, *335*, 322–331. https://doi.org/10.1016/j.jad.2023.05.021
- **citation_short:** Hammond et al. (2023)
- **doi:** 10.1016/j.jad.2023.05.021
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** School of Psychological Sciences, The University of Melbourne, Melbourne, VIC 3010,; School of Psychological Sciences, The University of Melbourne, Melbourne, Australia; Center for Neuroimaging, Shenzhen Institute of Neuroscience, Shenzhen, China; Institute of Applied Psychology, Tianjin University, Tianjin, China; Faculty of Psychology, Beijing Normal University, Beijing, China; ether such findings are specific to anxiety or; University, Tianjin, China; lable at ScienceDirect; emails: nicholas.vandam@unimelb.edu.au
- **code_url:** 

## Computational level
- **study_focus:** Socio-affective learning under volatility; how anxiety and depression relate to adaptive learning-rate adjustment in response to changing reinforcement contingencies using socio-affective (facial expression) feedback.
- **study_focus_short:** Socio-affective learning under volatility
- **learning_mode_description:** - Learning mode: Learning from socio-affective feedback (happy/neutral/angry faces + verbal expressions) about which stimulus option yields the best outcome under changing contingencies   - Learning from:     - Source type (social): world (experimenter-delivered social stimulus)     - Source content (social): outcome (socio-affective feedback — facial expressions and verbal statements)   - Learning about:     - Target type (non-social): world (stimulus-outcome contingencies)     - Target content (non-social): stimulus (which slot machine is better)
- **task_description:** Participants chose between two "slot machines" on each trial, receiving socio-affective feedback (happy, neutral, or angry faces paired with verbal statements). Outcome contingencies changed between stable (fixed 75/25 probabilities) and volatile (reversing 80/20 every 30 trials) blocks, across reward-maximisation (positive vs. neutral feedback) and punishment-minimisation (neutral vs. negative feedback) conditions.
- **task_paradigm:** Volatility task (Behrens)
- **players:** Single agent (participant), no social partner; feedback delivered by task.
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Colour-unique "slot machine" images; socio-affective feedback comprising facial images (from BESST stimulus set — happy, neutral, angry faces) paired with short written expressions (e.g., "Excellent!", "Acceptable", "Terrible!").
- **method:** online / behavioural
- **method_full:** Behavioural (online/in-lab, no neuroimaging)
- **main_result:** - Neither general affective distress nor anxiety/depression were consistently related to decreased adaptive learning-rate adjustment under volatility (Sample 1: $\beta_{\alpha:volatility}$ = -0.01, 95% HDI = -0.14, 0.13; Sample 2: $\beta_{\alpha:volatility}$ = -0.15, 95% HDI = -0.37, 0.05) - General distress was associated with higher learning rates under punishment-minimisation in Sample 1 ($\beta_{\alpha:incentive}$ = 0.24, 95% HDI = 0.08, 0.41) - Distress related to higher incentive x volatility interaction on learning rate in Sample 1 ($\beta_{\alpha:incentive \times volatility}$ = 0.15, 95% HDI = 0.03, 0.28) - General distress associated with less consistent responding (lower inverse temperature) in Sample 2
- **effect_size:** - $\beta_{\alpha:volatility}$ = -0.01 (95% HDI: -0.14, 0.13) [Sample 1]; -0.15 (95% HDI: -0.37, 0.05) [Sample 2] - $\beta_{\alpha:incentive}$ = 0.24 (95% HDI: 0.08, 0.41) [Sample 1]; 0.15 (95% HDI: -0.11, 0.44) [Sample 2] - $\beta_{\alpha:incentive \times volatility}$ = 0.15 (95% HDI: 0.03, 0.28) [Sample 1]; -0.07 (95% HDI: -0.26, 0.13) [Sample 2]
- **learning_from:** World; socio-affective feedback (happy/neutral/angry faces + verbal expressions) on chosen slot machine.
- **learning_about:** World; stimulus-outcome contingencies (which slot machine yields better feedback).  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** face_expression

## Algorithmic level
- **winning_model:** Rescorla-Wagner with softmax, decomposed learning rate and inverse temperature into linear combinations on logit scale coding volatility, incentive, and their interaction, plus group-level session and block effects (Model 3). Formula: logit($\alpha_{vp}$) = $\alpha_{baseline}$ + V$\alpha_{volatility}$ + P$\alpha_{incentive}$ + VI$\alpha_{volatility \times incentive}$; softmax with inverse temperature $\tau$ similarly decomposed. Hierarchical Bayesian estimation with phenotypic variables (distress) included in group-level mean.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Model 1 — Base Model", "family": "Rescorla-Wagner", "n_params": "α (4 components: baseline, volatility, incentive, interaction), τ (4 components)", "metric": "LOOIC: 34739 (S1), 29715 (S2)"} 2. {"name": "Model 2 — Added lapse parameter", "family": "Rescorla-Wagner + lapse", "n_params": "α (4 components), τ (4 components), ε (2 components: baseline + incentive)", "metric": "LOOIC: 34784 (S1), 29784 (S2)"} 3. {"name": "Model 3 — Added session/block effects (WINNING)", "family": "Rescorla-Wagner", "n_params": "α (4 individual + session/block group-level), τ (4 individual + session/block group-level)", "metric": "LOOIC: 34681 (S1), 29698 (S2)"} 4. {"name": "Model 4 — Added session×block×manipulation interactions", "family": "Rescorla-Wagner", "n_params": "Model 3 + session/block × volatility/incentive interactions", "metric": "LOOIC: 34668 (S1), 29750 (S2)"} 5. {"name": "Model 5 — Outcome-dependent learning rates", "family": "Rescorla-Wagner (dual LR)", "n_params": "Model 3 + good/bad outcome LR components", "metric": "LOOIC: 33664 (S1), 29285 (S2)"} 6. {"name": "Model 6 — Choice kernel", "family": "Rescorla-Wagner + choice kernel", "n_params": "Model 3 + η (choice kernel update rate, 2 components) + τ_k (choice kernel temperature, 2 components)", "metric": "LOOIC: 32010 (S1), 26919 (S2)"}
- **model_mb_mf:** MF
- **model_params:** - $\alpha_{baseline}$: learning rate baseline component - $\alpha_{volatility}$: learning rate volatility effect (volatile - stable) - $\alpha_{incentive}$: learning rate incentive effect (punishment - reward) - $\alpha_{volatility \times incentive}$: learning rate volatility × incentive interaction - $\tau_{baseline}$: inverse temperature baseline - $\tau_{volatility}$: inverse temperature volatility effect - $\tau_{incentive}$: inverse temperature incentive effect - $\tau_{volatility \times incentive}$: inverse temperature interaction - Group-level session and block effects on both $\alpha$ and $\tau$ - $\beta_{\alpha:volatility}$ [S]: beta coefficient for effect of general distress on volatility learning-rate adaptation - $\beta_{\alpha:incentive}$ [S]: beta coefficient for effect of distress on incentive learning-rate - $\beta_{\alpha:incentive \times volatility}$ [S]: beta coefficient for distress on incentive × volatility learning-rate interaction  Mean fitted values for group-level intercepts (Model 3): - $\mu_{0,\alpha:volatility}$ = 0.30 (S1), 0.15 (S2) - $\mu_{0,\alpha:incentive}$ = 0.06 (S1), 0.31 (S2)
- **social_param:** $\beta_{\alpha:volatility}$, $\beta_{\alpha:incentive}$, $\beta_{\alpha:incentive \times volatility}$ — these are the group-level beta coefficients indexing how psychological distress (anxiety/depression) modulates learning rate adaptation across experimental conditions. Note: these are not strictly "social" parameters but rather individual-difference moderators of learning under socio-affective feedback.
- **social_param_name:** $\beta_{\alpha:volatility}$
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** PSIS-LOO (Pareto-smoothed importance sampling leave-one-out cross-validation, LOOIC)
- **how_model_fit:** Individual-level fit within a hierarchical Bayesian framework (group-level priors constrain individual parameters); Stan/rstan with HMC sampling.
- **data_type_fit_to:** Choice behavior

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** 
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Sample 1: N = 100 (89 with both sessions after exclusions; 49% female; mean age 20.34, SD = 2.52, range 17-26; Chinese undergraduates). Sample 2: N = 91 (88 usable, 66 with both sessions after exclusions; 55.7% female; mean age 23.91, SD = 5.13, range 18-42; Australian community sample with mild-moderate distress). 3 participants in Sample 2 excluded entirely.
- **population_category:** clinical
- **population_age_range:** 17–26
- **ecological_validity:** Use of socio-affective feedback (faces + verbal expressions) is more ecologically valid than monetary or shock stimuli used in prior work. However, feedback is still experimenter-delivered (not from a real social partner), stimuli are categorical rather than continuous (limiting parameter estimation precision), and the task is a standard two-armed bandit rather than a naturalistic social interaction.
- **eligibility_flag:** Borderline — the paper uses socio-affective stimuli (faces) as reinforcers in what is otherwise a standard non-social probabilistic learning task. The "social" element is the feedback modality, not the learning context or target. The agent does not learn about another person, nor from another person's actions — they learn stimulus-outcome contingencies using social stimuli as feedback. This is socio-affective reinforcement learning rather than social learning per se. Flag as: "borderline social context — social feedback stimuli but non-social learning target.
- **concerns:** - Parameter identifiability issues acknowledged by authors — correlations between generative and recovered parameters for volatility components were only ~0.51-0.52 for the winning model - Models 5 and 6 (with better LOOIC) were rejected due to poor parameter recovery, meaning the winning model may not capture important aspects of behavior - High correlations between anxiety and depression scales (r = 0.67-0.95) complicate interpretation of separate effects - Inconsistent results across the two samples - Binary categorical feedback limits parameter estimation precision - ~15% of participants excluded due to poor task performance - The "social" element is limited to feedback stimulus type; no genuine social interaction
- **limitations_reported:** Inconsistencies between our samples, along with issues of parameter identifiability complicated interpretation"; "moderately poor rates of task comprehension and completion"; "roughly 15% of participants in each sample were excluded from sensitivity analyses due to poor task performance"; "observed effects were small and unreliable"; "ecologically valid stimuli which often cannot be accurately quantified with respect to their subjective magnitude"; "issues with parameter recovery for Models 5 and 6"; "difficulties with recovering model parameters"; "correlations of this magnitude [between scales] are likely to cause issues when seeking to identify beta coefficients"; "we were limited in our ability to disentangle variance unique to depression and anxiety
- **limitations_categorized:** Parameter identifiability; inconsistent replication across samples; limited sample composition; poor task comprehension/completion rates; small effect sizes; high collinearity of predictor variables; limited ecological validity of categorical stimuli; limited generalizability  ---  ### WC CHECKLIST  1. **Design a good experiment**: Yes — task specifically designed to assess adaptive learning under volatility with socio-affective feedback across reward/punishment conditions. 2. **Design good models**: Yes — 6 models compared, representing competing hypotheses (base, lapse, session/block effects, outcome-dependent LR, choice kernel). 3. **Simulate, simulate, simulate**: Yes — used fitted parameters to generate 10 simulated datasets per model to assess parameter recovery before selecting the winning model. 4. **Fit the parameters**: Yes — hierarchical Bayesian estimation via Stan/HMC. 5. **Check parameter recovery**: Yes — simulated 10 datasets per model, compared generative to recovered parameters (correlations reported in Table 2 and supplement Table S1/S2). 6. **Check model recovery**: No — no confusion matrix or model recovery analysis reported (only parameter recovery within each model, not cross-model recovery). 7. **Fit real data and compare models**: Yes — iterative model comparison using PSIS-LOO/LOOIC across all 6 models. 8. **Validate the winning model**: Yes — posterior predictive checks (model accuracy per participant), sensitivity analysis excluding poorly fit participants. 9. **Analyze the winning model**: Yes — analyzed beta coefficients linking distress to learning-rate components; individual parameter estimates examined. 10. **Report results transparently**: Partial — code described as modified from hBayesDM; no explicit data/code sharing statement found.
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
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_anxiety
- pop_depression
- pop_healthy_adults
- rr_pop_anxiety
- rr_pop_depression
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = general
- spec_locus = source+target+context
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = G_uncertainty_volatility
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = volatility
- tax_rr_topic_volatility
- tax_topic_volatility
