# DeJoseph (2023)

- **study_id:** `abb19da2267bf8662_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** DeJoseph, M. L. (2023). *Contextual influences on cognitive and psychophysiological mechanisms of learning in early adolescence* [Doctoral dissertation, University of Minnesota]. ProQuest Dissertations Publishing (30522997).
- **citation_short:** DeJoseph (2023)
- **doi:** Not reported (ProQuest Number: 30522997)
- **publication_type:** thesis
- **year:** 2023.0
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Reinforcement learning modulated by socioemotional context in adolescence — examining how socioemotionally salient stimuli (vs. neutral) modulate value-updating (learning rates) and decision-making (inverse temperature) during probabilistic reversal learning, and how these relate to cardiac psychophysiology.
- **study_focus_short:** Reinforcement learning modulated by socioemotional context in adolescence
- **learning_mode_description:** - Learning mode: Learning from reward/punishment feedback about stimulus-outcome associations, modulated by socioemotional salience of stimuli   - Learning from:     - Source type (non-social): world (task environment)     - Source content (non-social): outcome (reward/punishment feedback)   - Learning about:     - Target type (non-social): world (stimulus-outcome contingencies)     - Target content (non-social): stimulus (value of stimuli — which to press/avoid)
- **task_description:** Adolescents completed two versions of a probabilistic reversal learning task (adapted from Finger et al., 2008) in counterbalanced order: one with non-emotional line drawings and one with socioemotionally salient IAPS images. In each version, youth learned to press or withhold pressing on stimuli associated with reward (+100 points) or punishment (-100 points), with half the contingencies reversing after 96 trials. 768 total trials (384 per version), 48 stimulus-outcome pairs total.
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), no social interaction partner
- **n_players:** single agent (1)
- **partner_type:** human (live)
- **stimuli:** Line drawings (non-emotional version); IAPS images rated high in arousal depicting positive (e.g., happy family, money) and negative (e.g., neighborhood violence, couple fighting) socioemotional scenes (socioemotional version); binary feedback (win/lose 100 points with auditory cues)
- **method:** behavioural
- **method_full:** behavioural (with cardiac psychophysiology via ECG/HRV)
- **main_result:** - Main Results:   - Youth performed more optimally in the socioemotional vs. non-emotional version (B = 6.42, 95% CrI = [-1.42, 14.22], d = 0.22; modest Bayesian evidence)   - Higher punishment learning rates in socioemotional vs. non-emotional version (B = 0.11, 95% CrI = [0.04, 0.18], d = 0.46; very strong Bayesian evidence, ER ~14x)   - Higher reward learning rates in socioemotional vs. non-emotional version (B = 0.10, 95% CrI = [0.03, 0.16], d = 0.52; very strong Bayesian evidence, ER ~12x)   - No main effect of version on inverse temperature (B = 0.01, 95% CrI = [-0.16, 0.18], d = 0.02)   - Version x age interaction on inverse temperature (B = 0.25, 95% CrI = [0.07, 0.43]): older youth more exploitative in socioemotional condition   - Reward learning rate positively associated with cardiac complexity (B = 0.22, 95% CrI = [0.09, 0.35], std. beta = 0.29; very strong Bayesian evidence, ER ~15x)   - No meaningful effect of version on cardiac complexity (B = 0.01, 95% CrI = [-0.03, 0.05])  ---  ### 6. Winning Model
- **effect_size:** - Main Results:   - Youth performed more optimally in the socioemotional vs. non-emotional version (B = 6.42, 95% CrI = [-1.42, 14.22], d = 0.22; modest Bayesian evidence)   - Higher punishment learning rates in socioemotional vs. non-emotional version (B = 0.11, 95% CrI = [0.04, 0.18], d = 0.46; very strong Bayesian evidence, ER ~14x)   - Higher reward learning rates in socioemotional vs. non-emotional version (B = 0.10, 95% CrI = [0.03, 0.16], d = 0.52; very strong Bayesian evidence, ER ~12x)   - No main effect of version on inverse temperature (B = 0.01, 95% CrI = [-0.16, 0.18], d = 0.02)   - Version x age interaction on inverse temperature (B = 0.25, 95% CrI = [0.07, 0.43]): older youth more exploitative in socioemotional condition   - Reward learning rate positively associated with cardiac complexity (B = 0.22, 95% CrI = [0.09, 0.35], std. beta = 0.29; very strong Bayesian evidence, ER ~15x)   - No meaningful effect of version on cardiac complexity (B = 0.01, 95% CrI = [-0.03, 0.05])  ---  ### 6. Winning Model
- **learning_from:** World; reward/punishment outcome feedback on task stimuli
- **learning_about:** World; stimulus-outcome contingencies (which stimuli yield reward vs. punishment)  ---  ### 4. Computational Problem  What cognitive mechanisms (value-updating speed and exploration-exploitation balance) underlie reinforcement learning in adolescence, and how does the socioemotional salience of learning stimuli modulate these mechanisms? (Prediction / evaluation)
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Reward-Punishment RL model for multiple-block probabilistic reversal learning (prl_rp_multipleB from hBayesDM): 2 learning rates ($\alpha_{rew}$, $\alpha_{pun}$) + 1 inverse temperature ($\beta$)
- **model_family:** Q-learning
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Reward-Punishment RL (prl_rp_multipleB)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "hBayesDM default (hierarchical Bayesian)"}]  Note: Only one computational model was tested. Multiple Bayesian multilevel regression models were compared for the outcome analyses (version-only vs. version + age vs. version x age), compared via WAIC and LOOIC — but these are statistical outcome models, not competing computational learning models.  ---  ### 8. Model Comparison
- **model_mb_mf:** MF
- **model_params:** - $\alpha_{rew}$ (reward learning rate, 0 < $\alpha$ < 1): scales positive prediction errors; socioemotional version mean slightly higher than non-emotional - $\alpha_{pun}$ (punishment learning rate, 0 < $\alpha$ < 1): scales negative prediction errors; socioemotional version mean slightly higher than non-emotional - $\beta$ (inverse temperature, $\beta$ > 0): exploration-exploitation trade-off; nearly identical across versions on average, lower end (more exploratory)  Mean fitted values: Not reported as point estimates; described as "moderate range" for learning rates and "lower end" for inverse temperature. Confidence: MEDIUM.
- **social_param:** None — no explicitly social parameter in the computational model.  ---  ### 7. All Models Tested  Only one computational RL model was fitted (as per pre-registration). The study also fitted competing Bayesian multilevel regression models predicting outcomes from version and age, compared via WAIC/LOOIC.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** WAIC / LOOIC (for Bayesian multilevel regression models predicting outcomes). For the RL model itself, only one model was fitted (no model comparison).
- **how_model_fit:** Individual-level fit (hierarchical Bayesian estimation via hBayesDM, which estimates group-level and individual-level parameters simultaneously)
- **data_type_fit_to:** Choice behavior (press vs. no press)  ---  ### 9. Neuroimaging

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging; cardiac psychophysiology via ECG/DFA was used instead)
- **coordinates_peak:** N/A  ---  ### 10. Analysis Type
- **analysis_type:** N/A (no neuroimaging)  ---  ### 11. Sample Size
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 56 (Aim 1 behavioral); N = 55 (Aim 2 psychophysiology due to BIOPAC malfunction); ages 12-15 years (M = 13.3); 51.8% female; predominantly White, middle to upper-middle class  ---  ### 12. Ecological Validity
- **population_category:** adolescents
- **population_age_range:** 12–15
- **ecological_validity:** Improved over standard RL tasks by including socioemotionally salient IAPS images alongside traditional non-emotional stimuli, creating more ecologically meaningful learning conditions. However, still a laboratory-based computerized task with static visual images, no real social interaction, and stimuli limited to normed photograph sets. Authors acknowledge reliance on static images may have limited the depth of arousal elicited.  ---  ### 13. Eligibility Flag
- **eligibility_flag:** FLAG — borderline social context. The task uses socioemotionally salient images (depicting social scenes) as stimuli but involves no social interaction, no social agent, and no social learning per se. The "social" element is limited to the emotional/social content of the visual stimuli being learned about. Learning is from reward/punishment feedback about stimulus-outcome associations, not from or about a social agent. This is reinforcement learning modulated by socioemotional stimulus content, not social learning in the conventional sense. Additionally, this is a dissertation — only one study, so no double-counting concern.  ---  ### 14. Concerns
- **concerns:** - Only one computational model tested (pre-registered); no model comparison across alternative RL models - Small convenience sample (N=56), predominantly White upper-middle-class, limiting generalizability - No explicit social interaction or social agent — the "social" element is the content of IAPS images used as stimuli - Mean fitted parameter values not reported as specific numbers (only described qualitatively as "moderate" or "lower end") - Cross-sectional design precludes developmental inferences despite age being included as covariate - Cardiac complexity (DFA alpha) is a peripheral and relatively coarse measure of psychophysiological engagement
- **limitations_reported:** Small convenience sample due to COVID-19 limiting generalizability to White upper-middle-class youth; only one computational model fitted per pre-registration so better-fitting models may exist; cross-sectional design precludes developmental change inferences; static IAPS images may have limited arousal depth; lacked variability and sample size to examine nonlinear psychophysiological relations; cardiac complexity may be too peripheral to capture meaningful neuromodulatory differences; computational RL models may not accurately characterize cognitive processes in youth
- **limitations_categorized:** sample size; limited generalizability; no model comparison; cross-sectional design; limited ecological validity; task simplicity; measurement limitations; model validity uncertainty  ---  ### 15. Wilson-Collins Checklist  1. **Design a good experiment:** Yes — within-person design with two conditions (socioemotional vs. non-emotional), adapted validated task (Finger et al., 2008), engages targeted RL processes 2. **Design good models:** No — only one computational model tested (pre-registered; explicitly acknowledged as limitation) 3. **Simulate, simulate, simulate:** No — no simulation of model before fitting described (illustrative figures of learning rate/inverse temperature behavior shown but these are pedagogical, not model validation simulations) 4. **Fit the parameters:** Yes — hierarchical Bayesian fitting via hBayesDM package 5. **Check parameter recovery:** No — no parameter recovery reported 6. **Check model recovery:** No — only one model, no confusion matrix 7. **Fit real data and compare models:** No — only one computational model tested (Bayesian multilevel regression models were compared, but not competing RL models) 8. **Validate the winning model:** Partial — convergence checks (trace plots, Rhat) reported; prior-posterior predictive checks conducted on Bayesian outcome models; but no formal posterior predictive check on the RL model itself 9. **Analyze the winning model:** Yes — individual-level parameters extracted and used as outcomes in Bayesian multilevel models 10. **Report results transparently:** Yes — pre-registered on OSF; data and code shared on OSF  ---  ### 16. Preregistered
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
- **flagged_fields:** - `model_params` mean fitted values: MEDIUM — described qualitatively ("moderate range," "lower end") but no specific numeric means reported - `social_param`: N/A — no social parameter in model (HIGH confidence this is correct) - `eligibility_flag`: HIGH — clearly borderline for social learning inclusion criteria - `doi`: LOW — no DOI found; ProQuest number used instead
- **cannot_find:** - Exact mean fitted values for $\alpha_{rew}$, $\alpha_{pun}$, $\beta$ per condition (described qualitatively in text but numeric means from Table 3 not extractable from .txt conversion) - DOI (dissertation available via ProQuest only)
- **other_notes:** This is a doctoral dissertation (University of Minnesota, 2023) with one study. The supplement is included within the dissertation document itself (beginning at line 2018 of the .txt file). No separate supplement file exists. The paper's primary focus is on how socioemotional stimulus content modulates RL processes in adolescents — the "social" component is in the stimulus content (IAPS images of social scenes), not in social interaction or social agents. The paper explicitly thanks ChatGPT for coding assistance. Kate Nussenbaum consulted on the computational models.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_children
- rr_pop_adolescents
- rr_pop_children
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = general
- spec_locus = source+target
- tax_domain_E_self_in_social_context
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_temperature
- tax_popclass_developmental
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_family = q_learning
- tax_rr_model_q_learning
- tax_rr_param_learning_rate
- tax_rr_param_temperature
- tax_rr_primary_topic = social_approval_reward
- tax_rr_secondary_topic = volatility
- tax_rr_topic_social_approval_reward
- tax_rr_topic_volatility
- tax_topic_social_approval_reward
- tax_topic_volatility
