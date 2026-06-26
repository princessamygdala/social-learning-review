# Pinho et al. (2024)

- **study_id:** `a87df681de092cd6d_s3`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** da Silva Pinho, A., Céspedes Izquierdo, V., Lindström, B., & van den Bos, W. (2024). Youths' sensitivity to social media feedback: A computational account. *Science Advances*, *10*, eadp8775. https://doi.org/10.1126/sciadv.adp8775
- **citation_short:** Pinho et al. (2024)
- **doi:** 10.1126/sciadv.adp8775
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** department of Psychology, University of Amsterdam, Amsterdam, netherlands; mitations in the literature, it is cru-; ether, these findings highlight the; mpirical evidence is lacking; mitation in the field (27,; ether, these results sup-; mit on the posting rate)
- **code_url:** https://osf.io/mt2nv/

## Computational level
- **study_focus:** Neural correlates of social media feedback sensitivity; associations between brain volume (subcortical/cortical regions) and individual differences in sensitivity to social media feedback (RL learning rate) in emerging adults.
- **study_focus_short:** Neural correlates of social media feedback sensitivity
- **learning_mode_description:** - Learning mode: Learning from social media feedback (likes) about posting behavior, with neural structural correlates   - Learning from:     - Source type (social): group (anonymous social media audience)       - Source content (social): outcome (number of likes on Instagram posts)   - Learning about:     - Target type (non-social): self       - Target content (non-social): action/policy (posting latency / engagement policy)
- **task_description:** Emerging adults provided their historical Instagram trace data (spanning ~5.74 years of use), underwent structural MRI, and completed questionnaires on social anxiety and problematic social media use. The RL model was fit to their Instagram data to extract learning rates, which were then related to brain region volumes using random forest analyses.
- **task_paradigm:** Social media (likes) task
- **players:** Single agent (participant/Instagram user), multi-target (anonymous social media audience)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Real Instagram posts and likes (historical trace data); structural MRI scans
- **method:** fMRI / behavioural
- **method_full:** behavioural + structural MRI (not fMRI; structural brain volume analysis)
- **main_result:** - Several subcortical regions predicted social feedback sensitivity (alpha): amygdala, ventral diencephalon, pallidum, putamen, plus cortical regions - Amygdala was the only region associated with all three constructs: social feedback sensitivity, social anxiety, and problematic social media use - RL model fit better than null model (AIC = 67,390 vs. 69,880)
- **effect_size:** Not reported as standard effect sizes; feature permutation importance coefficients from random forest analyses (see Tables S8-S10 in supplement); specific values not extractable from text.
- **learning_from:** group (anonymous audience); social feedback (likes on Instagram posts over ~5.74 years)
- **learning_about:** self; own posting policy/engagement behavior (with brain volume correlates)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** RL foraging model (same as Study 1; 3 params: alpha, C, rho) fit to historical Instagram trace data
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Null model", "family": "null/baseline", "n_params": 1, "metric": "AIC"} - {"name": "RL model", "family": "Rescorla-Wagner (average reward rate)", "n_params": 3, "metric": "AIC"}
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate) [S]: sensitivity to social feedback. M = 0.0004 in this sample of emerging adults - C (effort cost sensitivity) - rho (initial policy)
- **social_param:** alpha (learning rate) [S] — sensitivity to social media feedback; used as the dependent variable in random forest brain volume analyses
- **social_param_name:** alpha
- **social_param_value:** 0.0004
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC
- **how_model_fit:** individual-level-fit (MLE per user)
- **data_type_fit_to:** choice behavior (posting latencies from historical Instagram trace data)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (structural MRI volumetry, not functional MRI)
- **contrast:** N/A (no functional contrasts; structural brain volume analysis using random forest regression with LOOCV)
- **key_regions:** Social feedback sensitivity (alpha) predicted by amygdala, ventral diencephalon, pallidum, putamen volumes. Amygdala uniquely associated with all three constructs (alpha, social anxiety, problematic social media use). Additional cortical regions also identified (see Fig. 4A).
- **key_regions_abbrev:** putamen, amygdala
- **coordinates_peak:** unavailable — not in main text or supplement (structural volumetric analysis used Desikan-Killiany atlas parcellations, not peak coordinates)
- **analysis_type:** ROI (Desikan-Killiany atlas regions; 83 brain regions extracted via FreeSurfer; random forest with leave-one-out cross-validation)  ---  ### QUALITY
- **analysis_type_clean:** ROI
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 96 (emerging adults aged 18-24; reduced from 106 after exclusion of those with <10 posts); 11,277 Instagram posts; structural MRI from 3T Philips Achieva scanner. For random forest analyses: n = 76 (learning rate) and n = 84 (social anxiety, problematic media use) due to further data availability.
- **population_category:** mixed
- **population_age_range:** 18–24
- **ecological_validity:** High for trace data component (real historical Instagram data spanning ~5.74 years). Structural MRI provides a static snapshot of brain volume, limiting causal interpretation. Cross-sectional design prevents developmental inferences.
- **eligibility_flag:** 
- **concerns:** Exploratory analyses — no preregistration for Study 3. Cross-sectional design cannot establish whether brain volume differences cause or result from social media feedback sensitivity. Small sample for random forest analyses (n = 76 for alpha). Learning rates were winsorized before random forest analysis. Brain data collected at ages 18-24 but Instagram data spans from age ~14 onward, creating a temporal mismatch. The same RL model as Study 1 was used without additional model development.
- **limitations_reported:** We emphasize that we focused on individual differences in normative social anxiety rather than on clinical cases"; "future research should include fine-grained developmental windows and longitudinal data"; results "do not imply direct causation"; brain processes "were also associated with distinct networks of regions" beyond amygdala.
- **limitations_categorized:** cross-sectional design; limited generalizability (non-clinical sample); small sample size (for brain analyses); exploratory (not preregistered); no causal inference
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Partial
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** yes
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - Study 2 eligibility: MEDIUM confidence — model was used for simulations only, not fit to Study 2 data - Study 3 coordinates: LOW confidence — no MNI coordinates available (structural volumetric analysis, not voxel-based) - Study 1 age estimates: MEDIUM confidence — participant ages estimated via automated heuristics, not self-reported - Effect sizes for Study 3: LOW confidence — random forest importance coefficients reported but not standard effect sizes - Model formula: MEDIUM confidence — exact mathematical formula not written out in full in the paper; described verbally and in Figure 1 caption (policy update based on alpha, delta, and change in posting latency)
- **cannot_find:** - Exact mathematical formula for the RL model (described verbally and in figure caption but not as a formal equation in the text; based on Lindström et al., 2021) - MNI peak coordinates (structural volumetric analysis used atlas parcellations) - Standard effect sizes for Study 3 brain-behavior associations - Specific AIC values for Study 1 RLd model comparisons between age groups separately (Table S1 has values but only total AIC reported in supplement text)
- **other_notes:** This paper builds on and extends Lindström et al. (2021) RL model of social media engagement. The same computational framework is applied across all three studies. The mood-RL model in Study 2 (m(t+1) = m(t) + eta(t) * (delta(t) - m(t))) draws on Rutledge et al. (2014) and Eldar & Niv (2015) but was used only for simulation, not model fitting. Studies 1 and 2 were preregistered; Study 3 was exploratory. Data and code are available at https://osf.io/m7hw6/.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = shared
- spec_source = social
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_topic_social_approval_reward
