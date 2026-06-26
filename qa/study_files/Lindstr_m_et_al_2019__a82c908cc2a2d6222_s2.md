# Lindström et al. (2019)

- **study_id:** `a82c908cc2a2d6222_s2`
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
- **study_focus:** Observational threat learning transfer to decision making
- **study_focus_short:** Observational threat learning transfer to decision making
- **learning_mode_description:** - Learning mode: Learning from observing another person receiving aversive outcomes (electric shocks) paired with cues, and how these observationally acquired Pavlovian associations transfer to one's own instrumental decision making.   - Learning from:     - Source type (social): other (demonstrator observed via video)     - Source content (social): outcome (observed electric shock to demonstrator)   - Learning about:     - Target type (non-social): world (cue-outcome threat contingency)     - Target content (non-social): stimulus (CS+/CS- threat value for self)
- **task_description:** Participants watched a video of a demonstrator receiving electric shocks paired with one cue (CS+) but not another (CS-). They then made 70 binary choices between these cues, where each choice was probabilistically punished with shocks to themselves; contingencies reversed after 35 trials.
- **task_paradigm:** Fear conditioning (social)
- **players:** Single agent (participant), single social source (video demonstrator). Half assigned to No Change group, half to Change group.
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Colored geometric shapes (yellow and blue), video of demonstrator receiving electric shocks, electric shocks (aversive US to participant during decision phase)
- **method:** behavioural
- **method_full:** Behavioural (skin conductance + choice behavior)
- **main_result:** - Main Results:   - Transfer of observational threat learning to decision making: Change group had markedly impaired decision making relative to No Change group (β = −1.73, SE = 0.32, z = −5.38, 95% CI [−2.36, −1.1])   - Change group received 20.4% more shocks during Transfer phase (Wilcox W = 295.5)   - Reversal of transfer after contingency switch (Group × Reversal: χ²(1) = 18.54, p < 0.0001)   - Simple effects Change > No Change in Reversal phase (β = 1.09, SE = 0.40, z = 2.72, 95% CI [0.31, 1.88])   - No reliable difference in transfer size between Exp 1 and Exp 2 (Group × Experiment: χ²(1) = 1.39, p = 0.24)   - Pavlovian weight ω highly similar to Exp 1 (M = 0.50)   - Empathy with demonstrator and unpleasantness of watching moderated transfer strength (Group × unpleasantness: F(1,29) = 5.19; Group × empathy: F(1,29) = 4.56)   - Successful observational threat learning confirmed by SCR (CS+ > CS−, t(38) = 2.36, 95% CI [0.054, 0.7])
- **effect_size:** β = −1.73 (transfer effect); β = 1.09 (reversal simple effect)
- **learning_from:** Other (demonstrator); observed aversive outcomes (electric shocks to another person)
- **learning_about:** World; cue-outcome threat contingencies for self (which cue predicts shock)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Competing systems model (Pavlovian + Instrumental RW controllers; 3 params: α, β, ω)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Competing systems model", "family": "Rescorla-Wagner (dual-controller)", "n_params": 3, "metric": "AIC/wAIC"} - {"name": "One system 1 (same α)", "family": "Q-learning (single controller)", "n_params": 2, "metric": "AIC/wAIC"} - {"name": "One system 2 (different α)", "family": "Q-learning (single controller)", "n_params": 3, "metric": "AIC/wAIC"} - {"name": "Confirmation bias", "family": "RL with biased updating", "n_params": "not specified", "metric": "wAIC"} - {"name": "IL-D (Instructed learning D)", "family": "RL with instructed bonus", "n_params": "not specified", "metric": "wAIC"} - {"name": "Outcome bonus", "family": "RL with outcome bonus", "n_params": "not specified", "metric": "wAIC"} - {"name": "Prior model", "family": "RL with prior on Q-values", "n_params": "not specified", "metric": "wAIC"}
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): M = 0.50 (SD = 0.34) - β (softmax temperature): M = 0.26 (SD = 0.29) - ω [S] (Pavlovian weight — relative influence of socially acquired Pavlovian values): M = 0.50 (SD = 0.35), not different from 0.5
- **social_param:** ω (Pavlovian weight) [S] — determines the relative influence of observationally acquired Pavlovian threat associations on instrumental decision making. Captures how strongly the socially learned threat values bias choices.
- **social_param_name:** ω
- **social_param_value:** 0.50
- **social_param_sd:** 0.35
- **social_param_range:** 
- **model_comparison_metric:** AIC (summed), wAIC; additionally Bayesian random effects model comparison (exceedance probability) using both AIC and BIC approximations
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
- **sample_size:** N = 40 (Experiment 2); mean age = 25.9
- **population_category:** healthy adults
- **population_age_range:** M=25.9
- **ecological_validity:** Observational learning via pre-recorded video of demonstrator (standardized, not live interaction); abstract cue stimuli; controlled but limited ecological validity compared to real-world vicarious learning through media or social networks.
- **eligibility_flag:** 
- **concerns:** Demonstrator was a pre-recorded video, not a live social interaction. No neural data collected. The social advice models compared against were originally developed for reward/monetary contexts and adapted here for aversive/threat context. Parameter counts for the social advice models are not fully specified in the paper.
- **limitations_reported:** the robustness, given the large number of predictors, and importance are unknown and requires future investigation" (re: empathy moderation); "characterizing the role of [the amygdala] in the transfer of social learning to decision making is an important goal for future research"; "it is likely that different patterns of connectivity in overlapping neural networks, or multivariate response patterns, underpin the difference between observational and instructed threat learning
- **limitations_categorized:** Limited ecological validity; no neural data; task simplicity; limited generalizability (lab stimuli vs. real media); no parameter recovery
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
- **ctx_copresence:** yes
- **ctx_observability:** yes
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
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_F_affective_moral
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
- tax_topic_threat_fear
