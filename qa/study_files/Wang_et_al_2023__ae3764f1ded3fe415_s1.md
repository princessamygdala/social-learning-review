# Wang et al. (2023)

- **study_id:** `ae3764f1ded3fe415_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Wang, Z., Nan, T., Goerlich, K. S., Li, Y., Aleman, A., Luo, Y., & Xu, P. (2023). Neurocomputational mechanisms underlying fear-biased adaptation learning in changing environments. *PLoS Biology*, *21*(5), e3001724. https://doi.org/10.1371/journal.pbio.3001724
- **citation_short:** Wang et al. (2023)
- **doi:** 10.1371/journal.pbio.3001724
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** labilityStatement:Thedatathatsupport identifiedthatthedrivingeffectwaslocatedintheTPJandwasassociatedwithdACCacti-; University,UNITEDKINGDOM experiment(n=37)withanovelcue-biasedadaptationlearningtask,duringwhichwe; UniversityMedicalCenterGroningen,Groningen,theNetherlands,5 ShenzhenKeyLaboratoryofAffective; CNRS—Centred’EconomiedelaSorbonne,Panthe´on-SorbonneUniversity,France,3 Schoolof; DepartmentofBiomedicalSciencesofCells&Systems,SectionCognitiveNeuroscience,; University,Shenzhen,China,6 TheStateKeyLabofCognitiveandLearning,Facultyof; CenterofAppliedPsychology,ChengduMedicalCollege,Chengdu,
- **code_url:** https://osf.io/avhne/.HDI

## Computational level
- **study_focus:** Fear-biased adaptation learning; how fear (induced by fearful facial expressions) suppresses flexible adaptation to environmental volatility during reward learning
- **study_focus_short:** Fear-biased adaptation learning
- **learning_mode_description:** - Learning mode: Learning from one's own reward outcomes about the reward structure of a volatile environment, with fear cues biasing adaptation to volatility   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (reward/no reward)   - Learning about:     - Target type (non-social): world (reward contingency / environmental volatility)     - Target content (non-social): state (reward probability structure)
- **task_description:** Participants completed a cue-biased adaptation learning task in which a fearful or neutral facial expression cue preceded each trial of a probabilistic reward reversal task; participants chose between two options (Gabor patches) to maximize reward, while environmental volatility (frequent vs. infrequent reversals of reward contingencies) and emotional valence of cues were simultaneously manipulated in a 2x2 within-subject design.
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), no social partner (facial expressions are cues, not interactive agents)
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Fearful and neutral facial expressions (from TFEID), horizontal and vertical Gabor patches, binary reward feedback (+1 green / +0 red)
- **method:** fMRI / behavioural
- **method_full:** fMRI (Experiment 2) + behavioural (Experiment 1)
- **main_result:** - Significant interaction between cue and environmental volatility on learning rates (Exp1: partial η² = 0.24; Exp2: partial η² = 0.16) - Higher learning rate for frequent vs. infrequent reversals under neutral cues (Exp1: partial η² = 0.18; Exp2: partial η² = 0.16), but this pattern absent under fearful cues - Behavioral bias correlated with neural bias in VS (r = 0.578), HI (r = 0.606), and PPC (r = 0.586) - dACC and VS encoded subjective volatility modulated by fear (dACC interaction: partial η² = 0.29; VS interaction: partial η² = 0.30) - dACC-TPJ functional connectivity modulated by fear × volatility (partial η² = 0.42) - DCM: driving effect from TPJ on fear-biased volatility adaptation (partial η² = 0.19) - Alexithymia (BVAQ) correlated with fear-biased learning rate (r = 0.351)
- **effect_size:** - Cue × volatility interaction on learning rate: Exp1 partial η² = 0.24; Exp2 partial η² = 0.16 - VS neural-behavioral correlation: r = 0.578 - HI neural-behavioral correlation: r = 0.606 - PPC neural-behavioral correlation: r = 0.586 - dACC cue × volatility interaction (subjective volatility): partial η² = 0.29 - VS cue × volatility interaction (subjective volatility): partial η² = 0.30 - dACC-TPJ connectivity interaction: partial η² = 0.42 - TPJ driving effect interaction: partial η² = 0.19 - BVAQ-learning rate bias correlation: r = 0.351
- **learning_from:** Self; reward outcome on chosen option (non-social)
- **learning_about:** World; reward contingency structure and environmental volatility (non-social)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** face_expression

## Algorithmic level
- **winning_model:** RW with 4 separate learning rates (1 α per condition: fear×freq, fear×infreq, neut×freq, neut×infreq) + 4 β parameters (M1; 8 params total)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "M1", "family": "Rescorla-Wagner (4 conditions, separate α and β)", "n_params": 8, "metric": "LOOIC/WAIC"} - {"name": "M2", "family": "RW (volatility only, no cue effect)", "n_params": 4, "metric": "LOOIC/WAIC"} - {"name": "M3", "family": "RW (4 α, shared β)", "n_params": 5, "metric": "LOOIC/WAIC"} - {"name": "M4", "family": "RW (two-arm bandit, only chosen updated)", "n_params": 8, "metric": "LOOIC/WAIC"} - {"name": "M5", "family": "RW + attentional lapse (ε)", "n_params": 9, "metric": "LOOIC/WAIC"} - {"name": "M6", "family": "RW + shared forgetting (φ)", "n_params": 9, "metric": "LOOIC/WAIC"} - {"name": "M7", "family": "RW + volatility-dependent forgetting", "n_params": 10, "metric": "LOOIC/WAIC"} - {"name": "M8", "family": "RW + cue-dependent forgetting", "n_params": 10, "metric": "LOOIC/WAIC"} - {"name": "M9", "family": "Hybrid RW + Pearce-Hall (shared ω)", "n_params": 7, "metric": "LOOIC/WAIC"} - {"name": "M10", "family": "Hybrid RW + Pearce-Hall (cue-dependent ω)", "n_params": 8, "metric": "LOOIC/WAIC"} - {"name": "M11", "family": "Hybrid RW + Pearce-Hall (cue-dependent κ)", "n_params": 8, "metric": "LOOIC/WAIC"} - {"name": "M12", "family": "RW (linear relationship among 4 α)", "n_params": 11, "metric": "LOOIC/WAIC"}
- **model_mb_mf:** MF
- **model_params:** - α_fear_freq: learning rate for fearful cue, frequent reversals (0 < α < 1) - α_fear_infreq: learning rate for fearful cue, infrequent reversals (0 < α < 1) - α_neut_freq: learning rate for neutral cue, frequent reversals (0 < α < 1) - α_neut_infreq: learning rate for neutral cue, infrequent reversals (0 < α < 1) - β_fear_freq: inverse temperature for fearful cue, frequent reversals (0 < β < 10) - β_fear_infreq: inverse temperature for fearful cue, infrequent reversals (0 < β < 10) - β_neut_freq: inverse temperature for neutral cue, frequent reversals (0 < β < 10) - β_neut_infreq: inverse temperature for neutral cue, infrequent reversals (0 < β < 10)  Note: Mean fitted parameter values are shown in violin plots (Fig 2C, 2D) but exact numeric values are not reported in text.  Additionally, a Bayesian Learner model was used for model-based fMRI (GLM2) to derive trial-by-trial subjective volatility, with parameters: V (reward probability), SV (subjective volatility), k (distrust parameter).
- **social_param:** None — no explicitly social parameter in the winning model
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** LOOIC, WAIC
- **how_model_fit:** individual-level-fit (hierarchical Bayesian estimation via MCMC with hBayesDM package)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + gPPI + DCM
- **contrast:** - GLM1: [(fear&freq – fear&infreq) – (neut&freq – neut&infreq)] at outcome, regressed against learning rate bias - GLM2: [(fear&freq – fear&infreq) – (neut&freq – neut&infreq)] parametric modulation of subjective volatility at outcome - gPPI: dACC seed, subjective volatility × condition interaction - DCM: 6 models testing effective connectivity between dACC and TPJ
- **key_regions:** Fear-biased adaptation to volatility encoded in VS and HI (learning rate bias); dACC and VS encoded subjective volatility modulation by fear; dACC-TPJ functional connectivity modulated by fear × volatility; DCM showed TPJ driving effect on fear-biased adaptation.
- **key_regions_abbrev:** dACC, ACC, TPJ
- **coordinates_peak:** - PPC (whole-brain): -50, -60, 50 - VS (ROI, learning rate): 4, 8, -4 (Note: reported as [4 8 –4] based on text "[48–4]" which likely represents "4, 8, -4" given text extraction artifacts) - HI (ROI, learning rate): 28, -16, -22 - dACC (ROI, subjective volatility): -2, 32, 32 (Note: reported as [–2 32 32] based on text "[–23232]") - VS (ROI, subjective volatility): 10, 16, -8 - TPJ (whole-brain, gPPI from dACC): -64, -52, 36
- **analysis_type:** both (ROI with SVC for a priori regions + exploratory whole-brain)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** Exp1: N = 21 (11 female, age 20.81 ± 1.94, behavioural); Exp2: N = 40 behavioural / N = 37 fMRI (16-18 female, age ~21.6, after exclusions from 43). Additional supplementary experiments: ExpS1 N = 27 (punishment context), ExpS2 N = 39 (happy face control).
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low — uses abstract Gabor patches in a probabilistic reversal task with static facial expression cues; emotional cues are brief face presentations rather than genuine social interactions; laboratory fMRI setting.
- **eligibility_flag:** The "social" element is limited to fearful/neutral facial expression cues that serve as emotional primes, not as social interaction partners. Learning is about non-social reward contingencies (Gabor patch → reward probability). The facial expressions do not convey social information about another agent's intentions, states, or actions — they serve purely as emotional cues. FLAG: Borderline social context — facial expressions are social stimuli but learning itself is non-social (reward contingency learning). The social component is limited to the emotional cue (fear face) rather than learning from or about social agents.
- **concerns:** - The facial expressions serve as emotional cues rather than social learning signals — the learning itself is about abstract reward contingencies, not social information - Exact mean fitted parameter values for the winning model (M1) are not reported numerically in the text (only shown in violin plots) - Coordinate extraction is uncertain due to text formatting artifacts (spaces removed between numbers in the .txt conversion) - The Bayesian Learner model was used for deriving neural regressors but was not the winning behavioral model — two different model frameworks were used for different purposes - Small sample sizes across experiments (N = 21, N = 37-40)
- **limitations_reported:** Fear may induce suboptimal learning in both frequent and infrequent environments rather than specifically disrupting adaptation to volatility; only classical Bayesian Learner model used without testing variants such as hierarchical Gaussian filter; fear induction relied on subjective self-report without real-time physiological measures (e.g., electrocardiography, eye-tracking)
- **limitations_categorized:** Ambiguity of manipulation effect; limited model space; reliance on subjective measures; no physiological validation of emotional manipulation
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 10
- **wc_total:** 10.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - coordinates_peak (MEDIUM): Text extraction artifacts make exact coordinate parsing uncertain — numbers run together without spaces in the .txt file. Coordinates were inferred from context (e.g., "[48–4]" interpreted as [4, 8, -4] for VS; "[–23232]" interpreted as [-2, 32, 32] for dACC). These should be verified against the original PDF. - model_params (MEDIUM): Exact mean fitted values for α and β parameters not reported numerically in text; only shown in violin plots - learning_mode (MEDIUM): Learning mode is non-social reward learning with social emotional cues — classification of social vs. non-social depends on how strictly "social context" is defined - social_param (HIGH): No social parameter — confirmed from model equations
- **cannot_find:** - Exact mean fitted parameter values for M1 (shown only in figures) - Supplement files (.docx) were not available as .txt — supplementary details on parameter recovery, model recovery, and additional analyses could not be verified directly
- **other_notes:** - This paper uses two complementary modeling frameworks: Rescorla-Wagner (winning model for behavior) and Bayesian Learner (for deriving trial-by-trial subjective volatility for model-based fMRI). The Bayesian Learner is not the winning behavioral model but is used as a computational tool for neural analysis. - Supplement not accessible as .txt file — supplementary materials are referenced as .docx and .tif files. The main text provides sufficient detail for extraction but supplement tables (e.g., S3 Table for model recovery, S7 Table for BOLD responses) could not be directly verified. - The paper includes 4 experiments total: Exp1 (behavioral, reward), Exp2 (fMRI, reward), ExpS1 (behavioral, punishment), ExpS2 (behavioral, happy face control). The main extraction focuses on Exp1 + Exp2 as the primary studies. - Data shared on OSF (https://osf.io/avhne/)
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = partly
- spec_depth = general
- spec_locus = source+target+context
- spec_neural = dedicated
- tax_domain_F_affective_moral
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = threat_fear
- tax_rr_secondary_topic = volatility
- tax_rr_topic_threat_fear
- tax_rr_topic_volatility
- tax_topic_threat_fear
- tax_topic_volatility
