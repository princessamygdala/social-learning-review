# Zhang et al. (2025)

- **study_id:** `a00e7bc280f881edb_s2`
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
- **study_focus:** Generalization of learned inequality aversion — testing whether inferred fairness preferences transfer to novel offer types not experienced during learning
- **study_focus_short:** Generalization of learned inequality aversion
- **learning_mode_description:** - Learning mode: Learning and generalizing another's inequality-averse punishment preferences from moderate offers to extreme offers   - Learning from:     - Source type (social): other (Teacher)     - Source content (social): action/policy (Teacher's preferred accept/reject for moderate offers only — 70:30 and 30:70)   - Learning about:     - Target type (social): other (Teacher)     - Target content (social): state (mental state; latent fairness preferences — envy and guilt parameters, generalized across offer types)
- **task_description:** Same three-phase Ultimatum Game as Experiment 1, but in the Learning phase, feedback was provided only for moderate offers (70:30 and 30:70), not extreme offers (90:10 and 10:90). This tests whether participants generalize inferred Teacher preferences to unseen offer types.
- **task_paradigm:** Ultimatum game
- **players:** Single agent (participant), dyadic (Teacher; fictitious Proposers). Between-subjects: Adv-Dis-I-Averse (N=100, 97 analyzed) vs. Dis-I-Averse (N=100, 97 analyzed).
- **n_players:** network (5+)
- **partner_type:** human (live)
- **stimuli:** Same as Experiment 1 (monetary offer splits, text feedback, fairness ratings), but extreme offers in Learning phase had no Teacher feedback.
- **method:** online / behavioural
- **method_full:** behavioural / online (Amazon Mechanical Turk)
- **main_result:** - Main Results:   - Generalization to extreme Adv-I (10:90) offers: participants in Adv-Dis-I-Averse condition increased rejection rates more than Dis-I-Averse condition (β = 0.12, SE = 0.04)   - No difference between conditions for extreme Dis-I (90:10) rejection rate changes (β = −0.05, SE = 0.04)   - Fairness ratings for extreme Adv-I (10:90) offers changed more in Adv-Dis-I-Averse condition (β = −0.97, SE = 0.18)   - No difference in fairness rating changes for extreme Dis-I (90:10) between conditions (β = 0.06, SE = 0.18)   - Learning phase: rejection rates for 10:90 Adv-I offers increased more in Adv-Dis-I-Averse condition (β = 0.81, SE = 0.26)   - Preference Inference model again provided best fit (lowest AIC across 5 models tested)
- **effect_size:** MEDIUM — only unstandardized β from mixed-effects models provided; no standardized effect sizes.  ### CANNOT FIND - Mean fitted parameter values for winning model (both experiments) — referenced as Supplementary file 1H and 1L - Exact AIC values per model — in supplement tables - Whether study was preregistered  ### OTHER NOTES - Published in eLife (2025), Version of Record December 2025. Originally posted as preprint August 2024. - Data and code publicly available at OSF (https://osf.io/6xn5b). - The Preference Inference model is conceptually related to Bayesian theory of mind but implemented as a delta-rule updater on Fehr-Schmidt parameters rather than full Bayesian inference. - The paper explicitly notes that the Preference Inference model's ability to generalize (update latent parameters from moderate offers that apply to extreme offers) is what distinguishes it from RL models, which are offer-specific. - No neuroimaging data in either experiment. - No supplement file found in the papers folder (only main PDF and .txt).
- **learning_from:** Other (Teacher); Teacher's preferred feedback on moderate Ultimatum Game offers only
- **learning_about:** Other (Teacher); Teacher's generalized latent inequality aversion preferences  ---  #### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Preference Inference model (same as Experiment 1: Fehr-Schmidt utility with trial-by-trial updating of α and β; 4 params)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** 1. {"name": "Random Choosing", "family": "Null/baseline", "n_params": 5, "metric": "AIC"} 2. {"name": "Static Preference (Fehr-Schmidt)", "family": "Utility function", "n_params": 3, "metric": "AIC"} 3. {"name": "Offer-Sensitive RL with Separate Initial Values", "family": "Rescorla-Wagner", "n_params": 7, "metric": "AIC"} 4. {"name": "Preference Inference", "family": "Fehr-Schmidt + delta updating", "n_params": 4, "metric": "AIC"} **[WINNING]** 5. {"name": "Similarity RL", "family": "Rescorla-Wagner with Gaussian generalization", "n_params": 4, "metric": "AIC"}
- **model_mb_mf:** MB
- **model_params:** Same as Study 1 (α₀, β₀, η, τ). Mean fitted values in Supplementary file 1L (not accessible).
- **social_param:** Same as Study 1: β (guilt) [S], α (envy) [S]
- **social_param_name:** Same as Study 1
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC
- **how_model_fit:** individual-level-fit (MLE, 100 random starts)
- **data_type_fit_to:** choice behavior  ---  #### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  #### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 200 (100 per condition); M age = 37.16 (SD = 11.79); 80 females. 6 excluded from contagion analysis due to missed trials. US-based, Amazon Mechanical Turk.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Same as Experiment 1. Additional strength: generalization design tests deeper inference beyond rote association. Same limitations regarding predetermined offers and anonymous Teacher.
- **eligibility_flag:** 
- **concerns:** Same as Study 1, plus: Models 3 and 4 (Basic RL, Offer-Sensitive RL) not tested in Experiment 2 due to poor performance in Experiment 1, reducing model comparison space; mean fitted parameters still not reported in main text.
- **limitations_reported:** Same as Study 1 (authors discuss limitations in a shared Discussion section).
- **limitations_categorized:** Same as Study 1.
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Partial
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
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
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_C_exchange_interdependence
- tax_mod_action_observation
- tax_mod_vicarious_outcome
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_bayesian
- tax_model_utility
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
