# Lockwood et al. (2020)

- **study_id:** `aad116851b47281bd_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lockwood, P. L., Klein-Flügge, M. C., Abdurahman, A., & Crockett, M. J. (2020). Model-free decision making is prioritized when learning to avoid harming others. *Proceedings of the National Academy of Sciences*, *117*(44), 27719–27730. https://doi.org/10.1073/pnas.2010890117
- **citation_short:** Lockwood et al. (2020)
- **doi:** 10.1073/pnas.2010890117
- **publication_type:** peer-reviewed journal (pnas)
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofExperimentalPsychology,UniversityofOxford,OxfordOX39DU,UnitedKingdom;cCentreforHumanBrainHealth,SchoolofPsychology,; DepartmentofExperimentalPsychology,UniversityofOxford,OxfordOX13PH,UnitedKingdom;bWellcomeCentreforIntegrativeNeuroimaging,; UniversityofBirmingham,BirminghamB152TT,UnitedKingdom;anddDepartmentofPsychology,YaleUniversity,NewHaven,CT06511; University,Cambridge,MA,andacceptedbyEditorialBoardMemberMichaelS; division routehomewasunexpectedlyblocked,whereasapurelymodel-; ether the moral consequences of actions affect the; ethercommonordistinctneuralprocessesareengagedwhen
- **code_url:** https://osf.io/3stp9/files/

## Computational level
- **study_focus:** Harm avoidance learning; model-free vs. model-based balance when learning to avoid harming others vs. self
- **study_focus_short:** Harm avoidance learning
- **learning_mode_description:** - Learning mode: Learning from aversive outcomes (electric shocks) to self or a stranger to avoid harmful actions   - Learning from:     - Source type (non-social): self (own actions/choices)     - Source content (non-social): outcome (pain / no pain to self or other)   - Learning about:     - Target type (social): other (anonymous stranger) [and non-social: self]     - Target content (social): outcome (harm avoidance — which actions lead to shock for other)     - Target content (non-social): outcome (harm avoidance — which actions lead to shock for self)
- **task_description:** Participants completed a two-step decision-making task (hybrid Daw et al./Kool et al. design) where first-stage choices probabilistically led to one of two second-stage states, and second-stage choices led to shock or no-shock outcomes for either themselves or an anonymous stranger. The probability of shock drifted over time, requiring continuous learning; 10% of accumulated shocks were delivered at the end of the session.
- **task_paradigm:** Two-step task
- **players:** Single agent (participant as decider), single target (anonymous stranger as receiver)
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Abstract fractal images, color-coded zones, electric shock/no-shock outcomes, instruction cues (self/other)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Model-free learning (main effect of outcome on stay/switch): d = 0.77   - Model-based learning (outcome × transition interaction): d = −0.53   - Greater model-free behavior for other vs. self (outcome × recipient interaction): d = −0.39   - No interaction of model-based component with recipient: d = −0.08, BF₀₁ = 5.1 (substantial evidence for null)   - ω parameter lower for other (0.45) than self (0.55): d = 0.40, 95% CI [0.06, 0.74]   - Thalamus/caudate: other PE > self PE (FWE-SVC): d = 0.39 (other PE), d = −0.50 (self PE)   - sgACC: stay vs. switch after no pain for other (FWE whole-brain corrected, Z = 3.88)   - sgACC response correlated with model-free × recipient behavioral interaction: r(31) = 0.36   - sgACC–dlPFC connectivity: switch vs. stay after no pain for other (FWE whole-brain, Z = 4.12)   - Rejection of instrumental harm correlated with model-free moral learning: r(34) = 0.37   - Outcome sensitivity correlated with switching after harm to other: r(33) = −0.37   - Outcome sensitivity correlated with thalamus/caudate other > self PE: r(31) = 0.385   - Outcome sensitivity correlated with sgACC model-free signal: r(30) = −0.374
- **effect_size:** - Main Results:   - Model-free learning (main effect of outcome on stay/switch): d = 0.77   - Model-based learning (outcome × transition interaction): d = −0.53   - Greater model-free behavior for other vs. self (outcome × recipient interaction): d = −0.39   - No interaction of model-based component with recipient: d = −0.08, BF₀₁ = 5.1 (substantial evidence for null)   - ω parameter lower for other (0.45) than self (0.55): d = 0.40, 95% CI [0.06, 0.74]   - Thalamus/caudate: other PE > self PE (FWE-SVC): d = 0.39 (other PE), d = −0.50 (self PE)   - sgACC: stay vs. switch after no pain for other (FWE whole-brain corrected, Z = 3.88)   - sgACC response correlated with model-free × recipient behavioral interaction: r(31) = 0.36   - sgACC–dlPFC connectivity: switch vs. stay after no pain for other (FWE whole-brain, Z = 4.12)   - Rejection of instrumental harm correlated with model-free moral learning: r(34) = 0.37   - Outcome sensitivity correlated with switching after harm to other: r(33) = −0.37   - Outcome sensitivity correlated with thalamus/caudate other > self PE: r(31) = 0.385   - Outcome sensitivity correlated with sgACC model-free signal: r(30) = −0.374
- **learning_from:** Self; own action outcomes (pain/no pain delivered to self or other)
- **learning_about:** Other (anonymous stranger); which actions lead to harmful outcomes (shock) for other vs. self  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Hybrid MB/MF with separate ω for self/other: 6-parameter model (αPain, αNoPain, β, ρ, ωSelf, ωOther; λ fixed at 1)
- **model_family:** MB/MF hybrid
- **model_class:** PE learning
- **all_models_tested:** Fitted separately to self and other: 1. M1 (7-param): αStage1, αStage2, βStage1, βStage2, ρ, λ, ω — full Daw et al. model; BIC metric 2. M2 (6-param): αStage1, αStage2, βStage1, βStage2, ρ, ω (λ=1); BIC metric 3. M3 (5-param): α, β, ρ, λ, ω; BIC metric 4. M4 (4-param): α, β, ρ, ω (λ=1); BIC metric 5. M5 (5-param, winning for separate fits): αPain, αNoPain, β, ρ, ω (λ=1); BIC metric  Fitted to pooled self+other data: 6. M5-pooled (5-param): αPain, αNoPain, β, ρ, ω (shared); BICint 7. M6 (6-param, overall winning): αPain, αNoPain, β, ρ, ωSelf, ωOther (λ=1); BICint, XP = 0.1088 (but BICint lowest at 22151) 8. M7 (7-param): αPain, αNoPain, β, ρSelf, ρOther, ωSelf, ωOther (λ=1); BICint
- **model_mb_mf:** MB/MF hybrid
- **model_params:** - αPain: learning rate for pain outcomes (mean = 0.35) - αNoPain: learning rate for no-pain outcomes (mean = 0.35) - β: inverse temperature / softmax parameter (mean = 3.81) - ρ: perseverance parameter (mean = 0.63) - ωSelf [S]: model-free/model-based weighting for self (mean = 0.55; higher = more model-based) - ωOther [S]: model-free/model-based weighting for other (mean = 0.45; higher = more model-based) - λ: eligibility trace (fixed at 1)
- **social_param:** ωSelf and ωOther — separate model-free/model-based weighting parameters for self and other conditions. ωOther significantly lower than ωSelf (0.45 vs. 0.55, d = 0.40), indicating more model-free learning when avoiding harm to others.
- **social_param_name:** ωSelf
- **social_param_value:** 0.55
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BICint (integrated BIC), exceedance probabilities via SPM's spm_BMS; also AIC, BIC, negLL reported
- **how_model_fit:** Individual-level fit using hierarchical Bayesian MAP estimation with expectation-maximization
- **data_type_fit_to:** Choice behavior (first-stage stay/switch decisions)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors from computational model); also PPI (psychophysiological interaction)
- **contrast:** - GLM1: Model-free PE at outcome, self and other separately; other PE > self PE (thalamus/caudate) - GLM1: Value difference at first-stage choice; state PE at second-stage choice - GLM1: VS bilaterally: PE for pain avoidance, self and other combined - GLM2: Stay vs. switch at choice after no pain for other > self (sgACC) - GLM3: Model-free (outcome) vs. model-based (outcome × transition) parametric regressors at choice (sgACC confirmation) - GLM4 (PPI): sgACC seed, switch vs. stay after no pain for other → dlPFC connectivity - GLM5 (PPI control): sgACC seed, switch vs. stay after no pain for self → no significant connectivity
- **key_regions:** Model-free PE for other > self in thalamus/caudate; bilateral VS tracked PE regardless of recipient; sgACC tracked model-free influence at choice for other (stay vs. switch after no pain); sgACC–dlPFC connectivity increased when switching after no pain for other; TPJ showed inverse pattern to sgACC (switch > stay after no pain for other).
- **key_regions_abbrev:** caudate, dlPFC, ACC, sgACC, TPJ, AI, thalamus
- **coordinates_peak:** - Right ventral striatum: 10, 12, −4 (Z = 5.84, k = 236, FWE whole-brain) - Left ventral striatum: −16, 6, −10 (Z = 5.77, k = 458, FWE whole-brain) - Thalamus/caudate (other PE > self PE): 16, −18, 0 (Z = 3.50, k = 84, FWE-SVC anatomical thalamus) - Thalamus/caudate (functional ROI): 12, −2, 4 (Z = 4.08, k = 125, FWE-SVC Neurosynth pain) - Thalamus/caudate (meta-analysis ROI): 10, −4, 4 (Z = 3.83, k = 54, FWE-SVC) - sgACC (stay vs. switch, no pain other): −2, 36, 6 (Z = 3.88, K = 498, FWE whole-brain) - sgACC (GLM3 confirmation): 0, 36, 6 (Z = 3.46, K = 29, FWE-SVC) - dlPFC (PPI with sgACC): −46, 38, 26 (Z = 4.12, k = 382, FWE whole-brain) - Right TPJ (stay vs. switch, no pain other): 54, −38, 34 (Z = 3.56, K = 39, FWE-SVC) - dACC/pre-SMA (state PE): −6, 10, 52 (Z = 4.85, K = 906, FWE whole-brain)
- **analysis_type:** both (whole-brain FWE cluster-corrected + ROI/SVC for a priori regions)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 41 recruited; N = 36 for behavioral analyses (16 female, 20 male, age 18–36); N = 34 for parametric fMRI; N = 33 for stay/switch fMRI analyses. 80% power to detect d = 0.50 with 33 subjects.
- **population_category:** healthy adults
- **population_age_range:** 18–36
- **ecological_validity:** LOW. Lab-based fMRI task with abstract stimuli (fractals), electric shock as proxy for harm, anonymous stranger never met; no real social interaction. However, real consequences (10% of shocks delivered) and careful pain-matching across self/other conditions improve validity somewhat.
- **eligibility_flag:** 
- **concerns:** - The two-step task variant used does not incentivize model-based strategy, which means apparently model-free behavior could reflect a rational MB agent who learned MB is not worth the effort (authors acknowledge this but show no increase in MF over time) - "Model-free" behavior on two-step tasks has been argued to potentially reflect use of different/nonstandard models rather than true model-free processing (ref 65, da Silva & Hare 2020) - Relatively small fMRI sample (N = 33–34) - Exploratory individual difference analyses (moral judgment correlations) not corrected for multiple comparisons - Opposing PE encoding in thalamus (positive for other, negative for self) interpretation is speculative - Anonymous stranger paradigm limits generalizability to real social relationships
- **limitations_reported:** Participants never met or had information about the receiver, limiting examination of how social knowledge influences moral learning; task variant did not incentivize model-based strategy, meaning a purely model-based learner could learn to become model-free over time; hybrid MB/MF strategy was most common (not purely MF); findings may not extend to other social decisions (rewards for others, monetary losses, non-human species); individual difference analyses were exploratory and should be tested in larger samples; cannot completely rule out effort or inattention accounts
- **limitations_categorized:** limited ecological validity; task simplicity; limited generalizability; small sample size for individual differences; alternative explanations not fully ruled out; anonymous partner limits social validity
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
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_comparison (MEDIUM): For pooled fits, the BICint favors M6 but the exceedance probability is only 0.11 (M5 has XP = 0.89). Authors rely on the BICint + significant parameter difference to justify M6 as winning model. - wc_8 (MEDIUM): No formal posterior predictive check, but model fit quality was compared across conditions.
- **cannot_find:** Nothing critical missing; all fields extractable from full text + supplement.
- **other_notes:** First author is Patricia Lockwood (the persona for this review). This paper is a key contribution linking MB/MF RL framework to moral/social learning. Code and data publicly available at OSF (https://osf.io/3stp9/) and NeuroVault (collection 8797). The paper uses the Daw et al. (2011) two-step task adapted for aversive outcomes and self/other conditions.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_MB_MF_balance
- tax_param_perseveration
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_MB_MF_hybrid
- tax_rr_model_family = MB_MF_hybrid
- tax_rr_param_MB_MF_balance
- tax_rr_param_PE_signal
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = moral_harm
- tax_rr_topic_moral_harm
- tax_rr_topic_prosocial_altruism
- tax_topic_moral_harm
- tax_topic_prosocial_altruism
