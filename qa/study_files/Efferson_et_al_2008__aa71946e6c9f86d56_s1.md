# Efferson et al. (2008)

- **study_id:** `aa71946e6c9f86d56_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Efferson, C., Lalive, R., Richerson, P. J., McElreath, R., & Lubell, M. (2008). Conformists and mavericks: The empirics of frequency-dependent cultural transmission. *Evolution and Human Behavior*, *29*(1), 56–64.
- **citation_short:** Efferson et al. (2008)
- **doi:** 10.1016/j.evolhumbehav.2007.08.003
- **publication_type:** peer-reviewed journal
- **year:** 2008.0
- **field_of_study:** Psychology
- **affiliations_raw:** mity is a type of social learning that has received considerable attention among social psychologists and human evolutionary; mityiscompellingbecauseitistheonlyformoffrequency-dependentsocialinfluencethatproducesbehaviorallyhomogeneoussocial; DepartmentofEconometricsandPoliticalEconomy,UniversityofLausanne,1015Lausanne,Switzerland; InstituteforEmpiricalResearchinEconomics,UniversityofZürich,8006Zürich,Switzerland; mpirical research does not identify conformity cleanly; mpirical research cannot identify conformity as a; mitationofsuccess,conformityplaysacriticalrolein; mity is more than just a
- **code_url:** 

## Computational level
- **study_focus:** Conformity / frequency-dependent social learning — whether individuals show a disproportionate tendency to follow the majority (conformity) versus linear or nonconformist frequency dependence.
- **study_focus_short:** Conformity / frequency-dependent social learning
- **learning_mode_description:** - Learning mode: Learning from the distribution of others' choices about which technology is optimal   - Learning from:     - Source type (social): group (5 individual learners)     - Source content (social): action/policy (distribution of color choices among individual learners)   - Learning about:     - Target type (non-social): world (which technology/color is optimal)     - Target content (non-social): state (world state; identity of optimal technology)
- **task_description:** In each of 150 periods (6 blocks of 25), players chose between two color-coded technologies with stochastic payoffs (one optimal). Individual learners received private payoff feedback; social learners only observed the distribution of choices among the 5 individual learners before making their own choice, with no payoff feedback until session end.
- **task_paradigm:** Social bandit / herding
- **players:** Multi-agent (2 groups within each "world"), asymmetric. Group of 5 individual learners; group of 6–7 social learners. Social learners observe individual learners' choices but not vice versa.
- **n_players:** small group (3-4)
- **partner_type:** human (live)
- **stimuli:** Abstract color-coded technologies (red vs. blue), stochastic payoff feedback (truncated normal distributions).
- **method:** behavioural
- **method_full:** Behavioural (lab experiment, computerized via z-Tree)
- **main_result:** - Individual learners showed a strong upward trend in choosing optimally over 25 periods (β_period = 0.012, R² = 0.930, p < .01, Newey-West corrected) - Two-parameter model (stated conformists vs. not) vastly improved over single-D model (AIC_c = 4032.78 vs. 4320.56; Akaike weight ≈ 1.27 × 10⁻⁴⁹ vs. 4.11 × 10⁻¹¹²) - Fixed-effects model (40 individual D parameters) best fitting (AIC_c = 3807.60; Akaike weight > 0.99) - Stated conformists: D̂ = 0.3805 (SE = 0.0250), consistent with conformity (D > 0) - Not stated conformists: D̂ = −0.4843 (SE = 0.0438), consistent with ignoring or weakly opposing frequency information - Strong positive relationship between D and earnings among social learners (visible in Fig. 5; no formal r or d reported)
- **effect_size:** - Individual learners showed a strong upward trend in choosing optimally over 25 periods (β_period = 0.012, R² = 0.930, p < .01, Newey-West corrected) - Two-parameter model (stated conformists vs. not) vastly improved over single-D model (AIC_c = 4032.78 vs. 4320.56; Akaike weight ≈ 1.27 × 10⁻⁴⁹ vs. 4.11 × 10⁻¹¹²) - Fixed-effects model (40 individual D parameters) best fitting (AIC_c = 3807.60; Akaike weight > 0.99) - Stated conformists: D̂ = 0.3805 (SE = 0.0250), consistent with conformity (D > 0) - Not stated conformists: D̂ = −0.4843 (SE = 0.0438), consistent with ignoring or weakly opposing frequency information - Strong positive relationship between D and earnings among social learners (visible in Fig. 5; no formal r or d reported)
- **learning_from:** group; distribution of choices among individual learners (social information about behavioral frequencies)
- **learning_about:** world; which of two technologies is optimal  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Frequency-dependent social learning model with individual fixed effects for D parameter (Eq. 2 from main text; 40 D parameters, one per social learner). P(choose R | i_t) = i_t(1−D)/N if i_t < N/2; 1/2 if i_t = N/2; i_t(1−D)/N + D otherwise.
- **model_family:** Agent-based / evolutionary
- **model_class:** Other
- **all_models_tested:** - {"name": "Single D", "family": "Frequency-dependent transmission", "n_params": 1, "metric": "AIC_c = 4320.56"} - {"name": "Conformist (Y or N) — two-group D", "family": "Frequency-dependent transmission", "n_params": 2, "metric": "AIC_c = 4032.78"} - {"name": "Individual fixed effects", "family": "Frequency-dependent transmission", "n_params": 40, "metric": "AIC_c = 3807.60"}
- **model_mb_mf:** N/A (not RL)
- **model_params:** - D: frequency-dependence parameter. D ∈ (0,1] = conformist; D = 0 = linear; D ∈ [−1,0) = nonconformist. [S] — this is the key social parameter controlling response to social frequency information.   - Single model: D̂ = 0.1081 (SE = 0.0005)   - Two-group model: D̂_Y (stated conformists) = 0.3805 (SE = 0.0250); D̂_N (not stated conformists) = −0.4843 (SE = 0.0438)   - Fixed effects: 40 individual D values (range: −0.9844 to 0.9471; see Table S2 in supplement)
- **social_param:** D — controls the degree and direction of frequency-dependent social influence. Positive D = conformity (disproportionate tendency to follow majority); negative D = nonconformity.
- **social_param_name:** D
- **social_param_value:** 0
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC_c (corrected Akaike Information Criterion) with Akaike weights
- **how_model_fit:** individual-level-fit (maximum likelihood estimation; log-likelihood function derived from Bernoulli observations, Eq. 13 in supplement)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 70 (30 individual learners, 40 social learners); University of Zürich and Swiss Federal Institute of Technology undergraduates; psychology students excluded.
- **population_category:** undergraduates
- **population_age_range:** 
- **ecological_validity:** Low — abstract two-armed bandit task with color-coded technologies and stochastic payoffs. No naturalistic social interaction; social learners passively observe frequency distributions without communication. However, the paradigm cleanly isolates frequency-dependent social learning from individual learning.
- **eligibility_flag:** 
- **concerns:** - Self-report questionnaire used for a priori grouping of social learners (stated conformists vs. not) — validity of self-report categorization uncertain - No formal test of the relationship between D and earnings (Fig. 5 shows visual pattern but no reported correlation coefficient or effect size) - Psychology students excluded, limiting generalizability - No parameter recovery or model recovery analyses reported - The model is relatively simple (piecewise linear) and may not capture nonlinear response patterns
- **limitations_reported:** Authors note: the stability of heterogeneity in social learning strategies across cultures or social settings is unclear; the experiment did not systematically vary the value of conformity, so it cannot determine whether subjects flexibly adjust their use of frequency-dependent social information; cannot distinguish innate desire to conform from recognition of its practical value; baseline of errors in Asch-type designs conflates frequency dependence with other biases.
- **limitations_categorized:** limited ecological validity; limited generalizability; task simplicity; inability to distinguish motivations; no systematic manipulation of key variable
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
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM — R² = 0.930 for individual learning trend reported, but no formal effect size for the key D–earnings relationship (Fig. 5) - model_family: MEDIUM — classified as "frequency-dependent cultural transmission model"; this is the authors' own framework, not a standard model family label - wc_3 (simulate): MEDIUM — theoretical dynamics simulated but unclear whether statistical model was simulated before fitting
- **cannot_find:** - Formal effect size for D–earnings relationship - Exact ages of participants - Whether code/data are publicly archived
- **other_notes:** This is a foundational paper in the cultural evolution literature on conformity. The key contribution is the formal distinction between conformity (D > 0, producing behavioral homogeneity) and nonconformity (D < 0, producing heterogeneity), and the empirical finding that both types coexist in the population. The Bayesian updating model in the supplement (Eqs. 5–9) provides additional theoretical grounding but is not fitted to data. The paper is from 2008 and predates modern computational modeling standards (e.g., Wilson & Collins, 2019).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_social_info_search
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- tax_domain_A_influence_transmission
- tax_mod_social_info_search
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_agent_based_evolutionary
- tax_rr_model_family = agent_based_evolutionary
- tax_rr_param_social_weight
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = cultural_transmission
- tax_rr_topic_cultural_transmission
- tax_rr_topic_norm_conformity
- tax_topic_cultural_transmission
- tax_topic_norm_conformity
