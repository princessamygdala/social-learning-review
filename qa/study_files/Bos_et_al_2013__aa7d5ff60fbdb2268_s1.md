# Bos et al. (2013)

- **study_id:** `aa7d5ff60fbdb2268_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** van den Bos, W., Talwar, A., & McClure, S. M. (2013). Neural correlates of reinforcement learning and social preferences in competitive bidding. *The Journal of Neuroscience*, *33*(5), 2137–2146. https://doi.org/10.1523/JNEUROSCI.3095-12.2013
- **citation_short:** Bos et al. (2013)
- **doi:** 10.1523/JNEUROSCI.3095-12.2013
- **publication_type:** peer-reviewed journal
- **year:** 2013.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ethatbiddingiswellcharacterizedbyreinforcementlearningwithbiasedrewardrepresentationsdependentonsocialpreferences; ethananitemisworth, erencemodels,wearguethatpeoplederiveutilityfromwinning; etherlandsOrganizationforScientificResearch(NWO)RubiconPostdoctoralFel-; ethankDavidEffelsbergandPhilippGolkafortheirhelpwiththedatacollection; DepartmentofPsychology,StanfordUniversity,Stanford,California94305; ethatincompetitivedecisions,socialpreferencesin- outcome; ether, these findings support a novel brain-based ac-; etheoryprescribes,resultinginlossesorsuboptimal; emails: wvdbos@stanford.edu
- **code_url:** 

## Computational level
- **study_focus:** Competition learning / social preference learning in auctions — how social preferences (utility of winning/disutility of losing) interact with reinforcement learning to bias competitive bidding strategies over time.
- **study_focus_short:** Competition learning / social preference learning in auctions
- **learning_mode_description:** - Learning mode: Learning from monetary and social outcomes of competitive auctions about optimal bidding strategy   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (monetary revenue from auction)     - Source type (social): other (competing bidders)       - Source content (social): outcome (winning/losing relative to others)   - Learning about:     - Target type (non-social): world (optimal bid strategy / bid factor)       - Target content (non-social): action/policy (bidding strategy)
- **task_description:** Groups of five participants simultaneously played a sealed-bid common value auction over 40 rounds. In each round, participants received a private estimate of an item's value and submitted a bid; the highest bidder won and learned the true value and their revenue (true value minus bid), while losers received zero monetary outcome.
- **task_paradigm:** Auction task
- **players:** Multi-agent (5 simultaneous players per group), competitive
- **n_players:** 
- **partner_type:** human (live)
- **stimuli:** Novel flower images (auction items), monetary unit values, personal value estimates with error terms, winner identification photos
- **method:** fMRI / hyperscanning / online / behavioural
- **method_full:** fMRI (hyperscanning — 5 simultaneous scanners) + behavioural (separate single-player online experiment)
- **main_result:** - Main Results:   - RL model with social preference parameters fit behavior significantly better than models without social parameters (BIC full model = 5185.4 vs. no social params = 7920.0)   - Prediction errors correlated with activity in striatum (caudate head) and VMPFC (Z = 6.45 and Z = 6.37, respectively; p < 0.05 FWE)   - Win > not-win contrast: right TPJ activation (Z = 5.05, p < 0.05 FWE)   - Not-win > win contrast: bilateral anterior insula (Z = 5.74 left, Z = 5.78 right) and dACC (Z = 5.95; p < 0.05 FWE)   - Individual σ_win correlated with TPJ activity during winning (r = 0.55, p < 0.002)   - Individual σ_loss correlated with AI activity during not-winning (r = 0.52, p < 0.01)   - TPJ-VMPFC connectivity after winning correlated with σ_win (r = 0.61, p < 0.003)   - AI-VMPFC connectivity after not-winning correlated with σ_loss (r = 0.45, p < 0.008)   - TPJ-VMPFC and AI-VMPFC connectivity predicted overbidding (mean β; r = 0.59, p < 0.005 and r = 0.51, p < 0.01)   - In behavioral study: σ_win and σ_loss correlated with self-reported social (not monetary) motivations (Spearman's ρ = 0.37, p < 0.02 and ρ = −0.46, p < 0.003)
- **effect_size:** See inline above. Key: r = 0.61 (TPJ-VMPFC connectivity ~ σ_win); r = 0.59 (TPJ-VMPFC connectivity ~ overbidding); Z = 6.45 (striatum PE); Z = 5.05 (TPJ win > not-win)
- **learning_from:** Self and others; monetary outcome (revenue) and social outcome (winning/losing the auction relative to competitors)
- **learning_about:** World/self; optimal bidding strategy (bid factor) in competitive auction  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RL with social utility: V(β) updated via PE; utility U = (x₀ − bᵢ + σ_win) if winner, (−σ_loss) otherwise; softmax decision with temperature m; generalized learning rate α scaled by distance from current β. 4 params: σ_win, σ_loss, α, m.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Full RL model (σ_win + σ_loss)", "family": "RL", "n_params": 4, "metric": "AIC = 5181.0, BIC = 5185.4"},   {"name": "RL no σ_win", "family": "RL", "n_params": 3, "metric": "AIC = 5531.1, BIC = 5534.5"},   {"name": "RL no σ_loss", "family": "RL", "n_params": 3, "metric": "AIC = 7560.9, BIC = 7564.1"},   {"name": "RL no σ_win or σ_loss", "family": "RL", "n_params": 2, "metric": "AIC = 7917.9, BIC = 7920.0"} ]
- **model_mb_mf:** MF
- **model_params:** - σ_win [S]: intrinsic utility of winning the auction independent of monetary outcome; group mean = 2.40, SE = 0.35 - σ_loss [S]: intrinsic disutility of not winning the auction; group mean = 0.49, SE = 0.11 - α: learning rate; group estimate = 0.138 - m: softmax temperature (inverse); group estimate = 10
- **social_param:** σ_win — intrinsic utility added to reward when winning the auction (social preference for winning); σ_loss — intrinsic negative utility when losing the auction (social aversion to losing)
- **social_param_name:** σ_win
- **social_param_value:** 2.40
- **social_param_sd:** 0.35
- **social_param_range:** 
- **model_comparison_metric:** AIC, BIC (Bayesian model comparison)
- **how_model_fit:** group-level-fit (simplex optimization minimizing sum-squared error between average model simulations over 10,000 runs and average subject behavior; then individual σ_win and σ_loss estimated with group α and m fixed)
- **data_type_fit_to:** choice behavior (bid factors across 40 rounds)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) + PPI (psychophysiological interaction connectivity analysis)
- **contrast:** - PE regressor (trial-by-trial prediction errors from RL model) → striatum, VMPFC (Z = 6.45, 6.37; p < 0.05 FWE) - Win > not-win → right TPJ (Z = 5.05; p < 0.05 FWE) - Not-win > win → bilateral AI (Z = 5.74, 5.78), dACC/pre-SMA (Z = 5.95; p < 0.05 FWE) - PPI: TPJ-VMPFC connectivity (win > not-win; t(21) = 3.11, p < 0.01) - PPI: AI-VMPFC connectivity (not-win > win; t(21) = −2.94, p < 0.01) - PPI: TPJ-Str connectivity (win > not-win; t(21) = 2.83, p < 0.02) - PPI: AI-Str connectivity (not-win > win; t(21) = 2.744, p < 0.03)
- **key_regions:** Prediction error signals in ventral striatum (caudate head) and VMPFC; social value of winning in right TPJ; social cost of losing in bilateral anterior insula and dACC; social value signals integrated in VMPFC and striatum via PPI connectivity with TPJ (winning) and AI (losing).
- **key_regions_abbrev:** VS, caudate, striatum, vmPFC, mPFC, dACC, ACC, TPJ, insula, AI
- **coordinates_peak:** VMPFC: −3, 54, −12 Ventral striatum (caudate head): −6, 3, 0 Right TPJ: 54, −57, 33 Posterior cingulate cortex: 4, −60, 35 Left anterior insula: −30, 27, 0 Right anterior insula: 45, 18, −9 dACC: 3, 18, 48 Right postcentral gyrus: 59, −24, 44
- **analysis_type:** both (whole-brain analysis for main contrasts at p < 0.05 FWE, k > 10; followed by ROI analyses using MarsBar for TPJ/AI connectivity and parameter estimate extraction)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** Study 1 (fMRI): N = 25 (22 usable for imaging; 11 male, 11 female; mean age 28.56, SD = 7.28). Study 2 (behavioral): N = 47 (40 usable after exclusions; all male; mean age 23.4, SD = 7.28).
- **population_category:** healthy adults
- **population_age_range:** M=28.56
- **ecological_validity:** Lab-based auction paradigm with real monetary incentives and real opponents (hyperscanning). More ecologically valid than typical economic games due to real competitive multi-player interaction. However, abstract goods (flower images) with known value distributions are not representative of real-world auction contexts. Behavioral study used simulated opponents (unknown to participants).
- **eligibility_flag:** 
- **concerns:** Group-level model fitting (α and m fixed at group level, only σ_win and σ_loss estimated individually) may mask important individual differences in learning rate. The behavioral validation study (Study 2) used only male participants. No parameter recovery or model recovery analyses reported. The text extraction from PDF has significant character-level corruption (garbled text in places), but key data were recoverable.
- **limitations_reported:** We have only begun to understand what is bound to be a number of complex factors that determine the impact of social values on competitive economic decisions"; TPJ activity is not exclusively related to social cognition — also associated with reorientation of attention to salient stimuli; anterior insula activation may reflect both socio-emotional processing and need for strategy change (not purely social); individual differences in depth of processing (theory of mind) may play a role in different auction types but were not modeled here.
- **limitations_categorized:** limited ecological validity; confound of social vs. attentional TPJ function; no parameter recovery; no model recovery; group-level fitting limitations; single gender in behavioral study; task simplicity
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
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - wc_3 (MEDIUM): Simulations were run to fit data and demonstrate model behavior, but it is unclear whether simulations were conducted before data collection for experimental design purposes - wc_8 (MEDIUM): Visual comparison of model-predicted and observed bid factors shown, plus likelihood ratio test; classified as Partial rather than full posterior predictive check - ecological_validity (MEDIUM): Judgment based on task features described in the paper
- **cannot_find:** No supplement available to check for additional model details or coordinates. No data/code sharing statement found.
- **other_notes:** This paper contains two studies — Study 1 (fMRI, N=25) and Study 2 (behavioral replication/validation, N=47). However, Study 2 is an adjunct validation experiment using simulated opponents rather than an independent study with its own learning model — it reuses the same model with the same group-level parameters. I have treated this as a single-study paper because the behavioral experiment serves as validation of the same model and does not introduce new computational elements. The paper is an early example of hyperscanning (5 simultaneous fMRI scans) applied to competitive auction behavior. The .txt extraction has significant OCR/conversion artifacts but all critical data points were recoverable. Supplement not found — no supplement file with matching name exists in the papers folder.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = parametric
- spec_neural = dedicated
- spec_source = partly
- spec_target = partly
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_social_bonus
- tax_rr_primary_topic = competition
- tax_rr_topic_competition
- tax_topic_competition
