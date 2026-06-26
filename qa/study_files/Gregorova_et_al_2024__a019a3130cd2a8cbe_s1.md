# Gregorova et al. (2024)

- **study_id:** `a019a3130cd2a8cbe_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Gregorova, K., Waltmann, M., Will, G.-J., Mittermeier, S., Kittel-Schneider, S., Bertsch, K., Romanos, M., Bürger, A., Deserno, L., & Reiter, A. M. F. (2024). Young individuals with Borderline Personality Disorder do not learn they are liked and show altered self-esteem reactivity to social feedback. *PsyArXiv*. https://osf.io/jpr3h/overview
- **citation_short:** Gregorova et al. (2024)
- **doi:** LOW — no DOI provided in text; preprint on PsyArXiv with OSF link only
- **publication_type:** preprint
- **year:** 2024.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Department of Psychology, Julius-Maximilians-University of Würzburg, Würzburg, Germany; Department of Child and Adolescent Psychiatry, Psychosomatics and Psychotherapy,; Department of Psychiatry, Psychosomatics and Psychotherapy, University Hospital; Department of Psychiatry and Neurobehavioural Science, University College Cork; ethods: We employed a social evaluation task simulating a social media context; Department of Clinical Psychology, Utrecht University, Utrecht, Netherlands; Center of Prevention Research on Mental Health, Würzburg, Germany; ether they expected Likes or Dislikes; emails
- **code_url:** https://osf.io/jpr3h/overview

## Computational level
- **study_focus:** Social feedback learning and self-esteem updating in Borderline Personality Disorder; how social prediction errors from peer evaluations (Likes/Dislikes) shape expectations of being liked and momentary self-esteem in adolescents/young adults with BPD symptoms.
- **study_focus_short:** Social feedback learning and self-esteem updating in Borderline Personality
- **learning_mode_description:** - Learning mode: Learning from peer social feedback (Likes/Dislikes) about expectations of being liked and own self-esteem   - Learning from:     - Source type (social): other (peers / raters)     - Source content (social): outcome (Like or Dislike feedback on one's social media profile)   - Learning about:     - Target type (social): self     - Target content (social): state (mental state; self-esteem / expectations of being liked)
- **task_description:** In a simulated social media task, participants predicted whether each of 192 color-coded peer raters (varying in benevolence and feedback uncertainty) would Like or Dislike their profile, received feedback, and repeatedly rated their momentary self-esteem on a 0-100 scale.
- **task_paradigm:** Self-evaluation / self-esteem task
- **players:** Single agent (participant), multi-target (192 simulated peer raters; 4 rater types)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Social media-style profiles (photo + personal questions), color-coded avatar raters, thumbs-up/thumbs-down feedback, continuous self-esteem slider
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - BPD predicted being liked significantly less than NCC overall (FE = -0.58, SE = 0.21)   - Group x rater benevolence interaction on predictions of being liked (FE = -0.46, SE = 0.04)   - BPD showed reduced learning to discriminate benevolent from critical raters over trials (3-way interaction benevolence x trials x group: FE = -0.12, SE = 0.05)   - BPD showed increased prediction switching after correctly predicting a Like (3-way interaction: FE = 0.25, SE = 0.04)   - Lower initial expectations (Q0) in BPD for benevolent-uncertain raters (corrected p < 0.001)   - Reduced learning from Likes from benevolent raters in BPD ($\alpha_{Likes\_benevolent}$: corrected p = 0.003; group estimate = -1.03, SE = 0.29)   - Increased learning from Dislikes from benevolent raters in BPD ($\alpha_{Dislikes\_benevolent}$: corrected p = 0.008; group estimate = 0.77, SE = 0.25)   - SPE x rater benevolence x group interaction on self-esteem (FE = -0.83, SE = 0.26)   - BPD self-esteem increased more to unexpected Likes from critical raters   - NCC self-esteem decreased more to unexpected Dislikes from benevolent raters   - Maternal adversity correlated with self-esteem reactivity to Likes from critical raters within BPD (r = 0.661)   - $\alpha_{Likes\_benevolent}$ negatively correlated with psychoticism in BPD (Spearman r = -0.357)
- **effect_size:** - Main Results:   - BPD predicted being liked significantly less than NCC overall (FE = -0.58, SE = 0.21)   - Group x rater benevolence interaction on predictions of being liked (FE = -0.46, SE = 0.04)   - BPD showed reduced learning to discriminate benevolent from critical raters over trials (3-way interaction benevolence x trials x group: FE = -0.12, SE = 0.05)   - BPD showed increased prediction switching after correctly predicting a Like (3-way interaction: FE = 0.25, SE = 0.04)   - Lower initial expectations (Q0) in BPD for benevolent-uncertain raters (corrected p < 0.001)   - Reduced learning from Likes from benevolent raters in BPD ($\alpha_{Likes\_benevolent}$: corrected p = 0.003; group estimate = -1.03, SE = 0.29)   - Increased learning from Dislikes from benevolent raters in BPD ($\alpha_{Dislikes\_benevolent}$: corrected p = 0.008; group estimate = 0.77, SE = 0.25)   - SPE x rater benevolence x group interaction on self-esteem (FE = -0.83, SE = 0.26)   - BPD self-esteem increased more to unexpected Likes from critical raters   - NCC self-esteem decreased more to unexpected Dislikes from benevolent raters   - Maternal adversity correlated with self-esteem reactivity to Likes from critical raters within BPD (r = 0.661)   - $\alpha_{Likes\_benevolent}$ negatively correlated with psychoticism in BPD (Spearman r = -0.357)
- **learning_from:** Other (peers); social feedback (Likes/Dislikes) on one's social media profile
- **learning_about:** Self; own expectations of being liked and momentary self-esteem  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Rescorla-Wagner with direct mapping (no free $\beta$), 4 Q0 (one per rater type), 4 $\alpha$s (2x2: benevolent/critical x Likes/Dislikes). Formula: $Q_{t+1} = Q_t + \alpha \times SPE$, where $SPE = outcome - Q_t$. Choice probability = $Q_t$ (direct mapping).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Model 1: 1 alpha, beta free", "family": "RW", "n_params": 6, "metric": "Exceedance prob = 0.000"},   {"name": "Model 2: 2 alpha (Like/Dislike), beta free", "family": "RW", "n_params": 7, "metric": "Exceedance prob = 0.000"},   {"name": "Model 3: 4 alpha (per rater type), beta free", "family": "RW", "n_params": 9, "metric": "Exceedance prob = 0.000"},   {"name": "Model 4: 8 alpha (rater type x valence), beta free", "family": "RW", "n_params": 13, "metric": "Exceedance prob = 0.000"},   {"name": "Model 5: 2 alpha (benevolent/critical), beta free", "family": "RW", "n_params": 7, "metric": "Exceedance prob = 0.000"},   {"name": "Model 6: 4 alpha (benev/crit x Like/Dislike), beta free", "family": "RW", "n_params": 9, "metric": "Exceedance prob = 0.000"},   {"name": "Model 7: 1 alpha, beta implicit", "family": "RW", "n_params": 5, "metric": "Exceedance prob = 0.000"},   {"name": "Model 8: 2 alpha (Like/Dislike), beta implicit", "family": "RW", "n_params": 6, "metric": "Exceedance prob = 0.000"},   {"name": "Model 9: 4 alpha (per rater type), beta implicit", "family": "RW", "n_params": 8, "metric": "Exceedance prob = 0.000"},   {"name": "Model 10: 8 alpha (rater type x valence), beta implicit", "family": "RW", "n_params": 12, "metric": "Exceedance prob = 0.000"},   {"name": "Model 11: 2 alpha (benevolent/critical), beta implicit", "family": "RW", "n_params": 6, "metric": "Exceedance prob = 0.000"},   {"name": "Model 12 (WINNING): 4 alpha (benev/crit x Like/Dislike), beta implicit", "family": "RW", "n_params": 8, "metric": "Exceedance prob = 1.000, freq = 47.37%"} ]
- **model_mb_mf:** MF
- **model_params:** MEDIUM — only group difference estimates reported on logit-transformed scale; raw mean fitted values per group not provided
- **social_param:** $\alpha_{Likes\_benevolent}$ and $\alpha_{Dislikes\_benevolent}$ — learning rates capturing asymmetric updating from social feedback (Likes vs. Dislikes) specifically from benevolent peer raters, which showed significant BPD vs. NCC group differences. Also $Q_{0,benevolent\_uncertain}$ — initial expectation of being liked by benevolent-uncertain raters, significantly lower in BPD.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Random-effects Bayesian model selection (CBM Toolbox); exceedance probability and protected exceedance probability
- **how_model_fit:** individual-level-fit (hierarchical Bayesian MAP estimation via CBM Toolbox)
- **data_type_fit_to:** choice behavior (binary predictions of Like vs. Dislike)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 122 (55 BPD, 67 NCC); ages 13-25 (BPD mean = 18.40, SD = 2.47; NCC mean = 18.55, SD = 2.69); predominantly female (50 women + 4 transgender men + 1 man in BPD; 64 women + 2 men in NCC). MOPS data missing for n = 28; BSCL data missing for n = 5.
- **population_category:** mixed
- **population_age_range:** 13–25
- **ecological_validity:** Task simulates a social media context (Likes/Dislikes on a profile), which has some ecological relevance for youth, and authors cite evidence linking task self-esteem dynamics to real-world self-esteem dynamics. However, it remains a lab/online task with pre-programmed raters and no real social interaction. Cover story debriefed immediately. Task perceived as moderately realistic (mean 59.25/100).
- **eligibility_flag:** 
- **concerns:** - Preprint, not yet peer-reviewed at time of posting. - Mean fitted parameter values on the original (untransformed) scale are not reported; only group comparison estimates on logit-transformed scale are provided. - No parameter recovery or model recovery analyses reported. - MOPS data missing for 28 participants (23% of sample), reducing power for family adversity analyses. - Cross-sectional design limits causal inference about developmental pathways.
- **limitations_reported:** The cross-sectional design of the study and the retrospective assessment of family adversity do not allow for inference regarding the developmental pathways from early family experiences to current self-esteem reactivity"; "our experimental task remains an artificial setting that might not fully capture the complexity of real-life social interactions, even though we recently demonstrated that self-esteem dynamics in this task are associated with real-word self-esteem dynamics in young individuals
- **limitations_categorized:** limited ecological validity; cross-sectional design; retrospective self-report measures; task simplicity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** - Mean fitted parameter values (untransformed) for each group separately - DOI - Preregistration status
- **other_notes:** - No supplement file found separately; supplement is appended to the main text file (starting at line 744). - Paper is a preprint posted on PsyArXiv. The article states "The article has been posted on PsyArXiv preprint server." - Self-esteem dynamics modeled via linear mixed-effects models with SPEs as predictors (not a separate computational model), which is appropriate for the research question. - The RL model is fitted to binary choice data (prediction of Like vs. Dislike), and SPEs are then extracted and used as regressors in a separate mixed-effects model predicting self-esteem ratings. - The task is based on Will et al. (2017, 2020) social evaluation paradigm. - Data and code publicly available at OSF.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_bpd
- rr_pop_adolescents
- rr_pop_bpd
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_clinical
- tax_popclass_developmental
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = self_esteem
- tax_rr_secondary_topic = social_approval_reward
- tax_rr_topic_self_esteem
- tax_rr_topic_social_approval_reward
- tax_topic_self_esteem
- tax_topic_social_approval_reward
