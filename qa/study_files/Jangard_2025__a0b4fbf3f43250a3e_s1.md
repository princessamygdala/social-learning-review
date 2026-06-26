# Jangard (2025)

- **study_id:** `a0b4fbf3f43250a3e_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Jangard, S. (2025). *Prosocial learning and decision-making in alcohol use disorder* [Doctoral thesis, Karolinska Institutet]. https://doi.org/10.69622/28731839
- **citation_short:** Jangard (2025)
- **doi:** 10.69622/28731839
- **publication_type:** thesis
- **year:** 2025.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Department of Clinical Neuroscience Institute of Neuroscience and Physiology; Department of Clinical Neuroscience Department of Management and Engineering; Centre for Psychiatry Research Department of Psychiatry and Neurochemistry; ether, the findings of the current thesis suggest that social behaviors; Department of Clinical Neuroscience Department of Clinical Neuroscience; Department of Clinical Neuroscience Faculty of Social Sciences; Centre for Psychiatry Research Division of Economics; ether and losing them can lead to social isolation—a
- **code_url:** 

## Computational level
- **study_focus:** Prosocial preferences -- computational modeling of how individuals value outcomes for self vs. other in a social allocation task, and effects of oxytocin in AUD.
- **study_focus_short:** Prosocial preferences -- computational modeling of how individuals value
- **learning_mode_description:** - Learning mode: Evaluating/expressing preferences over joint monetary allocations between self and other   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (monetary allocation pairs for self and other)   - Learning about:     - Target type (social): other (anonymous partner) -- **joint** (self and other outcomes jointly evaluated)       - Target content (social): outcome (preference for prosocial vs. selfish allocations)
- **task_description:** In a double-blind, placebo-controlled within-subject trial, participants (98 AUD, 110 controls) evaluated 82 monetary allocation pairs involving points for self and another person on a 4-point preference scale, and played a 2-trial Dictator Game splitting 50 points with an anonymous partner, under oxytocin vs. placebo conditions.
- **task_paradigm:** Dictator game
- **players:** Single agent (participant), single anonymous partner (allegedly real)
- **n_players:** single agent (1)
- **partner_type:** human (live)
- **stimuli:** Monetary allocation pairs (points for self and other), Dictator Game point allocation
- **method:** pharmacological / behavioural
- **method_full:** Behavioural (lab, pharmacological RCT)
- **main_result:** - Cosine similarity model provided best fit to preference data - AUD group showed significantly lower social reference point (φ) than healthy controls, indicating lower prosocial orientation - φ did not moderate the effect of oxytocin on prosocial preferences - Oxytocin reduced prosocial decision-making in AUD (Dictator Game) but increased prosocial preferences (Evaluation Task) - Individualistic disposition moderated oxytocin effect on decision-making - Lower emotional empathy and lower attachment anxiety predicted stronger oxytocin effect on preferences (AUD only)
- **effect_size:** No specific effect sizes reported in thesis summary. Refers to manuscript for details.
- **learning_from:** Non-social; own evaluation of monetary allocation pairs
- **learning_about:** Social; preferences for prosocial vs. selfish monetary outcomes involving another person
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Cosine similarity model: PreferenceRating ~ a * cos(θ - φ), where φ is the social reference point (prosocial orientation) and a is the scaling parameter.
- **model_family:** Utility / EV
- **model_class:** Utility maximization
- **all_models_tested:** 1. {"name": "Linear Additive Model", "family": "Utility/value function", "n_params": 2, "metric": "not specified in thesis"} 2. {"name": "Inequality Aversion Model", "family": "Utility/value function", "n_params": 3, "metric": "not specified in thesis"} 3. {"name": "Cosine Similarity Model", "family": "Utility/value function", "n_params": 2, "metric": "not specified in thesis"}
- **model_mb_mf:** N/A (not RL)
- **model_params:** - a: scaling parameter (amplitude of preference). No mean fitted value reported. - φ [S]: social reference point -- angular parameter representing prosocial orientation in self-other outcome space. AUD < controls. No mean fitted values reported.
- **social_param:** φ (social reference point) -- represents the individual's prosocial orientation as an angle in self-other outcome space. Lower φ indicates more selfish orientation; higher φ indicates more prosocial orientation.
- **social_param_name:** φ
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Not explicitly stated in thesis (refers to manuscript). The thesis states "best fit" without specifying metric.
- **how_model_fit:** Individual-level-fit (inferred; φ compared between groups)
- **data_type_fit_to:** Self-report ratings (preference ratings on 4-point Likert scale)  #### Implementation Level

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging)  #### Quality
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=208 (98 AUD, 110 healthy controls); males only, ages 18-24
- **population_category:** mixed
- **population_age_range:** 18–24
- **ecological_validity:** Double-blind RCT with ecological strengths (pharmacological manipulation) but limited by anonymous partner framing, abstract monetary allocations, and male-only sample. Within-subject design (oxytocin vs. placebo) is a strength.
- **eligibility_flag:** Borderline -- this is a value/preference evaluation task with computational modeling, but learning does not occur over time in the traditional sense (no trial-by-trial updating). The models are static preference models, not learning models. Flag: "Borderline learning-vs-decision-making; static preference evaluation rather than learning over time.
- **concerns:** - Thesis summary only; detailed statistics and model comparison metrics only in unpublished manuscript - Model comparison metric not specified - No parameter recovery or model recovery reported - Males only -- limited generalizability - This is a thesis with Studies II and III drawing on overlapping (but not identical) participant pools from the same research group -- potential for non-independence - The cosine similarity model is a static preference model, not a learning model - Supplement not accessible
- **limitations_reported:** Oxytocin does not uniformly increase prosocial behavior in AUD"; "the results emphasize the importance of individual tailoring when considering oxytocin as an intervention"; "its effect on preferences may be beneficial for individuals with AUD, but actual decisions to help others may be reduced
- **limitations_categorized:** Limited generalizability (males only); task simplicity (abstract allocations); no learning over time; static preference model; individual differences moderate effects unpredictably
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - effect_size: LOW -- no effect sizes reported in thesis text; refers to published papers/manuscripts - model_comparison_metric (Study III): LOW -- not specified - how_model_fit (both): MEDIUM -- inferred from context, not explicitly stated - social_param (Study II): MEDIUM -- no explicit social parameter in winning model - winning model fitted values (both): LOW -- not reported in thesis - preregistered (both): LOW -- not stated
- **cannot_find:** - Exact model comparison statistics (BIC values, delta BIC) - Fitted parameter values (mean α, β for Study II; mean a, φ for Study III) - Effect sizes for group comparisons on model parameters - Model comparison metric for Study III - Whether studies were preregistered - Parameter recovery / model recovery results (likely not conducted)
- **other_notes:** 
- **re_extract_flag:** true -- This is a thesis summary only. Full extraction requires reading the individual published papers (Jangard et al., 2025, *Translational Psychiatry* for Study II; unpublished manuscript for Study III). The thesis does not contain complete statistical details, effect sizes, or model fitting specifics.

## Taxonomy / categorization (active codes only)
- pharma_oxytocin
- pop_addiction
- pop_healthy_adults
- rr_pharma_oxytocin
- rr_pop_addiction
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = target+context
- spec_source = social
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_utility
- tax_popclass_clinical
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = utility_EV
- tax_rr_model_utility_EV
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_social_nonsocial_comparison
- tax_topic_prosocial_altruism
