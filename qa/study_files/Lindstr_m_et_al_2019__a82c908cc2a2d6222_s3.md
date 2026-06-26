# Lindström et al. (2019)

- **study_id:** `a82c908cc2a2d6222_s3`
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
- **study_focus:** Instructed threat learning transfer to decision making
- **study_focus_short:** Instructed threat learning transfer to decision making
- **learning_mode_description:** - Learning mode: Learning from verbal instruction about which cue is associated with threat (shock), and how this instructed knowledge transfers to one's own instrumental decision making.   - Learning from:     - Source type (social): other (experimenter providing verbal instruction)     - Source content (social): state (communicated threat contingency — verbal information about cue-shock association)   - Learning about:     - Target type (non-social): world (cue-outcome threat contingency)     - Target content (non-social): stimulus (CS+/CS- threat value for self)
- **task_description:** Participants were verbally instructed that one cue (CS+) would be paired with shocks and another (CS-) would not, with instructions repeated before each trial. They never saw the actual CS cues during conditioning (only control stimuli). They then made 70 binary choices between these cues with probabilistic shock punishment; contingencies reversed after 35 trials.
- **task_paradigm:** Fear conditioning (social)
- **players:** Single agent (participant), single social source (experimenter providing instructions). Half assigned to No Change group, half to Change group.
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Colored geometric shapes (yellow and blue), verbal/text instructions about threat contingencies, control stimuli (red and green triangles during conditioning), electric shocks during decision phase
- **method:** behavioural
- **method_full:** Behavioural (choice behavior)
- **main_result:** - Main Results:   - Transfer of instructed threat learning to decision making (β = −1.56, SE = 0.32, z = −4.85, 95% CI [−2.19, −0.93])   - Reversal of transfer (Group × Reversal: χ²(1) = 19.6, p < 0.0001)   - Magnitude comparable to Experiment 2 (Group × Reversal × Experiment: χ²(1) = 0.22, p = 0.64)   - Winning model: Prior model (instruction as prior on instrumental Q-values), wAIC = ~1.0   - This is distinct from the Competing systems model that won for observational learning   - Replicated in Experiment 3B (Prior model best: wAIC(Prior) = 1)   - Experiment 3C (instruction + shocks combined) also showed transfer (β = −0.88, SE = 0.38, z = −2.31) and reversal (χ²(1) = 8.1, p = 0.004), with Prior model winning (wAIC ~ 1)   - ρ parameter (prior strength) significantly lower in Exp 3B (M = 0.33) than Exp 3 (M = 0.75), t(63.17) = −3.0
- **effect_size:** β = −1.56 (transfer); ρ M = 0.75 (prior strength, Exp 3); ρ M = 0.33 (prior strength, Exp 3B)
- **learning_from:** Other (experimenter); verbal instruction about threat contingencies
- **learning_about:** World; cue-outcome threat contingencies for self  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Prior model (instruction sets initial Q-values; Q_CS+(t=1) = −ρN, Q_CS−(t=1) = ρN; 3 params: α, β, ρ)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Competing systems model", "family": "Rescorla-Wagner (dual-controller)", "n_params": 3, "metric": "AIC/wAIC"} - {"name": "Prior model", "family": "Q-learning with instruction prior", "n_params": 3, "metric": "AIC/wAIC"} - {"name": "Confirmation bias", "family": "RL with biased updating", "n_params": "not specified", "metric": "wAIC"} - {"name": "IL-D (Instructed learning D)", "family": "RL with instructed bonus", "n_params": "not specified", "metric": "wAIC"} - {"name": "Outcome bonus", "family": "RL with outcome bonus", "n_params": "not specified", "metric": "wAIC"}
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): fitted individually (mean not reported separately for Prior model in Exp 3) - β (softmax temperature): fitted individually - ρ [S] (prior strength — how strongly instruction determines initial Q-values, 0 ≤ ρ ≤ 1): M = 0.75 (Exp 3); M = 0.33 (Exp 3B)
- **social_param:** ρ (prior strength) [S] — determines how strongly verbal threat instruction sets the initial instrumental action values at the outset of decision making. Higher ρ means stronger influence of social instruction on subsequent choices.
- **social_param_name:** ρ
- **social_param_value:** 0.75
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC/wAIC; additionally Bayesian random effects model comparison (exceedance probability) using both AIC and BIC
- **how_model_fit:** Individual-level-fit (MLE per subject)
- **data_type_fit_to:** Choice behavior

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 40 (Experiment 3); mean age = 25. Control experiments: Exp 3B N = 40 (18 women, mean age = 26); Exp 3C N = 40 (25 women, mean age = 24.9); Exp 4 (baseline) N = 25 (18 women, mean age = 27).
- **population_category:** healthy adults
- **population_age_range:** M=25.
- **ecological_validity:** Verbal instruction from experimenter is relatively naturalistic for instructed learning. However, abstract cue stimuli and lab setting limit generalizability. The design where participants never see CS cues during conditioning is unusual and may limit comparability with real-world instructed learning.
- **eligibility_flag:** 
- **concerns:** Instruction from an experimenter is a minimal social manipulation. Participants never saw CS cues during the conditioning block in Experiment 3 (to avoid extinction), which is an unusual design choice that may affect generalizability. Parameter counts and formulas for some alternative models (Confirmation bias, IL-D, Outcome bonus) are not fully specified in the paper — they are referenced from prior literature. Mean fitted parameter values for the Prior model in Exp 3 are not fully reported (only ρ is reported).
- **limitations_reported:** Evaluating such predictions is an important goal for future research" (re: whether Pavlovian counterconditioning vs. divergent instrumental experience differentially overcome observational vs. instructed bias); "characterizing the role of [the amygdala] in the transfer of social learning to decision making is an important goal for future research"; "it is likely that different patterns of connectivity in overlapping neural networks, or multivariate response patterns, underpin the difference between observational and instructed threat learning
- **limitations_categorized:** Limited ecological validity; no neural data; task simplicity; incomplete parameter reporting; limited generalizability
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
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_F_affective_moral
- tax_mod_instructed
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = threat_fear
- tax_rr_topic_threat_fear
- tax_topic_threat_fear
