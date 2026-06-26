# Gaule et al. (2024)

- **study_id:** `aa56074d11a12abcd_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Gaule, A., Bevilacqua, L., Molleman, L., van den Bos, W., van Duijvenvoorde, A. C., Roberts, R., Pease, C. R., McCrory, E., & Viding, E. (2024). Social learning and preferences in adolescents with conduct problems and varying levels of callous-unemotional traits. *JAACAP Open*, *2*(2), 79–89. https://doi.org/10.1016/j.jaacop.2023.12.008
- **citation_short:** Gaule et al. (2024)
- **doi:** 10.1016/j.jaacop.2023.12.008 - Confidence: HIGH
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** ethod: WeusedaseriesofeconomicgamestoassesshowadolescentswithCP/HCU(n¼46),CP,andlowerlevelsofCUtraits(CP/LCU)(n¼; ethat,undercontrolledexperimentalconditions,adolescentswithCPhavemoredifficultylearningtodifferentiate; school without qualifications, and involve- differencesinengagementincooperativebehaviors:(1)social; laborative behaviors is an important factor for the example,gettingmoreorlessthanotherpeople; ethesocialworld,inparticularwhentotrustothersandhowtoworktogetherwiththem,iscrucialtowell-; laborate with others have been haviors, have trouble adjusting to social norms, and have; ethod
- **code_url:** 

## Computational level
- **study_focus:** Trust learning and social coordination learning in adolescents with conduct problems — how individuals learn to differentiate between cooperative and uncooperative social environments (trustworthy vs untrustworthy; friendly vs unfriendly partners), and whether social preferences (inequality aversion), prior beliefs, and belief updating explain group differences. - Confidence: HIGH
- **study_focus_short:** Trust learning and social coordination learning in adolescents with conduct
- **learning_mode_description:** - Learning mode: Learning from partners' cooperative/uncooperative choices about which social environments to trust and coordinate with   - Learning from:     - Source type (social): other (anonymous partner players from different social environments)     - Source content (social): action/policy (partner's choice of X or Y, reflecting cooperation level)   - Learning about:     - Target type (social): other (partner/social environment)     - Target content (social): state (mental state; trustworthiness/friendliness of social environment) - Confidence: HIGH
- **task_description:** Participants played incentivized economic games (Trust Game and Coordination Game) with partners from different social environments (trustworthy/untrustworthy; friendly/unfriendly). Participants chose between two options (A or B), then observed the partner's predetermined choice (X or Y), and received monetary payoffs determined by the combined choices. - Confidence: HIGH
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (partners from 2 social environments per game: trustworthy/untrustworthy in Trust Game; friendly/unfriendly in Coordination Game) - Confidence: HIGH
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Abstract economic game matrices (rows of boxes labeled A and B), stick figure partners with colored backgrounds indicating social environment, monetary outcomes (dots) - Confidence: HIGH
- **method:** behavioural
- **method_full:** behavioural - Confidence: HIGH
- **main_result:** - Main Results:   - CP/HCU adolescents significantly poorer than TD at differentiating trustworthy/untrustworthy environments in Trust Game (B = −0.565, p < .001)   - CP/LCU adolescents significantly poorer than TD at differentiating trustworthy/untrustworthy environments in Trust Game (B = −0.478, p = .002)   - CP/LCU significantly poorer than TD at differentiating friendly/unfriendly environments in Coordination Game (B = −0.322, p = .031)   - CP/HCU showed anti-correlated win-stay/lose-shift pattern differing from TD in Trust Game (B = −0.420, p = .012)   - No group differences in social preferences (inequality aversion), prior beliefs, or non-social learning   - Computational RL models could not be fit — learning rate estimates too low to interpret across all groups - Confidence: HIGH
- **effect_size:** - Trust Game: CP/HCU vs TD, B = −0.565; CP/LCU vs TD, B = −0.478 (GLMM coefficients) - Coordination Game: CP/LCU vs TD, B = −0.322 (GLMM coefficient) - Trust Game win-stay/lose-shift: CP/HCU vs TD, B = −0.420 - Non-social task win-stay: B = 0.454; Trust Game win-stay: B = 0.312 - Note: Only regression coefficients (B) reported; no standardized effect sizes (d, r, eta-squared) provided - Confidence: HIGH
- **learning_from:** Other (anonymous partner players); partner's cooperative/uncooperative choices (X or Y) in economic games - Confidence: HIGH
- **learning_about:** Other (social environment/partner); trustworthiness and friendliness of social partners - Confidence: HIGH  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Reinforcement learning model attempted but FAILED to fit — learning rate estimates were too low to interpret for any group. Authors resorted to win-stay/lose-shift heuristic analysis instead. No winning computational model. - Confidence: HIGH
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** MEDIUM — model details referenced to Supplement 4; only general description available in main text
- **model_mb_mf:** MEDIUM — inferred from RL framework described; not explicitly stated
- **model_params:** LOW — full parameter specification stated to be in Supplement 4 (not accessible from main text)
- **social_param:** LOW — could not be meaningfully estimated; details in inaccessible supplement
- **social_param_name:** LOW
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Not reported — model fitting failed - Confidence: HIGH
- **how_model_fit:** MEDIUM — inferred from description of fitting to binary choices; procedure details in supplement  ### CANNOT FIND  - Full model specification (formula, number of parameters, priors if Bayesian) — referenced to Supplement 4, not accessible - Model comparison metrics — model fitting failed; no comparison conducted - Exact fitting procedure details — in Supplement 4 - Parameter recovery or simulation results — likely absent even from supplement given model failure - Standardized effect sizes (d, r, η²)  ### OTHER NOTES  - This paper used the exact same task protocol as Westhoff et al. (2020) — potential for overlap if that paper is also in the corpus. However, this paper uses a clinical sample (CP adolescents) vs. the TD sample in Westhoff et al., so these are independent datasets. - The paper is published in JAACAP Open (open access) under CC BY license. - Supplement not found in papers folder; all four supplements (1–4) are referenced but none accessible. This is flagged but does not warrant `re_extract_flag: true` since the main text is complete and the key finding is that computational models could not be fit. - The paper's primary contribution is behavioral (group differences in choice patterns), not computational modeling per se. The computational modeling attempt is secondary and unsuccessful.  ### RE_EXTRACT_FLAG: false  ---  ### SELF-CRITIQUE  1. Re-read complete: confirmed all fields present and consistent. 2. The eligibility flag is appropriate — computational modeling was attempted but failed. This is a borderline case: the paper intended to use computational models and did attempt fitting, but the models could not produce interpretable parameters. The paper should be flagged but not excluded per instructions. 3. Learning mode correctly identifies social source (other's choices) and social target (other's trustworthiness/friendliness). 4. WC scores are consistent: only 1 model approach tested so Rule 2 = No, Rule 7 = No; no simulation = Rule 3 = No; no parameter/model recovery = Rules 5, 6 = No. 5. No coordinates needed (behavioral study). 6. All blank fields explicitly flagged in cannot_find with explanation.
- **data_type_fit_to:** choice behavior - Confidence: HIGH  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none - Confidence: HIGH
- **contrast:** N/A — no neuroimaging - Confidence: HIGH
- **key_regions:** N/A — no neuroimaging - Confidence: HIGH
- **coordinates_peak:** N/A — no neuroimaging - Confidence: HIGH
- **analysis_type:** N/A - Confidence: HIGH  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 151 (46 CP/HCU, 46 CP/LCU, 59 TD); all male; ages 11–16 years - Confidence: HIGH
- **population_category:** adolescents
- **population_age_range:** 11–16
- **ecological_validity:** Low ecological validity — computerized economic games with abstract stimuli and predetermined partner choices; no real-time social interaction; partners were described as from different "social environments" but behavior was pre-programmed. Limited to male adolescents only. - Confidence: HIGH
- **eligibility_flag:** FLAG — Computational modeling was attempted but failed (learning rates too low to interpret for any group). The paper ultimately relies on GLMM analysis of choice behavior and win-stay/lose-shift heuristics rather than successful computational model fitting. This is borderline for the inclusion criterion "uses computational modeling" since models were attempted but could not be fit. The learning component (adjusting to cooperative/uncooperative environments over repeated trials) is present. - Confidence: HIGH
- **concerns:** - Computational RL models could not be fit to any group — learning rate estimates too low to be meaningful. Authors acknowledged this and fell back to heuristic (win-stay/lose-shift) analysis. - Supplement 4 (containing full model specification and additional analyses) is referenced extensively but not accessible — model parameters, fitting procedure details, and model specification cannot be verified. - Effect sizes reported only as unstandardized B coefficients from GLMM; no standardized effect sizes (Cohen's d, r, etc.) reported. - All participants had below-average IQ (group means 86–90), which authors acknowledge may limit task/model suitability. - Task protocol adopted from Westhoff et al. (2020) designed for typically developing adolescents — may not be sensitive enough for CP populations. - Confidence: HIGH
- **limitations_reported:** our tasks were too complex for our CP participants, which led to more difficulty differentiating social environments"; "behavior across groups was generally erratic for all of our economic tasks, to the extent that we were unable to fit computational models"; "all of our groups had a mean level of IQ that was below average… this may limit the suitability of current tasks and computational models for elucidating the mechanisms underlying atypical behavior in CP"; "we were unable to investigate expectation updating because of poor model fit"; "we were unfortunately unable to compare whether groups were similar with respect to ethnicity due to low return rates of parent questionnaires"; "substantial heterogeneity in the responses within each group" - Confidence: HIGH
- **limitations_categorized:** Task complexity/suitability; poor computational model fit; limited sample characteristics (below-average IQ, all male); inability to test key mechanism (belief updating); missing demographic data (ethnicity); high within-group heterogeneity; limited ecological validity - Confidence: HIGH
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** No
- **wc_rule10:** Partial
- **wc_score:** 2.0
- **wc_total:** 2.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_psychopathy
- rr_pop_adolescents
- rr_pop_psychopathy
- rr_tax_mod_active_interaction
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target+context
- spec_source = social
- spec_target = partly
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_model_rescorla_wagner
- tax_popclass_clinical
- tax_popclass_developmental
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = trust
- tax_rr_secondary_topic = cooperation
- tax_rr_topic_cooperation
- tax_rr_topic_trust
- tax_topic_cooperation
- tax_topic_trust
