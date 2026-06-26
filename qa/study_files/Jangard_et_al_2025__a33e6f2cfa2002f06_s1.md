# Jangard et al. (2025)

- **study_id:** `a33e6f2cfa2002f06_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Jangard, S., Lindström, B., Khemiri, L., Jayaram-Lindström, N., & Olsson, A. (2025). Dissociating social reward learning and behavior in alcohol use disorder. *Translational Psychiatry*, *15*, 30. https://doi.org/10.1038/s41398-025-03236-3
- **citation_short:** Jangard et al. (2025)
- **doi:** 10.1038/s41398-025-03236-3
- **publication_type:** peer-reviewed journal (confidence: high)
- **year:** 2025.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** CentreforPsychiatryResearch,DepartmentofClinicalNeuroscience,KarolinskaInstitutet&StockholmHealthCareServices,RegionStockholm,Stockholm,Sweden; ETHODS:Weconducted one laboratory study (n=234)andone confirmatory online study (n=258),comparing youngadults; ethatprosocialdeficitsinAUDandrelateddisorders Americanonlinestudycomprising123individualswithAUD(51%males),; ether,theseresultsindicatethatrewardprocessesmaynotberelevantforunderstandingcompromisedsocialbehaviorinAUD; Department of Clinical Neuroscience, Karolinska Institutet, Stockholm, Sweden; Department of Medical Epidemiology and Biostati
- **code_url:** https://osf.io/25d8c/

## Computational level
- **study_focus:** Prosocial learning -- whether individuals with alcohol use disorder (AUD) show deficits in learning to maximize rewards for another person compared to self, and whether prosocial learning relates to prosocial behavior. (Confidence: HIGH)
- **study_focus_short:** Prosocial learning -- whether individuals with alcohol use disorder (AUD) show
- **learning_mode_description:** - Learning mode: Learning from one's own choice outcomes (reward/no reward) about stimulus-reward contingencies to maximize reward for another person (prosocial) or for oneself (self) or for no one (control).   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (reward feedback -- 100 points or 0)   - Learning about:     - Target type (social): other (anonymous interaction partner) [prosocial condition]     - Target type (non-social): self [self condition]; no one [control condition]     - Target content (non-social): stimulus (stimulus-reward contingencies / which symbol is more rewarding)  (Confidence: HIGH)
- **task_description:** Participants chose between two abstract symbols over 48 trials per condition (prosocial, self, no one; 144 total), where one symbol was rewarded 75% of the time and the other 25%, to maximize points for another participant, themselves, or no one. Prosocial behavior was additionally measured via a dictator game and self-report altruism scale. (Confidence: HIGH)
- **task_paradigm:** Dictator game
- **players:** Single agent (participant), single-target (anonymous interaction partner, deceptive cover story). (Confidence: HIGH)
- **n_players:** single agent (1)
- **partner_type:** human (live)
- **stimuli:** Abstract symbols (Agathodaimon font letters), binary feedback (100 points or 0 points). (Confidence: HIGH)
- **method:** online / behavioural
- **method_full:** Behavioural (laboratory + online replication). (Confidence: HIGH)
- **main_result:** - No effect of AUD on prosocial learning (Lab: chi-squared = 0.82, p = .665; Online: chi-squared = 3.03, p = .220) - No Group x Condition interaction on choice (Lab: chi-squared = 0.82, p = .665; Online: chi-squared = 3.03, p = .220) - No effect of AUD on main effect of choice (Lab: chi-squared = 0.08, p = .781; Online: chi-squared = 2.49, p = .114) - No Group x Trial x Condition interaction on learning speed (Lab: chi-squared = 4.20, p = .122; Online: chi-squared = 4.43, p = .109) - No association between prosocial learning and prosocial behavior (dictator game: Lab chi-squared = 0.07, p = .963; Online chi-squared = 0.16, p = .924) - No group difference in learning rate alpha (Lab: W = 7353, p = .325; Online: W = 7173, p = .060) - No group difference in temperature beta (Lab: W = 6726, p = .823; Online: W = 7806, p = .407) - Two-parameter model best fit (Lab: delta-BIC > 22.60; Online: delta-BIC > 22.08; BIC weight Model 1: Lab = .956, Online = .953)
- **effect_size:** LOW confidence -- no standardized effect sizes (Cohen's d, r, eta-squared) reported anywhere; only chi-squared and W statistics
- **learning_from:** Self; own reward outcome on chosen symbol. (Confidence: HIGH)
- **learning_about:** Stimulus-reward contingencies; reward maximization for other (prosocial), self, or no one. (Confidence: HIGH)
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** RW (1 alpha, 1 beta -- same across prosocial, self, and no one conditions). Q(t+1)(a) = Q(t)(a) + alpha * [r(t) - Q(t)(a)]; softmax action selection with temperature beta. (Confidence: HIGH)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Model 1 (1 alpha, 1 beta)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"} 2. {"name": "Model 2 (3 alpha, 1 beta)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BIC"} 3. {"name": "Model 3 (3 alpha, 3 beta)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "BIC"}  (Confidence: HIGH)
- **model_mb_mf:** MF (Confidence: HIGH)
- **model_params:** - alpha (learning rate): mean = 0.30 (lab), 0.18 (online) -- shared across conditions - beta (inverse temperature / softmax temperature): mean = 0.69 (lab), 0.77 (online) -- shared across conditions - No parameter is specifically social [S] in the winning model, since the winning model uses the same parameters across all conditions.  (Confidence: HIGH)
- **social_param:** None in winning model -- the winning model has identical parameters for prosocial and self conditions, meaning no parameter differentiates social from non-social learning. The losing Model 2 (3 alpha, 1 beta) would have had separate alpha_prosocial [S], alpha_self, alpha_noone. (Confidence: HIGH)
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (also reported AIC, LL); BIC weights (conditional probability). (Confidence: HIGH)
- **how_model_fit:** Individual-level fit (parameters estimated per participant). (Confidence: HIGH)
- **data_type_fit_to:** Choice behavior. (Confidence: HIGH)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (Confidence: HIGH)
- **contrast:** N/A (Confidence: HIGH)
- **key_regions:** N/A (Confidence: HIGH)
- **coordinates_peak:** N/A -- no neuroimaging. (Confidence: HIGH)
- **analysis_type:** N/A (no neuroimaging) (Confidence: HIGH)  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Study 1 (Lab): N = 234 (119 AUD, 115 HC); Study 2 (Online): N = 258 (123 AUD, 135 HC). Total N = 492. Ages 18-24. (Confidence: HIGH)
- **population_category:** clinical
- **population_age_range:** 18–24
- **ecological_validity:** Limited -- the prosocial learning task uses abstract symbols with a deceptive cover story about an anonymous partner; no real social interaction occurs. The task is a standard probabilistic RL task with a prosocial framing, not a naturalistic social interaction. However, the dictator game provides a complementary behavioral measure, and the two-study design (lab + online replication) strengthens external validity. (Confidence: HIGH)
- **eligibility_flag:** 
- **concerns:** - The "social" aspect is minimal: participants learn stimulus-reward contingencies identically whether rewards go to self, other, or no one. The winning model shows identical learning mechanisms across conditions, raising the question of whether this truly captures "social learning" vs. reward learning with a social framing. - No standardized effect sizes reported (no Cohen's d, no r); only chi-squared and Wilcoxon W. - Deceptive paradigm -- participants told they were playing with a real partner but were not. - High rate of non-learners, especially in online sample (74/258 = 28.7%). - Code/data available only "upon reasonable request" rather than openly shared.  (Confidence: HIGH)
- **limitations_reported:** Young adult sample (18-24) limits generalizability to older AUD populations where executive function deficits are more pronounced; heterogeneity between lab and online samples may limit generalizability; the task is model-free learning only and does not account for model-based learning mechanisms relevant to AUD; no environmental volatility, which has been shown to be relevant for identifying learning deficits in AUD and social learning in other psychiatric groups. (Confidence: HIGH)
- **limitations_categorized:** Limited generalizability (age range); limited generalizability (cross-sample heterogeneity); task simplicity (model-free only, no model-based component); task simplicity (no volatility); limited ecological validity. (Confidence: HIGH)
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_addiction
- pop_healthy_adults
- rr_pop_addiction
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = general
- spec_locus = source+target
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_topic_prosocial_altruism
