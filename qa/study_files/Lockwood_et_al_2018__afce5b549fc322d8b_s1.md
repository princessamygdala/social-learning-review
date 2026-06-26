# Lockwood et al. (2018)

- **study_id:** `afce5b549fc322d8b_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lockwood, P. L., Wittmann, M. K., Apps, M. A. J., Klein-Flugge, M. C., Crockett, M. J., Humphreys, G. W., & Rushworth, M. F. S. (2018). Neural mechanisms for learning self and other ownership. *Nature Communications*, *9*, 4747. https://doi.org/10.1038/s41467-018-07231-9
- **citation_short:** Lockwood et al. (2018)
- **doi:** 10.1038/s41467-018-07231-9
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** ether, these studies suggest that the pro- controlling for previous stimuli associations; DepartmentofExperimentalPsychology,UniversityofOxford,OxfordOX13PH,UK; DepartmentofPsychology,YaleUniversity,NewHaven,CT06511,USA; CentreforIntegrativeNeuroimaging,Departmentof; ethertheybelongtothemselvesortoaclose; UniversityofOxford,Oxford,UK; mpiricallyhere; emails: patricia.lockwood@psy.ox.ac.uk
- **code_url:** 

## Computational level
- **study_focus:** Ownership learning -- how people acquire associative representations of object ownership for self, friends, and strangers, and the self-ownership bias in learning.
- **study_focus_short:** Ownership learning -- how people acquire associative representations of object
- **learning_mode_description:** - Learning mode: Learning from correct/incorrect feedback about picture-agent pairings to acquire ownership associations for self, friend, and stranger.   - Learning from:     - Source type (non-social): world       - Feedback (correct/incorrect) provided by the task environment     - Source content (non-social): outcome       - Binary correctness feedback on ownership assignment   - Learning about:     - Target type (social): self / other (friend) / other (stranger)     - Target content (social): state (ownership associations between agents and objects)
- **task_description:** Participants viewed abstract fractal images and learned by trial and error whether each fractal belonged to themselves, a named best friend, or a named stranger, receiving correct/incorrect feedback after each ownership assignment.
- **task_paradigm:** Categorization task
- **players:** Single agent (participant), multi-target (1 friend, 1 stranger)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Abstract fractal images, binary correct/incorrect feedback, agent labels (mine, friend's name, stranger's name)
- **method:** fMRI
- **method_full:** fMRI
- **main_result:** - Self-ownership bias in initial preferences: participants more likely to label pictures as "mine" with no prior information (F(2,76)=5.26, eta-squared=.12) - Faster reaction times for correct self-responses vs. friend and stranger (F(2,76)=23.72, eta-squared=.38) - Higher accuracy for self-ownership (F(2,76)=7.50, eta-squared=.17) - Self-bias in learning (stay/switch): F(2,76)=8.51, eta-squared=.18 - Confirmation bias in learning: F(1,38)=89.06, eta-squared=.70 - Higher learning rate for self (M=.47) than stranger (M=.34) (F(2,76)=3.14, eta-squared=.08) - vmPFC tracked OAS for self > stranger (SVC-FWE p<.05); vmPFC tracked OAS for all three agents (all ps<.008) - Correlation between self learning rate and vmPFC self-OAS response: r(39)=.41 - Correlation between self learning rate and vmPFC self-OPE response: r(39)=.38 - Bilateral ventral striatum signalled OPEs for all agents (FWE whole-brain p<.001) - ACCg specifically coded OPEs for strangers (FWE-SVC p<.02); ACCg tracked OAS for friend and stranger but not self
- **effect_size:** - Self-ownership initial bias: eta-squared=.12 - RT self-bias: eta-squared=.38 - Accuracy self-bias: eta-squared=.17 - Learning stay/switch self-bias: eta-squared=.18 - Confirmation bias: eta-squared=.70 - Learning rate agent effect: eta-squared=.08 - vmPFC self-OAS and self learning rate: r=.41 - vmPFC self-OPE and self learning rate: r=.38
- **learning_from:** World; correct/incorrect feedback on ownership assignment. Source: world.
- **learning_about:** Ownership associations between agents (self, friend, stranger) and objects. Target: self / other.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** cognitive_only

## Algorithmic level
- **winning_model:** Associative learning model (Rescorla-Wagner; 3 learning rates: alpha_self, alpha_friend, alpha_stranger; 3 temperature parameters: beta_self, beta_friend, beta_stranger; 6 params total)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Full model (3 LRs, 3 betas)", "family": "Rescorla-Wagner", "n_params": 6, "metric": "AIC = 14333"} - {"name": "Deterministic model", "family": "Deterministic/logical", "n_params": 1, "metric": "AIC = 15626"} - {"name": "Starting bias as free parameter", "family": "Rescorla-Wagner", "n_params": 8, "metric": "AIC = 14600"} - {"name": "Counterfactual model", "family": "Rescorla-Wagner + counterfactual", "n_params": 7, "metric": "AIC = 15218"} - {"name": "Beta only model (LR=1)", "family": "Rescorla-Wagner (fixed LR)", "n_params": 1, "metric": "AIC = 14706"} - {"name": "One beta and one learning rate", "family": "Rescorla-Wagner", "n_params": 2, "metric": "AIC = 14217"}  Note: The simpler 2-parameter model (model 6) had a slightly better AIC (14217 vs. 14333), but the authors favored the full 6-parameter model because it allowed examination of agent-specific learning rate differences and brain-behavior correlations. Both produced the same neuroimaging results.
- **model_mb_mf:** MF
- **model_params:** - alpha_self [S]: learning rate for self-ownership associations (M=.47, SD=.29) - alpha_friend [S]: learning rate for friend-ownership associations (M=.37, SD=.30) - alpha_stranger [S]: learning rate for stranger-ownership associations (M=.34, SD=.26) - beta_self: inverse temperature for self choices (no significant agent differences, F(2,76)=.21, p>.80) - beta_friend: inverse temperature for friend choices - beta_stranger: inverse temperature for stranger choices  Starting values: set to each participant's average tendency to select self, friend, or stranger on the first trial (not a free parameter).
- **social_param:** alpha_self, alpha_friend, alpha_stranger [S] -- separate learning rates for forming ownership associations with self, friend, and stranger agents. The self learning rate was significantly higher than the stranger learning rate (p=.017), reflecting a self-ownership bias in associative learning.
- **social_param_name:** alpha_self
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (Akaike Information Criterion), NLL (Negative Log Likelihood), likelihood ratio test vs. chance model
- **how_model_fit:** individual-level-fit (minimized negative log likelihood for each subject individually)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** model-based fMRI (parametric regressors) -- OAS and OPE from the computational model used as parametric modulators in the GLM
- **contrast:** - Conjunction: OAS for all agents (self AND friend AND stranger) at time of picture -- mPFC (areas 8/9, dmPFC), TPJ - Conjunction: OPE for all agents at time of outcome -- bilateral ventral striatum, area 8m, area 9 in dmPFC - Self OAS > Stranger OAS -- vmPFC (area 14m extending into 11m) - Stranger OAS > Self OAS -- ACCs (negative coding pattern for all agents, strongest for self) - Stranger OPE > Self OPE -- ACCg (area 24), posterior cingulate, ventral mid-insula - Stranger OPE (specific) -- ACCg - OAS friend+stranger (not self) -- ACCg; dorsal area 11m
- **key_regions:** Self-ownership bias in vmPFC (area 14m/11m) for OAS tracking; domain-general OPE in bilateral ventral striatum; other-specific OPE in ACCg (area 24) for strangers; ACCg also tracked OAS for friend and stranger but not self; ACCs showed negative OAS coding biased toward self; dmPFC (area 8/9) and TPJ tracked OAS for all agents; dorsal area 11m tracked OPE for friend and stranger.
- **key_regions_abbrev:** VS, striatum, vmPFC, mPFC, dmPFC, ACC, TPJ, AI
- **coordinates_peak:** - Left ventral striatum (OPE all agents): -14, 10, -8 - Right ventral striatum (OPE all agents): 16, 6, -12 - Superior frontal gyrus / area 8m (OPE all agents): -18, 30, 56 - dmPFC area 9 (OPE all agents): -6, 66, 16 - vmPFC area 14m/11m (self OAS > stranger OAS): -6, 28, -14 and 6, 22, -14 - ACCs (stranger OAS > self OAS; negative coding): -8, 12, 48 - ACCg area 24 (stranger OPE): 10, 38, 6 and 6, 30, 28 - Dorsal area 11m (stranger OPE > self OPE): 10, 50, -6 - Posterior cingulate (stranger OPE): -10, -26, 32 - Ventral mid-insula BA13 (stranger OPE): -36, 8, -12  Note: Supplementary Table 2 (conjunction coordinates for OAS and OPE) was not extractable from the text conversion of the supplement (table formatting lost). The coordinates above are all from the main text.
- **analysis_type:** both (whole-brain FWE-corrected and small-volume correction using anatomical mPFC mask)  ---  ### QUALITY
- **analysis_type_clean:** both
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N=39 (1 excluded from original 40 due to neurological abnormalities identified during scanning; 21 females, age 19-34 years, right-handed healthy adults)
- **population_category:** healthy adults
- **population_age_range:** 19–34
- **ecological_validity:** Uses abstract fractal images rather than real-world objects, limiting ecological validity. Ownership is non-material (no reward or real possession involved). The "minimal ownership" paradigm controls for prior associations but is far from naturalistic ownership acquisition. The stranger is a name rather than a real person. Deterministic rather than probabilistic task structure.
- **eligibility_flag:** 
- **concerns:** The simpler 2-parameter model (1 LR, 1 beta) actually had a slightly better AIC (14217 vs. 14333) than the favored 6-parameter model. Authors justified using the more complex model because it allowed testing of agent-specific learning rate differences and brain-behavior correlations, but this is somewhat post-hoc. No parameter recovery or model recovery analyses reported. Group-average learning rates used for fMRI parametric regressors rather than individual-level estimates. Deterministic task structure may not generalize to probabilistic real-world ownership learning.
- **limitations_reported:** Authors acknowledge that the paradigm uses abstract fractals rather than real material objects; suggest future studies should examine effects on memory and willingness to pay; note that the task is deterministic rather than probabilistic; acknowledge that the spatial gradient analysis for self-other processing in mPFC was not significant; note that further studies should compare real ownership of take-home objects.
- **limitations_categorized:** limited ecological validity; task simplicity; no parameter recovery; no model recovery; deterministic task structure; abstract stimuli
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
- **wc_rule10:** Yes
- **wc_score:** 6.5
- **wc_total:** 6.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_comparison_metric: MEDIUM -- Authors used the 6-parameter model despite the 2-parameter model having slightly better AIC; justification is reasonable but worth noting - coordinates_peak: MEDIUM -- Supplementary Table 2 coordinates could not be extracted from text conversion; all coordinates reported are from the main text only - wc_guidelines rule 3 (simulate): HIGH confidence that No -- no simulation mentioned anywhere in text or supplement - wc_guidelines rule 5 (parameter recovery): HIGH confidence that No - wc_guidelines rule 6 (model recovery): HIGH confidence that No
- **cannot_find:** - Supplementary Table 2 actual coordinate data (table formatting lost in text conversion; described as "conjunction analyses showing overlap in neural responses to OAS and OPE" but actual values not extractable) - Exact beta (inverse temperature) parameter values (means/SDs not reported, only noted no significant difference across agents)
- **other_notes:** Patricia Lockwood is the first author of this paper. The paper uses a "minimal ownership" paradigm inspired by social psychology's minimal groups paradigm. The key theoretical contribution is showing that vmPFC and ACCs are biased toward self-relevant ownership learning but not exclusively self-related, while ACCg shows relative specialization for learning about others' ownership. Data and unthresholded statistical maps are publicly available.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_neural = dedicated
- spec_target = social
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = ownership
- tax_rr_secondary_topic = self_other_boundary
- tax_rr_topic_ownership
- tax_rr_topic_self_other_boundary
- tax_topic_ownership
- tax_topic_self_other_boundary
