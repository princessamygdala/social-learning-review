# Fornari et al. (2023)

- **study_id:** `aa09d738ea4dd18f0_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Fornari, L., Ioumpa, K., Nostro, A. D., Evans, N. J., De Angelis, L., Speer, S. P. H., Paracampo, R., Gallo, S., Spezio, M., Keysers, C., & Gazzola, V. (2023). Neuro-computational mechanisms and individual biases in action-outcome learning under moral conflict. *Nature Communications*, *14*, 1218. https://doi.org/10.1038/s41467-023-36807-3
- **citation_short:** Fornari et al. (2023)
- **doi:** 10.1038/s41467-023-36807-3
- **publication_type:** peer-reviewed journal (nature communications)
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** etherlandsInstituteforNeuroscience,KNAW,Meibergdreef47,1105BAAmsterdam,TheNetherlands; UniversityofAmsterdam,NieuweAchtergracht129-B,1018WTAmsterdam,TheNetherlands; ethepain-observationnetworkrepresentedpainprediction; College,1030ColumbiaAve,CA91711Claremont,CA,USA; SchoolofPsychology,UniversityofQueensland,; ethertheyprefertomaximize; mitigateharmstoothers1; Departmentof; emails: v.gazzola@nin.knaw.nl
- **code_url:** 

## Computational level
- **study_focus:** Harm avoidance / moral conflict learning — how people learn action-outcome associations when outcomes for self (money) and others (shock) are in conflict, and how individual differences in moral preferences bias this learning.
- **study_focus_short:** Harm avoidance / moral conflict learning
- **learning_mode_description:** - Learning mode: Learning from monetary and shock outcomes about symbol-outcome associations under moral conflict   - Learning from:     - Source type (non-social): self — monetary reward outcomes     - Source content (non-social): outcomes (monetary gains)     - Source type (social): other (confederate) — shock/pain outcomes observed via facial expressions     - Source content (social): outcomes (pain/harm to other)   - Learning about:     - Target type (non-social): world — symbol-outcome contingencies for money     - Target content (non-social): stimulus (abstract symbol associations)     - Target type (social): world — symbol-outcome contingencies for shock to other     - Target content (social): stimulus (abstract symbol associations predicting harm to other)
- **task_description:** Participants chose between two abstract symbols on each trial; one symbol was associated with high monetary reward for self and painful shock to a confederate (80% probability), and the other with low reward and non-painful shock. Participants learned these probabilistic associations over blocks of 10 trials, with some blocks including "dropout" trials where money or shock outcomes were removed to probe separable representations.
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), single target (confederate receiving shocks via pre-recorded videos). Online: N=79; fMRI: N=27.
- **n_players:** network (5+)
- **partner_type:** confederate
- **stimuli:** Abstract geometric symbols (pairs), pre-recorded videos of confederate receiving electrical stimulation (facial pain expressions), monetary reward amounts (euros).
- **method:** fMRI / online / behavioural
- **method_full:** fMRI (Study 2) + behavioural/online (Study 1)
- **main_result:** - Choices best described by M2Out (RL model with separable expected values for money and shocks, weighted at outcome phase): M2Out outperformed M1 and M2Dec at predicting 11th trial devaluation choices (log-likelihood comparison; no overlap in posterior distributions across 4000 draws) - Preference subgroups: 37% Considerate, 30% Lucrative, 33% Ambiguous (Online); 48% Considerate, 11% Lucrative, 41% Ambiguous (fMRI) - Explicit report bias correlated with choice preference (Pearson's r = 0.51) - wf correlated with proportion of considerate choices: Kendall's Tau = -0.82 (Online), Tau = -0.84 (fMRI) - wf predicted donation in independent helping task: Kendall's Tau = -0.47, BF10 = 76 - wf predicted helping better than IRI or MAS trait questionnaires: BF_incl = 11.74 for wf; all other BF_incl < 0.7 - PES loaded significantly on AVPS: t(24) = -5.46, BF10 = 1703; loading did not depend on wf (BF10 = 0.257, evidence of absence) - PES and PEM both loaded positively on Reward Signature: PES: t(24) = 3.28, BF10 = 12.7; PEM: t(24) = 2.82, BF10 = 4.96 - vmPFC (ventral cluster) showed PES signals dependent on wf; dorsal vmPFC showed PES signals independent of wf - Parameter recovery: r(wf_simulated, wf_estimated) = 0.69, BF10 > 10^6
- **effect_size:** - Explicit report bias ~ considerate choices: r = 0.51 - wf ~ considerate choices: Kendall's Tau = -0.82 (Online), -0.84 (fMRI) - wf ~ helping task donation: Kendall's Tau = -0.47, BF10 = 76 - PES on AVPS: BF10 = 1703 - PES on RS: BF10 = 12.7 - PEM on RS: BF10 = 4.96 - Explicit report bias (Considerate, Conflict shock-money diff): Cohen's d = 1.54 - wf BF_incl for predicting helping: 11.74
- **learning_from:** Other (confederate's pain expression via video) and self (monetary reward outcome). Source: self + other.
- **learning_about:** World: symbol-outcome contingency probabilities for both self-money and other-shocks.  ---  ### 3. ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** M2Out — Rescorla-Wagner with separate EVs for money (EVM) and shock (EVS), weighting factor (wf) applied at outcome phase. PEM = OutM × wf - EVM; PES = OutS × (1-wf) - EVS; EVM = EVM + LRM × PEM; EVS = EVS + LRS × PES; Decision: softmax(τ × [EVM + EVS across options]).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** | Model | Family | n_params | Metric | |-------|--------|----------|--------| | M0 (Random choice) | Null/random | 0 | LOOIC + 11th trial log-likelihood | | M1 (Combined value RL) | Rescorla-Wagner | 3 (wf, LR, τ) | LOOIC + 11th trial log-likelihood | | M2Out (Separable, wf at outcome) | Rescorla-Wagner | 4 (wf, LRM, LRS, τ) | LOOIC + 11th trial log-likelihood | | M2Dec (Separable, wf at decision) | Rescorla-Wagner | 4 (wf, LRM, LRS, τ) | LOOIC + 11th trial log-likelihood | | M2DO (wf at both, α=0.5) | Rescorla-Wagner | 4 (wf, LRM, LRS, τ) + fixed α | 11th trial log-likelihood |
- **model_mb_mf:** MF (model-free RL, but with separable representations akin to goal-directed/devaluation-sensitive behavior)
- **model_params:** - wf [S]: weighting factor (0-1), captures relative weight of money vs. shock in learning; wf close to 0 = considerate (minimize harm), wf close to 1 = lucrative (maximize money). Distribution shown across participants: Online median ~0.5 (range 0-1); fMRI median ~0.3. - LRM: learning rate for money outcomes (0-1). Median ~0.25 (Online). - LRS: learning rate for shock outcomes (0-1). Median ~0.25 (Online). - τ: inverse temperature (0-5), controls choice stochasticity.
- **social_param:** wf [S] — weighting factor that balances the relative importance of self-money (wf) vs. other-shock (1-wf) in computing prediction errors. Captures individual moral preferences under conflict.
- **social_param_name:** wf
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 0–1
- **model_comparison_metric:** LOOIC (leave-one-out information criterion) for first 10 trials; direct log-likelihood of 11th trial (not included in fitting) for devaluation predictions. Bayesian hierarchical model comparison.
- **how_model_fit:** Individual-level fit within hierarchical Bayesian framework (RStan, hierarchical Bayesian approach with population-level hyperparameters). Fitted using RStan version 2.18.2, adapted from hBayesDM package.
- **data_type_fit_to:** Choice behavior (binary symbol choices)  ---  ### 4. IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors) — PES and PEM from M2Out entered as parametric modulators of the outcome regressor; EVS and EVM as parametric modulators of the decision regressor. Also multivariate neural signature analysis (AVPS, RS dot-product with parameter estimate maps).
- **contrast:** - Outcome > 0 (main effect of outcome phase) - PES > 0 (positive prediction error for shock, after wf-normalization) - PEM > 0 (positive prediction error for money, after wf-normalization) - r(PES, 1-wf): PES signals that depend on moral preference - r(PEM, wf): PEM signals that depend on moral preference - PES × LRS > 0: shock value updating signal - PES loading on AVPS (affective vicarious pain signature) - PES and PEM loading on RS (reward signature) - -EVS (decision phase)
- **key_regions:** Pain-observation network (AVPS) represented shock prediction errors independently of individual preferences (wf). Ventral vmPFC showed PES signals dependent on wf (moral preference bias in valuation). Dorsal vmPFC showed PES signals independent of wf. Left somatomotor cortex (BA4, BA3) had PES signals dependent on wf. Striatal and ventral prefrontal clusters for PEM independent of wf. Right cerebellum, ventral temporal lobe, hippocampus for PEM signals dependent on wf. Medial prefrontal cortex for PES × LRS (value updating).
- **key_regions_abbrev:** vmPFC, mPFC, AI, hippocampus, cerebellum
- **coordinates_peak:** - PES × (1-wf) — ventral vmPFC / mid orbital gyrus (right): 6, 36, -14 - PES × (1-wf) — right insula: 28, 14, -18 - PES × (1-wf) — right rectal gyrus: 20, 18, -12 - PES × (1-wf) — left precentral gyrus (Area 4a): -36, -28, 66 - PES × (1-wf) — left postcentral gyrus (Area 4p): -38, -22, 52 - PES constant — dorsal vmPFC / right middle frontal gyrus (Area Fp1): 26, 50, 4 - PES constant — left ACC: -4, 50, -2 - PES constant — left middle frontal gyrus: -36, 52, 4 - PES constant (p<0.01) — right MCC: 14, -14, 50 - PES constant — right superior temporal gyrus (Area TE 1.1): 40, -32, 14 - PES constant — right insula (Area Ig1): 38, -20, 4 - PEM constant — left thalamus (temporal): -12, -32, 6 - PEM constant — right thalamus (temporal): 8, -20, 14 - PEM constant — left parahippocampal gyrus: -16, -20, -20 - PEM constant — left cerebellum (Lobule VIIa crus I): -14, -72, -32 - PEM constant — right IFG (p. Orbitalis): 32, 38, -10 - PEM constant — right putamen: 30, 6, -6 - PEM constant — left MCC: 0, -4, 34 - PEM × wf — right cerebellum (Lobule VI): 8, -68, -16 - PEM × wf — right fusiform gyrus (Area FG3): 40, -48, -22 - PEM × wf — right hippocampus (thal: temporal): 20, -34, 2 - PES × LRS — left posterior-medial frontal: -6, -12, 72 - PES × LRS — right superior frontal gyrus: 24, 38, 36 - PES × LRS — right IFG (Area 45): 56, 30, 16 - PES × LRS — left ACC: -12, 52, 26 - PES × LRS — left middle frontal gyrus: -22, 34, 40 - Main effect outcome — left middle occipital gyrus: -44, -80, -2 - Main effect outcome — right insula: 42, 20, -2 - Main effect outcome — right superior medial gyrus: 4, 32, 52 - Main effect outcome — right ACC: 6, 4, 28
- **analysis_type:** Both (whole-brain FWE cluster-corrected analyses + multivariate neural signature analyses [AVPS, RS])  ---  ### 5. QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N=79 (Online; 25y ± 7 SD; 39 females, 40 males) + N=27 (fMRI; 37y ± 17 SD; 27 females, 0 males). fMRI neuroimaging analysis: N=25 (right-handed only). Total behavioral: N=106.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate. Uses pre-recorded videos of confederate facial pain expressions rather than symbolic feedback, enhancing ecological validity of the harm outcome. However, the probabilistic symbol-outcome learning task is still abstract and lab-based. Online participants were deceived about real-time confederate participation. The fMRI sample was all-female, limiting generalizability.
- **eligibility_flag:** 
- **concerns:** - fMRI sample is all-female (N=27, with only 25 right-handed for fMRI analysis) — limits generalizability - Age and sex distribution differ significantly between Online and fMRI samples - Online experiment used deception about real-time confederate; 4/79 reported not acting as if shocks were real - Dropout trials may have influenced participants to adopt separable representations rather than revealing pre-existing strategy - fMRI experiment did not include dropout trials, so model selection was based entirely on Online data and applied to fMRI data - Relatively small fMRI sample (N=25) limits power for detecting weaker associations with wf (adequately powered for ρ=0.5 but not ρ=0.3) - Learning rates showed modest parameter recovery (Kendall's Tau ~0.25)
- **limitations_reported:** We limited our model comparison to a number of hypotheses driven by RLT models. We did not test ratio or logarithmic ratio models of valuational representation"; "some of them, may not use a RLT model at all. Instead, they may use rules such as 'choose a symbol randomly, and only switch if you encounter × unfavorable outcomes in a row'"; "we used wf to address quantitative individual differences within our specific Conflict task"; "our evidence that choices are dominated by separable but biased representations hinges on dropout trials in our Online experiment, and our request for probability reports. We introduced these trials to rigorously reveal the nature of the learning... However, we must consider the possibility that these very trials also influenced participants to separate their representations"; "learning rates can be significantly recovered by M2Out, the correlation values are more modest than for wf and τ
- **limitations_categorized:** Limited model space tested; alternative non-RL strategies not tested; task-specificity of individual difference parameter; potential demand characteristics from devaluation trials; modest parameter recovery for learning rates; small fMRI sample; gender imbalance in fMRI sample; age differences across studies  ---  ### 6. WILSON & COLLINS CHECKLIST  1. **Design a good experiment**: Yes — task specifically designed to engage moral conflict learning with conflict/no-conflict conditions and devaluation probes 2. **Design good models**: Yes — 4 competing models (M0, M1, M2Out, M2Dec) representing distinct hypotheses about combined vs. separable representations and where weighting occurs; also tested M2DO 3. **Simulate, simulate, simulate**: Yes — parameter recovery simulations performed (4000 simulated participants, Supplementary Note 13); also simulated choices for ambiguous group characterization 4. **Fit the parameters**: Yes — hierarchical Bayesian fitting using RStan / hBayesDM framework 5. **Check parameter recovery**: Yes — full parameter recovery assessment reported (Supplementary Note 13; wf: Kendall's Tau = 0.69/Pearson's r; τ: Kendall's Tau = 0.53; LRS: Kendall's Tau = 0.25; LRM: Kendall's Tau = 0.24) 6. **Check model recovery**: No — no confusion matrix or model recovery analysis reported 7. **Fit real data and compare models**: Yes — LOOIC for first 10 trials + log-likelihood for out-of-sample 11th trial predictions 8. **Validate the winning model**: Yes — out-of-sample prediction (11th trial not included in fitting); external validity of wf with independent helping task (Kendall's Tau = -0.47, BF10 = 76) 9. **Analyze the winning model**: Yes — extensive analysis of wf parameter, its distribution, correlation with choices, external validity with helping task, and use in fMRI analysis 10. **Report results transparently**: Yes — code and behavioral data available on OSF (https://doi.org/10.17605/OSF.IO/RK8W4); raw fMRI data restricted due to privacy laws but processed fMRI data available  ---  ### 7. ADDITIONAL
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
- **flagged_fields:** - model_mb_mf: MEDIUM confidence — The model is technically model-free RL (Rescorla-Wagner), but the authors note that devaluation sensitivity (dropout trials) is typically associated with model-based/goal-directed behavior. They suggest participants may represent the nature of outcomes while using model-free updating. - Learning rate mean fitted values: MEDIUM confidence — exact mean/median values not explicitly reported in main text for all parameters; distributions shown in Supplementary Fig. 15 with median ~0.25 for LR. - preregistered: LOW confidence — no mention of preregistration found in paper or supplement.
- **cannot_find:** - Exact mean fitted parameter values for τ, LRM, LRS (distributions shown in figures but exact numerical means not reported in text) - Preregistration status not mentioned
- **other_notes:** - Two studies: Online (N=79, behavioral only, includes conflict/no-conflict and dropout conditions) and fMRI (N=27, conflict condition only + helping task). Both studies are analyzed as part of one paper — they complement each other rather than being independent replications. - The winning model M2Out was selected from Online data and applied to fMRI data for parametric modulator extraction. This cross-study application is justified by supplementary analyses showing M2Out wins in age/gender-matched subsamples. - The wf parameter has noteworthy external validity — it predicted costly helping behavior in a completely separate task, outperforming established trait questionnaires (IRI, MAS). - The authors note their work was inspired by Lockwood et al.'s prosocial learning paradigm. - Data shared on OSF; code shared on OSF.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = partly
- spec_depth = parametric
- spec_locus = source
- spec_neural = shared
- spec_source = partly
- spec_target = partly
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
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
