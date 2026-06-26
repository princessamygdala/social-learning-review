# Wang et al. (2023)

- **study_id:** `a972fcd80ff0bfd61_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Wang, X., Liao, J., Nan, Y., Hu, J., & Wu, Y. (2023). Can testosterone modulate prosocial learning in healthy males? A double-blind, placebo-controlled, testosterone administration study. *Biological Psychology*, *178*, 108524. https://doi.org/10.1016/j.biopsycho.2023.108524
- **citation_short:** Wang et al. (2023)
- **doi:** 10.1016/j.biopsycho.2023.108524
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ether individuals need to gain or condition, participants were told that the rewards they obtained would; Institute for Sports Science and Technology, Hong Kong Polytechnic University, Hung Hom, Hong Kong; Department of Applied Social Sciences, Hong Kong Polytechnic University, Hung Hom, Hong Kong; School of Psychology and Cognitive Science, East China Normal University, Shanghai, China; Center for Neuroeconomics, Department of Economics, University of Zurich, Switzerland; School of Psychology, South China Normal University, Guangzhou, China; School of Psychology, Shenzhen University, Shenzhen
- **code_url:** https://osf.io/3u82k/

## Computational level
- **study_focus:** Prosocial learning — effects of exogenous testosterone on reinforcement learning for self, other, and computer recipients.
- **study_focus_short:** Prosocial learning
- **learning_mode_description:** - Learning mode: Learning from reward outcomes to choose high-reward symbols for different recipients (self, other, computer)   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (binary reward feedback on chosen symbol)   - Learning about:     - Target type (social): other (anonymous other person)       - Also non-social targets: self, computer — but the key prosocial condition targets another person     - Target content (social): outcome (reward value of symbols for the other)  Note: The task has three recipient conditions. The core "prosocial learning" condition involves learning to obtain rewards for another person. Across all conditions, the participant is the sole decision-maker learning from their own reward feedback. The source is always non-social (self-generated choice outcomes). The target varies: self (non-social), other (social), computer (non-social).
- **task_description:** Participants chose between two abstract symbols, one associated with 75% reward probability and the other with 25%, to earn rewards for one of three recipients (self, other, or computer) across 144 trials (3 recipients x 3 blocks x 16 trials). Testosterone or placebo gel was administered in a double-blind, between-subjects design.
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), multi-target (self, anonymous other, computer)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Abstract symbols, binary reward feedback (reward/no reward)
- **method:** pharmacological / behavioural
- **method_full:** Behavioural (pharmacological: testosterone gel administration)
- **main_result:** - Testosterone increased learning rates across all recipient conditions (main effect of treatment: F(1, 354) = 93.70, p < .001, η² = 0.21) - Significant treatment x recipient interaction (F(2, 354) = 8.53, p < .001, η² = 0.05) - Testosterone group had higher prosocial learning rate (α_other) than placebo (d = 1.57) - Testosterone group: α_other comparable to α_self (d = 0.13, n.s.); placebo group showed self-advantage (α_self > α_other, d = 1.20) - Prosocial learning rate difference (α_other - α_self) was higher in testosterone vs. placebo group (d = 0.87)
- **effect_size:** - Treatment main effect: η² = 0.21 - Recipient main effect: η² = 0.14 - Treatment x Recipient interaction: η² = 0.05 - Testosterone vs. placebo on α_other: d = 1.57 - Testosterone vs. placebo on α_self: d = 0.50 - Testosterone vs. placebo on α_computer: d = 0.99 - Prosocial learning rate (α_other - α_self) group difference: d = 0.87 - Placebo α_self vs. α_other: d = 1.20 - Placebo α_self vs. α_computer: d = 1.21
- **learning_from:** Self; own reward outcome on chosen symbol
- **learning_about:** Other (anonymous other person) — reward value of symbols; also self and computer conditions  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** RW (1 α per recipient condition; 1 β) — Rescorla-Wagner with separate learning rates for self, other, and computer conditions
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Rescorla-Wagner (RW)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "LOOIC"}, {"name": "Null model (random choice)", "family": "Null", "n_params": 0, "metric": "LOOIC"}]  Note: The paper describes fitting the RW model separately per recipient condition. Each fit has 2 parameters (α, β). The null model assumes random choice.
- **model_mb_mf:** MF
- **model_params:** - α (learning rate) [S in other condition]: controls degree to which expected value is updated by prediction error. Separate α fitted per recipient condition (self, other, computer). Mean fitted values not reported explicitly in paper. - β (inverse temperature): controls choice stochasticity in SoftMax function. Mean fitted value not reported.
- **social_param:** α_other [S] — learning rate in the other (prosocial) condition; the key parameter showing testosterone enhances learning for others.
- **social_param_name:** α_other [S]
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** LOOIC (leave-one-out cross-validation information criterion)
- **how_model_fit:** Individual-level fit (hierarchical Bayesian via hBayesDM package)
- **data_type_fit_to:** Choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 120 (healthy males; mean age = 21.0, SD = 1.9, range 18-26); between-subjects: testosterone group vs. placebo group (group sizes not specified but presumably ~60 each)
- **population_category:** healthy adults
- **population_age_range:** 18–26
- **ecological_validity:** Low — abstract symbol learning task in laboratory setting; prosocial context is minimal (participant told rewards go to "someone else" with no face-to-face interaction); pharmacological manipulation adds experimental control but limits naturalism.
- **eligibility_flag:** 
- **concerns:** - No manipulation check of testosterone levels (acknowledged by authors) - Potential testosterone transference between groups (acknowledged by authors) - Only 2 models compared (RW vs. null) — very limited model space - Mean fitted parameter values for α and β not reported - No parameter recovery or model recovery analyses - Effect sizes for testosterone on learning rate are unusually large (d = 1.57 for other condition) — may warrant scrutiny - Male-only sample limits generalizability - Group sizes for testosterone vs. placebo not explicitly stated
- **limitations_reported:** Only focused on activational effects of testosterone, not organizational effects; did not examine interaction between testosterone and other hormones (e.g., cortisol per dual-hormone hypothesis); testosterone gel protocol required 3-hour wait (nasal spray may be faster); no manipulation check of testosterone level; testosterone transference between groups possible.
- **limitations_categorized:** Limited ecological validity; limited generalizability (male-only); no manipulation check; potential contamination between groups; narrow hormonal scope; task simplicity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM — paper states α and β but does not report mean fitted values; separate α per condition inferred from results - all_models_tested n_params: MEDIUM — 2 params (α, β) per condition fit, but paper does not state n_params explicitly - sample_size group breakdown: MEDIUM — total N=120 stated; ~60 per group inferred from between-subjects design but not explicitly stated - effect_size d values: HIGH — directly reported in text
- **cannot_find:** - Mean fitted parameter values for α and β (not reported in paper) - Exact group sizes for testosterone vs. placebo - Exact model formula notation (reconstructed from equations 1 and 2 in the paper) - Whether α was fit jointly across conditions or separately — paper describes fitting per condition but this is somewhat ambiguous
- **other_notes:** - No supplement available for this paper - The prosocial learning task is adapted from Lockwood et al. (2016), a well-known paradigm in the field - The very large effect sizes (d = 1.57) are noteworthy and should be interpreted cautiously - Paper supports the social status hypothesis of testosterone
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pharma_testosterone
- pop_healthy_adults
- rr_pharma_testosterone
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = target
- spec_target = partly
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_topic_prosocial_altruism
