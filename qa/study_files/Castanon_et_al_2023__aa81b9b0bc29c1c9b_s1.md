# Castanon et al. (2023)

- **study_id:** `aa81b9b0bc29c1c9b_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Castanon, R., Campos, F. A., Villar, J., & Sanchez, A. (2023). A reinforcement learning approach to explore the role of social expectations in altruistic behavior. *Scientific Reports, 13*, 1717. https://doi.org/10.1038/s41598-023-28659-0
- **citation_short:** Castanon et al. (2023)
- **doi:** 10.1038/s41598-023-28659-0
- **publication_type:** peer-reviewed journal---
- **year:** 2023.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** laborative behavioral traits, thus equipping them to develop more comprehensive,; Institute for Systems and Computer Engineering, Technology and Science, Porto,; laborative initiatives are only established with the intention of reciprocity; mitations in their explanation of altruism, essentially due to a tendency; eth century, theories based on an intrinsically selfish or; eth century, reciprocal altruism was; mpirical and normative expectations,; mitations with regards to its; emails: rosendocastanon@idestadvisory.com
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning / cooperation learning -- how social expectations (empirical and normative) shape altruistic donation behavior through reinforcement learning in a Dictator Game
- **study_focus_short:** Prosocial learning / cooperation learning -- how social expectations (empirical
- **learning_mode_description:** - Learning mode: Learning from empirical and normative social expectations about how much to donate (aspiration updating) in a Dictator Game   - Learning from:     - Source type (social): other (peers -- other dictators for normative; assigned recipient for empirical)     - Source content (social): outcomes (donation amounts received) and actions/policy (shared aspiration levels of peer dictators)   - Learning about:     - Target type (non-social): self (own aspiration level / donation strategy)     - Target content (non-social): action/policy (own future cooperative behavior / aspiration)
- **task_description:** In an agent-based simulation of a repeated Dictator Game, 1000 agents are randomly assigned as dictators or recipients each round. Dictators first engage in normative interactions (sharing aspiration levels with Q=2 peers), update their aspirations via Bush-Mosteller reinforcement learning, then donate to recipients who in turn update their own aspirations based on the mismatch between received and expected amounts.
- **task_paradigm:** Dictator game
- **players:** Multi-agent (1000 simulated agents), symmetric role assignment (random dictator/recipient each round)
- **n_players:** 
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract monetary endowments in a Dictator Game; normative stimuli from peer dictators' communicated aspirations; empirical stimuli from received donations
- **method:** other
- **method_full:** Computational simulation / agent-based modeling
- **main_result:** - The model with "socially consistent" agents (single susceptibility parameter for both normative and empirical interactions) best reproduces experimental DG donation distributions - Negative interactions dominate over positive interactions in shaping donation profiles, consistent with prospect theory (negative impact ~3x positive impact yields best match to experimental data) - Empirical expectations dominate normative expectations in determining final donation profiles - Best-fitting parameter combination (W_emp,neg = W_nor,neg = 1; W_emp,pos = W_nor,pos = 1/3) yields mean donation of 31.6% vs. 30% in Engel's meta-analysis - Susceptibility to social stimuli decays exponentially to zero in the stationary regime, consistent with findings from Westhoff et al. (2020) - No formal effect sizes reported (simulation study comparing distributional properties to meta-analytic benchmarks)
- **effect_size:** No formal effect sizes reported; simulation study with qualitative distributional comparisons only
- **learning_from:** Other (peers' aspiration levels via normative interactions; donations via empirical interactions)
- **learning_about:** Self (own aspiration level and future donation strategy)---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Bush-Mosteller RL with dual susceptibility updating (empirical + normative stimuli; single susceptibility parameter l_i,t; asymmetric impact weights W_pos, W_neg)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Only two variants compared informally; n_params approximate since grid-searched rather than fitted
- **model_mb_mf:** MF (model-free reinforcement learning -- aspiration updated based on stimulus without a model of the environment)
- **model_params:** - W^{nor,pos}: impact of positive normative stimuli on susceptibility [0,1] -- best fit = 1/3 - W^{nor,neg}: impact of negative normative stimuli on susceptibility [0,1] -- best fit = 1 - W^{emp,pos}: impact of positive empirical stimuli on susceptibility [0,1] -- best fit = 1/3 - W^{emp,neg}: impact of negative empirical stimuli on susceptibility [0,1] -- best fit = 1 - l_{i,t} [S]: susceptibility to social stimuli (single parameter for both empirical and normative), initialized from U(0, 0.5), evolves over time - a_{i,t}: aspiration level, initialized from U(0.5*Phi, Phi) - Q: number of normative interactions per round (fixed at 2) - delta^{nor}, delta^{emp}: noise parameters (trembling hand), drawn from N(0,0.05) and N(0,0.1) respectively
- **social_param:** l_{i,t} [S] -- susceptibility to social stimuli, governs how strongly agents update aspirations in response to both empirical expectations (what others do) and normative expectations (what others say one should do). Decays exponentially over rounds.
- **social_param_name:** l_{i,t}
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** No formal statistical comparison metric; qualitative match to experimental benchmarks
- **how_model_fit:** Simulate-and-compare (agent-based simulation outputs compared to experimental distributional benchmarks)
- **data_type_fit_to:** Simulated choice behavior (donation distributions) compared to experimental behavioral data from literature (not fitted to individual-level data)---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=1000 simulated agents; 10 replications per parameter combination; no human participants
- **population_category:** non-human
- **population_age_range:** 
- **ecological_validity:** Low -- purely computational/agent-based simulation with no real human participants. Dictator Game is a standard but simplified experimental paradigm. Fully connected network topology does not reflect real social structures. Authors acknowledge this and suggest future work with complex networks.
- **eligibility_flag:** No human behavioral data -- simulation study only  ### CANNOT FIND - Formal effect sizes (not applicable to simulation study) - Formal model comparison statistics (BIC, AIC, etc.) - Parameter recovery / model recovery results - Preregistration status  ### OTHER NOTES - This is a computational/theoretical paper that proposes an agent-based model using Bush-Mosteller RL to explain altruistic behavior in the Dictator Game through social expectations (empirical + normative). It validates by comparing simulation outputs to published meta-analytic experimental benchmarks rather than collecting new human data. - The key theoretical contribution is that coupling empirical and normative susceptibility into a single parameter ("socially consistent" agents) and weighting negative interactions ~3x more than positive interactions best reproduces experimental DG donation profiles. - The supplement (Annex) presents results for the more general case where empirical and normative susceptibilities can differ, showing this leads to loss of heterogeneity in donation profiles inconsistent with experimental evidence. - DOI: 10.1038/s41598-023-28659-0 - Published in Scientific Reports (2023)  ### RE-EXTRACT FLAG: false
- **concerns:** - No human participants -- entirely simulation-based - No formal model comparison metric (qualitative comparison to experimental benchmarks only) - No parameter recovery or model recovery analyses - Fully connected network is unrealistic for social interactions - Parameters explored on a coarse grid (1/3 intervals) rather than continuous optimization - No formal statistical tests comparing model outputs to experimental data (MEDIUM)
- **limitations_reported:** Fully connected network does not capture real social structures; future work should consider complex networks and homophily; personal normative beliefs not modeled; role of "reference network" in normative interactions not explored; endowment effects under risk not addressed; positive and negative interaction impacts could be further personalized across agents
- **limitations_categorized:** Limited ecological validity; task simplicity; no real human data; limited generalizability; network structure oversimplification; no parameter recovery; coarse parameter search
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_cultural_network
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_F_affective_moral
- tax_mod_cultural_network
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_social_weight
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = norm_conformity
- tax_rr_topic_norm_conformity
- tax_rr_topic_prosocial_altruism
- tax_topic_norm_conformity
- tax_topic_prosocial_altruism
