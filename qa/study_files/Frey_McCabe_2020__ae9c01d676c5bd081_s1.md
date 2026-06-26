# Frey & McCabe (2020)

- **study_id:** `ae9c01d676c5bd081_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Frey, A.-L., & McCabe, C. (2020). Impaired social learning predicts reduced real-life motivation in individuals with depression: A computational fMRI study. *Journal of Affective Disorders*, *263*, 698–706. https://doi.org/10.1016/j.jad.2019.11.049
- **citation_short:** Frey & McCabe (2020)
- **doi:** 10.1016/j.jad.2019.11.049
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ethods: Forty-three individuals with high (HD; N=21) and low (LD; N=22) depression scores answered; SchoolofPsychologyandClinicalLanguageSciences,UniversityofReading,Reading,RG66AL,UK; ether,ourfindingssuggestthatreducedlearningfromsocialoutcomesmayimpairde-; mitations: Thesizeoftheincludedsamplewasrelativelysmall; ether these impairments are related to the above-; mitedevidenceforchangesinsocial; lable online 11 November 2019; mithaspreviouslybeen; emails: c.mccabe@reading.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Social learning from emotional faces in depression; learning associations between name cues and emotional facial expressions (happy/fearful) to predict social outcomes, and relating impairments to real-life social motivation.
- **study_focus_short:** Social learning from emotional faces in depression
- **learning_mode_description:** - Learning mode: Learning from probabilistic social outcomes (emotional facial expressions) about the predictive value of social cues   - Learning from:     - Source type (social): other (strangers' faces)     - Source content (social): outcomes (emotional facial expressions — happy or fearful vs. neutral)   - Learning about:     - Target type (social): other (strangers)     - Target content (social): state (predicted emotional expression likelihood; cue-outcome contingencies)
- **task_description:** Participants learned probabilistic associations between name cues and emotional facial expressions (happy, fearful, or neutral) presented at varying contingencies (25%, 50%, 75%). They indicated on a visual analogue scale their estimate of the likelihood that a given name cue would be followed by an emotional expression, across social reward (happy) and social aversion (fearful) blocks.
- **task_paradigm:** Social conditioning
- **players:** Single agent (participant), multi-target (6 strangers' faces)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Name cues (modified Scandinavian/Eastern European names), face photographs (happy, fearful, neutral expressions from Pictures of Facial Affect; Ekman & Friesen, 1976), visual analogue rating scale
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - HD participants showed elevated uncertainty about social outcomes compared to LD controls (F(1,41) = 3.67, p = 0.062)   - Group x probability interaction on likelihood ratings (F(2,82) = 11.77, partial effect not reported as η²)   - Task uncertainty + questionnaire measures predicted social engagement motivation (R² = 0.51)   - UIS negativity predicted reduced social motivation (β = −0.55)   - UIS negativity × task uncertainty interaction predicted reduced social motivation (β = −0.32)   - Lower learning rates in HD vs LD: social reward block (U = 351, p = 0.004), social aversion block (U = 355, p = 0.003)   - Reduced social reward prediction encoding in HD vs LD in superior parietal lobe/precuneus (Z = 3.80, p_FWE = 0.001) and right insula cluster (Z = 3.47, p_FWE = 0.045)   - Parietal prediction encoding correlated with social motivation (r = 0.49, p = 0.002; r = 0.36 controlling for BDI and uncertainty)   - Insula prediction encoding correlated with social motivation (r = 0.36, p = 0.023; ns when controlling for BDI)   - No group differences in striatal PE encoding (all F < 2.9)
- **effect_size:** - Main Results:   - HD participants showed elevated uncertainty about social outcomes compared to LD controls (F(1,41) = 3.67, p = 0.062)   - Group x probability interaction on likelihood ratings (F(2,82) = 11.77, partial effect not reported as η²)   - Task uncertainty + questionnaire measures predicted social engagement motivation (R² = 0.51)   - UIS negativity predicted reduced social motivation (β = −0.55)   - UIS negativity × task uncertainty interaction predicted reduced social motivation (β = −0.32)   - Lower learning rates in HD vs LD: social reward block (U = 351, p = 0.004), social aversion block (U = 355, p = 0.003)   - Reduced social reward prediction encoding in HD vs LD in superior parietal lobe/precuneus (Z = 3.80, p_FWE = 0.001) and right insula cluster (Z = 3.47, p_FWE = 0.045)   - Parietal prediction encoding correlated with social motivation (r = 0.49, p = 0.002; r = 0.36 controlling for BDI and uncertainty)   - Insula prediction encoding correlated with social motivation (r = 0.36, p = 0.023; ns when controlling for BDI)   - No group differences in striatal PE encoding (all F < 2.9)
- **learning_from:** Other (strangers' emotional facial expressions); probabilistic social outcomes (happy/fearful/neutral faces)
- **learning_about:** Other (strangers); cue-outcome contingency — predicted likelihood of emotional expressions  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** face_expression

## Algorithmic level
- **winning_model:** Rescorla-Wagner (1 α, 1 γ decay; V(t+1) = V(t) + α × δ; δ = r(t) − V(t))
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Rescorla-Wagner with decay", "family": "Rescorla-Wagner", "n_params": 2, "metric": "sum of squared errors"}] - Note: Only one model was tested; no formal model comparison was conducted.
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): mean fitted values — social reward block: 0.12 (average across all participants); social aversion block: 0.08 (average across all participants). HD < LD in both blocks (p = 0.004 and p = 0.003 respectively). [Not marked S — standard RW parameter] - γ (decay parameter): determines strength of forgetting between practice and experimental phases. No mean value reported. - V₀ (initial prediction value): fixed at 0.5
- **social_param:** None explicitly designated as a "social" parameter. The learning rate α governs learning from social outcomes (emotional faces) but is a standard RW parameter applied in a social context.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Sum of squared errors (model fit assessment only; no formal model comparison across competing models)
- **how_model_fit:** individual-level-fit (parameters estimated per participant by minimising sum of squared errors)
- **data_type_fit_to:** self-report ratings (likelihood ratings on visual analogue scale)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors)
- **contrast:** - Social reward prediction encoding: LD > HD (parametric modulation of prediction values at cue onset) — significant in superior parietal lobe/precuneus and right insula/supramarginal gyrus/superior temporal lobe - Social aversion prediction encoding: LD vs HD — no significant group differences - PE encoding (outcome and inverse prediction components in striatal ROI): no significant group differences - Supplementary GLM3: fearful vs neutral faces HD > LD — significant in dACC/MCC, dlPFC, vlPFC, insula, supramarginal gyrus, inferior temporal lobe, fusiform gyrus, occipital lobe
- **key_regions:** Reduced social reward prediction encoding in HD vs LD in superior parietal lobe/precuneus and right insula/supramarginal gyrus/superior temporal lobe; parietal prediction encoding correlated with real-life social motivation across groups. No group differences in striatal PE encoding. Supplementary: HD showed greater fearful vs neutral face responses in dACC, dlPFC, vlPFC, insula, supramarginal gyrus, inferior temporal lobe.
- **key_regions_abbrev:** dlPFC, dACC, ACC, insula, precuneus, parietal
- **coordinates_peak:** Main text Table 2 (LD > HD, social reward prediction encoding): - Superior Parietal Lobe/Precuneus: −18, −58, 68 - Right Insula: 48, −20, 18 - Right Supramarginal Gyrus: 58, −32, 24 - Right Superior Temporal Lobe: 68, −22, 12  ROI coordinates (from meta-analysis, Chase et al., 2015): - Left striatum ROI: −10, 8, −6 - Right striatum ROI: 10, 8, −10 - sgACC ROI 1: 4, 34, −6 - sgACC ROI 2: −6, 28, −20  Supplement Table S1 (LD main effect, social reward prediction): - Right Inferior Temporal Lobe: 52, −36, −22 - Right Superior Temporal Lobe: 44, −24, −4 - Right Fusiform Gyrus: 38, −34, −22  Supplement Table S2 (LD > HD, individual parameters): - Precuneus: 20, −50, 46 - Inferior Parietal Lobe: 32, −58, 48 - Superior Temporal Lobe: 38, −56, 18  Supplement Table S3 (HD > LD, fearful vs neutral faces): - Dorsal ACC/MCC: −2, 10, 28 - Right Occipital Lobe: 18, −92, −8 - Right Fusiform Gyrus: 34, −76, −18 - Right dlPFC (BA 8): 50, 24, 42 - Right vlPFC (BA 45): 54, 32, 10 - Right Insula: 46, 10, 12 - Right Supramarginal Gyrus: 36, −46, 50 - Right Inferior Temporal Lobe: 58, −54, −4 - Left Inferior Temporal Lobe: −54, −58, −14 - Left Supramarginal Gyrus: −28, −48, 52
- **analysis_type:** both (whole-brain for prediction encoding group comparisons + ROI for striatal PE and sgACC analyses)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 43 (21 HD, 22 LD); ages 18–45 (HD: M = 23.20, SD = 5.66; LD: M = 22.45, SD = 4.35); HD group: 17F/4M; LD group: 14F/8M
- **population_category:** clinical
- **population_age_range:** 18–45
- **ecological_validity:** Task uses abstract name-face pairings with probabilistic emotional expressions, which is a simplified lab proxy for real-life social prediction. However, the study explicitly links task performance to self-reported real-life social experiences (motivation, closeness to friends), which strengthens ecological relevance. Stimuli are faces of strangers, limiting generalizability to close relationships.
- **eligibility_flag:** 
- **concerns:** - Only one computational model tested (no model comparison) - Small sample size (N = 43) - HD group defined by BDI cutoffs, not clinical MDD diagnosis — limits clinical generalizability - Practice data missing for 4 HD and 9 LD participants due to technical difficulties - Uncorrected voxelwise threshold of p < 0.01 used (with cluster-level FWE correction) - Gender imbalance between groups (not statistically tested) - Average parameters used for fMRI parametric modulators rather than individual parameters (though individual parameter analysis in supplement yielded similar results) - No correction for multiple comparisons in correlation analyses between neural measures and real-life motivation
- **limitations_reported:** The size of the included sample was relatively small; results should be regarded as preliminary and replications in larger samples are called for; future studies should assess how social learning in depression is affected when other, including more rewarding, social stimuli are used.
- **limitations_categorized:** sample size; limited stimulus variety; limited ecological validity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - social_param: MEDIUM — no parameter explicitly designated as "social"; α governs learning from social stimuli but is a standard RW parameter - γ (decay parameter) mean value: LOW — not reported in text or supplement - effect_size for group x probability interaction: MEDIUM — η² not reported, only F-statistic - Gender balance: LOW — gender distribution differs between groups but statistical test not reported
- **cannot_find:** - Exact fitted γ (decay) parameter values - Individual-level α distributions (only group averages and group comparison U-tests reported) - Effect sizes in standardized format (Cohen's d) for most comparisons — reported as F, U, r, β - Code/data availability statement
- **other_notes:** The paper uses a Pavlovian conditioning paradigm framed in a social context (learning emotional expression probabilities from faces). The computational model is relatively simple (standard RW with one free learning rate per block). The key contribution is linking computational model-derived measures to both neural responses and real-life social functioning. The supplementary material provides substantial additional fMRI results including three separate GLM analyses, ROI analyses, and analyses with individual vs. average parameters.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_depression
- pop_healthy_adults
- rr_pop_depression
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = general
- spec_locus = source+target+context
- spec_neural = shared
- spec_source = social
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_decay
- tax_param_learning_rate
- tax_param_social_bonus
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = emotion_inference
- tax_rr_secondary_topic = social_approval_reward
- tax_rr_topic_emotion_inference
- tax_rr_topic_social_approval_reward
- tax_topic_emotion_inference
- tax_topic_social_approval_reward
