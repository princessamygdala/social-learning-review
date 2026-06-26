# Zhang et al. (2025)

- **study_id:** `a00e7bc280f881edb_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Zhang, S., FeldmanHall, O., Hétu, S., & Otto, A. R. (2025). Advantageous and disadvantageous inequality aversion can be taught through learning of others' preferences. *eLife*, *14*, e102800. https://doi.org/10.7554/eLife.102800
- **citation_short:** Zhang et al. (2025)
- **doi:** 10.7554/eLife.102800
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ether social behaviours promoting egalitarianism can be learned, even when implementing; Institute for Brain Research, Beijing Normal University, Beijing, China; 2Department; divisions of resources because doing so entails a sacrifice of one’s own benefit; Department of Psychology, Université de Montréal, Montréal, Canada; 6Centre; Institute for Brain Sciences, Brown University, Providence, United States;; ether individuals subsequently increase their punishment unfairly after; Laboratory of Cognitive Neuroscience and Learning & IDG/McGovern; Department of Psychology, McGill University, Montré
- **code_url:** https://osf.io/6xn5b

## Computational level
- **study_focus:** Observational learning of fairness norms / inequality aversion contagion (advantageous and disadvantageous)
- **study_focus_short:** Observational learning of fairness norms / inequality aversion contagion
- **learning_mode_description:** - Learning mode: Learning another's inequality-averse punishment preferences through observing and implementing their accept/reject decisions in an Ultimatum Game   - Learning from:     - Source type (social): other (Teacher)     - Source content (social): action/policy (Teacher's preferred accept/reject responses to offers)   - Learning about:     - Target type (social): other (Teacher)     - Target content (social): state (mental state; latent fairness preferences — envy and guilt parameters)
- **task_description:** Participants played a modified Ultimatum Game across three phases. In the Baseline and Transfer phases, they acted as Receiver responding to offers ranging from extreme disadvantageous to extreme advantageous inequity. In the Learning phase, they acted as a third-party agent deciding on behalf of a Teacher (Receiver), receiving trial-by-trial feedback about the Teacher's preferred response.
- **task_paradigm:** Ultimatum game
- **players:** Single agent (participant), dyadic (Teacher as observed partner; fictitious Proposers). Between-subjects: Adv-Dis-I-Averse condition (N=100) vs. Dis-I-Averse condition (N=100).
- **n_players:** network (5+)
- **partner_type:** human (live)
- **stimuli:** Monetary offer splits in Ultimatum Game (90:10, 70:30, 50:50, 30:70, 10:90 with jitter), text-based feedback (Teacher's preferred accept/reject), fairness ratings (1-7 scale)
- **method:** online / behavioural
- **method_full:** behavioural / online (Amazon Mechanical Turk)
- **main_result:** - Main Results:   - Participants exposed to Adv-Dis-I-Averse Teacher increased rejection of 30:70 Adv-I offers relative to Dis-I-Averse condition (β = 0.10, SE = 0.04)   - Participants exposed to Adv-Dis-I-Averse Teacher increased rejection of 10:90 Adv-I offers relative to Dis-I-Averse condition (β = 0.15, SE = 0.04)   - Fairness ratings for 30:70 offers changed more in Adv-Dis-I-Averse condition (β = −0.86, SE = 0.17)   - Fairness ratings for 10:90 offers changed more in Adv-Dis-I-Averse condition (β = −1.04, SE = 0.17)   - Learning phase: larger increase in rejection rates for Adv-I 30:70 offers in Adv-Dis-I-Averse condition (β = 0.77, SE = 0.24)   - Learning phase: larger increase in rejection rates for Adv-I 10:90 offers in Adv-Dis-I-Averse condition (β = 1.10, SE = 0.33)   - Preference Inference model best fit (lowest AIC across 7 models)
- **effect_size:** Standardized regression coefficients (β) from mixed-effects logistic/linear models reported above. No Cohen's d, r, or η² reported.
- **learning_from:** Other (Teacher); Teacher's preferred accept/reject feedback on Ultimatum Game offers
- **learning_about:** Other (Teacher); Teacher's latent inequality aversion preferences (envy for Dis-I, guilt for Adv-I)  ---  #### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Preference Inference model (Fehr-Schmidt utility with trial-by-trial updating of α [envy] and β [guilt]; 4 params: α₀, β₀, η, τ)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** 1. {"name": "Random Choosing", "family": "Null/baseline", "n_params": 5, "metric": "AIC"} 2. {"name": "Static Preference (Fehr-Schmidt)", "family": "Utility function (Fehr-Schmidt)", "n_params": 3, "metric": "AIC"} 3. {"name": "Basic RL", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AIC"} 4. {"name": "Offer-Sensitive RL", "family": "Rescorla-Wagner (separate LRs per offer)", "n_params": 6, "metric": "AIC"} 5. {"name": "Offer-Sensitive RL with Separate Initial Values", "family": "Rescorla-Wagner (separate LRs + initial values)", "n_params": 7, "metric": "AIC"} 6. {"name": "Preference Inference", "family": "Fehr-Schmidt + delta updating", "n_params": 4, "metric": "AIC"} **[WINNING]** 7. {"name": "Similarity RL", "family": "Rescorla-Wagner with Gaussian generalization", "n_params": 4, "metric": "AIC"}
- **model_mb_mf:** MB (model-based — infers latent structure of Teacher's preferences rather than learning action values)
- **model_params:** - α₀: initial envy parameter (Dis-I aversion), range [0, 10] - β₀: initial guilt parameter [S] (Adv-I aversion), range [0, 10] - η: learning rate for updating α and β, range [0, 5] - τ: inverse temperature (softmax), governs decision noise  Mean fitted values: Not reported in main text. Noted in Supplementary file 1H (supplement not accessible).
- **social_param:** β (guilt) — captures the Teacher's aversion to advantageous inequity; α (envy) — captures aversion to disadvantageous inequity. Both are social parameters [S] as they represent inferred preferences of another agent (the Teacher).
- **social_param_name:** β
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 0–10
- **model_comparison_metric:** AIC (Akaike Information Criterion)
- **how_model_fit:** individual-level-fit (MLE with 100 random start points per participant)
- **data_type_fit_to:** choice behavior (accept/reject decisions in Learning phase)  ---  #### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging)  ---  #### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 200 (100 per condition: Adv-Dis-I-Averse and Dis-I-Averse); M age = 37.53 (SD = 10.88); 75 females. US-based, recruited via Amazon Mechanical Turk.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate. Online Ultimatum Game with fictitious proposers and a single anonymous Teacher. No real social interaction; offers were predetermined. Monetary stakes present but task is highly abstracted from real-world fairness contexts.
- **eligibility_flag:** 
- **concerns:** - No "pure" control condition (no-feedback or random-feedback teacher) in this study; both conditions expose participants to some form of inequity-averse Teacher, making it difficult to disentangle learning vs. baseline drift - Offers were predetermined (not from real participants), raising ecological validity concerns - Mean fitted parameter values not reported in main text (stated to be in Supplementary file 1H, which is not separately accessible) - Effect sizes reported only as unstandardized β from mixed-effects models; no standardized effect sizes (d, r, η²)
- **limitations_reported:** Conclusions are based on comparison between two conditions that both expose participants to inequity-averse Teachers, so Dis-I-Averse condition may not provide a "pure" assessment of default tendency; previous work with random-preference teacher found little spontaneous change, but stricter controls needed; only one Teacher with no meaningful identity or social attributes; future work should examine teacher identity and number of teachers; social contagion effects may require repeated interactions with the same individual.
- **limitations_categorized:** limited control condition; limited ecological validity; single social partner; no identity/group manipulation; task simplicity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.5
- **wc_total:** 8.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** yes
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = structural
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_C_exchange_interdependence
- tax_mod_action_observation
- tax_mod_vicarious_outcome
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_bayesian
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = fairness_inequity
- tax_rr_secondary_topic = norm_conformity
- tax_rr_topic_fairness_inequity
- tax_rr_topic_norm_conformity
- tax_topic_fairness_inequity
- tax_topic_norm_conformity
