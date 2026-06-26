# Westhoff et al. (2021)

- **study_id:** `ad11fe61eb364c4c2_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Westhoff, B., Blankenstein, N. E., Schreuders, E., Crone, E. A., & van Duijvenvoorde, A. C. K. (2021). Increased ventromedial prefrontal cortex activity in adolescence benefits prosocial reinforcement learning. *Developmental Cognitive Neuroscience*, *52*, 101018. https://doi.org/10.1016/j.dcn.2021.101018
- **citation_short:** Westhoff et al. (2021)
- **doi:** 10.1016/j.dcn.2021.101018
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department of Clinical, Neuro and Developmental Psychology, Vrije Universiteit, Amsterdam, Netherlands; Institute of Psychology, Leiden University, Wassenaarseweg 52, 2333 AK Leiden, Netherlands; School of Social and Behavioural Sciences, Erasmus University Rotterdam, Netherlands; Institute for Brain and Cognition, Leiden, Netherlands; eth Schreudersa,b,d, Eveline; schools and local advertise-; lableonline2October2021; lable at ScienceDirect; emails: a.c.k.van.duijvenvoorde@fsw.leidenuniv.nl, b.westhoff@fsw.leidenuniv.nl
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning — developmental differences in learning to benefit others via reinforcement learning across adolescence, and the neural tracking of prediction errors for self vs. others.
- **study_focus_short:** Prosocial learning
- **learning_mode_description:** - Learning mode: Learning from monetary outcomes (gains/losses) about reward contingencies of stimuli, for oneself and for an unknown other   - Learning from:     - Source type (non-social): self (own choices and experienced outcomes)       - Source content (non-social): outcome (monetary gain/loss feedback, +1 or -1 point)   - Learning about:     - Target type (social): other (unknown peer participant)       - Target content (social): outcome (which stimulus yields positive monetary outcomes for the other)     - Target type (non-social): self       - Target content (non-social): outcome (which stimulus yields positive monetary outcomes for self)  Note: The task has three conditions (Self, Other, No One). The key social learning condition involves learning stimulus-reward associations where outcomes benefit an unknown other (prosocial learning). The Self and No One conditions serve as comparisons.
- **task_description:** Participants performed a two-choice probabilistic reinforcement learning task where they selected between two stimuli (common objects) with 75%/25% reward contingencies. Outcomes (+1 or -1 point) resulted in monetary consequences for themselves (Self), an unknown other participant (Other), or no one (No One), across 144 trials (48 per condition).
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), single-target (unknown other peer participant who cannot reciprocate)
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Common object images (chairs, apples, shoes), binary monetary feedback (+1/-1 point)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Performance improved linearly with age (GLMM main effect of Age, p = .001) - Age-related improvement in performance was larger for Other than Self (Age x Condition interaction, p = .005; Other vs Self p = .009) - Learning rates decreased with age (b = -0.04, p = .023), more strongly for Other than Self (b = -0.02, p < .001) - Common PE coding across all conditions in vmPFC, ventral striatum, and sgACC (conjunction) - Left ventral striatum responded more to Self PEs than Other PEs (Z = 4.37, p < .001 SVC-FWE) - vmPFC showed age-related increase in Other PE > Self PE coding (Z = 4.95, p = .004 SVC-FWE) - Cognitive empathy related to better prosocial learning performance (rs = 0.30, p = .01) and lower learning rates for Other (rs = -0.26, p = .027) - Cognitive empathy related to greater Other > Self PE activation in vmPFC (rs = 0.31, p = .007)
- **effect_size:** - Age x Condition on performance: p = .005 (no Cohen's d reported) - Age effect on learning rate: b = -0.04 - Age x Condition on learning rate (Other vs Self): b = -0.02 - Cognitive empathy - prosocial performance: rs = 0.30 - Cognitive empathy - Other learning rate: rs = -0.26 - Cognitive empathy - vmPFC Other>Self PE: rs = 0.31 - vmPFC conjunction PE: Z = 5.33 - VS Self > Other PE: Z = 4.37 - vmPFC age-related Other > Self PE: Z = 4.95
- **learning_from:** Self; own choice outcomes (monetary gain/loss feedback on chosen stimulus)
- **learning_about:** Other (unknown peer); which stimulus produces positive monetary outcomes for the other person. Also: Self; which stimulus produces positive outcomes for self.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RW (1 LR per condition: α_self, α_other, α_noone; 1 shared β)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "RW 1-learning-rate", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"}, {"name": "RW 2-learning-rates (separate for gains/losses)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "BIC"}]  Note: Models were fit separately per condition. The 1-learning-rate model had superior BIC fit for the majority of participants in each condition (81.1% Self, 74.3% Other, 76.7% No One).
- **model_mb_mf:** MF
- **model_params:** - α (learning rate) [S for Other condition]: bounded 0-1, fitted separately per condition. Mean values not reported in main text (noted as in Supplementary Table S1). Prior: Beta(1.2, 1.2). Learning rates decreased with age; were higher for Other and No One than Self. - β (inverse temperature): shared across conditions, Gaussian prior (0, 10). Increased with age (see Fig. S2).
- **social_param:** α_other — learning rate for the Other (prosocial) condition, indexing how quickly participants update stimulus values when outcomes benefit an unknown other. Lower α_other (more integration across trials) was associated with better prosocial learning and higher cognitive empathy.
- **social_param_name:** α_other
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC
- **how_model_fit:** individual-level-fit (MAP estimation with weakly informative priors per subject per condition)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — GLM with parametric modulators from RL model: expected value at choice onset, prediction error at outcome onset.
- **contrast:** - Conjunction: PE Self ∩ PE Other ∩ PE No One (vmPFC, VS, sgACC) - Self PE > Other PE (left ventral striatum: Z = 4.37, p < .001 SVC-FWE) - Other PE > Self PE (no significant voxels in ROIs at group level) - Other PE > Self PE × Age linear (vmPFC: Z = 4.95, p = .004 SVC-FWE)
- **key_regions:** Common PE coding in vmPFC, bilateral ventral striatum, and sgACC. Self-specific PE coding in left ventral striatum. Age-related increase in prosocial PE coding (Other > Self) in vmPFC. Cognitive empathy correlated with prosocial PE vmPFC activation.
- **key_regions_abbrev:** VS, striatum, vmPFC, mPFC, ACC, sgACC
- **coordinates_peak:** Conjunction (PE all conditions): - vmPFC: -9, 44, -11 - L ventral striatum: -9, 11, -11 - R ventral striatum: 12, 14, -8 - L sgACC: -6, 14, -8 - R sgACC: 6, 17, -8 - R sgACC: 9, 8, -14  Self PE > Other PE: - L ventral striatum: 12, 11, -11  Other PE > Self PE × Age (linear): - vmPFC: -15, 50, 8  Note: The coordinate "12, 11, -11" for the left ventral striatum labeled "Self PE > Other PE" appears to be in the right hemisphere based on the positive x-coordinate. The paper labels it as left ventral striatum; this may be a radiological convention issue or reporting error.
- **analysis_type:** ROI (primary hypotheses tested in a priori anatomical ROIs: bilateral ventral striatum, vmPFC, sgACC, with SVC-FWE correction; whole-brain results reported in supplemental tables)  ---  ### QUALITY
- **analysis_type_clean:** ROI
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 74 (39 female; age range 9.03-21.77 years, M = 15.64, SD = 4.18); all fMRI. Two participants excluded from original 76 (psychiatric diagnosis, scanner discomfort). Four participants missing one run.
- **population_category:** healthy adults
- **population_age_range:** M=15.64 (SD=4.18)
- **ecological_validity:** Limited — abstract probabilistic learning task with unknown anonymous other who cannot reciprocate; no real social interaction; stimuli are common objects rather than social stimuli; monetary outcomes rather than real prosocial consequences. However, the developmental design (ages 9-21) provides valuable cross-sectional insight.
- **eligibility_flag:** 
- **concerns:** - Cross-sectional design limits causal/developmental inference (authors acknowledge need for longitudinal studies) - The x-coordinate sign for the "left ventral striatum" in the Self > Other PE contrast (x = 12) suggests right hemisphere - No separate social parameter in the model — social vs. non-social learning is captured only by fitting the same model separately per condition, not by a dedicated social parameter within the model - The No One condition showed intermediate neural patterns that are difficult to interpret - Mean fitted parameter values not reported in main text (referenced to Supplementary Table S1, which is not accessible) - No model with a shared vs. separate learning rate across conditions was formally compared
- **limitations_reported:** Prosocial learning was restricted to unknown others and participants did not meet these others; it would be interesting to extend to other beneficiaries (friends, family); the No One condition showed an intermediate pattern that is difficult to interpret; the study used separate learning rates per condition rather than formally testing whether different parameters are needed across conditions; cross-sectional design; narrower age range (9-21) may have limited ability to detect quadratic effects
- **limitations_categorized:** limited ecological validity; restricted social target (unknown other only); ambiguous control condition; model comparison scope limited; cross-sectional design; restricted age range
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params mean fitted values: MEDIUM confidence — referenced to Supplementary Table S1, not accessible (no supplement file found) - coordinates_peak hemisphere labeling: LOW confidence — x = 12 labeled as "left" ventral striatum in Self > Other PE contrast appears inconsistent - social_param: MEDIUM confidence — no dedicated social parameter in the model; α_other is simply the learning rate fit to the Other condition, not a parameter that explicitly encodes social information
- **cannot_find:** - Mean fitted parameter values (referenced to Supplementary Table S1) - Whole-brain results tables (referenced to Supplementary Tables S2, S5) - Exact BIC values for model comparison (referenced to Fig. S3) - Expected value contrasts (referenced to Supplementary Table S3) - Between-condition contrasts within ROIs (referenced to Supplementary Table S4)
- **other_notes:** - Supplement not accessible as a file in the papers folder. The paper references extensive supplementary materials (Figs. S1-S8, Tables S1-S5) that contain parameter values, model comparison details, whole-brain results, and additional analyses. These are not available for extraction. - This study is a developmental extension of Lockwood et al. (2016), using the same prosocial learning task paradigm adapted for adolescents. - The paper fits the same RL model separately to each condition rather than using a single model with condition-specific parameters, which means the "social parameter" is really just a separately estimated learning rate. - The β parameter was shared across conditions (not separately estimated per condition), though the paper is somewhat ambiguous on this — line 203-204 states β "did not differ between conditions" which could mean it was fit jointly or fit separately and found not to differ.
- **re_extract_flag:** false (full text accessible; supplement not available as separate file but is online supplementary material referenced in the paper)

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_children
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_children
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_topic_prosocial_altruism
- tax_social_nonsocial_comparison
- tax_topic_prosocial_altruism
