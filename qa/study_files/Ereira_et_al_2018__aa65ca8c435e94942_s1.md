# Ereira et al. (2018)

- **study_id:** `aa65ca8c435e94942_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Ereira, S., Dolan, R. J., & Kurth-Nelson, Z. (2018). Agent-specific learning signals for self-other distinction during mentalising. *PLoS Biology*, *16*(4), e2004752. https://doi.org/10.1371/journal.pbio.2004752
- **citation_short:** Ereira et al. (2018)
- **doi:** 10.1371/journal.pbio.2004752
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** mitsunrestricteduse,distribution,and psychopathologicaltraitsisofinterestasapotentialneurocomputationalpsychiatric; schools/ socialcognition,anditmaybeimpairedinmentalhealthdisorderswithsocialcognitive; UCLCentreforComputationalPsychiatryandAgeingResearch,UCL,London,United; CentreforHumanNeuroimaging,UCL,London,UnitedKingdom,3 Google; Universityof PEsandbeliefsattributedtoanotheragent; etheraself–otherdistinctiondependson; labilityStatement:AllMEGand; ethodsinPsychiatryandAgeing; emails: samuel.ereira.14@ucl.ac.uk
- **code_url:** https://osf.io/dxzgf/.All

## Computational level
- **study_focus:** Mentalizing learning / self-other distinction during belief updating. Investigates how fundamental neural learning signals (prediction errors, beliefs) are selectively attributed to self versus another agent, and whether agent identity is encoded intrinsically in these learning signals.
- **study_focus_short:** Mentalizing learning / self-other distinction during belief updating
- **learning_mode_description:** - Learning mode: Learning to track a drifting environmental state (Bernoulli parameter) from one's own perspective and simultaneously simulating another agent's belief about the same environment based on different (limited/misleading) information.   - Learning from:     - Source type (non-social): world       - Bernoulli outcomes (sensory samples from environment)     - Source content (non-social): outcome   - Learning about:     - Target type (social): other (another participant / "manager")       - Target content (social): state (mental state; belief about environment)     - Target type (non-social): self       - Target content (non-social): state (belief about environment)
- **task_description:** Participants observed a sequence of Bernoulli outcomes from a drifting probability distribution while inside a MEG scanner. They tracked their own belief about the underlying probability and simultaneously simulated a second participant's belief, who received only partial and sometimes misleading information; on intermittent probe trials, they reported either their own or the other agent's estimated probability.
- **task_paradigm:** Probabilistic ToM task
- **players:** Single agent (scanned participant), dyadic (another real participant as "manager" whose beliefs are simulated); also a non-social control version replacing the other person with a computer.
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Abstract Bernoulli outcomes (visual images: umbrellas/sun-shades or cherry-cola/diet-cola cans), cue images indicating trial type (privileged/shared/decoy), continuous probability scale for responses.
- **method:** MEG / behavioural
- **method_full:** MEG (magnetoencephalography) + behavioural
- **main_result:** - Model 8 (4-parameter RW with separate PEs for self and other) was the winning model for both SV and NSV (BMS exceedance probability > 0.99) - Self vs. other agent identity could be decoded from MEG spatial patterns of PE representation ~300 ms post-stimulus in the social version (SVM classification, P < 0.05 FWE-corrected) but not in the non-social version - Neural self-other distinction (SV - NSV decoding accuracy) correlated with behavioural self-other distinction (leak parameter lambda contrast): Spearman's rho = -0.43, P < 0.01 - Cross-validated linear regression: neural SOD predicted behavioural lambda (median Pearson r = 0.31, P = 0.039) - Neural self-other distinction correlated with subclinical psychopathological traits (PC1): R = 0.39, P = 0.017; SV alone: R = 0.43, P < 0.01 - Cross-validated prediction of PC1 from neural SOD: median Pearson r = 0.34, P = 0.04 - Temporal correlation between PC1 and signed belief decoding contrast significant at ~110 ms post-stimulus (P < 0.05 FWE)
- **effect_size:** - Neural-behavioural correlation: Spearman's rho = -0.43 - Cross-validated neural-behavioural prediction: median r = 0.31 - Neural-psychopathology correlation (SV-NSV): R = 0.39 - Neural-psychopathology correlation (SV only): R = 0.43 - Cross-validated neural-psychopathology prediction: median r = 0.34 - BIC model comparison relative evidence for lambda-containing models: Spearman's rho = 0.32
- **learning_from:** World; sensory Bernoulli outcomes (observations of environment) -- differentiated by trial type (privileged to self, shared, decoy to other)
- **learning_about:** Other (another participant's false belief about environment); self (own belief about environment)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** RW with 2 separate PE signals (PEs for self, PEo for other); 4 free parameters: 1 shared learning rate (alpha), 1 shared memory decay (delta), 2 temperature parameters (tau_s, tau_o). Model 8 in their model space.  Formula: - B(t) = B(t-1) + alpha * PEs(t) + delta * (0.5 - B(t-1)) - Bfb(t) = Bfb(t-1) + alpha * PEo(t) + delta * (0.5 - Bfb(t-1)) - PEs(t) = Outcome(t) - B(t-1) [on privileged/shared trials; 0 on decoy] - PEo(t) = Outcome(t) - Bfb(t-1) [on shared/decoy trials; 0 on privileged]
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning / Belief updating
- **all_models_tested:** - Model 1: Group A, averaging (last probe), 1 param (tau) - Model 2: Group A, averaging (last 10 trials), 1 param (tau) - Model 3: Group B, RW basic, 2 params (alpha shared, tau shared) - Model 4: Group B, RW + decay, 3 params (alpha shared, tau shared, delta shared) - Model 5: Group B, RW + decay, 4 params (2 alpha, tau shared, delta shared) - Model 6: Group B, RW + decay, 5 params (2 alpha, 2 tau, delta shared) - Model 7: Group B, RW + decay, 6 params (2 alpha, 2 tau, 2 delta)
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate): shared between self and other update equations; bounded [0, 1]; fitted value ~0.1 (from pilot) - delta (memory decay): shared; bounded [0, 1]; governs decay of beliefs toward 0.5 - tau_s (temperature, self probes): bounded [0.0001, 0.08]; governs choice stochasticity on self probe trials - tau_o (temperature, other probes) [S]: bounded [0.0001, 0.08]; governs choice stochasticity on other probe trials - lambda (leak parameter, in alternative models) [S]: bounded [0, 1]; governs erroneous cross-agent PE updating
- **social_param:** lambda (leak parameter) [S] -- indexes the degree to which prediction errors are erroneously attributed to the wrong agent's belief, capturing failure in self-other distinction. tau_o [S] -- temperature specific to other-perspective probe responses.
- **social_param_name:** tau_o
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (mean across subjects); also random-effects Bayesian model selection (exceedance probability > 0.99); also between-game parameter consistency (Spearman rank correlation of parameter estimates between SV and NSV).
- **how_model_fit:** individual-level-fit (MLE via fmincon, minimum 20 random restarts per model per subject)
- **data_type_fit_to:** choice behavior (continuous probability reports on probe trials)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (MEG study -- mass-univariate regression of PE magnitude against ERF; multivariate SVM classification/decoding of agent identity from spatial patterns)
- **contrast:** - |PEs| regressed against ERF on privileged + shared trials (SV and NSV separately) - |PEo| regressed against ERF on decoy + shared trials (SV and NSV separately) - SVM decoding of agent identity (self vs. other) from PE pseudotrials, signed belief pseudotrials, unsigned belief pseudotrials - SV vs. NSV contrast in classification accuracy - Neural SOD (SV - NSV) correlated with behavioural lambda (SV - NSV) - Neural SOD (SV - NSV) correlated with PC1 psychopathological traits
- **key_regions:** No specific brain regions localised (MEG sensor-space analysis). Group-level PE clusters found in parietal and occipital sensors (SV) and frontal and parietal sensors (NSV). Spatial mapping (S7 Fig) showed left posterior frontal sensors implicated for PE decoding; occipital sensors implicated for belief decoding. No source-level reconstruction performed.
- **key_regions_abbrev:** AI, parietal
- **coordinates_peak:** unavailable -- MEG sensor-space analysis only; no MNI/Talairach coordinates reported
- **analysis_type:** N/A (MEG, no structural neuroimaging; sensor-space analysis only)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 38 (21 female; 3 excluded from original 41 due to head movement and technical faults); mean age 26.6 (SD 6.9); ages 18-42; healthy adults
- **population_category:** healthy adults
- **population_age_range:** 18–42
- **ecological_validity:** LOW. Highly controlled lab task with abstract stimuli (Bernoulli outcomes). The "social" element involves inferring another person's belief about an abstract probability, not a naturalistic social interaction. The non-social control (computer) helps isolate social specificity. Cover stories (shop assistant/weather) add ecological framing. Participants had previously met the other participant and experienced their role.
- **eligibility_flag:** 
- **concerns:** - MEG sensor-space analysis limits anatomical inferences about brain regions involved - Absolute classification accuracy differences as small as ~1%, though statistical significance established via permutation - No source reconstruction performed -- cannot make claims about specific cortical regions - The social vs. non-social contrast (SV vs. NSV) also differs in cover story and framing, not just social content - No clinical population tested; psychopathology assessed only via subclinical questionnaire measures - Supplement not available as separate file (supporting information referenced as S1-S7 Figs embedded in paper)
- **limitations_reported:** Anatomical inferences are limited for data acquired in sensor space"; "the heterogeneity would suggest a diversity of cortical regions encoding PEs"; "our findings do not rule out a possibility that the brain uses additional mechanisms to distinguish self from other, for instance, with an explicit encoding of agent identity that is separate from low-level learning signals"; differences between SV and NSV "do not necessarily mean that subjects were not engaging in social computations in the NSV"; "it will be important in future work to clarify why this long latency separation occurs in a nonsocial context
- **limitations_categorized:** limited anatomical resolution (MEG sensor space); cannot rule out alternative mechanisms; social vs. non-social confounds; no clinical sample; subclinical measures only  ---  ### WC GUIDELINES  1. **Design a good experiment**: Yes -- novel paradigm specifically designed to dissociate self-other distinction from instrumental/observational learning confounds; social and non-social versions 2. **Design good models**: Yes -- 21 models tested spanning 3 groups (averaging, RW, non-selective updating) with systematic parameter variation 3. **Simulate, simulate, simulate**: Partial -- used simulated agent to generate trial sequences and test parameter correlations; model generated synthetic choice data qualitatively similar to real data (Fig 2B); but no formal simulation-based design optimization reported 4. **Fit the parameters**: Yes -- MLE via fmincon with multiple random restarts 5. **Check parameter recovery**: Yes -- parameter recovery reported (S3 Fig): simulated data from Model 8 with fitted parameters, then refitted; high correlations between true and recovered parameters 6. **Check model recovery**: No -- no confusion matrix or model recovery analysis reported 7. **Fit real data and compare models**: Yes -- BIC comparison across 21 models + random-effects Bayesian model selection 8. **Validate the winning model**: Partial -- generative performance shown (Fig 2B) comparing winning model to less successful model; between-game parameter consistency assessed; but no formal posterior predictive check 9. **Analyze the winning model**: Yes -- latent variables (PEs, beliefs) from winning model used extensively in neural analyses; leak parameter from alternative models analyzed for individual differences 10. **Report results transparently**: Yes -- data shared on OSF (https://osf.io/dxzgf/); numerical data for all figures provided as supporting information
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.0
- **wc_total:** 8.0

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
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_neural = shared
- spec_source = partly
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_domain_E_self_in_social_context
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_bayesian
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_decay
- tax_rr_primary_topic = mentalizing
- tax_rr_secondary_topic = self_other_boundary
- tax_rr_topic_mentalizing
- tax_rr_topic_self_other_boundary
- tax_topic_mentalizing
- tax_topic_self_other_boundary
