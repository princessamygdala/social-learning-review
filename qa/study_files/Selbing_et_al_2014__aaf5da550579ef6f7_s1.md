# Selbing et al. (2014)

- **study_id:** `aaf5da550579ef6f7_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Selbing, I., Lindström, B., & Olsson, A. (2014). Demonstrator skill modulates observational aversive learning. *Cognition*, *133*, 128–139. https://doi.org/10.1016/j.cognition.2014.06.010
- **citation_short:** Selbing et al. (2014)
- **doi:** 10.1016/j.cognition.2014.06.010
- **publication_type:** peer-reviewed journal---
- **year:** 2014.0
- **field_of_study:** Psychology
- **affiliations_raw:** lable to the demonstrator and consequences of the the demonstrator’s overall performances is given; Institute,DivisionofPsychology,Nobelsväg9,17165Solna,Sweden; ethenumberofelectricshocksthroughindividuallearning; ethaninformationgainedthroughindividualexpe-; Institute,Retziusväg8,17165Solna,Sweden; lable theories on social learning; mitationovertimeforthe; lableonline11July2014; emails: bjorn.lindstrom@ki.se, andreas.olsson@ki.se, ida.selbing@ki.se
- **code_url:** 

## Computational level
- **study_focus:** Observational avoidance learning -- how demonstrator skill modulates observational learning from choices vs. consequences in an aversive domain
- **study_focus_short:** Observational avoidance learning -- how demonstrator skill modulates
- **learning_mode_description:** - Learning mode: Learning to avoid aversive outcomes (shocks) by observing a demonstrator's choices and their consequences, modulated by demonstrator skill   - Learning from:     - Source type (social): other (demonstrator)     - Source content (social): action/policy (demonstrator's choices) and outcome (consequences of demonstrator's choices -- shock/no shock)   - Learning about:     - Target type (non-social): world (stimulus-outcome contingencies)     - Target content (non-social): outcome (which choice minimizes shock probability)
- **task_description:** Participants performed a probabilistic two-choice task where they learned to minimize electric shocks by selecting the less-punished stimulus from pairs of abstract fractals. In addition to individual learning, participants observed a demonstrator (skilled or unskilled) performing the same task under three conditions: no observation, choice observation only, or choice-and-consequence observation.
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant), single demonstrator target (sex-matched confederate presented as another participant). Two between-subjects groups: SD group (skilled demonstrator, n=20) and UD group (unskilled demonstrator, n=20).
- **n_players:** network (5+)
- **partner_type:** confederate
- **stimuli:** Abstract fractals (180x180 px), electric shocks (100ms DC-pulse, primary reinforcer), shock/no-shock symbols, participant and confederate photos
- **method:** behavioural
- **method_full:** Behavioural
- **main_result:** - Main effect of Observational Learning Condition on performance (χ²(2) = 21.03, p < .001)- Group x Observational Learning Condition interaction (χ²(2) = 8.00, p = .02) -- SD group performed better than UD group during Choice Observation (β = 0.50, SE = 0.24, z = 2.11)- Group x Observational Learning Condition x Block interaction on performance (χ²(2) = 7.51, p = .02) -- SD group increased performance over blocks during Choice Observation (β = 0.67, SE = 0.13, z = 5.06)- Main effect of Group on Imitation (χ²(1) = 101.69, p < .001; β = 1.24, SE = 0.12, z = 10.08)- Group x Observational Learning Condition x Block interaction on imitation (χ²(1) = 4.39, p = .04) -- SD group increased imitation over blocks during Choice Observation (β = 0.57, SE = 0.14, z = 3.94)- CHCO.S winning model predicted ~68% of choices (69% SD, 67% UD)- Between-group difference in fitted imitation rate (t(27.34) = 2.24, p = .03) -- SD group higher- Block x Group interaction for imitation rate parameter (F(1) = 15.14, p < .001) -- imitation rate increased from first to last block for SD group (paired t(19) = 3.81, p < .01, mean increase = 0.20)---  ### ALGORITHMIC LEVEL
- **effect_size:** Effect sizes reported as regression coefficients (β, SE, z) from logistic mixed models and t-tests; no standardized effect sizes (Cohen's d, η²) reported  ### CANNOT FIND - Individual fitted parameter descriptives (means/SDs) for all parameters of CHCO.S model beyond the imitation rate - Standardized effect sizes (Cohen's d, r², η²)  ### OTHER NOTES - The demonstrator for the SD group was controlled by an RL algorithm (α = 0.3, β = 0.4, consequence values set to +10/-10), not a real person. The UD group demonstrator made random choices. Participants were told they were observing another participant (confederate). - This paper is purely behavioral -- the authors explicitly suggest future fMRI work combining RL modeling with neuroimaging to investigate neural correlates. - The supplement contains two additional exploratory models (CHCO.S.imitation and CHCO.S.tracking) testing possible mechanisms of skill modulation; neither improved fit over CHCO.S.
- **learning_from:** Other (demonstrator); demonstrator's choices and consequences (shock/no-shock outcomes)
- **learning_about:** World; stimulus-outcome contingencies (which choice minimizes shock probability)
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** CHCO.S -- Q-learning with separated observational learning: uses observation of consequences only during Choice-Consequence Observation and imitation only during Choice Observation. 4 free params: α_individual, β, α_imitation, α_obs.conseq.
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** | Model | Family | n_params | Metric | |---|---|---|---| | Individual | Q-learning | 2 (α_individual, β) | AIC weights | | CH | Q-learning + choice observation | 3 (α_individual, β, α_imitation) | AIC weights | | CO | Q-learning + consequence observation | 3 (α_individual, β, α_obs.conseq.) | AIC weights | | CHCO.H | Q-learning + hybrid observation | 4 (α_individual, β, α_imitation, α_obs.conseq.) | AIC weights | | CHCO.S | Q-learning + separated observation | 4 (α_individual, β, α_imitation, α_obs.conseq.) | AIC weights | | CHCO.t(choice) | CHCO.S + temporally changing imitation | 5 (α_individual, β, α_obs.conseq., α_imitation(F), α_imitation(L)) | AIC weights | | CHCO.t(cons.) | CHCO.S + temporally changing obs.conseq. | 5 (α_individual, β, α_imitation, α_obs.conseq.(F), α_obs.conseq.(L)) | AIC weights | | CHCO.S.imitation (supplement) | CHCO.S + learned imitation value | 5+ | AIC weights | | CHCO.S.tracking (supplement) | CHCO.S + skill tracking | 5+ | AIC weights |
- **model_mb_mf:** MF
- **model_params:** Mean fitted values for α_individual, β, α_obs.conseq. not reported
- **social_param:** α_imitation [S] -- rate at which participant imitates demonstrator's choices; α_obs.conseq. [S] -- rate at which participant updates action values from observing demonstrator's consequences
- **social_param_name:** α_imitation [S]
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC weights (wAIC) -- calculated per participant, compared via mean, SD, mean rank order, and number of wins across participants
- **how_model_fit:** Individual-level fit; parameters fitted per participant over all trials by minimizing negative log-likelihood using MLE (mle2 function in R, BFGS optimization, 40 random starts per participant)
- **data_type_fit_to:** Choice behavior (binary optimal/suboptimal choices)---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A -- no neuroimaging
- **key_regions:** N/A -- no neuroimaging
- **coordinates_peak:** N/A -- no neuroimaging
- **analysis_type:** N/A---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 40 (after excluding 2 for below-chance performance from initial 42); SD group n = 20 (13 women, mean age = 23.85, SD = 5.76), UD group n = 20 (9 women, mean age = 25.00, SD = 5.37)
- **population_category:** healthy adults
- **population_age_range:** M=23.85
- **ecological_validity:** Limited -- lab-based task with abstract fractals and electric shocks; confederate presented as co-participant but no real social interaction; demonstrator skill inferred rather than explicitly communicated, which adds some ecological validity. Social context is minimal (observation only, no interaction).
- **eligibility_flag:** 
- **concerns:** - Mean fitted parameter values for the winning model (CHCO.S) are not reported for all parameters (only the imitation rate difference between groups is tested). Individual α, β, and α_obs.conseq. group-level descriptives are not provided. - No parameter recovery or model recovery analyses. - No posterior predictive checks beyond overall choice prediction accuracy (68%). - The "demonstrator" is actually a computer algorithm (for SD group) or random generator (for UD group), not a real person -- participants were deceived into thinking they were observing another participant. - Relatively small sample (n = 20 per group).
- **limitations_reported:** Authors note: inability to determine the mechanism by which demonstrator skill modulates observational learning (learning the value of imitation vs. skill tracking -- neither supplementary model improved fit); cannot conclude from definition of imitation used whether increased imitation reflects copying of demonstrator choices or convergence of two agents learning the same task; suggest fMRI would be needed to investigate neural mechanisms; note that some UD group participants continued to imitate random behavior even after several blocks, warranting further investigation.
- **limitations_categorized:** Mechanistic ambiguity; task simplicity; limited ecological validity; sample size; no neuroimaging; limited model discriminability
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 5.5
- **wc_total:** 5.5

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
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = partly
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- tax_domain_B_inference_modelling_others
- tax_domain_F_affective_moral
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = imitation_emulation
- tax_rr_secondary_topic = threat_fear
- tax_rr_topic_imitation_emulation
- tax_rr_topic_threat_fear
- tax_topic_imitation_emulation
- tax_topic_threat_fear
