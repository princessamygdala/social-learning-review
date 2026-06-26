# Lengersdorff et al. (2020)

- **study_id:** `af2dc2132f93e9b22_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lengersdorff, L. L., Wagner, I. C., Lockwood, P. L., & Lamm, C. (2020). When implicit prosociality trumps selfishness: The neural valuation system underpins more optimal choices when learning to avoid harm to others than to oneself. *The Journal of Neuroscience*, *40*(38), 7286–7299. https://doi.org/10.1523/JNEUROSCI.0842-20.2020
- **citation_short:** Lengersdorff et al. (2020)
- **doi:** 10.1523/JNEUROSCI.0842-20.2020
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** UniversityofVienna,Vienna,1010,Austria,2DepartmentofExperimentalPsychology,UniversityofOxford,Oxford,OX13PH,UnitedKingdom,; Mittmann,AndréLüttig,SophiaShea,andLeonieBrögforassistanceduring personalharmaversion”hasbeenproposedasthebasisofproso-; ether humans are as good at learning to avoid others’ harm (prosocial learning) as they; CentreforHumanBrainHealth,UniversityofBirmingham,Birmingham,B152TT,UnitedKingdom; DepartmentofCognition,Emotion,andMethodsinPsychology,FacultyofPsychology,; ethe Datareportedherewereacquiredaspartofalongitudinalprojectinves-; ethe ful learningsignal,indicatingtheimm
- **code_url:** https://osf.io/h9txe/

## Computational level
- **study_focus:** Prosocial learning; harm avoidance learning for self vs. other
- **study_focus_short:** Prosocial learning; harm avoidance learning for self vs. other
- **learning_mode_description:** - Learning mode: Learning from pain/no-pain outcomes of one's own choices to avoid harm to self or another person   - Learning from:     - Source type (non-social): self       - The participant makes all choices     - Source content (non-social): outcome       - Painful vs. non-painful electrical stimulation feedback   - Learning about:     - Target type (social): other (confederate) — in the prosocial condition     - Target type (non-social): self — in the self-relevant condition     - Target content (social/non-social): outcome (harm avoidance)       - Which abstract symbol minimizes the probability of painful stimulation to self or other
- **task_description:** Participants chose between two abstract symbols on each trial to avoid painful electrical stimulation delivered to themselves (Self condition) or to a confederate (Other condition); one symbol had a 70% chance of no pain, the other 30%. Three blocks of 16 trials per condition (96 total trials) were completed in alternating order inside an fMRI scanner.
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), dyadic (male confederate partner)
- **n_players:** dyadic (2)
- **partner_type:** confederate
- **stimuli:** Abstract symbols (pairs), color-coded arrows (red = pain, blue = no pain), electrical stimulation, photographs of confederate with neutral/painful facial expressions
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Participants made significantly more optimal choices for Other than Self (GLMM: β = 0.099, χ² = 5.78, p = .016)   - Optimal choices increased over trials (β = 0.108, χ² = 55.92, p < .001)   - Winning model: higher inverse temperature (value sensitivity) for Other than Self (95% HDI of μ_β,Other − μ_β,Self = [0.03, 0.29]; transformed difference = 0.80 [0.11, 1.54])   - Difference in optimal choices fully mediated by value sensitivity (indirect effect = 0.059, 95% BCa-CI = [0.044, 0.077]; direct effect non-significant p = .666)   - Correlation between difference in optimal choices and difference in value sensitivity (r = 0.476, p < .001)   - Emotional contagion positively predicted prosocial value sensitivity difference (standardized β = 0.43, SE = 0.12, t(81) = 3.614, p < .001)   - Proximal responsivity negatively predicted prosocial value sensitivity difference (standardized β = −0.36, SE = 0.13, t(81) = −2.735, p = .008)   - QCAE subscales explained significant variance in β_Other − β_Self (R² = 0.183, F(5,81) = 3.62, p = .005)   - vmPFC value difference signal correlated with β_Other − β_Self at individual level (whole-brain correlation)   - vmPFC showed increased connectivity with rTPJ during Other vs. Self choices (gPPI; cluster peak: 46, −64, 20, z = 4.47)   - Posterior predictive check correlations: self r = 0.757 [0.678, 0.831]; other r = 0.796 [0.721, 0.867]
- **effect_size:** - Main Results:   - Participants made significantly more optimal choices for Other than Self (GLMM: β = 0.099, χ² = 5.78, p = .016)   - Optimal choices increased over trials (β = 0.108, χ² = 55.92, p < .001)   - Winning model: higher inverse temperature (value sensitivity) for Other than Self (95% HDI of μ_β,Other − μ_β,Self = [0.03, 0.29]; transformed difference = 0.80 [0.11, 1.54])   - Difference in optimal choices fully mediated by value sensitivity (indirect effect = 0.059, 95% BCa-CI = [0.044, 0.077]; direct effect non-significant p = .666)   - Correlation between difference in optimal choices and difference in value sensitivity (r = 0.476, p < .001)   - Emotional contagion positively predicted prosocial value sensitivity difference (standardized β = 0.43, SE = 0.12, t(81) = 3.614, p < .001)   - Proximal responsivity negatively predicted prosocial value sensitivity difference (standardized β = −0.36, SE = 0.13, t(81) = −2.735, p = .008)   - QCAE subscales explained significant variance in β_Other − β_Self (R² = 0.183, F(5,81) = 3.62, p = .005)   - vmPFC value difference signal correlated with β_Other − β_Self at individual level (whole-brain correlation)   - vmPFC showed increased connectivity with rTPJ during Other vs. Self choices (gPPI; cluster peak: 46, −64, 20, z = 4.47)   - Posterior predictive check correlations: self r = 0.757 [0.678, 0.831]; other r = 0.796 [0.721, 0.867]
- **learning_from:** Self; own choice outcomes (painful vs. non-painful electrical stimulation)
- **learning_about:** Other (confederate) in prosocial condition; self in self-relevant condition; harm avoidance — which symbol minimizes pain probability  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** RW with outcome-specific learning rates (α+, α−) and condition-specific inverse temperature (β_Self, β_Other)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "M0", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BF (mixture model)"}  — single α, single β - {"name": "M1", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BF (mixture model)"}  — α+, α−, single β - {"name": "M2.1", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BF (mixture model)"} — α+ per condition (random effect only), α−, β - {"name": "M2.2", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BF (mixture model)"} — α+ per condition (random + fixed effect), α−, β - {"name": "M3.1", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BF (mixture model)"} — α+, α− per condition (random effect only), β - {"name": "M3.2", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BF (mixture model)"} — α+, α− per condition (random + fixed effect), β - {"name": "M4.1", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BF (mixture model)"} — α+, α−, β per condition (random effect only) - {"name": "M4.2 (winning)", "family": "Rescorla-Wagner", "n_params": 4, "metric": "BF (mixture model)"} — α+, α−, β_Self, β_Other (random + fixed effect) - {"name": "M5.1", "family": "Rescorla-Wagner", "n_params": 5, "metric": "BF (mixture model)"} — α+ per condition (random), α−, β per condition - {"name": "M5.2", "family": "Rescorla-Wagner", "n_params": 5, "metric": "BF (mixture model)"} — α+ per condition (random + fixed), α−, β per condition - {"name": "M6.1", "family": "Rescorla-Wagner", "n_params": 5, "metric": "BF (mixture model)"} — α+, α− per condition (random), β per condition - {"name": "M6.2", "family": "Rescorla-Wagner", "n_params": 5, "metric": "BF (mixture model)"} — α+, α− per condition (random + fixed), β per condition
- **model_mb_mf:** MF
- **model_params:** - α+ (learning rate for positive outcomes / no-pain): μ = 0.37 [0.26, 0.49] (transformed), logit-scale μ = −0.53 [−1.04, −0.01] - α− (learning rate for negative outcomes / pain): μ = 0.14 [0.10, 0.18] (transformed), logit-scale μ = −1.83 [−2.19, −1.46] - β_Self [S] (inverse temperature / value sensitivity for self-relevant learning): μ = 4.73 [3.27, 6.33] (transformed), log-scale μ = 1.54 [1.20, 1.86] - β_Other [S] (inverse temperature / value sensitivity for prosocial learning): μ = 5.53 [3.82, 7.39] (transformed), log-scale μ = 1.70 [1.36, 2.02] - μ_β,Other − μ_β,Self = 0.16 [0.03, 0.29] (log-scale); 0.80 [0.11, 1.54] (transformed)
- **social_param:** β_Other — inverse temperature (value sensitivity) parameter specific to prosocial learning; significantly higher than β_Self, indicating participants were more sensitive to value differences when choosing for another person.
- **social_param_name:** β_Self
- **social_param_value:** 4.73
- **social_param_sd:** 
- **social_param_range:** 3.27–6.33
- **model_comparison_metric:** Bayes Factors (via mixture model approach; Kamary et al., 2014)
- **how_model_fit:** individual-level-fit (hierarchical Bayesian modeling with MCMC via STAN)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + PPI (generalized psychophysiological interaction)
- **contrast:** - ΔValue (value of chosen − unchosen symbol) parametric modulator during choice phase → vmPFC, subgenual ACC, precuneus, bilateral MTG - Correlation of [ΔValue,Other − ΔValue,Self] with [β_Other − β_Self] → vmPFC, precuneus, left angular gyrus - gPPI: vmPFC connectivity, Other > Self → rTPJ (right middle temporal gyrus/angular gyrus) - Positive > Negative outcomes → ventral striatum, vmPFC - Negative > Positive outcomes → bilateral AI, AMCC, supramarginal gyrus - (Negative − Positive)_Self > (Negative − Positive)_Other → bilateral AI, AMCC (stronger self-relevant aversive responses) - Prediction errors during prosocial > self-relevant → bilateral dorsomedial PFC, right orbitofrontal cortex
- **key_regions:** Value sensitivity in vmPFC and subgenual ACC; individual differences in prosocial value sensitivity correlated with vmPFC and precuneus activity; vmPFC-rTPJ connectivity increased during prosocial choices; outcome processing in bilateral AI and AMCC (stronger for self); prediction errors in dmPFC and OFC (stronger for other).
- **key_regions_abbrev:** vmPFC, mPFC, dmPFC, OFC, ACC, sgACC, TPJ, AI, precuneus
- **coordinates_peak:** Parametric modulation by ΔValue: - L/R precuneus: 4, −52, 18 - L/R superior frontal gyrus, medial orbital (vmPFC): 0, 58, −6 - L middle temporal gyrus: −62, −32, 2 - R superior temporal gyrus: 60, −26, 2 - R fusiform gyrus: 36, −52, −4 - L hippocampus: −20, −16, −20 - L angular gyrus: −46, −70, 24 - L/R olfactory cortex: 0, 8, −14 - L superior temporal gyrus: −34, −22, 2 - R postcentral gyrus: 48, −24, 62  Correlation [ΔValue,Other − ΔValue,Self] x [β_Other − β_Self]: - L/R precuneus: 6, −54, 24 - L/R superior frontal gyrus, medial orbital (vmPFC): 2, 52, −10 - L angular gyrus: −40, −64, 24  gPPI: vmPFC connectivity (Other > Self): - R middle temporal gyrus (rTPJ): 46, −64, 20
- **analysis_type:** whole-brain  ---  ## QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 96 males (ages 18–35); 91 included in fMRI analyses (5 excluded for excessive head motion); 87 included in empathy trait analyses (9 missing questionnaire data); 6 participants reported doubts about confederate deception (after session 2, 2 weeks later)
- **population_category:** healthy adults
- **population_age_range:** 18–35
- **ecological_validity:** Moderate. Uses electrical pain stimulation (ecologically relevant harm signal) rather than abstract monetary outcomes, increasing ecological validity for harm avoidance. However, the confederate paradigm with deception limits naturalistic social interaction; stimuli are abstract symbols; choices do not involve any cost-benefit trade-off between self and other (non-competitive); only males tested.
- **eligibility_flag:** 
- **concerns:** Only male participants tested, limiting generalizability. Confederate deception paradigm — 6/96 participants reported doubts about confederate (though after session 2). Reputation concerns cannot be ruled out as participant knew confederate would observe outcomes. Self vs. Other conditions were not in direct conflict (no trade-off). Cannot distinguish whether prosocial advantage is specific to physical harm or would extend to financial harm domains.
- **limitations_reported:** Only tested men, limiting conclusions to males; 6 of 96 participants reported doubts about confederate after second session — unclear if doubts were present during first session; cannot rule out that reputation concerns (rather than prosociality) contributed to better Other performance since confederate knew outcomes; cannot determine whether prosocial advantage is specific to physical harm contexts versus financial loss; task did not involve conflict between self-harm and other-harm minimization; GLM-based analyses may be too coarse to detect subtle differences in average VMPFC activation between conditions.
- **limitations_categorized:** limited generalizability (male-only sample); demand characteristics / deception concerns; confound with reputation motivation; limited ecological validity (no self-other trade-off); task simplicity (no conflict between self/other goals); methodological sensitivity (GLM may miss subtle effects)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - wc_guidelines rule 3 (simulate): MEDIUM — posterior predictive checks are reported (post-hoc validation), but no evidence of simulation prior to data fitting - wc_guidelines rule 5 (parameter recovery): HIGH confidence it was not done — not mentioned - wc_guidelines rule 6 (model recovery): HIGH confidence it was not done — not mentioned - coordinates for outcome-related and prediction-error contrasts: MEDIUM — main text references Extended Data Figures 4-1 and 4-2 which likely contain these coordinates, but no supplement file was available for extraction
- **cannot_find:** - Supplement not available (no _Supplements file found in papers folder). Extended Data Figures 4-1 and 4-2 referenced in main text likely contain additional coordinate tables for outcome and prediction error contrasts. These coordinates could not be extracted. - Exact n_params for each model variant is approximate — the hierarchical models have population-level hyperparameters in addition to individual-level parameters; the counts above reflect the number of distinct free parameter types per participant
- **other_notes:** Data were collected as part of a larger longitudinal project on violent video game effects; only session 1 (pre-intervention) data analyzed here. The Extended Data figures (4-1, 4-2) referenced in the text are part of the journal's online supplementary system (JNeurosci Extended Data) but were not available as a separate supplement file. Code and data shared at https://osf.io/53qvd/. Patricia Lockwood is a co-author on this paper.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
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
- tax_rr_param_learning_rate
- tax_rr_param_temperature
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = moral_harm
- tax_rr_topic_moral_harm
- tax_rr_topic_prosocial_altruism
- tax_topic_moral_harm
- tax_topic_prosocial_altruism
