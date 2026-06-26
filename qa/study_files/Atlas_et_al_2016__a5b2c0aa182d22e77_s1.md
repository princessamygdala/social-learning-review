# Atlas et al. (2016)

- **study_id:** `a5b2c0aa182d22e77_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Atlas, L. Y., Doll, B. B., Li, J., Daw, N. D., & Phelps, E. A. (2016). Instructed knowledge shapes feedback-driven aversive learning in striatum and orbitofrontal cortex, but not the amygdala. *eLife*, *5*, e15192. https://doi.org/10.7554/eLife.15192
- **citation_short:** Atlas et al. (2016)
- **doi:** 10.7554/eLife.15192
- **publication_type:** peer-reviewed journal
- **year:** 2016.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** lableunder notneedtogetburnttoavoidputtingourhandsonahotstove:Averbalwarningservesasasuffi-; Institutes of Health, Bayview, United States; 3Center for Neural Sciences, New York; Laboratory of Behavior and Mental Health, Peking University, Beijing, China; 6PKU-; Department of Psychology, Princeton Neuroscience Institute, Princeton University,; ether dynamic feedback-drivenaversivelearning ismodulated whenindividualsare; University, New York, United States; 5Department of Psychology, Beijing Key; University, New York, United States; 4Department of Psychology, Columbia; Center for Complementary a
- **code_url:** 

## Computational level
- **study_focus:** Learning from instructions / instructed aversive learning; how socially-conveyed verbal instructions modulate feedback-driven fear conditioning and reversal learning
- **study_focus_short:** Learning from instructions / instructed aversive learning
- **learning_mode_description:** - Learning mode: Learning from verbal instructions and aversive reinforcement about cue-outcome contingencies during fear conditioning with reversals   - Learning from:     - Source type (social): other (experimenter)       - Source content (social): action/policy (verbal instructions about contingencies and reversals)     - Source type (non-social): world       - Source content (non-social): outcome (electric shock / no shock)   - Learning about:     - Target type (non-social): world       - Target content (non-social): state (cue-outcome contingency; which stimulus predicts shock)
- **task_description:** Participants performed Pavlovian fear conditioning with serial reversals (3 reversals, 4 blocks of 20 trials). One image (CS+) was paired with mild electric shock at 30% reinforcement rate; the Instructed Group was informed about initial contingencies and told when reversals occurred, while the Uninstructed Group learned from reinforcement alone.
- **task_paradigm:** Fear conditioning (social)
- **players:** Multi-agent (experimenter provides instructions), single agent (participant) with between-groups design (Instructed Group n=30, 20 learners; Uninstructed Group n=40, 20 learners)
- **n_players:** network (5+)
- **partner_type:** human (live)
- **stimuli:** Angry male faces (Ekman set), mild electric shock (US), verbal/text instructions about contingencies
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Both groups showed differential SCRs that reversed with contingency changes (CS+ > CS-; β = 0.04, t = 5.82, p < 0.0001) - Differential responses were larger in the Instructed Group than Uninstructed Group (β = 0.03, t = 3.98, p = 0.0002) - Instructions immediately updated SCR before reinforcement (β = 0.04, t(19) = 3.50, p = 0.0024) - Instructed reversal parameter ρ = 0.943 in Instructed Group vs. ρ = 0.0 in Uninstructed Group; group difference t(38) = 6.53, p < 0.0001 - Amygdala tracked feedback-driven EV in both groups (bilateral: t(1,19) = 4.21, p = 0.0005) but did NOT update with instructions - Striatum and VMPFC/OFC tracked instruction-based EV in the Instructed Group - DLPFC showed greater activation in Instructed Group; DLPFC response to instructions correlated with instructed reversals in putamen and VMPFC/OFC
- **effect_size:** - SCR differential responding: β = 0.04, t = 5.82 - Group difference in SCR: β = 0.03, t = 3.98 - Instructed reversal on SCR: β = 0.04, t(19) = 3.50 - ρ group difference: t(38) = 6.53 - Amygdala feedback-driven EV (bilateral): t(1,19) = 4.21 - ROI Region effect (Uninstructed): F(2,40) = 5.13 - ROI Region effect (Instructed): F(2,40) = 6.49 - VMPFC/OFC instruction-based EV: t(1,19) = -2.61 - Feedback vs. instruction EV Region effect: F(2,40) = 3.76 - Amygdala feedback > instruction: t(1,19) = 2.57 - VMPFC/OFC instructed reversal: t(1,19) = -4.82
- **learning_from:** Other (experimenter); verbal instructions about contingencies and reversals. World; aversive reinforcement (electric shock).
- **learning_about:** World; cue-outcome contingency (which face predicts shock).  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Modified Rescorla-Wagner with instructed reversal parameter (α, ρ; 2 free params). V_{n+1}(x) = V_n(x) + α·δ_n; upon instruction: V_{n+1}(x_a) = ρ·V_n(x_b) + (1-ρ)·V_n(x_a)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Standard Rescorla-Wagner (feedback-driven)", "family": "Rescorla-Wagner", "n_params": 1, "metric": "Deviance (sum of squared errors)"}, {"name": "Modified Rescorla-Wagner with instructed reversal parameter ρ", "family": "Rescorla-Wagner", "n_params": 2, "metric": "Deviance (sum of squared errors)"}]
- **model_mb_mf:** MF (with instruction-based override parameter)
- **model_params:** - α (learning rate): Instructed Group across-subjects = 0.061; Uninstructed Group across-subjects = 0.042; Instructed within-subjects M = 0.07 (SD = 0.09); Uninstructed within-subjects M = 0.11 (SD = 0.22) - ρ (instructed reversal parameter) [S]: Instructed Group across-subjects = 0.943; Uninstructed Group across-subjects = 0.0; Instructed within-subjects M = 0.69 (SD = 0.32); Uninstructed within-subjects M = 0.10 (SD = 0.25)
- **social_param:** ρ (instructed reversal parameter): determines the extent to which expected value reverses upon verbal instruction delivery. ρ = 1 means EVs of two CSs swap completely; ρ = 0 means no effect of instructions (pure experiential model).
- **social_param_name:** ρ
- **social_param_value:** 0.69
- **social_param_sd:** 0.32
- **social_param_range:** 
- **model_comparison_metric:** Deviance (sum of squared errors from mixed-effects linear regression)
- **how_model_fit:** group-level-fit (across-subjects mixed effects analysis with fixed learning parameters, varying slopes) AND individual-level-fit (within-subjects analysis for each participant separately). Maximum likelihood estimation via Matlab's fminsearch.
- **data_type_fit_to:** skin conductance responses (SCR)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) AND univariate GLM (task-based event-related GLM for instructed reversal analysis)
- **contrast:** - Feedback-driven EV parametric modulator at CS onset (Uninstructed Group) - Instruction-based EV parametric modulator at CS onset (Instructed Group) - Direct comparison: feedback-driven EV vs. instruction-based EV within Instructed Group - CS x Phase interaction (pre- vs. post-instruction reversal) - Main effect of CS without interaction (previous CS+ > previous CS-) - Between-groups contrast across all CS trials (Instructed > Uninstructed) - Brain-behavior correlation: ρ parameter with instructed reversal neural effect - DLPFC instruction response correlated with instructed reversal effect
- **key_regions:** Amygdala tracks feedback-driven EV but NOT instruction-based EV (dissociation). Striatum (bilateral caudate, ventral striatum) and VMPFC/OFC update with instructions. DLPFC (left middle frontal gyrus) shows greater activation in Instructed Group; DLPFC response to instructions correlates with instructed reversals in putamen and VMPFC/OFC. Additional regions: dACC, bilateral insula, thalamus, PAG update with instructions.
- **key_regions_abbrev:** VS, caudate, putamen, striatum, vmPFC, mPFC, dlPFC, OFC, dACC, ACC, insula, amygdala, MFG, thalamus
- **coordinates_peak:** - Left DLPFC (middle frontal gyrus): -43, 43, 21 - Right putamen (DLPFC correlation): 24, 8, 11 - VMPFC/mOFC (DLPFC correlation): -5, 40, -17 - VMPFC/OFC ROI (functionally defined from shock deactivation): -6, 38, -16  Note: The paper references extensive coordinate tables in figure supplements (source data 1 and 2 for each figure supplement). Full coordinate tables are in the online supplementary source data files hosted at eLife, which are not available as separate downloaded supplements. The main text provides only the peaks listed above.
- **analysis_type:** both (ROI-based analyses using a priori amygdala, striatum, VMPFC/OFC ROIs; AND whole-brain voxel-wise FDR-corrected analyses)  ---  ## QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 68 total (46 female; mean age = 22.1, SE = 0.42); Instructed Group n = 30 (20 learners), Uninstructed Group n = 40 (20 learners, 2 excluded from original 40, leaving 38). Primary analyses restricted to 20 learners per group (n = 40 total for main analyses).
- **population_category:** healthy adults
- **population_age_range:** M=22.1
- **ecological_validity:** Low ecological validity. Pavlovian fear conditioning with electric shock in MRI scanner is highly controlled but artificial. Instructions are simple verbal statements about contingencies, not naturalistic social communication. Between-groups design limits within-subject comparisons. Use of angry faces as CSs adds some ecological relevance as biologically prepared stimuli.
- **eligibility_flag:** The "social" element is limited to verbal instructions from an experimenter about contingencies — the learning itself is about non-social cue-shock associations. The social component (instruction delivery) is minimal and one-directional. This is borderline for social learning; the paper primarily studies instructed vs. experiential learning of aversive contingencies. Flag: borderline social context — instructions are socially conveyed but the learning target is non-social (cue-shock contingencies).
- **concerns:** - The "social" agent is the experimenter delivering instructions — not a true social interaction partner - Learner selection criterion (SCR differential in second half of first run) is post-hoc and reduces sample substantially (20/30 Instructed, 20/38 Uninstructed) - Low reinforcement rate (33%) means Uninstructed Group shows slow/marginal reversal learning - Only two models tested (standard RW vs. modified RW with ρ) — limited model space - No formal model comparison (e.g., BIC/AIC) reported; only deviance values - Correlations between feedback-driven and instruction-based EV between reversals acknowledged but not fully addressed - EV, PE, and associability confounded due to algebraic collinearity; authors chose EV for simplicity - DLPFC group difference did not survive FDR correction (uncorrected p < 0.001) - VMPFC/mOFC DLPFC-correlation cluster was below cluster threshold (9 voxels vs. 10 required) - Brain-behavior correlations reported at exploratory threshold (p < 0.001, uncorrected)
- **limitations_reported:** Authors acknowledge that much of the activity in amygdala and striatum may reflect associability and PE rather than EV, and these signals are confounded in the current design due to algebraic collinearity; the current task cannot fully distinguish EV, PE, and associability signals in amygdala and striatum; it is unclear whether instruction-based effects are uniquely human or have parallels in other species; the study used language-based instructions and it is unknown whether non-verbal instruction would produce similar effects; minimizing dropout in OFC/VMPFC reduced parietal cortex coverage; the study did not use a full 2x2 design (instructed vs. uninstructed x initial learning vs. reversals); pupillometry data were corrupted for most participants and could not be analyzed
- **limitations_categorized:** signal confounding (EV/PE/associability collinearity); limited generalizability (species specificity unknown); task simplicity (verbal instructions only); limited brain coverage (reduced parietal signal); incomplete factorial design; data loss (pupillometry)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `eligibility_flag`: MEDIUM — instructions are socially conveyed but learning target is non-social; borderline social learning - `coordinates_peak`: MEDIUM — only 4 peak coordinates reported in main text; full tables are in online figure supplements (source data) hosted at eLife, not in a downloadable supplement PDF - `model_comparison_metric`: LOW — deviance reported but no formal model comparison (BIC/AIC/BMS) - `model_mb_mf`: MEDIUM — classified as MF with instruction override; the ρ parameter could be viewed as a model-based component but the authors frame it as a modification of MF RW - `wc_guidelines` Rule 7: MEDIUM — models were compared via deviance but without formal information criterion
- **cannot_find:** - Full coordinate tables for all contrasts (referenced as online figure supplement source data at eLife) - Formal model comparison statistics (BIC, AIC) — only deviance reported - Effect sizes in standardized form (Cohen's d, η²) — results reported as t-statistics and β coefficients from mixed models
- **other_notes:** This is an eLife paper (open access) with extensive online figure supplements containing source data tables with full coordinates. The supplement files are embedded in the eLife article as source data files, not as a separate downloadable PDF/docx. The paper is primarily about instructed vs. experiential learning of threat associations, with the "social" element being verbal instructions from an experimenter. The hybrid Pearce-Hall model was also tested but results are mentioned as "not shown." The paper bridges aversive learning, instruction effects, and dissociable neural systems — relevant for social influence on learning but not a prototypical social learning study.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_neural = shared
- spec_source = partly
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = threat_fear
- tax_rr_topic_threat_fear
- tax_topic_threat_fear
