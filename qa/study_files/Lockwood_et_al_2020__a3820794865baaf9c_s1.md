# Lockwood et al. (2020)

- **study_id:** `a3820794865baaf9c_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lockwood, P. L., Klein-Flügge, M. C., Abdurahman, A., & Crockett, M. J. (2020). Model-free decision making is prioritized when learning to avoid harming others. *Proceedings of the National Academy of Sciences*, *117*(44), 27719–27730. https://doi.org/10.1073/pnas.2010890117
- **citation_short:** Lockwood et al. (2020)
- **doi:** 10.1073/pnas.2010890117
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofExperimentalPsychology,UniversityofOxford,OxfordOX39DU,UnitedKingdom;cCentreforHumanBrainHealth,SchoolofPsychology,; DepartmentofExperimentalPsychology,UniversityofOxford,OxfordOX13PH,UnitedKingdom;bWellcomeCentreforIntegrativeNeuroimaging,; UniversityofBirmingham,BirminghamB152TT,UnitedKingdom;anddDepartmentofPsychology,YaleUniversity,NewHaven,CT06511; University,Cambridge,MA,andacceptedbyEditorialBoardMemberMichaelS; division routehomewasunexpectedlyblocked,whereasapurelymodel-; ether the moral consequences of actions affect the; ethercommonordistinctneuralprocessesareengagedwhen
- **code_url:** https://osf.io/3stp9/files/

## Computational level
- **study_focus:** Harm avoidance learning; moral learning; model-free vs. model-based learning for self vs. other
- **study_focus_short:** Harm avoidance learning · moral learning
- **learning_mode_description:** - Learning mode: Learning from aversive outcomes (pain/no pain) about which actions avoid harming self vs. a stranger   - Learning from:     - Source type (non-social): self (own actions and their consequences)       - When learning for other: outcomes are delivered to another person, so source content becomes social     - Source content (social/non-social): outcome (pain or no pain delivered to self or other)   - Learning about:     - Target type (social): other (stranger/receiver)       - Also non-social: self     - Target content (social): outcome (harm avoidance — which actions lead to pain vs. no pain for others)       - Also non-social: outcome (harm avoidance for self)  More precisely: - Learning mode: Learning which actions avoid delivering painful electric shocks to oneself and to a stranger via model-free and model-based reinforcement learning   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (pain/no-pain feedback)   - Learning about:     - Target type (non-social): self; Target content (non-social): outcome (pain avoidance for self)     - Target type (social): other (stranger); Target content (social): outcome (pain avoidance for other)
- **task_description:** Participants completed a two-stage decision-making task (hybrid of Daw et al. 2011 and Kool et al. 2016) in which first-stage choices probabilistically led to one of two second-stage states (70% common, 30% rare transitions), where a second choice led to either shock or no-shock outcomes for either themselves or an anonymous stranger. The probability of shock at each second-stage option drifted over time (drift rate 0.2, bounded 0–1); 10% of accumulated shocks were delivered to the relevant recipient post-scan.
- **task_paradigm:** Two-step task
- **players:** Single agent (participant as decider), single target (anonymous stranger as receiver)
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Abstract fractal images, colored zones indicating second-stage states, shock/no-shock outcome symbols, instruction cues for recipient (self/other)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Participants showed both model-free (main effect of outcome on stay/switch, d = 0.77) and model-based (outcome x transition interaction, d = −0.53) learning - Model-free learning was prioritized for other relative to self (outcome x recipient interaction, d = −0.39, P = 0.027) - No difference in model-based learning between self and other (BF01 = 5.1, substantial evidence for null) - Winning model ω parameter was lower for other (0.45) than self (0.55), t(35) = 2.41, P = 0.02, d = 0.40 - Ventral striatum bilaterally tracked model-free prediction errors for both self and other (no difference between conditions) - Thalamus/caudate distinguished model-free prediction errors for other > self (P = 0.033 FWE-SVC) - sgACC tracked model-free influence at choice time for other (stay > switch after no pain; P = 0.028 FWE whole-brain corrected) - sgACC–dlPFC connectivity increased during switch vs. stay after no pain for other (P = 0.039 FWE whole-brain corrected) - Rejection of instrumental harm correlated with model-free learning for others (r = 0.37, P = 0.026) - Outcome sensitivity in moral judgments correlated with model-free moral behavior (r = −0.37, P = 0.029) and thalamus/caudate PE signal (r = 0.385, P = 0.027)
- **effect_size:** - Model-free behavior (main effect of outcome): d = 0.77, CI [0.17, 0.42] - Model-based behavior (outcome x transition): d = −0.53, CI [−0.23, −0.05] - Model-free x recipient interaction: d = −0.39, CI [−0.12, −0.008] - ω self vs. other: d = 0.40 (self ω = 0.55, other ω = 0.45), 95% CI [0.06, 0.74] - Perseverance ρ self vs. other: d = 0.40, 95% CI [0.06, 0.74] - Thalamus PE for other: d = 0.39, 95% CI [0.04, 0.74]; PE for self: d = −0.50, 95% CI [−0.85, −0.14] - sgACC-model-free behavior correlation: r = 0.36, P = 0.039, 95% CI [0.02, 0.62] - Instrumental harm rejection x model-free: r = 0.37, P = 0.026, 95% CI [0.05, 0.62] - dlPFC-sgACC connectivity x instrumental harm endorsement: r = 0.43, P = 0.012, 95% CI [0.11, 0.68] - Outcome sensitivity x model-free behavior: r = −0.37, P = 0.029, 95% CI [−0.04, −0.62] - Outcome sensitivity x thalamus PE: r = 0.385, P = 0.027, 95% CI [0.05, 0.64] - Outcome sensitivity x sgACC: r = −0.374, P = 0.035, 95% CI [−0.04, −0.64]
- **learning_from:** Self; own action outcomes (pain/no-pain feedback from two-stage task). Source: self.
- **learning_about:** Self (pain avoidance for self) and other (pain avoidance for anonymous stranger). Target: self / other.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** pain_threat

## Algorithmic level
- **winning_model:** Hybrid MB/MF with 6 parameters: separate αPain, αNoPain, single β, single ρ, λ=1 (fixed), separate ωSelf and ωOther. When fitted separately per condition: 5-parameter model (αPain, αNoPain, β, ρ, ω) with λ=1. When fitted jointly across conditions: 6-parameter model with shared αPain, αNoPain, β, ρ but separate ωSelf, ωOther.
- **model_family:** MB/MF hybrid
- **model_class:** PE learning
- **all_models_tested:** Fitted separately for self and other: - M1 (7-param): αStage1, αStage2, βStage1, βStage2, ρ, λ, ω — BICint = 19400 (self), 15800 (other) - M2 (6-param): αStage1, αStage2, βStage1, βStage2, ρ, λ=1, ω — BICint = 19000 (self) - M3 (5-param): α, β, ρ, λ, ω — BICint = 14300 (self) - M4 (4-param): α, β, ρ, λ=1, ω — BICint = 13600 (self) - M5 (5-param, winning): αPain, αNoPain, β, ρ, λ=1, ω — XP = 0.9999 (self), 0.9588 (other)  Fitted jointly across self/other: - M5 (5-param): shared ω — BICint = 22175 - M6 (6-param, winning): separate ωSelf, ωOther — BICint = 22151 - M7 (7-param): separate ρSelf, ρOther, ωSelf, ωOther — BICint = 22225
- **model_mb_mf:** MB/MF hybrid
- **model_params:** - αPain: learning rate for pain outcomes; mean = 0.35 (joint fit) - αNoPain: learning rate for no-pain outcomes; mean = 0.35 (joint fit) - β: inverse temperature (softmax); mean = 3.81 (joint fit M6) - ρ: perseverance parameter; mean = 0.63 (joint fit M6) - ωSelf [S]: model-free/model-based weighting for self; mean = 0.55 (higher = more model-based) - ωOther [S]: model-free/model-based weighting for other; mean = 0.45 (lower = more model-free) - λ: eligibility trace; fixed at 1
- **social_param:** ωOther — model-free/model-based weighting parameter specific to learning for the other person. Lower ω indicates more model-free (less model-based) learning. ωOther = 0.45 was significantly lower than ωSelf = 0.55 (P = 0.02, d = 0.40), indicating prioritization of model-free learning when avoiding harm to others.
- **social_param_name:** ωSelf
- **social_param_value:** 0.55
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BICint (integrated BIC), exceedance probability (XP) via SPM's spm_BMS
- **how_model_fit:** individual-level-fit (hierarchical Bayesian / MAP estimation with expectation-maximization)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) / PPI
- **contrast:** - GLM1: Model-free prediction error at outcome (VS, bilateral; main effect) - GLM1: Other PE > Self PE (thalamus/caudate) - GLM2: Stay vs. switch after no pain for other (sgACC) - GLM3: Model-free (outcome) regressor at choice for other (sgACC, confirmatory) - GLM4 (PPI): sgACC seed, switch vs. stay after no pain for other → dlPFC connectivity - GLM5 (PPI control): sgACC seed, switch vs. stay after no pain for self (null) - Inverse value difference at first-stage choice (dACC/pre-SMA, bilateral inferior parietal, middle frontal gyrus) - State prediction error at second-stage (dorsal ACC)
- **key_regions:** Model-free prediction errors in bilateral ventral striatum for both self and other; thalamus/caudate distinguished other > self prediction errors; sgACC tracked model-free influence at choice specifically for other; dlPFC connected more strongly with sgACC during switching after no-pain for other; dorsal ACC tracked state prediction errors; TPJ showed inverse model-free pattern for other.
- **key_regions_abbrev:** VS, caudate, striatum, dlPFC, ACC, sgACC, TPJ, AI, thalamus
- **coordinates_peak:** Ventral striatum (PE, self + other): 10, 12, −4 (R); −16, 6, −10 (L) Thalamus (other PE > self PE): 16, −18, 0 (R) Thalamus/caudate (pain ROI): 12, −2, 4 (R) Thalamus/caudate (meta-analysis ROI): 10, −4, 4 (R) sgACC (stay > switch after no pain, other): −2, 36, 6 (L) sgACC (GLM3, model-free for other): 0, 36, 6 dlPFC (PPI with sgACC, switch > stay, no pain, other): −46, 38, 26 (L) Dorsal ACC (state PE): −6, 10, 52 (L) TPJ (switch > stay after no pain, other): 54, −38, 34 (R)
- **analysis_type:** both (whole-brain with small-volume correction for a priori ROIs)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 41 recruited; N = 36 for behavioral analyses (16 female, 20 male, age 18–36); N = 34 for parametric fMRI analyses (16 female, 18 male); N = 33 for stay/switch fMRI analysis
- **population_category:** healthy adults
- **population_age_range:** 18–36
- **ecological_validity:** Laboratory task using abstract fractals and electric shocks rather than naturalistic social harm; anonymous stranger as partner (no social information available); no real-time shock delivery during scanning (10% delivered post-scan); controlled for reputation and reciprocity motivations by design. Limited ecological validity but well-controlled for isolating the computational mechanisms of interest.
- **eligibility_flag:** 
- **concerns:** The two-step task variant used here did not incentivize model-based over model-free strategy (by design), which limits conclusions about whether the effect would generalize to tasks where model-based learning is adaptive. The authors acknowledge that apparently model-free behavior could reflect use of a different (non-standard) model rather than being truly model-free. The self/other comparison is within-subject but across blocks (not interleaved trial-by-trial), so block-level effects cannot be fully ruled out. Individual difference correlations with moral judgment scales are exploratory and from a modest sample (N ~ 34).
- **limitations_reported:** The study specifically designed the decider to never meet or have information about the receiver, which controls for reputation and reciprocity but does not examine how social knowledge of others influences moral learning; people might become more model-based for familiar others; the task variant used matched success rates for model-based and model-free strategies, meaning a purely model-based learner could learn over time that the model-based strategy is not worth the effort and come to masquerade as model-free, though this was not observed at the group level; the two-step task assesses relative balance of MB/MF but a hybrid strategy is the most common behavior; future studies should investigate whether findings generalize across different learning settings that impose different costs and benefits on model-based and model-free learning; individual difference analyses are exploratory and should be tested in larger samples.
- **limitations_categorized:** limited ecological validity; task simplicity (abstract stimuli, no real social interaction); limited generalizability (anonymous stranger only); potential confound of effort differences; exploratory individual difference analyses with modest sample size; hybrid MB/MF task design constraints
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
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_comparison (tables S1-S4): MEDIUM — supplement tables were extracted from .txt with formatting issues; exact BICint values for some models read from partially garbled table text - analysis_type: HIGH — explicitly stated as whole-brain FWE-corrected with SVC for a priori ROIs - learning_mode: HIGH — clearly described in text - all coordinates: HIGH — explicitly reported in main text and supplement - wc_guidelines rule 8 (validate winning model): MEDIUM — no formal posterior predictive check but extensive control analyses performed
- **cannot_find:** Nothing missing; all key fields were extractable from the main text and supplement.
- **other_notes:** This is a strong example of computational modeling applied to moral/harm avoidance learning using the classic two-step task adapted for social contexts. The study is by Lockwood, Klein-Flügge, Abdurahman, & Crockett (2020) in PNAS. Data and code are openly available. The paper provides a clear dissociation between model-free and model-based moral learning with both behavioral and neural evidence. The supplement contains full model equations, parameter recovery results, and extensive control analyses.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_perseveration
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_MB_MF_hybrid
- tax_rr_model_family = MB_MF_hybrid
- tax_rr_param_MB_MF_balance
- tax_rr_primary_topic = moral_harm
- tax_rr_topic_moral_harm
- tax_topic_moral_harm
