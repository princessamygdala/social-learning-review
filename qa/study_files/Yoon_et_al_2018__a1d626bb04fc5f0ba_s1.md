# Yoon et al. (2018)

- **study_id:** `a1d626bb04fc5f0ba_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Yoon, E. J., MacDonald, K., Asaba, M., Gweon, H., & Frank, M. C. (2018). Balancing informational and social goals in active learning. *Proceedings of the Annual Meeting of the Cognitive Science Society, 40*(0). https://escholarship.org/uc/item/08d6d2q6
- **citation_short:** Yoon et al. (2018)
- **doi:** No DOI provided; permalink: https://escholarship.org/uc/item/08d6d2q6
- **publication_type:** conference proceedings (peer-reviewed)
- **year:** 2018.0
- **field_of_study:** Cognitive science
- **affiliations_raw:** ethenewrecipethatmightresultinamorede- tiallyrisksnoimmediateeffect(neithersoundnorlightturn-; etheideathatsocialfactorsshapethe learning the toy’s causal mechanism; mpiricalworkineducation(Grabinger&Dunlap,1995)and; DepartmentofPsychology,StanfordUniversity; ethingworks)butalsosocialgoals(e; University of California; mpirical re-
- **code_url:** https://github.com/kemacdonald/soc-info

## Computational level
- **study_focus:** Social influence on active learning -- how social context (presence of an observer/boss) and social goals (self-presentation, performance) shape information-seeking behavior in a causal learning task.
- **study_focus_short:** Social influence on active learning -- how social context (presence of an
- **learning_mode_description:** - Learning mode: Learning about a toy's causal mechanism from one's own actions, modulated by social goals (self-presentation to an observer)   - Learning from:     - Source type (non-social): self     - Source content (non-social): outcome (action-effect contingency on a toy)   - Learning about:     - Target type (non-social): world (toy's causal mechanism)     - Target content (non-social): state (causal structure of the toy)  Note: The social component here is not in what is learned FROM or ABOUT, but in how goal weights are modulated by social context. The learning itself is non-social (causal learning about a toy). The social dimension enters through goal trade-offs (presentation utility requires reasoning about an observer's inference about competence).  ---  ### 4. COMPUTATIONAL PROBLEM  How does a learner balance informational goals (learning a toy's causal structure via information gain) against social goals (appearing competent to an observer) when selecting actions? This is an evaluation/action-goal selection problem: the agent must select actions that optimize a weighted combination of learning utility (information gain), performance utility (immediate reward), and presentation utility (inferred competence by an observer).  ---  ### 5. RESULTS WITH EFFECT SIZES
- **task_description:** Participants are presented with a toy with an ambiguous causal mechanism. They choose one action: a single action (informative but risky -- might produce no effect) or both actions simultaneously (immediately rewarding but uninformative). Social context is manipulated by the presence/absence of a boss observer and by goal instructions (learning, performance, presentation, no-goal).
- **task_paradigm:** Pedagogical learning
- **players:** 
- **n_players:** 
- **partner_type:** none
- **stimuli:** 
- **method:** online / behavioural
- **method_full:** Behavioural (online, Amazon Mechanical Turk)
- **main_result:** 
- **effect_size:** 
- **learning_from:** 
- **learning_about:** 
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Bayesian utility-theoretic model combining three utility functions:  U(a, o) = phi_learn * U_learn(a) + phi_perf * U_perf(a) + delta_o * phi_pres * U_pres(a)  Where: - U_learn(a) is based on expected information gain (OED/Shannon entropy reduction) - U_perf(a) = P_L(m|a), the likelihood of an immediate effect - U_pres(a) = P_O(m|a), the observer's estimate of effect likelihood (competence inference) - Action selection: P_L(a|o) proportional to exp(lambda * E[U_t(a,o)])
- **model_family:** Bayesian
- **model_class:** Utility maximization
- **all_models_tested:** 
- **model_mb_mf:** N/A (not RL; Bayesian utility-theoretic)  ---  ### 7. ALL MODELS TESTED  Only one model was tested (the Bayesian utility-theoretic model described above). No alternative/competing models were compared.  [{"name": "Bayesian social-active learning model", "family": "Bayesian utility-theoretic / OED", "n_params": 4, "metric": "BDA posterior fit"}]  ---  ### 8. MODEL COMPARISON
- **model_params:** - phi_learn: weight on learning utility (inferred per condition via BDA) - phi_perf: weight on performance utility (inferred per condition via BDA) - phi_pres [S]: weight on presentation utility -- social parameter, only active when observer present (inferred per condition via BDA) - lambda: optimality/softmax temperature parameter (MAP = 4.79, 95% HDI [3.96, 6.2]) - delta_o: indicator for observer presence (fixed, not fitted)
- **social_param:** phi_pres -- weight on self-presentation goal; captures how much the learner values appearing competent to the observer. Only active when an observer is present.
- **social_param_name:** phi_pres
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** No formal model comparison (single model). Fit assessed via Bayesian data analysis (MCMC posterior inference) and r-squared of predicted vs. observed action proportions.
- **how_model_fit:** Group-level fit via Bayesian data analytic techniques (MCMC, 4 chains x 100,000 iterations, 50,000 burn-in). Uninformative priors: phi ~ Unif(0,1), lambda ~ Unif(0,10).
- **data_type_fit_to:** Choice behavior (action selections)  ---  ### 9. NEUROIMAGING  None. No neuroimaging data.

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** 
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** - Exp 1: N = 189 (after exclusion of 7; 45-51 per condition; recruited 196) - Exp 2: N = 325 (after exclusion; 42-51 per condition; recruited 347)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate. Online one-shot decision task using a hypothetical toy scenario. Participants imagine a social context (boss present) rather than experiencing real social pressure. Single action choice rather than sequential learning. Authors acknowledge limitations: no differentiation between performance and presentation goals in the action space; limited to one social context type (boss); single action choice rather than sequential decision-making.  ---  ### 12. ELIGIBILITY FLAG
- **eligibility_flag:** 
- **concerns:** - Only one model tested -- no competing models compared, making it impossible to assess whether the specific utility decomposition is necessary vs. simpler alternatives. - One-shot paradigm limits generalizability to actual learning dynamics over time. - Social context is imagined (vignette-based), not experienced directly. - Performance and presentation goals are conflated in the action space -- both are satisfied by the "both actions" choice. - Conference proceedings paper (6 pages) -- limited detail on methods and model specification. - No supplement available.  ---  ### 14. WILSON & COLLINS CHECKLIST  1. **Design a good experiment:** Yes -- task clearly engages the targeted process (active learning with social goal trade-offs) 2. **Design good models:** No -- only one model tested; no competing hypotheses 3. **Simulate, simulate, simulate:** No -- no simulation of the model before fitting described 4. **Fit the parameters:** Yes -- Bayesian inference via MCMC 5. **Check parameter recovery:** No -- not reported 6. **Check model recovery:** No -- only one model, no confusion matrix 7. **Fit real data and compare models:** No -- only one model tested 8. **Validate the winning model:** Partial -- r-squared reported (0.9) but no formal posterior predictive checks 9. **Analyze the winning model:** Yes -- inferred phi values analyzed per condition 10. **Report results transparently:** Yes -- data, model, and analysis code shared on GitHub (https://github.com/kemacdonald/soc-info)
- **limitations_reported:** - Did not differentiate between performance and presentation goals, as "both" action satisfies both goals in this task; enriching the action space could tease these apart - Used a particular social context (boss presence); model could be extended to other observer types (e.g., teacher) - Limited to single action choice; real-world learning involves sequential decision-making - Limited ecological validity
- **limitations_categorized:** Task simplicity; limited ecological validity; limited generalizability; no sequential learning  ---  ### FLAGGED FIELDS  - `eligibility_flag`: MEDIUM confidence -- borderline one-shot vs. learning-over-time - `doi`: LOW confidence -- no DOI found, only escholarship permalink - `model_comparison_metric`: N/A -- only one model tested (flagged in concerns) - `all_models_tested`: only 1 model -- WC rules 2, 6, 7 automatically scored No - `effect_size`: Bayesian HDIs reported rather than traditional effect sizes (Cohen's d, etc.); beta coefficients from Bayesian logistic regression reported  ### CANNOT FIND  - DOI (only permalink available) - Alternative/competing models - Simulation results for model - Parameter recovery analysis - Exact prior specifications beyond Unif(0,1) and Unif(0,10) - Age range of participants  ### OTHER NOTES  - This is a CogSci conference proceedings paper (6 pages), not a full journal article. Details are necessarily abbreviated. - The paper is a "first step" toward integrating active learning and social reasoning -- explicitly described as preliminary work. - The model draws on Optimal Experiment Design (OED) and Rational Speech Act (RSA) frameworks. - Code and data publicly available at https://github.com/kemacdonald/soc-info - Two experiments reported -- but both use the same model and paradigm (Exp 2 extends Exp 1 with social context manipulation). These should be treated as a single study with two experiments for the review, as the computational model is the same across both.  ### SELF-CRITIQUE  - Re-checked learning mode: The core learning is non-social (causal mechanism of a toy), but the decision-making process is socially modulated. The social parameter (phi_pres) captures social influence on action selection, not on the learning process itself. This is an important distinction for the review taxonomy. - Re-checked eligibility: The one-shot nature is genuinely borderline. The model includes Bayesian updating (learning), but the behavioral data are from a single decision point. Flagged appropriately. - Verified r-squared = 0.9 is stated in the text (line 364). - Confirmed preregistration is stated (line 203-204).
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 4.5
- **wc_total:** 4.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_social_info_search
- spec_depth = parametric
- spec_locus = source+target+context
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_social_info_search
- tax_model_bayesian
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = pedagogical_reasoning
- tax_rr_topic_pedagogical_reasoning
- tax_rr_topic_social_info_use
- tax_topic_pedagogical_reasoning
- tax_topic_social_info_use
