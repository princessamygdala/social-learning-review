# Deng et al. (2023)

- **study_id:** `a69f025cbcb4e3d3f_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Deng, G., Ai, H., Qin, L., Xu, J., Feng, C., & Xu, P. (2023). Dissociated modulations of intranasal vasopressin on prosocial learning between reward-seeking and punishment-avoidance. *Psychological Medicine, 53*, 5415–5427. https://doi.org/10.1017/S0033291722002483
- **citation_short:** Deng et al. (2023)
- **doi:** 10.1017/S0033291722002483
- **publication_type:** peer-reviewed journal---
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** UniversityPress canbehaveprosociallyoregoisticallybylearningtheconsequencesoftheirdecisionsforothers; LaboratoryofAffectiveandSocialNeuroscience,MagneticResonanceImagingCenter,CenterforBrainDisorders; LaboratoryofAppliedExperimentalPsychology,NationalDemonstrationCenterforExperimental; University,Guangzhou,Chinaand5CenterforEmotionandBrain,ShenzhenInstituteof; FacultyofPsychology,BeijingNormalUniversity,Beijing,China;2ShenzhenKey; University,Shenzhen,China;3KeyLaboratoryofBrain,CognitionandEducation; ethathasbeeninvolvedinmodulatingvarioussocialbehaviorsinmammals,it; University),Guangzhou,Chin
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning — how individuals learn to benefit themselves vs. others under reward-seeking and punishment-avoidance frameworks, and how intranasal vasopressin (AVP) modulates this learning.
- **study_focus_short:** Prosocial learning
- **learning_mode_description:** - Learning mode: Learning from monetary outcomes (reward/no-reward, no-punishment/punishment) about which option benefits self or other in probabilistic reversal learning   - Learning from:     - Source type (non-social): self (participant's own choices and received feedback)     - Source content (non-social): outcome (monetary reward or punishment feedback)   - Learning about:     - Target type (social): other (next participant) — in prosocial conditions; self — in proself conditions       - If joint: not joint     - Target content (social): outcome (which option yields reward / avoids punishment for the beneficiary)
- **task_description:** In a probabilistic reversal learning task, participants chose between two options to either gain rewards (reward learning task) or avoid punishments (punishment learning task) for themselves or for another participant, with contingencies reversing after criterion performance.
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), single target (next participant; anonymous other). Between-subjects drug manipulation (AVP vs. PBO).
- **n_players:** single agent (1)
- **partner_type:** human (live)
- **stimuli:** Abstract visual stimuli (two options), monetary outcomes (win 5 cents / 0 cents in RLT; lose 0 cents / lose 5 cents in PLT), with 400 cents initial funding in PLT.
- **method:** EEG / pharmacological / behavioural
- **method_full:** EEG + behavioural + pharmacological (intranasal vasopressin vs. placebo)
- **main_result:** - Self-bias in punishment learning: accuracy higher for self than other in PLT in PBO group (F(1,102) = 5.311, p = .023, $\eta^2_P$ = 0.049)- Three-way Context x Target x Drug interaction on accuracy (F(1,102) = 5.231, p = .024, $\eta^2_P$ = 0.049)- AVP increased OP accuracy relative to OR (F(1,102) = 5.765, p = .018, $\eta^2_P$ = 0.053) and SR accuracy relative to OR (F(1,102) = 4.983, p = .028, $\eta^2_P$ = 0.047)- P-N model winning model across all four conditions (LOOIC comparison)- Four-way interaction on learning rates (F(1,100) = 78.122, p < .001, $\eta^2_P$ = 0.439)- Three-way interaction on $\eta_{neg}$: Context x Target x Drug (F(1,100) = 6.999, p = .009, $\eta^2_P$ = 0.065)- AVP increased $\eta_{neg}$ in OP condition relative to PBO (F(1,100) = 7.872, p = .006, $\eta^2_P$ = 0.073)- SPN three-way interaction (F(1,93) = 5.651, p = .019, $\eta^2_P$ = 0.057): AVP increased SPN for OP relative to OR- FRN three-way interaction (F(1,96) = 7.811, p = .006, $\eta^2_P$ = 0.075): AVP increased FRN difference wave for OP; PBO larger FRN for SP- P300 three-way interaction (F(1,96) = 5.332, p = .023, $\eta^2_P$ = 0.053): AVP increased P300 for SR- Theta four-way interaction (F(1,96) = 5.974, p = .016, $\eta^2_P$ = 0.059): AVP enhanced theta for OP and SR- AVP moderated SPN-$\eta_{neg}$ relationship in OP condition (b = 0.032, p = .005)- AVP moderated theta oscillation-($\eta_{neg}$ - $\eta_{pos}$) relationship in OP condition (b = -0.107, p = .036)
- **effect_size:** All effect sizes reported as partial eta-squared ($\eta^2_P$) for ANOVAs and unstandardized b for moderation models. See main_result above.
- **learning_from:** Self; own choice outcomes (reward/punishment monetary feedback).
- **learning_about:** Self (proself conditions) / other (prosocial conditions); which option maximizes reward or minimizes punishment for the beneficiary.---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Positive-Negative (P-N) model: RW with separate learning rates for positive ($\eta_{pos}$) and negative ($\eta_{neg}$) outcomes + softmax with bias ($\xi$) and inverse temperature ($\beta$). 4 parameters per condition.Formula: - V_{c,t} = V_{c,t-1} + $\eta_{pos}$(O_{t-1} - V_{c,t-1}), if O > 0 - V_{c,t} = V_{c,t-1} + $\eta_{neg}$(O_{t-1} - V_{c,t-1}), if O < 0 - Softmax: P(A) = 1 / (1 + exp(-$\beta$(V_A - V_B) - $\xi$))
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Fictitious update model", "family": "Rescorla-Wagner (counterfactual)", "n_params": 3, "metric": "LOOIC"} — parameters: $\alpha$ (learning rate), $\beta$ (inverse temperature), $\xi$ (bias) 2. {"name": "Experience-weighted attraction (EWA) model", "family": "EWA / Rescorla-Wagner variant", "n_params": 4, "metric": "LOOIC"} — parameters: $\phi$ (experience decay), $\rho$ (payoff decay), $\beta$ (inverse temperature), $\xi$ (bias) 3. {"name": "Positive-Negative (P-N) model", "family": "Rescorla-Wagner", "n_params": 4, "metric": "LOOIC"} — parameters: $\eta_{pos}$, $\eta_{neg}$, $\beta$ (inverse temperature), $\xi$ (bias) **[WINNING]**
- **model_mb_mf:** MF
- **model_params:** - $\eta_{pos}$: positive/reward learning rate [S — differs across self/other conditions] - $\eta_{neg}$: negative/punishment learning rate [S — differs across self/other conditions; key social parameter] - $\beta$: inverse temperature (computed via inverse logit) - $\xi$: indecision point / response bias  Mean fitted values: not reported numerically (only shown in figures). (MEDIUM — fitted values not tabulated)
- **social_param:** $\eta_{pos}$ and $\eta_{neg}$ — learning rates that differ between self-oriented and other-oriented (prosocial) conditions. The key finding is on $\eta_{neg}$: AVP increases negative learning rate specifically in the prosocial punishment-avoidance condition (OP).
- **social_param_name:** $\eta_{pos}$ and $\eta_{neg}$
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** LOOIC (Leave-One-Out Information Criterion) via hierarchical Bayesian analysis (hBayesDM package)
- **how_model_fit:** Individual-level fit via hierarchical Bayesian analysis (MCMC, 4 chains, 2000 post-warmup iterations per chain = 8000 valid samples) using hBayesDM package in R/Stan.
- **data_type_fit_to:** Choice behavior---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (EEG study, not fMRI)
- **contrast:** - SPN: anticipation stage, -200 to 0 ms at bilateral F5/F6, FC5/FC6; Context x Target x Drug interaction ($\eta^2_P$ = 0.057) - FRN: outcome evaluation, peak-to-peak difference wave (negative - positive feedback) at FCz, 220-320 ms; Context x Target x Drug interaction ($\eta^2_P$ = 0.075) - P300: outcome evaluation, mean voltage difference wave at CPz, 320-420 ms; Context x Target x Drug interaction ($\eta^2_P$ = 0.053) - Theta oscillation: 4-7 Hz at FCz, 100-300 ms post-feedback; four-way Frequency x Context x Target x Drug interaction ($\eta^2_P$ = 0.059) - Delta oscillation: <4 Hz at Cz, 320-420 ms post-feedback
- **key_regions:** Fronto-central (FCz) for FRN and theta oscillation; centro-parietal (CPz) for P300; bilateral frontal (F5/F6, FC5/FC6) for SPN; central (Cz) for delta oscillation. EEG scalp topography, not source-localized brain regions.
- **key_regions_abbrev:** AI, parietal
- **coordinates_peak:** N/A — EEG study; no MNI/Talairach coordinates reported. Electrode sites used: FCz, CPz, F5/F6, FC5/FC6, Cz.
- **analysis_type:** N/A (no neuroimaging; EEG with predefined electrode sites based on a priori hypotheses).---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 104 (54 AVP group [27 females], 50 PBO group [24 females]); ages 18-26. For EEG analyses: N reduced to 94-98 depending on component (6 excluded for incomplete EEG data, 2 for no trials available, 2 for left-handedness in SPN analysis). Two additional participants excluded from computational modeling (accuracy < 45%).
- **population_category:** healthy adults
- **population_age_range:** 18–26
- **ecological_validity:** Limited. Laboratory task with abstract stimuli and small monetary stakes (5 cents). The "other" is an anonymous next participant with no real interaction. Decisions are made in isolated self/other blocks, not interleaved. Pharmacological manipulation (intranasal AVP) is not naturalistic. However, the reward/punishment framing adds ecological relevance beyond pure reward learning.
- **eligibility_flag:** 
- **concerns:** - Mean fitted parameter values for the winning model not reported numerically (only in figures), making precise replication difficult - The "other" is described only as "the next participant" — minimal social context; no actual interaction - Between-subject drug design means individual differences could confound AVP vs. PBO comparisons - Multiple comparisons across many ERP components, oscillation bands, and conditions; correction strategy limited to Greenhouse-Geisser and Bonferroni post hocs - Formulas in supplement appear to have rendering issues (missing variable names due to PDF extraction) - No explicit model recovery / confusion matrix reported - Effect sizes for simple effects are partial eta-squared from omnibus ANOVA, not from focused contrasts
- **limitations_reported:** Authors do not have an explicit limitations section. From the discussion: consideration without tradeoffs between economic benefits and feelings of others may explain absence of altruism in PBO group; the nonsignificant difference toward learning performances and neural responses between PBO and AVP groups (only conditional three-way interaction significant, not main effect of drug).
- **limitations_categorized:** Limited ecological validity; no main effect of drug (only interaction); task simplicity (abstract stimuli, small stakes); no real social interaction; multiple comparisons; no explicit limitations section.
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
- **wc_rule10:** No
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `model_params` (mean fitted values): MEDIUM — values not reported numerically, only in figure - `limitations_reported`: MEDIUM — no dedicated limitations section; inferred from discussion - `wc_3` (simulate): MEDIUM — brief mention of simulation for parameter recovery, but details sparse - `wc_8` (validate winning model): MEDIUM — simulated choices mentioned but no formal posterior predictive check quantified
- **cannot_find:** - Exact mean fitted parameter values for $\eta_{pos}$, $\eta_{neg}$, $\beta$, $\xi$ per condition (shown only in figures) - Formal posterior predictive check results - Model recovery / confusion matrix - Data/code availability statement
- **other_notes:** The supplement contains additional detail on model equations (Fictitious update, EWA, P-N models), FRN measurement method, delta-band oscillation correlations with RT, and current source density analyses supporting electrode selection. The supplement also reports that in the PBO group, positive learning rate for self was significantly higher than for other in reward learning (t = 3.041, df = 101, p = .003; Supplementary Fig. S2), supporting the self-bias in reward learning not shown in accuracy. The Wilson & Collins (2019) paper is explicitly cited, indicating awareness of best practices. The paper uses the hBayesDM package with hierarchical Bayesian analysis, which is a rigorous fitting approach.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pharma_vasopressin
- pop_healthy_adults
- rr_pharma_vasopressin
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = target
- spec_neural = shared
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_topic_prosocial_altruism
