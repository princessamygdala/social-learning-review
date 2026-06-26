# Hackel & Zaki (2018)

- **study_id:** `a95f701fd9e24ed4f_s2`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hackel, L. M., & Zaki, J. (2018). Propagation of economic inequality through reciprocity and reputation. *Psychological Science, 29*(4), 604–613. https://doi.org/10.1177/0956797617741720
- **citation_short:** Hackel & Zaki (2018)
- **doi:** 10.1177/0956797617741720
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Psychology
- **affiliations_raw:** Department of Psychology, Stanford University,; Department of Psychology, Stanford University; laboratory, which can indicate; ether to; emails: lhackel@stanford.edu
- **code_url:** 

## Computational level
- **study_focus:** Reputation learning; how reinforcement learning about givers' generosity and reward value shapes reputation ratings and investment decisions in a social marketplace.
- **study_focus_short:** Reputation learning
- **learning_mode_description:** - Learning mode: Learning from monetary outcomes shared by givers about givers' trustworthiness/reputation to guide reputation ratings and third-party investment.   - Learning from:     - Source type (social): other (givers)     - Source content (non-social): outcome (points shared = reward value) and (social): action/policy (proportion shared = generosity)   - Learning about:     - Target type (social): other (givers)     - Target content (social): state (mental state; traits — trustworthiness/reputation)
- **task_description:** Participants ("recipients") learned about givers through repeated partner choices (identical to Study 1), then rated each giver on a 1–5 star scale for a trust game to be played by a third wave of participants ("investors"), who chose one giver to invest with based on these ratings.
- **task_paradigm:** Dictator game
- **players:** Multi-agent (3 waves: givers, recipients, investors); recipients rate 4 givers (2 higher-wealth, 2 lower-wealth); investors choose 1 giver
- **n_players:** 
- **partner_type:** human (live)
- **stimuli:** Face avatars, binary monetary feedback, 1-to-5 star reputation ratings
- **method:** online / behavioural
- **method_full:** Behavioural (online, MTurk)
- **main_result:** - Main Results:   - Effect of giver wealth on star ratings (b = 0.35, SE = 0.06, t(82.75) = 6.39, p < .001, 95% CI [0.24, 0.47])   - Effect of giver generosity on star ratings (b = 1.11, SE = 0.05, t(235) = 22.42, p < .001, 95% CI [1.01, 1.21])   - Total variance explained: R²_m = .59, R²_c = .69   - Difference of generosity vs. wealth coefficients (difference = 0.75, SE = 0.08, chi-sq(1) = 95.10, p < .001)   - Investors chose highest-rated giver 93% of the time   - Investments in higher-wealth givers: 755 cents vs. lower-wealth: 379 cents (chi-sq(1, N=82) = 9.56, p = .002)   - Correlation between w and preferential reputation for higher-wealth givers: r(83) = −.41, p < .001, 95% CI [−0.57, −0.22]
- **effect_size:** - Main Results:   - Effect of giver wealth on star ratings (b = 0.35, SE = 0.06, t(82.75) = 6.39, p < .001, 95% CI [0.24, 0.47])   - Effect of giver generosity on star ratings (b = 1.11, SE = 0.05, t(235) = 22.42, p < .001, 95% CI [1.01, 1.21])   - Total variance explained: R²_m = .59, R²_c = .69   - Difference of generosity vs. wealth coefficients (difference = 0.75, SE = 0.08, chi-sq(1) = 95.10, p < .001)   - Investors chose highest-rated giver 93% of the time   - Investments in higher-wealth givers: 755 cents vs. lower-wealth: 379 cents (chi-sq(1, N=82) = 9.56, p = .002)   - Correlation between w and preferential reputation for higher-wealth givers: r(83) = −.41, p < .001, 95% CI [−0.57, −0.22]
- **learning_from:** Other (givers); monetary reward outcomes and generosity proportion
- **learning_about:** Other (givers); trustworthiness/reputation  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Same model as Study 1. Reward-Generosity RL model (α, w, β). Study 2 fitted params: α mean = 0.38, median = 0.28; w mean = 0.41, median = 0.37; β mean = 0.34, median = 0.14.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Reward-Generosity RL model", "family": "Rescorla-Wagner", "n_params": 3, "metric": "MAP estimation"}]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): Study 2 mean = 0.38, median = 0.28 - w (weighting parameter) [S]: Study 2 mean = 0.41, median = 0.37 - β (exploration/inverse temperature): Study 2 mean = 0.34, median = 0.14
- **social_param:** w (weighting parameter) — same as Study 1
- **social_param_name:** w
- **social_param_value:** 0.41
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A — only one model tested
- **how_model_fit:** Individual-level fit (MAP estimation, same priors as Study 1)
- **data_type_fit_to:** Choice behavior (learning phase partner selection choices)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** Study 2: Wave 1 (givers) N = 101 (45F, 56M; ages 19–70, M = 34.92); Wave 2 (recipients) N = 85 after exclusions (46F, 54M; ages 18–65, M = 34.22; 15 excluded); Wave 3 (investors) N = 82 (40F, 41M, 1 undisclosed; ages 20–66, M = 34.21)
- **population_category:** healthy adults
- **population_age_range:** 19–70
- **ecological_validity:** Same as Study 1, but extends to a 3-wave social marketplace design with reputation transmission, which adds ecological relevance. The "Yelp-style" rating system and trust game investment have real-world analogues. However, still limited by artificial lab context and MTurk sample.
- **eligibility_flag:** 
- **concerns:** Same as Study 1. Additionally, the 3-wave design means investor behavior is contingent on a single recipient's ratings, which may not generalize to aggregated reputation systems. The minimum 2-cent investment requirement may constrain natural behavior.
- **limitations_reported:** Same paper-level limitations as Study 1.
- **limitations_categorized:** Limited ecological validity; task simplicity; no model comparison; limited generalizability; no neuroimaging; no parameter recovery
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 4.5
- **wc_total:** 4.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** yes
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `all_models_tested`: LOW confidence — only one model described; paper states it was "validated in previous work" but no alternative models compared in this paper   - `model_comparison_metric`: N/A — no model comparison performed (only 1 model)   - `preregistered`: MEDIUM — not mentioned in paper; marked "Not reported"   - `limitations_reported`: MEDIUM — authors discuss limitations in Discussion but do not have a formal limitations section
- **cannot_find:** - No formal model comparison (only 1 model tested)   - No parameter recovery or model recovery   - No simulation studies   - No neuroimaging data   - No explicit preregistration statement
- **other_notes:** The paper also reports 2 pilot studies (N = 46, N = 141) and a replication of Study 1 (N = 95) in the supplement, all showing consistent effects. The computational model is identical across all studies, with only minor adaptations for continuous vs. binary giver allocations in pilot studies. Supplement Table S9 provides fitted parameter values for all studies. Open data and materials available at https://osf.io/aj98f/. The model was originally developed and validated in Hackel, Doll, & Amodio (2015, Nature Neuroscience).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_social_weight
- tax_rr_primary_topic = reputation_learning
- tax_rr_secondary_topic = reciprocity
- tax_rr_topic_reciprocity
- tax_rr_topic_reputation_learning
- tax_topic_reciprocity
- tax_topic_reputation_learning
