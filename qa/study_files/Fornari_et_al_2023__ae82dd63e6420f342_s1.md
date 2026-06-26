# Fornari et al. (2023)

- **study_id:** `ae82dd63e6420f342_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Fornari, L., Ioumpa, K., Nostro, A. D., Evans, N. J., De Angelis, L., Speer, S. P. H., Paracampo, R., Gallo, S., Spezio, M., Keysers, C., & Gazzola, V. (2023). Neuro-computational mechanisms and individual biases in action-outcome learning under moral conflict. *Nature Communications*, 14, 1218. https://doi.org/10.1038/s41467-023-36807-3
- **citation_short:** Fornari et al. (2023)
- **doi:** 10.1038/s41467-023-36807-3
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** etherlandsInstituteforNeuroscience,KNAW,Meibergdreef47,1105BAAmsterdam,TheNetherlands; UniversityofAmsterdam,NieuweAchtergracht129-B,1018WTAmsterdam,TheNetherlands; ethepain-observationnetworkrepresentedpainprediction; College,1030ColumbiaAve,CA91711Claremont,CA,USA; SchoolofPsychology,UniversityofQueensland,; ethertheyprefertomaximize; mitigateharmstoothers1; Departmentof; emails: v.gazzola@nin.knaw.nl
- **code_url:** 

## Computational level
- **study_focus:** Moral conflict learning; learning action-outcome associations when outcomes for self (monetary gain) and others (shock/pain) conflict; individual differences in valuation weighting between self-benefit and other-harm.
- **study_focus_short:** Moral conflict learning
- **learning_mode_description:** - Learning mode: Learning from monetary outcomes to self and shock outcomes to another person about the value of abstract symbols under moral conflict.   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (monetary reward)     - Source type (social): other (confederate)       - Source content (social): outcome (pain/shock to other, conveyed via facial expressions)   - Learning about:     - Target type (non-social): world       - Target content (non-social): stimulus (symbol-outcome associations)     - Target type (social): other (confederate)       - Target content (social): outcome (expected shock intensity to other)
- **task_description:** Participants chose between two abstract symbols on each trial; one symbol was more likely associated with high monetary reward for self but painful shock to a confederate (lucrative), and the other with low monetary reward but non-painful shock (considerate). Participants had to learn these probabilistic symbol-outcome associations across blocks of 10 trials, with outcomes for money and shocks drawn independently at 80/20 probability ratios.
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), single target (confederate receiving shocks)
- **n_players:** single agent (1)
- **partner_type:** confederate
- **stimuli:** Abstract geometric symbols, monetary amounts (euros), pre-recorded videos of confederate's facial expressions in response to electrical stimulation (pain/no pain)
- **method:** fMRI / online / behavioural
- **method_full:** fMRI / behavioural / online
- **main_result:** - Main Results:   - Participants' choices were best described by a Rescorla-Wagner model tracking separate expected values for self-money and other-shocks (M2Out), with a weighting factor (wf) biasing expected values toward the individually preferred outcome   - M2Out outperformed M1 (combined value) and M2Dec (separate tracking, weighting only at decision) on critical devaluation (11th) trials (log-likelihood comparison, M2Out distribution non-overlapping with M1 and M2Dec; Fig. 5f)   - wf correlated with proportion of considerate choices (Online: Kendall's Tau = -0.82, BF10 = 2.35 x 10^23, p = 2.489 x 10^-26; fMRI: Kendall's Tau = -0.84, BF10 = 1.517 x 10^7, p = 8.481 x 10^-10)   - wf from learning task predicted donation in independent Helping task (Kendall's Tau = -0.47, BF10 = 76, p < 0.001)   - wf outperformed IRI empathy subscales and MAS in predicting helping (BFincl = 11.46, p = 0.009; all questionnaire BFincl < 0.7)   - Pain prediction errors (PES) loaded significantly on AVPS (t(24) = -5.46, p = 1 x 10^-5, BF10 = 1703) independently of wf (Tau = -0.007, p = 0.982, BF10 = 0.257)   - Both PES and PEM loaded on Reward Signature (PES: t(24) = 3.28, BF10 = 12.7; PEM: t(24) = 2.82, BF10 = 4.96)   - vmPFC showed PES signals dependent on wf (ventral cluster; FWEc = 181, punc < 0.001)   - Dorsal vmPFC showed PES signals independent of wf (FWEc = 167, punc < 0.001)   - Parameter recovery: wf accurately recovered (r(wf_simulated, wf_estimated) = 0.69, p < 10^-6, BF10 > 10^6)
- **effect_size:** - wf-considerate choices correlation: Kendall's Tau = -0.82 (Online), -0.84 (fMRI) - wf-Helping donation: Kendall's Tau = -0.47 - PES on AVPS: t(24) = -5.46, BF10 = 1703 - PES on RS: t(24) = 3.28, BF10 = 12.7 - PEM on RS: t(24) = 2.82, BF10 = 4.96 - wf BFincl for helping prediction: 11.46
- **learning_from:** Self (monetary outcome) and other (confederate's shock/pain outcome via facial expressions)
- **learning_about:** World (symbol-outcome associations for money and shock); other (expected shock to confederate)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** M2Out: RW with separate tracking of money and shock expected values, weighted at outcome phase. PE_M = (Out_M x wf) - EV_M; PE_S = (Out_S x (1-wf)) - EV_S; EV updated separately with LR_M and LR_S; Decision via softmax over (EV_M + EV_S). Parameters: wf [0,1], LR_M [0,1], LR_S [0,1], τ [0,5].
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "M0 (Random choice)", "family": "Null/random", "n_params": 0, "metric": "LOOIC + 11th trial log-likelihood"},   {"name": "M1 (Combined RW)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "LOOIC + 11th trial log-likelihood"},   {"name": "M2Out (Separate RW, weighting at outcome)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "LOOIC + 11th trial log-likelihood"},   {"name": "M2Dec (Separate RW, weighting at decision)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "LOOIC + 11th trial log-likelihood"},   {"name": "M2DO (Separate RW, weighting at both)", "family": "Rescorla-Wagner", "n_params": 5, "metric": "LOOIC + 11th trial log-likelihood"} ]
- **model_mb_mf:** MF (model-free; although devaluation sensitivity suggests goal-directed properties, the winning model is a Rescorla-Wagner model-free formulation with outcome-phase weighting)
- **model_params:** - wf [S]: weighting factor for monetary outcome relative to shock outcome; range [0,1]; wf closer to 0 = considerate (minimize harm to other), wf closer to 1 = lucrative (maximize self-money). Median Online ~0.5, fMRI ~0.3 (distributions shown in Fig. 6a). - LR_M: learning rate for money outcomes; range [0,1]; median ~0.25 (Online, from Supplementary Fig. 15) - LR_S: learning rate for shock outcomes; range [0,1]; median ~0.25 (Online, from Supplementary Fig. 15) - τ: inverse temperature; range [0,5]; controls exploration vs. exploitation
- **social_param:** wf (weighting factor): Captures individual differences in the relative weight placed on self-monetary outcomes versus other-shock outcomes. wf closer to 0 indicates a participant who prioritizes minimizing harm to the other person; wf closer to 1 indicates a participant who prioritizes maximizing their own monetary gain. This parameter biases prediction errors and expected values at the outcome phase and predicts costly helping in an independent task.
- **social_param_name:** wf
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 0–1
- **model_comparison_metric:** LOOIC (leave-one-out information criterion) for first 10 trials; direct log-likelihood comparison for 11th (devaluation) trial across 4000 posterior draws.
- **how_model_fit:** individual-level-fit (hierarchical Bayesian approach using RStan; individual parameters estimated within a hierarchical framework)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors); also multivariate neural signature analysis (AVPS, RS dot-product)
- **contrast:** - Outcome > 0 (main effect of outcome phase; FWEc = 903, punc < 0.001) - PES > 0 (shock prediction error; FWEc = 167 at punc < 0.001; also at punc < 0.01 FWEc = 950) - PES x (1-wf) (PES covarying with preference for shocks; FWEc = 181, punc < 0.001) - PEM > 0 (money prediction error; FWEc = 542, punc < 0.01) - PEM x wf (money PE covarying with preference; FWEc = 1642, punc < 0.01) - PES x LRS > 0 (shock value updating; FWEc = 121, punc < 0.001) - PES loading on AVPS (affective vicarious pain signature) - PES and PEM loading on RS (reward signature)
- **key_regions:** Pain prediction error (PES) independently of preference in dorsal vmPFC (ACC) and pain-observation network (AVPS); PES dependent on preference (wf) in ventral vmPFC (mid orbital gyrus, rectal gyrus) and left somatomotor cortex (BA4/3); money prediction error (PEM) independent of wf in striatum and ventral prefrontal cortex; PEM dependent on wf in right cerebellum, ventral temporal lobe, hippocampus; PES value updating (PES x LRS) in medial prefrontal cortex.
- **key_regions_abbrev:** striatum, vmPFC, mPFC, ACC, AI, hippocampus, cerebellum
- **coordinates_peak:** PES x (1-wf) (dependent on wf; FWEc = 181): - Mid Orbital Gyrus (R, Area s32): 6, 36, -14 - Insula (R): 28, 14, -18 - Rectal Gyrus (R): 20, 18, -12 - Precentral Gyrus (L, Area 4a): -36, -28, 66 - Postcentral Gyrus (L, Area 4p): -38, -22, 52 - Postcentral Gyrus (L, Area 1): -44, -26, 60  PES > 0 (independent of wf; FWEc = 167): - Middle Frontal Gyrus (R, Area Fp1): 26, 50, 4 - ACC (L, Area Fp2): -4, 50, -2 - ACC (R): 10, 38, -2 - ACC (L): -6, 46, -4 - Mid Orbital Gyrus (L): 0, 42, -8 - IFG p. Triangularis (L): -34, 40, 0 - Middle Frontal Gyrus (L): -36, 52, 4  PES x LRS > 0 (value updating; FWEc = 121): - (medial prefrontal regions; see Fig. 7e; specific coordinates in Supplementary Table 14 -- not fully extracted due to text limits)  Outcome > 0 (main effect; FWEc = 903): - Middle Occipital Gyrus (L): -44, -80, -2 - Fusiform Gyrus (L, Area FG3): -42, -52, -20 - Fusiform Gyrus (L, Area FG2): -42, -68, -18 - Fusiform Gyrus (R, Area FG3): 44, -54, -20 - Thalamus Parietal (L): -18, -28, -4 - Thalamus Temporal (L): -24, -26, -6 - Thalamus Visual (R): 24, -28, -4 - Middle Occipital Gyrus (L, Area hOc2): -18, -102, 0 - Insula (R): 42, 20, -2 - Superior Medial Gyrus (R): 4, 32, 52 - Superior Medial Gyrus (L): 2, 32, 42 - MCC (R): 4, 30, 38 - Posterior-Medial Frontal (R): 12, 26, 56 - ACC (R): 4, 36, 26 - Inferior Parietal Lobule (L, Area hIP3): -30, -52, 46 - Inferior Parietal Lobule (L, Area hIP2): -50, -42, 46 - Precuneus (L, Area 7P): 8, -76, 50 - ACC (R, Area 33): 6, 4, 28 - ACC (L, Area 33): -4, 2, 28
- **analysis_type:** whole-brain (FWE cluster-corrected at whole-brain level)  ---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 106 total (79 Online behavioural, ages 25 +/- 7 SD, 39 females; 27 fMRI, ages 37 +/- 17 SD, 27 females; 25 right-handed included in fMRI analysis). Online: 29 Considerate, 24 Lucrative, 26 Ambiguous. fMRI: 13 Considerate, 3 Lucrative, 11 Ambiguous.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate. Uses pre-recorded videos of a confederate's pain reactions rather than symbolic feedback, increasing ecological validity for pain-observation. However, it is a lab task with abstract symbols; the Online version involved deception about real-time shock delivery to a confederate who did not actually exist; the fMRI version also used deception (pre-recorded videos presented as live feed). The conflict is between financial gain and causing pain to another, which has real-world parallels but is simplified to a two-option probabilistic learning task.
- **eligibility_flag:** 
- **concerns:** - fMRI sample is small (N = 25 right-handed for imaging) and exclusively female, limiting generalizability - Online and fMRI samples differ significantly in age (25 vs. 37 years) and sex composition - The fMRI experiment only included ConflictNoDropout blocks (no devaluation trials), so the winning model (M2Out) was selected based on Online data and applied to fMRI data - Learning rates (LR_M, LR_S) had modest parameter recovery (Kendall's Tau ~0.25), and LR for the non-preferred outcome was poorly estimated - The devaluation (dropout) manipulation itself may have influenced participants to form separate representations, as acknowledged by the authors - Cluster-cutting threshold relaxed to punc < 0.01 for PEM and PEM x wf contrasts
- **limitations_reported:** Limited model comparison to RLT models; did not test ratio or logarithmic ratio models of valuation; some participants may not use RL at all and instead use heuristic rules; wf may not reflect stable moral preferences vs. situation-specific preference; dropout trials themselves may have influenced participants to separate representations; fMRI sample underpowered for detecting weak associations with wf (rho = 0.3 requires > 60 participants); model-free vs. model-based distinction not fully resolved
- **limitations_categorized:** limited model space; task simplicity; limited generalizability; small fMRI sample size; potential demand characteristics from task design; underpowered for individual-difference correlations
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
- **wc_rule10:** Yes
- **wc_score:** 9
- **wc_total:** 9.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_mb_mf: MEDIUM confidence. The winning model is a Rescorla-Wagner (model-free) formulation, but the devaluation sensitivity suggests goal-directed/model-based properties. The authors discuss this tension but do not definitively classify it. - LR_M and LR_S fitted values: MEDIUM confidence. Exact mean fitted values not clearly reported in main text; median ~0.25 inferred from Supplementary Fig. 15 description. Parameter recovery shows these are modestly recoverable. - Coordinates for PEM > 0, PEM x wf, and PES x LRS contrasts: MEDIUM confidence. PEM contrasts used relaxed threshold (punc < 0.01). Full coordinate tables for PEM and PES x LRS exist in supplement (Tables 12-14) but were only partially extracted due to text rendering.
- **cannot_find:** - Exact mean fitted parameter values for LR_M, LR_S, and τ (distributions shown in supplementary figures but numerical means not reported in text) - Full coordinate table for PES x LRS contrast (Supplementary Table 14; partially visible) - Full coordinate table for PEM x wf contrast (Supplementary Table 13; not fully extracted)
- **other_notes:** - This paper contains two studies (Online behavioural, N=79; fMRI, N=27) but they share the same core Conflict condition and are analyzed as complementary datasets within a single investigation. Treated as one study/one row. - The paper cites Lockwood et al. (2016, 2020) as key related work on prosocial learning and model-based vs. model-free learning for avoiding harm. - The authors developed a novel Rescorla-Wagner formulation (M2Out) that introduces a valuation weighting parameter (wf) at the outcome computation stage, allowing separate tracking of money and shock expected values with individually biased prediction errors. - Strong external validity demonstration: wf from the learning task predicted costly helping in an independent task better than standard trait questionnaires (IRI, MAS). - Data and code openly available on OSF.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = partly
- spec_target = partly
- tax_domain_F_affective_moral
- tax_mod_action_observation
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_temperature
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = moral_harm
- tax_rr_secondary_topic = prosocial_altruism
- tax_rr_topic_moral_harm
- tax_rr_topic_prosocial_altruism
- tax_topic_moral_harm
- tax_topic_prosocial_altruism
