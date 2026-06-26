# Connell et al. (2022)

- **study_id:** `ac41b67b58fda0894_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** O'Connell, K., Walsh, M., Padgett, B., Connell, S., & Marsh, A. A. (2022). Modeling variation in empathic sensitivity using go/no-go social reinforcement learning. *Affective Science*, *3*(3), 603–615. https://doi.org/10.1007/s42761-022-00119-4
- **citation_short:** Connell et al. (2022)
- **doi:** 10.1007/s42761-022-00119-4
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofPsychology,GeorgetownUniversity,; mit quantitative investiga-; ethatlearningforanother; University,; ethemost; emails: kmo52@georgetown.edu
- **code_url:** https://github.com/mpc-ucl/emfit

## Computational level
- **study_focus:** Empathic sensitivity / prosocial learning — how reinforcement learning for outcomes affecting another person (a stranger) varies with trait antisociality and empathy.
- **study_focus_short:** Empathic sensitivity / prosocial learning
- **learning_mode_description:** - Learning mode: Learning from monetary outcomes (reward/punishment) that affect oneself or a stranger partner, about the correct action (go/no-go) to obtain rewards or avoid losses for each target.   - Learning from:     - Source type (non-social): self — when playing for self     - Source type (social): other (stranger partner) — when playing for partner     - Source content (non-social/social): outcome (monetary win/loss feedback)   - Learning about:     - Target type (non-social): world — correct action-stimulus mapping     - Target content (non-social): action/policy (go vs. no-go for each fractal stimulus)
- **task_description:** Participants completed a go/no-go reinforcement learning task in which they learned the correct action (button press or no press) for 12 fractal images, with monetary outcomes (win/loss/no change) impacting either themselves, a stranger study partner, or no one across blocked conditions.
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), single target (stranger confederate partner)
- **n_players:** single agent (1)
- **partner_type:** confederate
- **stimuli:** Abstract fractal images, monetary outcomes (green up-arrow = win, red down-arrow = loss, yellow bar = no change), colored block borders indicating condition
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Significant action x valence (Pavlovian bias) interaction across all conditions (ηp² = 0.35, 95% CI [.16, .50])   - Mean accuracy significantly above chance (d = 0.90, 95% CI [0.60, 1.20])   - Social condition accuracy significantly lower than self condition (p < .001) and no-one condition (p = .019)   - Social aggression (STAB) negatively correlated with β_loss sensitivity in social condition (r = −.273, p_perm = .034)   - β_loss social predicted by antisociality even after controlling for demographics and β_loss self (β = −.22, R² = .41)   - Post-task motivation to avoid partner loss positively correlated with β_loss social parameter (r = .361, p_perm = .006)   - Trait anxiety associated with heightened Pavlovian avoidance bias during self-experienced negative affect (r = .258, p_perm = .045)   - No significant association between self-reported empathy (IRI) and social learning model parameters (all p_perm ≥ .320)
- **effect_size:** ηp² = 0.35 (action × valence interaction); d = 0.90 (overall accuracy vs. chance); r = −.273 (antisociality–β_loss social); R² = .41 (regression predicting β_loss social); r = .361 (motivation–β_loss social); r = .258 (anxiety–π_loss self)
- **learning_from:** Other (stranger partner) and self; monetary outcome feedback (win/loss)
- **learning_about:** World; correct go/no-go action for each stimulus  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RW with 8 params: 2β (β_win, β_loss), 1α, x (choice noise), b (constant go bias), 2π (π_win, π_loss), q (initial go bias) — "2βαxb2πq
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "βα", "family": "Rescorla-Wagner", "n_params": 2, "metric": "iBIC"} - {"name": "βαxb", "family": "Rescorla-Wagner", "n_params": 4, "metric": "iBIC"} - {"name": "βαxbπ", "family": "Rescorla-Wagner", "n_params": 5, "metric": "iBIC"} - {"name": "2βαxbπ", "family": "Rescorla-Wagner", "n_params": 6, "metric": "iBIC"} - {"name": "βαxb2πq", "family": "Rescorla-Wagner", "n_params": 7, "metric": "iBIC"} - {"name": "2βαxb2πq", "family": "Rescorla-Wagner", "n_params": 8, "metric": "iBIC (winning)"}
- **model_mb_mf:** MF
- **model_params:** - α: learning rate (1 parameter; median values ranged .046–.053 across conditions) - β_win: sensitivity to rewards [S in social condition] - β_loss: sensitivity to punishments [S in social condition] - x: choice noise (irreducible noise) - b: constant go bias - π_win: Pavlovian bias for wins (approach in positive affective states) - π_loss: Pavlovian bias for losses (avoidance in negative affective states) [S in social condition] - q: initial go bias  Note: Mean fitted parameter values are reported only in transformed form in Supplementary Fig. 3 (supplement not accessible). Median α values ranged from .046 to .053 across conditions (reported in Discussion).
- **social_param:** β_win (social), β_loss (social) — sensitivity to partner's rewards and punishments, respectively. β_loss social is the key parameter: indexes how much a partner's monetary loss influences learning; negatively associated with antisociality.
- **social_param_name:** β_win
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** integrated Bayesian information criterion (iBIC)
- **how_model_fit:** individual-level-fit (hierarchical expectation-maximization using emfit_toolbox; iterates between MAP estimation with Laplacian approximation and group prior updating)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 61 (from 71 enrolled; 40 female, 21 male; age M = 23.0 ± 6.9, range 18–49); community adults from Washington, DC metro area
- **population_category:** healthy adults
- **population_age_range:** 18–49
- **ecological_validity:** Participants met stranger confederate partner face-to-face before task, increasing ecological validity. However, outcomes were monetary and delivered via computer task with no real social interaction during learning. Authors note results may not generalize to more complex or interactive social situations.
- **eligibility_flag:** 
- **concerns:** Small effect sizes (authors acknowledge); relatively low learning rates across conditions; no-go-to-win trial type poorly captured by model; self-report empathy (IRI) showed no association with task parameters, raising questions about construct validity; 6 subjects doubted partner actually received outcomes but were retained; female-overrepresented sample (66%)
- **limitations_reported:** Paradigm complexity may have hindered learning performance, obtaining relatively small learning rates across conditions; a superior unspecified model likely exists that could better account for differences between self and social learning; use of self-report questionnaires assessed trait but not state empathy; results may not apply to more complex or interactive social situations; participant sample overrepresented females; effect sizes were small, suggesting replication in larger and more diverse samples will be important
- **limitations_categorized:** task complexity; model specification limitations; reliance on trait self-report measures; limited ecological validity; sample demographics bias; small effect sizes; limited generalizability
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
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params (MEDIUM): Exact mean fitted values for all parameters not available in main text; median α values (.046–.053) stated in Discussion; transformed parameters in Supplementary Fig. 3 (supplement not accessible) - wc_guidelines rule 3 (MEDIUM): Posterior predictive simulation was done post-fitting; unclear whether pre-fitting simulation was conducted - wc_guidelines rules 5 & 6 (MEDIUM): Parameter and model recovery described as in supplement (Supplementary Fig. 2), which could not be directly verified
- **cannot_find:** Exact untransformed mean fitted parameter values for all 8 parameters (reported only in supplement); iBIC values for all models in the pooled distribution (only self/social/no-one unpooled iBIC values are partially reported); Supplementary formulas for action weight calculation
- **other_notes:** Supplement not accessible (no supplement file found in papers folder). The paper references Supplementary Materials including Tables 2–4, Figs. 1–5, and formulas for action weights. Data are publicly available on OSF (https://osf.io/u9fx3/). The paper uses the emfit_toolbox (https://github.com/mpc-ucl/emfit) for model fitting. Task adapted from Mkrtchian et al. (2017) and Guitart-Masip et al. (2011, 2012).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_social_weight
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = empathy_vicarious
- tax_rr_topic_empathy_vicarious
- tax_rr_topic_prosocial_altruism
- tax_social_nonsocial_comparison
- tax_topic_empathy_vicarious
- tax_topic_prosocial_altruism
