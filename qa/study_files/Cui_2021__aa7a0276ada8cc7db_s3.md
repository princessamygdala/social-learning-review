# Cui (2021)

- **study_id:** `aa7a0276ada8cc7db_s3`
- **on_website:** NO — DROPPED (verify below)
- **why_not_on_website:** (no eligibility flag recorded — likely duplicate/superseded version; confirm)

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Cui, Z. (2021). Understanding social function in psychiatric illnesses through computational modeling and multiplayer games [Doctoral dissertation, Virginia Polytechnic Institute and State University]. (Paper III: Cui, Z., Chiu, P. H., & King-Casas, B.)
- **doi:** Not provided for dissertation.
- **publication_type:** thesis
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Social learning adaptation to environmental volatility in borderline personality disorder; disentangling effects of learning deficits vs. interpersonal hypersensitivity.
- **study_focus_short:** Social learning adaptation to environmental volatility in borderline
- **learning_mode_description:** - Learning mode: Learning from partner's sharing/keeping decisions about partner's trustworthiness under varying volatility   - Learning from:     - Source type (social): other (human partner) / Source type (non-social): world (computer)     - Source content (social): action/policy (share vs. keep decisions)   - Learning about:     - Target type (social): other (human partner) / Target type (non-social): world (computer)     - Target content (social): state (mental state -- trustworthiness/sharing tendency)
- **task_description:** Participants played a modified repeated Trust Game as investors with three human partners and three matched computers under low, medium, and high volatility (1, 2, or 4 reversals in partner's sharing probability). Participants chose to invest ($6 quadrupled to $24) or keep; partners chose to share ($12 each) or keep ($24 to partner, $0 to participant).
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (3 human partners, 3 computer partners; sequential)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Blurred faces (social) or computer images (nonsocial), monetary outcomes, binary choices (invest/keep)
- **method:** online (behavioural; Amazon MTurk)
- **main_result:** - High-MSI group invested more often (F = 8.67, p = .004) with lower accuracy (F = 16.93, p < .001) - Overall lower learning rate in high-MSI (t = -3.80, p < .001) - Three-way interaction: condition x volatility x group (t = -2.82, p = .005) - Diminished learning adaptation to volatility in high-MSI specifically in social condition (volatility x group: t = -4.72, p < .001) but not nonsocial (t = -1.27, p = .20) - Within high-MSI: reduced learning adaptation in social vs. nonsocial (volatility x condition: t = -3.96, p < .001) - Comparable betrayal aversion between groups (F = 1.31, p = .25) - Reduced loss aversion in high-MSI (F = 10.67, p = .001) - Gender effect: diminished social learning adaptation driven by males
- **effect_size:** - Group main effect on investing: F(1,205) = 8.67, eta-squared not reported - Group main effect on accuracy: F(1,205) = 16.93 - Group effect on learning rate: t = -3.80 - Three-way interaction: t = -2.82 - Social condition volatility x group: t = -4.72
- **learning_from:** Other (human partner) or world (computer); partner's share/keep decisions
- **learning_about:** Other (human partner) or world (computer); trustworthiness / sharing tendency  ---  #### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** HGF2 (2-level Hierarchical Gaussian Filter with omega_2 [tonic volatility], beta [inverse temperature], gamma [loss aversion])
- **model_family:** HGF
- **model_class:** Belief updating (precision-weighted prediction error learning)
- **all_models_tested:** - {"name": "HGF3", "family": "Hierarchical Gaussian Filter (3-level)", "n_params": 3, "metric": "LME (social): higher than HGF2; pxp < 0.01"} - {"name": "HGF2", "family": "Hierarchical Gaussian Filter (2-level)", "n_params": 3, "metric": "LME (social): lowest; pxp > 0.99"} - {"name": "RW2", "family": "Rescorla-Wagner (dual learning rate)", "n_params": 4, "metric": "LME: higher than HGF2"} - {"name": "RW1", "family": "Rescorla-Wagner (single learning rate)", "n_params": 3, "metric": "LME: highest (worst)"}
- **model_mb_mf:** Bayesian
- **model_params:** - omega_2 (tonic volatility) [S]: determines dynamic learning rate; Low-MSI social R1: -4.19 (2.21), High-MSI social R1: -4.74 (1.48). Higher omega_2 = faster learning. - gamma (loss aversion): additional cost when partner keeps; Low-MSI: ~0.42-0.77, High-MSI: ~-0.47 to -0.16 (social). Betrayal aversion = gamma_social - gamma_nonsocial. - beta (inverse temperature): decision noise; Low-MSI: ~1.18-1.30, High-MSI: ~0.81-1.05 (social HGF2)
- **social_param:** omega_2 (tonic volatility) -- lower in high-BPD, especially in social condition under high volatility; captures inferred environmental volatility that drives dynamic learning rate. Betrayal aversion (gamma_social - gamma_nonsocial) -- comparable between groups.
- **social_param_name:** omega_2
- **social_param_value:** -4.19
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Summed negative log-model evidence (LME); Bayesian Model Selection (BMS) with protected exceedance probability (pxp)
- **how_model_fit:** individual-level-fit (MAP estimation via HGF Toolbox/TAPAS)
- **data_type_fit_to:** choice behavior  ---  #### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioral study only)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  #### QUALITY

## Quality
- **sample_size:** N = 207 (104 low-MSI, 103 high-MSI); recruited from Amazon MTurk. Gender, age, ethnicity matched between groups.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate. Online MTurk study with preprogrammed (non-adaptive) partners limits ecological validity. Trust game structure provides social interaction framework but partners do not respond to participant choices. Separate social and nonsocial conditions well-matched.
- **eligibility_flag:** 
- **concerns:** MSI screening does not guarantee BPD diagnosis -- high MSI cutoff (>=8) used but not equivalent to clinical diagnosis. High exclusion rate (173/380 excluded for data quality). Preprogrammed partners lack reciprocal interaction. MTurk sample quality concerns.
- **limitations_reported:** Preprogrammed partners limit examination of high-order social inference; MSI screening paired with no semistructured interview does not guarantee BPD diagnosis; MTurk sample had relatively high exclusion rate for poor data quality; lack of in-person interaction may limit detection of interpersonal hypersensitivity.
- **limitations_categorized:** limited ecological validity; diagnostic validity (screening vs. clinical diagnosis); data quality (online sample); task simplicity (non-adaptive partners)
- **preregistered:** Not reported  ---  ### CROSS-STUDY NOTES
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
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
