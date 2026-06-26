# Rossi-Goldthorpe et al. (2021)

- **study_id:** `a9762e050e082aeee_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Rossi-Goldthorpe, R. A., Leong, Y. C., Leptourgos, P., & Corlett, P. R. (2021). Paranoia, self-deception and overconfidence. *PLoS Computational Biology*, *17*(10), e1009453.
- **citation_short:** Rossi-Goldthorpe et al. (2021)
- **doi:** 10.1371/journal.pcbi.1009453
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Psychology
- **affiliations_raw:** mitsunrestricteduse,distribution,and muchmorebasic,beingbasedinsteadinhowtheindividualmodelsandanticipatestheir; labilityStatement:DataAvailability:The ner,whowaseitheracollaborator(intheirgroup)oracompetitor(outsideoftheir; ETHERLANDS withtheideathatself-deception,paranoia,andoverconfidenceflourishunderuncertainty,; DepartmentofPsychology,UniversityofChicago,Chicago,Illinois,UnitedStatesofAmerica,; departmentalNeuroscienceProgram,YaleUniversity,NewHaven,Connecticut,UnitedStatesof; departmental paranoiawasassociatedwithparticipants’beliefsabouttheirownperformance; DepartmentofPsychiatry,YaleUn
- **code_url:** https://github.com/rosarossig/

## Computational level
- **study_focus:** Self-deception learning; paranoia; social influence on perceptual belief updating
- **study_focus_short:** Self-deception learning
- **learning_mode_description:** - Learning mode: Learning from social (partner bet) and non-social (image) information about perceptual categorization under social influence, examining how paranoia modulates reliance on social vs. non-social cues.   - Learning from:     - Source type (social): other (cooperating or competing partner)       - Source content (social): action/policy (partner's bet on image category)     - Source type (non-social): world (chimeric face/scene images)       - Source content (non-social): stimulus (image ambiguity/scene percentage)   - Learning about:     - Target type (non-social): world (image categorization: face vs. scene)       - Target content (non-social): stimulus (perceived image category tendency)     - Target type (social): other (perceived accuracy/reliability of partner's bets)       - Target content (social): state (mental state; partner reliability)
- **task_description:** Participants classified chimeric face/scene images (ranging from 100% face to 100% scene) and rated their confidence. In a second phase, they saw a partner's bet (cooperator or competitor) on the image category before classifying the same images again.
- **task_paradigm:** Social influence task
- **players:** Single agent (participant), single target (partner: cooperator or competitor; automated/uninformative)
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Chimeric face/scene images (varying ambiguity 0-100% scene), binary partner bets (face or scene), 1-7 confidence scale
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Motivational bias: participants aligned with cooperator bets and opposed competitor bets (bet x group interaction: z = 8.802, p < 2e-16, b = 0.131875) - High paranoia participants made more self-deceptive choices (F(1,659) = 13.65, p = 0.0007, eta_p2 = 0.02) - High paranoia participants were more confident on self-deceptive trials (F(1,620) = 81.691, p < 2e-16, eta_p2 = 0.116) - Confidence-weighted self-deception elevated in high paranoia (F(1,620) = 58.06, p = 2.87e-13, eta_p2 = 0.086) - Cooperation group had elevated initial social prior m0_2,s (F(1,654) = 16.74, p = 0.000145, eta_p2 = 0.039) - High paranoia had elevated omega_ns (F(1,654) = 18.68, p = 5.35e-5, eta_p2 = 0.027) and elevated omega_s (F(1,654) = 9.425, p = 0.0069, eta_p2 = 0.013) - omega_ns correlated with CWSD more strongly in high paranoia (r = 0.462) vs. low paranoia (r = 0.282; Fisher's z p = 0.0228) - Experiment 2: increasing bet accuracy to 75% reduced self-deception in high paranoia group (Cohen's d = 0.358) but not low paranoia - Parameter recovery: all key parameters significantly correlated with simulated counterparts (omega_ns: r = 0.24; omega_s: r = 0.73; m0_2,s: r = 0.78)
- **effect_size:** - Motivational bias: b = 0.132, 95% CI [0.103, 0.161] - Self-deception (paranoia): eta_p2 = 0.020 - Confidence on SD trials (paranoia): eta_p2 = 0.116 - CWSD (paranoia): eta_p2 = 0.086 - CWSD (cooperation vs. competition): eta_p2 = 0.027 - Social prior (group): eta_p2 = 0.039 - omega_ns (paranoia): eta_p2 = 0.027 - omega_s (paranoia): eta_p2 = 0.013 - omega_ns-CWSD correlation (high paranoia): r = 0.462 - omega_ns-CWSD correlation (low paranoia): r = 0.282 - Exp 2 raw SD (high paranoia): Cohen's d = 0.358 - Exp 2 confidence (high paranoia): Cohen's d = 0.416 - Rank difference-CWSD (high paranoia): r = 0.554 - Rank difference-CWSD (low paranoia): r = 0.343
- **learning_from:** Other (partner's bet; social) and world (chimeric images; non-social). Source: other + world.
- **learning_about:** World (image categorization tendency) and other (partner bet accuracy/reliability). Target: world + other.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** 2-stream HGF (2-level, parallel social + non-social arms; perceptual model P1 with scaled-omega_s; response model R1 softmax with decision noise only). Parameters: omega_s, omega_ns, m0_2,s, m0_2,ns, eta, beta.
- **model_family:** HGF
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "M1: P1 (HGF scaled-omega_s) + R1 (softmax, decision noise only) [winning]", "family": "HGF", "n_params": "not explicitly stated (estimated ~6: omega_s, omega_ns, m0_2s, m0_2ns, eta, beta)", "metric": "family-wise BMS (protected exceedance probability)"},   {"name": "P2: HGF with additive bias on social sigmoid", "family": "HGF", "n_params": "unknown", "metric": "family-wise BMS"},   {"name": "P3: HGF with multiplicative bias on social sigmoid", "family": "HGF", "n_params": "unknown", "metric": "family-wise BMS"},   {"name": "P4: HGF with combined additive + multiplicative bias", "family": "HGF", "n_params": "unknown", "metric": "family-wise BMS"},   {"name": "R1: Softmax (decision noise only) [winning response model]", "family": "softmax", "n_params": "1", "metric": "family-wise BMS (PXP=0.979)"},   {"name": "R2: Softmax with weighting term", "family": "softmax", "n_params": "2+", "metric": "family-wise BMS"},   {"name": "Rescorla-Wagner model", "family": "RW", "n_params": "unknown", "metric": "BMS (poor fit)"} ]
- **model_mb_mf:** Bayesian
- **model_params:** - omega_s: variance of 2nd-level belief on social stream (perceived volatility of bet accuracy). High paranoia > low paranoia (F = 9.425, eta_p2 = 0.013) [S] - omega_ns: variance of 2nd-level belief on non-social stream (perceived volatility of image categorization tendency). High paranoia > low paranoia (F = 18.68, eta_p2 = 0.027) - m0_2,s: initial prior belief about bet accuracy (2nd level social). Cooperation > competition (F = 16.74, eta_p2 = 0.039) [S] - m0_2,ns: initial prior belief about image tendency (2nd level non-social). Fitted values not reported. - eta: scaling parameter on omega_s in social sigmoid (multiplicative term, eta * omega_s). Fitted values not reported. - beta: inverse temperature (softmax response model). Fitted values not reported. - recency bias: deterministic function of previous image ambiguity (not a free parameter)  Note: Mean fitted parameter values are not reported in the main text. S3 Table and S7 Table (initial prior values) are referenced but stored as TIFF images and not accessible.
- **social_param:** omega_s [S]: perceived volatility of partner bet accuracy; m0_2,s [S]: initial prior belief about partner bet accuracy (distinguishes cooperation vs. competition groups); eta [S]: scales the influence of omega_s on social prediction
- **social_param_name:** omega_s [S]
- **social_param_value:** 9.425
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Family-wise Bayesian model selection (BMS) with protected exceedance probability
- **how_model_fit:** individual-level-fit (model inversion using MATLAB HGF toolbox)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only; discussion mentions OFC, amygdala, dmPFC, vmPFC as future targets but no neural data collected)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** Experiment 1: N = 663 (329 cooperation, 334 competition; online via CloudResearch). Experiment 2: N = 324 (online via CloudResearch with Data Quality feature). Total N = 987.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate; online chimeric image task with automated (uninformative) partner bets does not reflect genuine social interaction; partner is not a real person and bets are 50% or 75% accurate by design; self-report paranoia rather than clinical assessment.
- **eligibility_flag:** 
- **concerns:** Partner is automated and uninformative (bets are 50% or 75% accurate), so the "social" manipulation is minimal; online self-report of psychiatric symptoms without clinical verification; high collinearity between anxiety and depression measures complicates interpretation; mean fitted parameter values are not reported in main text; exact number of free parameters for winning model not explicitly stated; supplement tables are TIFF images and not directly accessible.
- **limitations_reported:** Our work involves online self-report of psychiatric symptoms. It is possible our high scoring participants were simply responding inattentively, and thus, our paranoid participants were not really paranoid but rather disengaged"; "our task did not have a conduit for that over-confidence -- in terms of convincing others of one's insights or abilities"; "A task with reciprocal exchange between participants would be enlightening
- **limitations_categorized:** online self-report validity; no reciprocal social interaction; limited ecological validity; no clinical verification of paranoia
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.5
- **wc_total:** 8.5

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params (MEDIUM): mean fitted values not reported in main text; S3 Table and S7 Table are TIFF images not accessible - all_models_tested (MEDIUM): exact number of parameters for alternative models and full model space not fully specified in main text; S4 Table (model space) is a TIFF image - winning_model n_params (LOW): not explicitly stated; estimated from parameter descriptions (~6 free parameters)
- **cannot_find:** Mean fitted parameter values for any parameter; exact number of free parameters for winning model; full model space details (in S4 Table, TIFF); initial prior values (in S7 Table, TIFF); perceptual model parameter descriptions (in S3 Table, TIFF)
- **other_notes:** Two experiments reported (Exp 1: N=663, 50% bet accuracy; Exp 2: N=324, 75% bet accuracy). Same model fit to both experiments. The paper explicitly compares Bayesian (HGF) vs. non-Bayesian (Rescorla-Wagner) approaches, finding HGF superior. The key finding is that paranoia relates to non-social parameters (omega_ns) rather than social parameters (m0_2,s), contradicting coalitional cognition accounts. Supplement tables are stored as TIFF images within the PLOS journal system and cannot be read as text. Data available at https://github.com/rosarossig/self-deception.git; code at https://osf.io/8kfph/.
- **re_extract_flag:** false (full text available and read; however, supplement tables in TIFF format could not be read -- flagged in cannot_find)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_paranoia
- rr_pop_healthy_adults
- rr_pop_paranoia
- rr_tax_mod_instructed
- rr_tax_mod_social_info_search
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target+context
- spec_source = partly
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_domain_E_self_in_social_context
- tax_mod_instructed
- tax_mod_social_info_search
- tax_model_HGF
- tax_model_bayesian
- tax_param_social_weight
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_HGF
- tax_rr_model_family = HGF
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = self_belief_confidence
- tax_rr_topic_self_belief_confidence
- tax_rr_topic_social_info_use
- tax_social_nonsocial_comparison
- tax_topic_self_belief_confidence
- tax_topic_social_info_use
