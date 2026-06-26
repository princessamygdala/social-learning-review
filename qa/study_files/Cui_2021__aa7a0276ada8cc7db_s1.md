# Cui (2021)

- **study_id:** `aa7a0276ada8cc7db_s1`
- **on_website:** NO — DROPPED (verify below)
- **why_not_on_website:** (no eligibility flag recorded — likely duplicate/superseded version; confirm)

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Cui, Z. (2021). Understanding social function in psychiatric illnesses through computational modeling and multiplayer games [Doctoral dissertation, Virginia Polytechnic Institute and State University]. (Paper I: Cui, Z., Zhu, L., Vilares, I., Chiu, P. H., & King-Casas, B.)
- **doi:** Not provided for dissertation. Paper I appears unpublished or in preparation at time of dissertation submission.
- **publication_type:** thesis
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Social competitive behavior in depression; disentangling effects of social reward valuation vs. interpersonal guilt on altered competitiveness.
- **study_focus_short:** Social competitive behavior in depression
- **learning_mode_description:** - Learning mode: Learning from opponent's bidding behavior during repeated social competition to update belief about opponent's strategy   - Learning from:     - Source type (social): other (opponent/computer partner)     - Source content (social): action/policy (bidding and challenge decisions)   - Learning about:     - Target type (social): other (opponent)     - Target content (social): action/policy (predicted bidding behavior conditional on context)
- **task_description:** Participants played a 30-round resource contest game with an adaptive computer partner (believed to be human). In each round, the alpha player distributed $10, then the beta player could challenge for the alpha position via a bidding contest; whoever bid more won.
- **task_paradigm:** Auction task
- **players:** Single agent (participant), dyadic (adaptive computer partner believed to be human)
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Monetary endowments, position labels (alpha/beta), bidding amounts, contest outcomes
- **method:** fMRI
- **main_result:** - Depressed participants made more high-value transfers than controls (z = 2.04, p = .04) - Group parameter for guilt significantly > 0 (95% HDI lower bound > 0), indicating higher guilt in depression - D (dominance preference) did not differ between groups (95% HDI includes 0) - Guilt positively correlated with symptom severity (r = 0.26, p = .04) - Change of guilt correlated with change of symptoms T1 to T2 (r = 0.29, p = .04) - Comparable bilateral VS response to winning in depressed vs. controls (t = 0.85, p = .40) - Higher guilt associated with greater VMPFC activation during transfer (r = 0.26, p = .01) - Higher guilt associated with greater ACC (r = 0.26, p = .006) and right AI (r = 0.29, p = .002) activation to challenge
- **effect_size:** - Guilt-symptom correlation: r = 0.26 - Longitudinal guilt-symptom change: r = 0.29 - Guilt-VMPFC: r = 0.26 - Guilt-ACC: r = 0.26 - Guilt-right AI: r = 0.29
- **learning_from:** Other (opponent); opponent's bidding actions during social contest
- **learning_about:** Other (opponent); opponent's likely bidding behavior conditional on transfer and role  ---  #### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Belief-learning + Fehr-Schmidt inequity aversion (4 params: phi [learning rate], D [dominance preference], guilt [advantageous inequity aversion], lambda [inverse temperature])
- **model_family:** Rescorla-Wagner
- **model_class:** Prediction error learning + utility maximization (social preference)
- **all_models_tested:** - {"name": "Model 1 (phi, lambda)", "family": "Belief learning", "n_params": 4, "metric": "iBIC = 13152"} - {"name": "Model 2 (phi, lambda, guilt)", "family": "Belief learning + Fehr-Schmidt", "n_params": 6, "metric": "iBIC = 12698"} - {"name": "Model 3 (phi, lambda, D)", "family": "Belief learning + dominance", "n_params": 6, "metric": "iBIC = 12309"} - {"name": "Model 4 (phi, lambda, guilt, D)", "family": "Belief learning + Fehr-Schmidt + dominance", "n_params": 8, "metric": "iBIC = 11785"}
- **model_mb_mf:** MF (belief learning is model-free fictitious play)
- **model_params:** - phi (learning rate) [S]: constrained 0-1; updates belief about opponent's action - D (dominance preference): constrained > 0; scales perceived chance of winning - guilt (advantageous inequity aversion) [S]: aversion to unequal resource distribution; depression group higher than controls - lambda (inverse temperature): constrained > 0; decision noise
- **social_param:** guilt -- aversion to advantageous inequity (Fehr-Schmidt); higher in depression, correlated with depressive symptoms (r = 0.26)
- **social_param_name:** phi
- **social_param_value:** 0.26
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Cumulative integrated Bayesian Information Criterion (iBIC)
- **how_model_fit:** individual-level-fit (hierarchical Bayesian via MCMC in RStan)
- **data_type_fit_to:** choice behavior  ---  #### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + univariate GLM (ROI)
- **contrast:** - Win vs. Loss at outcome (bilateral VS, whole-brain FWE p < .05) - Win PE at amount revelation (bilateral VS, SVC p < .05) - Transfer amount as parametric modulator in VMPFC (SVC p < .05) - Challenge vs. no-challenge in ACC and bilateral AI (SVC p < .05)
- **key_regions:** Comparable win signals in bilateral VS; guilt-associated VMPFC activation during transfer; guilt-associated ACC and right AI activation to challenge.
- **coordinates_peak:** - Left VS (win vs. loss): -12, 12, -6 - Right VS (win vs. loss): 12, 9, -6 - Left VS (win PE): -12, 15, -6 - Right VS (win PE): 12, 9, -9 - VMPFC (guilt x transfer): -6, 60, -15 - ACC (guilt x challenge): 0, 42, 27 - Left AI (guilt x challenge): -36, 27, -3 - Right AI (guilt x challenge): 27, 18, -21
- **analysis_type:** both (whole-brain FWE corrected + ROI/SVC)  ---  #### QUALITY

## Quality
- **sample_size:** N = 112 at T1 (65 depression, 47 controls); T2: 26 treatment completers, 25 non-treatment depression, 39 controls. Ages ~33-35.
- **population_category:** mixed
- **population_age_range:** 
- **ecological_validity:** Moderate. Resource contest game mimics real-world social competition with dynamic bidding; played with adaptive computer (believed human). Lab setting limits generalizability.
- **eligibility_flag:** 
- **concerns:** Opponent was adaptive computer, not a real human player. Transfer may reflect strategic concerns rather than pure altruism. No treatment effect on task performance at T2.
- **limitations_reported:** Higher transfer may reflect strategic concerns rather than pure altruism; no treatment effect on task performance; spontaneous recovery in non-treatment group may confound T2 comparisons.
- **limitations_categorized:** task simplicity; confound between altruism and strategy; limited treatment effect; spontaneous remission confound
- **preregistered:** Not reported
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - Study 1: Mean fitted parameter values not fully reported in accessible text (figures show distributions but exact means partially obscured by text conversion artifacts) -- MEDIUM confidence - All studies: DOI not available (dissertation) -- HIGH confidence - Study 1: fMRI coordinates extracted from figure captions; should be verified against supplement tables -- MEDIUM confidence
- **cannot_find:** - Exact DOI for the dissertation - Explicit data/code sharing links - Some exact mean parameter values for Study 1 (partially readable from supplement figure description)
- **other_notes:** This is a dissertation containing three separate but thematically related studies. Studies 1 and 2 use the same resource contest paradigm but different clinical populations (depression vs. PTSD). Study 3 uses a different paradigm (Trust Game + HGF). No supplement file was found separate from the dissertation itself -- all supplementary materials are embedded within the dissertation text. The dissertation was defended April 15, 2021 at Virginia Tech. Flag as dissertation; no double-counting concerns detected (each study uses a distinct clinical sample and appears independently conceived). Check whether Papers I, II, or III were subsequently published as journal articles -- if so, mark this dissertation entry as `duplicate_suspected` for those specific studies.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- _(taxonomy layer not generated for dropped studies)_
