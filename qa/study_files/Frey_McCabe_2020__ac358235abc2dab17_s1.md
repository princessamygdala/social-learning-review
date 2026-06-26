# Frey & McCabe (2020)

- **study_id:** `ac358235abc2dab17_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Frey, A.-L., & McCabe, C. (2020). Effects of serotonin and dopamine depletion on neural prediction computations during social learning. *Neuropsychopharmacology*, *45*(8), 1431–1437. https://doi.org/10.1038/s41386-020-0678-z
- **citation_short:** Frey & McCabe (2020)
- **doi:** 10.1038/s41386-020-0678-z
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** etheroleoftheseneurotransmittersinthesociallearningprocessusingadietarydepletionmanipulation; mitters have been thalamus, and midbrain, and to attenuate PE encoding in the; mitters on learning precuneus[25,32],whilealsodiminishingpunishmentprediction; ethecasethatdecreased5-HTlevelscontributetosociallearningdeficitsindepression; SchoolofPsychologyandClinicalLanguageSciences,UniversityofReading,Reading,UK; ethat5-HTdepletionimpairslearningfromsocialrewards,onboththe; ethis questionby loweringDAor5-HT levelsin; mittersmaycontributetotheseimpairments; emails: c.mccabe@reading.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Social reward learning; social aversion learning; neurotransmitter (5-HT and DA) modulation of social prediction signals
- **study_focus_short:** Social reward learning · social aversion learning
- **learning_mode_description:** - Learning mode: Learning from social emotional outcomes (facial expressions) about name-emotion contingencies   - Learning from:     - Source type (social): other (strangers' faces)     - Source content (social): outcome (emotional facial expression — happy or fearful vs. neutral)   - Learning about:     - Target type (social): other (stranger identity associated with name cue)     - Target content (social): stimulus (name-face emotion contingency; probability of emotional expression)
- **task_description:** Participants learned probabilistic associations between name cues and emotional facial expressions (happy or fearful vs. neutral) across social reward and social aversion blocks, rating the likelihood of an emotional outcome on each trial before seeing the face.
- **task_paradigm:** Social conditioning
- **players:** Single agent (participant), multi-target (6 name-face identities; 3 per valence block)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Name cues (modified Scandinavian/Eastern European names), facial expressions (happy, fearful, neutral) from the Pictures of Facial Affect series, visual analog rating scale (0–100%)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - 5-HT depletion impaired social reward learning: lower likelihood ratings for 75% trials (p = .010) and higher ratings for 25% trials (p = .002) vs. placebo - DA depletion led to higher ratings on 25% social reward trials vs. placebo (p = .040) - Significant group × valence × probability interaction (F(3.84, 109.45) = 3.72, p = .008) - No group differences in social aversion learning (all F < 2.65) - 5-HT depletion reduced social reward prediction encoding in dACC/dmPFC, premotor/dlPFC, bilateral temporal lobe/fusiform gyrus, right insula (whole-brain corrected) - DA depletion reduced social reward prediction encoding in dmPFC/pre-SMA and dACC vs. placebo - 5-HT depletion reversed prediction signals (tracked neutral rather than happy face predictions) - No group differences in striatal PE encoding (all F < 0.8)
- **effect_size:** - Group × probability (social reward): F(2.73, 77.65) = 4.42, p = .008 - Group × valence × probability: F(3.84, 109.45) = 3.72, p = .008 - 75% social reward, placebo vs. 5-HT: Bonferroni p = .010 - 25% social reward, placebo vs. 5-HT: Bonferroni p = .002 - 25% social reward, placebo vs. DA: Bonferroni p = .040 - Neuroimaging: whole-brain cluster-level FWE corrected (voxelwise p < .005); peak Z scores reported in Table S1 (e.g., dACC Z = 3.67; right insula Z = 3.77; premotor/dlPFC Z = 4.35) - No formal effect size measures (d, r, η²) reported
- **learning_from:** Other (strangers); social emotional facial expressions (happy/fearful vs. neutral outcomes)
- **learning_about:** Other (stranger name-face identities); name-emotion contingency (probability of emotional expression)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** face_expression

## Algorithmic level
- **winning_model:** Rescorla–Wagner (1 α, 1 γ decay; V(t+1) = V(t) + α·δ, where δ = R(t) − V(t); decay: V(49) = V(49) + γ·(0.5 − V(49)))
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Rescorla-Wagner with decay", "family": "Rescorla-Wagner", "n_params": 2, "metric": "sum of squared errors (minimized)"}]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): no significant group differences; no mean fitted values reported (social reward block: H(2) = 1.89, p = .389; social aversion block: H(2) = 0.80, p = .672) - γ (decay parameter): accounts for forgetting between practice and experimental trials; no significant group differences; no mean fitted values reported (reward: H(2) = 3.37, p = .185; aversion: H(2) = 1.56, p = .459)
- **social_param:** None explicitly designated as a social parameter. The model is a standard RW applied to social outcomes; no parameter specifically captures social content.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A — only one model tested; model fit assessed via mean squared errors (no significant group differences)
- **how_model_fit:** Individual-level fit (fmincon in MATLAB minimizing sum of squared errors between participant ratings and model predictions). Note: authors state extensive model fitting/comparison was not performed because the main purpose was model-based fMRI analysis, not behavioral parameter inference.
- **data_type_fit_to:** Choice behavior (likelihood ratings on visual analog scale)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors) + ROI analysis
- **contrast:** - Social reward prediction encoding: Placebo > 5-HT depletion (dACC, dmPFC, premotor/dlPFC, bilateral temporal lobe/fusiform, right insula) - Social reward prediction encoding: Placebo > DA depletion (pre-SMA/dmPFC, dACC) - Social aversion prediction encoding: 5-HT depletion > Placebo (right thalamus) - Social aversion prediction encoding: 5-HT depletion > DA depletion (precentral gyrus) - PE encoding (ROI): inverse predictions and outcome values at striatal ROIs — no group differences - Prediction value ROI at sgACC — no group differences - Happy vs. neutral faces; fearful vs. neutral faces; social aversion vs. social reward cues (supplementary) - 5-HT depletion showed reduced vmPFC response to fearful vs. neutral faces vs. placebo (Table S4)
- **key_regions:** 5-HT depletion reduced social reward prediction encoding in dACC/dmPFC, premotor cortex/dlPFC, bilateral temporal lobe/fusiform gyrus, and right insula; DA depletion reduced encoding in dmPFC/pre-SMA and dACC only. 5-HT depletion reversed prediction signals (tracking neutral rather than happy faces). No group differences in striatal PE encoding.
- **key_regions_abbrev:** mPFC, dmPFC, dlPFC, dACC, ACC, insula, FFA
- **coordinates_peak:** Social Reward Prediction — Placebo > 5-HT Depletion: - Premotor/BA 6 extending to dlPFC/BA 8: -26, 6, 48 - Dorsal ACC: 8, 20, 30 - Dorsomedial PFC: -8, 48, 34 - Left Superior Temporal Lobe: -44, -44, 16 - Right Lingual/Fusiform Gyrus: 22, -72, -2 - Right Superior Temporal Lobe: 58, -36, 14 - Right Insula: 34, -20, 14 - Left Fusiform Gyrus: -32, -66, -12  Social Reward Prediction — Placebo > DA Depletion: - Pre-SMA/Dorsomedial PFC: -10, 10, 60 - Dorsal ACC: 8, 22, 26  Social Aversion Prediction — 5-HT Depletion > Placebo: - Right Thalamus: 28, -30, 8  Social Aversion Prediction — 5-HT Depletion > DA Depletion: - Precentral Gyrus: 22, -8, 52  Inverse Social Reward Predictions (5-HT depleted, Table S2): - Left Superior Temporal Lobe: -44, -44, 14 - Cerebellum/Fusiform Gyrus: -8, -56, -12 - Right Middle Temporal Lobe: 68, -46, 8 - Precuneus: 6, -62, 54  Striatal PE ROIs (from meta-analysis, Chase et al.): - Left striatum: -10, 8, -6 - Right striatum: 10, 8, -10 sgACC ROIs: - ROI 1: 4, 34, -6 - ROI 2: -6, 28, -20
- **analysis_type:** both (whole-brain for prediction encoding contrasts; ROI for striatal PE and sgACC prediction analyses)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 70 (5-HT depletion: N = 24; DA depletion: N = 24; placebo: N = 22); ages 18–45; predominantly female (56/70 female). Behavioral outliers removed: N = 3 (5-HT), N = 3 (placebo), N = 4 (DA).
- **population_category:** healthy adults
- **population_age_range:** 18–45
- **ecological_validity:** Low — abstract name-face pairings with strangers' faces (Ekman stimuli); probabilistic Pavlovian contingencies rather than real social interaction; no actual social exchange or reciprocity. Lab-based fMRI environment.
- **eligibility_flag:** 
- **concerns:** - Only one computational model tested; no model comparison performed — authors explicitly state "extensive model fitting, comparison, and validation was not performed" - No parameter recovery or model recovery reported - No posterior predictive checks or model validation - Learning rate and decay parameters showed no group differences, and authors refrain from interpreting behavioral performance from model parameters — the model was used primarily as a tool to generate regressors for fMRI, not to draw behavioral inferences - Effect sizes (Cohen's d, η², etc.) not reported for behavioral or neural results - Social stimuli may not be sufficiently rewarding (authors acknowledge happy faces of strangers may not elicit robust DA response) - Potential 5-HT/DA interaction effects cannot be ruled out - Between-subjects design (no within-subject control) - Relatively small sample per group (N = 22–24)
- **limitations_reported:** The current interpretation of reversed prediction signals is speculative and alternative explanations exist; 5-HT depletion may have led to reduced DA activity in frontal cortex through 5-HT/DA interactions, so decreased DA rather than 5-HT functioning may have played a role in PFC effects; DA depletion had a less extensive effect which may suggest either that DA is less crucially involved in social learning or that the stimuli used (happy faces of strangers) were not rewarding enough to elicit a robust DA response; future studies using more rewarding social stimuli (such as pictures of friends) are needed
- **limitations_categorized:** Speculative interpretation; neurotransmitter system interaction confounds; limited ecological validity; stimulus salience limitations; small sample size per group; no model comparison; no parameter/model recovery
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Partial
- **wc_rule10:** Partial
- **wc_score:** 3.0
- **wc_total:** 3.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM — no formal effect size measures (d, r², η²) reported; only F-statistics, p-values, and Z-scores available - social_param: MEDIUM — no parameter explicitly designated as "social"; the standard RW model is applied to social stimuli but contains no social-specific parameter - model_params (mean fitted values): LOW — mean fitted α and γ values are not reported; only group-comparison test statistics provided - winning_model: HIGH — formula clearly stated in supplement - coordinates_peak: HIGH — comprehensive coordinate tables in supplement Tables S1–S4 - learning_mode: HIGH — directly inferred from task description
- **cannot_find:** - Mean fitted parameter values for α and γ (not reported in main text or supplement) - Formal effect sizes (Cohen's d, η², etc.) for behavioral or neural results - Data/code sharing statement
- **other_notes:** - Supplement accessed (.doc format); contains detailed computational model equations, fMRI analysis methods, and four coordinate tables (S1–S4) - This paper explicitly notes that model fitting was not the primary goal — the RW model served to generate parametric regressors for model-based fMRI - Authors reference Wilson & Niv (2015) to justify that precise model fitting is unnecessary for model-based fMRI parametric modulation analyses - Paper builds directly on Frey & McCabe (2019) which used the same task in individuals with high depression scores - The study is a between-subjects pharmacological manipulation (dietary amino acid depletion), not a clinical sample
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pharma_dopamine
- pharma_serotonin
- pop_healthy_adults
- rr_pharma_dopamine
- rr_pharma_serotonin
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = general
- spec_locus = source
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_decay
- tax_param_learning_rate
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_topic_social_approval_reward
