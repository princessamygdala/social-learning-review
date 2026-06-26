# Henco et al. (2020)

- **study_id:** `a9159d74bfbe6e921_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Henco, L., Diaconescu, A. O., Lahnakoski, J. M., Brandi, M.-L., Hormann, S., Hennings, J., Hasan, A., Papazova, I., Strube, W., Bolis, D., Schilbach, L., & Mathys, C. (2020). Aberrant computational mechanisms of social learning and decision-making in schizophrenia and borderline personality disorder. *PLoS Computational Biology*, *16*(9), e1008162. https://doi.org/10.1371/journal.pcbi.1008162
- **citation_short:** Henco et al. (2020)
- **doi:** 10.1371/journal.pcbi.1008162
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** InstituteforBiomedicalEngineering,UniversityofZurichandETHZurich,Zurich,Switzerland,5 Krembil; CentreforNeuroinformatics,CentreforAddictionandMentalHealth(CAMH),UniversityofToronto,Canada,; etherwiththe environmentalvolatility,bothinthenon-socialandthesocialdomain,butmoresointhelat-; UniversityofAugsburg,MedicalFaculty,Augsburg,Germany,11 InternationalMaxPlanckResearchSchool; InstituteofNeuroscienceandMedicine,Brain&Behaviour(INM-7),ResearchCentreJu¨lich,Ju¨lich,; InstituteofSystemsNeuroscience,MedicalFaculty,HeinrichHeineUniversityDu¨sseldorf,; UniversityofBasel,Basel,Switzerland,4 Translatio
- **code_url:** https://osf.io/8kfph/

## Computational level
- **study_focus:** Social learning and decision-making across psychiatric disorders (BPD, SCZ, MDD) -- probabilistic social inference in volatile environments; social cue weighting in decision-making; volatility learning in social vs. non-social domains.
- **study_focus_short:** Social learning and decision-making across psychiatric disorders (BPD, SCZ
- **learning_mode_description:** - Learning mode: Learning from social (gaze) and non-social (card color) cues about probabilistic contingencies in a volatile environment   - Learning from:     - Source type (social): other (animated face / gaze cue)     - Source content (social): action/policy (gaze direction toward winning card)     - Source type (non-social): world     - Source content (non-social): outcome (card color winning probability)   - Learning about:     - Target type (non-social): world     - Target content (non-social): state (probabilistic contingency of card winning & its volatility)     - Target type (social): other (animated face)     - Target content (social): state (predictive value / reliability of social gaze cue & its volatility)
- **task_description:** Participants chose between two colored cards to maximize monetary reward over 120 trials. An animated face gazed toward one card before each choice; the gaze's predictive validity and the card's winning probability varied independently across stable and volatile phases.
- **task_paradigm:** Volatility task (Behrens)
- **players:** Single agent (participant), single social target (animated face avatar)
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Animated face with gaze cues, colored cards (blue/green), binary feedback (correct/wrong), reward values (1-9)
- **method:** behavioural
- **method_full:** Behavioural
- **main_result:** - Overall performance difference between groups (F(3,108) = 7.504, p < .001, eta-squared = 0.167): SCZ and BPD performed worse than HC and MDD - Group x Cue Type interaction for response accuracy (F(3,108) = 4.820, p = .003, eta-squared = 0.108): BPD showed higher accuracy for social cue, HC and MDD for non-social cue - BPD showed reduced second-level precision weights (learning rates) compared to HC (d = 0.288) - BPD showed higher third-level precision weights (volatility learning) than all groups (BPD-HC: d = -0.390; BPD-MDD: d = -0.297; BPD-SCZ: d = -0.284) - Phase x Group interaction for volatility learning (F(3,108) = 5.962, p < .001, eta-squared = 0.071): BPD increased volatility learning more during volatile phases - Social weighting parameter z: BPD and SCZ showed higher z than HC (BPD-HC: d = -0.847; SCZ-HC: d = -0.691); BPD also higher than MDD (d = -0.818) - No transdiagnostic association of social anhedonia (ACIPS) with computational parameters (R-squared = 0.009, F(2,106) = 0.477, p = .622)
- **effect_size:** See above (Cohen's d and eta-squared reported inline).
- **learning_from:** Social: other (animated face gaze direction); Non-social: world (card color outcome)
- **learning_about:** Social: other (predictive value/reliability of social gaze cue); Non-social: world (winning probability of cards)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** HGF (3-level) with dual parallel hierarchies (social & non-social) + response model 1 (decision noise modulated by both social and non-social volatility estimates); parameters: omega_2card, omega_2gaze, omega_3card, omega_3gaze, z [S], beta, eta
- **model_family:** HGF
- **model_class:** PE learning / Belief updating
- **all_models_tested:** 1. HGF + Response Model 1 (decision noise ~ both volatilities): PXP = 0.173, XP = 0.914 -- WINNER 2. HGF + Response Model 2 (decision noise ~ social volatility): PXP = 0.119, XP = 0.019 3. HGF + Response Model 3 (decision noise ~ non-social volatility): PXP = 0.117, XP = 0 4. HGF + Response Model 4 (constant decision noise): PXP = 0.117, XP = 0 5. Sutton K1 + Response Model 4: PXP = 0.117, XP = 0 6. Rescorla-Wagner + Response Model 4: PXP = 0.122, XP = 0.068 7. Win-Stay-Lose-Shift: PXP = 0.117, XP = 0 8. Random responding: PXP = 0.117, XP = 0
- **model_mb_mf:** Bayesian
- **model_params:** - omega_2card: learning rate for non-social contingency (second level) - omega_2gaze [S]: learning rate for social contingency (second level) - omega_3card: learning rate for non-social volatility (third level) - omega_3gaze [S]: learning rate for social volatility (third level) - z [S]: social weighting factor -- weight of social vs. non-social prediction precision in decision-making - beta: inverse decision temperature (constant component) - eta: reward weighting parameter (linear vs. logarithmic reward weighting) (Mean fitted values reported in S5 Table -- supplement not accessible)
- **social_param:** z -- social weighting factor representing the propensity to weight social (gaze) over non-social (card) information in decision-making. Also omega_2gaze and omega_3gaze as social-domain learning rates.
- **social_param_name:** omega_2gaze
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Random-effects Bayesian Model Selection (BMS) using log model evidence (LME); protected exceedance probability (PXP), exceedance probability (XP), expected posterior probability (EXP_R)
- **how_model_fit:** Individual-level fit (per-participant parameter estimation using HGF toolbox v4.1, TAPAS)
- **data_type_fit_to:** Choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 116 (31 HC, 28 MDD, 29 SCZ, 28 BPD); age-matched groups; recruited from Max Planck Institute and university hospitals in Munich
- **population_category:** mixed
- **population_age_range:** 
- **ecological_validity:** Low-moderate. Task uses animated face gaze cue rather than real social interaction; gaze is a salient social cue but interaction is one-directional. No punishment for incorrect choices (only absence of reward). Probabilistic schedules are artificial.
- **eligibility_flag:** 
- **concerns:** - No non-social control cue (e.g., arrow) to fully dissociate social from general attentional effects on cue weighting - Most patients on psychopharmacological treatment during data acquisition - Different patient groups recruited from different clinical centers - Gender imbalance in SCZ and BPD groups - 16 subjects had higher model evidence for random responding than winning model (though exclusion did not change results) - PXP for winning model (0.173) is relatively low, though XP (0.914) is high - omega_3card could not be well recovered in parameter recovery analysis - Mean posterior parameter estimates only in supplement (S5 Table), which is not accessible
- **limitations_reported:** No non-social control cue to rule out general rather than specifically social information processing differences; most patients were in psychopharmacological treatment during data acquisition with different degrees of disorder severity and chronicity; different patient groups were assessed in different clinical centers; gender imbalance in the SCZ and BPD groups.
- **limitations_categorized:** Limited ecological validity; medication confound; recruitment site heterogeneity; gender imbalance; no non-social control condition
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
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params (mean fitted values): MEDIUM confidence -- mean posteriors reported only in S5 Table (supplement not accessible); parameter names and roles are clear from main text - omega_3card recovery: LOW confidence -- authors note this parameter could not be well recovered - PXP interpretation: MEDIUM confidence -- PXP = 0.173 is low; however XP = 0.914 is high, and the low PXP reflects the conservative correction for chance
- **cannot_find:** - Mean fitted parameter values (in S5 Table, supplement not accessible) - Exact prior configurations (in S3 Table, supplement not accessible) - Within-subject model comparison details (in S4 Table, supplement not accessible) - Demographic details and medication info (in S1/S2 Tables, supplement not accessible)
- **other_notes:** - Supplement (S1-S9 Tables, S1-S5 Figs) described as DOCX files but not available in the papers folder. Supplement not accessible -- mean parameter estimates and prior configurations cannot be verified. - This study uses the same "observing the observer" (OTO) paradigm as Sevgi et al. (2020) and Henco et al. (2020, Cortex) -- potential overlap should be checked for duplicate data. - The HGF toolbox v4.1 (TAPAS package) was used for all model fitting. - Data and code available at https://osf.io/8kfph/
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_bpd
- pop_depression
- pop_healthy_adults
- pop_schizophrenia
- rr_pop_bpd
- rr_pop_depression
- rr_pop_healthy_adults
- rr_pop_schizophrenia
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- rr_tax_mod_mentalizing_inference
- spec_depth = general
- spec_locus = source+context
- spec_source = partly
- spec_target = partly
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_mod_instructed
- tax_mod_mentalizing_inference
- tax_model_HGF
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_precision
- tax_param_social_weight
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = G_uncertainty_volatility
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_HGF
- tax_rr_model_family = HGF
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_uncertainty
- tax_rr_secondary_topic = volatility
- tax_rr_topic_social_uncertainty
- tax_rr_topic_volatility
- tax_social_nonsocial_comparison
- tax_topic_social_uncertainty
- tax_topic_volatility
