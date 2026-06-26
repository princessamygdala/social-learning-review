# DeJoseph et al. (2024)

- **study_id:** `a5f0d9e7021894afb_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** DeJoseph, M. L., Thomas, K. M., Frankenhuis, W. E., & Berry, D. (2024). Learning in context: Socioemotional stimuli enhance cognitive learning processes but not psychophysiological engagement in early adolescence. [Preprint]. https://osf.io/xqj8w/
- **citation_short:** DeJoseph et al. (2024)
- **doi:** Not available (OSF preprint; no DOI found in text)
- **publication_type:** preprint
- **year:** 2024.0
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Contextual modulation of reinforcement learning by socioemotional stimulus salience in adolescence
- **study_focus_short:** Contextual modulation of reinforcement learning by socioemotional stimulus
- **learning_mode_description:** - Learning mode: Learning from reward/punishment feedback about stimulus-outcome associations, comparing socioemotional vs. non-emotional stimulus contexts   - Learning from:     - Source type (non-social): world     - Source content (non-social): outcome (reward: +100 points; punishment: -100 points)   - Learning about:     - Target type (non-social): world (stimulus-outcome associations)     - Target content (non-social): stimulus (value of line drawings or IAPS images)
- **task_description:** Youth completed a within-person probabilistic reversal learning task with two stimulus versions (non-emotional line drawings vs. socioemotionally-salient IAPS images). In each version, participants learned to press or withhold pressing for 12 stimuli associated with reward (+100 pts) or punishment (-100 pts), with half of contingencies reversing after 96 trials.
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), no social interaction partner
- **n_players:** single agent (1)
- **partner_type:** human (live)
- **stimuli:** Line drawings (non-emotional version); IAPS images rated high in arousal (positive and negative scenes; socioemotional version); binary feedback (win/lose 100 points with auditory cues)
- **method:** behavioural
- **method_full:** behavioural (with psychophysiology/ECG)
- **main_result:** - Youth performed slightly more optimally in socioemotional vs. non-emotional version (B = 6.42, 95% CrI = [-1.42, 14.22], d = 0.22) - Punishment learning rate higher in socioemotional version (B = 0.11, 95% CrI = [0.04, 0.18], d = 0.46) - Reward learning rate higher in socioemotional version (B = 0.10, 95% CrI = [0.03, 0.16], d = 0.52) - Inverse temperature showed no main effect of version (B = 0.01, 95% CrI = [-0.16, 0.18], d = 0.02) but a version x age interaction (B = 0.25, 95% CrI = [0.07, 0.43]) - Reward learning rate positively associated with cardiac complexity (B = 0.22, 95% CrI = [0.09, 0.35], β = 0.29)
- **effect_size:** d = 0.22 (performance); d = 0.46 (punishment LR); d = 0.52 (reward LR); d = 0.02 (inverse temperature); β = 0.29 (reward LR → cardiac complexity)
- **learning_from:** World; reward/punishment feedback on chosen stimulus (+/- 100 points)
- **learning_about:** World; value of stimulus-outcome associations (line drawings or IAPS images)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Reward-Punishment RL model for probabilistic reversal learning (α_punishment, α_reward, β_inv_temp) — "prl_rp_multipleB" from hBayesDM
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Reward-Punishment Model for Multiple-Block Probabilistic Reversal Learning (prl_rp_multipleB)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "Bayesian hierarchical fitting via hBayesDM"}]
- **model_mb_mf:** MF
- **model_params:** - α_punishment (punishment learning rate): sensitivity to punishment prediction errors; socioemotional version M ≈ higher by 0.11 [S: No] - α_reward (reward learning rate): sensitivity to reward prediction errors; socioemotional version M ≈ higher by 0.10 [S: No] - β (inverse temperature): balance between exploration vs. exploitation; nearly identical across versions [S: No] - (Mean fitted values not reported directly in text; descriptives in Table 3 referenced but not fully reproduced in accessible text)
- **social_param:** None — no explicitly social parameters in the computational model
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** No formal model comparison across competing models; single model fitted via Bayesian hierarchical estimation (hBayesDM with default parameters); Bayesian multilevel models used for statistical inference on parameters (brms; evidence ratios / Bayes factors, 95% credible intervals)
- **how_model_fit:** individual-level-fit (hierarchical Bayesian; hBayesDM estimates group and individual-level parameters)
- **data_type_fit_to:** choice behavior (trial-by-trial press/no-press decisions)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging; psychophysiology only — cardiac complexity via DFA of heart rate variability)
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 56 (behavioural); N = 55 (psychophysiology, 1 excluded due to BIOPAC malfunction); ages 12–15 (M = 13.3 years; 51.8% female)
- **population_category:** adolescents
- **population_age_range:** 12–15
- **ecological_validity:** Within-person design with socioemotionally-salient IAPS images improves upon abstract-stimulus-only paradigms; however, stimuli are static images on a screen with no real social interaction; convenience sample of predominantly White, upper-middle-class youth limits ecological generalizability
- **eligibility_flag:** Stimulus learning is not inherently social — the task involves learning stimulus-outcome associations where socioemotional images serve as contextual modulators, not social agents. The "social" element is the stimulus content (IAPS images of social scenes), not social interaction or social learning per se. FLAG: borderline social context — socioemotional stimulus modulation of non-social reinforcement learning.
- **concerns:** (1) Only one computational model tested — no model comparison with alternatives; (2) The learning task is fundamentally non-social (probabilistic reversal learning with stimulus-outcome associations) — socioemotional content of images may not constitute "social learning" as defined by inclusion criteria; (3) Small sample (N=56) limits between-person inference; (4) Preprint — not peer-reviewed; (5) No parameter recovery or model recovery reported; (6) Cross-sectional design limits developmental inference
- **limitations_reported:** Small convenience sample due to COVID-19 pandemic, limiting model types and between-person inferences; sample predominantly White and upper middle class, limiting generalizability; single commonly used RL model fitted without comparing alternative models with different parameter sets; cross-sectional design precluded examination of developmental change over time; reliance on static visual images may have limited depth of attention and arousal; IAPS images subject to featural confounds interacting with prior life experience; socioemotional stimulus set too broad to examine fine-grained stimulus category effects; heart rate may have been too peripheral a measure to detect meaningful contextual differences
- **limitations_categorized:** sample size; limited generalizability; limited model comparison; cross-sectional design; task simplicity; stimulus confounds; measurement sensitivity
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 4.5
- **wc_total:** 4.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - doi: LOW — no DOI found in paper text; OSF link provided but no formal DOI - social_param: HIGH — confirmed none present - model_params mean fitted values: MEDIUM — descriptive values referenced in Table 3 but exact values not accessible in text - eligibility_flag: MEDIUM — borderline social learning; socioemotional stimulus content modulates non-social RL task - all_models_tested: HIGH — only one model tested, explicitly stated
- **cannot_find:** - Exact mean fitted parameter values (referenced in Table 3 but not fully reproduced in accessible text) - DOI (preprint on OSF, no DOI assigned) - Supplement content (no supplement file found in papers/ folder; supplement referenced extensively in paper)
- **other_notes:** This is a preprint (not peer-reviewed) from OSF. The paper is primarily about developmental reinforcement learning in adolescents with a within-person manipulation of stimulus socioemotional salience. The "social" aspect is limited to the content of the stimuli (IAPS images depicting social scenes) rather than any social interaction, social agent, or social learning mechanism. The computational model is a standard reward-punishment RL model with no social parameters. Supplement not accessible — referenced extensively for prior-posterior checks, descriptive histograms, convergence diagnostics, and DFA examples but no _Supplements file found in papers/ folder.
- **re_extract_flag:** false (full text accessible; supplement not found but main text extraction is complete)

## Taxonomy / categorization (active codes only)
- pop_adolescents
- rr_pop_adolescents
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = general
- spec_locus = source+target+context
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_temperature
- tax_popclass_developmental
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_temperature
- tax_rr_primary_topic = threat_fear
- tax_rr_topic_threat_fear
- tax_topic_threat_fear
