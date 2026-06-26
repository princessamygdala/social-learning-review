# Luo et al. (2025)

- **study_id:** `a098ba4b86e8ffd67_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Luo, X., Zhang, L., & Pan, Y. (2025). Do we advise as one likes? The alignment bias in social advice giving. *PLoS Computational Biology*, *21*(12), e1013732. https://doi.org/10.1371/journal.pcbi.1013732
- **citation_short:** Luo et al. (2025)
- **doi:** 10.1371/journal.pcbi.1013732
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** Department of Psychology and Behavioral Sciences, Zhejiang University, Hangzhou, China, 2 School; University of Birmingham, Birmingham, United Kingdom, 4 Institute for Mental Health, University; University, Hangzhou, China, 7 Zhejiang Key Laboratory of Neurocognitive Development and Mental; University of Birmingham, Birmingham, United Kingdom, 3 Centre for Human Brain; mity, persists even when advisors were directly incentivized to provide; Centre for Developmental Science, University of; Lab of Brain-Machine Intelligence, Zhejiang; University: Army Medical University, CHINA; emails: l.zhang.1
- **code_url:** https://osf.io/aehxr/

## Computational level
- **study_focus:** Social advice giving / alignment bias — how advisors conform to advisees' opinions and adapt advice-giving tendencies through feedback-driven reinforcement learning.
- **study_focus_short:** Social advice giving / alignment bias
- **learning_mode_description:** - Learning mode: Learning from advisee's acceptance/rejection feedback about advisee's preference for aligned vs. misaligned advice   - Learning from:     - Source type (social): other (advisee)     - Source content (social): outcome (acceptance/rejection feedback)   - Learning about:     - Target type (social): other (advisee)     - Target content (social): state (mental state; preference for aligned vs. misaligned advice)  ---  ### 5. COMPUTATIONAL PROBLEM  How do advisors update their advice-giving tendencies (aligned vs. misaligned with advisee's opinion) in response to social feedback (acceptance/rejection) from advisees, and what learning biases maintain a pre-existing alignment tendency? (Prediction / evaluation)  ---  ### 6. RESULTS WITH EFFECT SIZES
- **task_description:** Participants acted as advisors in an investment game, providing advice on whether estate property prices were higher or lower than actual values and wagering on their judgements. In Studies 1-2, they advised independently (Session 1) then after observing an alleged advisee's opinions (Session 2). In Studies 3-4, advisees' acceptance/rejection feedback was introduced in a probabilistic reversal design, with advisees' preferences for aligned vs. misaligned advice shifting across phases.
- **task_paradigm:** Investment game
- **players:** Single agent (participant as advisor), dyadic (alleged human advisee, actually simulated).
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Real estate property photos with prices, binary feedback (acceptance/rejection of advice).
- **method:** online / behavioural
- **method_full:** Behavioural (online/lab-based, no neuroimaging).
- **main_result:** 
- **effect_size:** 
- **learning_from:** 
- **learning_about:** 
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** M7 — Rescorla-Wagner RL with 4 asymmetric learning rates differentiated by advice type (aligned/misaligned) × feedback type (acceptance/rejection), plus non-social and social value weights (6 free parameters: α_accept_aligned, α_reject_aligned, α_accept_misaligned, α_reject_misaligned, w_ns, w_s)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 
- **model_mb_mf:** MF
- **model_params:** - α_accept_aligned (a^ac_al) [S]: learning rate for acceptance when giving aligned advice - α_reject_aligned (a^re_al) [S]: learning rate for rejection when giving aligned advice - α_accept_misaligned (a^ac_mis) [S]: learning rate for acceptance when giving misaligned advice - α_reject_misaligned (a^re_mis) [S]: learning rate for rejection when giving misaligned advice - w_ns: cognitive weight for non-social value - w_s [S]: cognitive weight for social value  Mean fitted values: not reported in main text (parameter recovery reported in supplement S3 Text, which is not accessible).
- **social_param:** Four asymmetric learning rates (a^ac_al, a^re_al, a^ac_mis, a^re_mis) capture how advisors differentially weight acceptance/rejection feedback depending on whether advice was aligned or misaligned with advisee's opinion; w_s captures weight of social value in decision-making.  ---  ### 8. ALL MODELS TESTED  | Model | Family | n_params | Metric | |-------|--------|----------|--------| | M1 (Baseline) | SoftMax on non-social value only | 1 (τ) | LOOIC | | M2 (Social bias, constant) | Constant social bias + non-social value | 2 (w_ns, w_s) | LOOIC | | M3 (Social bias, confidence) | Advisee confidence-weighted bias | 2 (w_ns, w_s) | LOOIC | | M4 (Social bias, acceptance) | Constant bias + acceptance sensitivity κ | 3 (w_ns, w_s, κ) | LOOIC | | M5 (Social learning, basic RW) | Rescorla-Wagner w
- **social_param_name:** α_accept_aligned
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** LOOIC (leave-one-out information criterion) via the loo package; Bayesian model averaging with Bayesian bootstrap for model weights.
- **how_model_fit:** Individual-level fit within hierarchical Bayesian framework (Stan, hBayesDM-style).
- **data_type_fit_to:** Choice behavior (binary judgement alignment: aligned vs. misaligned advice).  ---  ### 9. NEUROIMAGING

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** 
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** - Study 1: N = 73 (mean age 22.23, range 18–29; 42 females) - Study 2: N = 62 (mean age 23.03, range 18–32; 39 females) - Study 3: N = 111 (mean age 21.90, range 18–30; 69 females) - Study 4: N = 100 (mean age 20.49, range 18–27; 71 females) - Total: N = 346
- **population_category:** healthy adults
- **population_age_range:** 18–29
- **ecological_validity:** Task simulates advice-giving in an estate price evaluation domain unfamiliar to student participants. Deceptive manipulation creates perceived real-time interaction with an alleged human advisee. Feedback is binary (accept/reject) rather than graded. Authors acknowledge limited ecological validity: unfamiliar domain, binary feedback, lab-simulated interaction rather than real social relationships.  ---  ### 12. ELIGIBILITY FLAG
- **eligibility_flag:** 
- **concerns:** - Studies 1 & 2 do not involve computational modeling — only Studies 3 & 4 do. For the review, extraction of modeling details pertains to Studies 3 & 4 only. - Supplement (S3 Text with parameter recovery, model recovery, posterior predictive checks) is listed as DOCX but not available in the papers folder. Cannot verify parameter recovery details, mean fitted parameter values, or posterior predictive check quality. - The "advisee" is entirely simulated (deceptive paradigm); the social agent is automated/pre-programmed. - All participants are Chinese university students — limited cultural generalizability. - Fixed session order (non-social always before social) introduces potential order effects.
- **limitations_reported:** - Domain unfamiliarity: estate price evaluation task unfamiliar to student participants; unclear if alignment bias persists among domain experts; *limited ecological validity; limited generalizability* - Binary feedback format (accept/reject) oversimplifies real-world graded advice integration; *task simplicity* - Cannot determine whether feedback-driven adaptation reflects conscious or unconscious process; *limited mechanistic insight* - Simulated interaction via deception rather than real social relationship; unclear generalizability to real-world relationships (e.g., friendships); *limited ecological validity* - No comparison with non-social targets (e.g., AI advisee); *limited experimental control*
- **limitations_categorized:** limited ecological validity; limited generalizability; task simplicity; limited mechanistic insight; limited experimental control  ---  ### OTHER NOTES  - The paper contains 4 studies but only Studies 3 and 4 use computational modeling. For visualization_data.csv, Studies 3 and 4 should each get a row. Studies 1 and 2 should be flagged as ineligible (no computational modeling). - The social agent (advisee) is entirely automated/simulated — flag per instructions. - Data and code available at https://osf.io/aehxr/. - Supplement not accessible (listed as DOCX files: S1 Text, S2 Text, S3 Text) — not found in papers folder. Flagging: "Supplement not accessible." - re_extract_flag: false (full text was accessible; only supplement missing) - M7 won in both Study 3 (weight = 0.85) and Study 4 (weight = 0.499, with M5 at 0.417 — closer competition in Study 4).
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9.5
- **wc_total:** 9.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params mean fitted values: LOW confidence — "not reported in main text; supplement not accessible" - WC Rule 3 (simulate): MEDIUM — simulations mentioned for posterior predictive checks but pre-fitting simulation not explicitly described in main text - WC Rule 5 (parameter recovery): MEDIUM — stated as performed in S3 Text but cannot verify
- **cannot_find:** - Mean fitted parameter values for M7 - Full parameter recovery results (in S3 Text, not accessible) - Model recovery confusion matrix details (in S3 Text, not accessible)  ---  ### 14. WC CHECKLIST  1. **Design a good experiment:** Yes — task engages advice-giving learning process with probabilistic reversal design 2. **Design good models:** Yes — 7 competing models across 3 conceptual categories (baseline, social bias, social learning) 3. **Simulate, simulate, simulate:** Partial — posterior predictive checks conducted (simulating from fitted model); pre-fitting simulation not explicitly reported in main text (may be in supplement) 4. **Fit the parameters:** Yes — hierarchical Bayesian estimation via Stan 5. **Check parameter recovery:** Yes — stated as performed in S3 Text (Fig A in S3 Text), though supplement not accessible for verification 6. **Check model recovery:** Yes — full model recovery analysis conducted on all candidate models (Fig C in S3 Text), though supplement not accessible for verification 7. **Fit real data and compare models:** Yes — LOOIC comparison + Bayesian model averaging across 7 models 8. **Validate the winning model:** Yes — posterior predictive checks at trial-wise, individual, and grand-average levels (Fig B in S3 Text) 9. **Analyze the winning model:** Yes — learning rate asymmetries analyzed, linked to behavioral measurements (Tables 2-4) 10. **Report results transparently:** Yes — data and code shared on OSF (https://osf.io/aehxr/)
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = general
- spec_locus = source+target
- tax_domain_A_influence_transmission
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = advice_taking
- tax_rr_secondary_topic = norm_conformity
- tax_rr_topic_advice_taking
- tax_rr_topic_norm_conformity
- tax_topic_advice_taking
- tax_topic_norm_conformity
