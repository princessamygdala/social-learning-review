# Decker et al. (2015)

- **study_id:** `a0a10385d71888bda_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Decker, J. H., Lourenco, F. S., Doll, B. B., & Hartley, C. A. (2015). Experiential reward learning outweighs instruction prior to adulthood. *Cognitive, Affective, & Behavioral Neuroscience, 15*(2), 310–320. https://doi.org/10.3758/s13415-014-0332-5
- **citation_short:** Decker et al. (2015)
- **doi:** 10.3758/s13415-014-0332-5
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Psychology
- **affiliations_raw:** Institute for Developmental Psychobiology, Weill Cornell Medical College, 1300 York; ether the efficacy of learning from instruction versus experience changes across; mitting information through instruction is particularly evident in the; Center for Neural Science, New York University, New York, NY, USA; lable in PMC 2015 June 01; ether the; emails: cah2031@med.cornell.edu
- **code_url:** 

## Computational level
- **study_focus:** Learning from advice / instructed learning vs. experiential reward learning across development
- **study_focus_short:** Learning from advice / instructed learning vs. experiential reward learning
- **learning_mode_description:** - Learning mode: Learning from experiential reward feedback and explicit instruction about stimulus value, examining how instruction biases experiential value learning across development   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (positive/negative feedback on chosen stimulus)     - Source type (non-social): world (on-screen text instruction — no social source)       - Source content (non-social): action/policy (explicit recommendation about which stimulus to choose)   - Learning about:     - Target type (non-social): world       - Target content (non-social): stimulus (probabilistic reward value of stimuli/mouseholes)
- **task_description:** Participants completed a probabilistic selection task in which they chose between pairs of colored "mouseholes" across a learning phase (with feedback) and a test phase (without feedback). One stimulus in one pair was falsely recommended as likely rewarding via on-screen text instruction (no social source), allowing measurement of how instruction biased experiential value learning.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), no interactive partner; three age groups: children (N=30, ages 6–12), adolescents (N=31, ages 13–17), adults (N=26, ages 18–34)
- **n_players:** network (5+)
- **partner_type:** none
- **stimuli:** Colored mouseholes (abstract visual stimuli), binary cognitive feedback (happy mouse with cheese / sad mouse)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Adults showed strong instruction-consistent confirmation bias in test-phase choices; children and adolescents did not (instruction bias score: adults vs. children t = 2.24, d not reported; adults vs. adolescents t = 2.29)   - Instruction bias increased linearly with age (r = .246)   - Adults' choices were best fit by instruction-bias RL model; children's and adolescents' choices were best fit by standard RL model (AIC comparison)   - Age group differences in learning rate: children had higher α than adolescents and adults (Kruskal–Wallis H = 12.87 for standard model)   - Age group differences in inverse temperature: β increased with age (H = 16.26 for standard model)   - Adults' bias parameter (αI) significantly higher than children's (W = 156.5) and adolescents' (W = 237)
- **effect_size:** - Instruction bias (adults, DF pair): t(25) = 5.98, mean = 81.4% - Instruction bias linear correlation with age: r = .246 - Gender effect in adults: instruction bias difference = 0.298 - Standard RL learning rate age effect: H = 12.87 - Bias parameter age effect: H = 14.25 - Note: Cohen's d values referenced from prior work (d = 0.9–1.3) but not computed for present study's main effects
- **learning_from:** World; experiential reward feedback (positive/negative) on chosen stimuli, plus non-social on-screen text instruction recommending one stimulus
- **learning_about:** World; probabilistic reward value of stimuli (mouseholes)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Standard RL for children/adolescents (1 α, 1 β); Instruction-bias RL for adults (1 α, 1 αI, 1 β). Standard: Q(t+1) = Q(t) + α * δ(t), where δ(t) = r(t) − Q(t). Bias model: adds αI that multiplies positive PEs and divides negative PEs for instructed stimulus.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Standard RL", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AIC"}, {"name": "Instruction-bias RL", "family": "Rescorla-Wagner (with instruction bias)", "n_params": 3, "metric": "AIC"}]
- **model_mb_mf:** MF
- **model_params:** - α (learning rate): determines weight of prediction errors on value updating. Children median: 0.34 (standard), 0.37 (bias); Adolescents median: 0.11 (standard), 0.10 (bias); Adults median: 0.13 (standard), 0.10 (bias) - β (inverse temperature): determines choice determinism. Children median: 2.24 (standard), 2.42 (bias); Adolescents median: 3.53 (standard), 3.75 (bias); Adults median: 5.82 (standard), 7.29 (bias) - αI (instruction bias) [S]: amplifies instruction-consistent PEs and diminishes instruction-inconsistent PEs. Children median: 1.10; Adolescents median: 1.11; Adults median: 2.50
- **social_param:** αI (instruction bias parameter) — modulates weighting of prediction errors for the instructed stimulus; amplifies positive PEs (multiplied by αI) and diminishes negative PEs (divided by αI) when choosing the instructed option. Note: the instruction in this study was non-social (on-screen text with no social source), so the "social" nature of this parameter is debatable.
- **social_param_name:** αI
- **social_param_value:** 1.10
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (median AIC per age group)
- **how_model_fit:** individual-level-fit (maximum a posteriori estimation per participant using MATLAB Optimization Toolbox)
- **data_type_fit_to:** choice behavior (test-phase choices)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A — behavioural study only
- **key_regions:** N/A — behavioural study only. Authors discuss prefrontal cortex and striatum as hypothesized neural substrates but no neuroimaging data were collected.
- **coordinates_peak:** N/A — no neuroimaging
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 87 (30 children [18F, 12M; ages 6–12, M = 9.5], 31 adolescents [15F, 16M; ages 13–17, M = 14.8], 26 adults [17F, 9M; ages 18–34, M = 23.0])
- **population_category:** mixed
- **population_age_range:** 6–12
- **ecological_validity:** Low — task uses abstract stimuli (colored mouseholes) and cognitive (non-monetary) feedback in a lab setting; instruction is non-social (on-screen text) which limits generalizability to real-world social advice scenarios. Authors acknowledge that the instruction lacked a social source and that real-world advice comes from peers or authority figures.
- **eligibility_flag:** The instruction source is explicitly non-social (on-screen text, "not directly associated with the experimenter, or with any specific individual"). The learning is about probabilistic reward values of abstract stimuli, not about a social target. This paper examines how instruction (a potential social learning channel) influences experiential learning, but the instruction itself is not social in this implementation. FLAG: borderline social context — instruction is a non-social proxy for advice/social learning; no actual social agent or social target.
- **concerns:** - The instruction is explicitly described as non-social (on-screen text with no social source), which is a significant limitation for inclusion in a social learning review - No neuroimaging data despite discussion of neural mechanisms - No parameter recovery or model recovery analyses reported - No simulation studies reported - Effect sizes (Cohen's d) not reported for the main developmental comparisons; only t-statistics and log-odds provided - Model fitting used MAP estimation with weakly informative priors but no posterior predictive checks reported - Cross-sectional design limits causal developmental claims
- **limitations_reported:** An important consideration not addressed in this study is whether the social source of instruction might modulate its influence"; "the instruction provided to participants was simply presented on the screen, lacking any specific social origin"; "real-world advice often comes from peers or authority figures, which may yield different effects on behavior than a printed message does"; "the influence of instruction has been shown to depend on the perceived expertise of the advisor"; present study focused solely on behavior (no neuroimaging)
- **limitations_categorized:** limited ecological validity; non-social instruction source; no neuroimaging data; cross-sectional design; task simplicity; limited generalizability
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `eligibility_flag`: LOW confidence — the instruction is explicitly non-social; borderline inclusion for social learning review - `learning_mode`: MEDIUM confidence — categorized instruction as non-social since authors explicitly state no social source, but instruction is a social learning mechanism in general - `effect_size`: MEDIUM confidence — many effect sizes reported as t-statistics and log-odds rather than standardized effect sizes (Cohen's d, r², etc.) - `social_param`: MEDIUM confidence — αI is labeled as "social" parameter per schema conventions, but the instruction in this study is non-social
- **cannot_find:** - Exact AIC values per participant (only median AIC per age group reported in Table 1, which was not fully extractable from the text conversion) - Standardized effect sizes (Cohen's d) for main developmental comparisons - Supplement: no supplement found for this paper
- **other_notes:** - This is a behavioral-only developmental study examining how instruction biases experiential reinforcement learning across childhood, adolescence, and adulthood - The instruction bias RL model was originally developed by Doll et al. (2009) — this paper applies it developmentally - The key finding is that the confirmation bias induced by instruction is absent in children and adolescents, only emerging in adults, which the authors attribute to protracted prefrontal-striatal maturation - The paper's relevance to social learning is indirect: while instruction/advice is typically a social learning channel, this study deliberately used a non-social instruction source (on-screen text) - No supplement was available
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_children
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_children
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = general
- spec_locus = source
- tax_domain_A_influence_transmission
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_param_social_weight
- tax_param_valence_asymmetry
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_bonus
- tax_rr_primary_topic = advice_taking
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_advice_taking
- tax_rr_topic_social_info_use
- tax_topic_advice_taking
- tax_topic_social_info_use
