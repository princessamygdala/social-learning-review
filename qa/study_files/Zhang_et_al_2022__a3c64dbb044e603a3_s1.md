# Zhang et al. (2022)

- **study_id:** `a3c64dbb044e603a3_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Zhang, L., Kandil, F. I., Zhao, K., Fu, X., Lamm, C., Hilgetag, C. C., & Glascher, J. (2022). A causal role of the human left temporoparietal junction in computing social influence during goal-directed learning. *bioRxiv*. https://doi.org/10.1101/2022.06.13.495824
- **citation_short:** Zhang et al. (2022)
- **doi:** 10.1101/2022.06.13.495824
- **publication_type:** preprint
- **year:** 2022.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** Institute of Systems Neuroscience, University Medical Center Hamburg-Eppendorf, Hamburg,; ethods in Psychology, Faculty of Psychology, University of Vienna, Vienna, 1010, Austria; Department of Psychology, University of Chinese Academy of Sciences, Beijing, 100049,; Department of Neurology, Charité – Universitätsmedizin Berlin, Berlin, 13353, Germany; Institute of Computational Neuroscience, University Medical Center Hamburg-Eppendorf,; ether left or right TPJ was casually involved in representing dissenting social; ether left or right TPJ (with vertex as control) is causally involved in how;
- **code_url:** https://github.com/lei-zhang/SIT_TMS

## Computational level
- **study_focus:** Social influence learning / social influence on goal-directed learning
- **study_focus_short:** Social influence learning / social influence on goal-directed learning
- **learning_mode_description:** - Learning mode: Learning from others' dissenting choices to adjust one's own choice in a probabilistic reversal learning task, while also integrating vicarious value estimates from observing others' choice histories.   - Learning from:     - Source type (social): group (4 computer algorithms simulating other players)     - Source content (social): action/policy (others' choices, specifically dissenting choices)   - Learning about:     - Target type (non-social): world (which option is more rewarding)     - Target content (non-social): outcome (reward contingencies via value updating)
- **task_description:** Participants made an initial choice between two abstract fractals in a probabilistic reversal learning task, then observed the choices of four simulated intelligent computer algorithms, and were allowed to adjust their final choice before receiving a binary reward outcome. The task included multiple reward contingency reversals (every 8-12 trials) to maintain uncertainty and incentivize learning from others.
- **task_paradigm:** Reversal learning
- **players:** Single agent (participant), multi-target (4 computer algorithms simulating intelligent co-players)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Abstract fractals (3 pairs, counterbalanced), binary reward/punishment outcomes, human face icons representing computer algorithms
- **method:** TMS / behavioural
- **method_full:** TMS (cTBS) / behavioural
- **main_result:** - Main Results:   - Stimulation x consensus interaction on choice switch probability (F(4,180) = 3.90, eta-squared not reported; significant interaction)   - Left TPJ disruption reduced choice switch probability relative to right TPJ in 4:0 consensus condition (t(64) = 3.587, Tukey corrected)   - Left TPJ disruption reduced beta(N_against) relative to right TPJ (t(60) = 4.407, Tukey corrected) and vertex (t(60) = 2.626, Tukey corrected)   - No difference across stimulation sites for beta(V_other) (F(1,30) = 3.718; BF10 = 0.106, supporting null)   - Left TPJ disruption weakened predictability of beta(N_against) on switch probability (b = 0.063 vs vertex b = 0.109 vs rTPJ b = 0.084; Wald test lTPJ vs vertex: Bonferroni-corrected significant)   - Left TPJ stimulation increased RT in 4:0 consensus condition (beta_lTPJ x consensus_4:0 = 0.197)
- **effect_size:** - Main Results:   - Stimulation x consensus interaction on choice switch probability (F(4,180) = 3.90, eta-squared not reported; significant interaction)   - Left TPJ disruption reduced choice switch probability relative to right TPJ in 4:0 consensus condition (t(64) = 3.587, Tukey corrected)   - Left TPJ disruption reduced beta(N_against) relative to right TPJ (t(60) = 4.407, Tukey corrected) and vertex (t(60) = 2.626, Tukey corrected)   - No difference across stimulation sites for beta(V_other) (F(1,30) = 3.718; BF10 = 0.106, supporting null)   - Left TPJ disruption weakened predictability of beta(N_against) on switch probability (b = 0.063 vs vertex b = 0.109 vs rTPJ b = 0.084; Wald test lTPJ vs vertex: Bonferroni-corrected significant)   - Left TPJ stimulation increased RT in 4:0 consensus condition (beta_lTPJ x consensus_4:0 = 0.197)
- **learning_from:** Group (4 simulated co-players); others' choices (dissenting social information) and others' choice histories (observational learning)
- **learning_about:** World; optimal choice in a probabilistic reversal learning environment  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** M4: Fictitious RL (direct learning) + others' action preference (social learning) + social influence for choice adjustment. 6 params per condition: alpha (learning rate), beta(V_self), beta(V_other), beta(bias), beta(V_chosen - V_unchosen), beta(N_against)
- **model_family:** Bayesian
- **model_class:** PE learning
- **all_models_tested:** - M1: Fictitious RL (non-social baseline), 4 params, LOOIC delta = 283, weight = 0 - M2: M1 + social influence only, 5 params, LOOIC delta = 117, weight = 0 - M3: M2 + others' RL update (4 independent RL agents for others), 8 params, LOOIC delta = 100, weight = 0 - M4 (winning): M2 + others' action preference, 6 params, LOOIC delta = 0 (reference), weight = 0.811 - M5: M2 + others' current reward, 6 params, LOOIC delta = 35, weight = 0.189 - M6: M2 + others' cumulative reward, 7 params, LOOIC delta = 80, weight = 0
- **model_mb_mf:** MF (model-free; fictitious update RL with no explicit model of environment transitions)
- **model_params:** - alpha: learning rate for fictitious RL update (lTPJ: 0.25 [0.15, 0.38]; Vertex: 0.30 [0.20, 0.41]; rTPJ: 0.23 [0.12, 0.33]) - beta(V_self): weight for direct learning values (lTPJ: 1.85; Vertex: 1.73; rTPJ: 1.92) - beta(V_other) [S]: weight for social learning values (lTPJ: 0.45; Vertex: 0.43; rTPJ: 0.50) - beta(bias): switching bias/intercept (lTPJ: -2.06; Vertex: -2.17; rTPJ: -2.49) - beta(V_chosen - V_unchosen): value difference weight for switching (lTPJ: -0.65; Vertex: -0.56; rTPJ: -0.76) - beta(N_against) [S]: social influence weight for dissenting choices (lTPJ: 0.87; Vertex: 1.01; rTPJ: 1.50)
- **social_param:** - beta(N_against): degree to which dissenting social information (number of others choosing opposite option) influences choice switching. KEY parameter: reduced by left TPJ disruption. - beta(V_other): weight of vicarious value (from others' action preference) integrated into own valuation. NOT affected by TPJ disruption.
- **social_param_name:** beta
- **social_param_value:** 0.45
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** LOOIC (Leave-One-Out Information Criterion) + Bayesian model averaging with Bayesian bootstrap (model weights)
- **how_model_fit:** Individual-level fit via hierarchical Bayesian analysis (HBA using Stan/HMC with within-subject effect coding)
- **data_type_fit_to:** Choice behavior (Choice 1: which option selected; Choice 2: switch/stay)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none (TMS study; no neuroimaging conducted in this study)
- **contrast:** N/A (no neuroimaging; TMS stimulation sites were based on coordinates from prior fMRI study Zhang & Glascher, 2020)
- **key_regions:** Left TPJ causally involved in computing social influence during choice adjustment; right TPJ stimulation had no effect. Stimulation targets: left TPJ (MNI: -48, -62, 30), right TPJ (MNI: 50, -60, 34), vertex (control).
- **key_regions_abbrev:** TPJ
- **coordinates_peak:** - Left TPJ (stimulation target from prior study): -48, -62, 30 - Right TPJ (stimulation target from prior study): 50, -60, 34  Note: These are TMS stimulation targets derived from a previous fMRI study (Zhang & Glascher, 2020), not activation peaks from the current study.
- **analysis_type:** N/A (no neuroimaging in current study)  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** True
- **has_neural:** True

## Quality
- **sample_size:** N = 31 (17 females); 40 recruited, 9 excluded (1 prior participation, 1 low motor threshold, 3 technical failures, 1 no choice adjustment, 4 excessive missed responses). Within-subject design: each participant underwent all 3 cTBS conditions.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Limited. Participants interacted with computer algorithms (not real humans), presented with human face icons. Abstract fractals rather than naturalistic stimuli. However, algorithms were simulated from a validated computational model of real human behavior, and participants were truthfully informed they were algorithms (no deception).
- **eligibility_flag:** 
- **concerns:** - The "social agents" are computer algorithms, not real humans (though participants were informed of this). This may limit generalizability to genuine social influence. - This is a preprint (bioRxiv, June 2022) and has not been peer-reviewed. - No parameter recovery or model recovery reported. - Effect sizes (Cohen's d, eta-squared) not consistently reported for key contrasts; F-statistics and t-values given but standardized effect sizes often missing. - The study references a prior fMRI study (Zhang & Glascher, 2020) extensively; the current study is a TMS follow-up testing causality.
- **limitations_reported:** Authors acknowledge: potential attentional confound of TPJ stimulation (TPJ involved in dorsal attention network), though they argue against this based on stimulation site selection from mentalizing maps, spatial separability of attention vs ToM regions, and non-zero V_other across conditions; reduced connectivity between left TPJ and vmPFC/ACC is speculative and requires future combined TMS-fMRI experiments; the study did not involve real human co-players.
- **limitations_categorized:** Potential attentional confound; speculative connectivity interpretation; limited ecological validity (computer algorithms vs. real humans); no combined TMS-fMRI validation
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
- **wc_rule10:** Yes
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** unclear
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM — F-values and t-values reported but standardized effect sizes (Cohen's d, eta-squared) not consistently provided - publication_type: HIGH — clearly a bioRxiv preprint; should check if subsequently published in a peer-reviewed journal - coordinates_peak: MEDIUM — coordinates are TMS stimulation targets from a prior study, not activation peaks from the current study - wc_3 (simulate): MEDIUM — algorithms were simulated from prior model but no dedicated simulation study for current model set
- **cannot_find:** - Standardized effect sizes (Cohen's d, eta-squared) for main behavioral and computational effects - Age range of participants - Whether the preprint was subsequently published in a peer-reviewed journal - Formal posterior predictive checks
- **other_notes:** - This study is a direct TMS follow-up to Zhang & Glascher (2020, Science Advances), which established the fMRI correlational findings. The two papers share the same task paradigm but different samples and methods (fMRI vs. TMS). - The "social agents" being computer algorithms is explicitly disclosed to participants (no deception), which is noteworthy for social learning classification. - The within-subject design with effect coding in the hierarchical Bayesian framework is methodologically sophisticated and accounts for interdependencies across stimulation conditions. - Model M4 uses a beta cumulative distribution function at 0.5 to track others' action preferences over the last 3 trials — a relatively unique approach compared to standard RL-based observational learning models.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- rr_tax_mod_vicarious_outcome
- spec_depth = parametric
- spec_locus = source+target
- spec_neural = dedicated
- spec_source = social
- tax_domain_A_influence_transmission
- tax_mod_action_observation
- tax_mod_experiential
- tax_mod_vicarious_outcome
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_PE_signal
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_topic_social_info_use
- tax_topic_social_info_use
