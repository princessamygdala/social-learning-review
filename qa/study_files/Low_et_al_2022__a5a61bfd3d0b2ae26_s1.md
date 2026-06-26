# Low et al. (2022)

- **study_id:** `a5a61bfd3d0b2ae26_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Low, A. A. Y., Hopper, W. J. T., Angelescu, I., Mason, L., Will, G.-J., & Moutoussis, M. (2022). Self-esteem depends on beliefs about the rate of change of social approval. *Scientific Reports*, *12*, 6643. https://doi.org/10.1038/s41598-022-10260-6
- **citation_short:** Low et al. (2022)
- **doi:** 10.1038/s41598-022-10260-6
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** Department of Clinical, Educational and Health Psychology, University College London, London, UK; Centre for Computational Psychiatry and Ageing Research, University College London, London, UK; ether belief-based models offer the best account of momentary self-esteem, we first; ether self‑esteem based on social approval should be understood as; Centre for Human Neuroimaging, London, UK; University, Utrecht, The Netherlands; Institute, Paris, France; Department; emails: an.low.16@ucl.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Social approval learning / self-esteem updating. Whether momentary self-esteem is best explained by associative learning (Rescorla-Wagner) or Bayesian belief updating about the rate of change of social approval.
- **study_focus_short:** Social approval learning / self-esteem updating
- **learning_mode_description:** - Learning mode: Learning from others' social approval/disapproval feedback about one's own social standing (rate of change of approval)   - Learning from:     - Source type (social): other (multiple strangers/raters from 4 groups)     - Source content (social): outcome (approval or disapproval feedback)   - Learning about:     - Target type (social): self (own social worth / self-esteem)     - Target content (social): state (mental state; beliefs about rate of change of social approval)
- **task_description:** Participants created an online profile and later performed a social evaluation task where, on each trial, they predicted whether a stranger (from one of four groups varying in approval probability: ~15%, 30%, 70%, 85%) would approve or disapprove of them, then received thumbs-up/down feedback. Every 2-3 trials, participants rated momentary self-esteem on a visual analogue scale.
- **task_paradigm:** Self-evaluation / self-esteem task
- **players:** Single agent (participant), multi-target (192 strangers in discovery sample; 184 strangers in confirmation sample; 4 groups)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Rater group cue (indicating general approval tendency), thumbs-up/thumbs-down feedback icons, visual analogue self-esteem scale
- **method:** fMRI / behavioural
- **method_full:** behavioural (discovery sample includes 39 from a prior fMRI study + 21 behavioural; confirmation sample = 61 behavioural; no neuroimaging analysis in this paper)
- **main_result:** - Main Results:   - Belief-based model outperformed associative and associative-sigmoid models in discovery sample (median BIC difference: belief vs. associative = -4.9; belief vs. assoc_sigmoid = -33.6)   - Belief-based model replicated out-of-sample in confirmation dataset (median BIC difference: belief vs. associative = -14.3; belief vs. assoc_sigmoid = -61.7)   - No evidence for differential learning rates from approval vs. disapproval   - No evidence that perceived competence (predicting approval correctly) contributed to momentary self-esteem   - Model correlations between expected and actual self-esteem ratings: r = 0.744, 0.858, 0.818 for illustrative participants
- **effect_size:** BIC comparisons only; no standardized effect sizes (d, r, etc.) reported for key model comparison. Individual model-fit correlations reported for illustrative cases (r = 0.744, 0.858, 0.818).
- **learning_from:** Other (multiple strangers); social approval/disapproval feedback outcomes
- **learning_about:** Self; beliefs about the rate of change of social approval (momentary self-esteem)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** Bayesian belief model with beta-distribution beliefs about groups and about self (momentum of approval). Parameters: α_min(0), α_max(0), λ_acc (decay for group beliefs), ς (decay for self-beliefs), w (PE weight), m (sigmoid sensitivity), B (bias/baseline SE), T (decision temperature), positivity bias B_choice. Sigmoid response function maps belief distribution onto self-esteem ratings.
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "Original associative (RW)", "family": "Rescorla-Wagner", "n_params": "~5-6 (w0, w1, η, γ, σ, B)", "metric": "BIC"} - {"name": "2LR (dual learning rates)", "family": "Rescorla-Wagner", "n_params": "+1 vs original", "metric": "BIC"} - {"name": "2LR + separate expectation term", "family": "Rescorla-Wagner", "n_params": "+2 vs original", "metric": "BIC"} - {"name": "2LR + fixed positivity bias", "family": "Rescorla-Wagner", "n_params": "same or fewer", "metric": "BIC"} - {"name": "Competence-Acceptance", "family": "Rescorla-Wagner", "n_params": "+1 (w3)", "metric": "BIC"} - {"name": "Associative-sigmoid", "family": "Rescorla-Wagner + sigmoid", "n_params": "similar to belief", "metric": "BIC"} - {"name": "Belief model (beta-distribution)", "family": "Bayesian belief updating", "n_params": "~7-8 (α_min(0), α_max(0), λ_acc, ς, w, m, B, T)", "metric": "BIC"}
- **model_mb_mf:** Bayesian
- **model_params:** - α_min(0): initial alpha for least accepting group [no mean reported] - α_max(0): initial alpha for most accepting group [no mean reported] - n(0): initial sample size for group beliefs (derived from λ_acc via Eq. 15; not free) - λ_acc: decay coefficient for beliefs about groups - ς: trial-by-trial belief decay for self-beliefs (momentum) - w [S]: weight of social prediction error on self-belief updating - m: sensitivity of self-esteem sigmoid response function - B [S]: bias/baseline self-esteem in sigmoid response function - T: decision temperature for approval predictions - B_choice: positivity bias in choice spoke  Note: Exact parameter counts and fitted mean values are stated to be in Supplementary Table S4, which is not accessible.
- **social_param:** w [S] — weight of social prediction error on self-belief updating; B [S] — baseline self-esteem / bias in the sigmoid response function
- **social_param_name:** w
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion)
- **how_model_fit:** individual-level-fit (MLE with 129 grid-search starting points per participant using R's nlm function)
- **data_type_fit_to:** choice behavior (approval predictions) + self-report ratings (momentary self-esteem VAS)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging analysis in this paper)
- **key_regions:** N/A (no neuroimaging analysis in this paper)
- **coordinates_peak:** N/A — no neuroimaging analysis conducted in this paper
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** Discovery sample: N=60 (mean age=20.8, SD=2.14, 34 female; 39 from prior fMRI study + 21 behavioural). Confirmation sample: N=61 (mean age=20.6, SD=3.2, 32 female; 31 top decile + 30 bottom decile of trait self-esteem). Total N=121.
- **population_category:** healthy adults
- **population_age_range:** M=20.8
- **ecological_validity:** Moderate lab task. Social evaluation is computer-generated (bogus raters), not real social interaction. Participants believed profiles were rated by real people. Serial evaluation paradigm mimics joining a new social group, but lacks the richness and bidirectionality of real social encounters.
- **eligibility_flag:** 
- **concerns:** - Exact number of free parameters for each model variant is not fully specified in the main text (referred to Supplementary Table S4, which is not accessible) - No standardized effect sizes reported for the key model comparison (only BIC sums/medians) - Fitted parameter values not reported in main text (stated to be in supplement) - Social feedback was computer-generated, not from real raters - Discovery sample partially overlaps with prior published studies (Will et al. 2017, Will et al. 2020)
- **limitations_reported:** Both samples were restricted to young adults (mean age = 20.7, SD = 2.7), while self-esteem is important throughout the lifespan and cannot be assumed to follow the same dynamics; competence analyses were exploratory, as the task was not designed or powered to specifically investigate competence; the present work focuses on mechanisms of momentary self-esteem beliefs in general but does not examine whether differential updating depends on self-schemas associated with lower self-esteem or differs depending on how threatening an environment is
- **limitations_categorized:** limited generalizability (age range); task simplicity (not designed for competence); limited ecological validity (lab setting); no examination of individual differences in schema-based updating
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
- **wc_rule10:** Partial
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM — exact number and fitted mean values referred to Supplementary Table S4, not accessible - all_models_tested n_params: MEDIUM — exact parameter counts not fully specified in main text for all variants - effect_size: MEDIUM — no standardized effect sizes; only BIC values and illustrative correlations - wc_guidelines rule 5: MEDIUM — parameter recovery stated as conducted but no detail given
- **cannot_find:** - Supplementary Table S4 (parameter definitions, ranges, and fitted values) — supplement not accessible - Exact number of free parameters for each model variant - Fitted mean parameter values for winning model - Standardized effect sizes for model comparison
- **other_notes:** - This paper builds on Will et al. (2017) and Will et al. (2020) using the same task paradigm and partially overlapping data (discovery sample includes 39 participants from Will et al. 2017 fMRI study). Potential overlap should be noted if those papers are also in the review corpus. - The paper is purely behavioural in its analyses despite some data being collected during fMRI; no neuroimaging results are reported here. - Supplement not accessible — Supplementary Table S4 would contain full parameter specifications. This is flagged; `re_extract_flag` should be set if supplement becomes available. - Code available at: https://github.com/alexisaylow/selfeval
- **re_extract_flag:** true (supplement not accessible; parameter details likely in Supplementary Table S4)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_PE_signal
- tax_rr_param_precision
- tax_rr_primary_topic = self_esteem
- tax_rr_secondary_topic = social_approval_reward
- tax_rr_topic_self_esteem
- tax_rr_topic_social_approval_reward
- tax_topic_self_esteem
- tax_topic_social_approval_reward
