# Topel et al. (2024)

- **study_id:** `aececc2e97bdbec2b_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Topel, S., Ma, I., van Duijvenvoorde, A. C. K., van Steenbergen, H., & de Bruijn, E. R. A. (2024). Adapting to uncertainty: The role of anxiety and fear of negative evaluation in learning in social and non-social contexts. *Journal of Affective Disorders, 363*, 310--319. https://doi.org/10.1016/j.jad.2024.07.066
- **citation_short:** Topel et al. (2024)
- **doi:** 10.1016/j.jad.2024.07.066
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Psychology
- **affiliations_raw:** mitations: While transdiagnostic and dimensional approaches are important for investigating disturbed social; ethods: We implemented a modified trust game (N =190), where participants either retained or lost their; University, Institute of Psychology, Wassenaarseweg 52, 2333 AK Leiden, The Netherlands; University, Wassenaarseweg 52, 2333 AK Leiden, the Netherlands; Institute for Brain and Cognition, Leiden, The Netherlands; ether individuals with higher levels of trait; lable online 21 July 2024; lable at ScienceDirect; emails: s.topel@fsw.leidenuniv.nl
- **code_url:** https://osf.io/62mc7/

## Computational level
- **study_focus:** Learning under uncertainty in social vs. non-social contexts; role of trait anxiety and fear of negative evaluation (FNE) in reinforcement learning with stable/volatile outcome contingencies.
- **study_focus_short:** Learning under uncertainty in social vs. non-social contexts
- **learning_mode_description:** - Learning mode: Learning from social partner's reciprocation outcomes about the probability of loss associated with each partner, in a volatile or stable environment.   - Learning from:     - Source type (social): other (two anonymous online "players" acting as responders)       - Also non-social control: world (slot machines)     - Source content (social): outcome (loss vs. no-loss following trust/investment decision)       - Non-social control content (non-social): outcome (loss vs. no-loss from slot machine)   - Learning about:     - Target type (social): other (which responder minimizes losses)       - Non-social control: world (which slot machine minimizes losses)     - Target content (social): outcome (probability of loss associated with each player)       - Non-social control content (non-social): outcome (probability of loss for each machine)
- **task_description:** In a modified trust game (social task), participants as "deciders" chose which of two online "responders" to share points with on each trial; the responder either reciprocated (no loss) or kept all points (loss), with loss probabilities either stable (75/25%) or volatile (80/20% reversing every 15 trials). A matched non-social control task replaced players with slot machines.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (2 fictitious online players per block in social task; 2 slot machines in non-social task)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Colorful avatars (social task), colorful slot machines (non-social task), varying point magnitudes (10--80), binary feedback (loss vs. no-loss)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Higher learning rates in social vs. non-social task (B = -0.02, 95% CI [-0.03, -0.02], p < .001)   - More stay behavior after no-loss vs. loss (OR = 0.61, 95% CI [0.58, 0.65])   - Feedback x Task interaction on stay/switch behavior (OR = 1.11, 95% CI [1.07, 1.14])   - FNE x Feedback interaction on stay/switch in social task (OR = 0.91, 95% CI [0.85, 0.94])   - FNE main effect on learning rates in social task (B = 0.02, 95% CI [0.00, 0.04], p = .030)   - FNE x Task x Feedback 3-way interaction (OR = 1.04, 95% CI [1.01, 1.08], p = .025)   - Trait anxiety: no significant effect on learning rate adjustment (all ps > .13)   - No significant environment (stable vs. volatile) effect on learning rates (all ps > .59)   - FNE predicted higher uncertainty in social task (B = 0.26, 95% CI [0.07, 0.45], p = .008)
- **effect_size:** - Main Results:   - Higher learning rates in social vs. non-social task (B = -0.02, 95% CI [-0.03, -0.02], p < .001)   - More stay behavior after no-loss vs. loss (OR = 0.61, 95% CI [0.58, 0.65])   - Feedback x Task interaction on stay/switch behavior (OR = 1.11, 95% CI [1.07, 1.14])   - FNE x Feedback interaction on stay/switch in social task (OR = 0.91, 95% CI [0.85, 0.94])   - FNE main effect on learning rates in social task (B = 0.02, 95% CI [0.00, 0.04], p = .030)   - FNE x Task x Feedback 3-way interaction (OR = 1.04, 95% CI [1.01, 1.08], p = .025)   - Trait anxiety: no significant effect on learning rate adjustment (all ps > .13)   - No significant environment (stable vs. volatile) effect on learning rates (all ps > .59)   - FNE predicted higher uncertainty in social task (B = 0.26, 95% CI [0.07, 0.45], p = .008)
- **learning_from:** Other's reciprocation outcomes (social: loss/no-loss from player decisions); world (non-social: loss/no-loss from slot machines)
- **learning_about:** Other's loss probability / trustworthiness (social); world's loss probability (non-social)  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Rescorla-Wagner with probability prediction error (PPE), additive choice rule: 4 learning rates (alpha per task x environment), 1 beta (decision noise), 1 phi (weight for probability vs. magnitude difference in choice). "RW-PPE additive (4 alphas, 1 beta, 1 phi)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. Additive model, 4 alphas + 1 beta + 1 phi (6 params) -- WINNING 2. Additive model, all parameters varied by condition (varied alphas, betas, phis) 3. Additive model, varied phi + alphas by condition 4. Additive model with separate loss/no-loss learning rates 5. Multiplicative model, 4 alphas + 1 beta + 1 eta (6 params) 6. Multiplicative model, all parameters varied by condition 7. Multiplicative model, varied eta + alphas by condition 8. Multiplicative model with separate loss/no-loss learning rates 9. Betrayal aversion model (additive version) 10. Betrayal aversion model (multiplicative version)  (10 models total, compared using BIC; best additive vs. best multiplicative compared via bootstrapped 95% CI of BIC differences: Median = -15.57, CI [-18.89, -11.56] favoring additive)
- **model_mb_mf:** MF
- **model_params:** - alpha_social_stable: learning rate for social stable condition - alpha_social_volatile: learning rate for social volatile condition - alpha_nonsocial_stable: learning rate for non-social stable condition - alpha_nonsocial_volatile: learning rate for non-social volatile condition - beta: inverse temperature / decision noise - phi: weight parameter (0-1) for probability difference vs. magnitude difference in choice rule  No parameters are explicitly marked as social-specific in the model; the social dimension is captured by fitting separate alphas per task context.
- **social_param:** alpha_social_stable, alpha_social_volatile -- learning rates estimated separately for the social task, capturing social-specific learning speed. No structurally distinct social parameter in the model formula.
- **social_param_name:** alpha_social_stable
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion); bootstrapped 95% CI of BIC differences for final comparison
- **how_model_fit:** individual-level-fit (MLE using nloptr on HPC)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

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
- **sample_size:** N = 190 (95 female, 95 male; ages 18-36, M = 24.64, SD = 4.32); originally recruited 250, 60 excluded per preregistered and adjusted criteria
- **population_category:** healthy adults
- **population_age_range:** 18–36
- **ecological_validity:** Online study on Prolific with cover story (participants believed they played with real people); enhanced ecological validity by not providing explicit instructions about volatility structure; however, interactions were with fictitious players and identity was anonymous, limiting social realism. Loss frame only (no gain condition).
- **eligibility_flag:** 
- **concerns:** - No gain condition (loss frame only), limiting generalizability of social learning findings - FNE analyses were exploratory (not preregistered), increasing risk of Type I error - Trait anxiety and FNE were highly correlated (r = 0.58), making it difficult to disentangle their independent contributions - No volatility effect on learning rates found (deviates from prior literature), possibly due to task design - 34/189 participants reported some doubt about playing with real players in the funnel debriefing - Random chance model exclusion criterion used (2 participants) -- details sparse
- **limitations_reported:** Online study with limited control over participant environment, potentially yielding noisier data; healthy sample with low depressive symptom severity precluded depression analyses; dimensional approach may not generalize to clinical anxiety populations; task design did not allow separate learning about "better" vs. "worse" stimuli; FNE findings may be more pronounced with known-identity players; larger samples with multiple related measures needed to identify symptom-specific dimensions
- **limitations_categorized:** limited ecological validity; limited generalizability (subclinical sample); task simplicity (no valence-specific learning); online data collection noise; sample characteristics (low depression variance); construct specificity (FNE vs. trait anxiety overlap)
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - social_param: MEDIUM -- no structurally distinct social parameter; social dimension captured by separate alpha fitting per task - wc_3 (simulate): MEDIUM -- parameter recovery implies some simulation, but no explicit pre-fitting simulation described - wc_8 (validate): MEDIUM -- no formal posterior predictive check; only random-chance comparison - effect_size: MEDIUM -- most effects reported as regression coefficients (B) and odds ratios with CIs rather than standardized effect sizes (Cohen's d, etc.)
- **cannot_find:** Exact fitted mean parameter values for the winning model (alphas, beta, phi) -- paper reports learning rate analyses but not the raw fitted parameter means/SDs in main text or accessible supplement text. Formula is fully specified but mean fitted values are not explicitly tabulated.
- **other_notes:** The supplement is extensive (72+ tables) but the .txt extraction only captures table labels, not table contents. The parameter recovery results (Figure S2) show strong correlations but exact r values are only visible in the figure. The paper compares social vs. non-social learning within-subjects, making it a good design for isolating social-specific effects. FNE findings, though exploratory, converge across model-free (stay/switch) and model-based (learning rate) analyses.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_anxiety
- pop_healthy_adults
- rr_pop_anxiety
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target+context
- spec_source = partly
- spec_target = partly
- tax_domain_C_exchange_interdependence
- tax_domain_G_uncertainty_volatility
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = G_uncertainty_volatility
- tax_rr_domain_C_exchange_interdependence
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = volatility
- tax_rr_secondary_topic = trust
- tax_rr_topic_trust
- tax_rr_topic_volatility
- tax_social_nonsocial_comparison
- tax_topic_trust
- tax_topic_volatility
