# Kang et al. (2024)

- **study_id:** `a243d5dfd1ae939fc_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Kang, P., Moisa, M., Lindström, B., Soutschek, A., Ruff, C. C., & Tobler, P. N. (2024). Causal involvement of dorsomedial prefrontal cortex in learning the predictability of observable actions. *Nature Communications*, *15*, 8305. https://doi.org/10.1038/s41467-024-52559-0
- **citation_short:** Kang et al. (2024)
- **doi:** 10.1038/s41467-024-52559-0
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** CenterforNeuroeconomics,DepartmentofEconomics,UniversityofZurich,Zurich,Switzerland; CenterZurich,ETHZurichandUniversityofZurich,Zurich,Switzerland; etherDMPFC/preSMAsupportslearningfromobservedoutcomesor; UniversityMunich,DepartmentforPsychology,Munich,Germany; ether to rely on a particular demonstrator learning; DepartmentofClinicalNeuroscience,Divisionfor; Institute,Stockholm,Sweden; emails: pyungwon.kang@gmail.com
- **code_url:** 

## Computational level
- **study_focus:** Observational learning — learning from observed actions and outcomes of a demonstrator, and specifically learning about demonstrator predictability (a proxy for reliability) to modulate action-based observational learning.
- **study_focus_short:** Observational learning
- **learning_mode_description:** - Learning mode: Learning from observed demonstrator actions about the predictability/reliability of the demonstrator to guide one's own choices   - Learning from:     - Source type (social): other (demonstrator)       - Source content (social): action/policy (observed choices of demonstrator)   - Learning about:     - Target type (social): other (demonstrator)       - Target content (social): state (mental state; reliability/predictability)     - Target type (non-social): world       - Target content (non-social): stimulus (stimulus-reward associations)
- **task_description:** Participants observed a demonstrator choosing between two fractal images in a two-armed bandit and then chose for themselves; in different conditions they saw only the demonstrator's actions (Action-Only) or both actions and outcomes (Action-Outcome), with either a superb (≥70% correct) or bad (50% correct/random) demonstrator, while their own outcomes were scrambled to force reliance on observational learning.
- **task_paradigm:** Two-armed bandit
- **players:** Single agent (participant), single target (demonstrator; pre-recorded from previous study)
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Fractal images (pairs), face photographs of demonstrators, monetary outcomes (points convertible to CHF)
- **method:** TMS
- **method_full:** TMS (continuous theta burst stimulation, cTBS)
- **main_result:** - Main Results:   - DMPFC/preSMA cTBS decreased performance (proportion choosing high-reward option) in Action-Only condition with superb demonstrator vs. vertex (b = 0.341, z = 2.536, BF₁₀ = 7.26)   - DMPFC/preSMA cTBS had no effect on Action-Outcome learning from bad demonstrator (b = 0.016, z = 0.078, BF₁₀ = 0.02)   - DMPFC/preSMA cTBS decreased prediction accuracy of superb demonstrator actions in Action-Only condition (b = 0.264, z = 2.368, BF₁₀ = 0.78)   - Best model: Predictability learning-Action model (Model 5) — DMPFC/preSMA cTBS disrupted learning about demonstrator predictability which modulates action-based learning   - Stimulation parameter τ_choice significantly > 1 (t(29) = 5.83, d = 0.68, 95% CI [0.47, 0.98])   - Correlation between TMS-induced change in predictability learning rate and performance difference (r = 0.340)   - Individual learning unaffected by DMPFC/preSMA cTBS (b = −0.015, z = −0.407, BF₁₀ = 0.03)   - No effect on imitation behavior
- **effect_size:** Cohen's d = 0.68 for τ_choice stimulation parameter; Pearson's r = 0.340 (predictability learning rate difference ~ performance difference); BF₁₀ = 7.26 (Action-Only superb demonstrator choice); BF₁₀ = 5.08 (demonstrator quality main effect)
- **learning_from:** Other (demonstrator); observed actions and outcomes of the demonstrator. Source: other.
- **learning_about:** Other (demonstrator predictability/reliability); world (stimulus-reward associations). Target: other / world.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Predictability learning-Action model (Model 5): RL framework with simulated demonstrator Q-learning (fixed α_demonstrator = 0.2, β_demonstrator = 9), outcome prediction error update (Eq. 3), action prediction error update modulated by accumulated predictability (AcP; Eq. 14), Shannon entropy-based predictability (Eq. 9-10), predictability learning rate υ, stimulation parameter τ_choice modulating predictability learning in DMPFC/preSMA condition (Eq. 12); softmax with perseverance ρ.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Model 1: Outcome learning", "family": "RL (RW)", "n_params": "α, κ, ω, β, ρ, τ", "metric": "DIC"} - {"name": "Model 2: Action learning", "family": "RL (RW)", "n_params": "α, κ, ω, β, ρ, τ", "metric": "DIC"} - {"name": "Model 3: Action-Outcome learning", "family": "RL (RW)", "n_params": "α, κ, ω, β, ρ, τ (x2)", "metric": "DIC"} - {"name": "Model 4: Predictability learning-Outcome", "family": "RL (RW) + predictability", "n_params": "α, κ, ω, β, ρ, υ, τ", "metric": "DIC"} - {"name": "Model 5: Predictability learning-Action (WINNING)", "family": "RL (RW) + predictability", "n_params": "α, κ, ω, β, ρ, υ, τ_choice", "metric": "DIC"} - {"name": "Model 6: Predictability learning-Both", "family": "RL (RW) + predictability", "n_params": "α, κ, ω, β, ρ, υ, τ", "metric": "DIC"}
- **model_mb_mf:** MF (model-free RL with predictability meta-learning component)
- **model_params:** - α_demonstrator (fixed = 0.2): demonstrator's simulated learning rate - β_demonstrator (fixed = 9): demonstrator's simulated choice temperature - α: observer's outcome-based learning rate (range 0–1) - κ: observer's action-based learning rate (range 0–1) [S] - ω: weighting parameter arbitrating outcome vs. action predictions in Action-Outcome condition (range 0–1) [S] - β: observer's softmax temperature (range 0–30) - ρ: perseverance parameter (range 0–3) - υ: predictability learning rate (range 0–1) [S] — rate of learning about demonstrator predictability - τ_choice: stimulation parameter (range 0–10) [S] — modulates predictability learning under DMPFC/preSMA cTBS
- **social_param:** - υ (predictability learning rate) [S]: rate at which the observer learns about the predictability of the demonstrator's actions (proxy for demonstrator reliability) - τ_choice [S]: captures the effect of DMPFC/preSMA downregulation on predictability learning - κ (action learning rate) [S]: learning rate for action prediction errors from observed demonstrator choices - ω (weighting parameter) [S]: arbitrates between outcome- vs. action-based observational learning signals
- **social_param_name:** - υ
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 0–1
- **model_comparison_metric:** DIC (Deviance Information Criterion)
- **how_model_fit:** individual-level-fit (hierarchical Bayesian approach with group-level priors constraining individual parameters; MCMC via JAGS/R2jags; 3 chains, 40,000 samples per chain, 10,000 burn-in, thinning every 5th)
- **data_type_fit_to:** choice behavior (choice for self in decision phase; prediction of demonstrator actions fitted separately)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (TMS study; no neuroimaging data collected during task)
- **contrast:** DMPFC/preSMA cTBS vs. vertex cTBS (within-subject); Action-Only vs. Action-Outcome × superb vs. bad demonstrator
- **key_regions:** DMPFC/preSMA (x = 6, y = 14, z = 52) — stimulation target based on Suzuki et al. (2012); causally involved in learning predictability of observed actions. Vertex served as control stimulation site.
- **key_regions_abbrev:** mPFC, dmPFC
- **coordinates_peak:** - DMPFC/preSMA (stimulation target): 6, 14, 52 (MNI, from Suzuki et al. 2012)  Note: These are stimulation coordinates taken from a prior fMRI study, not peak activation coordinates from the current study. No neuroimaging data were collected in this study.
- **analysis_type:** N/A (no neuroimaging in this study; TMS behavioral study)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** N = 30 (1 excluded from original 31; 18 females; M_age = 23.59 ± 2.45); within-subject design (each participant received both DMPFC/preSMA and vertex cTBS in separate sessions)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Laboratory-based two-armed bandit task with pre-recorded demonstrators (not live social interaction). Abstract fractal stimuli reduce ecological validity. However, the use of TMS provides causal evidence for brain-behavior relationships that correlational neuroimaging cannot. The demonstrators were described as real previous participants, adding some social believability.
- **eligibility_flag:** 
- **concerns:** - No direct neuroimaging data collected — brain conclusions rely on stimulation of a single coordinate from a prior study - Predictability learning rate υ and stimulation parameter τ are multiplied, raising potential identifiability concerns (though authors report parameter recovery and note no excessive values) - Model recovery was weaker for prediction of demonstrator actions models, though authors argue this is secondary - BF₁₀ for prediction accuracy effect in Action-Only superb condition was only 0.78, which is inconclusive - Supplement referenced extensively in text (Figure S6, S7, S8, S9, S10, Tables S1–S6) but supplement file not accessible for verification
- **limitations_reported:** Offline TMS cannot disambiguate whether DMPFC/preSMA implements performance monitoring only or also performance adjustment; the stimulated area has ambiguous anatomical labeling (DMPFC vs. preSMA vs. posterior mPFC vs. dorsal ACC/rostral cingulate zone); model recovery was weaker for prediction of demonstrator actions; precise area in dorsal and ventral MPFC distinguishing self from other may depend on individual traits; cannot determine whether DMPFC controls behavior directly or sends error information to other brain regions like LPFC
- **limitations_categorized:** TMS temporal resolution (offline); anatomical specificity of stimulation; model recovery limitations; limited generalizability (single stimulation site); task simplicity (two-armed bandit)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 9.5
- **wc_total:** 9.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - coordinates_peak: MEDIUM — these are stimulation coordinates from a prior study (Suzuki et al. 2012), not activation peaks from this study - model_params (fitted values): LOW — mean fitted parameter values referenced in Tables S3–S6 in supplement, which was not accessible; only fixed demonstrator parameters (α = 0.2, β = 9) and stimulation parameter statistics reported in main text - wc_guidelines Rule 8: MEDIUM — model simulation shown but no formal posterior predictive check with quantitative fit metrics
- **cannot_find:** - Mean fitted values for individual observer parameters (α, κ, ω, β, ρ, υ) — reported only in supplementary Tables S3–S6 (supplement not accessible) - Exact DIC values for each model — shown in Fig. 3B graphically but exact numbers not stated in text - Exact n_params count for each model — parameter names listed but exact count per model not explicitly tabulated in main text - Full model equations in clean format — Eqs. 1–14 present but OCR quality poor in text extraction
- **other_notes:** - Supplement not accessible (no _Supplements.txt file found). The paper references Figure S3, S5, S6, S7, S8, S9, S10 and Tables S1–S6 extensively. Model equations overview (Figure S6), parameter recovery (Table S1), model recovery confusion matrix (Fig. S9), and posterior distributions (Fig. S10) are all in the supplement. - The paper uses the term "DMPFC/preSMA" throughout to acknowledge ambiguity in anatomical labeling of the stimulation site at Brodmann areas 6/9 border. - This is a TMS study, not an fMRI study — there are no neural activation results per se, only behavioral effects of brain stimulation interpreted through computational models. - Data and code publicly available on OSF. - The text file had significant OCR degradation in the equations sections (particularly Eqs. 5–12), with characters scattered across multiple lines, but core content was recoverable.
- **re_extract_flag:** false (main text fully read; supplement not accessible but flagged)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_vicarious_outcome
- spec_depth = parametric
- spec_locus = source
- spec_neural = dedicated
- spec_source = social
- spec_target = partly
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_vicarious_outcome
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_param_perseveration
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = imitation_emulation
- tax_rr_secondary_topic = reputation_learning
- tax_rr_topic_imitation_emulation
- tax_rr_topic_reputation_learning
- tax_topic_imitation_emulation
- tax_topic_reputation_learning
