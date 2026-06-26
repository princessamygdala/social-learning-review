# Lamba et al. (2020)

- **study_id:** `acb32d7c8936fcfe9_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lamba, A., Frank, M. J., & FeldmanHall, O. (2020). Anxiety impedes adaptive social learning under uncertainty. *Psychological Science*, *31*(5), 592–603. https://doi.org/10.1177/0956797620910993
- **citation_short:** Lamba et al. (2020)
- **doi:** 10.1177/0956797620910993
- **publication_type:** peer-reviewed journal---
- **year:** 2020.0
- **field_of_study:** Psychology
- **affiliations_raw:** Department of Cognitive, Linguistic, and Psychological Sciences, Brown University, and; ether they should continue to be trusted if contexts; Institute for Brain Science, Brown University; ether people can be trusted and, if so,; University, 190 Thayer St; mpirical and com-; emails: oriel.feldmanhall@brown.edu
- **code_url:** https://osf.io/ea67f/

## Computational level
- **study_focus:** Trust learning under uncertainty; how anxiety impairs adaptive social learning, specifically learning to stop investing in exploitative social partners.
- **study_focus_short:** Trust learning under uncertainty
- **learning_mode_description:** - Learning mode: Learning from a social partner's monetary reciprocation about whether the partner is worth trusting (investing in)   - Learning from:     - Source type (social): other (online partner/trustee)     - Source content (non-social): outcome (monetary return on investment)   - Learning about:     - Target type (social): other (online partner/trustee)     - Target content (social): state (trustworthiness / reward probability)  Note: A matched non-social condition (slot-machine game) is also included for comparison. In that condition: - Learning from: Source type (non-social): world (slot machine); Source content (non-social): outcome (monetary return) - Learning about: Target type (non-social): world (slot machine); Target content (non-social): state (reward probability)
- **task_description:** Participants played a repeated trust game with three preprogrammed online "partners" (and a matched slot-machine game), investing $0.10–$1.00 per trial; investments were quadrupled and the partner returned a proportion that drifted over 28 rounds per partner, creating change points between net-gain and net-loss blocks.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (3 preprogrammed partners; within-subject social vs. non-social conditions)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** MTurk usernames (anonymous online partners), slider bar for investment amounts, monetary feedback (proportion of quadrupled investment returned)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Healthy subjects invested more in slot-machine game than trust game (d = 0.13, 95% CI [-0.079, -0.042]) - Asymmetric investment across trust-game player types (F(2,512) = 23.52, d = 0.61) - Greater first-impression bias in social vs. non-social domain (t(256) = 2.74, 95% CI [0.007, 0.043]) - Anxiety x Valence interaction on trust-game investments (F(1,352) = 6.30, generalized eta-squared = .005) - Anxiety x Condition interaction on decay-rate difference (F(1,352) = 4.14, generalized eta-squared = .005) - Anxious subjects showed significantly different decay rate in trust game vs. healthy (t(352) = -2.57, p = .011) but not in slot-machine game (t(352) = -0.045, p = .96) - DBRL best-fitting model for healthy subjects (pxp > .99 for both games); no clear DBRL vs. BRL preference for anxious subjects (TG pxp = .56, SM pxp = .54)
- **effect_size:** - Healthy subjects invested more in slot-machine game than trust game (d = 0.13, 95% CI [-0.079, -0.042]) - Asymmetric investment across trust-game player types (F(2,512) = 23.52, d = 0.61) - Greater first-impression bias in social vs. non-social domain (t(256) = 2.74, 95% CI [0.007, 0.043]) - Anxiety x Valence interaction on trust-game investments (F(1,352) = 6.30, generalized eta-squared = .005) - Anxiety x Condition interaction on decay-rate difference (F(1,352) = 4.14, generalized eta-squared = .005) - Anxious subjects showed significantly different decay rate in trust game vs. healthy (t(352) = -2.57, p = .011) but not in slot-machine game (t(352) = -0.045, p = .96) - DBRL best-fitting model for healthy subjects (pxp > .99 for both games); no clear DBRL vs. BRL preference for anxious subjects (TG pxp = .56, SM pxp = .54)
- **learning_from:** Other (social partner's monetary return / reciprocation); world (slot machine outcome)
- **learning_about:** Other's trustworthiness (probability that investing is worthwhile); slot-machine reward probability---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Dynamic Bayesian RL (DBRL; 6 params: gamma_0pos, gamma_0neg, gamma_1pos, gamma_1neg, beta_inv_temp, bias) — Beta distribution belief tracking with valence-dependent decay modulated by entropy changes
- **model_family:** Bayesian
- **model_class:** PE learning / Belief updating
- **all_models_tested:** 1. Dynamic Bayesian RL (DBRL) — family: Bayesian RL; n_params: 6; metric: AIC + BMS exceedance probability 2. Simplified Bayesian RL (BRL) — family: Bayesian RL; n_params: 4; metric: AIC + BMS exceedance probability 3. Standard Reinforcement Learning (RL) — family: RL (Q-learning); n_params: 3; metric: AIC + BMS exceedance probability
- **model_mb_mf:** Bayesian
- **model_params:** - gamma_0pos: positive decay intercept (degree of decay of positive outcomes) [range 0.1–1.0]; Healthy TG mean = -0.87 (SE 0.04), SM mean = -0.88 (SE 0.04); Anxious TG mean = -0.82 (SE 0.06), SM mean = -0.79 (SE 0.06) - gamma_0neg: negative decay intercept (degree of decay of negative outcomes) [range 0.1–1.0]; Healthy TG mean = -0.95 (SE 0.04), SM mean = -0.97 (SE 0.04); Anxious TG mean = -0.83 (SE 0.06), SM mean = -0.96 (SE 0.06) - gamma_1pos [S]: positive dynamic decay (modulation of positive decay by entropy change Delta-H) [range -2.0 to 0]; Healthy TG mean = 0.44 (SE 0.02), SM mean = 0.43 (SE 0.02); Anxious TG mean = 0.54 (SE 0.03), SM mean = 0.53 (SE 0.03) - gamma_1neg [S]: negative dynamic decay (modulation of negative decay by entropy change Delta-H) [range -2.0 to 0]; Healthy TG mean = 0.52 (SE 0.02), SM mean = 0.48 (SE 0.02); Anxious TG mean = 0.49 (SE 0.02), SM mean = 0.48 (SE 0.02) - beta (inverse temperature): explore/exploit trade-off [range 1–20]; Healthy TG mean = 7.31 (SE 0.26), SM mean = 7.26 (SE 0.26); Anxious TG mean = 7.17 (SE 0.38), SM mean = 6.40 (SE 0.38) - bias: choice benchmark for investing [range 0.1–1.0]; Healthy TG mean = 0.52 (SE 0.01), SM mean = 0.50 (SE 0.01); Anxious TG mean = 0.52 (SE 0.02), SM mean = 0.47 (SE 0.02)  [HIGH — values from Supplement Table S4]
- **social_param:** gamma_0pos - gamma_0neg (decay-rate difference) [S] — indexes asymmetric weighting of positive vs. negative social feedback; healthy subjects selectively shift toward weighting losses more in social contexts, anxious subjects do not. Also gamma_1pos, gamma_1neg — dynamic decay parameters indexing sensitivity to uncertainty changes.
- **social_param_name:** gamma_1pos
- **social_param_value:** 0.44
- **social_param_sd:** 0.02
- **social_param_range:** -2.0–0
- **model_comparison_metric:** AIC + Bayesian Model Selection (BMS) with protected exceedance probability (pxp) using spm_BMS
- **how_model_fit:** individual-level-fit (MLE via fmincon in MATLAB across 5 iterations per subject)
- **data_type_fit_to:** choice behavior (binarized investment decisions: $1.00 vs $0.10)---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging)---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 354 (257 healthy, 97 clinically significant anxiety on GAD-7; from initial N = 412 recruited on MTurk; 58 excluded based on AIC criteria); ages mean = 34.61, SD = 9.41; 53.1% female
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Uses an incentive-compatible trust game with real monetary stakes and drifting reward contingencies designed to simulate evolving real-world social exchanges; however, partners are preprogrammed algorithms (not real people), and the task is conducted online via MTurk. 70% of participants reported little to no doubt partners were real. The matched social/non-social design is a strength.
- **eligibility_flag:** 
- **concerns:** Partners were preprogrammed algorithms, not real humans — this limits ecological validity of the "social" condition. Anxiety was assessed via self-report GAD-7 threshold, not clinical diagnosis. The decision space was binarized for modeling despite continuous investment options. Within-subject counterbalanced design means order effects could influence learning. No neuroimaging data to assess neural mechanisms. [HIGH]
- **limitations_reported:** The design and analysis plans were not preregistered"; authors acknowledge that overinvestment in exploitative partners by anxious individuals "could also indicate use of an alternative decision policy—one in which subjects were strategically forgoing monetary gains to promote trust and cooperation in exploitative social partners"; authors note this "may represent learning differences at the level of decision making rather than at the level of uncertainty perception"; future research needed to "further explore how uncertainty perception affects downstream learning and decision-making."
- **limitations_categorized:** not preregistered; alternative interpretation of key finding; limited ecological validity (preprogrammed partners); no neuroimaging; self-report anxiety measure
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
- **wc_rule10:** Yes
- **wc_score:** 6.5
- **wc_total:** 6.5

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
- pop_anxiety
- pop_healthy_adults
- rr_pop_anxiety
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target+context
- spec_source = partly
- spec_target = partly
- tax_domain_C_exchange_interdependence
- tax_domain_G_uncertainty_volatility
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_bayesian
- tax_param_decay
- tax_param_social_weight
- tax_param_temperature
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = trust
- tax_rr_secondary_topic = social_uncertainty
- tax_rr_topic_social_uncertainty
- tax_rr_topic_trust
- tax_social_nonsocial_comparison
- tax_topic_social_uncertainty
- tax_topic_trust
