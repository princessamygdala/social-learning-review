# Cui (2021)

- **study_id:** `aa7a0276ada8cc7db_s2`
- **on_website:** NO — DROPPED (verify below)
- **why_not_on_website:** (no eligibility flag recorded — likely duplicate/superseded version; confirm)

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Cui, Z. (2021). Understanding social function in psychiatric illnesses through computational modeling and multiplayer games [Doctoral dissertation, Virginia Polytechnic Institute and State University]. (Paper II: Cui, Z., Zhu, L., Chiu, P. H., & King-Casas, B.)
- **doi:** Not provided for dissertation.
- **publication_type:** thesis
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Social competitive behavior in combat-related PTSD; disentangling effects of conflict avoidance, dominance preference, and social learning on aggression.
- **study_focus_short:** Social competitive behavior in combat-related PTSD
- **learning_mode_description:** - Learning mode: Learning from opponent's bidding behavior during repeated social competition to update belief about opponent's strategy   - Learning from:     - Source type (social): other (opponent/computer partner)     - Source content (social): action/policy (bidding and challenge decisions)   - Learning about:     - Target type (social): other (opponent)     - Target content (social): action/policy (predicted bidding behavior conditional on context)
- **task_description:** Veterans played a 30-round resource contest game with an adaptive computer partner (believed to be human). Alpha distributed $10, beta could challenge for alpha position via bidding contest. Same paradigm as Study 1.
- **task_paradigm:** Auction task
- **players:** Single agent (participant), dyadic (adaptive computer partner believed to be human)
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Monetary endowments, position labels (alpha/beta), bidding amounts, contest outcomes
- **method:** behavioural
- **main_result:** - Veterans with current PTSD challenged more often than controls (t = 2.0, p = .04) - PTSD veterans less responsive to opponent's previous bid (interaction t = -2.12, p = .03) - Lower conflict avoidance (A) in current PTSD vs. controls (t = -2.46, p = .01) - Diminished learning rate in current PTSD vs. controls (t = -2.36, p = .02) and vs. remitted (t = -2.57, p = .01) - Comparable D across groups (|t|s < 1.12, ps > .26) - LR negatively correlated with PCL symptom severity (r = -0.18, p = .02) - LR-symptom association held after controlling BDI, CES, TBI (partial r = -0.22, p = .005)
- **effect_size:** - Challenge rate group difference: t = 2.0 - A group difference (current PTSD vs. no PTSD): t = -2.46 - LR group difference (current PTSD vs. no PTSD): t = -2.36 - LR-symptom correlation: r = -0.18 - LR-symptom partial correlation: r = -0.22 (beta = -0.36)
- **learning_from:** Other (opponent); opponent's bidding actions during social contest
- **learning_about:** Other (opponent); opponent's likely bidding behavior conditional on transfer and role  ---  #### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Belief-learning + Fehr-Schmidt inequity aversion + conflict avoidance (6 params: LR, D, A, envy, guilt, IT)
- **model_family:** Rescorla-Wagner
- **model_class:** Prediction error learning + utility maximization (social preference + conflict avoidance)
- **all_models_tested:** - {"name": "6P (A + D + IA)", "family": "Belief learning + full", "n_params": 6, "metric": "iBIC = 17992.5"} - {"name": "5P (D + IA)", "family": "Belief learning + D + inequity", "n_params": 5, "metric": "iBIC = 18727.7"} - {"name": "5P (A + IA)", "family": "Belief learning + A + inequity", "n_params": 5, "metric": "iBIC = 19127.4"} - {"name": "4P (A + D)", "family": "Belief learning + A + D", "n_params": 4, "metric": "iBIC = 19283.3"} - {"name": "4P (IA)", "family": "Belief learning + inequity", "n_params": 4, "metric": "iBIC = 19611.1"} - {"name": "3P (D)", "family": "Belief learning + D", "n_params": 3, "metric": "iBIC = 19742.6"} - {"name": "3P (A)", "family": "Belief learning + A", "n_params": 3, "metric": "iBIC = 20264.9"}
- **model_mb_mf:** MF
- **model_params:** - LR (learning rate) [S]: constrained 0-1; No PTSD: 0.16 (0.10), Current PTSD: 0.12 (0.07), Remitted: 0.17 (0.11) - D (dominance preference): constrained > 0; No PTSD: 11.41 (3.92), Current PTSD: 11.68 (3.33), Remitted: 10.78 (3.29) - A (conflict avoidance) [S]: No PTSD: 3.85 (1.58), Current PTSD: 3.14 (1.54), Remitted: 3.05 (1.63) - envy (disadvantageous inequity aversion): No PTSD: 1.13 (0.37), Current PTSD: 1.08 (0.37), Remitted: 1.04 (0.51) - guilt (advantageous inequity aversion) [S]: No PTSD: 0.08 (0.81), Current PTSD: 0.01 (0.75), Remitted: 0.11 (0.67) - IT (inverse temperature): No PTSD: 0.52 (0.10), Current PTSD: 0.49 (0.07), Remitted: 0.51 (0.08)
- **social_param:** A (conflict avoidance) -- lower in PTSD, captures threshold for engaging in social contest; LR (learning rate) -- lower in PTSD, captures speed of updating belief about opponent
- **social_param_name:** LR
- **social_param_value:** 0.16
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Cumulative integrated Bayesian Information Criterion (iBIC)
- **how_model_fit:** individual-level-fit (hierarchical Bayesian via MCMC in RStan)
- **data_type_fit_to:** choice behavior  ---  #### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioral study only)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  #### QUALITY

## Quality
- **sample_size:** N = 177 combat-exposed veterans (118 current PTSD, 20 remitted PTSD, 39 no PTSD). Age ~31 years.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate. Resource contest game mimics real-world social competition; dynamic interaction with adaptive computer partner (believed human). Military sample enhances relevance for combat PTSD but limits generalizability. Online not reported -- appears lab-based.
- **eligibility_flag:** 
- **concerns:** Small remitted PTSD group (N = 20) limits generalizability. Mostly male sample (88-95% male). High comorbidity with depression in PTSD group (55% comorbid MDD). No pre-deployment measures; cannot determine causality.
- **limitations_reported:** Small remitted PTSD sample; predominantly male sample limits gender analysis; lack of pre-deployment measures makes it difficult to determine if aggression preceded PTSD onset.
- **limitations_categorized:** sample size (remitted group); limited generalizability (gender); limited causal inference (cross-sectional)
- **preregistered:** Not reported
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
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
