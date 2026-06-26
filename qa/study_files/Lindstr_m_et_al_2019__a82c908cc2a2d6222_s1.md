# Lindström et al. (2019)

- **study_id:** `a82c908cc2a2d6222_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lindström, B., Golkar, A., Jangard, S., Tobler, P. N., & Olsson, A. (2019). Social threat learning transfers to decision making in humans. *Proceedings of the National Academy of Sciences*, *116*(10), 4732–4737. https://doi.org/10.1073/pnas.1810180116
- **citation_short:** Lindström et al. (2019)
- **doi:** 10.1073/pnas.1810180116
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofEconomics,UniversityofZürich,8001Zürich,Switzerland;cSectionforPsychology,DepartmentofClinicalNeuroscience,Karolinska; DepartmentofSocialPsychology,UniversityofAmsterdam,1018WTAmsterdam,TheNetherlands;bLaboratoryforSocialandNeuralSystemsResearch,; Institutet,17177Stockholm,Sweden;anddDepartmentofClinicalPsychology,UniversityofAmsterdam,1018WTAmsterdam,TheNetherlands; ethreatassociationsandlearntoavoidthreateningandfear- morecommonthanever,asillustratedbyfootageofterrorand; University,Princeton,NJ,andapprovedJanuary15,2019(receivedforreviewJune18,2018); ether the social information
- **code_url:** https://osf.io/xfe72/

## Computational level
- **study_focus:** Threat conditioning transfer to decision making (Pavlovian Instrumental Transfer; non-social baseline)
- **study_focus_short:** Threat conditioning transfer to decision making (Pavlovian Instrumental Transfer
- **learning_mode_description:** - Learning mode: Learning from one's own direct experience of aversive outcomes (electric shocks paired with cues) about cue-threat associations, and how these Pavlovian associations transfer to instrumental decision making.   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (electric shock)   - Learning about:     - Target type (non-social): world (cue-outcome contingency)     - Target content (non-social): stimulus (CS+/CS- threat value)
- **task_description:** Participants first underwent Pavlovian threat conditioning where one colored shape (CS+) was paired with electric shocks and another (CS-) was not. They then made 70 binary choices between these same cues, where each choice was probabilistically punished with shocks; outcome contingencies reversed after 35 trials.
- **task_paradigm:** Fear conditioning (social)
- **players:** Single agent (participant), no social targets. Half assigned to No Change group (CS+ remains higher shock probability), half to Change group (CS+ has lower shock probability in decision phase).
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Colored geometric shapes (yellow and blue), electric shocks (aversive US)
- **method:** behavioural
- **method_full:** Behavioural (skin conductance + choice behavior)
- **main_result:** - Main Results:   - Transfer of Pavlovian conditioning to decision making: Change group had decreased probability of optimal choice relative to No Change group (β = −1.28, SE = 0.34, z = −3.81, 95% CI [−1.94, −0.62])   - Reversal of transfer effect after contingency switch (Group × Reversal interaction: χ²(1) = 6.86, p = 0.009)   - Simple effects contrast Change > No Change in Reversal phase (β = 0.62, SE = 0.34, z = 1.86, 95% CI [−0.033, 1.29])   - Successful threat conditioning confirmed by SCR (CS+ > CS−, t(38) = 2.33)
- **effect_size:** β = −1.28 (transfer effect); Cohen's d = 0.93 (from power analysis based on prior study, ref. 3)
- **learning_from:** Self; direct aversive experience (electric shocks paired with cues)
- **learning_about:** World; cue-outcome threat contingencies (which cue predicts shock)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Competing systems model (Pavlovian + Instrumental RW controllers; 3 params: α, β, ω)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Competing systems model", "family": "Rescorla-Wagner (dual-controller)", "n_params": 3, "metric": "AIC/wAIC"} - {"name": "One system 1 (same α)", "family": "Q-learning (single controller)", "n_params": 2, "metric": "AIC/wAIC"} - {"name": "One system 2 (different α)", "family": "Q-learning (single controller)", "n_params": 3, "metric": "AIC/wAIC"}
- **model_mb_mf:** MF
- **model_params:** - α (learning rate, shared between Pavlovian and Instrumental controllers): M = 0.46 (SD = 0.35) - β (inverse temperature / softmax temperature, 0 < β ≤ 1): M = 0.28 (SD = 0.35) - ω [S] (Pavlovian weight, relative influence of Pavlovian controller on choice, 0 ≤ ω ≤ 1): M = 0.49 (not significantly different from 0.5)
- **social_param:** ω (Pavlovian weight) — determines relative influence of Pavlovian vs. instrumental controller on decision making. In Experiment 1 this is not specifically a social parameter but becomes one when Pavlovian learning is acquired socially (Exp. 2).
- **social_param_name:** ω
- **social_param_value:** 0.49
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (summed across participants), wAIC (Akaike weights)
- **how_model_fit:** Individual-level-fit (MLE per subject, BFGS optimization with 10 random starts)
- **data_type_fit_to:** Choice behavior

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 40 (Experiment 1); 69% female across all experiments; mean age = 26.7
- **population_category:** healthy adults
- **population_age_range:** M=26.7
- **ecological_validity:** Lab-based threat conditioning with electric shocks rather than naturalistic threats; abstract colored shapes as CS stimuli rather than ecologically relevant stimuli; well-controlled but limited ecological validity.
- **eligibility_flag:** Learning does not occur in a social context. Experiment 1 is a non-social Pavlovian baseline. Flag: non-social learning condition serving as comparison for social experiments.
- **concerns:** Experiment 1 alone does not involve social learning; it is included as a Pavlovian baseline for the social experiments. The softmax temperature β is constrained to (0,1] which is unusual. Single learning rate shared across Pavlovian and instrumental controllers is a simplifying assumption.
- **limitations_reported:** Although both relationships are meaningful, their robustness, given the large number of predictors, and importance are unknown and requires future investigation"; "characterizing the role of [the amygdala] in the transfer of social learning to decision making is an important goal for future research"; sample sizes based on prior effect sizes that may be inflated.
- **limitations_categorized:** Limited ecological validity; task simplicity; no neural data; simplified model assumptions
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - Experiment 1 eligibility: MEDIUM confidence — Experiment 1 is non-social (Pavlovian conditioning from direct experience), flagged accordingly   - Parameter counts for social advice models (Confirmation bias, IL-D, Outcome bonus): LOW confidence — not explicitly reported, referenced from prior literature   - Prior model α and β mean values for Exp 3: cannot find — not reported separately   - Effect sizes for social advice model comparisons: only wAIC reported, no individual model AIC sums for Exp 3   - Social parameter designation for ω in Exp 1: MEDIUM — ω captures Pavlovian influence but Exp 1 is not social
- **cannot_find:** - Exact n_params for Confirmation bias, IL-D, Outcome bonus models   - Mean fitted α and β for Prior model in Experiment 3   - Individual AIC sums for all models in Experiment 3 (only graphical wAIC shown in Fig 6B)   - Whether Bayesian random effects exceedance probabilities were >0.95 for Exp 2 (stated for Exp 3 in SI but exact values not given for Exp 2)
- **other_notes:** This paper presents a novel extension of Pavlovian-Instrumental Transfer (PIT) to social threat learning. The key finding is a dissociation: observational threat learning operates through a Pavlovian competing systems mechanism (like direct conditioning), while instructed threat learning operates as a prior on instrumental action values. Data publicly available at https://osf.io/xfe72/. Total sample across all experiments including controls: N = 225 (120 main + 25 baseline + 80 control experiments 3B/3C). The paper includes extensive model simulations demonstrating that predictions hold across the parameter space. The competing systems model formula is: P(i) = exp[((1-ω)Q_Instrumental_i + ωV_Pavlovian_i)/β] / Σ exp[((1-ω)Q_Instrumental_j + ωV_Pavlovian_j)/β]. The Prior model formula is: Q_CS+(t=1) = −ρN, Q_CS−(t=1) = ρN, with standard Q-learning update thereafter.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = general
- spec_locus = source+target
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_instructed
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = threat_fear
- tax_rr_topic_threat_fear
- tax_social_nonsocial_comparison
- tax_topic_threat_fear
