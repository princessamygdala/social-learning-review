# Hein et al. (2018)

- **study_id:** `af87f2f9e5c91cf2a_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hein, G., Engelmann, J. B., & Tobler, P. N. (2018). Pain relief provided by an outgroup member enhances analgesia. *Proceedings of the Royal Society B: Biological Sciences*, *285*(1887), 20180501. https://doi.org/10.1098/rspb.2018.0501
- **citation_short:** Hein et al. (2018)
- **doi:** 10.1098/rspb.2018.0501
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Center for Research in ExperimentalEconomics and PoliticalDecision Making(CREED), AmsterdamSchool; DepartmentofEconomics,LaboratoryforSocialandNeuralSystemsResearch,UniversityofZurich,Zurich8006,; DepartmentofPsychiatry, Psychosomatic andPsychotherapy,TranslationalSocial NeuroscienceUnit,; lable arrow) with painful stimulation to be delivered to the back of their left; UniversityofWurzburg, Wurzburg 97080,Germany; UniversityofAmsterdam, Amsterdam1001,; etherlands; emails: hein_g@ukw.de
- **code_url:** https://github.com/AffectiveNeuroeconomics/Social_

## Computational level
- **study_focus:** Social analgesia / pain relief learning modulated by intergroup context (ingroup vs. outgroup treatment provider)
- **study_focus_short:** Social analgesia / pain relief learning modulated by intergroup context
- **learning_mode_description:** - Learning mode: Learning from an ingroup or outgroup member's pain relief decisions about anticipated pain relief value   - Learning from:     - Source type (social): other (ingroup or outgroup treatment provider)     - Source content (non-social): outcome (pain relief vs. pain delivery)   - Learning about:     - Target type (non-social): world (pain anticipation / cue value)     - Target content (non-social): state (anticipated pain relief value associated with cue)
- **task_description:** Participants received painful electrical stimulation and learned to associate a cue with pain; during treatment, an ingroup or outgroup confederate ostensibly decided on 75% of trials to prevent pain, providing pain relief. Before and after treatment, participants received pain stimulation and rated pain while undergoing fMRI.
- **task_paradigm:** Empathy / pain task
- **players:** Single agent (participant), single target (1 confederate: ingroup or outgroup treatment provider); between-subjects design (N=18 ingroup treatment, N=18 outgroup treatment)
- **n_players:** network (5+)
- **partner_type:** confederate
- **stimuli:** Visual cues (green arrow, lightning bolt symbols), painful electrical shocks, emotion rating scales
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Pre-to-post pain rating reduction in outgroup treatment group (d = 0.74, p = 0.006) but not ingroup treatment group (d = 0.03, p = 0.87)   - Time × treatment group interaction on pain ratings (F(1,34) = 6.13, f = 0.425)   - Interaction of learning signal × social context on pre-post pain rating difference (F(1,30) = 7.421, f = 0.497)   - Right AI tracks learned pain relief anticipation across both groups (Z = 3.7, p(SV FWE) = 0.04, d(cluster) = 0.76, d(anatomical mask) = 0.318)   - Pre-vs-post reduction in bilateral AI pain response after outgroup treatment: left AI (Z = 3.68, p(SV FWE) = 0.05, d(cluster) = 0.8, d(anatomical mask) = 0.38)   - Learning signal predicts pre-post change in right AI pain-related activation (Z = 4.4, p(SV FWE) = 0.006, f²(cluster) = 0.36, f²(anatomical mask) = 0.42)   - Path analysis: indirect effect via learning significant (Path a standardized = −0.409, Path b standardized = 0.330); direct path not significant (standardized = −0.121)   - Moderated mediation by treatment group (χ²(1) = 4.56, p = 0.033, w = 0.356)   - Impression ratings: main effect of social context (F(1,34) = 10.85, f = 0.565); ingroup rated more favorably
- **effect_size:** - Main Results:   - Pre-to-post pain rating reduction in outgroup treatment group (d = 0.74, p = 0.006) but not ingroup treatment group (d = 0.03, p = 0.87)   - Time × treatment group interaction on pain ratings (F(1,34) = 6.13, f = 0.425)   - Interaction of learning signal × social context on pre-post pain rating difference (F(1,30) = 7.421, f = 0.497)   - Right AI tracks learned pain relief anticipation across both groups (Z = 3.7, p(SV FWE) = 0.04, d(cluster) = 0.76, d(anatomical mask) = 0.318)   - Pre-vs-post reduction in bilateral AI pain response after outgroup treatment: left AI (Z = 3.68, p(SV FWE) = 0.05, d(cluster) = 0.8, d(anatomical mask) = 0.38)   - Learning signal predicts pre-post change in right AI pain-related activation (Z = 4.4, p(SV FWE) = 0.006, f²(cluster) = 0.36, f²(anatomical mask) = 0.42)   - Path analysis: indirect effect via learning significant (Path a standardized = −0.409, Path b standardized = 0.330); direct path not significant (standardized = −0.121)   - Moderated mediation by treatment group (χ²(1) = 4.56, p = 0.033, w = 0.356)   - Impression ratings: main effect of social context (F(1,34) = 10.85, f = 0.565); ingroup rated more favorably
- **learning_from:** Other (ingroup or outgroup treatment provider); pain relief/pain delivery outcomes
- **learning_about:** World; anticipated pain relief value (cue-outcome association)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Rescorla-Wagner (fixed α = 0.3; V(t+1) = V(t) + α(λ(t) − V(t)))
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Rescorla-Wagner (fixed α = 0.3)", "family": "Rescorla-Wagner", "n_params": 0, "metric": "N/A — fixed parameter, no model comparison"}] - Note: Only one model was used. The learning rate was fixed at 0.3 based on literature; behavioral confirmation was done post hoc by fitting α to emotion ratings (mean fitted α ≈ 0.35 outgroup, 0.39 ingroup, not significantly different from 0.3).
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): fixed at 0.3 (behaviorally estimated: 0.35 [0.24–0.45] outgroup; 0.39 [0.28–0.49] ingroup) - λ(t): outcome (+1 pain relief, −1 pain) - V(t): pain relief anticipation value (used as parametric modulator) - δ(t): prediction error = α(λ(t) − V(t))
- **social_param:** None explicitly — the social manipulation is between-subjects (ingroup vs. outgroup), not parameterized within the RL model. The model is identical across groups.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A — only one model tested; learning rate confirmed via behavioral fitting (non-linear least squares)
- **how_model_fit:** params-calculated-independently (fixed α = 0.3; post hoc behavioral confirmation via non-linear least squares fitting of emotion ratings)
- **data_type_fit_to:** Neural activity (parametric modulator of fMRI); behavioral emotion ratings (for learning rate confirmation)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — trial-by-trial V(t) from RL model used as parametric modulator of cue-related BOLD
- **contrast:** - Pain relief anticipation (V(t)) as parametric modulator during pain-predicting cue → right AI (SV FWE p = 0.04) - Pre-treatment pain > post-treatment pain (outgroup group) → bilateral AI (left AI, SV FWE p = 0.05) - Pre-vs-post pain change predicted by right AI learning signal (regression) → right AI (SV FWE p = 0.006; whole-brain cluster FWE p = 0.02)
- **key_regions:** Pain relief learning signal in right anterior insula (AI); pre-to-post pain reduction in bilateral AI after outgroup treatment; SMA and middle temporal gyrus in exploratory whole-brain analyses.
- **key_regions_abbrev:** insula, AI
- **coordinates_peak:** Table S1 (learning signal, whole sample): - right anterior insula/inferior frontal gyrus: 48, 26, 2 - right anterior insula/inferior frontal gyrus (sub-peak): 39, 26, 5 - left temporal pole: −33, 17, −22 - left SMA: −15, 5, 62 - right SMA: 6, 11, 59 - right middle frontal gyrus: 42, −4, 53 - right middle occipital gyrus: 36, −88, 8 - right fusiform gyrus: 30, −67, −13 - left superior occipital gyrus: −15, −97, 17 - left middle temporal gyrus: −51, −55, 5 - left lingual gyrus: −18, −85, −10 - right lingual gyrus: 21, −85, −13 - left precentral gyrus: −45, 2, 29 - right precentral gyrus: 51, 5, 32 - cerebellar vermis: 3, −40, −13  Table S3 (pre-to-post outgroup treatment): - left anterior insula: −42, 2, 5 - left postcentral gyrus: −63, −22, 20 - left inferior parietal lobe: −51, −25, 41  Table S4 (pre-vs-post pain change predicted by learning signal): - right anterior insula: 39, 17, −7 - left anterior insula/left inferior frontal gyrus: −39, 20, −4 - left inferior frontal gyrus: −57, 14, 5 - left SMA: −18, −10, 59 - right SMA: 15, 11, 62 - left middle temporal gyrus: −54, −16, −16
- **analysis_type:** both (primary analyses used ROI with bilateral anatomical insular cortex masks and SV FWE correction; exploratory whole-brain analyses also reported at p < 0.001 uncorrected, k ≥ 5)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 40 (36 included in analyses after 4 exclusions: 2 motion artefacts, 2 technical problems); 18 ingroup treatment, 18 outgroup treatment; all male; mean age = 22.7 (SE = 0.41)
- **population_category:** healthy adults
- **population_age_range:** M=22.7
- **ecological_validity:** Moderate. Uses real painful electrical stimulation and ethnic/national group manipulation with ecological validity in Swiss context (Swiss vs. Balkan names). However, interaction is minimal (no face-to-face exchange), confederates are strangers, and social manipulation is limited to name-based national identity cuing. All-male sample limits generalizability.
- **eligibility_flag:** Borderline — the computational model is a standard Rescorla-Wagner with a fixed learning rate (no free parameters fitted to individual data for the primary fMRI analysis). The model is used as a parametric modulator rather than being fitted/compared in a model comparison framework. The learning occurs over time (20 treatment trials). Flag as: "Minimal computational modeling — fixed-parameter RL used as parametric modulator only; no model comparison or individual-level fitting for primary analysis.
- **concerns:** - Only one model tested (Rescorla-Wagner with fixed α = 0.3); no model comparison - Learning rate fixed a priori from literature, not individually estimated for fMRI analysis - Small sample (N = 36 analyzed, 18 per group) for between-subjects fMRI design - All-male sample - Post hoc behavioral fitting of α to emotion ratings used to justify assumed learning rate, but this was not used in the primary fMRI analysis - Path analysis/mediation used with small between-subjects sample — power concerns for moderated mediation - No parameter recovery or model recovery reported - Social manipulation is between-subjects, meaning the social variable is not computationally modeled within the RL framework
- **limitations_reported:** The relatively small sample size (N = 40, 36 included in all analyses) remains a limitation of this study"; "Owing to the complex experimental design (social group manipulation, pain thresholding, coordination between four confederates and the participants), it was not possible to record data from more than 40 subjects"; authors encourage future research to adapt and simplify the design; all-male sample acknowledged implicitly by describing design choice to "limit total number of confederates and avoid complications of gender-mixed pairing
- **limitations_categorized:** sample size; limited generalizability (all-male sample); task complexity limiting sample size; limited ecological validity (impersonal intergroup setting)  ---  ## WC CHECKLIST  1. Design a good experiment: **Yes** — task engages pain relief learning in social context with between-subjects manipulation 2. Design good models: **No** — only one model (RW with fixed α); no competing models tested 3. Simulate, simulate, simulate: **No** — no simulations described 4. Fit the parameters: **Partial** — learning rate fixed at 0.3 for primary analysis; post hoc behavioral fitting done separately but not used in fMRI analysis 5. Check parameter recovery: **No** — not reported 6. Check model recovery: **No** — not reported (only one model) 7. Fit real data and compare models: **No** — only one model tested 8. Validate the winning model: **Partial** — behavioral confirmation that estimated learning rates do not differ from assumed 0.3, but no posterior predictive check or formal model validation 9. Analyze the winning model: **Yes** — V(t) used as parametric modulator; learning signals analyzed in relation to pain outcomes 10. Report results transparently: **Yes** — data and scripts shared on GitHub; imaging data on NeuroVault
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `winning_model`: MEDIUM confidence — described as "standard reinforcement learning model" but with fixed (not fitted) learning rate for primary analysis - `eligibility_flag`: MEDIUM — borderline computational modeling (fixed-parameter RL as parametric modulator) - `social_param`: LOW — no social parameter within the model; social variable is between-subjects only - `model_comparison_metric`: N/A — only one model, no comparison - `effect_size`: HIGH — multiple effect sizes reported throughout (Cohen's d, f, f², w, standardized path coefficients)
- **cannot_find:** No fields left blank without explanation. All coordinates extracted from supplement tables S1, S3, S4.
- **other_notes:** The paper also includes a separate OLS regression model and path/mediation analysis (using Lavaan in R) to test whether social context affects pain directly or indirectly through learning. This is a statistical mediation model, not a computational model of learning per se. The RL model serves primarily as a tool to generate trial-by-trial regressors for fMRI, not as a substantive computational model that is compared or fitted. Data shared openly (GitHub + NeuroVault). A second independent task was performed in the same scanning session but published separately (Hein et al., 2016 PNAS).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = general
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- tax_domain_D_group_structure_identity
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = D_group_structure_identity
- tax_rr_domain_D_group_structure_identity
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = intergroup_bias
- tax_rr_secondary_topic = empathy_vicarious
- tax_rr_topic_empathy_vicarious
- tax_rr_topic_intergroup_bias
- tax_topic_empathy_vicarious
- tax_topic_intergroup_bias
