# Thompson & Westwater (2017)

- **study_id:** `a4d0cf163e6e71f5b_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Thompson, J. C., & Westwater, M. L. (2017). Alpha EEG power reflects the suppression of Pavlovian bias during social reinforcement learning. *bioRxiv*, 153668. https://doi.org/10.1101/153668
- **citation_short:** Thompson & Westwater (2017)
- **doi:** 10.1101/153668
- **publication_type:** preprint (biorxiv; not certified by peer review)
- **year:** 2017.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department of Psychiatry, Addenbrooke’s Hospital, University of Cambridge, Cambridge, UK; Department of Psychology, George Mason University, Fairfax, VA, USA; lable under; emails: jthompsz@gmu.edu
- **code_url:** 

## Computational level
- **study_focus:** Social reinforcement learning; Pavlovian-Instrumental interactions during learning from social (facial expression) feedback
- **study_focus_short:** Social reinforcement learning · Pavlovian-Instrumental interactions during learning from social
- **learning_mode_description:** - Learning mode: Learning cue-action associations from social feedback (facial expressions), with Pavlovian biases to approach reward-predicting cues and avoid punishment-predicting cues interfering with instrumental learning   - Learning from:     - Source type (social): other (faces of strangers)     - Source content (social): outcome (happy/angry facial expressions as reward/punishment)   - Learning about:     - Target type (non-social): world (cue-action contingencies)     - Target content (non-social): action/policy (correct Go/No-Go response to cue shapes)
- **task_description:** Participants performed a Go/No-Go learning task where four abstract cue shapes signaled whether to respond (Go) or withhold response (No-Go), with social feedback (happy/angry faces) or monetary feedback (+/- 25 cents) provided probabilistically (80/20). The design orthogonalized action (Go/No-Go) and outcome valence (Win/Avoid Loss), creating congruent (Go-to-Win, NoGo-to-Avoid) and incongruent (Go-to-Avoid, NoGo-to-Win) Pavlovian-Instrumental conditions.
- **task_paradigm:** Social conditioning
- **players:** Single agent (participant), no interactive partner (faces are non-contingent feedback stimuli)
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Abstract cue shapes (4 per task version), NimStim happy/angry facial expressions (18 male, 18 female), monetary symbols (+$/-$/=)
- **method:** EEG
- **method_full:** EEG (122-channel high-density)
- **main_result:** - Pavlovian bias present in both Social and Monetary tasks: accuracy higher in no-conflict than conflict conditions for Social (posterior mean slope = 10.72 [95% HDI: 4.17, 17.52]) and Monetary (posterior mean slope = 11.33 [0.11, 21.93]) - RTs faster for Go-to-Win than Go-to-Avoid for Social (posterior mean diff = -0.08 [-0.14, -0.01]) and Monetary (posterior mean diff = -0.16 [-0.31, -0.02]) - Pavlovian bias indices (PPB) above 50% for both tasks: Social PPB 95% HDI [56.68, 68.15]; Monetary PPB [56.59, 76.02] - Social and Monetary PPB not correlated across participants (posterior mean r = 0.13 [-0.79, 0.88]) - Conflict-specific alpha power negatively correlated with PPB in Social task (frontal/posterior cluster: 20-268ms; p = 0.005 corrected) - Conflict-specific theta power negatively correlated with PPB in Monetary task (frontal/parietal cluster: 200-528ms; p = 0.002 corrected) - Model-based Pavlovian parameter (π) correlated with PPB: Social (posterior mean r = 0.77 [0.40, 0.98]); Monetary (posterior mean r = 0.74 [0.45, 0.96]) - Winning computational model (M4a): alpha EEG modulates Pavlovian influence trial-by-trial for Social task; theta EEG modulates Pavlovian influence for Monetary task
- **effect_size:** Posterior mean slopes, HDIs, and correlations reported above (Bayesian framework; no frequentist effect sizes like Cohen's d reported)
- **learning_from:** Other (strangers' facial expressions — happy/angry faces as social reward/punishment feedback)
- **learning_about:** World (cue-action contingencies — which Go/No-Go response is correct for each cue shape)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** - Social task: M4a: Q + Go + Pavlovian * EEG(alpha), where Q(Go|s) = Q(Go|s) + b + (ρ * EEG_alpha + π) * V(S); 5 params: α, β, b, π, ρ - Monetary task: M4a: Q + Go + Pavlovian * EEG(theta), where Q(Go|s) = Q(Go|s) + b + (ρ * EEG_theta + π) * V(S); 5 params: α, β, b, π, ρ
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** 1. M1: Q-learning; family: Q-learning; n_params: 2 (α, β); metric: WAIC (Social: 4092, Monetary: 3525) 2. M2: Q + Go; family: Q-learning + Go bias; n_params: 3 (α, β, b); metric: WAIC (Social: 3661, Monetary: 3014) 3. M3: Q + Go + Pavlovian; family: Q-learning + Go + Pavlovian; n_params: 4 (α, β, b, π); metric: WAIC (Social: 3373, Monetary: 2747) 4. M4a: Q + Go + Pav * EEG (alpha); n_params: 5 (α, β, b, π, ρ); metric: WAIC (Social: 3358, Monetary: 2714) 5. M4a: Q + Go + Pav * EEG (theta); n_params: 5 (α, β, b, π, ρ); metric: WAIC (Social: 3371, Monetary: 2697) 6. M4b: Q * EEG + Go + Pav (alpha); n_params: 5; metric: WAIC (Social: 3364) 7. M4c: Q/Pav * EEG + Go (alpha); n_params: 5; metric: WAIC (Social: 3366) 8. M4b: Q * EEG + Go + Pav (theta); n_params: 5; metric: WAIC (Monetary: 2938) 9. M4c: Q/Pav * EEG + Go (theta); n_params: 5; metric: WAIC (Monetary: 2747)
- **model_mb_mf:** MF (both Pavlovian and Instrumental systems are model-free)
- **model_params:** - α: learning rate [0,1] - β: inverse temperature (softmax) - b: Go bias - π: Pavlovian bias strength [S] - ρ: EEG modulation of Pavlovian influence [S] (trial-by-trial weight of alpha/theta EEG on Pavlovian system)  (Note: Mean fitted parameter values are shown in Figure 4A as posterior distributions but exact numerical group means are not reported in text.)
- **social_param:** - π (Pavlovian bias): strength of Pavlovian influence on Go action values; V(S) represents learned stimulus value from social reward/punishment history - ρ (EEG modulation): weight of trial-by-trial EEG power on Pavlovian influence during conflict trials
- **social_param_name:** - π
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** WAIC (Widely-Applicable Information Criterion; Watanabe, 2013)
- **how_model_fit:** Individual-level fit via hierarchical Bayesian estimation (HMC/NUTS in Stan; group-level priors, individual-level random effects)
- **data_type_fit_to:** Choice behavior (trial-by-trial Go/No-Go responses) + EEG power (trial-by-trial alpha/theta band power as regressor in model)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (EEG study, not fMRI)
- **contrast:** - Conflict (Go-to-Avoid + NoGo-to-Win) vs. No Conflict (Go-to-Win + NoGo-to-Avoid) in theta, alpha, beta bands - Correlation of conflict-specific EEG power with PPB and model π parameter
- **key_regions:** Frontal alpha (8-14Hz) power associated with suppression of social Pavlovian bias (20-268ms post-cue); frontal/parietal theta (4-7Hz) power associated with suppression of monetary Pavlovian bias (200-528ms post-cue). EEG scalp topography — no MNI coordinates (EEG study).
- **key_regions_abbrev:** parietal
- **coordinates_peak:** unavailable — EEG study; no MNI/source-localized coordinates reported
- **analysis_type:** N/A (EEG scalp-level analysis with cluster-based permutation testing; no structural/functional MRI)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 20 (22 recruited, 2 excluded for psychological treatment; 15 female; M_age = 18.6, SD = 1.3; 13 White/Latino, 5 Asian, 2 African-American, 2 Biracial/Other)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low — abstract cue shapes paired with NimStim facial expression photographs (not real social interaction); no live social partner; within-subjects comparison with monetary task; lab-based EEG
- **eligibility_flag:** 
- **concerns:** - Very small sample (N=20) limits generalizability and statistical power - Preprint not peer-reviewed (bioRxiv 2017) - Social task uses static face photographs as feedback — limited ecological validity for social interaction - No parameter recovery or model recovery analyses reported - No simulation of models prior to fitting described - Exact numerical values of group-level posterior means for model parameters not reported in text (only shown in figure) - WAIC values reported but not all M4b/M4c models shown for both tasks (some cells appear missing in Table 1) - The paper treats social and monetary tasks separately with separate model fits, so direct statistical comparison of parameters across domains is limited
- **limitations_reported:** Authors acknowledge: the computational approach represents both Pavlovian and Instrumental systems as model-free, which is "likely an oversimplification, as model-based strategies play an important role in controlling behavior including learning from social feedback"; the study uses facial expressions only as social feedback, which is only one form of social signal; the EEG scalp-level analysis cannot definitively identify the neural sources of alpha vs. theta effects
- **limitations_categorized:** Task simplicity; limited ecological validity; model simplification (both systems model-free); limited neural source localization (EEG); sample size
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params fitted values: MEDIUM — posterior distributions shown in Figure 4A but exact group means not stated in text - wc_10 (transparency): MEDIUM — no mention of open data/code - No supplement available — confirmed no supplement file exists
- **cannot_find:** - Exact numerical group-level posterior mean values for all model parameters (only shown in figure) - Whether data or code are publicly shared - Whether this preprint was subsequently published in a peer-reviewed journal
- **other_notes:** - This is a bioRxiv preprint (June 2017), not peer-reviewed. Should check if a published version exists to avoid duplicate counting. - The paper treats Social and Monetary Go/No-Go as two separate tasks within the same participants (within-subjects design). Both are modeled separately. For the systematic review, the Social task is the primary focus. The winning model for the Social task uses alpha EEG, while the Monetary task uses theta EEG — this dissociation is the central finding. - No supplement was found in the papers folder. - Number of studies: 1 (single study with two task conditions analyzed separately but same participants)
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_PE_signal
- tax_rr_param_social_bonus
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_topic_social_approval_reward
