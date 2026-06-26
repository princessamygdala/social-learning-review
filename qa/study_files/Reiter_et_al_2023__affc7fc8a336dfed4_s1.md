# Reiter et al. (2023)

- **study_id:** `affc7fc8a336dfed4_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Reiter, A. M. F., Hula, A., Vanes, L., Hauser, T. U., Kokorikou, D., Goodyer, I. M., NSPN Consortium, Fonagy, P., Moutoussis, M., & Dolan, R. J. (2023). Self-reported childhood family adversity is linked to an attenuated gain of trust during adolescence. *Nature Communications*, *14*, 6920. https://doi.org/10.1038/s41467-023-41531-z
- **citation_short:** Reiter et al. (2023)
- **doi:** 10.1038/s41467-023-41531-z
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Psychology
- **affiliations_raw:** LaboratoryofCognitiveNeuroscienceandLearning,IDG/McGovernInstituteforBrainResearch,Beijing; DepartmentofChildandAdolescencePsychiatry,PsychosomaticsandPsychotherapy,CentreofMental; UCLCentreforComputationalPsychiatryandAgeingResearch,UniversityCollegeLondon,London,UK; DepartmentofClinical,EducationalandHealthPsychology,UniversityCollegeLondon,London,UK; sectionalstudies,withinconsistentfindingsespeciallyinrelationtoa report,seeMethods)); DepartmentofPsychology,Julius-Maximilians-UniversitätWürzburg,Würzburg,Germany; SchoolandUniversityHospital,EberhardKarlsUniversityofTübingen,Tübingen,Germany
- **code_url:** https://github.com/AndreasHula/BacktestingTrustNSPNBaseline

## Computational level
- **study_focus:** Trust learning / trust development across adolescence; how childhood family adversity moderates longitudinal development of trust behaviour, and the role of trust as a resilience factor for peer relationship quality.
- **study_focus_short:** Trust learning / trust development across adolescence
- **learning_mode_description:** - Learning mode: Learning from a partner's repayment behaviour about the partner's trustworthiness (inequality aversion) and irritability in an iterated trust game.   - Learning from:     - Source type (social): other (anonymous trustee partner)     - Source content (social): action/policy (repayment decisions) and outcomes (coins returned)   - Learning about:     - Target type (social): other (anonymous trustee partner)     - Target content (social): state (mental state; trustworthiness/inequality aversion, irritability)
- **task_description:** Participants played as the investor in a 10-round iterated trust game against a computer algorithm mimicking a human trustee. Each round, participants received 20 coins, decided how much to invest (tripled by experimenter), and observed the trustee's repayment, with the goal of maximizing earnings across rounds.
- **task_paradigm:** Trust game
- **players:** Single agent (participant as investor), dyadic (anonymous trustee; actually computer algorithm emulating healthy adult trustee behaviour)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Coins/monetary endowment, trustee repayment feedback (numerical)
- **method:** behavioural
- **method_full:** behavioural (longitudinal, ~1.5-year follow-up; also structural MRI ROI analysis in supplement for subset)
- **main_result:** - Main Results:   - Longitudinal increase in round-by-round investment (trust) with development (F(1,10819)=109.81, p<0.001, estimate=0.27, se=0.05)   - Longitudinal decrease in social risk aversion parameter with development (F(1,567.10)=20.49, p<0.001, estimate=-0.055, se=0.01)   - Family adversity x longitudinal development interaction on trust (F(1,9696)=6.83, p=0.009, estimate=-0.03, se=0.01): higher adversity attenuated trust growth   - Family adversity main effect on Irritability parameter (F(1,506)=7.92, p=0.005, estimate=0.006, se=0.002): higher adversity linked to higher irritability   - Social risk aversion negatively correlated with total winnings at T1 (r=-0.68) and T2 (r=-0.75)   - A-priori trust at T1 predicted longitudinal peer relation quality (F(1,757.74)=5.27, p=0.022, estimate=0.06, se=0.02)   - Trust x adversity x longitudinal development interaction on peer relations (F(1,1050.70)=6.77, p=0.009, estimate=0.05, se=0.01)
- **effect_size:** r=-0.68 (social risk aversion vs. total wins T1); r=-0.75 (social risk aversion vs. total wins T2); effect sizes for mixed model estimates reported as unstandardized coefficients (see main_result)
- **learning_from:** Other (anonymous trustee); trustee's repayment actions/outcomes
- **learning_about:** Other (anonymous trustee); trustee's trustworthiness (inequality aversion) and irritability  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** I-POMDP trust model (7 params: α inequality aversion, ω risk aversion, k ToM sophistication, P planning, ζ irritability, q(ζ) irritation awareness, β inverse temperature) — Full model M1
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** - {"name": "M1 (Full model)", "family": "I-POMDP", "n_params": 7, "metric": "BIC (average=26.56)"} - {"name": "M2 (No irritability, no irritation belief)", "family": "I-POMDP (reduced)", "n_params": 5, "metric": "BIC (average=28.33)"} - {"name": "M3 (M2 + fixed risk aversion=1, stochasticity=1/3)", "family": "I-POMDP (reduced)", "n_params": 3, "metric": "BIC (average=29.74)"} - {"name": "M4 (M3 + ToM=0)", "family": "I-POMDP (reduced)", "n_params": 2, "metric": "BIC (average=30.5)"} - {"name": "M5 (Random model)", "family": "Random", "n_params": 0, "metric": "BIC (average=32.19)"}
- **model_mb_mf:** MB (model-based; the I-POMDP involves explicit planning ahead and Bayesian inference over partner states)
- **model_params:** - α (inequality aversion): {0, 0.4, 1} — degree of sensitivity to unfair outcomes [S] - ω (risk aversion): {0.4, 0.6, 0.8, 1.0, 1.2, 1.4, 1.6, 1.8} — multiplier for value of money kept over money returned by partner [S] - k (Theory of Mind sophistication): {0, 1, 2, 3, 4} — number of recursive reasoning steps [S] - P (Planning): {1, 2, 3, 4} — number of steps ahead planned [S] - ζ (Irritability): {0, 0.25, 0.5, 0.75, 1} — shift toward punishment behaviour when experiencing below-expectation partner actions [S] - q(ζ) (Irritation Awareness): {0, 1, 2, 3, 4} — awareness of partner irritability [S] - β (Inverse Temperature): {1/4, 1/3, 1/2, 1} — stochasticity in choices  Note: Mean fitted values not reported in the main text. All parameters are on discrete grids.
- **social_param:** ω (Social Risk Aversion) — captures preference for securely kept coins over socially returned coins, key developmental parameter decreasing with age; ζ (Irritability) — captures shift to retaliatory punishment upon experiencing below-expectation partner actions, linked to family adversity; k (Theory of Mind) — recursive reasoning about partner's beliefs; q(ζ) (Irritation Awareness) — belief about partner's irritability.
- **social_param_name:** α
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Draper BIC (average negative log likelihood + parameter penalty per Eq. 9)
- **how_model_fit:** individual-level-fit (full grid search over discrete parameter space per participant, minimizing negative log likelihood)
- **data_type_fit_to:** choice behavior (investment decisions across 10 rounds)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (main analyses are behavioural; a structural MRI ROI analysis is mentioned in the supplement but is not the primary analysis and supplement is not accessible)
- **contrast:** N/A (no functional neuroimaging contrasts in main text)
- **key_regions:** N/A (no functional neuroimaging in main analyses; structural ROI analysis of grey matter volume co-development with trust parameters mentioned as being in supplementary materials, but supplement not accessible)
- **coordinates_peak:** unavailable — not in main text or supplement (supplement not accessible)
- **analysis_type:** N/A (no neuroimaging contrasts in the main analyses; structural ROI analysis mentioned in supplement only)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=570 (284 female, 286 male; ages 14–25 at baseline); longitudinal follow-up ~1.5 years; retest subsample n=55 (3 time points); structural MRI subset n=294; questionnaire subsample n=511; peer relations analysis n=786
- **population_category:** mixed
- **population_age_range:** 14–25
- **ecological_validity:** Moderate — uses an iterated economic trust game against a computer algorithm (not a real partner), limiting ecological validity. However, the task is embedded in a large longitudinal community cohort with real-world peer relation measures as outcome variables, enhancing external validity. Retrospective self-report measures of family adversity are subject to recall bias.
- **eligibility_flag:** 
- **concerns:** - The trustee is a computer algorithm, not a real social partner (participants were deceived into believing it was a real peer). - Parameters are estimated on a discrete grid rather than continuous optimization — authors acknowledge this as a limitation with ongoing work to address it. - The model was validated in previous work (Hula et al., 2018, 2021) on baseline data from the same cohort; no independent parameter or model recovery reported in this paper specifically. - Family adversity measured via retrospective self-report with known biases. - Most participants reported low levels of adversity, yielding modest effect sizes. - Supplement not accessible for verification of structural MRI ROI analysis or additional computational details.
- **limitations_reported:** By design we have relied on retrospective, self-reported family experiences, and several biases are known to arise from retrospective self-reports of adverse experiences in the context of child maltreatment"; "the majority of our sample reported low levels of negative family experiences and this might explain the modest effect sizes observed in our study, highlighting a need for large samples"; discrete parameter grid is a limitation "that ongoing work is aiming to lift in the future
- **limitations_categorized:** retrospective self-report bias; limited ecological validity (computer trustee); modest effect sizes due to low-adversity sample; discrete parameter estimation; limited generalizability (low-adversity community sample)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM confidence — mean fitted parameter values not reported in main text; only discrete grid ranges provided - coordinates_peak: LOW confidence — structural MRI ROI analysis mentioned as in supplement, but supplement not accessible - analysis_type: MEDIUM confidence — marked N/A based on main text, but supplement contains structural MRI ROI analysis that could not be verified - effect_size: MEDIUM confidence — most effects reported as unstandardized mixed model estimates rather than standardized effect sizes; r values provided for correlation of risk aversion with winnings
- **cannot_find:** - Mean fitted parameter values for the winning model - Supplement (contains structural MRI ROI analysis, full model details, additional S-Tables and S-Figures referenced throughout) - MNI coordinates (if any, would be in supplement for the structural analysis) - Parameter recovery results (referenced to prior publications) - Model recovery/confusion matrix
- **other_notes:** - This paper builds directly on two prior publications using the same NSPN dataset: Hula et al. (2021) for baseline cross-sectional computational modelling, and van Harmelen et al. (2017) for the family experience factor. The current paper's novel contribution is the longitudinal analysis. - The computational model (I-POMDP) was developed and validated in Hula et al. (2015, 2018) and applied to this dataset's baseline in Hula et al. (2021). Potential duplicate flagging: if Hula et al. (2021) is in the review corpus, note shared baseline dataset but different analyses (cross-sectional vs. longitudinal). - Supplement not accessible — flagged. Brain-behaviour co-development ROI analysis is described as being in supplementary materials and supplementary note/discussion, but cannot be verified.
- **re_extract_flag:** false (full text accessed; however, supplement not accessible — note this for coordinate and structural MRI fields)

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = structural
- spec_locus = target
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_social_weight
- tax_rr_primary_topic = trust
- tax_rr_topic_trust
- tax_topic_trust
