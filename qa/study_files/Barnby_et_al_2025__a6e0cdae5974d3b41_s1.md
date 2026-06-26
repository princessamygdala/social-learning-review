# Barnby et al. (2025)

- **study_id:** `a6e0cdae5974d3b41_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Barnby, J. M., Nguyen, J., Griem, J., Wloszek, M., Burgess, H., Richards, L. J., Kingston, J., Cooper, G., Montague, P. R., Dayan, P., Nolte, T., Fonagy, P., & London Personality and Mood Disorders Consortium. (2025). Self-other generalisation shapes social interaction and is disrupted in borderline personality disorder. *eLife*, *14*, RP104008. https://doi.org/10.7554/eLife.104008
- **citation_short:** Barnby et al. (2025)
- **doi:** 10.7554/eLife.104008
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Department of Psychology, Royal Holloway, University of London, London, United; College London, London, United Kingdom; 5Anna Freud, London, United Kingdom;; University, Perth, Australia; 4Department for Clinical, Educational, and; Institute of Psychiatry, Psychology and Neuroscience, King’s College; Centre for Human Neuroscience Research, Virginia Tech, Blacksburg,; ethods employed are clever and sophisticated and the strength of; Division of Psychology and Language Sciences, University; Institute of Biological Cybernetics, Tübingen, Germany;; emails: joseph.barnby@kcl.ac.uk
- **code_url:** https://github.com/josephmbarnby/SocialTransfer_Barnby_etal_2024

## Computational level
- **study_focus:** Self-other generalisation in social learning; self-insertion (using own preferences to predict others) and social contagion (others' preferences shifting one's own) during observational social value orientation learning, and disruption in borderline personality disorder.
- **study_focus_short:** Self-other generalisation in social learning
- **learning_mode_description:** - Learning mode: Learning from observing a partner's social value orientation choices about the partner's reward allocation preferences, and how these observations shift one's own preferences.   - Learning from:     - Source type (social): other (anonymous virtual partner)     - Source content (social): action/policy (partner's binary allocation choices + correctness feedback)   - Learning about:     - Target type (social): other (anonymous virtual partner)       - If joint: marked as **joint** (relative reward preferences concern joint outcomes)     - Target content (social): state (mental state; social value preferences -- absolute reward α and relative/prosocial-competitive reward β)   - Secondary learning about (social contagion):     - Target type (non-social): self     - Target content (non-social): state (own social value preferences, shifted by exposure to partner)
- **task_description:** Participants played the "Intentions Game," a three-phase social value orientation task with virtual partners. In Phase 1, participants chose between two options for splitting points with an anonymous partner (36 trials); in Phase 2, they predicted a new partner's choices and received accuracy feedback (54 trials; partner calibrated to be ~50% different from participant); in Phase 3, they again chose allocations with a third anonymous partner (36 trials), allowing measurement of whether observing the Phase 2 partner shifted their own preferences.
- **task_paradigm:** Social allocation task
- **players:** Single agent (participant), sequential dyadic (3 anonymous virtual partners across 3 phases; Phase 2 partner algorithmically matched to be ~50% dissimilar)
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Binary forced-choice point allocation options (e.g., self=5/other=5 vs self=10/other=5), correctness feedback in Phase 2, slider ratings for partner attributions
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Healthy controls best fit by M1 (self-insertion + social contagion; exceedance probability = 0.98, frequency = 0.59); BPD best fit by M4 (neither self-insertion nor social contagion; exceedance probability = 0.86, frequency = 0.54)   - No group difference in predictive accuracy (CON = 77.2%, BPD = 72.7%; linear estimate = 2.44, 95% CI: -0.67, 5.54; t = 1.56, p = 0.12)   - BPD participants had lower absolute reward preferences (Δμ[αm_ppt] = -7.83, 95% HDI: -11.06, -4.75) and greater certainty over self-preferences (Δμ[ασ_ppt] = -0.89, 95% HDI: -1.01, -0.75; Δμ[βσ_ppt] = -0.32, 95% HDI: -0.60, -0.04)   - BPD participants used neutral, disintegrated priors about partner relative reward (Δμ[0 - βm_par] = -0.39, 95% HDI: -0.77, -0.05)   - BPD participants showed less belief updating (KL divergence) throughout Phase 2 vs CON (DKL[αm_par]: linear estimate = 0.40, t = 7.18, p < 0.001; DKL[βm_par]: linear estimate = 0.17, t = 3.06, p = 0.002)   - CON participants shifted preferences more between Phases 1 and 3 than BPD (M1: linear estimate = 0.67, 95% CI: 0.16, 1.19; t = 2.57, p = 0.011)   - Childhood trauma (CTQ) negatively associated with shifts in absolute reward preferences (r = -0.25, p[fdr] = 0.03); poor mentalising (MZQ) negatively associated with shifts in relative reward preferences (r = -0.26, p[fdr] = 0.03)   - Model recovery: simulated data reproduced model comparison (CON → M1, exceedance probability = 0.98; BPD → M4, exceedance probability = 0.85); parameter recovery ρ = 0.70-0.94
- **effect_size:** - Exceedance probability M1 for CON = 0.98; M4 for BPD = 0.86 - Δμ[αm_ppt] = -7.83, 95% HDI: [-11.06, -4.75] - Δμ[ασ_ppt] = -0.89, 95% HDI: [-1.01, -0.75] - Δμ[βσ_ppt] = -0.32, 95% HDI: [-0.60, -0.04] - DKL[αm_par] group difference: linear estimate = 0.40, t = 7.18 - DKL[βm_par] group difference: linear estimate = 0.17, t = 3.06 - M1 contagion group effect: linear estimate = 0.67, 95% CI: [0.16, 1.19] - CTQ → Δαm_ppt: r = -0.25 - MZQ → Δβm_ppt: r = -0.26 - Model simulation accuracy: median = 0.80; parameter recovery ρ = 0.70-0.94; model confusion ρ = 0.46-0.97
- **learning_from:** Other (anonymous virtual partner); partner's binary allocation choices with accuracy feedback
- **learning_about:** Other's social value preferences (absolute reward α and relative/prosocial-competitive reward β); secondarily, own shifted preferences (social contagion)
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Fehr-Schmidt utility + Bayesian belief updating. CON: M1 (self-insertion + social contagion; 6 free params: αm_ppt, βm_ppt, ασ_ppt, βσ_ppt, αref_par, βref_par). BPD: M4 (neither transfer; 8 free params: αm_ppt, βm_ppt, ασ_ppt, βσ_ppt, ᾱm_par, β̄m_par, αref_par, βref_par).
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "M1 (self-insertion + social contagion)", "family": "Bayesian belief updating", "n_params": 6, "metric": "HBI exceedance probability"},   {"name": "M2 (self-insertion only)", "family": "Bayesian belief updating", "n_params": 6, "metric": "HBI exceedance probability"},   {"name": "M3 (social contagion only)", "family": "Bayesian belief updating", "n_params": 8, "metric": "HBI exceedance probability"},   {"name": "M4 (neither transfer)", "family": "Bayesian belief updating", "n_params": 8, "metric": "HBI exceedance probability"},   {"name": "Beta model (M1 architecture, single β dimension only)", "family": "Bayesian belief updating", "n_params": 3, "metric": "HBI exceedance probability"} ]
- **model_mb_mf:** Bayesian
- **model_params:** - αm_ppt: Median of absolute reward preferences (free, Phase 1). CON mean = 18.41; BPD mean = 10.57 - βm_ppt: Median of relative reward preferences (free, Phase 1) [S]. CON mean = -7.50; BPD mean = -6.59 - ασ_ppt: SD of absolute reward preferences (free, Phase 1) - βσ_ppt: SD of relative reward preferences (free, Phase 1) [S] - αref_par: Prior beliefs SD over partner's absolute reward preferences (free, Phase 2) — belief flexibility - βref_par: Prior beliefs SD over partner's relative reward preferences (free, Phase 2) [S] — belief flexibility - ᾱm_par (M3/M4 only): New prior median over partner's absolute reward preferences (free, Phase 2) [S] - β̄m_par (M3/M4 only): New prior median over partner's relative reward preferences (free, Phase 2) [S]. BPD mean = -0.47 - αm_par: Posterior belief median over partner's absolute reward (derived, Phase 2) [S] - βm_par: Posterior belief median over partner's relative reward (derived, Phase 2) [S] - ασ_par: Posterior belief SD over partner's absolute reward (derived, Phase 2) [S] - βσ_par: Posterior belief SD over partner's relative reward (derived, Phase 2) [S] - α̃m_ppt (M1/M3 only): Shifted median absolute reward preferences (derived, Phase 3) - β̃m_ppt (M1/M3 only): Shifted median relative reward preferences (derived, Phase 3) [S] - α̃σ_ppt (M1/M3 only): Shifted SD absolute reward preferences (derived, Phase 3) - β̃σ_ppt (M1/M3 only): Shifted SD relative reward preferences (derived, Phase 3) [S]
- **social_param:** βm_ppt (relative reward preference — how much the participant cares about equality of outcomes with partner); β̄m_par (new prior over partner's relative reward); βref_par (flexibility of prior beliefs about partner's relative reward); social contagion mechanism (Eq. 7) shifting self-preferences based on precision-weighted combination of self and inferred partner beliefs.
- **social_param_name:** ᾱm_par
- **social_param_value:** -7.50
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Hierarchical Bayesian Inference (HBI) with random effects: group-level model frequency, individual-level model responsibility, protected exceedance probability
- **how_model_fit:** individual-level-fit (hierarchical Bayesian inference with group-level hyperparameters and individual-level parameters via HBI algorithm; Piray et al., 2019)
- **data_type_fit_to:** choice behavior (binary allocation choices in Phase 1 & 3; binary predictions in Phase 2)

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
- **sample_size:** N = 103 (53 healthy controls, 50 BPD); matched on age (CON mean = 30.0, BPD mean = 31.2), gender, education (~14.6 years), and social deprivation index. Ages not range-specified.
- **population_category:** mixed
- **population_age_range:** 
- **ecological_validity:** Lab-based online task (Intentions Game) with virtual partners whose behavior was algorithmically generated via server-side matching (~50% dissimilarity). Participants were incentivized via points and lottery. The task is abstract (point allocation), limiting ecological validity relative to real social interactions. Authors acknowledge this limitation: "it remains unclear whether these effects will persist in richer conditions, particularly when higher affective arousal and challenges to mentalising are present." The use of a novel server architecture for dynamic partner matching is a strength for experimental control.
- **eligibility_flag:** 
- **concerns:** Different winning models for each group (M1 for CON, M4 for BPD) makes direct parameter comparison across groups somewhat complicated, though the authors address this by also fitting all models to both groups. The virtual partner is algorithmically generated, not a real person. No neuroimaging data. Exploratory psychometric correlations did not all survive FDR correction when controlling for group status.
- **limitations_reported:** We focused on the ability of individuals to integrate their self-concept into beliefs about others. It is also possible that humans possess strong, salient representations of others (or groups of others) that serve as dominant templates for learning"; "The use of a salient, negative other-prior as a basis for learning was not measured in this study"; "While we predict that these processes will apply in more naturalistic settings, this has yet to be tested, and it remains unclear whether these effects will persist in richer conditions, particularly when higher affective arousal and challenges to mentalising are present"; "The action space and parameters governing choice in our study were quite simple — two actions influenced by two parameters. This was a deliberate computational choice to avoid overly complex action spaces"; "behaviour in tasks based on economic preferences may not have clinical validity
- **limitations_categorized:** limited ecological validity; task simplicity; limited generalizability (abstract economic task to real-world social behavior); alternative model structures not tested (salient negative other-prior); clinical validity of economic preference tasks uncertain
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 10
- **wc_total:** 10.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - preregistered (MEDIUM): No explicit mention of preregistration in the paper; defaulting to "Not reported" - sample_size (MEDIUM): Age range not explicitly stated; only means and SDs given
- **cannot_find:** - Supplement files: The paper references Supplementary files 1-5, which appear to be embedded supplementary tables within the eLife publication. No separate supplement file was available in the papers folder. The supplementary tables contain additional parameter values and statistical tests but the core extraction data (model formulas, parameter descriptions, model comparison) are fully reported in the main text.
- **other_notes:** This is an eLife publication with embedded figure supplements and supplementary files (tables). The paper introduces a novel "Intentions Game" paradigm and uses hierarchical Bayesian inference (HBI; Piray et al., 2019) for model fitting and comparison. Different models win for different groups (M1 for healthy controls, M4 for BPD), which is the core finding rather than a single winning model. Data and code are open-source on GitHub. The paper makes strong connections between computational findings and clinical theory about self-other representation in BPD.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_bpd
- pop_healthy_adults
- rr_pop_bpd
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = structural
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_E_self_in_social_context
- tax_mod_active_interaction
- tax_mod_mentalizing_inference
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_precision
- tax_param_social_weight
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = mentalizing
- tax_rr_secondary_topic = self_other_boundary
- tax_rr_topic_mentalizing
- tax_rr_topic_self_other_boundary
- tax_topic_mentalizing
- tax_topic_self_other_boundary
