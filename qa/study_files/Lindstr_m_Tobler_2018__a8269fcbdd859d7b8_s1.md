# Lindström & Tobler (2018)

- **study_id:** `a8269fcbdd859d7b8_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lindström, B., & Tobler, P. N. (2018). Incidental ostracism emerges from simple learning mechanisms. *Nature Human Behaviour*, *2*(6), 405–414. https://doi.org/10.1038/s41562-018-0355-y
- **citation_short:** Lindström & Tobler (2018)
- **doi:** 10.1038/s41562-018-0355-y
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** Laboratory for Social and Neural Systems Research, Department of Economics, University; Section for Psychology, Department of Clinical Neuroscience, Karolinska Institute,; University of Zurich; University Library
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning; social network learning; incidental ostracism emergence from reinforcement learning in partner-choice dynamics on dynamic social networks.
- **study_focus_short:** Cooperation learning · social network learning
- **learning_mode_description:** - Learning mode: Learning from one's own payoff outcomes in social interactions to select interaction partners, with ostracism emerging as a by-product of partner-choice learning.   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (monetary payoffs from Prisoner's Dilemma or coordination game interactions)   - Learning about:     - Target type (social): other (specific interaction partners in a 6-person group)     - Target content (social): action/policy (which partner to select for future interactions; value of each partner)
- **task_description:** Groups of 6 anonymous participants played an iterated Prisoner's Dilemma (Exps 1, 3, 4) or coordination game (Exp 2) for 35 periods. In each period, each participant chose one partner and an action; they could also be chosen by up to 5 others as a responder, with monetary payoffs determined by the game matrix.
- **task_paradigm:** Prisoner's dilemma
- **players:** Multi-agent (6-person groups), asymmetric roles (initiator/responder per period); dynamic partner selection.
- **n_players:** 
- **partner_type:** human (live)
- **stimuli:** Abstract numbered player identifiers (Player 1–6), binary action choices (A/B), monetary payoff matrix outcomes.
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Objective ostracism was prevalent: Gini coefficient ~0.32 (95% CI [0.29, 0.36]) in Exp 1, significantly different from random partner selection (K-S D = 0.34, p < .0001)   - Path dependence: Early objective ostracism (periods 1–5) strongly predicted late objective ostracism (periods 31–35) controlling for free-riding (β = 1.2, SE = 0.24, t = 5.1, p < .0001; model R² = .29) — Exp 1   - Free-riding did not reliably predict final ostracism when controlling for path dependence (smallest p = .09) — Exp 1   - Exp 2 (coordination game, no free-riding possible): Path dependence replicated (β = 2.82, SE = 0.45, t = 6.63, p < .0001; model R² = .54)   - Model comparison: Emergence (RL) model preferred over instrumental model for 168/186 participants (ΔBIC > 2); exceedance probability = 1.0   - Causal manipulation: Imposing path dependence reduced objective ostracism (Exp 3: β = −6.79, SE = 2.76, p = .015; Exp 4: β = −7.71, SE = 2.82, p = .007) and subjective ostracism (Exp 3: β = −0.66, SE = 0.17, p < .001; Exp 4: β = −0.70, SE = 0.17, p < .0001)
- **effect_size:** - Exp 1 path dependence: β = 1.2 (standardized), R² = .29 - Exp 2 path dependence: β = 2.82 (standardized), R² = .54 - Exp 3 ostracism reduction: β = −6.79 - Exp 4 ostracism reduction: β = −7.71 - Subjective ostracism reduction Exp 3: β = −0.66; Exp 4: β = −0.70 - Model comparison: exceedance probability = 1.0 for emergence model
- **learning_from:** Self; own payoff outcomes from social interactions (monetary rewards from PD/coordination game). Source: self.
- **learning_about:** Other (specific partners); expected value of interacting with each partner, driving partner selection. Target: other.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Rescorla-Wagner RL agent-based model (3 params: α [learning rate], β [softmax inverse temperature], ω [initiator vs. responder weighting])
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Emergence model (RL)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC/AIC"},   {"name": "Instrumental model", "family": "Probabilistic grim/heuristic strategy", "n_params": 3, "metric": "BIC/AIC"} ]
- **model_mb_mf:** MF
- **model_params:** - α: learning rate (updates expected value of partner based on prediction error) — mean fitted value not reported in main text (see Supplementary Table 9 for relationship to ostracism) - β: softmax inverse temperature (controls exploration vs. exploitation in partner choice)  - ω: weighting parameter for initiator vs. responder payoffs [S] (balances how much the agent values outcomes from interactions they initiated vs. responded to)  Note: All three parameters are fitted at the individual level. Exact mean fitted values are referenced in supplementary materials (Supplementary Table 9) which are not accessible in this text. The model uses standard Rescorla-Wagner update rule: V(partner) ← V(partner) + α × (outcome − V(partner)), with softmax action selection over partners.
- **social_param:** ω — weighting of initiator vs. responder payoff outcomes [S]; this parameter captures how much the agent weights outcomes from self-initiated interactions vs. interactions initiated by others (a social structural parameter governing the social learning dynamics).
- **social_param_name:** ω
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (also AIC, with identical results); exceedance probability from random-effects Bayesian model selection.
- **how_model_fit:** individual-level-fit (models fitted to individual-level trial-by-trial choice data); then simulate-and-compare for generative validation.
- **data_type_fit_to:** choice behavior (partner selection choices, trial-by-trial)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 456 total (259 female, mean age ~24); Exp 1: n = 186; Exp 2: n = 90; Exp 3: n = 90; Exp 4: n = 90. Exp 1 had two payoff conditions (cumulative n = 78, randomized n = 108) crossed with visibility condition (visible n = 96, not visible n = 90).
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Stylized laboratory economic games with monetary payoffs and anonymous players; limited ecological validity as no real social cues (appearance, prior knowledge) were available. Authors acknowledge this: "our experimental model, which was stylized and based on economic games with monetary payoffs, does not directly speak to forms of instrumental ostracism targeted at individuals who are not free-riders in a standard sense." However, the real-world social network analysis provides some ecological grounding.
- **eligibility_flag:** 
- **concerns:** - Model details (exact formulas, parameter recovery, model recovery) are relegated to Supplementary Methods, which are not accessible in this text file. The main text references "Supplementary Methods for details" repeatedly. - Mean fitted parameter values are not reported in the main text (referenced in Supplementary Table 9). - The instrumental model is a heuristic/strategy model rather than a true competing computational model of learning, making the model comparison somewhat asymmetric. - Data stated as "available from the corresponding author" rather than in a public repository.
- **limitations_reported:** Our experimental model, which was stylized and based on economic games with monetary payoffs, does not directly speak to forms of instrumental ostracism targeted at individuals who are not free-riders in a standard sense"; "evaluating the emergence models in other experimental situations, involving non-monetary payoffs, represents an important future direction"; "Other forms of punitive ostracism, such as the silent treatment between spouses, fall outside our emergence account"; "as our experiments were based on dyadic interactions, where the participants had no knowledge about the payoffs of group members they did not interact with, our findings do not speak to the role of welfare or group-level payoff concerns"; "it is likely that additional factors contribute to ostracism in real-world social situations (e.g., prior information about other individuals, physical appearance)
- **limitations_categorized:** Limited ecological validity; task simplicity; limited generalizability (monetary payoffs only); limited to dyadic interactions; no group-level information; stylized experimental paradigm
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Partial
- **wc_rule10:** Partial
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM — exact formulas and mean fitted values are in Supplementary Methods/Tables, not accessible in this text file - social_param (ω): MEDIUM — described conceptually in main text but formula details in supplement - wc_guidelines rules 5 & 6: MEDIUM — may be in supplement but cannot verify - effect_size: HIGH — all reported directly in text - learning_mode: HIGH — clearly described
- **cannot_find:** - Exact mathematical formula for the emergence model (referenced as "see Supplementary Methods for details") - Mean fitted parameter values for α, β, ω (referenced as Supplementary Table 9) - Parameter recovery analysis (may be in supplement) - Model recovery analysis (may be in supplement) - Initial values / priors for model fitting
- **other_notes:** - Supplement not accessible (no _Supplements.txt file found). Supplementary Methods contain the full model specification, fitting procedures, parameter analyses, and additional experimental details. This is flagged for re-extraction if supplement becomes available. - The paper uses agent-based modeling (ABM) where each agent runs an RL algorithm — this is a multi-agent simulation approach rather than a standard single-subject model fitting paradigm. The model is fitted to individual participants' partner-choice data from Exp 1, then simulated as an ABM to test generative performance. - The paper also analyzes 4 pre-existing real-world longitudinal social network datasets for ecological validation of path dependence predictions.
- **re_extract_flag:** true (Supplementary Methods not accessible; model formulas, parameter values, and potentially parameter/model recovery analyses are only in the supplement)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_domain_D_group_structure_identity
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_social_weight
- tax_param_temperature
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = cooperation
- tax_rr_secondary_topic = social_network_structure
- tax_rr_topic_cooperation
- tax_rr_topic_social_network_structure
- tax_topic_cooperation
- tax_topic_social_network_structure
