# Schie et al. (2023)

- **study_id:** `afacb782a99839f93_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** van Schie, C., Cook, J. L., Elzinga, B., & Ly, V. (2023). A boost in self-esteem after positive social evaluation predicts social and non-social learning. *Royal Society Open Science*, *10*, 230027. https://doi.org/10.1098/rsos.230027
- **citation_short:** Schie et al. (2023)
- **doi:** 10.1098/rsos.230027
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofClinicalPsychology,LeidenInstituteforBrainandCognitionand2Institute; mitation, understanding of social cues and theory of mind play an; Institute ofPsychology,Leiden University, Leiden, The Netherlands; School ofPsychology,UniversityofBirmingham, Birmingham, UK; InstituteandtheSchoolofPsychology,Universityof; ether social acceptance and rejection; University Library user; emails: cvschie@uow.edu.au, j.l.cook@bham.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Social influence learning / learning from social advice modulated by self-esteem change following social acceptance vs. rejection
- **study_focus_short:** Social influence learning / learning from social advice modulated by
- **learning_mode_description:** - Learning mode: Learning from social advice and individual outcome history to select rewarding stimuli, modulated by prior social evaluation   - Learning from:     - Source type (social): other (social advisor / confederate)       - Source content (social): action/policy (advice about which stimulus is correct)     - Source type (non-social): self       - Source content (non-social): outcome (reward feedback on chosen stimulus)   - Learning about:     - Target type (non-social): world       - Target content (non-social): state (probability that blue/green stimulus is correct; probability that social advice is correct)
- **task_description:** Participants first received standardized positive or negative social feedback from a confederate based on a personal interview, then performed a social-learning task where they chose between blue and green stimuli to earn points by combining individually experienced outcome history with advice putatively from a social advisor (second confederate).
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant), multi-target (2 confederates: social feedback provider, social advisor); between-subjects design (positive N=43, negative N=44)
- **n_players:** network (5+)
- **partner_type:** confederate
- **stimuli:** Blue and green abstract stimuli, social advice (red frame indicating advisor's choice), reward feedback (correct/incorrect), social feedback words (positive, negative, intermediate adjectives)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Participants' choices predicted by both optimal individual and social learner models (M1: χ²(2) = 1413.45, p < 0.001)   - Feedback condition x learner model interaction (M3: χ²(2) = 7.59, p = 0.022)   - Three-way interaction: Δself-esteem x feedback condition x learner model (M7: χ²(2) = 49.32, p < 0.001)   - Increase in self-esteem after positive feedback associated with decreased individual learning (b = −0.21, s.e. = 0.05, Z = −4.30, 95% CI [−0.31, −0.12])   - Increase in self-esteem after positive feedback associated with increased social learning (b = 0.26, s.e. = 0.05, Z = 5.22, 95% CI [0.17, 0.37])   - Within positive condition: Δself-esteem x individual learner (b = −0.14, s.e. = 0.03, Z = −4.20, 95% CI [−0.21, −0.07])   - Within positive condition: Δself-esteem x social learner (b = 0.23, s.e. = 0.03, Z = 6.68, 95% CI [0.17, 0.30])   - Positive condition: correlation between self-esteem change and relative social vs. individual learning weight (r = 0.38, 95% CI [0.09, 0.62])   - Negative condition: no significant correlation (r = −0.14, 95% CI [−0.42, 0.17])   - State self-esteem increase after positive feedback (b = 12.11, s.e. = 3.49, t = 3.47, 95% CI [5.24, 19.00])
- **effect_size:** - Main Results:   - Participants' choices predicted by both optimal individual and social learner models (M1: χ²(2) = 1413.45, p < 0.001)   - Feedback condition x learner model interaction (M3: χ²(2) = 7.59, p = 0.022)   - Three-way interaction: Δself-esteem x feedback condition x learner model (M7: χ²(2) = 49.32, p < 0.001)   - Increase in self-esteem after positive feedback associated with decreased individual learning (b = −0.21, s.e. = 0.05, Z = −4.30, 95% CI [−0.31, −0.12])   - Increase in self-esteem after positive feedback associated with increased social learning (b = 0.26, s.e. = 0.05, Z = 5.22, 95% CI [0.17, 0.37])   - Within positive condition: Δself-esteem x individual learner (b = −0.14, s.e. = 0.03, Z = −4.20, 95% CI [−0.21, −0.07])   - Within positive condition: Δself-esteem x social learner (b = 0.23, s.e. = 0.03, Z = 6.68, 95% CI [0.17, 0.30])   - Positive condition: correlation between self-esteem change and relative social vs. individual learning weight (r = 0.38, 95% CI [0.09, 0.62])   - Negative condition: no significant correlation (r = −0.14, 95% CI [−0.42, 0.17])   - State self-esteem increase after positive feedback (b = 12.11, s.e. = 3.49, t = 3.47, 95% CI [5.24, 19.00])
- **learning_from:** Social: other (social advisor's advice); Non-social: self (own reward outcomes)
- **learning_about:** World: probability of stimulus being correct; probability of social advice being correct  ---  ### 3. ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Bayesian learner model (Behrens et al., 2008) — two parallel Bayesian models: one tracking reward probability r (individual learning) and one tracking social advice accuracy (social learning), each with volatility estimation. Used as regressors in logistic multilevel model predicting choice.
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [{"name": "Bayesian learner model (individual + social)", "family": "Bayesian belief updating", "n_params": "not individually fitted — model generates optimal probability estimates used as regressors", "metric": "chi-squared model comparison of multilevel logistic models (M0–M7)"}]  Note: The authors did not fit free parameters of the Bayesian model to individual subjects. They used the Bayesian learner algorithm (from Behrens et al., 2008) to generate optimal trial-by-trial probability estimates, which were then entered as fixed regressors in multilevel logistic regressions. The model comparison (M0–M7) pertains to the multilevel statistical models, not to alternative computational models.
- **model_mb_mf:** Bayesian
- **model_params:** - r: reward probability (probability blue is correct), estimated trial-by-trial - v: volatility of reward probability - k: rate of change of volatility - Parallel parameters for social information probability - No free parameters fitted at individual level; the Bayesian algorithm generates optimal estimates deterministically from the programmed schedules
- **social_param:** Social learner model — Bayesian estimate of trial-by-trial probability that social advice is correct, used as a regressor for social learning weight
- **social_param_name:** Social learner model
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** χ² likelihood ratio tests comparing nested multilevel logistic models (M0–M7), plus AIC and BIC
- **how_model_fit:** params-calculated-independently (Bayesian learner model generates optimal estimates from the objective probability schedules; no individual-level parameter estimation. Estimates used as regressors in multilevel logistic regression.)
- **data_type_fit_to:** choice behavior  ---  ### 4. IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A — behavioural study only
- **analysis_type:** N/A  ---  ### 5. QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 87 (43 positive feedback, 44 negative feedback); all female; M_age = 21.91, SD = 3.36, range 18–30 years
- **population_category:** healthy adults
- **population_age_range:** 18–30
- **ecological_validity:** Limited — laboratory setting with confederates posing as other participants; social feedback was standardized (not genuine); social advisor was fictitious; task involved abstract stimuli (blue/green) rather than naturalistic social decisions. However, the social feedback paradigm used a personal interview to increase ecological validity of the acceptance/rejection manipulation.
- **eligibility_flag:** The Bayesian learner model is not fitted to individual participants — it generates normative/optimal predictions used as regressors in a statistical model. This is a borderline case for "uses computational modeling" as the computational model is used as a benchmark rather than fitted. Flag: borderline computational modeling — model used as optimal benchmark regressor, not fitted to individual behavior.
- **concerns:** - The Bayesian model was not fitted to individual participants; it generates optimal predictions from the programmed schedules and is used as a regressor. No individual-level computational model parameters were estimated. - Only one computational model was tested (no model comparison of alternative learning algorithms). - All-female sample limits generalizability. - No neutral control condition. - Between-subjects design means individual differences in social learning at baseline are uncontrolled. - The negative feedback condition did not produce a significant change in self-esteem, limiting interpretation of negative feedback effects.
- **limitations_reported:** A limitation to the study is that we did not include a neutral-only control group"; "Since the effects of social acceptance are not necessarily the opposite or mirror image of social rejection, future research should include a neutral control group or include assessments of social learning at pre- and post-manipulation to allow more rigorous testing"; "The fact that five out of six participants who reported doubts about the credibility of the social feedback at the debriefing were in the negative feedback condition may indicate that the manipulation was less successful in this condition"; "we have investigated females only as males and females may value social feedback differently
- **limitations_categorized:** no neutral control condition; limited generalizability (female-only sample); manipulation credibility concerns (negative condition); limited ecological validity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 3.5
- **wc_total:** 3.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - eligibility_flag (MEDIUM): Borderline — computational model used as normative benchmark, not fitted to individuals - model_params (MEDIUM): No free parameters fitted; the Bayesian model is deterministic given the schedules - wc_guidelines rules 2–7 (HIGH): Scored as No because no alternative models tested and no individual fitting
- **cannot_find:** - Supplement not accessible (hosted on figshare, not in papers folder). Supplementary material may contain additional details about the Bayesian learner model implementation, validation study, and probability schedules. - No individual-level fitted parameter values (model is not fitted to individuals) - No effect sizes in standard formats (Cohen's d, η²) — results reported as regression coefficients and correlations
- **other_notes:** - This paper uses the Bayesian learner model from Behrens et al. (2008) as an optimal observer model. The model is not fitted with free parameters to individual participants. Instead, it generates trial-by-trial optimal probability estimates that are used as regressors in a multilevel logistic regression. The main analytical focus is on how self-esteem change moderates the degree to which participants' choices align with these optimal learner models. - The social-learning task was previously used by Cook et al. (2014, 2019) and Behrens et al. (2008). - The paper explicitly calls for future work using neuroimaging and computational modelling (with individual-level fitting) to further investigate these effects.
- **re_extract_flag:** false (full text accessible; supplement not in folder but main text extraction is complete)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target+context
- spec_source = social
- tax_domain_A_influence_transmission
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_instructed
- tax_model_bayesian
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_social_weight
- tax_rr_primary_topic = advice_taking
- tax_rr_secondary_topic = self_esteem
- tax_rr_topic_advice_taking
- tax_rr_topic_self_esteem
- tax_social_nonsocial_comparison
- tax_topic_advice_taking
- tax_topic_self_esteem
