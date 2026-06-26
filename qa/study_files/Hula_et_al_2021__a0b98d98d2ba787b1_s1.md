# Hula et al. (2021)

- **study_id:** `a0b98d98d2ba787b1_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hula, A., Moutoussis, M., Will, G.-J., Kokorikou, D., Reiter, A. M., Ziegler, G., NSPN Consortium, Bullmore, E., Jones, P. B., Goodyer, I., Fonagy, P., Montague, P. R., & Dolan, R. J. (2021). Multi-round trust game quantifies inter-individual differences in social exchange from adolescence to adulthood. *Computational Psychiatry*, *5*(1), 102–118. https://doi.org/10.5334/cpsy.65
- **citation_short:** Hula et al. (2021)
- **doi:** 10.5334/cpsy.65
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** laboration forms a spring-board for longer-term relationships (see Crone & Dahl,; mits a fine-grained study of the ability to establish and maintain cooperation; sectional sample (n = 784) to study how the challenges of Andreas; mith, 2003, King-Casas et al, 2005) (called; ether they will reciprocate; emails: Andreas.Hula@ait.ac.at
- **code_url:** 

## Computational level
- **study_focus:** Trust learning; developmental changes in social exchange risk aversion, inequality aversion, and theory of mind during adolescence to young adulthood
- **study_focus_short:** Trust learning
- **learning_mode_description:** - Learning mode: Learning from a partner's reciprocation behavior about the partner's social characteristics (inequality aversion, irritability) to guide investment decisions   - Learning from:     - Source type (social): other (anonymous trustee partner)     - Source content (social): action/policy (trustee's repayment decisions)   - Learning about:     - Target type (social): other (anonymous trustee partner)     - Target content (social): state (mental state; inequality aversion, irritability traits)
- **task_description:** Participants played the role of investor in a 10-round multi-round trust game with an anonymous partner (actually a computer algorithm emulating healthy adult trustees). Each round, the investor received 20 monetary units, chose how much to invest (investment tripled by experimenter), and the trustee decided how much to return.
- **task_paradigm:** Trust game
- **players:** Single agent (participant as investor), dyadic (anonymous trustee partner; computer algorithm)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Monetary units (play-coins), numerical investment/return decisions, binary feedback on trustee repayment
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Model parameters explained 69% of variance in total investment (adjusted R² = 0.69)   - Risk aversion alone explained 49% of investment variance (adjusted R² = 0.49)   - Significant negative effect of age on risk aversion (b = −0.3, p < 10⁻⁵)   - Significant negative effect of IQ on risk aversion (b = −0.43, p < 10⁻¹⁰)   - Significant effect of sex on risk aversion (b = 0.82, p < 10⁻¹⁰; females more risk averse)   - Sex difference in total earnings (d = 0.44; males earned more)   - Significant effect of SES on risk aversion (b = 0.19, p = 0.04; higher deprivation = more risk averse)   - Significant quadratic SES effect on risk aversion (b = −0.12, p = 0.01)   - Significant effect of sex on inequality aversion (b = 0.47, p = 0.001; females more inequality averse)   - Marginally significant effect of age on inequality aversion (b = 0.14, p = 0.06)   - Significant effect of IQ on inverse temperature (b = 0.024, p = 0.03)
- **effect_size:** R² = 0.69 (full model on investment); R² = 0.49 (risk aversion alone); d = 0.44 (sex difference in earnings); see regression coefficients above
- **learning_from:** Other (anonymous trustee partner); trustee's repayment actions across rounds
- **learning_about:** Other (anonymous trustee partner); partner's inequality aversion and irritability traits  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** I-POMDP (7 params: α inequality aversion, ω risk aversion, k ToM level, P planning horizon, ζ irritability, q(ζ) irritation awareness, β inverse temperature)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [{"name": "I-POMDP (full 7-parameter model)", "family": "I-POMDP", "n_params": 7, "metric": "NLL + AIC stepwise selection for regression models"}] Note: Only one computational model of behavior was tested (the I-POMDP). Multiple regression models were compared for demographic predictors using AIC stepwise selection, but these are statistical models, not competing computational models of the task.
- **model_mb_mf:** MB (model-based; the I-POMDP involves forward planning and mental models of partner)
- **model_params:** - α (inequality aversion/guilt) [S]: sensitivity to unfair outcomes against the other player; values {0, 0.4, 1}; inferred interactively during task - ω (risk aversion): multiplier for value of money kept over money returned by partner; values {0.4, 0.6, 0.8, 1.0, 1.2, 1.4, 1.6, 1.8} - k (ToM level) [S]: number of recursive mentalizing steps about the other player; values {0, 1, 2, 3, 4} - P (planning horizon): number of steps planned ahead; values {1, 2, 3, 4} - ζ (irritability) [S]: shift towards punishment behavior when partner actions fall below expectations; values {0, 0.25, 0.5, 0.75, 1}; inferred interactively during task - q(ζ) (irritation awareness) [S]: awareness of partner irritability; values {0, 1, 2, 3, 4} - β (inverse temperature): choice stochasticity; values {1/4, 1/3, 1/2, 1}  Mean fitted values not reported in the paper (only distributions shown in figures).
- **social_param:** - α (inequality aversion/guilt): sensitivity to inequitable outcomes between self and partner - k (ToM level): recursive mentalizing depth about partner's beliefs - ζ (irritability): propensity for punishment behavior following unsatisfactory partner actions - q(ζ) (irritation awareness): prior belief about partner's irritability
- **social_param_name:** α
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Maximum likelihood estimation (exhaustive grid search over discrete parameter space); NLL = 8.13 average per subject. AIC used for stepwise regression model selection on demographic predictors.
- **how_model_fit:** individual-level-fit (exhaustive search over all parameter combinations per subject, selecting parameter vector with lowest NLL)
- **data_type_fit_to:** choice behavior (investment amounts across 10 rounds)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study only)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 784 (403 female, 381 male); age range 14–25, mean age 19.05, SD = 2.96; from NSPN cohort (London and Cambridge)
- **population_category:** healthy adults
- **population_age_range:** 14–25
- **ecological_validity:** The trust game uses monetary incentives and anonymous interaction which captures economic trust but lacks the richness of real social relationships; the trustee was a computer algorithm (not a real person), limiting ecological validity of the social interaction; cross-sectional design limits developmental inference.
- **eligibility_flag:** 
- **concerns:** The trustee was a computer algorithm emulating healthy adult behavior (not a real human partner), though participants believed they were playing with a peer — this limits the genuinely interactive nature of the social exchange. Only one game played per participant limits parameter recovery reliability. All parameters discretized on a grid due to computational constraints rather than estimated continuously. No competing computational models were tested (only the I-POMDP). Cross-sectional design precludes within-subject developmental claims.
- **limitations_reported:** Overall, the reliability, predictive and construct validity of MRT tasks remain to be better established"; "the model parameters needed to be discrete because of computational limitations"; "parameter recoverability is always subject to limitations, in particular in a task where partner actions strongly influence the dynamics of the interaction"; "only 1 dyad is available per subject"; "The cross-sectional nature of the present sample limited us to statements about population distributions rather than within-subject, developmental effects"; "the validity of 'risk aversion' in socio-economic exchanges needs to be characterised both in terms of test-retest but also construct validity
- **limitations_categorized:** limited construct validity; parameter discretization constraints; limited parameter recovery; single observation per participant; cross-sectional design limits developmental inference; no test-retest reliability
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Partial
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 6.0
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `all_models_tested`: MEDIUM — only one computational model described; multiple regression models were used for demographic analysis but these are statistical not computational models of the task - `model_params` (mean fitted values): LOW — distribution figures shown but no mean fitted values reported in text - `wc_guidelines` rule 5 (parameter recovery): MEDIUM — recovery shown only for risk aversion, not other parameters; scored as Partial - `wc_guidelines` rule 8 (model validation): MEDIUM — variance explained reported but no formal posterior predictive check; scored as Partial
- **cannot_find:** - Mean fitted parameter values (only distributions shown in figures, no numerical summaries) - Supplement (no supplement found for this paper)
- **other_notes:** This paper is from the NSPN consortium. The I-POMDP model was developed in prior work (Hula et al., 2015, 2018) and applied here to a large developmental sample. The key novelty is the large-scale application to study demographic correlates (age, sex, IQ, SES) of computationally derived social exchange parameters. The "trustee" is a computer algorithm matching behavior from a database of recorded interactions, not a real partner. No supplement was found for this paper.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = structural
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = trust
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_trust
- tax_topic_mentalizing
- tax_topic_trust
