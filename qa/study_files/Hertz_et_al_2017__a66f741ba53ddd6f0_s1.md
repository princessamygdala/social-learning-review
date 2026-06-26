# Hertz et al. (2017)

- **study_id:** `a66f741ba53ddd6f0_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Hertz, U., Palminteri, S., Brunetti, S., Olesen, C., Frith, C. D., & Bahrami, B. (2017). Neural computations underpinning the strategic management of influence in advice giving. *Nature Communications*, 8, 2191. https://doi.org/10.1038/s41467-017-02314-5
- **citation_short:** Hertz et al. (2017)
- **doi:** 10.1038/s41467-017-02314-5
- **publication_type:** peer-reviewed journal
- **year:** 2017.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** InstituteofPhilosophy,SchoolofAdvancedStudy,UniversityofLondon,SenateHouse,MaletStreet,LondonWC1E7HU,UK; UCLInstituteofCognitiveNeuroscience,UniversityCollegeLondon,17QueenSquare,LondonWC1N3ARUK; LaboratoredeNeurosciencesCognitives,InstitutNationaldelaSantéetdelaRecherche; mitted by objective evidence (positive during a strategic advice-giving task; ethatislower andtheaccuracyofheradvicerelativetotherivaladviser; CentreforNeuroimaging,UniversityCollegeLondon,12QueenSquare,; Department,UniversityofHaifa,Haifa3498838,Israel; ether people would give overconfident; emails: uhertz@is.haifa.ac.il
- **code_url:** 

## Computational level
- **study_focus:** Social influence learning; strategic advice giving; learning about one's influence over a client and one's relative merit compared to a rival adviser
- **study_focus_short:** Social influence learning
- **learning_mode_description:** - Learning mode: Learning from client's adviser selection and from outcome-based social comparison to strategically modulate advice confidence   - Learning from:     - Source type (social): other (client)       - Source content (social): action/policy (client's choice of which adviser to follow)     - Source type (social): other (rival adviser)       - Source content (social): outcome (rival's advice prognostic value compared to own)   - Learning about:     - Target type (social): self (own influence status relative to client)       - Target content (social): state (mental state; social rank/influence level)     - Target type (social): other (rival adviser)       - Target content (social): state (mental state; relative merit)
- **task_description:** In a three-sided advice-giving game, two advisers (participant and a rival) competed to influence a client by modulating their confidence ratings about which lottery urn contained a hidden reward. The client chose which adviser to follow each trial based on advisers' prior accuracy and confidence; advisers saw probabilistic evidence and declared confidence on a 10-level scale, and outcomes were revealed to all.
- **task_paradigm:** Advice-taking task
- **players:** Single agent (participant as adviser), multi-target (1 virtual client; 1 virtual rival adviser). In experiment 4: multi-agent (triad of 3 human participants: 2 advisers + 1 client).
- **n_players:** multi-target (3+)
- **partner_type:** human (live)
- **stimuli:** Grid of black and white squares (probability evidence), 10-level confidence scale, binary outcome (coin in black or white urn)
- **method:** fMRI / online / behavioural
- **method_full:** fMRI (scanner cohort, N=32), behavioural (online N=58, lab N=29, fully interactive N=32 advisers)
- **main_result:** - Main Results:   - Advisers showed systematic overconfidence (d = 1.56)   - Advice deviance was greater when ignored vs. chosen by client (d = 0.28)   - Interaction model best fit: advice deviance highest when positive relative merit but ignored by client (interaction effect: F(1,358) = 17.95, η²_partial = 0.14)   - Main effect of relative merit on advice deviance (F(1,358) = 14.4, η²_partial = 0.14)   - Main effect of selection by client on advice deviance (F(1,358) = 8.1, η²_partial = 0.04)   - FNE score correlated with selection parameter (R = 0.25, R² = 0.06)   - rTPJ selection-by-client effect correlated with FNE score (R = 0.65, R² = 0.39)   - Fully interactive replication: significant interaction (F(1,96) = 5.05, η²_partial = 0.14), significant relative merit effect (F(1,96) = 4.43, η²_partial = 0.125)
- **effect_size:** See main_result above (d = 1.56 for overconfidence; d = 0.28 for selection effect; η²_partial = 0.14 for interaction; R² = 0.39 for rTPJ-FNE correlation)
- **learning_from:** Other (client's selection of adviser; rival adviser's advice outcomes). Source: social other (client) and social other (rival).
- **learning_about:** Self (own influence/social rank relative to client); other (relative merit vs. rival adviser). Target: social self and social other.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Interaction model: AdviceDeviance(t) = Bias + β_Selection × Selection(t) + β_Merit × sign(RelativeMerit(t)) + β_Interaction × Selection(t) × sign(RelativeMerit(t)); with RelativeMerit updated via PE learning with rate γ
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Bias Model", "family": "linear regression", "n_params": 1, "metric": "DIC"},   {"name": "Client Model", "family": "linear regression + bias", "n_params": 2, "metric": "DIC"},   {"name": "Merit Model", "family": "RW + linear regression", "n_params": 3, "metric": "DIC"},   {"name": "Mixed Model", "family": "RW + linear regression", "n_params": 4, "metric": "DIC"},   {"name": "Interaction Model", "family": "RW + linear regression", "n_params": 5, "metric": "DIC"},   {"name": "Amplitude Model", "family": "RW + linear regression (sign + magnitude)", "n_params": 5, "metric": "DIC"} ]
- **model_mb_mf:** MF (model-free prediction error learning for relative merit)
- **model_params:** - Bias (intercept / trait overconfidence): mean ± SEM = 0.67 ± 0.05 [S] - γ (learning rate for relative merit updating) [S] - β_Selection (weight of client selection on advice deviance): mean ± SEM = −0.07 ± 0.02 [S] - β_Merit (weight of sign of relative merit on advice deviance) [S] - β_Interaction (weight of selection × relative merit interaction on advice deviance) [S]  Note: All parameters are social as they govern social influence strategy. Mean fitted values for γ, β_Merit, and β_Interaction are reported in Supplementary Table 1, which is not accessible.
- **social_param:** β_Selection [S] — governs how client's selection (ignored vs. chosen) modulates advice confidence deviance (negative = competitive strategy; positive = defensive strategy). γ [S] — learning rate for accumulating relative merit from social comparison with rival adviser.
- **social_param_name:** Bias
- **social_param_value:** 0.67
- **social_param_sd:** 0.05
- **social_param_range:** 
- **model_comparison_metric:** DIC (Deviance Information Criterion; Markov Chain Monte Carlo fitting with marginal parameter integration)
- **how_model_fit:** individual-level-fit (MCMC parameter estimation for each participant individually, using marginal distribution integration)
- **data_type_fit_to:** choice behavior (advice confidence deviance from probabilistic evidence)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + univariate GLM (2×2 factorial: selection by client × relative merit)
- **contrast:** - Selection by client: Ignored > Chosen at evidence stage (rTPJ) - Client selection switch (parametric modulator) at evidence stage (VS) - Relative merit PE (parametric modulator) at outcome stage (mPFC) - Relative merit PE (parametric modulator) at appraisal stage (VS)
- **key_regions:** Selection by client (ignored > chosen) in rTPJ; client selection switches in VS; relative merit PE in mPFC at outcome and VS at appraisal. Individual differences in rTPJ selection response correlated with FNE score.
- **key_regions_abbrev:** mPFC, TPJ, AI
- **coordinates_peak:** rTPJ (selection by client, ignored > chosen): 51, −58, 35 mPFC (relative merit PE, outcome stage): −9, 56, 5 Left VS ROI (NeuroSynth-defined): −12, 8, −8 Right VS ROI (NeuroSynth-defined): 10, 6, −8 Right VS (NeuroSynth, time course extraction): 18, 8, −10  Note: VS activation for client selection switch and relative merit PE reported at whole-brain level (P < 0.001, FWE cluster-corrected P < 0.05) but exact peak coordinates for VS whole-brain results are referenced to Supplementary Tables 3 and 5 (supplement not accessible). The VS ROI coordinates above are NeuroSynth-defined spheres used for time-course analysis.
- **analysis_type:** both (whole-brain parametric modulation analysis + ROI time-course analysis using NeuroSynth-defined VS spheres and mPFC peak)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 151 total across 4 experiments. Online: N = 58 (31 male, 27 female; ages 33.7 ± 9.6 / 36 ± 8.5); Lab: N = 29 (13 male, 16 female; ages ~26); fMRI: N = 32 (18 male, 14 female; ages ~24); Fully interactive: N = 48 (32 advisers from 16 triads; 24 male, 33 female; ages ~21–25). FNE questionnaire: N = 69 subsample.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Strong for a lab paradigm: includes a fully interactive human-triad replication (Experiment 4) demonstrating generalizability beyond virtual agents. However, the primary fMRI experiment used computer-controlled client and rival, limiting real social interaction during scanning. The task captures competitive social dynamics but remains abstracted from real-world persuasion contexts.
- **eligibility_flag:** 
- **concerns:** (1) The relative merit variable is latent and constructed by the experimenters' model — its neural correlates depend on model assumptions. (2) The fMRI sample (N=32) is modest for individual-differences claims (FNE correlation based on N=28 fMRI subsample). (3) Client and rival adviser were algorithmic in the fMRI experiment, not human. (4) Supplement not accessible — full parameter estimates, model comparison statistics (Supplementary Table 1), and some whole-brain peak coordinates (Supplementary Tables 2–5) could not be verified.
- **limitations_reported:** Authors note the importance of individual differences in social self-perception on strategic social behaviour; they acknowledge the task involves virtual confederates for the main experiments and that the fully interactive experiment was needed to confirm ecological validity; they note that the FNE questionnaire was administered 6 months post-experiment to avoid interference.
- **limitations_categorized:** limited ecological validity (virtual confederates in main experiments); sample size (modest fMRI N); limited generalizability (laboratory paradigm); correlational individual-differences claims
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params (γ, β_Merit, β_Interaction mean values): MEDIUM confidence — reported in Supplementary Table 1 which is not accessible; only β_Selection and Bias means given in main text - coordinates_peak (VS whole-brain activations): MEDIUM confidence — exact peak coordinates for VS whole-brain results referenced to Supplementary Tables 3 and 5, not accessible - wc_guidelines Rule 8: MEDIUM confidence — simulation-based validation described but not a standard posterior predictive check
- **cannot_find:** - Full parameter estimates for γ, β_Merit, β_Interaction (in Supplementary Table 1) - Exact peak coordinates for VS activations from whole-brain analysis (in Supplementary Tables 3, 5) - Full DIC values for model comparison (in Supplementary Table 1 and Figure 2) - Supplement not accessible (no supplement file found in papers folder)
- **other_notes:** This paper uses a novel three-agent asymmetric social interaction paradigm (two advisers competing for a client). The computational model combines a Rescorla-Wagner-style prediction error mechanism for tracking relative merit with a linear policy model for advice deviance. The paper includes four separate experimental cohorts (online, lab, fMRI, fully interactive) providing strong replication. The "Interaction model" winning model captures how selection by client and relative merit jointly determine strategic overconfidence. Data and statistical maps are openly available.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_domain_D_group_structure_identity
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = D_group_structure_identity
- tax_rr_domain_B_inference_modelling_others
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_hierarchy
- tax_rr_secondary_topic = strategic_reasoning
- tax_rr_topic_social_hierarchy
- tax_rr_topic_strategic_reasoning
- tax_topic_social_hierarchy
- tax_topic_strategic_reasoning
