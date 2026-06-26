# Unruh-Pinheiro et al. (2020)

- **study_id:** `a6b9bc33a9a00f6e5_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Unruh-Pinheiro, A., Hill, M. R., Weber, B., Boström, J., Elger, C. E., & Mormann, F. (2020). Single-neuron correlates of decision confidence in the human medial temporal lobe. *Current Biology*, *30*(23), 4722–4732. https://doi.org/10.1016/j.cub.2020.09.021
- **citation_short:** Unruh-Pinheiro et al. (2020)
- **doi:** 10.1016/j.cub.2020.09.021
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofNeurosurgery,UniversityofBonnMedicalCenter,Venusberg-Campus1,53127Bonn,Germany; DepartmentofEpileptology,UniversityofBonnMedicalCenter,Venusberg-Campus1,53127Bonn,Germany; CenterforEconomicsandNeuroscience,UniversityofBonn,Venusberg-Campus1,53127Bonn,Germany; lableoptions,ontoacommonscalethatallowscomparing differenceinvalueorthechosenvalue; etheamygdalahas ous study has reported confidence correlates in the human; ether graded measure of belief that can be explicitly reported in an; emails: florian.mormann@ukbonn.de
- **code_url:** https://github.com/jniediek/combinato/

## Computational level
- **study_focus:** Decision confidence metacognition in value-based choice (non-social). Confidence: HIGH.
- **study_focus_short:** Decision confidence metacognition in value-based choice (non-social) · Confidence: HIGH
- **learning_mode_description:** - Learning mode: No social learning present. This is a value-based decision-making task with metacognitive confidence ratings.   - Learning from:     - Source type (non-social): self     - Source content (non-social): stimulus (food item pictures)   - Learning about:     - Target type (non-social): world (food item values)     - Target content (non-social): stimulus value / decision confidence  Confidence: MEDIUM — there is no clear "learning over time" in this study; participants make decisions based on existing preferences, not via trial-by-trial updating.
- **task_description:** Participants (epilepsy patients with implanted depth electrodes) performed a valuation task rating 20 food items on a scale from −100 to +100, followed by a 2AFC task where they chose their preferred item from sequentially presented pairs and rated their decision confidence. After a satiation break (consuming preferred item), both tasks were repeated. Confidence: HIGH.
- **task_paradigm:** Decision-confidence task
- **players:** Single agent (participant), no social interaction. Confidence: HIGH.
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** High-resolution pictures of 20 junk food products (10 salty, 10 sweet), Likert scale ratings. Confidence: HIGH.
- **method:** other
- **method_full:** Single-unit electrophysiology (intracranial microelectrode recordings in MTL). Confidence: HIGH.
- **main_result:** - Main Results:   - Two independent subpopulations of MTL neurons persistently correlated with decision confidence (11.81%, p < 10⁻¹⁴) and reaction time (13.01%, p < 10⁻¹⁵)   - Change in confidence between experimental sets accompanied by correlated change in neural activity (Wilcoxon signed-rank test, sustained significance)   - Confidence and RT better explained persistent neural activity than all 122 alternative variables tested (post hoc binomial tests, all p < 0.05)   - Transient stimulus-locked activity correlated with value ratings (9.88%, p < 10⁻⁸) but value was no better than nutritional features (taste, sugar, salt, fiber — all p > 0.05 in post hoc comparison)   - No evidence that change in subjective value between sets was accompanied by correlated change in neural activity   - Behavioral model: unsigned difference in value predicted confidence (β = 0.46, t₄₅₅₆ = 9.73, p < 10⁻²¹); RT negatively predicted confidence (β = −0.07, t₄₅₅₆ = −3.53, p < 10⁻³); summed value predicted confidence (β = 0.33, t₄₅₅₆ = 4.93, p < 10⁻⁶)
- **effect_size:** β = 0.46 (unsigned |DV| → confidence); β = −0.07 (RT → confidence); β = 0.33 (summed value → confidence); β = 5.64 (DV → choice, logistic); β = 2.87 (DV × confidence interaction → choice); proportion of neurons: 11.81% confidence, 13.01% RT. Confidence: HIGH.
- **learning_from:** Self; own food item preferences and decision outcomes. Confidence: HIGH.
- **learning_about:** World; food item values and decision confidence. Confidence: HIGH.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Mixed-effects linear model: Conf ~ Normal(β₀ + β₁[|DV|] + β₂[RT] + β₃[DV] + ε) — Model 5 from Table S1 (best BIC for confidence prediction). No trial-by-trial learning model was fitted. Confidence: HIGH.
- **model_family:** Descriptive / regression
- **model_class:** Other
- **all_models_tested:** [   {"name": "Model 1: Conf ~ |DV|", "family": "linear mixed-effects", "n_params": "2 fixed", "metric": "BIC"},   {"name": "Model 2: Conf ~ |DV| + RT", "family": "linear mixed-effects", "n_params": "3 fixed", "metric": "BIC"},   {"name": "Model 3: Conf ~ |DV| + DV", "family": "linear mixed-effects", "n_params": "3 fixed", "metric": "BIC"},   {"name": "Model 4: Conf ~ |DV| + RT + DV", "family": "linear mixed-effects", "n_params": "4 fixed", "metric": "BIC"},   {"name": "Model 5: Choice ~ DV (logistic)", "family": "logistic mixed-effects", "n_params": "2 fixed", "metric": "BIC"},   {"name": "Model 6: Choice ~ DV + Conf (logistic)", "family": "logistic mixed-effects", "n_params": "3 fixed", "metric": "BIC"},   {"name": "Model 7: Choice ~ DV + Conf + SV (logistic)", "family": "logistic mixed-effects", "n_params": "4 fixed", "metric": "BIC"},   {"name": "Model 8: Choice ~ DV + Conf + SV + DV×Conf (logistic)", "family": "logistic mixed-effects", "n_params": "5 fixed", "metric": "BIC"},   {"name": "Model 9: Choice ~ DV + Conf + SV + DV×Conf + DV×SV (logistic)", "family": "logistic mixed-effects", "n_params": "6 fixed", "metric": "BIC"},   {"name": "Model 10: RT ~ UV", "family": "linear mixed-effects", "n_params": "2 fixed", "metric": "BIC"},   {"name": "Model 11: RT ~ UV + Val + UV×Val", "family": "linear mixed-effects", "n_params": "4 fixed", "metric": "BIC"} ]  Confidence: HIGH.
- **model_mb_mf:** N/A (not RL). Confidence: HIGH.
- **model_params:** β₀ (intercept), β₁ (unsigned difference in value), β₂ (RT), β₃ (summed value) for confidence model. No social parameters. Fitted values: β₁ = 0.46, β₂ = −0.07, β₃ = 0.33. Confidence: HIGH.
- **social_param:** None — no social parameters. Confidence: HIGH.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion). Confidence: HIGH.
- **how_model_fit:** group-level-fit (mixed-effects models with MLE). Confidence: HIGH.
- **data_type_fit_to:** choice behavior, confidence ratings, reaction times. Confidence: HIGH.  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (single-unit electrophysiology, not fMRI). Confidence: HIGH.
- **contrast:** - Sliding-window Spearman's rank correlation of firing rate with confidence (persistent activity, 11.81% of neurons) - Sliding-window Spearman's rank correlation of firing rate with RT (persistent activity, 13.01% of neurons) - Transient stimulus-locked correlation with value ratings (9.88%) - Actual vs swapped correlation analysis (change between experimental sets) - 122-variable quantitative comparison  Confidence: HIGH.
- **key_regions:** Decision confidence correlated with persistent firing in amygdala (11.32%), hippocampus (11.15%), entorhinal cortex (15.13%), and parahippocampal cortex (9.26%). RT correlated in all four regions (A: 12.08%, H: 13.44%, EC: 13.82%, PHC: 11.11%). Transient value correlates in amygdala and hippocampus. Confidence: HIGH.
- **key_regions_abbrev:** amygdala, hippocampus
- **coordinates_peak:** unavailable — not applicable; single-unit electrophysiology study with microelectrode recordings; no MNI/Talairach coordinates reported (electrode locations defined by region — amygdala, hippocampus, entorhinal cortex, parahippocampal cortex — not by standardized coordinates). Confidence: HIGH.
- **analysis_type:** N/A (single-unit electrophysiology, not neuroimaging). Confidence: HIGH.  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 12 (6 female, 6 male; all right-handed; mean age 40 ± 13.62 SD, range 20–62); 830 units recorded (480 single units, 350 multi-units) across amygdala (265), hippocampus (305), entorhinal cortex (152), parahippocampal cortex (108). Confidence: HIGH.
- **population_category:** healthy adults
- **population_age_range:** 20–62
- **ecological_validity:** Limited — patients with pharmacologically intractable temporal lobe epilepsy choosing between junk food pictures in a hospital setting. Not naturalistic decision-making. Satiation manipulation provides some ecological validity for preference dynamics. Confidence: HIGH.
- **eligibility_flag:** Ineligible — no computational model of learning; no social context; decision-making/metacognition study with descriptive statistical models only. Does not meet criteria for: (1) computational modeling, (2) social context, (3) learning over time.
- **concerns:** - No computational model of learning is used — only descriptive mixed-effects regressions and sliding-window correlations - No social context whatsoever — purely individual value-based decision-making - No trial-by-trial learning process modeled - Epilepsy patient sample limits generalizability - Small sample (N = 12), though typical for intracranial recordings - One subject declined to eat during satiation break
- **limitations_reported:** A limitation of this study is that the subjective values were not as strongly perturbed between experimental sets as other variables, which limits the sensitivity of our analysis"; "A limitation of our statistical approach is that it neglects the strength of the association between cognitive variables and the activity of single neurons"; "there could be small subpopulations of neurons whose activity was strongly correlated with other cognitive variables but whose proportion of neurons did not reach significance after correction for multiple comparisons"; "we recorded only a small fraction of MTL units, neurons in other subregions of the amygdala and the human MTL could reveal value or unsigned-value correlates
- **limitations_categorized:** limited sensitivity of satiation manipulation; statistical approach limitations (proportion-based, not effect-size-based); small recording sample (fraction of MTL); limited generalizability (epilepsy patients)
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `eligibility_flag`: LOW confidence that this paper belongs in a social learning review — it is a non-social decision-making/metacognition study with no computational learning model - `learning_mode`: MEDIUM — no clear learning-over-time process; categorization is approximate - `model_family` / `model_class`: HIGH — accurately described as descriptive regression, but this is NOT a computational model of learning
- **cannot_find:** - No social learning component - No computational learning model (RL, Bayesian updating, etc.) - No MNI coordinates (single-unit study)
- **other_notes:** This paper investigates single-neuron correlates of decision confidence and reaction time in the human medial temporal lobe during a food-preference decision-making task. It is a neuroscience/metacognition study, not a social learning study. The paper uses only descriptive statistical models (mixed-effects linear and logistic regressions) to characterize behavioral data, and sliding-window correlations for neural data. No trial-by-trial computational model of learning is fitted. The paper has no social component whatsoever. It should be flagged as ineligible for the systematic review on all three criteria: no computational modeling of learning, no social context, and no learning over time.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = general
- spec_locus = source+target
- spec_neural = shared
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_param_social_bonus
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_drift_diffusion
- tax_rr_model_family = drift_diffusion
- tax_rr_param_precision
- tax_rr_primary_topic = self_belief_confidence
- tax_rr_topic_self_belief_confidence
- tax_topic_self_belief_confidence
