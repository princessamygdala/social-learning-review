# Contreras-Huerta (2021)

- **study_id:** `ab3bd6a979910aae4_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Contreras-Huerta, L. S. (2021). *Computational, psychological and neural mechanisms of prosocial motivation* [Doctoral thesis, University of Oxford]. University of Oxford.
- **citation_short:** Contreras-Huerta (2021)
- **doi:** 10.1037/emo0000813
- **publication_type:** thesis
- **year:** 2021.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** lab even before it had a real name! Thanks for the technical advice, but more; mitted in partial fulfilment of the requirements for the; ethodological overview on what factors might be; Lab members for being such special people; Department of Experimental Psychology; Mitko, I really hope our paths cross; lab members, who were like a family; ethods, strong in theoretical
- **code_url:** https://github.com/SICLab/detecting-bots

## Computational level
- **study_focus:** Prosocial motivation; cost-benefit decision-making in harm aversion and prosocial effort contexts; interoception and prosocial motivation; prosocial foraging.
- **study_focus_short:** Prosocial motivation
- **learning_mode_description:** - Learning mode: N/A -- no learning over time occurs in any study   - Learning from: N/A (decisions are static cost-benefit trade-offs, not learning from feedback)   - Learning about: N/A (parameters reflect stable preferences, not learned associations)   - Note: If forced to categorize: Source type (non-social): self; Source content (non-social): outcomes (monetary rewards, physical effort, electric shocks). Target type (social): other (anonymous stranger); Target content (social): outcomes (rewards, harm).
- **task_description:** - Ch. 3 (Study 1): Participants (N=66) completed a harm aversion task (trading off money vs. electric shocks for self or anonymous other) in fMRI and a prosocial effort task (trading off physical effort vs. monetary rewards for self or other) behaviorally, approximately one week apart. - Ch. 4 (Study 2-3): Online participants (Study 1: N=113; Study 2: N=212) completed adapted versions of both tasks; computational parameters correlated with psychiatric/affective traits via CCA. - Ch. 5 (Study 4): Same sample as Ch. 3 (N=61) completed a moral judgment task and prosocial effort task to quantify moral hypocrisy. - Ch. 6 (Study 5): Participants (N=58) completed a passive reward viewing task in fMRI, an interoception respiratory task, and the prosocial effort task. - Ch. 7 (Study 6-7): Participants (Study 1: N=40; Study 2: N=29) completed a social patch-leaving foraging task, collecting rewards for self or other in rich/poor environments.
- **task_paradigm:** Effort / cost-benefit prosocial task
- **players:** - Ch. 3, 5, 6: Single agent (participant), single target (anonymous stranger) - Ch. 4: Single agent (participant), single target (anonymous other via MTurk) - Ch. 7: Single agent (participant), single target (anonymous receiver/confederate)
- **n_players:** single agent (1)
- **partner_type:** confederate
- **stimuli:** Monetary rewards, electric shocks (real in Ch. 3/5, hypothetical in Ch. 4), physical effort (grip force in Ch. 3/5/6, box-ticking online in Ch. 4), monetary outcomes (passive viewing in Ch. 6), berries/rewards in virtual foraging patches (Ch. 7).
- **method:** fMRI / online / behavioural
- **method_full:** - Ch. 3: fMRI + behavioural - Ch. 4: online behavioural - Ch. 5: behavioural - Ch. 6: fMRI + behavioural - Ch. 7: behavioural (lab-based)
- **main_result:** - Ch. 3: Hyperaltruism replicated (kappa_other > kappa_self, z = -3.45, p < 0.001); prosocial apathy replicated (lambda_other > lambda_self, z = -6.94, p < 0.001); prosocial behaviors correlated across tasks (rho = 0.33, p < 0.008); vAI response to others' harm correlated with prosocial effort (r = -0.42, p < 0.003 FDR); ACCg (r = -0.3, p < 0.03 FDR); TPJp (r = -0.3, p < 0.03 FDR); TPJa money contrast (r = 0.44, p < 0.002 FDR). - Ch. 4: Study 1 hyperaltruism replicated (kappa_other > kappa_self, z = -2.28, p < 0.03); CCA revealed empathic concern and low apathy predict prosociality (Rc = 0.38, p < 0.001). - Ch. 5: Hypocrisy model improved fit over simple model (AIC difference significant; chi-sq loglikelihood); effort x beneficiary x hypocrisy interaction (b = 0.36, SEM = 0.17, z = 2.1, p < 0.04). - Ch. 6: Interoception model outperformed simple model (AIC: 5079.3 vs 5115.5, chi-sq = 52.28, df = 8, p < 0.001); interoception x reward x beneficiary interaction (b = 0.42, SEM = 0.11, z = 3.87, p < 0.001); RdAI similarity correlated with interoception (r = -0.41, p < 0.02 FDR); ACCg similarity with other reward sensitivity (r = 0.35, p = 0.009 uncorrected). - Ch. 7: Study 1 patch x beneficiary interaction (b = -1.37, t = -3.53, p < 0.001); Study 2 replication (b = -1.26, t = -6.69, p < 0.001); no environment x beneficiary interaction in either study.
- **effect_size:** See main_result above. Key effect sizes: prosocial behavior correlation rho = 0.33; vAI-prosocial effort r = -0.42; interoception-reward sensitivity r = 0.27.
- **learning_from:** N/A (no learning). Decisions based on: self -- monetary outcomes, effort costs, electric shocks; other -- harm/reward to anonymous stranger.
- **learning_about:** N/A (no learning). Decisions reveal: sensitivity to self vs. other costs and benefits (stable parameters).  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** - Harm aversion: DeltaV = (1-kappa)*Delta_m - kappa*Delta_s, with separate kappa_self, kappa_other; softmax with beta (4 params: kappa_self, kappa_other, beta_self, beta_other) - Prosocial effort: SV = R - lambda*E^2, with separate lambda_self, lambda_other; softmax with beta (3 params: lambda_self, lambda_other, beta) - Ch. 7: MVT (no free parameters fitted to individual data; optimal predictions compared against behavior)
- **model_family:** Utility / EV
- **model_class:** PE learning / Belief updating
- **all_models_tested:** - For harm aversion: single model used (validated in Crockett et al., 2014, 2015, 2017); no model comparison within thesis - For prosocial effort: single model used (validated in Lockwood, Hamonet et al., 2017); compared parabolic vs. linear vs. hyperbolic in prior work - Ch. 5: Simple MM vs. Hypocrisy MM (AIC comparison) - Ch. 6: Simple MM vs. Interoception MM (AIC comparison) - Ch. 7: MVT optimal predictions vs. behavior (no model fitting)
- **model_mb_mf:** N/A (not RL)
- **model_params:** - Harm aversion: kappa_self (mean = 0.27, SEM = 0.03) [harm aversion for self]; kappa_other (mean = 0.38, SEM = 0.03) [S] [harm aversion for other]; beta_self, beta_other [inverse temperature] - Prosocial effort: lambda_self (mean = 0.06, SEM = 0.007) [effort discount for self]; lambda_other (mean = 0.28, SEM = 0.04) [S] [effort discount for other]; beta [inverse temperature]
- **social_param:** kappa_other [S] -- harm aversion parameter for other: degree to which profit is discounted by harm to another person. lambda_other [S] -- effort discount parameter for other: degree to which reward is discounted by effort when benefiting another person.
- **social_param_name:** kappa_other [S]
- **social_param_value:** 0.27
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (for mixed-effects model comparisons in Ch. 3, 5, 6); log-likelihood ratio tests (Ch. 5, 6). No formal model comparison for computational models themselves (single model used per task based on prior validation).
- **how_model_fit:** individual-level-fit (maximum likelihood estimation for computational model parameters per participant)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** - Ch. 3: model-based fMRI (parametric regressors for money and shocks at decision onset) + ROI analysis - Ch. 6: GLM with categorical regressors (reward magnitudes) + MVPA (multivariate similarity analysis between self/other reward maps in ROIs)
- **contrast:** - Ch. 3: Parametric modulation by Delta_shocks_other > baseline (in vAI, ACCg, TPJp); Delta_money_other > Delta_money_self (in TPJa) - Ch. 6: Self/other reward similarity in RdAI correlated with interoception; self/other reward similarity in ACCg correlated with prosocial motivation
- **key_regions:** Ch. 3: Other's harm encoded in vAI, ACCg, TPJp; moral conflict in TPJa. Ch. 6: Interoception-linked self/other reward dissimilarity in right dAI; motivation-linked self/other reward similarity in ACCg.
- **key_regions_abbrev:** ACC, TPJ, AI
- **coordinates_peak:** From Appendix A (Ch. 3, whole-brain uncorrected): - Shocks self: Lingual Gyrus: 12, -79, -7; Superior Frontal Gyrus: -18, -10, 65; Precuneus: 9, -67, 41 - Money self: Angular Gyrus: 51, -52, 20; Right Amygdala: 24, -1, -19; Left Amygdala: -18, -7, -19 - Shocks other: Lingual Gyrus: -12, -82, -13; Left Caudate: -15, -7, 26; Right Caudate: 21, -4, 26 - Money other: Lateral Occipital Cortex: -54, -67, 26; Frontal Pole: -12, 59, 20  From Appendix B (Ch. 6, Neurosynth ROIs uncorrected): - Interoception: Anterior Insula: 38, 11, 5; PCC: 1, -26, 28; Precentral Gyrus: -51, 10, 38; Supramarginal Gyrus: 58, -34, 46 - Other reward: Thalamus: -26, -24, 8  Note: Primary ROI analyses used anatomical masks (not peak coordinates) for ACCg, vAI, dAI, TPJp, TPJa from published parcellations (Deen et al., 2011; Neubert et al., 2015; Mars et al., 2012).
- **analysis_type:** Both (ROI-based primary analyses; whole-brain exploratory analyses reported in appendices)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** - Ch. 3: N=66 (34 fMRI + behavioural); ages M=22.6, SD=3.8 - Ch. 4 Study 1: N=113 (online); ages M=35.7, SD=11.6 - Ch. 4 Study 2: N=212 (online); ages M=37.7, SD=10.6 - Ch. 5: N=61 (subset of Ch. 3 sample) - Ch. 6: N=58 (fMRI); ages not specified for this chapter specifically - Ch. 7 Study 1: N=40 (lab); ages M=24.8, SD=5.18 - Ch. 7 Study 2: N=29 (lab); ages M=24.7, SD=5
- **population_category:** healthy adults
- **population_age_range:** M=22.6 (SD=3.8)
- **ecological_validity:** Tasks use parametric cost-benefit trade-offs in controlled lab settings (or online). The harm aversion task in Ch. 4 was hypothetical (no real shocks or money). Ch. 7 foraging task has greater ecological validity than standard prosocial tasks by using continuous dynamic decisions mirroring real-world foraging problems. However, all social manipulations involve anonymous strangers via role-assignment procedure (confederate), limiting generalizability to real social relationships.
- **eligibility_flag:** FLAGGED -- thesis; no learning over time in any study; pure cost-benefit decision-making with stable utility parameters. Models are utility/value functions, not learning models. Does not meet inclusion criterion: "learning occurs in a social context" or "learning happens over time." Flag as `type: thesis; eligibility: no_temporal_learning; decision_making_not_learning`.
- **concerns:** 1. No learning over time -- all models assume stable parameters across trials 2. Same sample reused across Chapters 3 and 5 (N=66/61) -- potential double-counting 3. Ch. 4 harm aversion task was entirely hypothetical 4. Ch. 6 ACCg result did not survive FDR correction (p = 0.06 FDR) 5. Whole-brain results reported uncorrected (p < 0.001 in Ch. 3; p < 0.01 in Ch. 6) 6. Ch. 7 uses no formal computational model fitting -- MVT predictions simply compared to behavior 7. Correlational design throughout -- no causal evidence
- **limitations_reported:** Correlational designs -- absence of causal evidence"; "results fit specific cost-benefit definition of prosocial behaviour, open debate on whether this captures essence of prosociality"; "limited to two specific domains/paradigms (prosocial effort, harm aversion)"; "all beneficiaries were anonymous strangers -- unknown if results generalize across social distances"; "neuroimaging based on specific hypothesis-driven structures -- cannot conclusively say only these areas underlie prosocial variability"; "fMRI indirect measure of neuronal activity; limited temporal resolution; correlational"; "sample sizes for individual difference analyses may be insufficient (especially Ch. 7)
- **limitations_categorized:** correlational design; limited ecological validity; limited generalizability (anonymous strangers only); task simplicity; ROI bias; fMRI limitations (temporal resolution, indirect measure); sample size (especially Ch. 7)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 3.5
- **wc_total:** 3.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - learning_mode: LOW -- no learning occurs; forced categorization would be misleading - eligibility_flag: HIGH -- clearly flagged as non-learning decision-making - model_comparison: MEDIUM -- no formal model comparison within thesis; relies on prior validation - coordinates_peak: MEDIUM -- primary analyses used anatomical masks, not peak coordinates; whole-brain peaks from uncorrected analyses only - doi: MEDIUM -- thesis itself lacks DOI; constituent publications have separate DOIs
- **cannot_find:** - Fitted beta (inverse temperature) parameter values not reported - Exact DOI for thesis itself - Ages for Ch. 6 sample specifically - Preregistration status
- **other_notes:** This is a PhD thesis by Luis Sebastian Contreras-Huerta (Oxford, 2021), supervised by Matthew Apps, Molly Crockett, and Geoffrey Bird. The thesis acknowledgments mention Patricia Lockwood (the review author). Chapter 4 is published in *Emotion* (2020). The theoretical framework in Chapter 1 is published in *Neuroscience and Biobehavioural Reviews* (2020). The computational models used are NOT learning models -- they are utility/value function models that quantify stable preferences for cost-benefit trade-offs. This thesis would be most appropriately categorized under "social decision-making" rather than "social learning." The same dataset from Ch. 3 is reused in Ch. 5, so if included, these should NOT be treated as independent studies.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_bayesian
- tax_model_utility
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = utility_EV
- tax_rr_model_utility_EV
- tax_rr_param_social_bonus
- tax_rr_param_social_weight
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = moral_harm
- tax_rr_topic_moral_harm
- tax_rr_topic_prosocial_altruism
- tax_topic_moral_harm
- tax_topic_prosocial_altruism
