# Li et al. (2023)

- **study_id:** `a224dcce611192bff_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Li, S., Huang, G., Ma, Z., & Qu, C. (2023). Superior bias in trust-related decisions. *Current Psychology*, *42*, 24822–24836. https://doi.org/10.1007/s12144-022-03567-0
- **citation_short:** Li et al. (2023)
- **doi:** 10.1007/s12144-022-03567-0
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** Faculty of Education, Northeast Normal University, spectives, their degree of trust in superiors may be related; Laboratory of Mental Health and Cognitive Science, in the daily working life between employees and superiors; Laboratory of Brain, Cognition and Education Sciences, leadership and organizational performance; University, Guangzhou 510631, China (Dahlhaus & Schlösser, 2021); School of Nursing, Peking Union Medical College, No; School of Psychology, Center; emails: zhenlingma@163.com, fondest@163.com
- **code_url:** 

## Computational level
- **study_focus:** Trust learning; effect of social status (hierarchy) on baseline trust in one-shot trust game
- **study_focus_short:** Trust learning
- **learning_mode_description:** - Learning mode: No learning over time -- one-shot trust decisions based on social status prior only   - Learning from:     - Source type (social): other (partner/trustee)     - Source content (social): stimulus (social status label)   - Learning about:     - Target type (social): other (partner/trustee)     - Target content (social): state (mental state; trustworthiness)
- **task_description:** Participants played a one-shot trust game as trustors with 40 different partners (faces labeled as high- or low-status). They decided how much of 10 yuan to share with each partner, with no feedback about reciprocity.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (40 partners; 20 high-status, 20 low-status)
- **n_players:** multi-target (3+)
- **partner_type:** human (recorded)
- **stimuli:** Grayscale male face photographs from CAS-PEAL database, text labels ("high-status" / "low-status"), monetary endowment (10 yuan)
- **method:** online / behavioural
- **method_full:** behavioural (online)
- **main_result:** - Participants invested more in high-status partners (M = 3.70) than low-status partners (M = 3.24) (d = 0.389) - No significant difference in trustworthiness ratings between high-status (M = 4.40) and low-status (M = 4.49) partners (d = -0.106)
- **effect_size:** Cohen's d = 0.389 (share amount); Cohen's d = -0.106 (trustworthiness rating, n.s.)
- **learning_from:** other (partner); social status label as social prior
- **learning_about:** other (partner); trustworthiness / investment decision  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** N/A -- no computational model in Experiment 1
- **model_family:** Rescorla-Wagner
- **model_class:** Other
- **all_models_tested:** 
- **model_mb_mf:** 
- **model_params:** 
- **social_param:** 
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** 
- **how_model_fit:** 
- **data_type_fit_to:** N/A  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging)  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 112 (69 females; aged 26.92 +/- 7.77 years; 131 recruited, 19 excluded for incomplete task); online study
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low -- artificial social status manipulation via labels on faces; online paradigm; one-shot game with no real interaction
- **eligibility_flag:** Does not meet "learning over time" criterion -- one-shot trust game with no feedback and no learning/updating process. No computational modeling. Flag: no temporal learning, no computational model.
- **concerns:** One-shot paradigm with no learning component; no computational modeling; serves as behavioral baseline only. Social status manipulation via text labels is artificial.
- **limitations_reported:** More evidence is needed to support this view"; "learning is a complex process that is not solely motivated by information updating"; "other phases of learning may also be affected by prior knowledge of social statuses, such as information collection and integration
- **limitations_categorized:** limited ecological validity; task simplicity; limited generalizability
- **preregistered:** No
- **wc_rule1:** 
- **wc_rule2:** 
- **wc_rule3:** 
- **wc_rule4:** 
- **wc_rule5:** 
- **wc_rule6:** 
- **wc_rule7:** 
- **wc_rule8:** 
- **wc_rule9:** 
- **wc_rule10:** 
- **wc_score:** 0
- **wc_total:** 0.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** winning_model (N/A -- no modeling); all algorithmic fields (N/A); eligibility_flag (no learning over time, MEDIUM confidence)
- **cannot_find:** N/A -- all relevant fields extracted
- **other_notes:** Experiment 1 is a baseline behavioral study only. Computational modeling is applied in Experiments 2, 3a, and 3b.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_domain_D_group_structure_identity
- tax_mod_experiential
- tax_mod_instructed
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_bonus
- tax_rr_primary_topic = trust
- tax_rr_secondary_topic = social_hierarchy
- tax_rr_topic_social_hierarchy
- tax_rr_topic_trust
- tax_topic_social_hierarchy
- tax_topic_trust
