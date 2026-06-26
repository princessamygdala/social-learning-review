# Reiter et al. (2019)

- **study_id:** `a0d3ac52f7335afbc_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Reiter, A. M. F., Suzuki, S., O'Doherty, J. P., Li, S.-C., & Eppinger, B. (2019). Risk contagion by peers affects learning and decision-making in adolescents. *Journal of Experimental Psychology: General*, *148*(9), 1494–1504. http://dx.doi.org/10.1037/xge0000512
- **citation_short:** Reiter et al. (2019)
- **doi:** 10.1037/xge0000512
- **publication_type:** peer-reviewed journal
- **year:** 2019.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** InstituteofTechnology;Shu-ChenLi,LifespanDevelopmentalNeuroscience,; Faculty of fromtheGermanResearchFoundation(DFG;SFB940/2B7)awarded; University,Montreal,Quebec,CanadaandTechnischeUniversitätDresden; FacultyofPsychology,TechnischeUniversitätDresden;BenEppinger,De-; laboratorysetting,participantsareoftentestedindividually,andit; UniversitätDresdenandMax-Planck-Institutefor TohokuUniversity; UniversitätDresden,andDepartmentofNeurology, toBenEppinger; InstituteforHumanCognitiveandBrainSciences,Leipzig,Ger- C; emails: a.reiter@ucl.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Social influence learning / risk contagion — how observing peers' risky decision-making behavior affects one's own risk preferences and learning about others' preferences, with developmental comparison (adolescents vs. adults).
- **study_focus_short:** Social influence learning / risk contagion
- **learning_mode_description:** - Learning mode: Learning from observation of others' risky choice behavior about one's own risk preferences and about others' risk preferences   - Learning from:     - Source type (social): other (peer or adult confederate/observee)     - Source content (social): action/policy (observed risk-taking choices — accept or reject gambles)   - Learning about:     - Target type (social): other (observee's risk preference) **and** self (own risk preference shift)       - If joint: not joint     - Target content (social): state (mental state; risk preference of other) **and** (non-social): action/policy (own gambling decisions/risk preference)
- **task_description:** Participants chose between a safe bet (€5) and a risky gamble with varying probabilities and magnitudes across four sessions. Between self-choice sessions, they observed a confederate (presented as a peer teenager or adult) making risk-seeking or risk-averse choices on the same gamble task, and predicted the confederate's future choices.
- **task_paradigm:** Risky decision-making
- **players:** Single agent (participant), multi-target (2 confederate observees per testing day — 1 risk-averse, 1 risk-seeking; tested across 2 days with teenage and adult observees)
- **n_players:** multi-target (3+)
- **partner_type:** confederate
- **stimuli:** Pie chart probability displays, monetary gambles (€5 safe option vs. risky gamble), photos of confederates (peers or adults)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Significant risk contagion effect across both age groups (one-sample t test: t = 8.70, p < .001)   - Three-way interaction of own age group × observee's age group × observee's risk preference on risk contagion (F = 5.82, p = .017)   - Adolescents showed significantly more risk contagion after observing risk-seeking teen vs. risk-seeking adult (t = 2.20, p = .033)   - Peer effect stronger in risk-seeking than risk-averse observee condition (t = 2.58, p = .011)   - Teens vs. adults showed more risk contagion after observing risk-seeking teens (t = 2.83, p = .006)   - Adolescents slower RTs after observing peers vs. adults — interaction of own age × observee age on RT (F = 4.10, p = .045)   - Adolescents learned to predict peer's choices more effectively than adult's choices (interaction of block × own age × observee age on prediction accuracy: χ² = 9.47, p = .009)   - Prediction accuracy positively associated with risk contagion when teens observed teens (χ² = 6.05, p = .01; three-way interaction χ² = 18.00, p < .001)   - Peer-biased risk contagion positively correlated with social integration in adolescents (r = .44, p = .012)   - No association of peer-biased risk contagion with impulsivity (r = −.052, p = .76)
- **effect_size:** - Main Results:   - Significant risk contagion effect across both age groups (one-sample t test: t = 8.70, p < .001)   - Three-way interaction of own age group × observee's age group × observee's risk preference on risk contagion (F = 5.82, p = .017)   - Adolescents showed significantly more risk contagion after observing risk-seeking teen vs. risk-seeking adult (t = 2.20, p = .033)   - Peer effect stronger in risk-seeking than risk-averse observee condition (t = 2.58, p = .011)   - Teens vs. adults showed more risk contagion after observing risk-seeking teens (t = 2.83, p = .006)   - Adolescents slower RTs after observing peers vs. adults — interaction of own age × observee age on RT (F = 4.10, p = .045)   - Adolescents learned to predict peer's choices more effectively than adult's choices (interaction of block × own age × observee age on prediction accuracy: χ² = 9.47, p = .009)   - Prediction accuracy positively associated with risk contagion when teens observed teens (χ² = 6.05, p = .01; three-way interaction χ² = 18.00, p < .001)   - Peer-biased risk contagion positively correlated with social integration in adolescents (r = .44, p = .012)   - No association of peer-biased risk contagion with impulsivity (r = −.052, p = .76)
- **learning_from:** Other (peer or adult confederate); observed risk-taking choices (accept/reject gambles)
- **learning_about:** Other's risk preference (prediction of observee's choices) and self (own risk preference shift via contagion)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Mean-variance utility function: U = EV + ρ × Var, where ρ is the risk preference parameter; choices modeled via softmax with inverse temperature β
- **model_family:** Utility / EV
- **model_class:** Utility maximization
- **all_models_tested:** [{"name": "Mean-variance utility model", "family": "Utility function", "n_params": 2, "metric": "MLE fitting (see supplement)"}]
- **model_mb_mf:** N/A (not RL)
- **model_params:** - ρ (rho): risk preference parameter — positive = risk-seeking, negative = risk-averse. Fitted per participant per session. Δρ used as model-based risk contagion measure. Mean Δρ across entire sample = 0.002 (SD = 0.007). - β: inverse temperature / softmax parameter (not explicitly reported in main text; described in supplement)
- **social_param:** Δρ — change in risk preference parameter (ρ) from pre- to post-observation of social partner; captures degree of risk contagion. Not a model parameter per se but derived from comparing fitted ρ values before and after social observation.
- **social_param_name:** Δρ
- **social_param_value:** 0.002
- **social_param_sd:** 0.007
- **social_param_range:** 
- **model_comparison_metric:** Not reported in main text — only one model family used. Supplement referenced for fitting details.
- **how_model_fit:** individual-level-fit (MLE fitting of utility function to each participant's choices per session)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 86 (n = 40 male adolescents, ages 12–15, median age 13; n = 46 male young adults, ages 20–33, median age 26). Originally recruited 52 adolescents and 51 adults; exclusions for no-shows, errors, psychiatric conditions, and missing data.
- **population_category:** mixed
- **population_age_range:** 12–15
- **ecological_validity:** Limited — confederates' choices were predetermined (not genuine social interaction); participants met confederates briefly but had no prior relationship; no real reciprocity or ongoing social interaction; monetary stakes may differ in subjective value across age groups; male-only sample limits generalizability.
- **eligibility_flag:** 
- **concerns:** - Male-only sample limits generalizability - Confederate choices were pre-programmed, not genuine — limits ecological validity of "social" manipulation - No direct social interaction or reciprocity between participant and observee - Supplement not accessible — model fitting details (exact softmax formulation, parameter bounds, simulation details) referenced in online supplemental materials but supplement file not available for verification - The "learning over time" component is somewhat limited — risk contagion is measured as a pre-post shift rather than trial-by-trial updating, though predict trial accuracy does show learning over blocks - Only one model tested — no formal model comparison
- **limitations_reported:** Restricted to male participants to avoid confounding influence of baseline gender differences in risk-taking from different pubertal trajectories; adolescent group consisted of early adolescents and young adults only — risk taking and peer effects change over adolescence and adulthood; peer-biased conformity might be specific to early adolescents; measures of risk preference depend on the specific task used; predict trials may have explicitly encouraged deliberation about observee's behavior, possibly provoking conformity with peers' choices; lack of reciprocity/social interaction; relatively high degree of social distance between peers who had not met before and had no reason to anticipate meeting again
- **limitations_categorized:** limited generalizability (male-only sample); limited age range; task specificity; demand characteristics (predict trials may encourage conformity); limited ecological validity (no real social interaction, no reciprocity); social distance between participants
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.5
- **wc_total:** 4.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM confidence — β parameter mentioned but exact values not reported in main text; details in inaccessible supplement - winning_model formula: MEDIUM confidence — utility function described conceptually (U = EV + ρ × Var) but exact softmax specification referenced to supplement - wc_guidelines rule 3: MEDIUM confidence — simulations for generating confederate choices described, but whether model was simulated before fitting to real data is unclear without supplement - social_param: MEDIUM confidence — Δρ is a derived measure, not a structural social parameter within the model itself
- **cannot_find:** - Exact softmax/choice function formula (referenced to supplement) - Exact fitted β values - Parameter bounds/priors for MLE fitting - Whether data/code are publicly shared - Supplement not available for verification of computational modeling details
- **other_notes:** - Supplement referenced (http://dx.doi.org/10.1037/xge0000512.supp) but not available as a file in the papers folder. Supplement reportedly contains: computational modeling details, model fitting procedure including a priori simulations, full statistical model outputs (Tables S-1 through S-7), and additional figures (Figures S-1 through S-3). - The model is primarily descriptive — a utility function fit to choices to derive a risk preference parameter, rather than a trial-by-trial learning model. The "learning" component is captured by the predict trials (accuracy improving over blocks) and by the pre-post shift in risk preference (contagion), not by a formal learning algorithm with prediction errors. - This paper is borderline for the "learning occurs over time" criterion: risk contagion is measured as a pre-post session shift, and predict trial accuracy improves over blocks, but there is no trial-by-trial computational learning model (e.g., no Rescorla-Wagner or Bayesian updating). The utility function is static within sessions. Flagging this for review but not excluding.
- **re_extract_flag:** false (full text read; supplement not accessible but main text extraction is complete)

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_vicarious_outcome
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_mod_action_observation
- tax_mod_vicarious_outcome
- tax_model_utility
- tax_param_social_bonus
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = utility_EV
- tax_rr_model_utility_EV
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_norm_conformity
- tax_rr_topic_social_info_use
- tax_topic_norm_conformity
- tax_topic_social_info_use
