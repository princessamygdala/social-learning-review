# Charpentier et al. (2019)

- **study_id:** `a5dd8a3151396baf3_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Charpentier, C. C., Iigaya, K., & O'Doherty, J. P. (2019). Neuro-computational account of arbitration between imitation and emulation during human observational learning. *bioRxiv*, 828723. https://doi.org/10.1101/828723
- **citation_short:** Charpentier et al. (2019)
- **doi:** 10.1101/828723
- **publication_type:** preprint
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Division of Humanities and Social Sciences, California Institute of Technology, Pasadena, CA,; mitation learning was found in dorsomedial and dorsolateral prefrontal cortex; mitation, individuals learn by repeating actions that were most frequently; mitation involves learning to repeat the previous actions of; mitation has been proposed to be accounted for in a; lable in their environment from observing their; mitation and flexibly changed between the two; ether it is learning a new skill by
- **code_url:** https://osf.io/49ws3/

## Computational level
- **study_focus:** Observational learning -- arbitration between imitation (action copying) and emulation (goal inference) during observational learning, modulated by environmental uncertainty and volatility.
- **study_focus_short:** Observational learning -- arbitration between imitation (action copying) and
- **learning_mode_description:** - Learning mode: Learning which slot machine to choose by observing another agent's actions, arbitrating between imitating the agent's actions and inferring the agent's goals (emulation)   - Learning from:     - Source type (social): other (observed agent/partner)       - The partner performs actions that the participant observes     - Source content (social): action/policy (partner's slot machine choices)   - Learning about:     - Target type (non-social): world (which token is currently valuable / which slot machine to choose)     - Target content (non-social): state (world state -- which of 3 tokens is valuable) and action/policy (which slot machine to select)
- **task_description:** Participants observe another agent choose between slot machines containing different token distributions, knowing the agent has full information about which token is currently valuable. On 1/3 of trials, participants choose for themselves, using either imitation (repeating observed actions) or emulation (inferring which token is valuable from observed choices).
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant), single demonstrator (observed partner with full information)
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Slot machines with colored token probability distributions (green/blue/red), video of partner's button press, token outcomes
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Both action learning (imitation) and token learning (emulation) regressors significantly predicted choice in Study 1 (action: β = 0.865, T₂₉ = 5.94; token: β = 1.174, T₂₉ = 6.42) and Study 2 (action: β = 0.857, T₂₉ = 7.78; token: β = 0.843, T₂₉ = 5.42)   - Arbitration model (Model 7, pre-registered) outperformed all single-strategy models (OOS accuracy: 76.5% Study 1, 74.9% Study 2)   - Exploratory Model 10 (1-step imitation + emulation arbitration) outperformed Model 7 (OOS accuracy: 76.5% Study 1, 76.2% Study 2; lower iBIC)   - Arbitration weight higher in volatile/low-uncertainty trials (ω = 0.604) than stable/high-uncertainty trials (ω = 0.474), T₂₉ = 15.22   - Main effect of volatility F(1,29) = 61.2 and uncertainty F(1,29) = 267.3 on arbitration weight (Study 1)   - Emulation reliability (arbitration signal) encoded in vlPFC, TPJ, ACC (replicated across studies)   - Emulation update (KL divergence) tracked in dmPFC, preSMA, bilateral insula, IFG, dorsal striatum (replicated)   - Imitation update (action change) tracked in preSMA, bilateral inferior parietal, left dlPFC (replicated with exploratory Model 10)   - Imitation RL signals (pre-registered Model 7) did NOT replicate in Study 2
- **effect_size:** - Arbitration weight condition difference: T₂₉ = 15.22 (Study 1), T₂₉ = 10.97 (Study 2) - Volatility main effect: F(1,29) = 61.2 (Study 1), F(1,29) = 47.3 (Study 2) - Uncertainty main effect: F(1,29) = 267.3 (Study 1), F(1,29) = 124.8 (Study 2) - Model OOS accuracy: 76.5% (Model 10, Study 1), 76.2% (Model 10, Study 2)
- **learning_from:** Other (observed partner's slot machine choices/actions). Source: other.
- **learning_about:** World (which token is valuable) and own action policy (which slot machine to choose). Target: world.  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Arbitration Model 10: Bayesian emulation (multiplicative token value update, λ = 0.99) + 1-step imitation (repeat partner's last action), arbitrated by emulation reliability (Shannon entropy of emulation action values); 3 free params: β_em, β_im, δ
- **model_family:** MB/MF hybrid
- **model_class:** Other
- **all_models_tested:** [   {"name": "Model 1: Emulation (fixed λ=0.99)", "family": "Bayesian belief updating", "n_params": 1, "metric": "iBIC / OOS accuracy"},   {"name": "Model 2: Emulation (free λ)", "family": "Bayesian belief updating", "n_params": 2, "metric": "iBIC / OOS accuracy"},   {"name": "Model 3: Imitation RL (fixed α)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "iBIC / OOS accuracy"},   {"name": "Model 4: Imitation RL (dynamic α)", "family": "Rescorla-Wagner (dynamic LR)", "n_params": 3, "metric": "iBIC / OOS accuracy"},   {"name": "Model 5: Emulation RL (fixed α)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "iBIC / OOS accuracy"},   {"name": "Model 6: Emulation RL (dynamic α)", "family": "Rescorla-Wagner (dynamic LR)", "n_params": 3, "metric": "iBIC / OOS accuracy"},   {"name": "Model 7: Arbitration (EM+IM RL, fixed λ)", "family": "Hybrid Bayesian + RL arbitration", "n_params": 4, "metric": "iBIC / OOS accuracy"},   {"name": "Model 8: Arbitration (EM+IM RL, free λ)", "family": "Hybrid Bayesian + RL arbitration", "n_params": 5, "metric": "iBIC / OOS accuracy"},   {"name": "Model 9: Outcome RL", "family": "Rescorla-Wagner", "n_params": 2, "metric": "iBIC / OOS accuracy"},   {"name": "Model 10: Arbitration (EM + 1-step IM)", "family": "Hybrid Bayesian + 1-step imitation arbitration", "n_params": 3, "metric": "iBIC / OOS accuracy"} ]
- **model_mb_mf:** Hybrid -- emulation component is model-based (Bayesian inference over hidden state), imitation component is neither standard MF nor MB (1-step action copy). The paper explicitly argues these are distinct from MB/MF RL.
- **model_params:** - β_em: inverse temperature for emulation strategy (softmax). No mean fitted value reported. - β_im: inverse temperature for imitation strategy (softmax). No mean fitted value reported. - δ: arbitration bias parameter (δ > 0 = bias toward emulation, δ < 0 = bias toward imitation). No mean fitted value reported. - λ = 0.99 (fixed): trust in current token value estimates (emulation component; controls forgetting/volatility sensitivity) - [Derived] ω(t): arbitration weight = σ(R_EM(t) + δ), probability of relying on emulation [S] - [Derived] R_EM(t): emulation reliability, computed from normalized Shannon entropy of emulation action values [S]
- **social_param:** δ (arbitration bias) -- governs default tendency toward social inference (emulation) vs. social imitation. ω(t) (arbitration weight) -- trial-by-trial probability of relying on emulation (social goal inference) over imitation (social action copying), driven by emulation reliability. [S]
- **social_param_name:** δ
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Group-level integrated Bayesian Information Criteria (iBIC) via hierarchical Bayesian random-effects analysis; out-of-sample (OOS) predictive accuracy via 5-fold cross-validation
- **how_model_fit:** individual-level-fit (hierarchical Bayesian EM with Laplace approximation for iBIC; MLE with fminunc for OOS accuracy)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors derived from computational model)
- **contrast:** - Emulation reliability (arbitration signal) > 0 at slot machine onset (observe + play trials): vlPFC, TPJ, ACC, bilateral insula - Token KL divergence (emulation update) > 0 at feedback: bilateral anterior insula, bilateral IFG, preSMA/dACC, dmPFC, dorsal striatum, right inferior parietal - Action change (1-step imitation signal) at feedback: preSMA/SMA, bilateral inferior parietal, left dlPFC - Imitation reliability > 0 (pre-registered, Study 1 only): mOFC/vmPFC - Reliability difference (emulation - imitation) > 0: right anterior insula, ACC/dmPFC, right IFG, right angular gyrus - Chosen action value > 0 at play choice: mOFC (positive), preSMA (negative) - Previous action unavailable > available: preSMA, bilateral anterior insula, bilateral IFG, bilateral caudate, parietal regions
- **key_regions:** Emulation reliability (arbitration signal) in bilateral TPJ, right vlPFC, ACC, bilateral insula. Emulation update (KL divergence) in dmPFC, preSMA/dACC, bilateral anterior insula, bilateral IFG, dorsal striatum. Imitation update (1-step action change) in preSMA/SMA, bilateral inferior parietal lobule, left dlPFC. Chosen value in mOFC (positive) and preSMA (negative). Functional dissociation: emulation update more anterior/ventral in preSMA region; imitation update more posterior/dorsal in SMA.
- **key_regions_abbrev:** dStr, striatum, mPFC, dmPFC, dlPFC, OFC, dACC, ACC, TPJ, insula, AI, IFG, parietal
- **coordinates_peak:** Arbitration signal (emulation reliability): - ACC: 0, 39, 3 - Right vlPFC/insula: 53, 32, 1 - Right mid/sup temporal: 48, -21, -7 - Left postcentral/supramarginal: -58, -29, 18 - Right supramarginal/inferior parietal: 65, -31, 26 - Left fusiform gyrus: -25, -71, -15 - Right fusiform gyrus: 30, -69, -10 - dACC: 5, 17, 31 - Mid-cingulate cortex: 15, -21, 41 - Left insula: -40, -9, -7 - Left anterior insula: -43, 12, -12 - SMA/preSMA: 8, -9, 76 - Left pSTS/TPJ: -58, -54, 13  Emulation update (token KL divergence) at feedback: - Left anterior insula: -35, 17, -7 - Right anterior insula: 35, 19, -10 - Right IFG: 43, 9, 26 - Left IFG: -40, 7, 28 - Right caudate/thalamus: 8, -1, 8 - Left fusiform gyrus: -35, -56, -15 - Left inf-sup parietal/precuneus: -25, -71, 38 - Right inferior parietal: 50, -34, 46 - SMA/preSMA: 5, 22, 48 - Right TPJ/pSTS: 55, -44, 23  Imitation update (action change) at feedback: - SMA/preSMA: -5, 4, 66 - Left inferior parietal: -38, -54, 41 - Right inferior parietal: 50, -39, 48 - Left dlPFC: -45, 32, 31 - Left anterior insula: -35, 22, -10 - Left IFG: -45, 4, 26  Study 1 whole-brain clusters (Table S2): - Reliability difference: right anterior insula: 40, 17, -12; ACC/dmPFC: 13, 44, 26; right IFG: 45, 4, 21; right angular gyrus: 40, -74, 48 - Emulation reliability: right anterior insula: 43, 17, -12 - Imitation reliability (positive): mOFC/vmPFC/ACC: 3, 37, -7 - Imitation reliability (negative): right inferior parietal/angular gyrus: 48, -46, 58 - Token KL divergence: left anterior insula: -33, 14, -10; right IFG/precentral: 35, 9, 33; right anterior insula: 40, 19, -2; preSMA/dACC: -8, 19, 46; left IFG/precentral: -48, 7, 26; right supramarginal/inferior parietal: 53, -39, 46 - Token entropy: bilateral inferior parietal/angular gyrus/TPJ/precuneus: 38, -49, 46 (k=3755)
- **analysis_type:** both (whole-brain cluster-level FWE correction + pre-registered ROI analyses with 8 a priori ROIs)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** Study 1: N = 30 (12 females, 18 males; mean age = 31.67 ± 4.94); Study 2: N = 30 (12 females, 18 males; mean age = 31.2 ± 8.15; 3 excluded from original 33). Total N = 60.
- **population_category:** healthy adults
- **population_age_range:** M=31.67
- **ecological_validity:** Laboratory fMRI task with abstract slot machines and colored tokens. The "observed agent" was presented via pre-recorded video, not a live interacting partner. Low ecological validity -- no real social interaction, abstract stimuli, deterministic agent behavior. However, the 2x2 manipulation of volatility and uncertainty creates a richer environment than many OL tasks.
- **eligibility_flag:** 
- **concerns:** - This is a bioRxiv preprint (November 2019) -- not peer-reviewed at time of posting. Should check whether a peer-reviewed version has been published. - Mean fitted parameter values for β_em, β_im, δ are not reported in the main text or supplement. - The "observed agent" is fully deterministic (100% correct), reducing the social inference complexity. - The exploratory Model 10 was developed post-hoc after Study 1 results, though it was validated across both datasets. - Scanner was upgraded between studies (Trio to Prisma), introducing potential hardware confound, though acquisition parameters were kept similar.
- **limitations_reported:** Those results that did not replicate well in the 2nd fMRI dataset pertained to the imitation system, as implemented via our proposed action-based reinforcement-learning model"; acknowledged that imitation reliability was not robustly tracked in the brain; noted that further work is needed to establish causal role of identified regions via stimulation/inhibition; acknowledged that the revised model (Model 10) is exploratory and "subsequent work will ideally subject this new model and findings to further confirmatory replication"; noted risk of modeler/experimenter degrees of freedom in computational modeling and neuroimaging.
- **limitations_categorized:** partial replication failure (imitation signals); exploratory model not independently confirmed; no causal manipulation (TMS/lesion); limited ecological validity; deterministic observed agent; no parameter recovery reported; mean fitted parameters not reported
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM confidence -- mean fitted parameter values for β_em, β_im, δ are not reported anywhere in the main text or supplement. Only arbitration weight ω values are reported by condition. - publication_type: HIGH -- clearly marked as bioRxiv preprint. A peer-reviewed version may exist (should check for duplicate). - winning_model: MEDIUM -- The paper reports Model 7 as pre-registered winner but Model 10 (exploratory) as the overall best model. I report Model 10 as winning model because it outperforms on both OOS accuracy and iBIC across both studies.
- **cannot_find:** - Mean fitted values for β_em, β_im, δ (not reported in main text or supplement) - Individual parameter distributions or summary statistics beyond what is in Table 1 - Explicit statement of whether code/data are publicly shared (OSF project page referenced but sharing not confirmed in text)
- **other_notes:** - This paper may have a peer-reviewed published version (check DOI/title for journal publication to avoid duplicate counting). - The paper is notable for its within-paper replication design with pre-registration between studies. - The exploratory finding that 1-step imitation outperforms RL-based imitation has important theoretical implications for distinguishing OL strategies from experiential MB/MF RL. - Coordinates reported in MNI space. - Pre-registered ROIs defined as 8mm spheres from Neurosynth and prior literature.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_mentalizing_inference
- spec_context = partly
- spec_depth = structural
- spec_locus = source+target+context
- spec_neural = dedicated
- spec_source = partly
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_bayesian
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_MB_MF_hybrid
- tax_rr_model_family = MB_MF_hybrid
- tax_rr_param_MB_MF_balance
- tax_rr_param_precision
- tax_rr_primary_topic = imitation_emulation
- tax_rr_topic_imitation_emulation
- tax_social_nonsocial_comparison
- tax_topic_imitation_emulation
