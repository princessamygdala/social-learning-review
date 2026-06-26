# Cooper et al. (2014)

- **study_id:** `a6dd1e063ef951bf7_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Cooper, J. C., Dunne, S., Furey, T., & O'Doherty, J. P. (2014). The role of the posterior temporal and medial prefrontal cortices in mediating learning from romantic interest and rejection. *Cerebral Cortex*, *24*(9), 2502–2511. https://doi.org/10.1093/cercor/bht102
- **citation_short:** Cooper et al. (2014)
- **doi:** 10.1093/cercor/bht102
- **publication_type:** peer-reviewed journal
- **year:** 2014.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ether they would be interested in seeing each partner beliefs about another person’s thoughts and motivations; DepartmentofComputationandNeuralSystems,CaliforniaInstituteofTechnology,Pasadena,CA91125,USA,2TrinityCollege; etheranother person likes or dislikesyou can netic resonance imaging (fMRI) with face-to-face romantic; ething primarily One hundred fifty-one heterosexual student volunteers from Trinity; InstituteofNeuroscienceand3SchoolofPsychology,TrinityCollegeDublin,Dublin2,Ireland; DepartmentofComputationandNeuralSystems,CaliforniaInstituteofTechnology,Pasadena,; ethinkweknowaboutanothe
- **code_url:** 

## Computational level
- **study_focus:** Social approval learning / romantic interest learning — learning about one's own desirability from romantic expressions of interest and rejection, and updating beliefs about partners.
- **study_focus_short:** Social approval learning / romantic interest learning
- **learning_mode_description:** - Learning mode: Learning from romantic partners' acceptance/rejection decisions about one's own desirability and about partners' feelings   - Learning from:     - Source type (social): other (speed-dating partners)     - Source content (social): outcomes (yes/no romantic decisions)   - Learning about:     - Target type (social): self       - Target content (social): state (mental state; self-perceived desirability)     - Target type (social): other (partner)       - Target content (social): state (mental state; partner's feelings/beliefs about participant)
- **task_description:** Participants attended speed-dating events where they met ~20 opposite-sex partners for 5-minute conversations and made yes/no decisions about seeing each partner again. In a subsequent fMRI session (1–3 days later), participants viewed each partner's photo and learned for the first time whether that partner said yes or no to them, then rated their happiness with the outcome.
- **task_paradigm:** Self-evaluation / self-esteem task
- **players:** Single agent (scanned participant), multi-target (~51 speed-dating partners across 3 events)
- **n_players:** multi-target (3+)
- **partner_type:** human (live)
- **stimuli:** Photographs of real speed-dating partners, yes/no decision feedback, happiness rating scale
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - pSTS activated for mismatched vs. matched decisions (violations of partner-specific expectations; peak Z = 4.33)   - RMPFC correlated with unsigned prediction errors from RL model of own desirability (peak Z = 4.60)   - VMPFC activation greater for Match > Unrequited outcomes (peak Z = 5.56)   - VMPFC activation for Match outcomes predicted desire for future contact with that partner (t(648) = 4.97, p < .001), even controlling for happiness and excitement ratings (t(644) = 2.12, p = .02)   - Rostral ACC activated for Rejection > Disinterest (peak Z = 4.25)   - RL learning term significantly improved behavioral model fit (χ²(4) = 17.18, p = 0.002; learning rate α = 0.22)   - Happiness interaction: participants much happier when decisions matched (t(1922) = 10.85, p < .001)
- **effect_size:** - RL model learning rate: α = 0.22 - Whole-brain activations reported as peak Z-scores (see coordinates below); no Cohen's d or r² reported for primary imaging contrasts - VMPFC ROI: desire-for-contact prediction t(648) = 4.97; controlling for happiness/excitement t(644) = 2.12
- **learning_from:** Other (speed-dating partners); romantic acceptance/rejection decisions (yes/no outcomes)
- **learning_about:** Self (own romantic desirability); other (partner's feelings/beliefs about participant)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Rescorla–Wagner (1 α; prediction error δ fit to absolute RT)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Full RL model (RW with PE term)", "family": "Rescorla-Wagner", "n_params": 7, "metric": "likelihood-ratio test"}, {"name": "Reduced model (no learning/PE term)", "family": "linear regression", "n_params": 4, "metric": "likelihood-ratio test"}]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): mean fitted value = 0.22 [S] — governs update of expected probability of receiving "yes" from partners - β₁ (intercept) - β₂ (partner decision) - β₃ (participant decision) - β₄ (match interaction) - β₅ (trial number) - β₆ (absolute prediction error magnitude)
- **social_param:** α (learning rate) — rate at which participants update their expectation of being romantically accepted based on partners' decisions; δ (prediction error) — surprise signal about romantic desirability computed from partner yes/no decisions vs. expected acceptance probability
- **social_param_name:** α
- **social_param_value:** 0.22
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Likelihood-ratio test (χ²(4) = 17.18, p = 0.002, comparing full RL model with reduced model without learning term)
- **how_model_fit:** individual-level-fit (hierarchical/mixed-effects model with fixed and random effects estimated via MLE using fminsearch)
- **data_type_fit_to:** response times (square-root-transformed reaction times for happiness ratings)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — GLM with trial-by-trial RL-derived prediction errors as parametric modulators
- **contrast:** - Yes > No (Match + Unrequited > Rejection + Disinterest): large network including VMPFC, ventral striatum, medial parietal, pSTS/TPJ, DLPFC - Mismatched > Matched (Rejection + Unrequited > Match + Disinterest): left pSTS, left VLPFC - Unsigned prediction error (RL model): RMPFC - Match > Unrequited: posterior cingulate, VMPFC, medial temporal cortex, DLPFC, dorsal caudate - Rejection > Disinterest: rostral ACC - Anticipation: Yes partners > No partners (face phase): lateral occipital, anterior insula, ventral striatum, VMPFC, premotor cortex - No partners > Yes partners (face phase): right TPJ
- **key_regions:** Unsigned PE from RL model in RMPFC; mismatched decisions in left pSTS and left VLPFC; reward value of match in VMPFC and ventral striatum; rejection-specific activation in rostral ACC; anticipation of desired partner in anterior insula and ventral striatum.
- **key_regions_abbrev:** VS, striatum, vmPFC, mPFC, ACC, rACC, STS, insula, AI
- **coordinates_peak:** Table 1 (Yes > No): - Dorsolateral PFC: -21, 26, 53 - Lateral parietal/temporoparietal cortex: -45, -70, 28 - Ventromedial PFC: -3, 38, 15 - Posterior middle temporal gyrus: -54, -49, -7 - Medial parietal cortex: -18, -19, 57 - Rostral medial PFC: -15, 65, 17 - Ventral striatum: 9, 14, -4 - Lateral occipitotemporal junction: 43, -61, -15 - Lateral cerebellum: -42, -64, -25 - Rostral anterior cingulate: 6, 29, 14 - Medial cerebellum: 6, -58, -18 - Lateral cerebellum: 36, -76, -32  Table 2 (Mismatched > Matched): - Posterior superior temporal sulcus: -51, -43, 0 - Ventrolateral PFC: -36, 20, -18  Table 2 (Unsigned PE from RL model): - Rostromedial PFC: 9, 53, 25  Table 3 (Match > Unrequited): - Posterior cingulate: -3, -61, 21 - Posterior cingulate: -3, -34, 39 - Ventromedial PFC: -3, 44, -15 - Medial temporal cortex: -33, -49, 0 - Medial temporal cortex: 33, -34, -4 - Dorsolateral PFC: -21, 32, 42 - Occipito-parietal junction: -33, -70, 35 - Dorsal caudate: 18, -4, 28  Table 3 (Rejection > Disinterest): - Anterior cingulate: 12, 41, 14  Table 4 (Anticipation: Yes > No partners): - Lateral occipital cortex: -36, -82, 0 - Lateral occipital cortex: 39, -79, -14 - Anterior insula: 33, 29, 0 - Medial premotor cortex: 9, 11, 64 - Posterior parietal cortex: 24, -46, 46 - Ventral thalamus: -3, -19, 0 - Ventral striatum: -6, 11, -4 - Medial cerebellum: 6, -43, -43 - Medial cerebellum: -6, -70, -22 - VMPFC: -6, 38, -15 - Medial occipital cortex/posterior cingulate: -6, -73, 21 - Dorsolateral PFC: 48, 8, 18 - Dorsolateral PFC: 39, -4, 46 - Posterior cingulate: 9, -34, 42  Table 4 (No > Yes partners): - Right temporoparietal junction: 54, -55, 28
- **analysis_type:** whole-brain (voxelwise P < 0.001 with FWE-corrected cluster extent; one ROI analysis for VMPFC desire-for-contact correlation)  ---  ## QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 151 total (38 scanned: 18 women, 20 men, ages 19–31, M = 21.47; 113 behavioral-only: 53 men, 60 women, ages 18–32, M = 20.45). fMRI analyses based on N = 38 (one female participant excluded from scanning results due to missing 2 events).
- **population_category:** healthy adults
- **population_age_range:** 19–31
- **ecological_validity:** HIGH — used real face-to-face speed-dating events with genuine romantic decisions followed by fMRI. Partners were real people, not confederates or photographs of strangers. The 50% minimum yes-rate instruction is a minor constraint on ecological validity but sensitivity analyses using continuous desirability ratings confirmed results were robust to this.
- **eligibility_flag:** 
- **concerns:** - The 50% minimum yes-rate instruction may have inflated yes rates and introduced demand characteristics, though authors address this with continuous rating analyses - Scanning sample is relatively small (N = 38) for individual-differences claims - RL model is very simple (single learning rate, no decay, same α for positive and negative PEs) — no model variants tested - Reaction time used as proxy for surprise/cognitive processing is indirect; could also reflect avoidance motivation - Only 2 models compared (full RL vs. reduced without learning term) — limited model space
- **limitations_reported:** Slower reaction times used as index of greater cognitive processing might also indicate avoidance motivation rather than surprise; more focused study needed to disentangle negative emotion and increased cognitive processing; the study is the first of its kind and further studies needed to extend findings.
- **limitations_categorized:** Ambiguous RT interpretation; limited model comparison space; small neuroimaging sample; task simplicity (single RL model)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - learning_mode target: MEDIUM — paper describes learning about both self-desirability and partner's feelings; both are captured but relative emphasis is ambiguous - model_params (β values): LOW — individual β coefficients for the behavioral model are not all reported with fitted values; only α = 0.22 is reported - effect_size: MEDIUM — primary imaging results reported as peak Z-scores from whole-brain maps; no standardized effect sizes (d, r²) for imaging contrasts - coordinates (Table 1, some rows): MEDIUM — OCR artifacts in the .txt file garbled some table entries; coordinates extracted as best as possible from legible portions
- **cannot_find:** - Exact fitted values for β₁–β₆ in the behavioral RL model (only α = 0.22 reported) - Supplement: referenced in paper ("Supplementary material can be found at: http://www.cercor.oxfordjournals.org/") but no supplement file available in the papers folder. Supplementary Figures 1 and 2 referenced but not accessible. - Effect sizes in standardized form (Cohen's d, r², η²) for imaging contrasts — only Z-scores reported - No data or code sharing information
- **other_notes:** The paper mentions supplementary material hosted online (Supplementary Figs 1–2) but no supplement file was available in the papers folder. The .txt conversion has significant OCR artifacts, particularly in table regions and where columns of text were merged (e.g., lines 360–520 are garbled table data). Coordinates were extracted from the cleaner portions of the tables. This is a single-study paper. The RL model is relatively simple — a basic Rescorla-Wagner rule applied to learning one's own general desirability across partners, with prediction errors then used as parametric regressors in the fMRI GLM. The paper makes a strong case for ecological validity through the real speed-dating paradigm.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_social_approval_reward
- tax_topic_mentalizing
- tax_topic_social_approval_reward
