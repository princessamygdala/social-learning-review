# Huber et al. (2015)

- **study_id:** `a5fa9856df9dfb976_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Huber, R. E., Klucharev, V., & Rieskamp, J. (2015). Neural correlates of informational cascades: Brain mechanisms of social influence on belief updating. *Social Cognitive and Affective Neuroscience*, *10*(4), 589–597. https://doi.org/10.1093/scan/nsu090
- **citation_short:** Huber et al. (2015)
- **doi:** 10.1093/scan/nsu090
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Department ofPsychology, University ofBasel, 4055 Basel,Switzerland, 2Department of HigherNervous Activity and Psychophysiology, Saint; University199034, SaintPetersburg, Russia, and3Department of Psychology, NationalResearch UniversityHigher School of; ethankMarkusKlarhoefer,OliverSchu¨rmannandStefanThommenforassistanceinthefMRIexperimentsand; labor market information,onwhichafinaldecisionunderuncertaintyrests; mpiricalworkineconomics the theory of informational cascades; etheprobabilitythatacascadestartsinadecisiveway; lable social information may; lable social etal
- **code_url:** 

## Computational level
- **study_focus:** Social influence learning / informational cascades — how individuals weight social vs. private information when sequentially updating beliefs, and how overweighting of private information modulates the probability of starting an informational cascade.
- **study_focus_short:** Social influence learning / informational cascades
- **learning_mode_description:** - Learning mode: Learning from others' observed decisions and one's own private signal about which option (stock) is profitable   - Learning from:     - Source type (social): other (two fictitious stock traders)       - Source content (social): action/policy (observed buy decisions of traders)     - Source type (non-social): self       - Source content (non-social): outcome (private recommendation from rating agency)   - Learning about:     - Target type (non-social): world (which stock is profitable)       - Target content (non-social): state (world state; probability that a stock is "good")
- **task_description:** Participants acting as stock market traders sequentially observed the buying decisions of two fictitious traders (social information I and II) and then received a private recommendation from a rating agency, after which they chose which of two stocks to buy and reported their posterior probability judgment of having chosen correctly. A performance-contingent bonus was based on the accuracy of probability estimates via a quadratic scoring rule.
- **task_paradigm:** Social influence task
- **players:** Single agent (participant), multi-target (2 fictitious traders)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Abstract stock symbols (W, S), text-based decisions of fictitious traders, quality indicators (+, ++), probability rating scale
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Main Results:   - Participants chose in accordance with the Bayesian solution in 93.18% of trials   - Majority of participants (24/27) overweighted private vs. social information (Social Model preferred over Full Model and Bayesian Model; ΔDIC_FM-SM = 10.4; ΔDIC_BM-SM = 1590.4)   - Information weighting index negatively correlated with conformity index (r(25) = −0.83, p < .001)   - Belief updating by private information activated IFG/anterior insula, DLPFC, parietal cortex, precuneus (Table 1)   - Overweighting of private information positively correlated with IFG/anterior insula activity during private belief updating (Z = 3.35 at 45, 38, 10)   - Overweighting of private information negatively correlated with parietal-temporal cortex activity during private belief updating (Z = 3.46 at −51, −64, 22)
- **effect_size:** - r(25) = −0.83 (information weighting index × conformity index correlation) - ΔDIC_FM-SM = 10.4; ΔDIC_BM-SM = 1590.4 (model comparison) - Z = 3.35 (IFG positive correlation with information weighting index) - Z = 3.46 (MTG/parietal-temporal negative correlation with information weighting index)
- **learning_from:** Other (fictitious traders' decisions = social information) and self (private rating agency recommendation); source: other + self
- **learning_about:** World; probability that a stock is profitable (world state)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Social Model (SM): Evidence Model with 2 free parameters — one weight for social information (β_social for t=1 and t=2 combined) and one weight for private information (β_private for t=3). Y = Σ β_t × ln[p(e_t|good_W) / p(e_t|good_S)]
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** [   {"name": "Bayesian Model (BM)", "family": "Bayesian belief updating", "n_params": 0, "metric": "DIC"},   {"name": "Social Model (SM)", "family": "Bayesian belief updating (weighted)", "n_params": 2, "metric": "DIC"},   {"name": "Full Model (FM)", "family": "Bayesian belief updating (weighted)", "n_params": 4, "metric": "DIC"} ]
- **model_mb_mf:** Bayesian
- **model_params:** - β_social [S]: weight given to social information (trader I and II decisions combined); group-level posterior: M_social credibly < M_private - β_private: weight given to private information (personal recommendation) - (BM: all β = 1, β₀ = 0; FM additionally includes β₀ bias and separate β for each of three information stages) - Information weighting index = β_private / (β_private + β_social); majority > 0.50
- **social_param:** β_social [S] — weight assigned to socially inferred information (others' observed decisions); compared against β_private to derive the information weighting index reflecting individual tendency to over- or under-weight social vs. private evidence.
- **social_param_name:** β_social
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** DIC (Deviance Information Criterion); Bayes factors at individual level
- **how_model_fit:** individual-level-fit (Bayesian parameter estimation; see Supplementary Methods — details of estimation procedure referenced but supplement not accessible)
- **data_type_fit_to:** choice behavior (probability judgments / posterior probability estimates)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) — parametric regressors tracking belief updating magnitude (Bayesian posterior probability change) and log odds of probability judgments
- **contrast:** - General belief updating (social + private combined): parametric regressor of belief updating magnitude at t=2 and t=3 → fronto-parietal activation (Table 1) - Belief updating by social information (t=2 specific): left MTG/IPL activation - Belief updating by private information (t=3 specific): bilateral IFG/anterior insula, DLPFC/DMPFC, bilateral IPL, precuneus/PCC, dorsal striatum (Table 1) - Individual differences regression: information weighting index as covariate on private belief updating contrast → positive: IFG (45, 38, 10); negative: MTG/parietal-temporal (−51, −64, 22)
- **key_regions:** Belief updating by private information in bilateral IFG/anterior insula, DLPFC/DMPFC, bilateral IPL, precuneus/PCC, dorsal striatum; overweighting of private information positively associated with IFG/anterior insula activity and negatively associated with parietal-temporal cortex activity.
- **key_regions_abbrev:** dStr, striatum, mPFC, dmPFC, dlPFC, PCC, insula, AI, precuneus, IFG, parietal
- **coordinates_peak:** General effects of belief updating: - Superior temporal gyrus/inferior parietal cortex (R): 63, −49, 19 - Precuneus/posterior cingulate: 3, −61, 34 - Superior/middle frontal gyrus DLPFC (L): −15, 29, 52 - Superior temporal gyrus/inferior parietal cortex (L): −42, −61, 28 - Superior/middle frontal gyrus (R): 21, 26, 46 - Superior/medial frontal gyrus (L): −18, 53, 19  Belief updating by social information: - Middle temporal gyrus (L): −42, −58, 22  Belief updating by private information: - Superior/middle frontal gyrus DLPFC/DMPFC (R): 48, 32, 19 - Precuneus/posterior cingulate: 6, −58, 40 - Inferior frontal gyrus/anterior insula (R): 48, 41, −14 - Inferior parietal lobe (R): 33, −64, 40 - Inferior parietal lobe (L): −48, −64, 43 - Middle occipital gyrus (R): 27, −88, −5 - Middle temporal gyrus (R): 42, −52, −11 - Cerebellum (L): −33, −73, −38 - Inferior frontal gyrus/anterior insula (L): −33, 20, −2 - Middle/inferior frontal gyrus (L): −39, 41, −8 - Middle occipital gyrus (L): −36, −64, −11 - Parahippocampal gyrus (R): 21, −28, −11 - Dorsal striatum (R): 12, 14, 7  Individual differences (information weighting index): - Inferior frontal gyrus (R, positive): 45, 38, 10 - IFG/anterior insula (R, positive, p<.005): 39, 17, −5 - Middle temporal gyrus (L, negative): −51, −64, 22 - Midbrain (negative): −3, −10, −11 - Middle temporal gyrus (L, negative): −54, 2, −23 - Middle temporal gyrus (L, negative): −48, 11, −29 - Midbrain (negative): −6, −13, −8 - Middle temporal gyrus (L, negative): −63, −31, −8 - Middle temporal gyrus (L, negative): −51, 2, −29 - Precuneus (negative): −3, −52, 40 - Middle temporal gyrus (L, negative): −57, −31, −11
- **analysis_type:** whole-brain (uncorrected P < 0.001, minimum cluster size 20 voxels; ROI extraction for illustration via MarsBaR but primary analyses are whole-brain)  ---  ### QUALITY
- **analysis_type_clean:** whole-brain
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 27 (from initial 32; 5 excluded: 2 technical, 1 device error, 1 left-handed, 1 script error); ages 20–29, M = 22.4, SD = 2.0; 9 females. All fMRI.
- **population_category:** healthy adults
- **population_age_range:** 20–29
- **ecological_validity:** Low-moderate. Hypothetical stock trading scenario with fictitious traders (no real social interaction). Decisions of "other traders" were pre-programmed, not from real participants. Performance-contingent bonus was very small (mean ~4 CHF). Authors acknowledge the need to examine situations with real behavior of other people.
- **eligibility_flag:** 
- **concerns:** - Uncorrected thresholds throughout (P < 0.001 uncorrected, minimum 20 voxels) — no correction for multiple comparisons - Individual differences regression used even more liberal threshold (P < 0.005 uncorrected) for some results - Fictitious traders — no real social interaction - Small sample (N = 27) - Supplement referenced for model estimation details and additional fMRI results but supplement not accessible in this extraction - The "social information" is inferred from pre-programmed decisions, not genuine social agents
- **limitations_reported:** Further experiments are needed to explore this hypothesis [two-fold neural mechanism]"; "it appears necessary to examine situations in which social information is inferred from real behavior of other people in the future"; "in our task it is difficult to differentiate the neural effects related to belief updating and decision-making at the last stages of a trial"; "Additional studies will also help to generalize the observed mechanisms to different social environments
- **limitations_categorized:** limited ecological validity; confound between belief updating and decision-making; limited generalizability; small sample size; no correction for multiple comparisons
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** No
- **wc_score:** 5.5
- **wc_total:** 5.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `how_model_fit`: MEDIUM confidence — paper references "Supplementary Methods" for estimation details; main text says Bayesian estimation but specifics unavailable - `model_params` (fitted values): LOW confidence — exact posterior means for β_social and β_private not numerically reported in main text; only distributions shown in Figure 3 - `wc_guidelines` Rule 8: MEDIUM — behavioral consistency reported but no formal posterior predictive check
- **cannot_find:** - Exact fitted parameter values for β_social and β_private (shown graphically in Figure 3 posterior distributions but not reported as numerical point estimates in main text) - Supplementary Methods details (supplement not accessible — referenced for model estimation procedure) - Supplementary fMRI results (referenced in text but supplement not available)
- **other_notes:** Supplement not accessible — referenced repeatedly for model estimation details and additional fMRI results. The paper's "Evidence Model" is a modification of Hung & Plott (2001), using log-odds Bayesian framework with differential weighting parameters. The paradigm places the participant as the third decision-maker who can initiate or end an informational cascade. The social agents are fictitious (pre-programmed), which should be flagged for the review. The study is single-study (1 study).
- **re_extract_flag:** false (full main text accessible; supplement unavailable but main text extraction is complete)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_instructed
- rr_tax_mod_social_info_search
- spec_depth = parametric
- spec_locus = source
- spec_neural = dedicated
- spec_source = social
- tax_domain_A_influence_transmission
- tax_mod_instructed
- tax_mod_social_info_search
- tax_model_bayesian
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_social_weight
- tax_rr_primary_topic = informational_cascade
- tax_rr_secondary_topic = social_info_use
- tax_rr_topic_informational_cascade
- tax_rr_topic_social_info_use
- tax_social_nonsocial_comparison
- tax_topic_informational_cascade
- tax_topic_social_info_use
