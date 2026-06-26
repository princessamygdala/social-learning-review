# Dubey (2023)

- **study_id:** `a3ef0606f3dae7a0f_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Dubey, R. (2023). *The successes and failures of human drives* [Doctoral dissertation, Princeton University].
- **citation_short:** Dubey (2023)
- **doi:** Not available (dissertation)
- **publication_type:** thesis
- **year:** 2023.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** lab with lots of big-picture ideas but without clear vision about how to work towards; mitha Milli, Thanard Kurutach, Aida Nematzadeh, and Brian Christian; school friend, Gaurav, who made me fall; school – it has truly been a blast; ether, this work makes progress; Department of Computer Science; ething I will; University
- **code_url:** https://osf.io/3pnkv

## Computational level
- **study_focus:** Not applicable -- no chapter involves computational modeling of social learning
- **study_focus_short:** Not applicable -- no chapter involves computational modeling of social learning
- **learning_mode_description:** 
- **task_description:** Chapter 2: Participants rate curiosity/confidence for trivia questions and choose which answers to reveal; Chapter 3: Curiosity ratings for scientific topics with usefulness manipulation; Chapter 4: Problem-solving with Aha! moment ratings; Chapter 5: Agent-based RL simulations in gridworlds and multi-armed bandits (no human participants); Chapter 6: Field experiment on water conservation messaging in wealthy households.
- **task_paradigm:** Curiosity / insight task (non-social)
- **players:** Varies by chapter -- all involve single agents (no social interaction partners)
- **n_players:** 
- **partner_type:** unclear
- **stimuli:** Varies: trivia questions (Ch 2-3), compound remote associate problems (Ch 4), simulated gridworld/bandit environments (Ch 5), water use reports with prosocial/financial messaging (Ch 6)
- **method:** online / behavioural
- **method_full:** behavioural / online / agent-based simulation (varies by chapter)
- **main_result:** N/A for review purposes (no social learning findings)
- **effect_size:** 
- **learning_from:** N/A (no social learning)
- **learning_about:** N/A (no social learning)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Chapter 2: Rational analysis model of curiosity (Bayesian expected information gain); Chapter 4: Metacognitive prediction error model; Chapter 5: Q-learning with subjective reward function f = w1*Objective + w2*Expect + w3*Compare
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** N/A for review purposes
- **model_mb_mf:** MF (Chapter 5 Q-learning)
- **model_params:** Chapter 5: w1, w2, w3 (reward function weights), alpha (learning rate), epsilon (exploration), gamma (discount), rho (aspiration level) -- none are social parameters
- **social_param:** None -- no social parameters in any model
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** 
- **how_model_fit:** simulate-and-compare (Chapter 5)
- **data_type_fit_to:** agent simulation performance (Chapter 5); choice behavior (Chapters 2-4)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Ch 2: N=303 (MTurk); Ch 3: Exp1 N=174, Exp2 N=343, Exp3 N=289 (all MTurk); Ch 4: Exp1 N=460, Exp2 N=304, Exp3 N=200 (MTurk); Ch 5: agent simulations only; Ch 6: Exp1 N=10,500 households, Exp2a/2b Facebook ad experiments
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Chapter 5 uses stylized gridworld/bandit simulations with limited generalizability to real-world settings (acknowledged by authors). Chapter 6 uses real-world field experiments with high ecological validity but no computational modeling.
- **eligibility_flag:** Does not meet inclusion criteria. This dissertation contains six studies across six chapters. None of the chapters combine computational modeling with learning in a social context over time: Chapters 2-4 use computational models (rational analysis of curiosity, curiosity intervention, metacognitive prediction errors for Aha! moments) but learning is entirely non-social (individual curiosity-driven information seeking). Chapter 5 uses RL agent simulations to study habituation and aspiration-based comparisons, but the agent operates in a non-social gridworld/bandit environment with no social agents or social context -- the authors explicitly note as a limitation that they "did not consider how aspirations can be influenced by social comparisons" (p. 147). Chapter 6 is a field experiment on prosocial messaging to reduce water consumption among the wealthy, which involves a social manipulation but no computational modeling and no learning over time. **No chapter qualifies individually.**  ---  ## COMPUTATIONAL LEVEL
- **concerns:** No chapter meets all four inclusion criteria (computational modeling + human behavioral data + social context + learning over time). The dissertation is primarily about non-social intrinsic motivation and reward design.
- **limitations_reported:** Chapter 5: "we did not consider how aspirations can be influenced by social comparisons"; "it is not completely clear how much our results will generalize to more real-world situations"; "we assumed that the agent designer directly provided the reward function to the agent"; "we did not investigate in detail the potential interaction of discounting with prior expectations and relative comparisons
- **limitations_categorized:** limited ecological validity; no social comparisons modeled; limited generalizability; simplified agent architecture
- **preregistered:** No
- **wc_rule1:** 
- **wc_rule2:** 
- **wc_rule3:** 
- **wc_rule4:** 
- **wc_rule5:** 
- **wc_rule6:** 
- **wc_rule7:** 
- **wc_rule8:** 
- **wc_rule9:** 
- **wc_rule10:** 
- **wc_score:** 0
- **wc_total:** 0.0

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** All fields marked N/A due to eligibility flag -- the dissertation does not contain a study meeting all inclusion criteria (HIGH confidence in this assessment based on full-text reading of all chapters)
- **cannot_find:** 
- **other_notes:** This is a Princeton CS dissertation (Adviser: Thomas L. Griffiths). Chapter 5 was published as Dubey, R., Griffiths, T. L., & Dayan, P. (2022). The pursuit of happiness: A reinforcement learning perspective on habituation and comparisons. *PLOS Computational Biology*, 18(8), e1010316. Chapter 6 was available as a preprint: Kraft-Todd, G.*, Dubey, R.*, Yoeli, E., Rand, D., & Bhanot, S. (2021). Public good messaging motivates the wealthy to reduce water consumption. *PsyArXiv*. No supplement file was found. The dissertation is relevant to computational psychiatry and RL but does not study social learning. The closest connection to social learning is Chapter 6's use of prosocial framing, but that chapter lacks computational modeling entirely. Chapter 5's aspiration/comparison framework could theoretically be extended to social comparisons, but this was explicitly not done and is noted as a future direction.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = general
- spec_locus = source
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_model_MF
- tax_model_bayesian
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_weight
- tax_param_temperature
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_info_use
- tax_rr_topic_social_info_use
- tax_topic_social_info_use
