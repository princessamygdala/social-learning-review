# Ide et al. (2018)

- **study_id:** `a41e88db4ec71fbb1_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Ide, J. S., Nedic, S., Wong, K. F., Strey, S. L., Lawson, E. A., Dickerson, B. C., Wald, L. L., La Camera, G., & Mujica-Parodi, L. R. (2018). Oxytocin attenuates trust as a subset of more general reinforcement learning, with altered reward circuit functional connectivity in males. *NeuroImage*, *174*, 35–43.
- **citation_short:** Ide et al. (2018)
- **doi:** 10.1016/j.neuroimage.2018.02.035
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofBiomedicalEngineering,StonyBrookUniversitySchoolofMedicine,StonyBrook,NY,11794,USA; etheirtrustingbehaviorafter Syntocinon (Oxytocin) Nasal Spray (Novartis) was administered; DepartmentofBiomedicalEngineering,StonyBrookUniversity,StonyBrook,NY,11794-5281,USA; CenterforBiomedicalImaging,MassachusettsGeneralHospital,Charlestown,MA,02129,USA; DepartmentofNeurobiologyandBehavior,StonyBrookUniversity,StonyBrook,NY,11794,USA; DepartmentofNeurology,MassachusettsGeneralHospital,Boston,MA,02114,USA; ether OT's putative effect in blocking the effects of Studieslookin; ethat,whileoriginallyth
- **code_url:** 

## Computational level
- **study_focus:** Trust learning; reinforcement learning under oxytocin; social reward learning
- **study_focus_short:** Trust learning; reinforcement learning under oxytocin; social reward learning
- **learning_mode_description:** Learning from a partner's monetary repayment outcomes about how much to trust/invest in the partner over 20 repeated interactions in an iterated trust game.
- **task_description:** In an iterated Trust Game (20 rounds), participants ("Investors") received 20 monetary units each round and decided how much to invest with a (fictional) Trustee partner whose repayment was algorithmically determined; invested amounts were tripled and the Trustee returned some portion, with participants learning over rounds.
- **task_paradigm:** Trust game
- **players:** Single agent (participant as Investor), dyadic (fictional Trustee partner)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Monetary units (0-20 MU), investment/repayment numerical displays
- **method:** fMRI
- **method_full:** fMRI (7T)
- **main_result:** - OT reduced RL learning rates in 13/15 subjects (paired t-test, p = 0.007; α_PL = 0.53 ± 0.30 vs. α_OT = 0.33 ± 0.27) - Including excluded subjects: p = 0.0007 (α_PL = 0.77 ± 0.59 vs. α_OT = 0.48 ± 0.37) - OT reduced sequential effects of P(trust) in 12/17 subjects (z_PL = 0.33 ± 0.45 vs. z_OT = 0.19 ± 0.43; p = 0.03 excluding one poor learner) - No OT effect on inverse temperature (p = 0.17) or investment ratio (p = 0.35) - OT reduced tit-for-tat rounds (PL: 8.29 ± 2.44 vs. OT: 6.88 ± 2.23; p = 0.02) - No OT effect on benevolent or malevolent rounds (n.s.) - P(trust) positively modulated head of caudate, dACC, MCC, OFC during investment (I2>R2) - OT reduced P(trust) modulation in bilateral amygdala (PL > OT, p < 0.05 corrected; effect sizes: PL = 2.55 ± 1.42, OT = -6.04 ± 2.06) - OT reduced bilateral amygdala response to prediction error (R3>I3; left: p = 0.0002, right: p = 0.006) - OT reduced OFC-amygdala and OFC-habenula functional connectivity during feedback (PPI; p = 0.021 and p = 0.029 respectively) - OFC-left amygdala connectivity correlated with malevolent rounds (r = 0.48, p = 0.007) - Right amygdala PE modulation correlated with tit-for-tat rounds (r = -0.41, p = 0.02) - DCM: OFC→amygdala connection weight was 0.45 for PL vs. 0.18 for OT; OFC→AM weight correlated with average P(trust) (r = 0.42, p = 0.014); NAcc→OFC weight negatively correlated with P(trust) (r = -0.47, p = 0.007)
- **effect_size:** - RL learning rate OT vs. PL: paired t-test p = 0.007 (N=15), p = 0.0007 (N=17) - ANOVA treatment effect on α: F = 9.057, p = 0.01 - Amygdala PE modulation effect sizes: PL = 2.55 ± 1.42, OT = -6.04 ± 2.06 - PPI OFC-left amygdala: paired t-test p = 0.021 - PPI OFC-LHb: paired t-test p = 0.029 - OFC-AM connectivity ~ malevolent rounds: r = 0.48, p = 0.007 - Right AM PE modulation ~ tit-for-tat: r = -0.41, p = 0.02 - DCM OFC→AM ~ P(trust): r = 0.42, p = 0.014 - DCM NAcc→OFC ~ P(trust): r = -0.47, p = 0.007 - P(trust) ~ investment ratio: r = 0.64, p = 0.0032 (representative subject)
- **learning_from:** Other (trustee partner); monetary repayment outcomes
- **learning_about:** Other (trustee partner); trustworthiness / expected reciprocity  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Two complementary models used: (1) Dynamic Bayesian belief updating of P(trust) with parameters θ (volatility), pm (prior mean), sc (scale); (2) Standard RL with softmax: V_j(t) = V_j(t-1) + α(r(t) - V_j(t-1)), P(a_j) = exp(βV_j) / Σexp(βV_i); 2 params: α, β
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [{"name": "Dynamic Bayesian P(trust)", "family": "Bayesian belief updating", "n_params": 3, "metric": "correlation with investment"}, {"name": "Reinforcement learning (softmax)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "negative log-likelihood"}, {"name": "DCM Model #11 (PL winning)", "family": "DCM", "n_params": "not specified", "metric": "BMS"}, {"name": "DCM Model #12 (OT winning)", "family": "DCM", "n_params": "not specified", "metric": "BMS"}]
- **model_mb_mf:** MF (the RL model is model-free); Bayesian model is not strictly RL
- **model_params:** - Bayesian model: θ (volatility/stability of trust belief) = 0.79 ± 0.21 (group average); pm (prior mean trust) = 0.37 ± 0.33; sc (scale) = 10 (fixed) - RL model: α [S] (learning rate): PL = 0.53 ± 0.30, OT = 0.33 ± 0.27; β (inverse temperature): PL = 0.16 ± 0.23, OT = 0.30 ± 0.29 (n.s.) - DCM: OFC→AM connection weight: PL = 0.45, OT = 0.18
- **social_param:** α [S]: learning rate for trust — quantifies how rapidly an investor updates trust beliefs from partner feedback; θ [S]: stability of trust belief over interactions; pm [S]: prior expectation of partner trustworthiness
- **social_param_name:** α [S]
- **social_param_value:** 0.53
- **social_param_sd:** 0.30
- **social_param_range:** 
- **model_comparison_metric:** Correlation with investment values (Bayesian model); negative log-likelihood minimization (RL model); BMS exceedance probability (DCM)
- **how_model_fit:** individual-level-fit (fminsearch for RL; grid search for Bayesian; DCM with BMS at group level)
- **data_type_fit_to:** choice behavior (investment values)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + PPI + DCM
- **contrast:** - I2 > R2 positively modulated by P(trust): head of caudate, dACC, MCC, OFC - I2 > R2 P(trust) modulation PL > OT: bilateral amygdala, IFG, ACC/mFC, MCC, MFG - R3 > I3 modulated by prediction error: bilateral amygdala (PL > OT) - PPI (seed: OFC, R3 > I3): OFC-left amygdala, OFC-bilateral LHb connectivity reduced under OT - DCM: OFC→amygdala effective connectivity reduced under OT
- **key_regions:** Trust belief P(trust) modulated head of caudate, dACC, MCC, OFC during investment; OT suppressed amygdala response to P(trust) and prediction error; OT reduced OFC-amygdala and OFC-lateral habenula functional connectivity; DCM confirmed reduced OFC→amygdala effective connectivity under OT.
- **key_regions_abbrev:** caudate, OFC, dACC, ACC, amygdala
- **coordinates_peak:** - MCC/SMA: 0, 2, 52 - dACC: 2, 34, 8 - Left head of caudate: -16, 24, 0 - Left OFC: -38, 36, -14 - Left amygdala (P(trust) PL>OT): -26, -2, -14 - Right amygdala (P(trust) PL>OT): 14, -8, -10 - IFG: -36, 42, 0 - ACC/medial frontal cortex: 12, 42, 18 - MCC (PL>OT): 4, 8, 34 - MFG: 30, 22, 46 - Left amygdala (PE): -24, -2, -20 - Right amygdala (PE): 30, 4, -18 - Left amygdala (PPI OFC seed): -26, -12, -26 - Bilateral lateral habenula (PPI OFC seed): -4, -26, 0
- **analysis_type:** both (whole-brain GLM with parametric modulators + anatomically defined ROI seeds for PPI + DCM)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 17 (all male; mean age 25.4 ± 3.7 years; 2 left-handed); N = 16 for neuroimaging (1 excluded for head motion); N = 15 for RL learning rate comparison (2 excluded for α > 1); within-subject crossover design (OT vs. PL)
- **population_category:** healthy adults
- **population_age_range:** M=25.4
- **ecological_validity:** Low-moderate; uses an iterated Trust Game with a fictional partner (computer algorithm mimicking human behavior), which captures iterative social feedback but lacks genuine human interaction; male-only sample limits generalizability; single-dose pharmacological design.
- **eligibility_flag:** 
- **concerns:** Very small sample size (N=17); male-only sample; fictional trustee (not real social interaction); no formal model comparison between Bayesian and RL models (both used in parallel); DCM model space and number of models compared not fully described in main text; 2 subjects excluded from RL analysis for learning rates > 1, suggesting poor model fit for some participants; clinical trial registration NCT01834261 but not described as preregistered for analyses.
- **limitations_reported:** this study was not designed to compare social versus non-social learning"; "our findings are limited to men in a specific context in which cooperation is incentivized"; "Given the likelihood of sex-differences"; "two important future directions will be to see if our effects replicate for women, as well as for adversarial contexts"; "future studies are needed to delineate the effect, to determine if attenuation of learning persists in non-social contexts
- **limitations_categorized:** limited generalizability (male-only); limited ecological validity (cooperation context only); no social vs. non-social comparison; small sample size; sex differences not tested
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.5
- **wc_total:** 4.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_comparison_metric (MEDIUM): Bayesian and RL models not formally compared; each used for different purpose - social_param (MEDIUM): all parameters operate in social context but not specifically social vs. non-social - preregistered (MEDIUM): clinical trial registered but analysis preregistration unclear - DCM model space (LOW): number and structure of competing DCM models not fully described in main text; supplement mentions Models #11 and #12 as winners but full model space not enumerated - effect_size (MEDIUM): many effects reported as paired t-test p-values; some correlations reported
- **cannot_find:** Total number of DCM models compared; full DCM model space specification; exact BMS exceedance probabilities for DCM; code/data availability statement
- **other_notes:** Supplement is a .doc file (no .txt version). The supplement confirms DCM analysis with spectral DCM (spDCM) for the NAcc-amygdala-OFC circuit, with separate winning models for PL (Model #11) and OT (Model #12) conditions selected via BMS. The study uses two parallel computational frameworks (Bayesian belief updating for P(trust) as parametric modulator in fMRI; RL for behavioral learning rate comparison) rather than formally comparing them. Clinical trial registration: NCT01834261.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pharma_oxytocin
- pop_healthy_adults
- rr_pharma_oxytocin
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target+context
- spec_neural = shared
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_MF
- tax_model_bayesian
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = trust
- tax_rr_topic_trust
- tax_topic_trust
