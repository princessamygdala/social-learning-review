# Bang et al. (2017)

- **study_id:** `a95eb220fdbe63dcd_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Bang, D., Aitchison, L., Moran, R., Herce Castanon, S., Rafiee, B., Mahmoodi, A., Lau, J. Y. F., Latham, P. E., Bahrami, B., & Summerfield, C. (2017). Confidence matching in group decision-making. *Nature Human Behaviour*, *1*, 0117.
- **citation_short:** Bang et al. (2017)
- **doi:** 10.1038/s41562-017-0117
- **publication_type:** peer-reviewed journal---
- **year:** 2017.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** ether, estimating and was driven by an underlying convergence in accuracy (fraction of; Department of Experimental Psychology, University of Oxford, Oxford OX1 3UD, UK; ethods), pairs of participants (30 groups, tested; Centre for Evolution and Human Sciences,; University of Oxford, Oxford OX1 4AU, UK; ether the ball crossed the goal line; mity to the incident); ether than when
- **code_url:** 

## Computational level
- **study_focus:** Social influence learning / confidence alignment in group decision-making
- **study_focus_short:** Social influence learning / confidence alignment in group decision-making
- **learning_mode_description:** - Learning mode: Learning to match one's own confidence reports to a partner's confidence during joint perceptual decisions   - Learning from:     - Source type (social): other (anonymous partner)     - Source content (social): action/policy (partner's communicated confidence level)   - Learning about:     - Target type (non-social): self     - Target content (non-social): action/policy (own confidence reporting function / subjective mapping)
- **task_description:** Pairs of participants each privately judged which of two visual displays contained a higher-contrast target and reported confidence (1–6). In the social condition, both responses were revealed and the higher-confidence decision was automatically selected as the joint decision; feedback on accuracy was provided.
- **task_paradigm:** Social influence task
- **players:** Multi-agent (dyad), symmetric. Six experiments with varying partners: EXP1–3 real partners; EXP4 computer-generated partners; EXP5–6 anonymous real partners.
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Gabor patches (contrast discrimination), confidence scale (1–6 discrete or continuous), monetary outcomes in EXP5 (proper scoring rule).
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Group members' mean confidence converged in the social condition but not isolated condition (EXP1: t(29) = 4.195, P < 0.001, paired t-test)- Convergence in confidence did not scale with convergence in accuracy (all P > 0.25 per experiment)- Group optimality scaled with similarity of expertise (P < 0.001, robust regression across N = 82 groups)- Confidence matching helped poorly calibrated groups but disadvantaged well-calibrated groups (EXP4: interaction between calibration and change in joint accuracy, P < 0.001)- Trial-by-trial serial dependence: partner's confidence on t−1 to t−3 predicted participant's confidence (all t(163) > 3.900, all P < 0.001)- Confidence matching persisted under proper scoring rule incentives (EXP5: t(9) = 2.158, P = 0.045)- Social task showed stronger matching than observe-only task (EXP6: t(22) = 2.100, P = 0.047)
- **effect_size:** Effect sizes not reported as Cohen's d, r², η², or β. Only t-statistics and P-values provided. (HIGH — the paper genuinely does not report standardized effect sizes)
- **learning_from:** Other (partner); partner's communicated confidence on recent trials.
- **learning_about:** Self; own confidence reporting strategy (subjective mapping from probability correct to confidence).---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Temporal difference learning model: c^{o}_{t+1} = c^{o}_t + γ(c^{p}_t − c^{o}_t), where γ is adaptation rate; combined with partner confidence estimate update: c^{p}_{t+1} = c^{p}_t + α(ĉ^{p}_t − c^{p}_t), where α is learning rate.
- **model_family:** Signal detection
- **model_class:** PE learning
- **all_models_tested:** - Signal detection model (SDT): used for simulating optimal benchmarks and confidence landscapes; 1 free parameter (σ, sensory noise); thresholds determined by observed response distributions. Not formally compared via model comparison metric. - Temporal difference learning model: process model for confidence matching; parameters γ (adaptation rate) and α (learning rate); used for qualitative predictions about serial dependence.  Note: The paper does NOT perform formal model comparison (e.g., BIC/AIC). The SDT model is used for simulation/benchmarking, and the TD learning model is used for qualitative trial-by-trial predictions. Neither is "fit" competitively against alternatives.
- **model_mb_mf:** MF (model-free temporal difference learning)
- **model_params:** - σ (sensory noise): fitted per participant; only free parameter of SDT model- γ (adaptation rate): fixed at 0.20 in simulations; governs how much agent adjusts own confidence toward partner's- α (learning rate): fixed at 0.12 in simulations; governs update of estimated partner confidence- Thresholds: determined by observed response distributions, not free parameters
- **social_param:** γ (adaptation rate) — rate at which agent adapts own mean confidence toward estimated partner mean confidence [S]. α (learning rate) — rate at which agent updates estimate of partner's mean confidence [S].
- **social_param_name:** γ
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** None. No formal model comparison conducted. SDT model fit assessed by squared error between observed and model-derived accuracy. TD learning model evaluated qualitatively by whether it predicts observed serial dependence patterns.
- **how_model_fit:** The SDT model: individual-level-fit (minimized squared error between observed and model-derived accuracy per participant). The TD learning model: simulate-and-compare (simulated predictions compared qualitatively to empirical serial dependence).
- **data_type_fit_to:** choice behavior (accuracy, confidence reports)---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A (no neuroimaging)---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** EXP1: N=60 (30 pairs), Iran, all male, ages 18–40; EXP2: N=30 (15 pairs), UK, all male; EXP3: N=30 (15 pairs), UK, all male; EXP4: N=38 (19 female), UK; EXP5: N=20 (13 female), UK; EXP6: N=24 (14 female), UK. Total unique participants: N=202.
- **population_category:** healthy adults
- **population_age_range:** 18–40
- **ecological_validity:** Low-to-moderate. Perceptual discrimination task is highly controlled but artificial. Social interaction is mediated by computer display with no face-to-face communication. EXP4 uses deception (computer partners). However, tested across two cultures (Iran, UK) and with both discrete and continuous confidence scales, enhancing generalizability.
- **eligibility_flag:** FLAGGED — Borderline on "learning over time" criterion. The confidence matching effect is demonstrated at the aggregate level (mean confidence converges across blocks) and at short time scales (trial-by-trial serial dependence extending 3 trials back). However, the TD learning model is used for qualitative simulation rather than formal fitting, and the primary analyses are about aggregate convergence rather than trial-by-trial learning dynamics. The computational modeling is relatively light (SDT for benchmarking + qualitative TD model). This is borderline between social influence/adaptation and genuine computational modeling of learning.
- **concerns:** - No formal model comparison between competing models (e.g., TD learning vs. alternative adaptation rules) - TD learning model parameters (γ, α) were fixed in simulations rather than fitted to individual data - No parameter recovery or model recovery analyses - Effect sizes not reported in standardized form (only t-statistics and P-values) - Sample sizes for individual experiments are small (10–30 pairs) - EXP1–3 used only male participants - Supplement referenced but not accessible for verification of supplementary figures and methods
- **limitations_reported:** Authors acknowledge: confidence matching is sub-optimal and can cause miscommunication about who is more likely to be correct; the strategy is costly when group members differ in expertise; alternative explanations exist (e.g., maintaining equal influence, avoiding conflict, diffusing responsibility); it remains to be seen whether social interaction changes internal probability estimates vs. just the report function; the learning model parameters were chosen to match observed data rather than formally fitted.
- **limitations_categorized:** sub-optimal heuristic; limited ecological validity; alternative explanations not ruled out; model parameters not formally fitted; task simplicity; no parameter recovery; limited generalizability (male-only samples in 3/6 experiments)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Partial
- **wc_rule10:** Partial
- **wc_score:** 4.5
- **wc_total:** 4.5

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
- rr_tax_mod_active_interaction
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_E_self_in_social_context
- tax_mod_active_interaction
- tax_mod_multiplayer_live
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = signal_detection
- tax_rr_model_signal_detection
- tax_rr_param_precision
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = self_belief_confidence
- tax_rr_topic_self_belief_confidence
- tax_rr_topic_social_info_use
- tax_topic_self_belief_confidence
- tax_topic_social_info_use
