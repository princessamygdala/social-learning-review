# Chang et al. (2010)

- **study_id:** `a6e4643b5be9b53d0_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Chang, L. J., Doll, B. B., van 't Wout, M., Frank, M. J., & Sanfey, A. G. (2010). Seeing is believing: Trustworthiness as a dynamic belief. *Cognitive Psychology*, *61*(2), 87–105. https://doi.org/10.1016/j.cogpsych.2010.03.001
- **citation_short:** Chang et al. (2010)
- **doi:** 10.1016/j.cogpsych.2010.03.001
- **publication_type:** peer-reviewed journal
- **year:** 2010.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** DepartmentsofCognitive&LinguisticSciencesandPsychology,BrownUniversity,190ThayerSt,Providence,; mpiricalworkhasshownthatmostinvestorsarewillingtotransferabouthalfoftheir; lableinformation,andthenupdatethisjudgmentbasedonsubsequentinteractions; DepartmentofPsychology,UniversityofArizona,1503E; UniversityBlvd,Tucson,AZ85721,UnitedStates; etheirtrustbykeepingall(ormost)of; ethissensitiveinformationtoDavid; ethenotionoftrustworthiness; emails: asanfey@u.arizona.edu
- **code_url:** 

## Computational level
- **study_focus:** Trust learning — how implicit facial trustworthiness judgments interact with experienced trustworthiness (reciprocation history) to dynamically update trust beliefs in an iterated social exchange.
- **study_focus_short:** Trust learning
- **learning_mode_description:** - Learning mode: Learning from a partner's reciprocation behavior and initial facial trustworthiness cues about the partner's trustworthiness (probability of reciprocation)   - Learning from:     - Source type (social): other (partner)     - Source content (social): outcome (reciprocation vs. defection) and stimulus (facial trustworthiness)   - Learning about:     - Target type (social): other (partner)     - Target content (social): state (mental state; trustworthiness belief / probability of reciprocation)
- **task_description:** Participants played a repeated Trust Game as Player A (investor) with four partners (2x2 design: high/low facial trustworthiness crossed with high/low reciprocation probability of 80%/20%) over 15 trials each, deciding how much of a $10 endowment to invest. Two slot machines served as non-social controls.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (4 partners: 2 high/low facial trustworthiness x 2 high/low reciprocation probability; plus 2 slot machine controls)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Photographs of faces (normed for trustworthiness from Winston stimulus set), slot machine images; monetary outcomes (investment x4, 50% split if reciprocated, $0 if not)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Main effect of reciprocation probability on investment amount (η² = 0.68; F(1,60) = 125.70)   - Partner type x reciprocation interaction on investment (η² = 0.08; F(2,120) = 5.34)   - Facial trustworthiness effect on first-trial investment (η² = 0.05; F(2,120) = 3.22)   - Interaction persists on last trial (η² = 0.06; F(2,120) = 4.13)   - Post-game trustworthiness ratings: main effect of partner type (η² = 0.10), reciprocation (η² = 0.75), interaction (η² = 0.13)   - Dynamic Belief model best fit in-sample (AIC = 21460.57) and out-of-sample (AIC = 21619.04)   - Model-predicted trustworthiness ratings better predict subjective ratings than normative ratings (β = 0.62 vs. β = 0.13; Williams T2: t(57) = 3.15)
- **effect_size:** - Main Results:   - Main effect of reciprocation probability on investment amount (η² = 0.68; F(1,60) = 125.70)   - Partner type x reciprocation interaction on investment (η² = 0.08; F(2,120) = 5.34)   - Facial trustworthiness effect on first-trial investment (η² = 0.05; F(2,120) = 3.22)   - Interaction persists on last trial (η² = 0.06; F(2,120) = 4.13)   - Post-game trustworthiness ratings: main effect of partner type (η² = 0.10), reciprocation (η² = 0.75), interaction (η² = 0.13)   - Dynamic Belief model best fit in-sample (AIC = 21460.57) and out-of-sample (AIC = 21619.04)   - Model-predicted trustworthiness ratings better predict subjective ratings than normative ratings (β = 0.62 vs. β = 0.13; Williams T2: t(57) = 3.15)
- **learning_from:** Other (partner); facial appearance (implicit trustworthiness cue) and reciprocation outcomes
- **learning_about:** Other (partner); trustworthiness as a dynamic belief about probability of reciprocation  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Dynamic Belief model: Gain-Loss RL with dynamic trustworthiness belief update (α_G, α_L, φ, h; 4 params). T_S(t+1) = T_S(t) + φ[Outcome(t) - T_S(t)]; V_S(t+1) = V_S(t) + α_G·δ⁺ + α_L·δ⁻ + h[T_S(t+1)·repay - T_S(t+1)·abuse]
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning / Belief updating
- **all_models_tested:** [   {"name": "Gain-Loss (baseline)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AIC = 21620.29 (train); 21753.11 (test)"},   {"name": "GL Initialization", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC = 21615.64 (train); 21764.75 (test)"},   {"name": "Confirmation Bias", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC = 21496.84 (train); 21663.21 (test)"},   {"name": "Trust Decay", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC = 21485.47 (train); 21672.25 (test)"},   {"name": "Dynamic Belief", "family": "Rescorla-Wagner", "n_params": 4, "metric": "AIC = 21460.57 (train); 21619.04 (test)"} ]
- **model_mb_mf:** MF
- **model_params:** - α_G (gain learning rate): 0.01 — weight for positive prediction error (reciprocation) - α_L (loss learning rate): 0.34 — weight for negative prediction error (defection) - φ (trustworthiness learning rate) [S]: 0.12 — rate at which trustworthiness belief T_S updates based on outcomes - h (trustworthiness scaling) [S]: 0.45 — scales influence of trustworthiness belief on value update
- **social_param:** φ (trustworthiness learning rate) — rate at which the belief about a partner's trustworthiness updates based on reciprocation outcomes; h (trustworthiness scaling) — scales how much the trustworthiness belief biases the value update as a bonus/deduction
- **social_param_name:** φ
- **social_param_value:** 0.12
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (with cross-validation: train on odd trials, test on even trials). BIC also reported (consistent results; Dynamic Belief BIC = 6725.86, lowest).
- **how_model_fit:** group-level-fit (parameters estimated for entire group by minimizing SSE pooled across subjects; individual trial-by-trial sequences used but parameters shared)
- **data_type_fit_to:** choice behavior (investment amounts in dollars)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A — no neuroimaging data collected.
- **coordinates_peak:** N/A — no neuroimaging.
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 61 (64 recruited, 3 excluded for not understanding the task); mean age = 18.67 (SD = 1.38); 79% female. Undergraduate psychology participant pool, University of Arizona.
- **population_category:** undergraduates
- **population_age_range:** M=18.67 (SD=1.38)
- **ecological_validity:** Lab-based Trust Game with photographs of partners (not live interaction); participants likely knew partners were not real people (dated photographs); slot machine control condition provides non-social baseline. Limited ecological validity due to stylized economic game with fixed reciprocation probabilities.
- **eligibility_flag:** 
- **concerns:** Parameters estimated at group level due to small number of trials per condition (N = 15 per partner), limiting individual-level inference. Authors note parameters "should be interpreted with caution." No parameter recovery or model recovery analyses reported. Participants likely did not believe they were playing real people (no manipulation check for belief in real partner). Cross-validation was odd/even split rather than leave-one-out or k-fold. Investment multiplied by 4 but slot machine only doubled — asymmetric payoff structure for social vs. non-social conditions.
- **limitations_reported:** Did not ask participants whether they believed they were playing a "real person"; photographs were dated; limited to implicit trustworthiness signals (facial appearance) rather than explicit moral information; small number of trials per condition limits individual parameter estimation stability; group-level parameter estimation due to collinearity between parameters.
- **limitations_categorized:** limited ecological validity; no manipulation check; task simplicity; sample size (trials per condition); limited generalizability; group-level fitting only
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 6.0
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params confidence: MEDIUM — parameters reported from group-level fit with caution noted by authors about limited trials - wc_guidelines Rule 3: MEDIUM — simulation shown post-hoc but unclear if done pre-fitting - ecological_validity: MEDIUM — inferred from task description and discussion
- **cannot_find:** Supplement (no supplement found for this paper); individual-level parameter estimates; formal effect sizes for model comparison (only AIC/BIC reported, no likelihood ratio tests)
- **other_notes:** This is a behavioural-only study (no neuroimaging). The Dynamic Belief model is notable for being one of the first computational models of trust updating in an iterated social exchange. The key innovation is that trustworthiness serves both as an input to and output of the learning process — facial trustworthiness initializes the belief, which then updates based on partner behavior, and this updated belief in turn modulates how future outcomes are weighted. The non-social slot machine control was not formally modeled. The paper also reports BIC values in a footnote (consistent with AIC rankings).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_bayesian
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = trust
- tax_rr_secondary_topic = trait_impression
- tax_rr_topic_trait_impression
- tax_rr_topic_trust
- tax_topic_trait_impression
- tax_topic_trust
