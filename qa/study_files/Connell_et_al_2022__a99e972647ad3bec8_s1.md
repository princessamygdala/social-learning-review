# Connell et al. (2022)

- **study_id:** `a99e972647ad3bec8_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** O'Connell, K., Walsh, M., Padgett, B., Connell, S., & Marsh, A. A. (2022). Modeling variation in empathic sensitivity using go/no-go social reinforcement learning. *Affective Science*, *3*, 603–615. https://doi.org/10.1007/s42761-022-00119-4
- **citation_short:** Connell et al. (2022)
- **doi:** 10.1007/s42761-022-00119-4
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofPsychology,GeorgetownUniversity,; mit quantitative investiga-; ethatlearningforanother; University,; ethemost; emails: kmo52@georgetown.edu
- **code_url:** https://github.com/mpc-ucl/emfit

## Computational level
- **study_focus:** Empathic sensitivity / prosocial learning -- quantifying individual differences in sensitivity to others' rewards and punishments during reinforcement learning, and their association with antisociality.
- **study_focus_short:** Empathic sensitivity / prosocial learning -- quantifying individual differences
- **learning_mode_description:** - Learning mode: Learning to perform go/no-go actions to obtain rewards or avoid punishments for self, a stranger partner, or no one.   - Learning from:     - Source type (non-social): self (own actions and resulting feedback)     - Source content (non-social): outcome (monetary win/loss/no-change feedback)   - Learning about:     - Target type (social): other (stranger study partner) [social condition]; self [self condition]; world [no-one condition]     - Target content (social): outcome (monetary rewards and punishments for partner) [social condition]; (non-social): outcome [self/no-one conditions]
- **task_description:** Participants completed a go/no-go reinforcement learning task where they learned the correct action (button press or no press) for fractal images, with monetary outcomes (win/loss/no change) affecting themselves, a stranger study partner, or no one across counterbalanced blocks. The task fully crossed action requirement (go/no-go) with valence (win/avoid loss) across 720 trials (60 per trial type per condition).
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), single target (stranger confederate partner)
- **n_players:** single agent (1)
- **partner_type:** confederate
- **stimuli:** Abstract fractal images, monetary feedback (green up-arrow for win, red down-arrow for loss, yellow bar for no change)
- **method:** behavioural
- **method_full:** Behavioural
- **main_result:** - Main Results:   - Action x valence interaction on accuracy (ηp2 = 0.35, 95% CI [.16, .50])   - Main effect of condition on accuracy (ηp2 = 0.18, 95% CI [.06, .29])   - Main effect of action on accuracy (ηp2 = 0.47, 95% CI [.27, .59])   - Main effect of valence on accuracy (ηp2 = 0.22, 95% CI [.06, .38])   - Overall accuracy above chance (d = 0.90, 95% CI [0.60, 1.20])   - Social β_loss negatively correlated with antisociality (STAB Social Aggression) (r = −.273)   - Social β_win trend-level negative correlation with antisociality (r = −.246)   - Regression: antisociality predicted social β_loss after controlling for demographics and self β_loss (β = −.22; model R2 = .41)   - Regression: antisociality did NOT significantly predict social β_win after controls (β = −.13; model R2 = .35)   - Post-task motivation to avoid partner loss positively correlated with social β_loss (r = .361)   - Trait anxiety positively correlated with self Pavlovian avoidance bias π_loss (r = .258)   - Antisociality positively correlated with social learning rate α (r = .285)   - No significant association between IRI trait empathy and social β or π parameters   - Self-reported motivation: main effect of condition (ηp2 = .44, 95% CI [.30, .54])   - Effort ratings: main effect of condition (ηp2 = .28, 95% CI [.14, .40])
- **effect_size:** - Main Results:   - Action x valence interaction on accuracy (ηp2 = 0.35, 95% CI [.16, .50])   - Main effect of condition on accuracy (ηp2 = 0.18, 95% CI [.06, .29])   - Main effect of action on accuracy (ηp2 = 0.47, 95% CI [.27, .59])   - Main effect of valence on accuracy (ηp2 = 0.22, 95% CI [.06, .38])   - Overall accuracy above chance (d = 0.90, 95% CI [0.60, 1.20])   - Social β_loss negatively correlated with antisociality (STAB Social Aggression) (r = −.273)   - Social β_win trend-level negative correlation with antisociality (r = −.246)   - Regression: antisociality predicted social β_loss after controlling for demographics and self β_loss (β = −.22; model R2 = .41)   - Regression: antisociality did NOT significantly predict social β_win after controls (β = −.13; model R2 = .35)   - Post-task motivation to avoid partner loss positively correlated with social β_loss (r = .361)   - Trait anxiety positively correlated with self Pavlovian avoidance bias π_loss (r = .258)   - Antisociality positively correlated with social learning rate α (r = .285)   - No significant association between IRI trait empathy and social β or π parameters   - Self-reported motivation: main effect of condition (ηp2 = .44, 95% CI [.30, .54])   - Effort ratings: main effect of condition (ηp2 = .28, 95% CI [.14, .40])
- **learning_from:** Self; own action outcomes (monetary feedback: win/loss/no change)
- **learning_about:** Other (stranger partner's monetary outcomes) [social condition]; self (own monetary outcomes) [self condition]; world [no-one condition]  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Adapted RW go/no-go: 2βαxb2πq (8 params: β_win, β_loss, α, x, b, π_win, π_loss, q)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** | Model | Family | n_params | Metric | |---|---|---|---| | βα | Rescorla-Wagner | 2 | iBIC | | βαxb | Rescorla-Wagner | 4 | iBIC | | βαxbπ | Rescorla-Wagner | 5 | iBIC | | 2βαxbπ | Rescorla-Wagner | 6 | iBIC | | βαxb2πq | Rescorla-Wagner | 7 | iBIC | | 2βαxb2πq (winner) | Rescorla-Wagner | 8 | iBIC |  Each model tested in both pooled and unpooled distributions (pooled won for all).
- **model_mb_mf:** MF
- **model_params:** - β_win: outcome sensitivity for wins (scales reward in PE). Separate for each condition. [S] in social condition. - β_loss: outcome sensitivity for losses (scales punishment in PE). Separate for each condition. [S] in social condition. - α: learning rate (single, constant across conditions). Median values ranged .046–.053 across conditions. - x: irreducible choice noise parameter. - b: constant go bias (added to go action weight). - π_win: Pavlovian bias for wins (positive affective state biases approach). [S] in social condition. - π_loss: Pavlovian bias for losses (negative affective state biases avoidance). [S] in social condition. - q: initial go bias (initializes go action weight > 0).  Mean fitted values: Not reported as means; median α ranged from .046 to .053. Exact fitted means for other parameters not provided in main text or supplement (parameters shown only as transformed distributions in Supplementary Fig. 3). **Flagged**: exact mean fitted parameter values not reported.
- **social_param:** β_win [S] and β_loss [S] in the social condition -- index sensitivity to the partner's rewards and punishments respectively. β_loss in the social condition was the key parameter negatively associated with antisociality.
- **social_param_name:** β_win [S] and β_loss [S] in the social condition
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Integrated Bayesian Information Criterion (iBIC)
- **how_model_fit:** Group-level fit (hierarchical expectation-maximization using emfit toolbox; iterates between MAP inference with Laplacian approximation and updating group priors)
- **data_type_fit_to:** Choice behavior (go/no-go responses)

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study)
- **key_regions:** 
- **coordinates_peak:** N/A -- no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 61 (40 female, 21 male; age M = 23.0, SD = 6.9, range 18-49); recruited from community sample in Washington, DC metro area. 71 enrolled; 10 excluded (2 incomplete, 5 same-action >90%, 3 non-responsive). 6 additional subjects expressed doubt about social condition but were retained.
- **population_category:** healthy adults
- **population_age_range:** 18–49
- **ecological_validity:** Moderate-low. Participants met their study partner (a confederate) briefly before the task, adding some ecological validity. However, the task used abstract fractals and monetary outcomes in a lab setting. No real social interaction occurred during the task. Authors note results may not apply to more complex or interactive social situations.
- **eligibility_flag:** 
- **concerns:** - Relatively small sample (N=61) with overrepresentation of females (66%) - Small effect sizes for key correlations - Confederate partner (not genuine social interaction) - Small learning rates (median α = .046-.053) suggest task complexity may have hindered learning - No significant association with self-reported empathy (IRI) despite theoretical predictions - 6 subjects expressed doubt about reality of social condition outcomes - No mean fitted parameter values reported (only medians for α, distributions in supplementary figure)
- **limitations_reported:** Task complexity may have hindered learning performance, as evidenced by small learning rates; model fits are relative and a superior unspecified model may exist that better accounts for differences between self and social learning; use of self-report questionnaires that assessed trait but not state empathy; participant sample overrepresented females; effect sizes were small suggesting replication in larger and more diverse samples is important; ecological validity limited as results may not apply to more complex or interactive social situations; the model does not fully capture subjects' extremely poor performance on no-go to win trial type.
- **limitations_categorized:** Task complexity; model specification limitations; reliance on trait self-report measures; sample composition (gender imbalance); small effect sizes; limited ecological validity; limited generalizability; model fit limitations (poor fit for specific trial types).
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 10
- **wc_total:** 10.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM confidence for mean fitted values -- only median α reported (.046-.053); other parameter means not reported, only distributions shown in supplementary figure - social_param mapping to empathy: LOW confidence -- β parameters were NOT associated with IRI empathy scores despite predictions; interpretation as "empathic sensitivity" is theoretical
- **cannot_find:** Exact mean (or median) fitted values for all 8 parameters across conditions (only α medians given); exact iBIC values for non-winning models (only winning model iBIC = 4.62x10^4 reported in supplement figure caption)
- **other_notes:** This study applies the Guitart-Masip go/no-go RL paradigm to a social context for the first time. Key novel finding: antisociality (STAB Social Aggression) is negatively associated with modeled sensitivity to a stranger's losses (β_loss social), even after controlling for self-oriented loss sensitivity. The null finding for IRI empathy is notable and discussed at length. The authors used emfit_toolbox for hierarchical EM fitting. Data available on OSF. The "no one" condition serves as a useful non-social control. The pooled distribution (fitting all conditions together) outperformed the unpooled distribution for all models.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_target = partly
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = empathy_vicarious
- tax_rr_topic_empathy_vicarious
- tax_rr_topic_prosocial_altruism
- tax_social_nonsocial_comparison
- tax_topic_empathy_vicarious
- tax_topic_prosocial_altruism
