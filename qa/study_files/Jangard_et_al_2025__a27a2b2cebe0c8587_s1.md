# Jangard et al. (2025)

- **study_id:** `a27a2b2cebe0c8587_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Jangard, S., Lindström, B., Khemiri, L., Jayaram-Lindström, N., & Olsson, A. (2025). Dissociating social reward learning and behavior in alcohol disorder. *Translational Psychiatry*, 15(1), 30. https://www.nature.com/articles/s41398-025-03236-3
- **citation_short:** Jangard et al. (2025)
- **doi:** 10.1038/s41398-025-03236-3
- **publication_type:** peer-reviewed journal (published in translational psychiatry; extracted from thesis)
- **year:** 2025.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** CentreforPsychiatryResearch,DepartmentofClinicalNeuroscience,KarolinskaInstitutet&StockholmHealthCareServices,RegionStockholm,Stockholm,Sweden; ETHODS:Weconducted one laboratory study (n=234)andone confirmatory online study (n=258),comparing youngadults; ethatprosocialdeficitsinAUDandrelateddisorders Americanonlinestudycomprising123individualswithAUD(51%males),; ether,theseresultsindicatethatrewardprocessesmaynotberelevantforunderstandingcompromisedsocialbehaviorinAUD; Department of Clinical Neuroscience, Karolinska Institutet, Stockholm, Sweden; Department of Medical Epidemiology and Biostati
- **code_url:** https://osf.io/25d8c/

## Computational level
- **study_focus:** Prosocial learning — social reward learning (learning which actions benefit others) in alcohol use disorder.
- **study_focus_short:** Prosocial learning · social reward learning (learning which actions benefit others) in alcohol use disorder
- **learning_mode_description:** - Learning mode: Learning from probabilistic reward feedback about which actions benefit another person   - Learning from:     - Source type (non-social): self (own choices)     - Source content (non-social): outcome (probabilistic reward feedback — whether chosen symbol yielded reward for other)   - Learning about:     - Target type (social): other (anonymous partner)     - Target content (social): outcome (which actions benefit the other person)
- **task_description:** Participants completed a reinforcement learning task with 144 trials across three conditions (prosocial, self, no-one), choosing between two symbols with different reward probabilities (75% vs. 25%), where rewards went to another person, to themselves, or to no one depending on condition.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), single anonymous partner (allegedly real interaction partner, actually simulated).
- **n_players:** single agent (1)
- **partner_type:** human (live)
- **stimuli:** Abstract symbols (probabilistic reward associations), binary reward feedback.
- **method:** online / behavioural
- **method_full:** Behavioural (lab + online replication)
- **main_result:** - No group differences in social reward learning accuracy between AUD and healthy controls (consistent across lab and online samples) - No group differences in computational model parameters (learning rate α, temperature β) - AUD participants showed reduced prosocial behavior in Dictator Game (fewer points transferred) and lower self-reported altruism - Dissociation: intact social learning but reduced prosocial motivation/behavior
- **effect_size:** LOW confidence — not reported in thesis summary; requires standalone paper
- **learning_from:** Self; own choice outcomes (probabilistic reward feedback indicating whether action benefited the other person)
- **learning_about:** Other (anonymous partner); which actions/symbols yield rewards for the other person  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Rescorla-Wagner (shared α, shared β across conditions; 2 parameters)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "Full model (separate α and β per condition)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "BIC"} 2. {"name": "Intermediate model (shared β, separate α per condition)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BIC"} 3. {"name": "Simplest model (shared α, shared β)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"}
- **model_mb_mf:** MF
- **model_params:** LOW confidence — no mean fitted values reported in thesis
- **social_param:** MEDIUM confidence — the finding is negative (no social-specific parameter needed), which is itself informative
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion)
- **how_model_fit:** MEDIUM confidence — inferred as individual-level from context but not explicitly stated
- **data_type_fit_to:** Choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=492 total (Lab sample: n=119 AUD + n=115 healthy controls = 234; Online sample: n=123 AUD + n=135 healthy controls = 258). Ages 18-24.
- **population_category:** healthy adults
- **population_age_range:** 18–24
- **ecological_validity:** Lab-based and online computerized task with abstract symbols and allegedly real (but simulated) interaction partners. Limited ecological validity — one-shot anonymous partner, no face-to-face interaction, abstract stimuli rather than real social exchange. Deception about partner identity used. Online replication adds generalizability.
- **eligibility_flag:** 
- **concerns:** - Extraction based on thesis summary (kappa), not the standalone published paper. Parameter values, exact model formulas, and full effect sizes not available from thesis text alone. - Interaction partners were simulated (deception); ~19% of lab participants and ~5% of online participants suspected this, though this reportedly did not affect results. - The winning model has shared parameters across social and non-social conditions, meaning the model itself does not contain a social-specific mechanism — the "social" aspect is in the task design (reward recipient), not in the model architecture.
- **limitations_reported:** (From thesis discussion) "Despite the possibility of prosocial learning deficits in more complex learning environments (e.g., model-based learning that requires a mental model of the task environment), our findings support that the ability to learn what benefits others is preserved in AUD"; thesis acknowledges the task tests model-free learning only and more complex social learning environments could reveal differences.
- **limitations_categorized:** Task simplicity; limited ecological validity; model-free learning only tested; no neuroimaging
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

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
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_topic_prosocial_altruism
