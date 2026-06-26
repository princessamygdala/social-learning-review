# Bellucci & Park (2023)

- **study_id:** `a0c8ea17d52248403_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Bellucci, G., & Park, S. Q. (2023). Neurocomputational mechanisms of biased impression formation in lonely individuals. *Communications Biology*, *6*, 1118. https://doi.org/10.1038/s42003-023-05429-2
- **citation_short:** Bellucci & Park (2023)
- **doi:** 10.1038/s42003-023-05429-2
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ether and how loneliness affects impression for- both behavioral and computational mechanisms underlying; UniversitätsmedizinBerlin,CorporatememberofFreieUniversitätBerlin,Humboldt-UniversitätzuBerlin,andBerlin; DepartmentofDecisionNeuroscienceandNutrition,GermanInstituteofHumanNutrition(DIfE),Potsdam-Rehbruecke,; DepartmentofPsychology,RoyalHolloway,UniversityofLondon,EghamTW200EX,UK; mpirical anddishonesty,andhowneuralpatternsduringlearningrelateto; InstituteofHealth,NeuroscienceResearchCenter,10117Berlin,Germany; DepartmentofPsychologyI,UniversityofLübeck,; ether initial, negative; emails:
- **code_url:** https://osf.io/raf5h/.UnthresholdedstatisticalmapswereuploadedtoNeuroVault.org

## Computational level
- **study_focus:** Trust learning / impression formation — how first impressions and loneliness bias the integration of social information about others' trustworthiness during repeated social interactions.
- **study_focus_short:** Trust learning / impression formation
- **learning_mode_description:** - Learning mode: Learning from an adviser's honest/dishonest behavior about the adviser's trustworthiness over repeated interactions   - Learning from:     - Source type (social): other (adviser)     - Source content (social): action/policy (honesty/dishonesty in advice giving)   - Learning about:     - Target type (social): other (adviser)     - Target content (social): state (mental state; trustworthiness trait)
- **task_description:** Participants (advisees) played a card game with two advisers over 264 trials across 3 blocks; advisers gave advice about which card to pick, and participants received feedback about the adviser's honesty and their own monetary outcome, allowing trial-by-trial learning of each adviser's trustworthiness. Advisers' honesty changed across blocks (one initially honest, one initially dishonest) but was equated overall.
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant as advisee), multi-target (2 advisers; computerized but presented as real co-players)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Avatars representing advisers, card numbers (1–9 except 5), binary social feedback (honest/dishonest), binary nonsocial feedback (win/loss; green/red circles)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - First impressions biased advice-taking behavior across blocks (adviser × block interaction: F(2,68) = 6.03, p = 0.003, $\eta_p^2$ = 0.08) - Participants took less advice overall from initially dishonest advisers despite equal honesty rates (t(34) = −3.85, p < 0.001, Cohen's d = 0.65) - Negative first impressions induced a negativity bias in information weighting (dishonesty weighted more strongly for initially dishonest advisers: t(34) = −2.74, p = 0.010, Cohen's d = 0.46) - Loneliness correlated with more negative general expectations of others' trustworthiness (r(31) = −0.35, p = 0.045) - Loneliness correlated with stronger negativity bias for initially dishonest advisers (r(31) = 0.43, p = 0.012) - Reduced OFC activity fully mediated the relationship between loneliness and the negativity bias (indirect effect significant via bootstrap, direct effect c': $\beta$ = 0.01, SE = 0.01, p = 0.491) - OFC classified adviser identity by initial impression (accuracy = 60%, p = 0.015) - Stronger OFC-TPJ coupling associated with more positive trustworthiness judgments of initially dishonest advisers (r(33) = 0.34, p = 0.045), moderated by loneliness ($\beta$ = 0.30(0.15), 89% HDI [0.04, 0.57])
- **effect_size:** $\eta_p^2$ = 0.08 (adviser × block interaction); Cohen's d = 0.65 (overall advice-taking difference); Cohen's d = 0.46 (negativity bias for initially dishonest); Cohen's d = 0.39 (dishonest weighting by impression); r = −0.35 (loneliness × expectations); r = 0.43 (loneliness × negativity bias); r = −0.55 (OFC activity × negativity bias); r = 0.48 (OFC activity × loneliness); $\beta$ = −0.48 (Bayesian regression OFC → loneliness, 89% HDI [−0.75, −0.22])
- **learning_from:** Other (adviser); adviser's honest/dishonest behavior in advice giving (social information revealed as feedback)
- **learning_about:** Other (adviser); adviser's trustworthiness (trait inference from repeated behavioral signals)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Impression-dependent belief updating model with 2 social learning rates per adviser ($\tau$ = honesty LR, $\delta$ = dishonesty LR) + 1 $\beta$ (inverse temperature). M7.  Formula: $V_t = V_{t-1} + \tau \cdot S_t \cdot \mathbf{1}_t + \delta \cdot S_t \cdot (1 - \mathbf{1}_t)$  where $V_t$ = subjective value of trusting adviser on trial t; $S_t$ = social surprise signal ($I_t - V_{t-1}$); $\mathbf{1}_t$ = indicator function (1 if honest, 0 if dishonest); $\tau$ = honesty learning rate; $\delta$ = dishonesty learning rate. Choices via softmax: $p_t = (1 + e^{-\beta V_{t-1}})^{-1}$.
- **model_family:** Bayesian
- **model_class:** PE learning / Belief updating
- **all_models_tested:** - {"name": "M1", "family": "RW (single LR, no social/nonsocial distinction)", "n_params": "not specified exactly", "metric": "AIC + BMS exceedance probability"} - {"name": "M2", "family": "RW (single LR, social info only)", "n_params": "not specified exactly", "metric": "AIC + BMS exceedance probability"} - {"name": "M3", "family": "RW (single LR, nonsocial info only)", "n_params": "not specified exactly", "metric": "AIC + BMS exceedance probability"} - {"name": "M4", "family": "RW (2 LRs by nonsocial info type, no social distinction)", "n_params": "not specified exactly", "metric": "AIC + BMS exceedance probability"} - {"name": "M5", "family": "RW (1 LR, social info type distinguished)", "n_params": "not specified exactly", "metric": "AIC + BMS exceedance probability"} - {"name": "M6", "family": "RW (1 LR, social info type distinguished, variant)", "n_params": "not specified exactly", "metric": "AIC + BMS exceedance probability"} - {"name": "M7 (WINNING)", "family": "RW (2 social LRs: τ honesty, δ dishonesty)", "n_params": "5 (2 LRs × 2 advisers + 1 β)", "metric": "AIC + BMS exceedance probability"} - {"name": "M8", "family": "RW (2 LRs, social + nonsocial distinguished)", "n_params": "not specified exactly", "metric": "AIC + BMS exceedance probability"} - {"name": "M9", "family": "RW (2 LRs, social + nonsocial distinguished, variant)", "n_params": "not specified exactly", "metric": "AIC + BMS exceedance probability"} - {"name": "M10", "family": "RW (4 LRs, social × nonsocial fully crossed)", "n_params": "not specified exactly", "metric": "AIC + BMS exceedance probability"}
- **model_mb_mf:** MF
- **model_params:** - $\tau$ (honesty learning rate) [S] — estimated separately per adviser; controls weighting of honest social information; mean fitted value not reported in main text - $\delta$ (dishonesty learning rate) [S] — estimated separately per adviser; controls weighting of dishonest social information; mean fitted value not reported in main text - $\beta$ (inverse temperature) — captures choice noise; mean fitted value not reported in main text - Negativity bias operationalized as $\delta - \tau$ (not a free parameter, derived)
- **social_param:** $\tau$ (honesty learning rate) and $\delta$ (dishonesty learning rate) — separate learning rates for positive (honest) and negative (dishonest) social information from the adviser. Their difference ($\delta - \tau$) indexes the negativity bias in impression formation.
- **social_param_name:** $\tau$
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (transformed to log model evidence: -AIC/2) + random-effects Bayesian model selection (exceedance probability via spm_BMS)
- **how_model_fit:** individual-level-fit (MLE, AIC computed per participant; then group-level BMS)
- **data_type_fit_to:** choice behavior (advice-taking decisions)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + PPI (psychophysiological interaction) + MVPA (multivariate classification/regression)
- **contrast:** - Positive social surprise signals > baseline (bilateral TPJ, OFC, PCC; cFWE < 0.05, cluster-forming p < 0.001) - Negative social surprise signals > baseline (lateral PFC, inferior parietal lobule; cFWE < 0.05, cluster-forming p < 0.001) - Negativity bias × feedback regressor (reduced OFC and caudate; cFWE < 0.05, cluster-forming p < 0.005) - Loneliness × feedback regressor for initially dishonest adviser (reduced OFC; cFWE_svc < 0.05) - OFC seed PPI: OFC–TPJ coupling during social information encoding (cFWE_svc < 0.05) - MVPA: OFC activity classified adviser identity by initial impression (accuracy = 60%, p = 0.015)
- **key_regions:** Positive social surprise in bilateral TPJ, OFC, and PCC; negative social surprise in lateral PFC and inferior parietal lobule; negativity bias associated with reduced OFC and caudate activity; loneliness associated with reduced OFC engagement; OFC-TPJ functional coupling compensated negativity bias especially in lonelier individuals.
- **key_regions_abbrev:** caudate, lPFC, OFC, PCC, TPJ, parietal
- **coordinates_peak:** - OFC (loneliness × negativity bias mediation): −14, 26, −10 - Remaining coordinates (bilateral TPJ, OFC for surprise signals, caudate, lateral PFC, IPL, PCC) reported in Supplementary Tables S1 and S2 — supplement not accessible.
- **analysis_type:** both (whole-brain analyses with small-volume correction for OFC)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 35 (25 female; age: 22.37 ± 2.62 M ± SD); all right-handed, no neurological/psychiatric history; N = 33 for questionnaire-based analyses (2 lost due to technical problems). UCLA loneliness scores: M = 28.52, SD = 6.84, range 20–45.
- **population_category:** healthy adults
- **population_age_range:** 20–45
- **ecological_validity:** Moderate — the task uses a sequential interactive social paradigm with trial-by-trial learning (more ecological than vignette-based methods), but the "advisers" were computerized (though ~78% of participants believed they were real). Loneliness was measured as individual difference, not manipulated. Limited to advice-taking context; not fully naturalistic social interaction.
- **eligibility_flag:** 
- **concerns:** - Small sample size (N = 35, N = 33 for loneliness analyses) limits power for individual differences and brain-behavior correlations - Advisers were computerized, not real social agents — flagged as automated social agent - Loneliness not manipulated; correlational design limits causal inference - Exact n_params for most models (M1–M6, M8–M10) not clearly specified in main text - Mean fitted parameter values ($\tau$, $\delta$, $\beta$) not reported in main text - Supplementary Tables S1 and S2 (containing coordinate tables) not accessible — most peak coordinates unavailable
- **limitations_reported:** A potential limitation of this study is that we did not manipulate subjective feelings of loneliness"; authors note that advanced statistical methods like stratified sampling with a longitudinal approach should be employed to isolate loneliness dynamics from personality/psychoses; difficulty testing how biases lead to overly negative social expectations over time.
- **limitations_categorized:** no experimental manipulation of key variable (loneliness); sample size; limited ecological validity; cross-sectional design; no longitudinal data; potential confounds (personality, psychoses)
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
- **wc_rule10:** Yes
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `coordinates_peak`: LOW — only 1 of multiple reported coordinates available in main text; rest in Supplementary Tables S1 & S2 (not accessible) - `model_params` (mean fitted values): LOW — not reported in main text - `all_models_tested` (n_params for M1–M6, M8–M10): MEDIUM — exact parameter counts not specified for most models; only M7 structure clearly described - `wc_guidelines` rule 8: MEDIUM — cross-validation was on neural decoding, not behavioral model validation per se
- **cannot_find:** - Supplementary material (Tables S1, S2, Fig S1, S2) — no supplement file available; coordinates for most brain regions unavailable - Mean fitted values for $\tau$, $\delta$, $\beta$ - Exact number of free parameters for models M1–M6 and M8–M10
- **other_notes:** - Supplement not accessible (no _Supplements.txt or _Supplements.pdf found in papers folder). The paper references Supplementary Tables S1 and S2 for full coordinate tables, and Supplementary Fig S2 for model comparison results. - ~78% of participants believed they were playing with real partners despite computerized advisers. - The negativity bias ($\delta - \tau$) is a derived measure, not a free parameter — it indexes impression-consistent asymmetric weighting of social information. - Data and unthresholded statistical maps publicly available (OSF: https://osf.io/raf5h/; NeuroVault: https://neurovault.org/collections/15181/).
- **re_extract_flag:** false (full text accessible; supplement unavailable but flagged)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_bayesian
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_weight
- tax_param_valence_asymmetry
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = trait_impression
- tax_rr_secondary_topic = trust
- tax_rr_topic_trait_impression
- tax_rr_topic_trust
- tax_topic_trait_impression
- tax_topic_trust
