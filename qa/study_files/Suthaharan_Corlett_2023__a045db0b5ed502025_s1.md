# Suthaharan & Corlett (2023)

- **study_id:** `a045db0b5ed502025_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Suthaharan, P., & Corlett, P. R. (2023). Assumed shared belief about conspiracy theories in social networks protects paranoid individuals against distress. *Scientific Reports*, *13*, 6084. https://doi.org/10.1038/s41598-023-33305-w
- **citation_short:** Suthaharan & Corlett (2023)
- **doi:** 10.1038/s41598-023-33305-w
- **publication_type:** peer-reviewed journal---
- **year:** 2023.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** departmental Neuroscience Program, Yale University, New Haven, CT, USA; Department of Psychiatry, Connecticut Mental Health Center, Yale; Department of Psychology, Yale University, New Haven, CT, USA; ether a particular belief is adopted and m aintained4; Institute, Yale University, New Haven, CT, USA; mitigate distress and suffering10; University, New Haven, CT, USA; Institute for Neuroscience,; emails: philip.corlett@yale.edu
- **code_url:** 

## Computational level
- **study_focus:** Belief updating under uncertainty, conspiracy belief endorsement, social network assumed shared belief, and paranoia
- **study_focus_short:** Belief updating under uncertainty, conspiracy belief endorsement, social
- **learning_mode_description:** - Learning mode: Learning from probabilistic reward feedback about which option is currently best, in both social (avatar/partner) and non-social (card deck) frames   - Learning from:     - Source type (non-social): world       - Source content (non-social): outcome (win/loss feedback)   - Learning about:     - Target type (non-social): world       - Target content (non-social): state (reward contingencies / volatility of environment)  Note: Although participants completed a "social" version of the task (avatars representing partners), the authors explicitly found no effect of social vs. non-social task frame on behavior or model parameters. The task itself is a standard 3-armed probabilistic reversal learning task; the "social" framing is cosmetic. The social network survey component is correlational/descriptive and does not involve computational learning.
- **task_description:** Participants chose between three card decks (non-social version) or three avatars (social version) in a probabilistic reversal learning task, learning which option was most rewarding while contingencies shifted. Separately, participants completed self-report measures of paranoia and conspiracy beliefs, and a social network survey about their alters' beliefs.
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), no interactive partners
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Card decks or avatar images, binary win/loss feedback
- **method:** online / behavioural
- **method_full:** Behavioural / online
- **main_result:** - Paranoid individuals expected more task volatility: W = 275568, p < .001- Paranoia correlated with COVID-19 vaccine conspiracy belief: ρ = 0.42- Paranoia correlated with QAnon conspiracy belief: ρ = 0.30- Paranoia correlated with general conspiracy belief: ρ = 0.41- COVID-19 vaccine conspiracy belief correlated with μ₃⁰: ρ = 0.29- QAnon conspiracy belief correlated with μ₃⁰: ρ = 0.21- General conspiracy belief correlated with μ₃⁰: ρ = 0.17- Paranoia correlated with μ₃⁰: ρ = 0.24- Network size × assumed shared belief interaction on psychopathology: F(7, 195) = 4.03, p = .01- Paranoia × strong ties × assumed shared belief interaction on volatility: F(13, 189) = 3.97, p = .03- Reduced psychopathology model: Adjusted R² = 0.10, p < .001- Reduced volatility model: Adjusted R² = 0.16, p < .001
- **effect_size:** - Paranoid individuals expected more task volatility: W = 275568, p < .001- Paranoia correlated with COVID-19 vaccine conspiracy belief: ρ = 0.42- Paranoia correlated with QAnon conspiracy belief: ρ = 0.30- Paranoia correlated with general conspiracy belief: ρ = 0.41- COVID-19 vaccine conspiracy belief correlated with μ₃⁰: ρ = 0.29- QAnon conspiracy belief correlated with μ₃⁰: ρ = 0.21- General conspiracy belief correlated with μ₃⁰: ρ = 0.17- Paranoia correlated with μ₃⁰: ρ = 0.24- Network size × assumed shared belief interaction on psychopathology: F(7, 195) = 4.03, p = .01- Paranoia × strong ties × assumed shared belief interaction on volatility: F(13, 189) = 3.97, p = .03- Reduced psychopathology model: Adjusted R² = 0.10, p < .001- Reduced volatility model: Adjusted R² = 0.16, p < .001
- **learning_from:** World; reward outcome on chosen deck/avatar
- **learning_about:** World; reward contingency structure and environmental volatility---  ### ALGORITHMIC LEVEL
- **outcome_modality:** social_feedback

## Algorithmic level
- **winning_model:** HGF (3-level Hierarchical Gaussian Filter with softmax-mu03 response model; key parameter: μ₃⁰ = initial prior on volatility)
- **model_family:** HGF
- **model_class:** PE learning / Belief updating
- **all_models_tested:** Only one model configuration reported: - {"name": "3-level HGF with softmax-mu03", "family": "Hierarchical Gaussian Filter", "n_params": "not explicitly enumerated in paper", "metric": "N/A — single model"}
- **model_mb_mf:** Bayesian
- **model_params:** - μ₃⁰: initial prior belief on task volatility (key parameter related to paranoia) — mean fitted values not reported per group in this paper- Perceptual model parameters estimated individually for first half (trials 1–80) and second half (trials 81–160)- Specific parameter list (κ, ω, etc.) not enumerated in this paper; authors refer to prior work (Suthaharan et al., 2021; Reed et al., 2020) and the TAPAS/HGF toolbox v5.3.1
- **social_param:** None explicitly designated as social. μ₃⁰ is domain-general; the authors argue paranoia (a social concern) is linked to domain-general volatility beliefs.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A — only one model tested
- **how_model_fit:** Individual-level fit (parameters estimated individually per participant using TAPAS/HGF toolbox in MATLAB)
- **data_type_fit_to:** Choice behavior---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A — no neuroimaging
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging)---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 1538 total. Social network study: n = 372 (310 low paranoia, 62 high paranoia); psychopathology subset: n = 203. Replication study: n = 1166 additional (combined: 831 nonsocial task, 707 social task; 1206 low paranoia, 332 high paranoia). Online participants via CloudResearch.
- **population_category:** clinical
- **population_age_range:** 
- **ecological_validity:** Social network survey captures real-world self-reported social connections and beliefs about alters — more ecologically valid than lab-only tasks. However, all social network data are ego-reported (no alter verification), and the probabilistic reversal learning task is a standard lab paradigm with abstract stimuli. The link between lab-derived volatility and real-world conspiracy beliefs is correlational.
- **eligibility_flag:** The paper uses computational modeling (HGF) and human behavioral data, and learning occurs over time in the reversal learning task. However, the social component is primarily correlational (social network survey data correlated with model parameters). The learning task itself is NOT inherently social — the authors explicitly show no difference between social and non-social framings. The computational model is fit to a non-social probabilistic learning task; the "social" element is in the correlational analyses linking model parameters to conspiracy beliefs and social network features. FLAG: Borderline — computational learning occurs in a non-social task; social context is in correlational/survey analyses only, not in the learning process itself.
- **concerns:** - Only one model tested — no model comparison performed - The social framing of the task (avatars) produced no behavioral or parameter differences vs. the non-social framing, yet the paper is framed as about social belief - Social network measures are entirely ego-reported with no verification - Cross-sectional correlational design — no causal claims possible - Mean fitted parameter values for μ₃⁰ not reported by group - Full parameter list for the HGF not enumerated in this paper (refers to prior publications)
- **limitations_reported:** Social network measures are all derived from egos expressing memories/attitudes/beliefs about self-reported alters — could not confirm alters' actual existence or beliefs; correlative data — cannot make causal claims — would require time-series data; homophily may explain network composition; paranoia and conspiracies are not synonymous and may have unique predictors; delusions may not merely be extreme conspiracy theorizing; self-reference findings need replication in clinical populations
- **limitations_categorized:** Self-report bias; no causal inference (cross-sectional design); limited ecological validity (lab task); no alter verification; potential confound (homophily); limited generalizability (online sample, non-clinical)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 6.0
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_paranoia
- rr_pop_healthy_adults
- rr_pop_paranoia
- rr_tax_mod_experiential
- spec_depth = general
- spec_locus = source+context
- tax_domain_B_inference_modelling_others
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_model_HGF
- tax_model_bayesian
- tax_param_social_bonus
- tax_param_social_weight
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = G_uncertainty_volatility
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_HGF
- tax_rr_model_family = HGF
- tax_rr_param_PE_signal
- tax_rr_param_precision
- tax_rr_primary_topic = social_uncertainty
- tax_rr_secondary_topic = reputation_learning
- tax_rr_topic_reputation_learning
- tax_rr_topic_social_uncertainty
- tax_social_nonsocial_comparison
- tax_topic_reputation_learning
- tax_topic_social_uncertainty
