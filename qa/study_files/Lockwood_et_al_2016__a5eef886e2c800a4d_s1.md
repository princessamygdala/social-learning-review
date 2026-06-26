# Lockwood et al. (2016)

- **study_id:** `a5eef886e2c800a4d_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lockwood, P. L., Apps, M. A. J., Valton, V., Viding, E., & Roiser, J. P. (2016). Neurocomputational mechanisms of prosocial learning and links to empathy. *Proceedings of the National Academy of Sciences*, *113*(35), 9763–9768. https://doi.org/10.1073/pnas.1603198113
- **citation_short:** Lockwood et al. (2016)
- **doi:** 10.1073/pnas.1603198113
- **publication_type:** peer-reviewed journal
- **year:** 2016.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DivisionofPsychologyandLanguageSciences,UniversityCollegeLondon,LondonWC1H6BT,UnitedKingdom;bDepartmentofExperimentalPsychology,; UniversityofOxford,OxfordOX13UD,UnitedKingdom;andcInstituteofCognitiveNeuroscience,UniversityCollegeLondon,LondonWC1N3AZ,; UniversityofZurich,Zurich,Switzerland,andacceptedbyEditorialBoardMemberSusanT
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning — how people learn to obtain rewards for others vs. self, and links to trait empathy.
- **study_focus_short:** Prosocial learning
- **learning_mode_description:** - Learning mode: Learning from one's own choice outcomes (rewards/no rewards) about stimulus-reward contingencies to benefit self, another person, or no one.   - Learning from:     - Source type (non-social): self       - Agent makes the choice and observes outcome     - Source content (non-social): outcome       - Binary reward feedback (100 points / 0 points)   - Learning about:     - Target type (social): other (confederate) [prosocial condition]; (non-social): self [self condition]; (non-social): no one [control condition]     - Target content (social): outcome       - Stimulus-reward contingencies that determine rewards delivered to another person (prosocial), self (self), or no one (control)
- **task_description:** Participants chose between two abstract symbols with different reward probabilities (75% vs. 25%) across three conditions: self (participant receives reward), prosocial (confederate receives reward), and no one (no beneficiary). They had to learn the stimulus-reward contingencies through trial and error over 144 trials (48 per condition, 3 blocks of 16 per condition).
- **task_paradigm:** Prosocial choice task
- **players:** Single agent (participant), single target (age- and gender-matched confederate believed to be a naïve participant)
- **n_players:** single agent (1)
- **partner_type:** confederate
- **stimuli:** Abstract symbols (Agathodaimon font), binary feedback (100 points / 0 points)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Participants learned to obtain rewards in all conditions but had a significantly higher learning rate for self vs. prosocial (d = 0.87, P < 0.001) and self vs. no one (d = 0.53, P = 0.01); main effect of condition on learning rate: F(2,60) = 11.47, P < 0.001 - No difference in learning rate between prosocial and no one (d = 0.25, P = 0.18) - Bayesian model comparison: winning model (separate α and β per condition) had ΔBIC > 600 over alternatives - Ventral striatum bilaterally coded PEs regardless of beneficiary (conjunction analysis; right: Z = 4.09, k = 91, P = 0.006 SVC-FWE; left: Z = 3.72, k = 78, P = 0.023 SVC-FWE) - sgACC uniquely coded prosocial PEs (prosocial PE > self + no one PE): Z = 3.83, k = 148, P = 0.019 SVC-FWE - DLPFC showed greater responses to self/no one PEs than prosocial PEs (left: Z = 4.47, k = 62, P = 0.006 SVC-FWE; right: Z = 4.36, k = 27, P = 0.020 SVC-FWE) - Online simulation empathy subscale correlated with prosocial–self learning rate difference (r = 0.44, P = 0.01, 95% CI = 0.18, 0.66) - Online simulation correlated with prosocial–self PE response in sgACC (r = 0.39, P = 0.03, 95% CI = 0.13, 0.60)
- **effect_size:** - Self vs. prosocial learning rate: d = 0.87 - Self vs. no one learning rate: d = 0.53 - Prosocial vs. no one learning rate: d = 0.25 (n.s.) - Self vs. prosocial choice variability: d = 0.24 (n.s.) - No one vs. self choice variability: d = 0.46 - No one vs. prosocial choice variability: d = 0.58 - Empathy (online simulation) × prosocial–self learning rate: r = 0.44 - Empathy (online simulation) × sgACC prosocial–self PE: r = 0.39
- **learning_from:** Self; own choice outcomes (reward/no reward feedback on chosen symbol)
- **learning_about:** Other (confederate) in prosocial condition; self in self condition; no one in control condition — stimulus-reward contingencies  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** RW with separate parameters per condition (α_self, α_prosocial, α_noone, β_self, β_prosocial, β_noone); 6 parameters total. Q_{t+1}(a) = Q_t(a) + α × [r_t − Q_t(a)]; choice via softmax with temperature β.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Full RL model (separate α and β per condition)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "BIC"},   {"name": "Null model (α = 0, β varies)", "family": "Null/random", "n_params": 1, "metric": "BIC"},   {"name": "Fixed-parameter RL (single α and β across conditions)", "family": "Rescorla-Wagner", "n_params": 2, "metric": "BIC"} ]
- **model_mb_mf:** MF
- **model_params:** - α_self: learning rate for self condition [bounded 0–1]; mean not reported individually per condition in text but group comparison shown in Fig 1C - α_prosocial [S]: learning rate for prosocial condition [bounded 0–1] - α_noone: learning rate for no one condition [bounded 0–1] - β_self: softmax temperature for self condition - β_prosocial [S]: softmax temperature for prosocial condition - β_noone: softmax temperature for no one condition
- **social_param:** α_prosocial — learning rate specifically for learning to benefit another person; β_prosocial — choice variability when choosing for another. The prosocial–self learning rate difference was the key social parameter, which correlated with trait empathy.
- **social_param_name:** α_prosocial
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion); ΔBIC > 10 = decisive evidence; full model had ΔBIC > 600 over alternatives
- **how_model_fit:** individual-level-fit (MAP — maximum a posteriori; two-stage procedure: first MLE per subject, then re-estimation with Gaussian priors derived from group MLE distribution)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — PE and chosen value from RL model used as parametric modulators at outcome and cue events respectively; ROI analysis with anatomically defined masks + conjunction-null analysis
- **contrast:** - Conjunction-null: self PE ∩ prosocial PE ∩ no one PE → bilateral VS - Prosocial PE > self PE + no one PE → sgACC (Z = 3.83, P = 0.019 SVC-FWE) - Self PE + no one PE > prosocial PE → bilateral DLPFC (left: Z = 4.47, P = 0.006 SVC-FWE; right: Z = 4.36, P = 0.020 SVC-FWE) - Self PE > prosocial PE + no one PE → no suprathreshold voxels - No one PE > self PE + prosocial PE → parahippocampal gyrus (uncorrected) - Prosocial PE > self PE (without no one) → sgACC (Z = 3.90) - Self PE > prosocial PE (without no one) → thalamus, DLPFC, cerebellum
- **key_regions:** Bilateral ventral striatum coded PEs across all conditions (domain-general). sgACC (BA25/s24)/basal forebrain coded prosocial PE exclusively. Bilateral DLPFC (BA9/46d) coded self/no one PE > prosocial PE. No dACC responses observed.
- **key_regions_abbrev:** VS, striatum, dlPFC, dACC, ACC, sgACC, AI
- **coordinates_peak:** Main effect PE (whole-brain FWE corrected, Table S1): - Caudate R: 10, 15, −9 (Z = 6.92, k = 694) - Putamen R: 20, 9, −11 (Z = 6.36) - Putamen L: −10, 9, −11 (Z = 6.65, k = 605) - Middle temporal gyrus L: −40, −66, 24 (Z = 6.31, k = 399) - Middle frontal gyrus L: −26, 20, 52 (Z = 5.57, k = 102) - Posterior cingulate sulcus L: −10, −42, 37 (Z = 5.56, k = 854) - Fusiform gyrus L: −20, −82, −20 (Z = 5.42, k = 74) - Amygdala L: −26, −4, −21 (Z = 5.40, k = 67)  Conjunction (self PE ∩ prosocial PE ∩ no one PE, ROI): - Ventral striatum R: 10, 15, −9 (Z = 4.09, k = 91, P = 0.006 SVC-FWE) - Ventral striatum L: −12, 10, −11 (Z = 3.72, k = 78, P = 0.023 SVC-FWE)  Self PE (ROI): - Putamen R: 18, 6, −8 (Z = 6.02, k = 226) - Caudate R: 12, 12, −6 (Z = 5.19) - Putamen L: −12, 8, −11 (Z = 5.22, k = 104)  Prosocial PE (ROI): - Caudate R: 8, 12, −11 (Z = 5.02, k = 30) - sgACC/basal forebrain L: −6, 15, −8 (Z = 4.95, k = 12)  Prosocial PE > self + no one PE: - sgACC/basal forebrain L/R: 0, 6, −15 (Z = 3.87, k = 182) - sgACC L: −3, 18, −6 (Z = 3.47) - sgACC R: 2, 12, −9 (Z = 3.22) - From main text: sgACC: −2, 4, −15 (Z = 3.83, k = 148, P = 0.019 SVC-FWE)  Self + no one PE > prosocial PE: - Middle frontal gyrus (DLPFC) L: −36, 18, 43 (Z = 4.47, k = 347) - DLPFC R: 42, 39, 36 (Z = 3.51, k = 184) - Inferior frontal gyrus L: −54, 39, −3 (Z = 4.06, k = 190) - Supramarginal gyrus L: −58, −46, 33 (Z = 3.77, k = 124) - Superior temporal gyrus L: −58, −28, −2 (Z = 3.77, k = 114) - Inferior parietal lobule L: −64, −36, 39 (Z = 3.77, k = 136)
- **analysis_type:** both (whole-brain FWE corrected for main effects; ROI with SVC-FWE for a priori regions: VS, sgACC, dACC, DLPFC)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 31 (34 recruited; 3 excluded: 2 for chance-level performance, 1 for neurological abnormality); all right-handed males, age 19–32, M = 22.7, SD = 3.0. 80% power to detect d = 0.52 at alpha = 0.05.
- **population_category:** healthy adults
- **population_age_range:** 19–32
- **ecological_validity:** Low-to-moderate. The prosocial condition involved learning for an anonymous confederate believed to be another participant, which captures some elements of prosocial motivation but in a highly constrained, abstract lab task. No real social interaction occurred; participants never saw the confederate receive outcomes. Deception was used (fixed payment regardless of performance; confederate was not a real participant). Male-only sample limits generalizability.
- **eligibility_flag:** 
- **concerns:** - Male-only sample limits generalizability to females - Deception used (confederate was not naïve; all participants received fixed payment); though debriefing confirmed no participant became suspicious - No one condition: no difference in learning rate from prosocial condition (d = 0.25, n.s.), which complicates interpretation of sgACC specificity for "prosocial" learning — the behavioral difference was driven by self > others, not prosocial > no one - 1.5T scanner (relatively low field strength for fMRI) - ROI analysis with anatomically defined masks — may miss relevant regions outside a priori hypotheses - Mean fitted parameter values for α and β not reported numerically (shown only in figures)
- **limitations_reported:** Sample composed only of males — future studies would benefit from examining prosocial learning in females; difficult to interpret null finding in anterior insula and dACC; reference frame (self-action) differs from typical empathy/vicarious processing studies; cannot dissociate heterogeneous subregions of sgACC with current resolution; genetic vs. environmental contributions to sgACC specificity unknown
- **limitations_categorized:** limited generalizability (male-only sample); limited ecological validity; task simplicity; null findings in expected regions unexplained; spatial resolution limitations; no causal evidence
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM — mean fitted values of α and β per condition not reported numerically in text, only shown in bar charts (Fig 1C, 1E) - wc_guidelines rule 3 (simulate): HIGH — no simulation described - wc_guidelines rule 5 (parameter recovery): HIGH — not reported - wc_guidelines rule 6 (model recovery): HIGH — not reported
- **cannot_find:** - Exact mean fitted values of α_self, α_prosocial, α_noone, β_self, β_prosocial, β_noone (shown in figures but not reported as numbers in text or supplement)
- **other_notes:** This is a foundational paper in prosocial learning using computational modeling. The sgACC finding has been influential. The paper uses a classic Rescorla-Wagner framework with condition-specific parameters. The empathy correlation (online simulation subscale of QCAE with prosocial–self learning rate difference) provides a mechanistic link between trait empathy and prosocial learning. The supplement confirms that the full model with separate parameters per condition was decisively favored (ΔBIC > 10) over both the null model and the fixed-parameter model. The supplement also contains extensive coordinate tables (Tables S1–S4) that have been extracted above.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = empathy_vicarious
- tax_rr_topic_empathy_vicarious
- tax_rr_topic_prosocial_altruism
- tax_topic_empathy_vicarious
- tax_topic_prosocial_altruism
