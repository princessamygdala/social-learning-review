# Moutoussis et al. (2016)

- **study_id:** `a1a7bf1b4dc8e94bb_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Moutoussis, M., Dolan, R. J., & Dayan, P. (2016). How people use social information to find out what to want in the paradigmatic case of inter-temporal preferences. *PLoS Computational Biology, 12*(7), e1004965.
- **citation_short:** Moutoussis et al. (2016)
- **doi:** 10.1371/journal.pcbi.1004965
- **publication_type:** peer-reviewed journal
- **year:** 2016.0
- **field_of_study:** Psychology
- **affiliations_raw:** Institute signatureofBayesianupdatingisthatthedegreeoftastechangeshouldcorrelatewiththat; UCLCentreforComputationalPsychiatryandAgeingResearch,UniversityCollegeLondon,; CentreforNeuroimaging,UniversityCollegeLondon,London,UnitedKingdom,2 Max; etheirchoices,usuallyinthedirectionofconformity,whentheylearnwhatoth-; etheterm‘taste’inastrictsensetomeanthefunctiondirectlymapping; labilityStatement:Allrelevantdataare significance; ethemechanistic,suchasformsofpriming;theinstru-; etheirpreferencesinthelightofwhatotherschoose; emails: m.moutoussis@ucl.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Social influence learning / preference learning under social influence -- learning about one's own preferences (temporal discounting taste) through observing another's choices
- **study_focus_short:** Social influence learning / preference learning under social influence
- **learning_mode_description:** Learning about one's own temporal discounting preferences (taste for patience) from observing a peer's discounting choices. Self-preferences are treated as uncertain beliefs that are updated via Bayesian inference when social evidence becomes available.
- **task_description:** In the Delegated Interpersonal Discounting (DID) task, participants made temporal discounting choices (smaller-sooner vs. larger-later rewards) in Phase 1 to estimate their initial discounting preference (K1). In Phase 2, they learned a simulated peer's discounting preference by predicting the peer's choices and receiving feedback. In Phase 3, they again made choices for themselves and for the other, allowing assessment of preference shift.
- **task_paradigm:** Delay discounting / intertemporal
- **players:** Single agent (participant), single social target (simulated gender-matched peer)
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Monetary reward pairs (smaller-sooner vs. larger-later), text-based choices, gender-matched name for simulated other
- **method:** behavioural
- **method_full:** behavioural (large community sample)
- **main_result:** - Main Results:   - The preference-uncertainty (KU) model fit better than the preference-temperature (KT) model: 64% of participants had better log-likelihood under KU (Wilcoxon p = 1.7e-11; BIC difference = 740 over 738 participants)   - Participants shifted preferences toward the other's discounting rate; vast majority shifted toward other without overtaking (consistent with Bayesian updating)   - Preference shift correlated with preference uncertainty (u): partial r(shift, u | sigma_r) = 0.61, p < 1e-30   - Preference shift negatively correlated with reference dispersion (sigma_r): partial r(shift, sigma_r | u) = -0.56, p < 1e-30   - Age negatively correlated with preference shift: r(|m3-m1|, age) = -0.12, p = 0.0021   - Age effect fully mediated by preference uncertainty (u): u declined with age (r = -0.14, p = 7.7e-5); after controlling for u, age partial r for shifting = -0.06, p = 0.11   - Only 4.2% of participants showed strong evidence (BIC > 6) for processes not captured by the main model
- **effect_size:** - KU vs KT: BIC difference = 740 (N = 738); 64% of participants favored KU - Partial r(shift, sigma_r | u) = -0.56 - Partial r(shift, u | sigma_r) = 0.61 - r(K-T correlation in KT model) = 0.55 (abolished under KU: r = -0.03) - r(|shift|, age) = -0.12 - r(u, age) = -0.14 - Effect size for u difference (patient vs. impatient other): ~0.24 - Effect size for sigma_r difference: ~0.44
- **learning_from:** Other's choices (simulated peer's temporal discounting decisions); Source: other
- **learning_about:** Own temporal discounting preferences (self's taste for patience); Target: self  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Bayesian uncertainty-relevance preference shift (PS) model: KU backbone (log-normal preference sampling, Eq 3-4) + Bayesian updating of self-preference beliefs using other's choices via reference dispersion (sigma_r). 5 parameters: k_hat_s (modal self-preference), u_s (preference uncertainty), sigma_r (reference dispersion), tau_o (other-choice temperature), xi (lapse rate).
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "KT (preference-temperature)", "family": "Hyperbolic discounting + softmax", "n_params": 2, "metric": "BIC, log-likelihood"} - {"name": "KU (preference-uncertainty)", "family": "Hyperbolic discounting + log-normal sampling", "n_params": 2, "metric": "BIC, log-likelihood"} - {"name": "PS (preference-shift / uncertainty-relevance)", "family": "Bayesian belief updating (Gaussian)", "n_params": 5, "metric": "BIC"} - {"name": "Perturbation model (arbitrary k-shift)", "family": "KU + free shift parameter", "n_params": 3, "metric": "BIC"} - {"name": "KTC model (KT + constant C adjustment)", "family": "Hyperbolic + softmax + C", "n_params": 3, "metric": "BIC (in supplement)"}
- **model_mb_mf:** Bayesian
- **model_params:** - k_hat_s (m_s): modal log-discounting preference for self (mean fitted value: population mean m1 = -4.67) - u_s: preference uncertainty / standard deviation of log(K) belief distribution [S] -- drives social updating (population mean u1: SD = 1.82 for m; u median ~1.19 based on partial results) - sigma_r [S]: reference dispersion -- width of reference population distribution; quantifies epistemic trust / how relevant the other's preferences are to self (mean fitted = 1.13) - tau_o: temperature parameter for other-choice predictions (not social per se) - xi: lapse rate for self-choices (median = 0.015)
- **social_param:** sigma_r [S] -- reference dispersion parameter quantifying the degree to which the other's preferences are treated as relevant evidence about one's own preferences (epistemic trust); u_s [S] -- preference uncertainty that determines susceptibility to social influence (more uncertain = more shift)
- **social_param_name:** sigma_r
- **social_param_value:** 1.82
- **social_param_sd:** 1.82
- **social_param_range:** 
- **model_comparison_metric:** BIC (per-participant), log-likelihood, Wilcoxon signed-rank test across participants
- **how_model_fit:** individual-level-fit (MCMC with Laplace approximation initial conditions; empirical Bayes priors from population distribution in second pass)
- **data_type_fit_to:** choice behavior (temporal discounting choices across all three phases)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study)
- **key_regions:** N/A (behavioural study)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 738 (from 750 recruited; 5 withdrew, 4 excluded for wellbeing, 3 technical problems); ages 14-24; equal gender distribution; community sample from North London and Cambridgeshire (NSPN cohort)
- **population_category:** adolescents
- **population_age_range:** 14–24
- **ecological_validity:** Large community sample of young people (N=738, ages 14-24) is a strength for ecological validity and developmental relevance. However, the "other" is a simulated agent (not a real person), discounting choices are hypothetical (though one trial paid out for real), and the social influence context is artificial (participants told the other's choices but no genuine interaction occurs). The task is well-established (DID paradigm) with real monetary incentives for own choices.
- **eligibility_flag:** 
- **concerns:** (1) The simulated "other" is not a real person -- this limits ecological validity of the social learning component. (2) K1 estimation used T=1 approximation during the experiment itself (to set Ko), which the authors acknowledge may introduce bias. (3) Some asymmetry in shifting toward more patient preferences not fully explained by the model. (4) Hierarchical model fitting was approximate (empirical Bayes in stages rather than full hierarchical MCMC) due to dimensionality (3700 parameters). (5) The supplement (S1 Text, described as .DOCX) was not accessible for verification of additional analyses referenced in the paper.
- **limitations_reported:** individual variation will be more complex than our simple parametrization allowed"; authors note 5.4% of participants had very low taste uncertainty and may not have been well-captured; "one limitation of our experiment is that we have little independent evidence about the value of sigma_r"; authors acknowledge the slight overall bias toward more patient choices is not fully accounted for; authors note the need for future studies to "actively manipulate interpersonal context on the basis of specific hypotheses about factors that determine epistemic trust"; authors acknowledge the cross-sectional (not longitudinal) age design limits causal claims about developmental change in preference malleability
- **limitations_categorized:** model simplicity; limited ecological validity (simulated agent); no independent manipulation of epistemic trust; cross-sectional design (not longitudinal); approximate fitting procedure; unexplained asymmetry in preference shift direction; task simplicity
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
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: exact mean fitted values for u_s and sigma_r not reported as single summary statistics; partial information from text (sigma_r mean = 1.13; u mean for patient-other group = 1.27, impatient-other group = 1.11) -- MEDIUM confidence - wc_guidelines rule 3: rated Partial -- some simulation but no formal simulation study -- MEDIUM confidence - supplement (S1 Text): described as .DOCX but not available in papers folder; additional analyses (S3 section) referenced but not verified -- LOW confidence for supplement-dependent claims
- **cannot_find:** S1 Text supplement (supporting information .DOCX) -- not available in papers folder; no _Supplements file found. Additional analyses described in S1 Text sections S1-S3 could not be verified.
- **other_notes:** This is an important paper demonstrating Bayesian preference learning under social influence. The key innovation is treating preferences as uncertain beliefs that can be updated via social observation, rather than fixed traits subject to conformity pressure. The reference dispersion parameter (sigma_r) formalizes epistemic trust in an elegant way. The large community sample (N=738, ages 14-24) from the NSPN cohort is a notable strength. The finding that preference malleability decreases with age (mediated by decreasing preference uncertainty) has developmental significance. The paper builds on Garvert et al. (2015) which used a similar task with fMRI. Data shared as S1 Data. Supplement not accessible for this extraction.
- **re_extract_flag:** false (full text was available and read; however supplement S1 Text was not accessible -- flagged in cannot_find but main text extraction is complete)

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_healthy_adults
- rr_tax_mod_mentalizing_inference
- rr_tax_mod_social_info_search
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_domain_E_self_in_social_context
- tax_mod_mentalizing_inference
- tax_mod_social_info_search
- tax_model_bayesian
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = self_belief_confidence
- tax_rr_topic_self_belief_confidence
- tax_rr_topic_social_info_use
- tax_topic_self_belief_confidence
- tax_topic_social_info_use
