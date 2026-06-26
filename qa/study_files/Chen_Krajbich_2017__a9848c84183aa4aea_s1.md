# Chen & Krajbich (2017)

- **study_id:** `a9848c84183aa4aea_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Chen, W. J., & Krajbich, I. (2017). Computational modeling of epiphany learning. *Proceedings of the National Academy of Sciences*, *114*(18), 4637–4642. https://doi.org/10.1073/pnas.1618161114
- **citation_short:** Chen & Krajbich (2017)
- **doi:** 10.1073/pnas.1618161114
- **publication_type:** peer-reviewed journal (pnas)
- **year:** 2017.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** DepartmentofEconomics,TheOhioStateUniversity,Columbus,OH43210;andbDepartmentofPsychology,TheOhioStateUniversity,Columbus,; mit to the optimal strategy in which each of two players chooses an integer from 0 and 10; University,PaloAlto,CA,andapprovedFebruary23,2017(receivedforreviewNovember1,2016); mitedpriorresearch becauseitssuperiorsignal-to-noiseratio(relativetobrainimag-; mit to a strategy at any time, eliminating problemwhilereceivingfeedback; ethathasanopti- TousethesemethodstostudyEL,wesoughtadecisionset-; ether subjects truly undergo EL in this setting; lable options and accumulates evi
- **code_url:** 

## Computational level
- **study_focus:** Epiphany learning — sudden insight-driven strategy discovery in a strategic game, modeled as latent evidence accumulation rather than gradual reinforcement learning.
- **study_focus_short:** Epiphany learning
- **learning_mode_description:** - Learning mode: Learning from own game outcomes about the optimal strategy in a two-person strategic game   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (win/loss feedback from game)   - Learning about:     - Target type (non-social): world (optimal strategy/dominant strategy in the game)     - Target content (non-social): action/policy (choosing 0 as the dominant strategy)
- **task_description:** Participants repeatedly played a two-person beauty contest game (30 trials) against different opponents drawn from a database, choosing an integer from 0 to 10 with the goal of being closer to 0.9 times the average of both numbers. After each choice, participants could commit to their number for the remainder of the study for a small monetary bonus.
- **task_paradigm:** Beauty contest game
- **players:** Single agent (participant), dyadic (opponent from database; different each trial)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Integers 0–10 displayed in circular arrangement, binary feedback (win/lose/tie), monetary outcomes (10 ECU per win)
- **method:** behavioural
- **method_full:** Behavioural + eye-tracking (fixation patterns and pupil dilation)
- **main_result:** - 53% (K-S) or 66% (model comparison) of subjects classified as epiphany learners - Commit-to-0 subjects' dwell time on 0 positively correlated with model-estimated evidence ev(t-1) (P < 0.001); this effect was significantly smaller for commit > 0 subjects (P < 0.001) - Refixation in first 3 trials correlated with commit timing for commit-to-0 group (r, P = 0.006) but not commit > 0 (P = 0.282) - Dwell time on "yes" button jumped significantly more at commit trial for commit-to-0 vs commit > 0 subjects (14% difference, P = 0.04) - Commit-to-0 subjects looked significantly more at game outcome approaching commit trial (P = 0.003); commit > 0 subjects looked more at opponent's choice (P = 0.026) - Pupil dilation positively correlated with prediction error for commit-to-0 subjects (P = 0.001); only marginally for commit > 0 (P = 0.056) - EL model outperformed RL model for commit-to-0 subjects (mean BIC: EL = 109.94 vs RL = 173.63 for base models; Table S1) - No formal effect sizes (d, r², etc.) reported; results presented as regression coefficients with p-values
- **effect_size:** LOW confidence — no formal effect sizes reported; only p-values and regression coefficients
- **learning_from:** Self; own game outcomes (win/loss against opponent)
- **learning_about:** World; optimal strategy (dominant strategy of choosing 0) in the beauty contest game  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Epiphany Learning (EL) model — sequential-sampling/random-walk: ev(t) = ev(t-1) + d × (-1)^I(t), where I(t) = 1 if negative evidence, 0 otherwise; epiphany occurs when ev(t) >= 1. Pre-epiphany choice probability of 0 = q₁; post-epiphany = q₂. (3 params: d, q₁, q₂)
- **model_family:** Drift-diffusion
- **model_class:** Evidence accumulation
- **all_models_tested:** 1. EL base model (___ ; no extensions) — 3 params (d, q₁, q₂); BIC comparison 2. EL with generalization (G__) — 4 params (d, q₁, q₂, K); BIC 3. EL with negative epiphanies (_N_) — 3 params; BIC 4. EL with any epiphany (__A) — 4 params (d, q₁, q₂, c); BIC 5. EL GN_ — 4 params; BIC 6. EL GNA — 5 params; BIC (only for commit > 0) 7. EL _NA — 4 params; BIC (only for commit > 0) 8. EL G_A — 5 params; BIC 9. RL base model (___ ; experience-weighted attraction) — 3 params (λ, φ, A₁(0)); BIC 10. RL with generalization (G__) — 4 params; BIC 11. RL with any epiphany (__A) — 4 params; BIC 12. RL G_A — 5 params; BIC
- **model_mb_mf:** MF (model-free; evidence accumulation from direct outcomes, no model of opponent or environment structure)
- **model_params:** - d: evidence increment per trial (0 to 1); free parameter - q₁: pre-epiphany probability of choosing 0; free parameter - q₂: post-epiphany probability of choosing 0; free parameter - RL alternative: λ (sensitivity/temperature), φ (discount factor for attraction, 0 to 1), A₁(0) (initial attraction for non-0 choices)  No social parameters — evidence accumulation is based on own outcomes only.
- **social_param:** None. The model contains no explicitly social parameters; evidence accumulation is driven by own win/loss outcomes.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion); also negative log-likelihood reported per subject (Table S8). K-S test used separately to identify change points.
- **how_model_fit:** Individual-level fit (maximum likelihood estimation per subject, using quasi-Newton method with 165 starting points for EL and 572 for RL)
- **data_type_fit_to:** Choice behavior (probability of choosing 0 on each trial, up to commit trial)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (eye-tracking study, no brain imaging)
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 59 (undergraduates, Ohio State University); additional N = 28 for database generation experiment. No age range reported.
- **population_category:** undergraduates
- **population_age_range:** 
- **ecological_validity:** Low-moderate. Stylized strategic game (two-person beauty contest) with abstract numerical choices; opponents drawn from a pre-recorded database rather than real-time interaction; commitment mechanism is artificial. However, repeated feedback and the eye-tracking setup provide process-level data.
- **eligibility_flag:** HIGH confidence — the paper is borderline for social learning inclusion; the social context is incidental to the learning mechanism
- **concerns:** - The "social" aspect is minimal: the dominant strategy is independent of the opponent's choice, making this essentially a non-social optimization problem embedded in a game-theoretic frame - Opponents are from a database, not live — no genuine social interaction - No formal effect sizes (Cohen's d, r², etc.) reported; results rely on p-values from regressions - Model comparison is done via BIC but no formal Bayesian model selection (e.g., exceedance probability) - No out-of-sample validation or posterior predictive checks for the winning model - Eye-tracking predictions are qualitative rather than quantitatively derived from the model
- **limitations_reported:** It remains to be seen how well the model will generalize to other settings"; "not all learning can be classified as EL"; "it remains to be seen what makes different problems more or less amenable to EL"; the RL model presented is simple and "there are certainly more sophisticated RL models in the literature
- **limitations_categorized:** Limited generalizability; task simplicity; model comparison limited to simple RL baseline; no parameter recovery; no model recovery
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.0
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = general
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_model_MF
- tax_model_drift_diffusion
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_drift_diffusion
- tax_rr_model_family = drift_diffusion
- tax_rr_param_PE_signal
- tax_rr_primary_topic = strategic_reasoning
- tax_rr_topic_strategic_reasoning
- tax_topic_strategic_reasoning
