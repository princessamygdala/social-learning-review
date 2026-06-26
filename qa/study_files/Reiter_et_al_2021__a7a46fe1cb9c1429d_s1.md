# Reiter et al. (2021)

- **study_id:** `a7a46fe1cb9c1429d_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Reiter, A. M. F., Moutoussis, M., Vanes, L., Kievit, R., Bullmore, E. T., Goodyer, I. M., Fonagy, P., Jones, P. B., NSPN Consortium, & Dolan, R. J. (2021). Preference uncertainty accounts for developmental effects on susceptibility to peer influence in adolescence. *Nature Communications*, 12, 3823. https://doi.org/10.1038/s41467-021-23671-2
- **citation_short:** Reiter et al. (2021)
- **doi:** 10.1038/s41467-021-23671-2
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** UCLCentreforComputationalPsychiatryandAgeingResearch,UniversityCollegeLondon,London,UK; DepartmentofClinical,EducationalandHealthPsychology,UniversityCollegeLondon,London,UK; sectionaleffectofmoresusceptibilitytopeerinfluenceinalargedatasetofadolescents14to; DepartmentofChildandAdolescentPsychiatry,PsychosomaticsandPsychotherapy,University; DepartmentofPsychiatry,UniversityofCambridge; ether mPFC myelin is related to develop-; sectional and longitudinal developmental; sectionally, but also longitudinally; emails: a.reiter@ucl.ac.uk
- **code_url:** https://osf.io/cf59r/

## Computational level
- **study_focus:** Social influence learning; how preference uncertainty drives susceptibility to peer influence in adolescent delay discounting
- **study_focus_short:** Social influence learning
- **learning_mode_description:** - Learning mode: Learning from another person's delay discounting preferences to update one's own preferences   - Learning from:     - Source type (social): other (experimental partner/computerised agent)     - Source content (social): action/policy (other's delay discounting choices and preferences)   - Learning about:     - Target type (non-social): self     - Target content (non-social): state (own preference/taste — delay discounting rate)
- **task_description:** Participants completed a social delay discounting task in three phases: (1) they made 60 delay discounting choices expressing their own temporal preferences; (2) they made choices on behalf of another person to learn that person's discounting preferences with feedback; (3) they repeated phase 1 self-choices, allowing measurement of preference shift toward the other's discounting rate.
- **task_paradigm:** Delay discounting / intertemporal
- **players:** Single agent (participant), dyadic (computerised partner with manipulated delay discounting preferences)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Monetary choice options (smaller-sooner vs. larger-later amounts), feedback on other's preferences (correct/incorrect)
- **method:** behavioural
- **method_full:** behavioural, structural MRI (magnetisation transfer mapping)
- **main_result:** - Social susceptibility (preference shift) decreased with age cross-sectionally (r = −0.10, df = 782, t = −2.94, p = 0.003) - Social susceptibility decreased longitudinally within-person over ~1.5-year follow-up (F(1,566.64) = 5.11, unstandardised estimate = 0.17, p = 0.02) - Social susceptibility at baseline predicted improvement in peer relations at follow-up (z = 2.12, standardised β = 0.08, p = 0.03), driven by younger (<18) subsample (z = 2.17, standardised β = 0.20, p = 0.03) - Preference uncertainty negatively correlated with age at baseline (r = −0.15, t = −4.36, df = 780, p < 0.001) - Preference uncertainty decreased longitudinally (F(1,564.86) = 5.69, p = 0.02) with age × time interaction (F(1,565.41) = 9.29, p = 0.002) - Full mediation: age effect on social susceptibility mediated by preference uncertainty (proportion of mediation z = 3.03, standardised β = 0.723, p = 0.002) - Longitudinal change in preference uncertainty covaried with change in social susceptibility (z = 3.82, standardised β = 0.205, p < 0.001) - Baseline mPFC myelin (MT) predicted longitudinal decrease in preference uncertainty (z = −2.14, standardised β = −0.13, p = 0.03)
- **effect_size:** - Cross-sectional age–susceptibility: r = −0.10 - Cross-sectional age–preference uncertainty: r = −0.15 - Mediation proportion: standardised β = 0.723 - Longitudinal change covariation (preference uncertainty × social susceptibility): standardised β = 0.205 - mPFC myelin → preference uncertainty change: standardised β = −0.13 - Social susceptibility → peer relations change (younger group): standardised β = 0.20
- **learning_from:** Other (experimental partner); other's delay discounting choice preferences
- **learning_about:** Self; own delay discounting preference (own preference uncertainty)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Bayesian belief updating model of preference uncertainty (5 parameters: log k, σ² [preference uncertainty], σ²_other [relevance of other], noise parameters). Previously validated in Moutoussis et al. (2016).
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [{"name": "Bayesian preference uncertainty model", "family": "Bayesian belief updating", "n_params": 5, "metric": "model selection in prior validation study (Moutoussis et al., 2016)"}] Note: The present paper does not perform new model comparison; the model was validated and selected in a prior study (Moutoussis et al., 2016) on 738 of the 784 baseline participants. The prior study tested this model against alternatives including softmax decision noise.
- **model_mb_mf:** Bayesian
- **model_params:** - log k: log hyperbolic discounting parameter (discount rate); mean fitted values reported as distributions, not single values - σ² (preference uncertainty) [S]: width of belief distribution over own discounting preference — captures how uncertain a person is about their own preferences prior to social exposure; key developmental parameter - σ²_other (relevance of the other) [S]: width of reference distribution assumed shared by subject and social partner — captures how relevant the other's preferences are - Additional noise/choice parameters (exact specification deferred to Moutoussis et al., 2016)
- **social_param:** σ² (preference uncertainty) [S] — degree of uncertainty about one's own delay discounting preferences; higher uncertainty leads to greater adoption of others' preferences (informational conformity mechanism). σ²_other (relevance of the other) [S] — captures the assumed similarity between subject and social partner, determining how much the other's preferences influence belief updating.
- **social_param_name:** σ²
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Model selection performed in prior validation study (Moutoussis et al., 2016); deviance-based fit measure used in current study as covariate. No new model comparison in this paper.
- **how_model_fit:** individual-level-fit (sampling-based Bayesian fitting, as noted by deviance measure "appropriate for sampling-method based fits")
- **data_type_fit_to:** choice behavior (delay discounting choices across phases 1–3)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (structural MRI — quantitative magnetisation transfer mapping for myelin estimation; no functional imaging)
- **contrast:** N/A (no functional neuroimaging contrasts; structural ROI analysis only)
- **key_regions:** Baseline mPFC myelin marker (magnetisation transfer saturation) predicted longitudinal decrease in preference uncertainty (standardised β = −0.13, p = 0.03). Control region (angular gyrus) showed no significant brain-behaviour coupling.
- **key_regions_abbrev:** mPFC, AI
- **coordinates_peak:** unavailable — not in main text or supplement. Anatomically defined ROI masks used (Harvard-Oxford atlas, mPFC thresholded at 30%; angular gyrus control ROI).
- **analysis_type:** ROI  ---  ### QUALITY
- **analysis_type_clean:** ROI
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 784 (401 female) at baseline, ages 14.10–24.99 (mean = 19.05, sd = 2.96); N = 569 (284 female) at ~1.5-year follow-up; N = 55 retest subsample (3 time points including 6-month short follow-up); N = 186 (91 female) with structural MRI at both time points. N = 738 of baseline previously used in Moutoussis et al. (2016) model validation.
- **population_category:** adolescents
- **population_age_range:** 
- **ecological_validity:** Social influence was implemented via a computerised agent rather than real social interaction partner; no non-social control condition in the present study (though prior study using same task included control experiments ruling out stimulus-based reinforcement). The partner was a computerised agent, which limits ecological validity but is arguably relevant given digital social influence on adolescents.
- **eligibility_flag:** 
- **concerns:** (1) No new model comparison performed — model was validated in prior study on largely overlapping sample; (2) Model fit correlates with age, meaning younger participants are fit less well; (3) Social partner is a computerised agent, not a real person; (4) No non-social control condition in this study (relies on control conditions from Garvert et al., 2015); (5) 738/784 baseline participants overlap with Moutoussis et al. (2016) — potential partial duplicate dataset concern; (6) No functional neuroimaging — structural MRI (myelin mapping) only; (7) Effect sizes are small throughout.
- **limitations_reported:** Further limitations of this study relate to ecological validity, in that a social influence was implemented by a computerised agent rather than a real social interaction partner"; "The study did not include a non-social control condition"; "a limitation is that model fit correlated with age, such that younger participants were fit less well by our computational model"; "Varying goodness-of-fit of a specific model is a challenge for developmental modelling studies and may be indicative of either varying stochasticity or different cognitive processes underlying task behaviour at different ages"; "the effect size of the developmental effects on susceptibility to social influence, as well as their association with peer relations or neuro-developmental markers, was lower than might be expected from theoretical accounts and lower sample size studies"; "our sample did not include very young adolescents for whom strong susceptibility effects have been reported previously
- **limitations_categorized:** limited ecological validity; no non-social control condition; age-dependent model fit; small effect sizes; limited age range; task simplicity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - all_models_tested: MEDIUM — no new model comparison in this paper; relies on Moutoussis et al. (2016) validation - model_params: MEDIUM — full parameter specification deferred to Moutoussis et al. (2016); 5 parameters mentioned but not all named explicitly in this paper - coordinates_peak: LOW — no peak coordinates reported; anatomically defined ROI masks used - wc_guidelines rules 2, 3, 7: MEDIUM — model comparison and simulation were performed in prior study, not this one
- **cannot_find:** - Exact formulas for all 5 model parameters (deferred to Moutoussis et al., 2016) - Peak MNI coordinates (anatomical ROI masks used instead) - Exact mean fitted parameter values for model parameters
- **other_notes:** This paper primarily extends a previously validated computational model (Moutoussis et al., 2016) to a developmental/longitudinal context. The computational model itself was not developed or compared in this paper. 738/784 baseline participants overlap with the model validation paper. The structural MRI component uses magnetisation transfer (MT) saturation as a myelin proxy, not functional neuroimaging — hence no BOLD contrasts or functional coordinates. The social partner is explicitly a computerised agent with manipulated delay discounting preferences; a prior study (Garvert et al., 2015) showed that the "active ingredient" is mentalizing about the other agent rather than the agent's physical nature.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_instructed
- tax_model_bayesian
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = norm_conformity
- tax_rr_topic_norm_conformity
- tax_topic_norm_conformity
