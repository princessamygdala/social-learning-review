# Yoshida et al. (2010)

- **study_id:** `a8b11e1958a9bf87b_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Yoshida, W., Seymour, B., Friston, K. J., & Dolan, R. J. (2010). Neural mechanisms of belief inference during cooperative games. *The Journal of Neuroscience, 30*(32), 10744–10751. https://doi.org/10.1523/JNEUROSCI.5895-09.2010
- **citation_short:** Yoshida et al. (2010)
- **doi:** 10.1523/JNEUROSCI.5895-09.2010
- **publication_type:** peer-reviewed journal
- **year:** 2010.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ethertohunthighlyvaluedstagstogetherandsharethe dateandendorseourcomputationalmodelandprovideanew; etheoryinwhichhumansubjectsinteract frontalcortex,withinwhatistraditionallyreferredtoasatheory; CentreforNeuroimaging,InstituteofNeurology,UniversityCollegeLondon,LondonWC1N3BG,UnitedKingdom; University College London, 12 Queen Square, London WC1N 3BG, United Kingdom; depthofrecursionofthestrategybeingused,anindexofexecutivesophistication; ethearguablyuniqueabilitytounderstandthementalrepresentationsofothers; mittedtoitdespitetheoccasional mizetheirownbehaviorandmaximizerewards; ethescanningexper
- **code_url:** 

## Computational level
- **study_focus:** Mentalizing learning / Theory of mind — recursive belief inference about another agent's level of strategic sophistication during a cooperative stag hunt game.
- **study_focus_short:** Mentalizing learning / Theory of mind
- **learning_mode_description:** - Learning mode: Learning from the computer agent's observed movement choices about its level of strategic sophistication (recursive belief inference), then optimizing own strategy accordingly.   - Learning from:     - Source type (social): other (computerized agent playing as co-hunter)     - Source content (social): action/policy (observed movement decisions of the other player)   - Learning about:     - Target type (social): other (computerized agent)     - Target content (social): state (mental state; level of strategic sophistication / recursive intentionality)
- **task_description:** In a grid-based stag hunt game, participants and a computerized agent each move sequentially to hunt either low-value stationary rabbits (solo capture) or a high-value mobile stag (requires cooperative "pincer" capture by both hunters). The computer agent's strategy (1st-, 3rd-, or 5th-order sophistication) shifted every 5–8 games without notice, requiring participants to continuously infer the agent's level of cooperative sophistication and adapt their own strategy.
- **task_paradigm:** Stag hunt
- **players:** Single agent (participant), dyadic (computerized agent partner)
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Grid maze, mobile stag icon, stationary rabbit icons, point-based monetary feedback
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Cooperation rate significantly higher with 5th-order agent (0.405) vs. 3rd-order (0.089, p < 0.0001) and 1st-order (0.026, p < 0.00001)   - ToM model explained behavior significantly better than fixed-strategy model (Bayesian model selection; inferred subject sophistication bound K = 5)   - Bilateral ventral striatum correlated with payoff at outcome (R: Z = 4.67; L: Z = 3.89; SVC corrected R p < 0.01, L p < 0.05)   - Caudal ventral striatum correlated with sophistication level at stag move (R: Z = 3.55; L: Z = 3.84), indexing social reward of cooperation   - Anterior MPFC (paracingulate cortex) correlated with entropy of belief inference about other's strategy (Z = 4.76; SVC p < 0.01)   - Left DLPFC correlated with sophistication level (Z = 4.26)   - Bilateral FEF correlated with sophistication level (L: Z = 4.25; R: Z = 4.17)   - Left SPL correlated with sophistication level (Z = 4.22)
- **effect_size:** - Main Results:   - Cooperation rate significantly higher with 5th-order agent (0.405) vs. 3rd-order (0.089, p < 0.0001) and 1st-order (0.026, p < 0.00001)   - ToM model explained behavior significantly better than fixed-strategy model (Bayesian model selection; inferred subject sophistication bound K = 5)   - Bilateral ventral striatum correlated with payoff at outcome (R: Z = 4.67; L: Z = 3.89; SVC corrected R p < 0.01, L p < 0.05)   - Caudal ventral striatum correlated with sophistication level at stag move (R: Z = 3.55; L: Z = 3.84), indexing social reward of cooperation   - Anterior MPFC (paracingulate cortex) correlated with entropy of belief inference about other's strategy (Z = 4.76; SVC p < 0.01)   - Left DLPFC correlated with sophistication level (Z = 4.26)   - Bilateral FEF correlated with sophistication level (L: Z = 4.25; R: Z = 4.17)   - Left SPL correlated with sophistication level (Z = 4.22)
- **learning_from:** Other (computerized agent); observed movement actions/policy of the other player in sequential game trials.
- **learning_about:** Other (computerized agent); mental state — level of strategic sophistication (recursive intentionality/theory of mind depth).  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Theory of Mind (ToM) Bayesian belief inference model (K = 5; 2 params: subjective utility ρ, forgetting parameter κ)
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "Fixed-strategy model (k=1 through k=6)", "family": "Fixed strategy", "n_params": 1, "metric": "Bayesian model selection (log evidence)"},   {"name": "ToM model (K=1 through K=6)", "family": "Bayesian belief updating", "n_params": 2, "metric": "Bayesian model selection (log evidence)"} ] (12 models total: 6 fixed-strategy + 6 ToM models)
- **model_mb_mf:** MB (model-based — subjects maintain internal model of other's strategy and use recursive inference to optimize own policy)
- **model_params:** - ρ (subjective utility parameter): scales utility of rabbit relative to stag; mean fitted value = 0.41 (SD = 0.01; range 0.39–0.43) [S — influences social vs. competitive behavior] - κ (forgetting parameter): exponentially discounts previous evidence, allowing faster response to strategy changes; mean fitted value = 0.68 (SD = 0.11; range 0.51–0.84) [S — governs speed of adaptation to other's changing strategy] - K (sophistication bound): inferred = 5 (not a free parameter; selected via model comparison)
- **social_param:** ρ (subjective utility) — scales rabbit vs. stag utility, governing the trade-off between competitive (solo rabbit) and cooperative (joint stag) behavior; κ (forgetting) — governs how quickly the subject adapts belief about the other agent's changing strategy.
- **social_param_name:** ρ
- **social_param_value:** 0.41
- **social_param_sd:** 0.01
- **social_param_range:** 0.39–0.43
- **model_comparison_metric:** Bayesian model selection (log model evidence; Stephan et al., 2009)
- **how_model_fit:** individual-level-fit (MLE per subject for ρ; κ optimized per subject; also group-level estimation reported: ρ = 0.41, κ = 0.75 from all subjects' data)
- **data_type_fit_to:** choice behavior (movement selections in grid maze)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — two parametric modulators derived from the ToM model (entropy of belief distribution and sophistication level) used as regressors at computer move events; payoff and sophistication level as parametric regressors at outcome and stag move events.
- **contrast:** - Payoff amount at outcome event → bilateral ventral striatum - Sophistication level at stag move event → caudal ventral striatum (social reward of cooperation) - Entropy of belief inference at computer move event → anterior MPFC (paracingulate cortex), posterior cingulate - Sophistication level at computer move event → left DLPFC, bilateral FEF, left SPL
- **key_regions:** Entropy of belief inference (uncertainty about other's strategy) in anterior rostral MPFC (paracingulate, BA 10); depth of recursive strategic thinking in left DLPFC (BA 46), bilateral FEF (BA 7), and left SPL (BA 6); payoff in bilateral ventral striatum; social cooperation reward in caudal ventral striatum.
- **key_regions_abbrev:** VS, striatum, mPFC, dlPFC, AI
- **coordinates_peak:** Ventral striatum (payoff, R): 16, 21, -8 Ventral striatum (payoff, L): -10, 19, 0 Ventral striatum (sophistication, R): 8, 8, 0 Ventral striatum (sophistication, L): -10, 8, 0 Medial prefrontal cortex (entropy, L): -6, 53, 14 Medial prefrontal cortex (entropy, R): 4, 50, 8 Posterior cingulate (entropy): 2, -50, 32 Dorsolateral prefrontal cortex (sophistication, L): -50, 28, 32 Frontal eye field (sophistication, L): -20, 6, 46 Frontal eye field (sophistication, R): 30, 9, 59 Posterior parietal cortex / SPL (sophistication, L): -16, -55, 65 Dorsolateral prefrontal cortex (sophistication, R): 40, 38, 36  Note: Coordinates are in Talairach space, not MNI. The paper used SPM5 with MNI normalization but Table 2 header states "Talairach axis" — this is a potential inconsistency worth flagging.
- **analysis_type:** both (ROI with small volume correction for ventral striatum and MPFC based on prior coordinates; whole-brain at p < 0.001 uncorrected, k > 100 for other regions)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 12 (3 female; mean age 24.8 ± 3.0 years). 11 of 12 completed two sessions (80 games); 1 completed one session (40 games) due to technical problem.
- **population_category:** children
- **population_age_range:** M=24.8
- **ecological_validity:** The grid-based stag hunt game was designed to be less abstract than normal-form games and to necessitate rapid online assessment — authors claim "a high degree of ecological realism." However, the partner was a computerized agent (not human), limiting true social interaction. The agent did not reciprocally adapt to the subject's behavior, which the authors acknowledge limits the social ecological validity.
- **eligibility_flag:** 
- **concerns:** - Very small sample (N = 12) by current standards - Computerized agent rather than human partner — the agent does not reciprocally adapt to the participant, limiting true social interaction (authors acknowledge this) - Coordinates labeled "Talairach axis" in Table 2 but the paper describes MNI normalization in SPM5 — coordinate space may be ambiguous - Threshold p < 0.001 uncorrected with cluster extent k > 100 is liberal by current standards - No supplement accessible to verify additional details (supplement referenced as "supplemental material" hosted on jneurosci.org but not available as a file in the papers folder)
- **limitations_reported:** an experimental design that incorporates a computer agent allows flexible control of the level of sophistication of the other player, it does not capture the full depth of strategic play in purely human games, since subjects should appreciate that the computer agent does not reciprocally adapt its behavior based on their actions"; "it is possible that subjects' actions do not necessarily correspond precisely to their beliefs. Such mismatches have been shown in previous data... and this might be caused by irrational learning or belief inference modified by the circumstances (or situations)"; observation that payoff balance between stag and rabbit may affect behavior suggests "model parameters might be adjusted from trial to trial
- **limitations_categorized:** limited ecological validity (computer vs. human partner); action-belief mismatch; potential parameter non-stationarity; small sample size
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - coordinates_peak: MEDIUM confidence — Table 2 says "Talairach axis" but methods describe MNI normalization; coordinate space ambiguous - wc_3 (simulate): MEDIUM — simulations mentioned in supplemental figures but supplement not accessible to verify extent - effect_size: MEDIUM — Z-values and SVC p-values reported but no standardized effect sizes (d, r, etc.) for behavioral or neural effects
- **cannot_find:** - Full model equations (Equation 1 is partially garbled due to text extraction artifacts; full specification refers to Yoshida et al., 2008) - Supplementary Figures S1–S3 referenced but not accessible as files - Standardized behavioral effect sizes (only raw cooperation rates and p-values reported) - Whether coordinates are truly Talairach or MNI (contradictory information)
- **other_notes:** - The computational model (ToM model) was previously described in Yoshida et al. (2008, PLoS Computational Biology) — the current paper applies it to fMRI data - Text extraction has OCR artifacts: "(cid:1)" appears throughout for mathematical symbols (±, ×, ≤, etc.) and Greek letters - Supplement not available in the papers folder; referenced as online supplemental material at jneurosci.org - The paper's key contribution is dissociating two components of theory of mind in prefrontal cortex: uncertainty of belief inference (MPFC) vs. depth of recursive reasoning (DLPFC)
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = structural
- spec_locus = target
- spec_neural = dedicated
- spec_source = social
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MB
- tax_model_bayesian
- tax_param_PE_signal
- tax_param_decay
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_decay
- tax_rr_param_precision
- tax_rr_primary_topic = strategic_reasoning
- tax_rr_secondary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_rr_topic_strategic_reasoning
- tax_topic_mentalizing
- tax_topic_strategic_reasoning
