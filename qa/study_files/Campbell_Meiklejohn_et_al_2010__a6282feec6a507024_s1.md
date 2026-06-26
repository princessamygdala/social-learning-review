# Campbell-Meiklejohn et al. (2010)

- **study_id:** `a6282feec6a507024_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Campbell-Meiklejohn, D. K., Bach, D. R., Roepstorff, A., Dolan, R. J., & Frith, C. D. (2010). How the opinion of others affects our valuation of objects. *Current Biology*, *20*(13), 1165–1170. https://doi.org/10.1016/j.cub.2010.04.055
- **citation_short:** Campbell-Meiklejohn et al. (2010)
- **doi:** 10.1016/j.cub.2010.04.055
- **publication_type:** peer-reviewed journal
- **year:** 2010.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** CentreforNeuroimaging,12QueenSquare, beforeratingeachreviewerfrom1(notatall)to7(verymuch); University, taskdescribedinFigure1whilebeingscannedwithfunctional; mittedalistof20songsthatcouldbepurchased justtwoexpertindividuals; ethatsocial Unlessotherwisestated,allfMRIanalysiswascompletedby; CentreofFunctionally thatthey(thesubject)wouldlike; mity,butithadprevi- AgreementwithExpertReviewers; mity through which we change object valuation; etheror meanfemalereviewer’sratingwas4; emails: dan.cfin@gmail.com
- **code_url:** 

## Computational level
- **study_focus:** Social influence learning — how expert opinions alter the subjective value of objects (music) through modulation of reinforcement learning circuitry.
- **study_focus_short:** Social influence learning
- **learning_mode_description:** - Learning mode: Learning from expert reviewers' opinions about a song to update one's own valuation of that song   - Learning from:     - Source type (social): other (two expert reviewers)     - Source content (social): action/policy (reviewer preference/opinion)   - Learning about:     - Target type (non-social): world (object — song)     - Target content (non-social): outcome (subjective value of the song)
- **task_description:** Participants indicated their preference between a self-selected song and an alternative, then observed two expert music reviewers' preferences for the same songs, and finally received a token for one of the songs (independent of reviewer opinions). Songs with the most tokens at the end were purchased for the participant.
- **task_paradigm:** Social influence task
- **players:** Single agent (participant), multi-target (2 expert reviewers)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Song titles (participant-selected and alternatives), photographs of reviewers and participant, token rewards
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Receiving preferred song vs. alternative activated ventral striatum (peak MNI: 14, 10, −8; −16, −2, 2) — whole-brain cluster-corrected Z > 2.3, p < 0.05   - Agreement with both reviewers vs. both disagreeing activated left ventral striatum (peak: −10, 8, −12) — whole-brain cluster-corrected Z > 2.3, p < 0.05   - Social influence on object value (interaction of review outcome × object outcome × B_inf) activated ventral striatum (400 voxels, Z_max = 3.44, right peak: 10, 18, −8; left peak: −6, 14, −8) — whole-brain cluster-corrected Z > 2.3, p < 0.05   - Mean behavioral influence coefficient B_inf = 0.091 (SD = 0.17)   - Disagreement × B_inf: rTPJ (peak: 66, −30, 36), dACC (peak: 4, 16, 34), bilateral insula (right peak: 52, 8, 2; left peak: −38, 14, 0), lateral PFC (right peak: 36, 48, 22; left peak: −44, 48, 4)
- **effect_size:** - Main Results:   - Receiving preferred song vs. alternative activated ventral striatum (peak MNI: 14, 10, −8; −16, −2, 2) — whole-brain cluster-corrected Z > 2.3, p < 0.05   - Agreement with both reviewers vs. both disagreeing activated left ventral striatum (peak: −10, 8, −12) — whole-brain cluster-corrected Z > 2.3, p < 0.05   - Social influence on object value (interaction of review outcome × object outcome × B_inf) activated ventral striatum (400 voxels, Z_max = 3.44, right peak: 10, 18, −8; left peak: −6, 14, −8) — whole-brain cluster-corrected Z > 2.3, p < 0.05   - Mean behavioral influence coefficient B_inf = 0.091 (SD = 0.17)   - Disagreement × B_inf: rTPJ (peak: 66, −30, 36), dACC (peak: 4, 16, 34), bilateral insula (right peak: 52, 8, 2; left peak: −38, 14, 0), lateral PFC (right peak: 36, 48, 22; left peak: −44, 48, 4)
- **learning_from:** Other (expert reviewers); reviewer preference opinions about songs
- **learning_about:** World (object); subjective value of songs  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** Linear regression model: B_inf = standardized change in song desirability rating per unit net reviewer opinion. Used as between-subject regressor in fMRI GLM. No formal computational model (e.g., RL, Bayesian) was fit to trial-by-trial behavior.
- **model_family:** Utility / EV
- **model_class:** Other
- **all_models_tested:** [{"name": "Linear regression (B_inf as influence measure)", "family": "linear regression", "n_params": 1, "metric": "N/A — used as regressor, not compared"}]
- **model_mb_mf:** N/A (not RL)
- **model_params:** - B_inf: standardized regression coefficient capturing the degree to which net reviewer opinion shifted post-experiment song desirability ratings (mean = 0.091, SD = 0.17) [S]
- **social_param:** B_inf — individual tendency to be influenced by reviewer opinions on song valuation [S]
- **social_param_name:** B_inf
- **social_param_value:** 0.091
- **social_param_sd:** 0.17
- **social_param_range:** 
- **model_comparison_metric:** N/A — single descriptive measure, no model comparison performed
- **how_model_fit:** params-calculated-independently (B_inf calculated from pre/post behavioral ratings via linear regression, then entered as between-subject covariate in fMRI analysis)
- **data_type_fit_to:** choice behavior (song desirability ratings pre vs. post)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — B_inf used as between-subject regressor in whole-brain GLM; also univariate GLM for main effects
- **contrast:** - Object reward: [R_S S + R_A S] − [R_S A + R_A A] (preferred song token vs. alternative token) → VS, lPFC, PCC - Reviewer agreement: [R_S S + R_S A] − [R_A S + R_A A] (both agree vs. both disagree) → left VS - Social influence on object value (interaction × B_inf): [R_S S − R_S A] − [R_A S − R_A A] × B_inf → bilateral VS - Disagreement × B_inf: dACC, bilateral insula, lateral PFC, rTPJ - Unanimous agreement vs. split: R_S − R_SPLIT → right anterior insula (peak: 34, 18, −14) - Unanimous disagreement vs. split: R_A − R_SPLIT → right anterior insula (peak: 42, 24, −8)
- **key_regions:** Social influence on object value in bilateral ventral striatum; reviewer agreement in left ventral striatum; disagreement sensitivity (B_inf) in rTPJ, dACC, bilateral anterior insula, lateral PFC; unanimous opinions in right anterior insula.
- **key_regions_abbrev:** VS, striatum, lPFC, dACC, ACC, TPJ, insula, AI
- **coordinates_peak:** Object reward (preferred > alternative): - Right ventral striatum: 14, 10, −8 - Left ventral striatum: −16, −2, 2 - Left lateral PFC: −46, 40, 4 - Posterior cingulate cortex: −2, −36, 34  Reviewer agreement (both agree > both disagree): - Left ventral striatum: −10, 8, −12 - Right ventral striatum (Z > 2.0): 8, 8, −12 - Left parieto-occipital/retrosplenial: −16, −56, 2 - Right parieto-occipital: 8, −62, 10 - Left occipital fusiform (V4): −18, −86, −14  Agreement masked by object reward: - Ventral striatum: −8, 10, −10  Social influence on object value (interaction × B_inf): - Right ventral striatum: 10, 18, −8 - Left ventral striatum: −6, 14, −8  Disagreement × B_inf: - Right insula/central opercular cortex: 52, 8, 2 - Left insula/central opercular cortex: −38, 14, 0 - Dorsal ACC: 4, 16, 34 - Right lateral PFC: 36, 48, 22 - Left lateral PFC: −44, 48, 4 - Right TPJ: 66, −30, 36  Unanimous agreement > split: - Right anterior insula: 34, 18, −14  Unanimous disagreement > split: - Right anterior insula: 42, 24, −8  Negative B_inf subgroup agreement: - Right ventral striatum: 6, 14, −6 - Left ventral striatum: −6, 16, 2
- **analysis_type:** whole-brain  ---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 28 (15 male, 13 female); healthy adults
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderately ecological — participants used their own desired songs (personally relevant stimuli), but reviewer opinions were experimentally manipulated and the interaction context was artificial (no real-time social exchange). Expert reviewers were described and shown in photos but were not real interacting agents.
- **eligibility_flag:** The paper does not fit a formal computational model of learning (no RL, Bayesian, or similar trial-by-trial model). The "model" is a linear regression coefficient (B_inf) used as a between-subject covariate. This is borderline — flag as: "No formal computational learning model; B_inf is a descriptive behavioral measure used as fMRI regressor, not a trial-by-trial computational model of learning.
- **concerns:** - No formal computational model of learning was employed (no RL, Bayesian belief updating, or similar). The analysis relies on a simple linear regression coefficient (B_inf) and standard fMRI GLM contrasts. - The B_inf measure captures pre-to-post rating change, not trial-by-trial learning dynamics. - The paper frames findings in terms of reinforcement learning circuitry but does not actually implement or test any computational learning model. - Supplement not accessible (no supplement file found in papers folder). Coordinate tables referenced as Table S1 and Table S2 in supplement were not available for verification.
- **limitations_reported:** Authors note that: individual differences in influence are large and not all participants were influenced in the same direction (7 showed negative B_inf); the mechanism by which reviewer opinions change object value is unclear — it could be via expectations of social consequences (approval, affiliation) or via expectations about non-social features of the song; the anterior insula finding for unanimous opinions was unexpected and the explanation (feeling states rather than uncertainty) is speculative; the study cannot distinguish whether value changes are driven by informational vs. normative social influence.
- **limitations_categorized:** limited ecological validity; no formal computational model; unclear mechanism of social influence; individual differences not fully explained; correlational fMRI design; small sample size
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Partial
- **wc_rule10:** Partial
- **wc_score:** 2.5
- **wc_total:** 2.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** yes
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - winning_model (LOW): No formal computational model — B_inf is a descriptive regression coefficient, not a computational learning model - model_family (LOW): Classified as linear regression/GLM; paper references reinforcement learning concepts but does not implement one - eligibility_flag (MEDIUM): Borderline — no formal computational model of learning; may not meet inclusion criterion "uses computational modeling" - coordinates_peak (MEDIUM): Main text coordinates extracted; full Table S1 and S2 referenced in supplement but supplement not available for verification
- **cannot_find:** - Full coordinate tables (Table S1, Table S2) — referenced as being in supplement, which was not available - Any formal computational model specification (none exists in this paper) - Effect sizes beyond Z-statistics and cluster sizes (no Cohen's d, r, or similar reported)
- **other_notes:** This paper is primarily an fMRI study examining neural correlates of social influence on object valuation. It references computational/reinforcement learning concepts (prediction errors, value signals, dopamine) but does not implement any formal computational model. The "model" is a standard GLM with a behavioral covariate. This may not meet the inclusion criterion of "uses computational modeling" depending on how strictly that is interpreted. The paper is influential in the social influence/valuation literature and demonstrates overlap between social agreement signals and reward signals in ventral striatum. Supplement not accessible — noted accordingly.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_depth = parametric
- spec_locus = source
- spec_neural = dedicated
- spec_source = social
- tax_domain_A_influence_transmission
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_instructed
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = utility_EV
- tax_rr_model_utility_EV
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_approval_reward
- tax_rr_secondary_topic = norm_conformity
- tax_rr_topic_norm_conformity
- tax_rr_topic_social_approval_reward
- tax_topic_norm_conformity
- tax_topic_social_approval_reward
