# Siegel et al. (2019)

- **study_id:** `ae7c3b95a8b8f7d2a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Siegel, J. Z., Estrada, S., Crockett, M. J., & Baskin-Sommers, A. (2019). Exposure to violence affects the development of moral impressions and trust behavior in incarcerated males. *Nature Communications*, *10*, 1942. https://doi.org/10.1038/s41467-019-09962-9
- **citation_short:** Siegel et al. (2019)
- **doi:** 10.1038/s41467-019-09962-9
- **publication_type:** peer-reviewed journal---
- **year:** 2019.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** sectionalandlongitudinalresearchfindsthatexposuretoviolence rowly centered around a few points within that range25–27; mpirical evidence identifying and Scale(ETV)29,aswellasaclinicalassessmentmeasuringdifferent; etherotherindividualsmight development of subjective impressions, and consequently, the; ether in a larger distinct components of harm learning: the ability to develop; ether it is witnessing fromthegeneralpopulation,thistypeofsampledoesserveasan; DepartmentofExperimentalPsychology,UniversityofOxford,OxfordOX12JD,UK; DepartmentofPsychology, YaleUniversity,NewHaven,CT06520,; mpirical e
- **code_url:** 

## Computational level
- **study_focus:** Moral impression learning / harm learning / trust learning -- How exposure to violence affects the ability to learn about others' harmfulness from observed choices, form moral impressions, and adapt trust behavior.
- **study_focus_short:** Moral impression learning / harm learning / trust learning -- How exposure to
- **learning_mode_description:** - Learning mode: Learning from observed choices of agents (who decide whether to inflict shocks for money) to form beliefs about agents' harm preferences and moral character, then using those impressions to guide trust behavior.   - Learning from:     - Source type (social): other (two agents -- "good" and "bad" deciders)     - Source content (social): action/policy (agents' choices between money and shocks to another person)   - Learning about:     - Target type (social): other (the two agents)     - Target content (social): state (mental state; moral character / harm preference / trustworthiness)
- **task_description:** Participants predicted sequences of 50 choices made by each of two agents who decided between inflicting more shocks on another person for more money vs. fewer shocks for less money, receiving accuracy feedback after each prediction and rating agents' moral character every three trials. After the learning phase, participants played a one-shot trust game with each agent.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (2 agents: good agent and bad agent)
- **n_players:** dyadic (2)
- **partner_type:** unclear
- **stimuli:** Text-based choice options (shocks vs. money trade-offs), accuracy feedback, moral character rating scales (nasty-to-nice), trust game endowment
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - ETV score did not predict prediction accuracy for either agent (good: ρ = -0.065; bad: ρ = 0.043)- ETV score was not related to belief volatility ω for either agent (good: ρ = 0.025; bad: ρ = -0.014) or Δω (ρ = 0.008)- Higher ETV scores predicted less differentiation in moral impressions between good and bad agents (ETV x Agent interaction: β = 0.037 ± 0.009, t = 4.222)- Higher ETV scores predicted more favorable impressions of bad agent (β = 0.019 ± 0.007) and less favorable impressions of good agent (β = -0.019 ± 0.006)- Higher ETV scores predicted less differentiation in uncertainty ratings (ETV x Agent: β = -0.045 ± 0.009, t = -4.973)- Trust game: Agent effect moderated by ETV score (F(13,119) = 2.142, η² = 0.210)- Higher ETV scores predicted less trust with good agent (ρ = -0.220)- Indirect mediation effect of Δjudgment on Δentrust: effect = -0.812, 95% CI [-1.705, -0.054]- Serial mediation (ETV → Δjudgment → Δentrust → prison violations): indirect effect = 0.099, 95% CI [0.002, 0.274]- Less discrepant trust behavior associated with more prison violations (ρ = -0.208) and aggressive violations (ρ = -0.217)
- **effect_size:** - Main Results:   - ETV score did not predict prediction accuracy for either agent (good: ρ = -0.065; bad: ρ = 0.043)- ETV score was not related to belief volatility ω for either agent (good: ρ = 0.025; bad: ρ = -0.014) or Δω (ρ = 0.008)- Higher ETV scores predicted less differentiation in moral impressions between good and bad agents (ETV x Agent interaction: β = 0.037 ± 0.009, t = 4.222)- Higher ETV scores predicted more favorable impressions of bad agent (β = 0.019 ± 0.007) and less favorable impressions of good agent (β = -0.019 ± 0.006)- Higher ETV scores predicted less differentiation in uncertainty ratings (ETV x Agent: β = -0.045 ± 0.009, t = -4.973)- Trust game: Agent effect moderated by ETV score (F(13,119) = 2.142, η² = 0.210)- Higher ETV scores predicted less trust with good agent (ρ = -0.220)- Indirect mediation effect of Δjudgment on Δentrust: effect = -0.812, 95% CI [-1.705, -0.054]- Serial mediation (ETV → Δjudgment → Δentrust → prison violations): indirect effect = 0.099, 95% CI [0.002, 0.274]- Less discrepant trust behavior associated with more prison violations (ρ = -0.208) and aggressive violations (ρ = -0.217)
- **learning_from:** Other's choices (two agents' decisions about inflicting shocks for money); feedback on prediction accuracy
- **learning_about:** Other's harm preferences (moral character / trustworthiness of good vs. bad agent)---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Hierarchical Gaussian Filter (HGF; 2 params: ω tonic volatility, β prediction noise)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "1-learning-rate Rescorla-Wagner", "family": "Rescorla-Wagner", "n_params": 2, "metric": "LME (sum = -6376)"} - {"name": "2-learning-rate Rescorla-Wagner (asymmetric)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "LME (sum = -6055)"} - {"name": "Hierarchical Gaussian Filter (HGF)", "family": "Bayesian belief updating", "n_params": 2, "metric": "LME (sum = -5920)"} [WINNER]
- **model_mb_mf:** Bayesian
- **model_params:** - ω (tonic volatility): Governs rate at which beliefs evolve over time; controls volatility of beliefs at second level. Prior mean = -4, prior variance = 1. Estimated in native space. [S] -- captures individual differences in learning rate about social agents' harm preferences.- β (prediction noise): Sensitivity of prior beliefs to the relative utility of different outcomes. Prior mean = 1, prior variance = 1. Estimated in log-space.- μ (latent variable): Trial-wise belief estimate about agent's harm preference (exchange rate between money and pain). Not estimated as a free parameter.- σ (latent variable): Trial-wise uncertainty on beliefs. Not a free parameter.- Prior on x₂ (agent's harm aversion κ): μ₂ = 0.5 (fixed, neutral); σ₂ = 0.35 (fixed).
- **social_param:** ω (tonic volatility) [S] -- captures individual differences in the rate of belief updating about another person's moral character (harm preference). Although ω is a general learning parameter, in this task it is applied specifically to learning about a social agent's preferences.
- **social_param_name:** ω
- **social_param_value:** -4
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Log-model evidence (LME); Bayesian Model Selection (BMS) with protected exceedance probability
- **how_model_fit:** individual-level-fit (hierarchical Bayesian; participant-specific parameters estimated)
- **data_type_fit_to:** choice behavior (participants' binary predictions of agents' choices)---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study only)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 119 incarcerated males from a high-security correctional institution in Connecticut; ages 20-58 (M = 34.98, SD = 9.94)
- **population_category:** healthy adults
- **population_age_range:** 20–58
- **ecological_validity:** Moderate -- task uses abstract shock-for-money decisions rather than naturalistic harmful behavior; however, trust game outcomes significantly predicted real-world prison violations, providing ecological validity for the behavioural measure. The sample (incarcerated males with full range of ETV scores) enhances ecological validity for the target population.
- **eligibility_flag:** 
- **concerns:** - The trust game was not incentivized with real money (Connecticut DOC rules prohibited paying incarcerated participants); instead a leaderboard was used. This could affect trust game validity. - Cross-sectional design prevents causal inference about direction of effects between ETV and learning. - The "social agents" in the learning task were simulated (pre-determined choice sequences), not real people -- though this is standard in the field. - The computational model (HGF) was fit only to prediction data, not to impression ratings or trust behavior. The link between model parameters and the key findings (impression disruption) is correlational rather than mechanistic.
- **limitations_reported:** Sample limited to incarcerated offenders, unknown whether incarceration status impacts the relationship between exposure to violence and harm learning; community and university samples often suffer from restricted range in ETV scores; implementing shocks in the task is not as extreme as real-world violence experiences; need to replicate in non-incarcerated samples with representative ETV range; future research should vary stimuli used to assess learning considering cultural and situational contexts
- **limitations_categorized:** limited generalizability (incarcerated sample only); limited ecological validity (abstract shock stimuli vs. real-world violence); task simplicity (shock paradigm less extreme than real violence); sample specificity (no non-incarcerated comparison group)
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
- **wc_rule10:** Partial
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
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target+context
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_domain_F_affective_moral
- tax_mod_action_observation
- tax_mod_mentalizing_inference
- tax_model_HGF
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_C_exchange_interdependence
- tax_rr_domain_F_affective_moral
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_learning_rate
- tax_rr_param_precision
- tax_rr_primary_topic = moral_harm
- tax_rr_secondary_topic = trust
- tax_rr_topic_moral_harm
- tax_rr_topic_trust
- tax_topic_moral_harm
- tax_topic_trust
