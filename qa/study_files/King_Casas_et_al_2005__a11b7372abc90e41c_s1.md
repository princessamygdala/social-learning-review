# King-Casas et al. (2005)

- **study_id:** `a11b7372abc90e41c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** King-Casas, B., Tomlin, D., Anen, C., Camerer, C. F., Quartz, S. R., & Montague, P. R. (2005). Getting to know you: Reputation and trust in a two-person economic exchange. *Science*, *308*(5718), 78–83. https://doi.org/10.1126/science.1108062
- **citation_short:** King-Casas et al. (2005)
- **doi:** 10.1126/science.1108062
- **publication_type:** peer-reviewed journal
- **year:** 2005.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ethe work of all authors cited; College of Medicine in; ethendecidedhowmuch; InstituteofTech-; ethods
- **code_url:** 

## Computational level
- **study_focus:** Trust learning / reputation learning — learning about a partner's trustworthiness through iterated economic exchange, with reputation building over time.
- **study_focus_short:** Trust learning / reputation learning
- **learning_mode_description:** - Learning mode: Learning from a partner's reciprocity behavior about the partner's trustworthiness (reputation) over repeated trust exchanges   - Learning from:     - Source type (social): other (anonymous partner — investor, from trustee perspective)     - Source content (social): action/policy (reciprocity — fractional change in investment/repayment)   - Learning about:     - Target type (social): other (anonymous partner)     - Target content (social): state (mental state; trustworthiness / reputation)
- **task_description:** In a multiround trust game, one player (investor) decides how much of a $20 endowment to invest with an anonymous partner (trustee); the investment is tripled and the trustee decides how much to repay. The same dyad plays 10 consecutive rounds, allowing reputation to develop.
- **task_paradigm:** Trust game
- **players:** Multi-agent (dyad), asymmetric (investor and trustee roles fixed throughout)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Monetary units (abstract numerical amounts), bar graphs displaying investment/repayment amounts
- **method:** fMRI / hyperscanning / behavioural
- **method_full:** fMRI (hyperscanning — simultaneous scanning of both players at separate sites) + behavioural
- **main_result:** - Main Results:   - Investor reciprocity (ΔI_j − ΔR_{j-1}) strongly predicted subsequent changes in trustee repayment (r = 0.56)   - Head of caudate nucleus in trustee brain showed greater BOLD response to benevolent vs. malevolent investor reciprocity (T(247), p < .001, uncorrected)   - "Intention to trust" signal in trustee caudate shifted by 14 s from reactive (post-revelation) to anticipatory (pre-revelation) across rounds, consistent with reputation/model building   - Cross-brain correlation between investor MCC and trustee caudate "intention to trust" signal peaked at 14-s shift (r = 0.59)   - Increases in repayment correlated with subsequent investment changes (r = 0.27); decreases did not (r = 0.00)   - Behavioral experiment (n = 21 pairs): trustee accuracy in guessing investor's next move improved over rounds, paralleling the temporal transfer
- **effect_size:** r = 0.56 (reciprocity predicting trust change); r = 0.59 (cross-brain MCC-caudate correlation); r = 0.27 (repayment increase predicting investment change); T(381), p < .0001 (benevolent/malevolent > neutral contrast); T(247), p < .001 (benevolent > malevolent caudate contrast)
- **learning_from:** Other (partner); reciprocity behavior (fractional change in investment/repayment across rounds)
- **learning_about:** Other (partner); partner's trustworthiness / reputation  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** No formal computational model fitted. The paper uses a descriptive operationalization of reciprocity (ΔI_j − ΔR_{j-1}) and linear regression to predict behavior. The authors draw an analogy to reinforcement learning prediction error signals (temporal transfer resembling reward prediction error shift) but do not fit an RL or any other computational model to the data.
- **model_family:** Rescorla-Wagner
- **model_class:** Other
- **all_models_tested:** None — no formal model comparison conducted.
- **model_mb_mf:** 
- **model_params:** N/A — no model parameters estimated. The reciprocity measure (ΔI_j − ΔR_{j-1}) is a descriptive behavioral variable, not a model parameter.
- **social_param:** 
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A — no model comparison performed.
- **how_model_fit:** N/A — no model fitting performed. Linear regression and correlational analyses used on behavioral and neural data.
- **data_type_fit_to:** N/A (behavioral analyses used linear regression on choice behavior; neural analyses used GLM on BOLD signal, but no computational model was fitted)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** univariate GLM (random-effects analysis with reciprocity as between-group factor) + ROI time-series analysis + cross-brain correlational analysis (hyperscanning)
- **contrast:** - Benevolent or malevolent reciprocity > neutral reciprocity (trustee brain): inferior frontal sulcus, superior frontal sulcus, thalamus, i/s colliculi - Benevolent reciprocity > malevolent reciprocity (trustee brain): head of caudate nucleus - "Intention to trust" signal: caudate ROI segregated by subsequent repayment increase vs. decrease - Cross-brain: trustee caudate "intention to trust" correlated with investor MCC and trustee ACC
- **key_regions:** Social reciprocity surprise signal in inferior frontal sulcus, superior frontal sulcus, thalamus, and colliculi; benevolent reciprocity preference in head of caudate nucleus; intention-to-trust temporal transfer in caudate; cross-brain correlation with investor MCC and trustee ACC.
- **key_regions_abbrev:** caudate, ACC, AI, IFG, SFG, thalamus
- **coordinates_peak:** Contrast 1 (benevolent or malevolent > neutral): - i/s colliculi (R): 4, -28, -4 - i/s colliculi (L): -8, -28, -8 - thalamus (R): 8, -4, 0 - thalamus (L): -8, 0, 0 - inferior frontal sulcus (R): -48, 4, 32 - inferior frontal sulcus (L): 48, 8, 28 - superior frontal sulcus (R): -32, 12, 48  Contrast 2 (benevolent > malevolent): - caudate (R): 12, 24, 4 - caudate (L): -8, 20, 4  Additional ROI coordinates from text: - MCC (investor brain): 0, 12, 40 - ACC (trustee brain): 8, 40, -8
- **analysis_type:** both (whole-brain GLM for contrast identification + ROI analyses on caudate, MCC, ACC)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 48 pairs (96 subjects) for fMRI hyperscanning study; N = 21 pairs (42 subjects) for behavioral replication/model-building experiment. Total N = 138.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** The multiround format improves ecological validity over single-shot trust games by allowing reputation building, but the interaction remains abstract (monetary units only, no face-to-face contact, anonymous partners at different geographic sites). No verbal communication or social cues beyond monetary decisions.
- **eligibility_flag:** The paper does not fit a formal computational model to behavioral or neural data. The analogy to reinforcement learning prediction errors is descriptive only. This should be flagged: "No formal computational model fitted — descriptive/correlational analysis with RL analogy discussed but not implemented. Borderline for inclusion criterion 'uses computational modeling.
- **concerns:** - No formal computational model is specified or fitted despite the paper being frequently cited as a computational study of trust learning. The reciprocity measure is a descriptive behavioral variable, not a model-derived quantity. - The "social prediction error" interpretation is analogical — the temporal transfer is compared to reward prediction error shifts but no RL model generates the predictions. - Statistical thresholds for neuroimaging contrasts are uncorrected (p < .0001 for Contrast 1; p < .001 for Contrast 2), with a minimum cluster size of only 10 voxels. - Note on SOM Table 1: laterality labels appear inconsistent — inferior frontal sulcus "R" has negative x-coordinate (-48) and "L" has positive x-coordinate (48). This may reflect a labeling error or radiological convention issue in the original paper.
- **limitations_reported:** Authors do not report a formal limitations section. Discussion notes: the temporal transfer observation is "consistent" with but does not prove the prediction error interpretation; the reason the signal transferred to its specific anticipatory time point remains an "open issue"; behavioral signals are "intrinsically lower dimensional than their underlying neural responses.
- **limitations_categorized:** no formal computational model; uncorrected statistical thresholds; limited ecological validity; no formal limitations section reported; analogy-based interpretation rather than model-based inference
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** No
- **wc_rule10:** Partial
- **wc_score:** 1.5
- **wc_total:** 1.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_family: LOW — paper discusses RL analogy but no formal model is implemented - model_class: LOW — no model fitted; classified as N/A - eligibility_flag: MEDIUM — borderline for "uses computational modeling" criterion; the paper uses GLM on neural data and linear regression on behavior but no computational cognitive model - coordinates_peak laterality: MEDIUM — SOM Table 1 laterality labels may be inconsistent with x-coordinates for inferior frontal sulcus
- **cannot_find:** - Formal computational model specification (no model equations in main text or supplement) - Model parameters, model comparison metrics (none exist — no computational model fitted) - Effect sizes in standardized format (Cohen's d, η²) — paper reports correlations (r) and T-statistics only
- **other_notes:** This is a landmark hyperscanning study of trust and reputation learning. The paper is heavily cited in the computational social neuroscience literature, and the "social prediction error" framing is influential, but no formal RL or Bayesian model is actually fitted to data. The temporal transfer of the caudate signal from reactive to anticipatory is the key finding, interpreted as analogous to the temporal shift of dopaminergic reward prediction errors in conditioning. A separate behavioral experiment (n = 21 pairs) confirmed that trustees build increasingly accurate models of investor behavior over rounds. The paper would benefit from formal computational modeling (e.g., fitting an RL model with a social learning rate to the behavioral data) to move beyond the descriptive analogy.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = general
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_primary_topic = trust
- tax_rr_secondary_topic = reputation_learning
- tax_rr_topic_reputation_learning
- tax_rr_topic_trust
- tax_topic_reputation_learning
- tax_topic_trust
