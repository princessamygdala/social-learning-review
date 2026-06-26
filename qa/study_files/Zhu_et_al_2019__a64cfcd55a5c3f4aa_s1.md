# Zhu et al. (2019)

- **study_id:** `a64cfcd55a5c3f4aa_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Zhu, L., Jiang, Y., Scabini, D., Knight, R. T., & Hsu, M. (2019). Patients with basal ganglia damage show preserved learning in an economic game. *Nature Communications*, *10*, 802. https://doi.org/10.1038/s41467-019-08766-1
- **citation_short:** Zhu et al. (2019)
- **doi:** 10.1038/s41467-019-08766-1
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** SchoolofPsychologicalandCognitiveSciences;BeijingKeyLaboratoryofBehaviorandMentalHealth;IDG/McGovernInstituteforBrainResearch;Peking-; DepartmentofPsychology,UniversityofCalifornia,Berkeley,CA94720,USA; centeredintheOFCandincludingportionsofareas12,25,and47insome; CenterforLifeSciences,PekingUniversity,Beijing100871,China; SchoolofBusiness,UniversityofCalifornia,Berkeley,; ethods such as transcranial magnetic stimulation; UniversityofCalifornia,Berkeley,CA; ethatsocialfunctioningisspared; emails: mhsu@haas.berkeley.edu, lushazhu@pku.edu.cn
- **code_url:** 

## Computational level
- **study_focus:** Strategic learning in competitive economic games; dissociation between reinforcement learning and belief-based learning following basal ganglia vs. orbitofrontal cortex lesions
- **study_focus_short:** Strategic learning in competitive economic games
- **learning_mode_description:** - Learning mode: Learning to compete optimally in a Patent Race game by updating action values through received rewards and anticipation of opponents' strategies   - Learning from:     - Source type (social): other (anonymous opponents in population)       - Source content (social): action/policy (opponents' investment choices) and outcome (received and foregone payoffs)     - Source type (non-social): self       - Source content (non-social): outcome (own received payoff)   - Learning about:     - Target type (non-social): self       - Target content (non-social): action/policy (optimal investment strategy)
- **task_description:** In the Patent Race game, participants (Strong or Weak players) competed against anonymous opponents by choosing how much of their endowment to invest; the higher investor won a prize while both lost their invested amount. Participants completed 80 rounds each of a strategic condition (vs. human opponents) and a non-strategic condition (vs. a computer algorithm generating matched choices).
- **task_paradigm:** Auction task
- **players:** Single agent (participant), multi-target (anonymous opponents from a 16-person pool; random matching each round)
- **n_players:** multi-target (3+)
- **partner_type:** human (live)
- **stimuli:** Numerical endowments (5 or 4 units), potential prize (10 units), integer investment choices, payoff feedback (received and foregone)
- **method:** lesion / behavioural
- **method_full:** behavioural (lesion study)
- **main_result:** - BG patients showed preserved learning in the strategic condition, with sensitivity to both payoff and regret (payoff: beta = 0.74, regret: beta = -1.07), comparable to HC - BG patients showed impaired learning in the non-strategic condition, with no significant sensitivity to payoff or regret (payoff: beta = 0.26, n.s.; regret: beta = 0.10, n.s.) - OFC patients showed the opposite pattern: impaired in strategic (payoff: beta = 0.00, n.s.; regret: beta = 0.24, n.s.) but preserved payoff sensitivity in non-strategic (beta = 0.75) - EWA model fit (pseudo-R2): BG strategic = 0.45 +/- 0.02, HC strategic = 0.42 +/- 0.01 (n.s. difference); BG non-strategic = 0.26 +/- 0.02, HC non-strategic = 0.36 +/- 0.01 (significant difference) - Significant cohort x condition interaction: BG patients showed greater increase in EWA fit from non-strategic to strategic (increase = 0.20 +/- 0.03) vs. HC (increase = 0.06 +/- 0.02), bootstrapped 95% CI = (0.05, 0.22) - EWA significantly improved fit over baseline RL for BG patients in strategic condition (BIC improvement = 7.62 +/- 2.29, bootstrapped 95% CI = (1.28, 12.63)) but not in non-strategic condition (BIC = -1.68, n.s.)
- **effect_size:** - BG strategic payoff sensitivity: beta = 0.74, 95% CI (0.18, 1.30) - BG strategic regret sensitivity: beta = -1.07, 95% CI (-1.67, -0.49) - HC strategic payoff: beta = 0.86, 95% CI (0.56, 1.17) - HC strategic regret: beta = -0.45, 95% CI (-0.74, -0.15) - Pseudo-R2 BG strategic: 0.45 +/- 0.02; HC strategic: 0.42 +/- 0.01 - Pseudo-R2 BG non-strategic: 0.26 +/- 0.02; HC non-strategic: 0.36 +/- 0.01 - BIC improvement EWA vs RL, BG strategic: 7.62 +/- 2.29 - BIC improvement EWA vs RL, HC strategic: 7.36 +/- 2.50
- **learning_from:** Other (anonymous opponents); opponents' investment choices and foregone payoffs (social); own received payoff (non-social)
- **learning_about:** Self; own optimal investment policy  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Experience-Weighted Attraction (EWA) hybrid model (parameters: delta, phi, rho, lambda, N(0); nests RL as special case when delta=0, N(0)=1, rho=0)
- **model_family:** MB/MF hybrid
- **model_class:** PE learning / Belief updating
- **all_models_tested:** [{"name": "RL (Reinforcement Learning)", "family": "Rescorla-Wagner / RL", "n_params": 2, "metric": "BIC, pseudo-R2"}, {"name": "EWA (Experience-Weighted Attraction)", "family": "Hybrid RL + belief learning", "n_params": 5, "metric": "BIC, pseudo-R2"}, {"name": "Self-tuning EWA", "family": "Hybrid RL + belief learning (adaptive)", "n_params": "varies (some params replaced by functions of experience)", "metric": "BIC, pseudo-R2"}]
- **model_mb_mf:** MB/MF hybrid (EWA nests model-free RL and model-based belief learning)
- **model_params:** - delta: weight on foregone payoffs relative to received payoff (delta=0 reduces to pure RL; delta=1 is full belief learning) [S] - phi: discount factor that depreciates previous subjective values - rho: controls decay rate of N(t), the experience weight - N(0): initial value of the experience weight function - lambda (inverse temperature): controls choice stochasticity in softmax
- **social_param:** delta -- controls the extent to which the player weights foregone payoffs (derived from opponents' actions) relative to received payoff. Higher delta reflects greater reliance on belief-based / strategic learning about opponents.
- **social_param_name:** delta
- **social_param_value:** 0
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion); pseudo-R2 (relative to random choice model); out-of-sample hold-out prediction accuracy (first 60 trials for fitting, last 20 for test)
- **how_model_fit:** individual-level-fit (MLE per cohort per condition)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (lesion study, no fMRI conducted in this paper)
- **contrast:** N/A (lesion study; no neuroimaging contrasts computed)
- **key_regions:** Lesion locations only (no functional imaging): BG group -- maximal overlap in ventral rostral putamen (6/6), globus pallidus (4/6), caudate (2/6). OFC group -- Brodmann's areas 10, 11, 13, 14, with extensions to areas 12, 25, 47. No functional activation data reported.
- **key_regions_abbrev:** caudate, putamen, OFC
- **coordinates_peak:** unavailable -- not in main text or supplement (lesion study; no fMRI activation coordinates reported)
- **analysis_type:** N/A (no neuroimaging)  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 32 total (6 BG patients, 6 OFC patients, 20 healthy comparison subjects); 16 additional "pool players" for generating opponent choices. Demographic details in Supplementary Table 1.
- **population_category:** clinical
- **population_age_range:** 
- **ecological_validity:** Uses a stylized economic game (Patent Race) with hypothetical payoffs and anonymous random matching; designed to model competitive situations like commuter traffic or bazaar bargaining. Limited ecological validity due to hypothetical payoffs, abstract game structure, and lab setting. Population-level random matching minimizes reputation effects but also removes repeated-interaction dynamics present in real social life.
- **eligibility_flag:** 
- **concerns:** Very small patient sample sizes (N=6 per lesion group); unilateral BG lesions only (bilateral damage too rare/devastating) so intact contralateral BG may compensate; hypothetical (not real) payoffs used; OFC lesion group has heterogeneous damage extent including lateral OFC and white matter in some cases; potential model misspecification as acknowledged by authors; no neuroimaging data collected in this study (relies on prior fMRI findings from separate studies for neural interpretation); the "non-strategic" condition still involves learning from a sequence matched to human play, so it is not purely non-social in stimulus statistics.
- **limitations_reported:** Limited sample size of patient cohorts given inherent rarity of focal BG lesion; findings may be driven by damage to specific BG nuclei or adjacent regions; unilateral BG lesions only so intact contralateral BG may provide compensation; OFC effects were heterogeneous and sensitive to analytic choices, possibly reflecting variation in damage extent; potential model misspecification as EWA makes strong assumptions about how past experiences are integrated; unclear whether findings generalize to other types of social decisions including prosocial motivations, reciprocity, and social dominance
- **limitations_categorized:** sample size; lesion specificity; unilateral lesion limitation; limited generalizability; model misspecification risk; analytic sensitivity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM confidence -- exact fitted parameter values (means) for delta, phi, rho, N(0), lambda are not reported in the main text; the paper focuses on model comparison metrics (pseudo-R2, BIC) rather than individual parameter estimates, as authors explicitly note that parameter-level comparisons are problematic for lesion cohorts with poor model fits - wc_rule3 (simulate): MEDIUM -- power analysis used simulation but no dedicated model simulation/recovery analysis - coordinates_peak: N/A -- this is a lesion study with no fMRI data collected
- **cannot_find:** Exact mean fitted values for EWA parameters (delta, phi, rho, N(0), lambda) per cohort/condition; supplement not available to check for additional parameter tables; demographic details of lesion patients (referenced as Supplementary Table 1)
- **other_notes:** This paper is a lesion study, not an fMRI study. It builds on prior fMRI work (Zhu, Mathewson, & Hsu, 2012, PNAS) that identified dissociable neural signatures of RL and belief prediction errors in the putamen and mPFC during the same Patent Race task. The current study tests causal necessity of BG for these computations. The key finding -- that BG patients show preserved strategic learning but impaired non-strategic RL -- supports a model where BG receives higher-order learning signals from prefrontal cortex and is necessary for trial-and-error RL but not for belief-based strategic learning when compensatory cortical mechanisms are available. Supplement is referenced but was not found in the papers folder.
- **re_extract_flag:** false (full text was accessible and read; however, supplement was not available -- noted in cannot_find)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_bayesian
- tax_param_decay
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_MB_MF_hybrid
- tax_rr_model_family = MB_MF_hybrid
- tax_rr_param_MB_MF_balance
- tax_rr_param_PE_signal
- tax_rr_primary_topic = strategic_reasoning
- tax_rr_secondary_topic = competition
- tax_rr_topic_competition
- tax_rr_topic_strategic_reasoning
- tax_topic_competition
- tax_topic_strategic_reasoning
