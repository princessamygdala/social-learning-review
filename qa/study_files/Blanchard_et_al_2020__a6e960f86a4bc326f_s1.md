# Blanchard et al. (2020)

- **study_id:** `a6e960f86a4bc326f_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Blanchard, M. A., Belmans, E., Takano, K., & Raes, F. (2020). Remembering happy times instead of sticking to negative memories after social exclusion. *Journal of Behavior Therapy and Experimental Psychiatry*, *68*, 101570. https://doi.org/10.1016/j.jbtep.2020.101570
- **citation_short:** Blanchard et al. (2020)
- **doi:** 10.1016/j.jbtep.2020.101570
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** DepartmentofPsychology,UniversitéCatholiquedeLouvain,PlaceduCardinalMercier,10,B-1348,Louvain-la-Neuve,Belgium; DepartmentofPsychology,ClinicalPsychologyandPsychotherapy,Ludwig-Maximilians-UniversityMunich,Germany; mitations: Doubtsremainregardingwhetherparticipantsfullyunderstoodaction-outcomecontingencies,and; ethods: WeadministeredCyberballto130participantsrandomlyassignedtotheexcludedorincludedcon-; CenterforthePsychologyofLearningandExperimentalPsychopathology,UniversityofLeuven,Belgium; etherparticipantstrulyretrievedmemories,whichcouldhaveaffectedresults; ethis,andweexamineditsconstruct
- **code_url:** https://osf.io/jc2u9/

## Computational level
- **study_focus:** Social exclusion; negative self-referential processing; reversal learning; mood repair
- **study_focus_short:** Social exclusion
- **learning_mode_description:** - Learning mode: Learning from probabilistic reward/punishment feedback about which emotional valence choice (positive vs. negative memory retrieval) is currently rewarded   - Learning from:     - Source type (non-social): world (computerized probabilistic feedback)     - Source content (non-social): outcomes (reward or punishment tokens)   - Learning about:     - Target type (non-social): self (own action-outcome contingency)     - Target content (non-social): action/policy (which valence choice to make to maximize reward)  Note: The social manipulation (Cyberball exclusion) is an experimental condition moderator, not the learning source/target itself. The ERLT learning is non-social in nature -- participants learn from computerized reward/punishment feedback about action-outcome contingencies for memory valence choices.
- **task_description:** After random assignment to social inclusion or exclusion via Cyberball, participants completed an Emotional Reversal Learning Task (ERLT) where they chose between retrieving positive or negative autobiographical memories and received probabilistic reward/punishment feedback (80/20) across three phases with contingency reversals.
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), no social partner during learning task; Cyberball manipulation involves 2 computer-controlled co-players
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Emotional valence labels (positive/negative), memory prompts (matched antonyms, e.g. "calm"/"agitated"), point token feedback (e.g. +/-5 points)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - No evidence that social exclusion affected negative-punished learning rate (t(126.45) = -1.80, p = .07, d = 0.32) - Cyberball manipulation check: excluded participants had lower NTS scores (d = 3.06) and lower mood (d = 1.71) - ERLT manipulation check: significant effect of phase on negative choice frequency (F(2,384) = 14.88, p < .001, eta_p2 = 0.095) - Exploratory: excluded participants learned positive-rewarded association faster than included participants (t(125.87) = -2.33, p = .01, d = 0.41) - No moderation by IDS or CTQ subscales on negative-punished learning rate - No significant correlation between depressive symptoms and learning rates
- **effect_size:** d = 0.32 (exclusion effect on negative-punished alpha, NS); d = 3.06 (NTS Cyberball manipulation check); d = 1.71 (mood Cyberball check); eta_p2 = 0.095 (ERLT phase effect); d = 0.41 (exclusion effect on positive-rewarded alpha); d = 0.95 (acquisition to reversal 1 negative choice shift); d = 0.90 (reversal 1 to reversal 2 negative choice shift)
- **learning_from:** World; probabilistic reward/punishment feedback (point tokens) on valence choices
- **learning_about:** Self; which emotional valence choice (positive vs. negative memory) maximizes reward  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Q-learning with 4 learning rates (alpha_neg-pun, alpha_neg-rew, alpha_pos-pun, alpha_pos-rew; 1 beta)
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [{"name": "1-alpha model (single learning rate)", "family": "Q-learning", "n_params": 2, "metric": "RMSE"}, {"name": "2-alpha model (rewarded vs. punished; did not converge)", "family": "Q-learning", "n_params": 3, "metric": "N/A"}, {"name": "2-alpha model (negative vs. positive; did not converge)", "family": "Q-learning", "n_params": 3, "metric": "N/A"}, {"name": "4-alpha model (neg-pun, neg-rew, pos-pun, pos-rew; winning)", "family": "Q-learning", "n_params": 5, "metric": "RMSE"}]
- **model_mb_mf:** MF
- **model_params:** - alpha_neg-pun: learning rate for negative-punished trials (M = 0.82, SD = 0.10) - alpha_pos-pun: learning rate for positive-punished trials (M = 0.64, SD = 0.20) - alpha_neg-rew: learning rate for negative-rewarded trials (M = 0.25, SD = 0.15) - alpha_pos-rew: learning rate for positive-rewarded trials (M = 0.49, SD = 0.15) - beta (inverse temperature): not reported separately (flagged)
- **social_param:** None. No explicitly social parameter in the Q-learning model. The social manipulation (exclusion) is an external between-subjects factor, not a model parameter.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** RMSE (Root Mean Square Error for observed vs. model-predicted choice responses); 4-alpha RMSE = 0.66 [95% CI: 0.64, 0.67] vs. 1-alpha RMSE = 0.70 [95% CI: 0.69, 0.71]
- **how_model_fit:** hierarchical Bayesian (RStan); individual-level parameters drawn from group-level distribution
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 130 (116 women, 14 men; M_age = 18.7, SD = 1.68; 65 excluded, 65 included); mostly university students
- **population_category:** undergraduates
- **population_age_range:** M=18.7 (SD=1.68)
- **ecological_validity:** Low-moderate. The ERLT uses autobiographical memory retrieval which has ecological validity, but the probabilistic reward/punishment contingency structure is artificial. Cyberball is a validated exclusion paradigm but brief and lacks real social interaction.
- **eligibility_flag:** The social exclusion manipulation (Cyberball) precedes but is not part of the learning task itself. The ERLT learning loop is non-social (computerized feedback on valence choices). The paper examines whether social exclusion moderates non-social reinforcement learning, rather than modeling learning in a social context per se. FLAG: borderline -- social context is a between-subjects manipulation, not integrated into the learning process.
- **concerns:** Two of four models (2-alpha variants) did not converge and were dropped without further analysis. Beta (inverse temperature) parameter not reported with fitted values. No direct check whether participants actually retrieved memories. Near-chance negative choice frequency during acquisition (~51%) suggests possible task comprehension issues. RMSE used as sole model comparison metric rather than information criteria (BIC/AIC).
- **limitations_reported:** Doubts remain regarding whether participants fully understood action-outcome contingencies; did not explicitly check whether participants truly retrieved memories which could have affected results; did not measure rejection sensitivity; physical neglect and physical abuse CTQ subscales had very poor internal consistency (alpha = 0.46 and 0.24 respectively); negative choice frequency during acquisition was close to chance level unlike previous studies
- **limitations_categorized:** task comprehension; no manipulation check for memory retrieval; missing individual difference measure (rejection sensitivity); poor internal consistency of subscales; low task engagement
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.5
- **wc_total:** 4.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - eligibility_flag (MEDIUM): social context is in the Cyberball manipulation, not in the learning task itself -- borderline inclusion - social_param (HIGH): no social parameter exists in the model - beta parameter (MEDIUM): inverse temperature not reported with fitted values - model_comparison (MEDIUM): only 2 of 4 models converged; RMSE used instead of information criteria - winning_model n_params (MEDIUM): paper lists 4 alphas but does not clarify beta or other params explicitly; assumed 5 total (4 alpha + 1 beta)
- **cannot_find:** Beta (inverse temperature) fitted values; explicit number of total free parameters in winning model; details of priors and transformations (referred to Supplementary Materials which are not accessible); code/data availability statement
- **other_notes:** Supplement referenced for parameter estimation details, model construction, priors, and additional exploratory analyses but no supplement file found in the papers folder. The paper's primary finding was null -- social exclusion did not affect NSP disengagement. The exploratory finding (excluded participants learned positive-reward association faster, interpreted as mood repair) was not preregistered. This paper is at the boundary of the inclusion criteria because the learning itself is non-social; the social element is only the Cyberball manipulation that precedes the ERLT.
- **re_extract_flag:** false (full text available; supplement not accessible but main text extraction is complete)

## Taxonomy / categorization (active codes only)
- pop_depression
- pop_healthy_adults
- rr_pop_depression
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = partly
- spec_depth = general
- spec_locus = source
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = social_approval_reward
- tax_rr_secondary_topic = volatility
- tax_rr_topic_social_approval_reward
- tax_rr_topic_volatility
- tax_topic_social_approval_reward
- tax_topic_volatility
