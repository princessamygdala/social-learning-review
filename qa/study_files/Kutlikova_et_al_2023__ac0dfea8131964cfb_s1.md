# Kutlikova et al. (2023)

- **study_id:** `ac0dfea8131964cfb_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Kutlikova, H. H., Zhang, L., Eisenegger, C., van Honk, J., & Lamm, C. (2023). Testosterone eliminates strategic prosocial behavior through impacting choice consistency in healthy males. *Neuropsychopharmacology*, *48*, 1541–1550. https://doi.org/10.1038/s41386-023-01570-y
- **citation_short:** Kutlikova et al. (2023)
- **doi:** 10.1038/s41386-023-01570-y
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Pharmacology
- **affiliations_raw:** etherthesteroidhormonetestosteroneplaysa testosterone was found to increase dopamine levels in the rat; DepartmentofCognition,Emotion,andMethodsinPsychology,UniversityofVienna,Vienna,Austria; CentreforHumanBrainHealth,SchoolofPsychology,UniversityofBirmingham,Birmingham,UK; DepartmentofPsychiatryandMentalHealth,UniversityofCapeTown,CapeTown,SouthAfrica; ether,ourstudyprovidesnovelevidenceoftestosterone’seffectsonimplicit; DepartmentofExperimentalPsychology,HelmholtzInstitute,Utrecht; mity anddeceptive reputation strategies; UniversityofBirmingham,Birmingham,UK; emails: hana.kutlikova@univie.ac
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning / audience effect on prosocial reinforcement learning; role of testosterone in strategic prosociality
- **study_focus_short:** Prosocial learning / audience effect on prosocial reinforcement learning
- **learning_mode_description:** - Learning mode: Learning from reward feedback about which abstract symbol yields higher reward, performed for self or for a charitable other, under private or observed conditions   - Learning from:     - Source type (non-social): self       - Participant's own choices and their outcomes     - Source content (non-social): outcome       - Binary reward feedback (points or no points)   - Learning about:     - Target type (non-social): world       - Which abstract symbol has higher reward probability     - Target content (non-social): stimulus       - Stimulus-reward contingencies (75% vs. 25% reward probability symbols)  Note: The social component is the audience manipulation (observed vs. private) and the prosocial recipient (self vs. NGO), but the learning itself is non-social reward learning. The "social" aspect is the context modulating reward learning rather than learning about a social entity. **Confidence: MEDIUM** — the task is a standard RL task with a social framing (audience effect, prosocial recipient), but the learning target is stimulus-reward associations, not social agents per se.
- **task_description:** Participants performed a probabilistic reinforcement learning task choosing between two abstract symbols (75% vs. 25% reward probability) across 6 blocks (3 for self, 3 for NGO), each of 16 trials. The task was performed either in private or while being observed by two female observers introduced as NGO representatives.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), with between-subjects manipulation of observation (2 female observers present vs. private) and drug treatment (testosterone vs. placebo). N=190 across 4 groups.
- **n_players:** network (5+)
- **partner_type:** unclear
- **stimuli:** Abstract symbols (pairs), binary feedback (points or no points), red frame indicating observation condition, "YOU" or "NGO" labels indicating recipient
- **method:** pharmacological / behavioural
- **method_full:** Behavioural (pharmacological: testosterone vs. placebo, double-blind, between-subjects)
- **main_result:** - Three-way interaction of drug treatment x visibility x recipient on correct choices (OR = 0.94, CI = [0.89, 1.00], p = 0.043) - Placebo group showed audience effect: more prosocial choices when observed vs. private (recipient x visibility: OR = 1.43, CI = [1.01, 2.02], p = 0.042) - Testosterone eliminated the audience effect (recipient x visibility in testosterone group: OR = 0.87, CI = [0.62, 1.22], p = 0.418) - When observed, testosterone reduced correct prosocial choices vs. placebo (OR = 0.69, CI = [0.50, 0.94], p = 0.019) - Choice consistency (inverse temperature tau) showed three-way interaction (B = 0.98, CI = [0.97, 0.98], p < 0.001) and predicted prosociality (B = 3.82, CI = [2.64, 5.01], p < 0.001) - Trait dominance moderated testosterone's effect on correct prosocial choices (4-way interaction: OR = 1.04, CI = [1.01, 1.09], p = 0.026)
- **effect_size:** - 3-way interaction on correct choice: OR = 0.94 - Audience effect in placebo: OR = 1.43 - Testosterone effect on prosocial choice when observed: OR = 0.69 - Choice consistency 3-way interaction: B = 0.98 - Choice consistency predicting prosociality: B = 3.82 - 4-way interaction with trait dominance: OR = 1.04
- **learning_from:** Self; own reward outcomes (binary feedback on chosen abstract symbol)
- **learning_about:** World; stimulus-reward contingency (which symbol is more rewarding), performed for self or for charitable other (NGO)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** RLDDM-nonlinear with dual learning rates (DLR): $\alpha_{pos}$, $\alpha_{neg}$, $\beta$ (inverse temperature/choice consistency), $v_{max}$, $v_{scaling}$, threshold $a$, non-decision time $T$; 14 parameters per between-subject condition (7 for self, 7 for other)
- **model_family:** Drift-diffusion
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "RW DDM (single LR, DDM only)", "family": "DDM", "n_params": 8, "metric": "LOOIC"},   {"name": "RW RLDDM (single LR, linear RLDDM)", "family": "RLDDM", "n_params": 10, "metric": "LOOIC"},   {"name": "RW RLDDM-nonlinear (single LR, nonlinear RLDDM)", "family": "RLDDM-nonlinear", "n_params": 12, "metric": "LOOIC"},   {"name": "DLR DDM (dual LR, DDM only)", "family": "DDM", "n_params": 10, "metric": "LOOIC"},   {"name": "DLR RLDDM (dual LR, linear RLDDM)", "family": "RLDDM", "n_params": 12, "metric": "LOOIC"},   {"name": "DLR RLDDM-nonlinear (dual LR, nonlinear RLDDM)", "family": "RLDDM-nonlinear", "n_params": 14, "metric": "LOOIC (winning)"} ]
- **model_mb_mf:** MF
- **model_params:** - $\alpha_{pos}$ (0 < $\alpha_{pos}$ < 1): Learning rate for positive prediction errors - $\alpha_{neg}$ (0 < $\alpha_{neg}$ < 1): Learning rate for negative prediction errors - $\beta$ (inverse temperature, $\beta$ > 0): Choice consistency — how consistently choices follow learned values [S — key social parameter, as testosterone x audience interaction acts through this parameter] - $v_{max}$ ($v_{max}$ > 0): Maximum drift rate in non-linear sigmoid function - $v_{scaling}$ ($v_{scaling}$ > 0): Drift scaling mapping value difference into drift rate - $a$ ($a$ > 0): Decision threshold — amount of evidence needed for decision - $T$ (0 < $T$ < min(RT)): Non-decision time (sensory delay/motor initiation) - Initial bias $z$ fixed at 0.5  Note: All 7 free parameters are estimated separately for "self" and "other" conditions within each between-subject group, yielding 14 parameters per group. Mean fitted values not reported in main text or supplement (only group-level posterior means shown in figures). **Confidence: MEDIUM** for exact fitted values.
- **social_param:** $\beta$ (inverse temperature / choice consistency parameter, also called $\tau$ in main text): Captures the degree to which learned values translate into consistent choice behavior. This is the parameter through which testosterone's effect on audience-dependent prosociality operates — testosterone reduced the consistency of prosocial choices when observed.
- **social_param_name:** $\beta$
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** LOOIC (Leave-One-Out Information Criterion) + Bayesian Model Averaging (BMA) with Bayesian bootstrap weights
- **how_model_fit:** Individual-level fit via hierarchical Bayesian analysis (HBA) using Stan/HMC with 4 MCMC chains, 1000 warmup + 1000 sampling iterations each
- **data_type_fit_to:** Choice behavior and response times (simultaneously)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=190 (from original N=192, 2 excluded for non-compliance); healthy adult males aged 18–40 (M=24.89, SD=4.08); 4 groups: Placebo-Private (n=47), Placebo-Observed (n=45), Testosterone-Private (n=53), Testosterone-Observed (n=45)
- **population_category:** healthy adults
- **population_age_range:** 18–40
- **ecological_validity:** Lab-based probabilistic RL task with abstract symbols; prosociality measured indirectly through task performance for an NGO rather than direct sharing decisions; observation manipulation was relatively naturalistic (real observers present in room with live screen monitoring and red frame cue); limited to Western male student sample; between-subject design reduces demand effects but limits within-individual comparisons
- **eligibility_flag:** The learning in this task is reward learning about stimulus-reward contingencies (non-social learning target). The social component is the audience manipulation and prosocial framing (self vs. NGO recipient), but participants are not learning about a social agent. FLAG: borderline — learning is temporal and computational, but target of learning is non-social (world/stimulus-reward associations). The social context modulates learning but the learning itself may not qualify as "learning in a social context" in the strict sense of learning about social entities. **Confidence: MEDIUM**
- **concerns:** - Between-subjects design for drug and visibility means individual differences could confound group comparisons despite randomization - 16 trials per block is relatively few for stable RL parameter estimation (mitigated by HBA) - Contamination of 34 baseline saliva samples with above-normal testosterone levels (retained for behavioral analyses) - Only male participants; only female observers — generalizability limited - Self-reported trait dominance used for median split (exploratory) - Value orientation analyses were post-hoc and exploratory - Mean fitted parameter values not explicitly reported in text or tables (only shown in figures)
- **limitations_reported:** Due to sex differences in testosterone metabolism and unknown pharmacokinetics following topical administration in women, the study included only male participants — generalization to females requires further investigation; observers were exclusively female — future research needed to test whether testosterone's influence on audience effect is sensitive to gender, number, and salience of observers; cultural differences may affect results (contrasting findings in Eastern vs. Western samples); value orientation analyses were exploratory and post-hoc, requiring independent confirmation
- **limitations_categorized:** Limited generalizability (male-only sample); limited generalizability (female observers only); cultural specificity; exploratory analyses require replication
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
- **ctx_audience:** yes
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `learning_mode`: MEDIUM — the task involves social context (audience, prosocial recipient) but the learning target is non-social stimulus-reward associations - `eligibility_flag`: MEDIUM — borderline social learning; the social component is contextual/motivational rather than the target of learning - `model_params` (fitted values): MEDIUM — exact mean posterior values not reported in tabular form, only shown in figures - `social_param`: MEDIUM — $\beta$/tau is not inherently social but is the parameter through which the social (audience) effect operates
- **cannot_find:** - Exact mean fitted parameter values for winning model (shown in figures only, not in tables) - Preregistration status
- **other_notes:** - This paper uses a psychopharmacogenetic approach combining testosterone administration with computational modeling (RLDDM) - The RLDDM framework jointly models choice and RT, providing more granularity than RL or DDM alone - Key finding: testosterone acts on choice consistency (inverse temperature), not on learning rates, suggesting the hormone affects how learned values are expressed in behavior rather than the learning process itself - Data and code available at https://osf.io/qr4ve/ - Christoph Eisenegger is listed as deceased - The paper uses the term "tau" in the main text and "$\beta$" (inverse temperature) in the supplement for the same choice consistency parameter
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pharma_testosterone
- pop_healthy_adults
- rr_pharma_testosterone
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_MF
- tax_model_drift_diffusion
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = F_affective_moral
- tax_rr_domain_E_self_in_social_context
- tax_rr_domain_F_affective_moral
- tax_rr_model_drift_diffusion
- tax_rr_model_family = drift_diffusion
- tax_rr_param_learning_rate
- tax_rr_param_temperature
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = social_approval_reward
- tax_rr_topic_prosocial_altruism
- tax_rr_topic_social_approval_reward
- tax_social_nonsocial_comparison
- tax_topic_prosocial_altruism
- tax_topic_social_approval_reward
