# Konovalov et al. (2021)

- **study_id:** `a950c7c6f86c80e02_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Konovalov, A., Hill, C., Daunizeau, J., & Ruff, C. C. (2021). Dissecting functional contributions of the social brain to strategic behavior. *Neuron*, *109*(20), 3323–3337. https://doi.org/10.1016/j.neuron.2021.07.025
- **citation_short:** Konovalov et al. (2021)
- **doi:** 10.1016/j.neuron.2021.07.025
- **publication_type:** peer-reviewed journal
- **year:** 2021.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** CenterforNeuroeconomics(ZNE),DepartmentofEconomics,UniversityofZurich,Zurich8006,Switzerland; etheyspecializedforbehaviorinsocialcontextsordotheyimplementcomputa-; ether activity in social-brain regions reflects specifically the; ethistypeofsituationrequiresparticulardomain-general; ethat,inanalogytohowsomevisualareasevolved; etheoriesputforwardtoanswerthisquestion; etheritinstantiatesgeneral-pur-; ethatthiseffectmightbe; emails: christian.ruff@uzh.ch, arkady.konovalov@uzh.ch
- **code_url:** https://mbb-team.github.io/VBA-toolbox/

## Computational level
- **study_focus:** Strategic social learning — investigating whether the "social brain" network responds specifically to social context or to the computational demands of dealing with a reactive environment during strategic interactions.
- **study_focus_short:** Strategic social learning
- **learning_mode_description:** - Learning mode: Learning to predict and counteract an opponent's strategy in a competitive matching pennies game   - Learning from:     - Source type (social in social condition; non-social in non-social condition): other (opponent / card deck)       - Algorithms are identical across conditions     - Source content (non-social): outcomes (win/loss feedback) and actions (opponent's choices)   - Learning about:     - Target type (social in social condition; non-social in non-social condition): other (opponent's strategy / deck's pattern)     - Target content (non-social): action/policy (opponent's choice strategy; predicting next action)
- **task_description:** Participants played a matching pennies card game (228 trials) against two computer-controlled opponents (a reactive "learner" using 0-ToM Bayesian strategy and a non-reactive "sequencer" producing probabilistic sequences), framed either as playing against human opponents (social, n=31) or against card decks (non-social, n=29). Participants had to predict the opponent's/deck's next choice, winning a point for correct matches and losing a point for mismatches.
- **task_paradigm:** Matching pennies
- **players:** Single agent (participant), single target (one opponent at a time; 2 opponent algorithms). Between-subjects context manipulation (social vs. non-social framing).
- **n_players:** single agent (1)
- **partner_type:** unclear
- **stimuli:** Abstract cards (Tree/Rock), color-coded screen frames (red/blue) indicating opponent identity, monetary outcomes (win/loss points).
- **method:** fMRI / behavioural
- **method_full:** fMRI (+ behavioral pilot study)
- **main_result:** 
- **effect_size:** 
- **learning_from:** Other's actions and outcomes; opponent's past choices and win/loss feedback.
- **learning_about:** Other's action strategy/policy; predicting next choice of opponent.  ---  ## 3. MAIN RESULTS AND EFFECT SIZES  - Social context cued better performance against the reactive (learner) opponent: interaction effect (mixed-effects logistic regression, fMRI dataset n=60: z = 2.27; behavioral dataset n=20: z = 2.57; combined: z = 3.2) - Social context increased use of second-order belief strategy (k parameter): z = 4.6 against learner - Correlation between k weight and reward rate against learner: r = 0.77 - Correlation between g weight and reward rate against sequencer: r = 0.86 - Correlation between individual performance difference and strategy parameter difference: r = 0.82 - Almost all social-brain ROIs showed stronger activation for learner vs. sequencer opponent (all p[FDR] < 0.05); social context per se did not elicit differential activation (effect sizes < 0.13 for social vs. non-social context differences) - rTPJ was the only region showing significant interaction of social context x algorithm (t[535] = -2.06) and social context x reward (t[535] = 2.94) - rTPJ: learner > sequencer (t[538] = 5.7) - dmPFC activity correlated with k (strategy use) specifically against learner in social context (t[89] = 2.7); interaction of k x context: dmPFC (t[174] = 2.25), precuneus (t[174] = 2.48) - rTPJ-nucleus accumbens connectivity increased for learner vs. sequencer during loss outcomes (beta = 0.07, t[59] = 3.55, p[FDR] = 0.007) - rTPJ-dmPFC connectivity increased during win vs. loss (beta = 0.12, t[59] = 4.44, p[FDR] = 0.0004) - MVPA decoding: algorithm type from ToM network = 63.3%; context = 61.6%. rTPJ alone: algorithm 59.1%, context 65%. - vmPFC encoded model-predicted choice value (peak MNI: -2, 56, -5; t[59] = 6.1, p[SVC] = 0.0002) - Reactivity measure encoded in rTPJ (t[59] = 3.8, p[FDR] < 0.001) - Nucleus accumbens encoded absolute value update (t[59] = 4.27, p[FDR] < 0.001) - Model fit: 71.5% (SD = 6%) balanced classification accuracy for choice model  ---  ## 4. ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Linear Volterra decomposition (logistic regression): P(a^s_t) = 1 / (1 + exp(-(b + k*a^s_{t-1} + l*a^s_{t-2} + d*a^o_{t-1} + g*a^o_{t-2})))  Abbreviated: Volterra choice model (5 params: b, k, l, d, g); fit as mixed-effects logistic regression.
- **model_family:** No formal model
- **model_class:** Other
- **all_models_tested:** - Volterra choice model (selected; 5 params; variational Bayes / mixed-effects logistic regression) - Q-learning (not selected; n_params not specified; variational Bayes via VBA toolbox) - Win-stay-lose-shift (not selected; n_params not specified; variational Bayes via VBA toolbox) - Influence learning (not selected; n_params not specified; variational Bayes via VBA toolbox) - Markov matrix-based sequence learning (not selected; n_params not specified; variational Bayes via VBA toolbox)  Details of alternative models are reported in supplementary Figure S1 (supplement not accessible).
- **model_mb_mf:** Descriptive (not RL per se; decomposes influence of past actions on current choice — captures both model-based strategic reasoning and simpler heuristics)
- **model_params:** - b: bias/intercept - k [S]: weight on own choice at t-1 (indexes second-order belief / mentalizing strategy, optimal against reactive learner) - l: weight on own choice at t-2 - d [S]: weight on opponent's choice at t-1 - g [S]: weight on opponent's choice at t-2 (indexes sequence-tracking strategy, optimal against sequencer)  Mean fitted values: Not reported as point estimates; individual posterior estimates used.
- **social_param:** k — weight on own choice at t-1, reflecting tendency to switch each trial (second-order belief / mentalizing strategy); g — weight on opponent's choice at t-2, reflecting sequence-tracking strategy. Both are social in the social condition context.
- **social_param_name:** k
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Variational Bayes (free energy / model evidence via VBA toolbox) for individual model comparison; mixed-effects logistic regression for main analyses. Balanced classification accuracy (71.5%) reported for winning model.
- **how_model_fit:** Individual-level fit (VBA toolbox, variational Bayes) for model comparison; group-level hierarchical mixed-effects logistic regression (lme4 in R) for main analyses.
- **data_type_fit_to:** Choice behavior  ---  ## 5. IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** Model-based fMRI (parametric regressors for RPE, APE, reactivity, value update) + univariate GLM + MVPA (SVM decoding) + PPI (functional connectivity)
- **contrast:** - Feedback: learner > sequencer (social brain activation) - Win > loss x social > non-social interaction (rTPJ) - Win > loss x sequencer > learner interaction (IPS) - Conjunction: learner > sequencer AND win > loss x social > non-social (TPJ cluster) - Parametric modulators at feedback: signed RPE, action PE, reactivity measure, absolute value update - PPI: rTPJ seed, win vs. loss, learner vs. sequencer, social vs. non-social + interactions - Choice value at choice stage (vmPFC validation)
- **key_regions:** Social brain network responds to opponent reactivity (learner > sequencer) rather than social context per se. rTPJ uniquely encodes context-dependent outcome processing and reactivity detection; dmPFC encodes strategy implementation and action prediction errors; precuneus shows context x outcome interaction; nucleus accumbens encodes absolute value update; vmPFC encodes model-predicted choice value; IPS responds to sequence prediction.
- **key_regions_abbrev:** NAcc, vmPFC, mPFC, dmPFC, ACC, TPJ, AI, precuneus
- **coordinates_peak:** - vmPFC (choice value): -2, 56, -5 - IPS (sequencer > learner win interaction): -42, -42, 48 - rTPJ (context x outcome conjunction): 31, 21, 50 (Note: this z-coordinate of 50 seems unusually dorsal for TPJ; this is reported as stated in paper: "t[56] = -5.1, MNI peak x = 31, y = 21, z = 50") - ROIs defined from NeuroSynth "theory of mind" meta-analysis masks: rTPJ (1519 voxels), lTPJ (1301 voxels), precuneus (1358 voxels), lTP (1741 voxels), rTP (1665 voxels), dmPFC (1961 voxels), nucleus accumbens (L: 386 voxels, R: 323 voxels) — exact coordinates for ROI centers not reported (functional masks from NeuroSynth)
- **analysis_type:** Both (whole-brain permutation-based FWE-corrected analyses + a priori ROI analyses using NeuroSynth masks)  ---  ## 6. QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 60 for fMRI (31 social, 29 non-social; from 66 recruited; 28 male, 38 female; ages 18–25); N = 20 for behavioral pilot. Exclusions: 1 negative score, 1 wrong instructions, 1 partial fMRI data loss, 2 excessive head movement.
- **population_category:** healthy adults
- **population_age_range:** 18–25
- **ecological_validity:** Laboratory competitive game (matching pennies) with deception-based social context manipulation. Limited ecological validity: binary choices, computer-generated opponents, no real face-to-face interaction. However, matching pennies is a well-established paradigm for studying strategic interactions reflecting everyday competitive scenarios.
- **eligibility_flag:** 
- **concerns:** - The rTPJ "conjunction" peak coordinate (31, 21, 50) appears unusually dorsal for TPJ — may be more consistent with dorsal frontal/premotor regions. Authors note overlap with NeuroSynth TPJ mask but this warrants caution. - Between-subjects design for social context manipulation limits statistical power for context effects (authors acknowledge this). - Winning model is a logistic regression decomposition rather than a formal learning model — it describes strategy use but does not capture trial-by-trial belief updating dynamics. - Alternative model details (Q-learning, WSLS, influence learning, Markov) are only in supplement which was not accessible. - Opponent algorithms are computer-generated; social manipulation relies on deception (confederate setup).
- **limitations_reported:** - Study addresses a general question about the social brain in just one specific experimental game setting (matching pennies) and against two specific types of algorithms; remains to be established whether findings apply to other social settings such as collaborative behavior. - Between-subjects design for social/non-social comparison limits statistical power; weak effect sizes for context differences (< 0.13) suggest even a within-subject design with 60 subjects would not yield significant context effects. - Some situations involving social brain activation (e.g., observational learning, learning others' preferences) do not necessarily involve a reactive environment — reactivity processing may be just part of a more complex computation yet to be identified.
- **limitations_categorized:** Limited generalizability (single game paradigm); limited ecological validity; between-subjects design reduces power; task simplicity (two specific algorithms only); incomplete theoretical account (reactivity may be only part of social brain function).
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `coordinates_peak`: MEDIUM confidence — only 3 peak coordinates reported in main text; ROIs defined via NeuroSynth masks without center coordinates. The rTPJ conjunction peak (31, 21, 50) appears atypically dorsal for TPJ. - `all_models_tested`: LOW confidence — alternative model details (n_params, exact formulations) only available in supplement which was not accessible. - `model_family`: MEDIUM confidence — classified as logistic regression/Volterra decomposition; this is not a standard computational model family like RL or Bayesian updating. - `winning_model` formula: HIGH confidence — Equation 1 directly reported. - `social_param`: MEDIUM confidence — k, d, g are "social" only in social condition; they reflect general strategy weights applicable in both conditions.
- **cannot_find:** - Exact n_params for alternative models (Q-learning, WSLS, influence learning, Markov) — in supplement only. - Mean fitted parameter values for k, g, l, d, b — individual posterior estimates used but group means not tabulated. - Full coordinate table for brain activations — ROIs are mask-based; only 3 peak coordinates from whole-brain analyses reported. - Supplement content (not available as a file).
- **other_notes:** - Supplement not accessible — no supplement file found in the papers folder. Model comparison details, Figure S1–S4, Table S1–S3 are referenced but unavailable. - The paper's primary contribution is dissociating rTPJ (context-dependent outcome/reactivity processing) from dmPFC (strategy implementation) rather than proposing a new computational model of learning. - The "learning" model is more of a strategy decomposition tool than a trial-by-trial learning algorithm. - Paper includes both a behavioral pilot (N=20) and fMRI study (N=60); results are from a single study design. - Data and code shared on OSF.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target+context
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = no_model
- tax_rr_model_no_model
- tax_rr_param_PE_signal
- tax_rr_param_perseveration
- tax_rr_primary_topic = strategic_reasoning
- tax_rr_topic_strategic_reasoning
- tax_social_nonsocial_comparison
- tax_topic_strategic_reasoning
