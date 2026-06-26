# Pisauro et al. (2022)

- **study_id:** `a935c9d6fc7644f65_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Pisauro, M. A., Fouragnan, E. F., Arabadzhiyska, D. H., Apps, M. A. J., & Philiastides, M. G. (2022). Neural implementation of computational mechanisms underlying the continuous trade-off between cooperation and competition. *Nature Communications*, *13*, 6873. https://doi.org/10.1038/s41467-022-34509-w
- **citation_short:** Pisauro et al. (2022)
- **doi:** 10.1038/s41467-022-34509-w
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** lability of resources and their dis- multipletrialsinthreeblockswithpayoffmatricescreatingdifferent; CentreforHumanBrainHealth,SchoolofPsychology,UniversityofBirmingham,; SchoolofPsychologyandNeuroscience,UniversityofGlasgow,Glasgow,UK; DepartmentofExperimentalPsychology,UniversityofOxford,Oxford,UK; etheirdegreeofcooperativenessovertimeincooperative; FacultyofHealth,UniversityofPlymouth,Plymouth,UK; ethebestpositionedplayerwinsarewardwhilethe; CenterandSchoolofPsychology,; emails: m.a.pisauro@bham.ac.uk
- **code_url:** https://osf.io/sydea

## Computational level
- **study_focus:** Cooperation learning; continuous trade-off between cooperation and competition; how social context, social biases, and inferences about others' intentions modulate cooperativeness over time.
- **study_focus_short:** Cooperation learning
- **learning_mode_description:** - Learning mode: Learning from a co-player's spatial positioning decisions about their degree of cooperativeness, to update one's own cooperative/competitive behaviour over trials   - Learning from:     - Source type (social): other (co-player)     - Source content (social): action/policy (spatial positioning indicating cooperativeness)   - Learning about:     - Target type (social): other (co-player)     - Target content (social): state (mental state; cooperative/competitive intention)
- **task_description:** Pairs of participants played the "Space Dilemma," a continuous spatial foraging game where each player chose a position in a linear territory to predict a random target location; the player closest to the target won a reward distributed according to three social contexts (cooperative: equal split; intermediate: winner-takes-all; competitive: winner gains double, loser loses). Over 60 trials per context, participants had to infer their co-player's competitive intentions and adjust their own cooperativeness accordingly.
- **task_paradigm:** Joint action / coordination
- **players:** Multi-agent (dyad), symmetric; one participant in fMRI scanner, one in adjacent room.
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Linear spatial territory (bar moving across screen), target position (randomly sampled from uniform distribution), reward feedback, co-player position reveal.
- **method:** fMRI / behavioural
- **method_full:** fMRI (+ behavioural session)
- **main_result:** - Social context significantly modulated average cooperativeness of players (β = −0.12, P < 0.001, linear mixed model) - Social context significantly reduced distance between players (β = −0.25, P < 0.001, linear mixed model) - Tit-for-tat reciprocation: larger co-player position changes led to larger reciprocal changes (β = 0.03, P < 0.001) - Winning Bayesian model B6 predicted observed positions (Pearson's r = 0.91, P = 1 × 10⁻⁶) - Strong negative correlation between TitxTat and Social Bias parameters (r = −0.62, β = −3.79, P < 0.05) - Precision parameter correlated with behavioural variance (β = 6.64, P = 1 × 10⁻⁶, r = 0.73) - Unsigned social PE in posterior rTPJ (Z = 4.40, MNI: 52, −58, 30); signed social PE in anterior rTPJ (Z = −3.67, MNI: 50, −38, 32) - Context-modulated self-cooperation encoding in pDMPFC (Z = −4.09, MNI: −8, 16, 52) - Context-modulated signed PE in ACCg (Z = −3.13, MNI: 0, 34, 20) and PaCg (Z = −3.36, MNI: 2, 50, 12) - Striatum response to winning modulated by social context (t = 3.61, p = 0.0006 for STR)
- **effect_size:** r = 0.91 (model-behaviour correlation); r = −0.62 (TitxTat vs Social Bias); r = 0.73 (precision model-behaviour); β = −0.12 (context on cooperativeness); β = 0.03 (tit-for-tat); β = 6.64 (precision); Z-stats for brain activations as above.
- **learning_from:** Other (co-player); observed spatial position indicating cooperativeness/competitiveness.
- **learning_about:** Other (co-player); cooperative/competitive intention and strategy.  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Bayesian learner B6: choice(t) ~ N(TitXTatFactor × coplayer_exp_pos(t) + SocialBias, 1/Precision), where TitXTatFactor = TitXTat / (1 + q_risk × social_risk) and social_risk = 2α − 1. Four free parameters: Precision, SocialBias, TitXTat, q_risk.
- **model_family:** Bayesian
- **model_class:** PE learning / Belief updating
- **all_models_tested:** | Model | Family | n_params | Metric (BIC) | |-------|--------|----------|-------------| | S1 | Simple reactive (reciprocate last position) | 1 | 9484 | | S2 | Simple reactive (reciprocate change + bias) | 2 | 12647 | | S3 | Simple reactive (3 context biases) | 4 | 12683 | | S4 | Simple reactive (TitxTat scaled) | 3 | 7295 | | B1 | Bayesian (reciprocate expected) | 1 | 7184 | | B2 | Bayesian (+ SocialBias) | 2 | 6463 | | B3 | Bayesian (+ TitXTat) | 3 | 5845 | | B4 | Bayesian (+ TargetBias) | 4 | 6169 | | B5 | Bayesian (+ context-modulated TitXTat + TargetBias) | 5 | 6606 | | B6 | Bayesian (context-modulated TitXTat, no target) | 4 | 5553 | | B7 | Bayesian (+ betrayal expectation, added to risk) | 5 | 5995 | | B8 | Bayesian (+ betrayal expectation, added to choice) | 5 | 5933 | | R1 | Reward (shift on win/lose) | 3 | 7841 | | R2 | Reward (shift by direction) | 3 | 8181 | | R3 | Reward (+ TitxTat + bias) | 5 | 7709 | | R4 | Reward (+ TitxTat + bias + direction) | 5 | 7749 | | R5 | Reward (R1 with actual previous choice) | 3 | 6213 | | R6 | Reward (R2 with actual previous choice) | 3 | 6241 |
- **model_mb_mf:** Bayesian (not RL; Bayesian belief updating framework)
- **model_params:** - Precision: intrinsic sensory-motor response variability (range 0–10000) - SocialBias [S]: individual bias towards cooperation or competition (range −1000 to 1000) - TitXTat [S]: context-independent degree of reciprocation of co-player's expected cooperation - q_risk [S]: sensitivity to social risk induced by context (modulates TitXTat by social context)  Mean fitted values: Not explicitly reported in text; significant variability across participants shown in Supplementary Fig. 3c.
- **social_param:** SocialBias [S] — individual's inherent preference towards cooperating or competing; TitXTat [S] — degree of reciprocation of co-player's expected cooperativeness; q_risk [S] — sensitivity to social risk modulating TitXTat by context.
- **social_param_name:** SocialBias
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (Bayesian Information Criterion) and Log Likelihood (LL)
- **how_model_fit:** individual-level-fit (fmincon in MATLAB; each participant fitted individually across all three social contexts)
- **data_type_fit_to:** choice behavior (spatial positioning)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors from Bayesian model: KLD magnitude, KLD sign, expected co-player position, player cooperation level, reward, win/lose)
- **contrast:** - Unsigned social PE (|KLD|) at opponent response reveal → prTPJ (whole-brain) - Signed social PE (KLD sign) at opponent response reveal → arTPJ (whole-brain) - Self cooperation level × context contrast (coop vs comp) at player response → pDMPFC, SFG, Insula, Precuneous - Signed social PE × context contrast (coop vs comp) at opponent reveal → ACCg, PaCg - Win trials at target appearance → bilateral striatum (context modulated) - Reward available at target → ACC, sgACC, MCC, PCC, vmPFC - Baseline activity (boxcar) coop vs comp → dACC (more active during cooperation)
- **key_regions:** Unsigned social PE in posterior rTPJ; signed social PE in anterior rTPJ predicting future behaviour change; context-modulated self-cooperation encoding in posterior DMPFC/cingulate cortex; context-modulated signed PE in ACCg and paracingulate gyrus (PaCg); reward-related activity in bilateral striatum modulated by social context; rostro-caudal self-other gradient in ACC for cooperation encoding.
- **key_regions_abbrev:** striatum, mPFC, dmPFC, ACC, TPJ
- **coordinates_peak:** Posterior rTPJ (unsigned PE): 52, −58, 30 Anterior rTPJ (signed PE): 50, −38, 32 pDMPFC (self coop × context): −8, 16, 52 ACCg (signed PE × context): 0, 34, 20 (reported as 4, 32, 20 in supplement table) PaCg (signed PE × context): 2, 50, 12 SFG (self coop × context): 28, 6, 56 Insula R (self coop × context): 30, 26, 0 Precuneous (self coop × context): −6, −56, 56 Bilateral Striatum/Putamen (win): L: −14, 8, −12; R: 16, 10, −12 IFG (unsigned PE): 50, 16, 14 MFG (unsigned PE): 44, 16, 40 Bilateral Insula (unsigned PE): ±34, 22, −4 MTG (unsigned PE): 56, −30, −10 / 60, 4, −24 ACC (reward): 0, 36, 16 sgACC (reward): −4, 34, −10 MCC (reward): −4, −10, 34 PCC (reward): −4, −32, 34 vmPFC (reward): −2, 26, −26 dACC (baseline coop > comp): −4, 22, 28 (from Supplement GLM2)
- **analysis_type:** whole-brain (cluster-corrected, |Z| > 3.1, FWE P < 0.05 at cluster level); supplemented by ROI analyses on identified clusters.  ---  ## QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 54 participants in fMRI session (27 same-sex pairs); 2 pairs excluded (1 excessive head motion, 1 scanner technical problem); final N = 50 (25 pairs; 7 male pairs, 18 female pairs); all right-handed. Additional N = 81 participated in behavioural session. Ages not explicitly stated.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Novel continuous spatial game (Space Dilemma) offers more ecologically valid parameterization of cooperation-competition than binary choice tasks; however, still a lab-based task with abstract stimuli (bar positions, not real-world social interaction). Real dyadic interaction (no deception) increases validity. Foraging framing adds naturalistic element.
- **eligibility_flag:** 
- **concerns:** - Order of conditions was kept constant (cooperative → competitive → intermediate) for all pairs, introducing potential order effects that are not counterbalanced. - Ages of participants not reported. - Mean fitted parameter values not reported in main text. - Model comparison used summed BIC across all participants rather than random-effects model comparison (e.g., BMS with exceedance probability). - No model recovery analysis (confusion matrix between models); only parameter recovery was performed.
- **limitations_reported:** Authors acknowledge: the paradigm studies a specific instantiation of cooperation-competition trade-off; future experiments could vary reward probability, task difficulty, number of players; the study uses a finite number of trials making it susceptible to end-game effects; the continuous measure is a particular parametrization that may not capture all aspects of cooperation.
- **limitations_categorized:** task simplicity; limited generalizability; potential order effects; no model recovery; limited sample diversity information.  ---  ## WC CHECKLIST  1. Design a good experiment: **Yes** — Novel Space Dilemma with three social contexts designed to parametrically vary cooperation-competition trade-off.2. Design good models: **Yes** — 18 models across 3 classes (Simple, Bayesian, Reward) tested.3. Simulate, simulate, simulate: **Partial** — Parameter recovery analysis involved simulating data from fitted parameters, but no extensive simulation study prior to fitting described.4. Fit the parameters: **Yes** — MLE fitting using fmincon in MATLAB, individual-level.5. Check parameter recovery: **Yes** — Parameter recovery analysis with 6 simulated datasets × 10 repetitions; most parameters recovered reliably (Supplementary Fig. 6c).6. Check model recovery: **No** — No confusion matrix or model recovery analysis reported.7. Fit real data and compare models: **Yes** — BIC comparison across all 18 models on real data.8. Validate the winning model: **Yes** — Model predictions correlated with observed behaviour (r = 0.91); precision parameter correlated with behavioural variance (r = 0.73); regression analysis confirming Bayesian expectation predicts better than last position.9. Analyze the winning model: **Yes** — Latent parameters (SocialBias, TitXTat, Precision, q_risk) analyzed for inter-individual correlations and brain-behaviour correlations.10. Report results transparently: **Yes** — Data and code available on OSF (https://osf.io/sydea).
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.5
- **wc_total:** 8.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `sample_size`: ages not reported (MEDIUM confidence on age range) - `model_params`: mean fitted values not explicitly tabulated in text (MEDIUM — distributions shown in Supplementary Fig. 3c but values not listed) - `wc_guidelines` Rule 3: scored Partial — parameter recovery was done but no pre-fitting simulation study described (MEDIUM)
- **cannot_find:** - Exact mean fitted parameter values (shown only as distributions in supplementary figure) - Participant age range - Whether the study was preregistered
- **other_notes:** - The paper develops a novel economic game (Space Dilemma) that generalizes the Prisoner's Dilemma to a continuous measure. - The Bayesian model uses KL divergence as the social prediction error signal, which is then used as a parametric regressor in fMRI. - The supplement contains extensive coordinate tables (Supplementary Tables 2 and 3) with full whole-brain results. - A rostro-caudal self-other gradient in ACC for cooperation encoding is described in supplementary results. - Data and code deposited at OSF.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target+context
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_mod_multiplayer_live
- tax_model_bayesian
- tax_param_PE_signal
- tax_param_precision
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = cooperation
- tax_rr_secondary_topic = competition
- tax_rr_topic_competition
- tax_rr_topic_cooperation
- tax_topic_competition
- tax_topic_cooperation
