# Kuroda et al. (2022)

- **study_id:** `a1bfd75a72ec23693_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Kuroda, K., Ogura, Y., Ogawa, A., Tamei, T., Ikeda, K., & Kameda, T. (2022). Behavioral and neuro-cognitive bases for emergence of norms and socially shared realities via dynamic interaction. *Communications Biology*, *5*, 1379. https://doi.org/10.1038/s42003-022-04329-1
- **citation_short:** Kuroda et al. (2022)
- **doi:** 10.1038/s42003-022-04329-1
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** InstituteforResearchinBusinessandEconomics,FacultyofEconomics,MeijiGakuinUniversity,Minato-ku,Tokyo108-8636,Japan; etheperceptionofwhatmostpeople take the example of a weight scale with low validity but high; CenterforExperimentalResearchinSocialSciences,HokkaidoUniversity,Sapporo,Hokkaido060-0810,; DepartmentofMechano-Informatics,TheUniversityofTokyo,Bunkyo-ku,Tokyo113-0033,Japan; DepartmentofSocialPsychology,TheUniversityofTokyo,Bunkyo-ku,Tokyo113-0033,Japan; ether such neurocognitive mechanisms that underpin the formation of per-; DepartmentofRobotics,RitsumeikanUniversity,Kusatsu,Shiga525-
- **code_url:** https://osf.io/d2f73/

## Computational level
- **study_focus:** Norm learning / social influence learning — How perceptual norms emerge endogenously as shared realities through dyadic interaction, and how reciprocity (bilateral vs. unilateral influence) stabilizes covert psychophysical functions.
- **study_focus_short:** Norm learning / social influence learning
- **learning_mode_description:** - Learning mode: Learning from a partner's perceptual estimates (reciprocal social influence) about one's own psychophysical function (estimation weight) for a shared perceptual target   - Learning from:     - Source type (social): other (interaction partner / computer agent)     - Source content (social): action/policy (partner's dot-number estimates)   - Learning about:     - Target type (non-social): world (perceptual stimulus — number of dots)       - If joint: marked as **joint** (shared perceptual norm)     - Target content (non-social): state (psychophysical function / estimation weight calibration)
- **task_description:** Participants estimated the number of randomly presented dots (25–55) on screen. In interaction phases, they were paired with either a reciprocating (Sherif-type) or non-reciprocating (Asch-type) partner (real partner in Study 1; computer agent in Studies 2–3) and saw each other's estimates after each trial. Pre- and post-interaction solo phases measured changes in estimation weights and stability.
- **task_paradigm:** Conformity / Asch-style
- **players:** Single agent (participant), dyadic (partner: real participant in Study 1; computer agent described as another participant in Studies 2–3). Study 3: between-subjects 2x2 design (partner type x estimation bias).
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Random colored dots (25–55), numeric estimates displayed after each trial.
- **method:** fMRI / online / behavioural
- **method_full:** fMRI (Study 2), behavioural (Studies 1 and 3; Study 3 was online).
- **main_result:** - H1 — Covert psychophysical functions converge within real pairs through interaction (paired t(20) = 2.81, P = 0.011, d = 0.61); convergence greater for real vs. shuffled pairs (Welch's t(21.2) = 2.27, P = 0.034, d = 0.49) - H2 — Pair interaction stabilizes psychophysical function (sigma decrease, paired t(41) = 34.86, P < 0.001, d = 5.38 in pair condition; sigma increase in individual condition: t(41) = -31.37, d = 6.85; difference: Welch's t(42.4) = 46.02, d = 12.18) - H3 (fMRI) — Sigma decreased more after Sherif-type (d = 6.38) than Asch-type (d = 0.86) partner; difference: paired t(27) = 39.56, d = 7.48 - Time-series: Sim coefficient negative for Sherif-type partner (d = 0.65), positive for Asch-type (d = 0.60); difference: paired t(27) = 5.46, d = 1.03 - H4 (fMRI) — RTPJ tracked similarity with Sherif-type (t(27) = 2.63, d = 0.50) but not Asch-type (d = 0.13); difference: t(27) = 2.25, d = 0.42 - RTPJ beta correlated with post-Sherif stability (robust r = -0.48, P = 0.010) - RTPJ-DMPFC functional connectivity correlated with post-Sherif stability (robust r = -0.74, P < 0.001) - Online replication (H3): Partner type main effect F(1,212) = 388.03, P < 0.001, $\eta^2_p$ = 0.65; estimation bias main effect F(1,212) = 1373.32, $\eta^2_p$ = 0.87; interaction F(1,212) = 410.39, $\eta^2_p$ = 0.66  ---  ### ALGORITHMIC LEVEL
- **effect_size:** - H1 — Covert psychophysical functions converge within real pairs through interaction (paired t(20) = 2.81, P = 0.011, d = 0.61); convergence greater for real vs. shuffled pairs (Welch's t(21.2) = 2.27, P = 0.034, d = 0.49) - H2 — Pair interaction stabilizes psychophysical function (sigma decrease, paired t(41) = 34.86, P < 0.001, d = 5.38 in pair condition; sigma increase in individual condition: t(41) = -31.37, d = 6.85; difference: Welch's t(42.4) = 46.02, d = 12.18) - H3 (fMRI) — Sigma decreased more after Sherif-type (d = 6.38) than Asch-type (d = 0.86) partner; difference: paired t(27) = 39.56, d = 7.48 - Time-series: Sim coefficient negative for Sherif-type partner (d = 0.65), positive for Asch-type (d = 0.60); difference: paired t(27) = 5.46, d = 1.03 - H4 (fMRI) — RTPJ tracked similarity with Sherif-type (t(27) = 2.63, d = 0.50) but not Asch-type (d = 0.13); difference: t(27) = 2.25, d = 0.42 - RTPJ beta correlated with post-Sherif stability (robust r = -0.48, P = 0.010) - RTPJ-DMPFC functional connectivity correlated with post-Sherif stability (robust r = -0.74, P < 0.001) - Online replication (H3): Partner type main effect F(1,212) = 388.03, P < 0.001, $\eta^2_p$ = 0.65; estimation bias main effect F(1,212) = 1373.32, $\eta^2_p$ = 0.87; interaction F(1,212) = 410.39, $\eta^2_p$ = 0.66  ---  ### ALGORITHMIC LEVEL
- **learning_from:** Other (partner's dot estimates); social influence via shared estimates after each trial.
- **learning_about:** World / self (own psychophysical estimation weight for perceptual stimuli; convergence toward shared perceptual norm).
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** State-space model (hierarchical local-level model) for estimation weight stability (Eqs. 4–7: $w_i(t) \sim N(\mu_i(t), \sigma_{obs,i})$; $\mu_i(t) \sim N(\mu_i(t-1), \sigma_{\mu,i})$), combined with a time-series model decomposing estimation weight during interaction into Baseline + Atypicality + Similarity components (Eq. 11).
- **model_family:** State-space / HMM
- **model_class:** Belief updating
- **all_models_tested:** - Linear psychophysical model (Eq. 1: Est(t) = w_i * DotNum(t) + epsilon) — won over log-linear by AIC (Supplementary Table 1) - Log-linear psychophysical model (Eq. 3: Est(t) = w_i * log(DotNum(t)) + epsilon) - State-space model for sigma estimation (Eqs. 4–7) — fit via MCMC - Time-series model (Eq. 11 with Eqs. 12–13) — Baseline + Atypicality + Similarity decomposition, fit via MCMC - For the time-series model, 7 reduced models compared via WAIC (see Supplementary Fig. 5): Null, +Similarity, +Atypicality, +Atypicality+Similarity (full), and variants
- **model_mb_mf:** Bayesian (state-space model, not RL)
- **model_params:** - $w_i$ — estimation weight (psychophysical slope) - $\sigma_{obs,i}$ — observation noise - $\sigma_{\mu,i}$ — system noise (stability index) [S — key dependent variable reflecting social influence effect] - Baseline — estimation weight without social influence - $Coef_{Sim}$ — coefficient for similarity with partner [S] - $Coef_{Atyp}$ — coefficient for partner's atypicality [S] - $\gamma_{Sim}$, $\gamma_{Atyp}$ — drift terms for Sim and Atyp coefficients - $a_j$, $b_j$ (j=1...5) — Sherif-type partner's updating weights from partner's and participant's past estimates
- **social_param:** $Coef_{Sim}$ (Similarity coefficient) — how the participant updates estimation weight in response to closeness with partner's estimate in the preceding trial. Negative value = approaching partner. Also $\sigma_{\mu}$ as an index of stabilization modulated by social interaction (reciprocity).
- **social_param_name:** $Coef_{Sim}$ — coefficient for similarity with partner
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (linear vs. log-linear); WAIC (time-series model variants)
- **how_model_fit:** Individual-level fit via MCMC (rstan); posterior predictive checking performed (Supplementary Fig. 6)
- **data_type_fit_to:** Choice behavior (numeric dot estimates)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors from time-series model) + PPI (gPPI for RTPJ-DMPFC functional connectivity)
- **contrast:** - GLM1: Parametric modulation of Sim on RTPJ activity during interaction (Sherif > Asch) - GLM3: Parametric modulation of Est on DMPFC activity during interaction - gPPI: RTPJ seed, Sim-modulated connectivity with DMPFC - Functional localizer: ToM > non-ToM (for ROI definition)
- **key_regions:** RTPJ tracked estimation similarity with reciprocating partner; DMPFC tracked estimation output during interaction; RTPJ-DMPFC functional connectivity predicted post-interaction stabilization of psychophysical function (Sherif-type only).
- **key_regions_abbrev:** mPFC, dmPFC, TPJ
- **coordinates_peak:** Unavailable — not reported as MNI coordinates in main text. Individual ROIs were defined from a functional localizer; group peaks referenced in Supplementary Table 2, which is not accessible. Supplement not available for coordinate extraction.
- **analysis_type:** ROI (a priori individual ROIs from functional localizer for RTPJ and DMPFC)  ---  ### QUALITY
- **analysis_type_clean:** ROI
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** Study 1: N = 63 (42 pair condition, 21 individual condition; ages ~21–22). Study 2 (fMRI): N = 28 (30 scanned, 2 excluded; 13 men, 15 women; age 22.2 +/- 2.3). Study 3 (online): N = 216 (132 men, 84 women; age 23.0 +/- 2.1). All University of Tokyo students.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** The dot-estimation task is a simplified perceptual paradigm — ecologically limited as a model for real social norm formation. Partners in Studies 2–3 are computer agents, reducing social realism. However, the paradigm isolates reciprocity mechanisms and the design is cleverly motivated by classic Asch/Sherif paradigms. Anonymous interaction with no verbal communication limits generalizability to real-world norm emergence.
- **eligibility_flag:** 
- **concerns:** - Computer agents used in Studies 2–3 rather than real interaction partners (though Study 1 uses real pairs) - Very large effect sizes for stability comparisons (d > 5) suggest the sigma measure may be mechanically constrained - RTPJ/DMPFC ROIs defined individually from localizer, but group-level peak coordinates not reported in main text (referred to Supplementary Table 2, not accessible) - The "learning" is psychophysical calibration rather than traditional reward-based learning — borderline for computational models of social learning as typically conceived
- **limitations_reported:** Authors acknowledge: limited to perceptual norms and dot estimation (suggest extending to social/moral norms); anonymous interaction without verbal communication limits ecological validity; computer agents may not fully capture real social dynamics; the paradigm cannot distinguish informational vs. normative social influence fully.
- **limitations_categorized:** Limited ecological validity; task simplicity; artificial social agents; limited generalizability (perceptual domain only); no distinction between influence mechanisms.
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
- **wc_rule10:** Yes
- **wc_score:** 7
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `coordinates_peak`: LOW — Referred to Supplementary Table 2 for group peaks, supplement not accessible. Individual ROIs used but coordinates not reported in main text. - `model_family`: MEDIUM — Described as "state-space modeling approach" and "hierarchical local-level model" with MCMC estimation; classified as Bayesian hierarchical state-space model. - `learning_mode target_type`: MEDIUM — The target is arguably both "world" (perceptual stimulus) and "self" (own psychophysical function); classified primarily as world/joint since the convergence creates a shared norm.
- **cannot_find:** - MNI coordinates for RTPJ and DMPFC peaks (referred to Supplementary Table 2, supplement not accessible) - Exact WAIC values for model comparison (referred to Supplementary Fig. 5) - Parameter recovery or model recovery analyses
- **other_notes:** This paper bridges social psychology (Asch/Sherif paradigms) with computational neuroscience. The "learning" here is psychophysical calibration through social interaction rather than traditional reward prediction error-based learning. The state-space model is used descriptively to track stability rather than as a mechanistic learning model. Study 3 pre-registered at OSF. Data and code openly available. Supplement not accessible — coordinates and detailed model comparisons may be there.
- **re_extract_flag:** false (full text read; supplement not available but main text extraction is complete)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_mod_active_interaction
- tax_mod_vicarious_outcome
- tax_model_bayesian
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = state_space_HMM
- tax_rr_model_state_space_HMM
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_norm_conformity
- tax_rr_topic_social_info_use
- tax_topic_norm_conformity
- tax_topic_social_info_use
