# Colombo et al. (2014)

- **study_id:** `ac7c0ebf911382402_s2`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Colombo, M., Stankevicius, A., & Series, P. (2014). Benefits of social vs. non-social feedback on learning and generosity: Results from the Tipping Game. *Frontiers in Psychology*, *5*, 1154. https://doi.org/10.3389/fpsyg.2014.01154
- **citation_short:** Colombo et al. (2014)
- **doi:** 10.3389/fpsyg.2014.01154
- **publication_type:** peer-reviewed journal
- **year:** 2014.0
- **field_of_study:** Psychology
- **affiliations_raw:** Instituteof relatively little is known about how different types of feedback impact adaptive changes; ethatpeople’sdecision-makingisoften characterizedbythemerepresenceofothers(Allport,1920);and; CenterforLogic,GeneralEthics,andPhilosophyofScience,TilburgUniversity,Tilburg,Netherlands; etheexampleoftippingandask:how social(greenorredlights)reinforcementwasused(Hurlemann; etheycanfunctionas social nature of the evidence itself (Becker,1976; Oaksford and; etheeffectiveuseand vide an unambiguous answer to the question of how learning; InstituteforAdaptiveandNeuralComputation,UniversityofEdinburgh
- **code_url:** 

## Computational level
- **study_focus:** Norm learning; social vs. non-social feedback effects on learning and generosity, with varying norm levels and feedback reliability.
- **study_focus_short:** Norm learning
- **learning_mode_description:** - Learning mode: Learning from positive/negative feedback (social facial expressions or non-social symbols) about whether one's tipping action conforms to a social norm.   - Learning from:     - Source type (social in social condition; non-social in non-social condition): world (feedback from environment/task)       - Social condition: feedback is happy/angry facial expressions       - Non-social condition: feedback is tick/cross marks     - Source content (non-social): outcome (positive or negative feedback signal)   - Learning about:     - Target type (social): world (social norm)     - Target content (social): state (social norm of tipping -- what percentage to tip)
- **task_description:** Same Tipping Game as Experiment 1 but with 4 blocks instead of 3, including a block with a below-standard tipping norm (7%) and a block with more reliable feedback, designed to test whether social feedback effects are driven by generosity vs. learning and whether they depend on task difficulty.
- **task_paradigm:** Norm learning
- **players:** Single agent (participant), no interactive partner (feedback from task environment).
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Restaurant bills (numerical), service quality labels (good/bad), facial expressions (happy/angry from JAFFE database) or tick/cross marks as feedback.
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Social feedback had significant effect on tipping in all 4 blocks (MANCOVA: Block 1 F(1,1597)=77.01, eta-p-squared=0.046; Block 2 F(1,1597)=8.11, eta-p-squared=0.005; Block 3 F(1,1597)=10.81, eta-p-squared=0.007; Block 4 F(1,1597)=117.13, eta-p-squared=0.068)   - Social group tipped more by 7.2%, 1.8%, 2.9%, and 10.6% closer to norm in blocks 1-4   - More participants displayed learning in social group (17/20) than non-social group (10/20)   - Significant difference in w_econ between groups (p=0.049, independent two-tailed t-test)
- **effect_size:** - Main Results:   - Social feedback had significant effect on tipping in all 4 blocks (MANCOVA: Block 1 F(1,1597)=77.01, eta-p-squared=0.046; Block 2 F(1,1597)=8.11, eta-p-squared=0.005; Block 3 F(1,1597)=10.81, eta-p-squared=0.007; Block 4 F(1,1597)=117.13, eta-p-squared=0.068)   - Social group tipped more by 7.2%, 1.8%, 2.9%, and 10.6% closer to norm in blocks 1-4   - More participants displayed learning in social group (17/20) than non-social group (10/20)   - Significant difference in w_econ between groups (p=0.049, independent two-tailed t-test)
- **learning_from:** World; probabilistic positive/negative feedback on tipping action (social: facial expressions; non-social: tick/cross marks).
- **learning_about:** Social norm of tipping (what percentage to tip given service quality).  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Rescorla-Wagner with modified reward signal: Q-learning with softmax action selection; reward = tanh(w_out * r_out - w_econ * r_econ); 4 parameters: alpha, tau, w_out, w_econ.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Rescorla-Wagner with economic/outcome weights", "family": "Rescorla-Wagner", "n_params": 4, "metric": "maximum likelihood"}] - Note: Only one model was tested. No model comparison was performed.
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate, 0 <= alpha <= 1): Social mean = 0.40, Non-social mean = 0.29 - tau (inverse temperature, positive): Social mean = 20.7, Non-social mean = 59.9 - w_out (outcome weight, 0 <= w_out <= w_max): Social mean = 5.68, Non-social mean = 4.51 - w_econ [S] (economic weight, 0 <= w_econ <= 10; sensitivity to economic cost of tipping): Social mean = 0.002, Non-social mean = 0.081
- **social_param:** w_econ -- economic weight parameter capturing sensitivity to the economic cost of tipping. Social feedback group showed significantly lower w_econ (p=0.049), indicating reduced sensitivity to economic costs and more generous tipping.
- **social_param_name:** w_econ
- **social_param_value:** 0.002
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A -- only one model tested; maximum likelihood used for fitting.
- **how_model_fit:** individual-level-fit (MLE fitted to each participant individually)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=40 (20 social condition, 20 non-social condition; 12 males total). University of Edinburgh students, all lived in UK 1+ year. No personality questionnaires administered in this experiment.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate -- same as Experiment 1; additional block with below-standard norm (7%) tests whether social feedback biases toward over-tipping even when norm is low.
- **eligibility_flag:** 
- **concerns:** Same as Experiment 1; additionally, no personality questionnaires collected in this experiment so cannot rule out personality trait confounds; effect sizes still small (eta-p-squared range 0.005-0.068).
- **limitations_reported:** Same as Experiment 1 (limitations discussed in General Discussion covering both experiments).
- **limitations_categorized:** Limited generalizability (clinical populations not tested); potential gender confound; task difficulty/noise structure; confound between social and emotional cues; limited ecological validity (fictional stakes); no personality measures collected.
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 3.5
- **wc_total:** 3.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `all_models_tested`: LOW confidence -- only one model described; unclear if authors tested alternative models and did not report them, or genuinely only fitted one model.   - `learning_mode` source type: MEDIUM confidence -- the feedback comes from the task/environment, not from a real social agent. In the social condition, faces serve as feedback stimuli but do not represent a real interacting person. Classified as "world" for source type.
- **cannot_find:** - No model comparison (only 1 model fitted)   - No simulation/parameter recovery/model recovery analyses   - No posterior predictive checks   - No data or code sharing links   - No supplement found
- **other_notes:** The paper uses the same Rescorla-Wagner model for both experiments, with parameters fitted separately per participant. The key social manipulation is between-subjects (social vs. non-social feedback condition), not within-model. The social parameter w_econ is not inherently "social" -- it captures economic sensitivity, which differs between conditions receiving social vs. non-social feedback. The paper is explicitly behavioral with no neuroimaging; authors suggest fMRI as future work. No supplement was found for this paper.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_social_bonus
- tax_rr_param_temperature
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = social_approval_reward
- tax_rr_topic_norm_conformity
- tax_rr_topic_social_approval_reward
- tax_social_nonsocial_comparison
- tax_topic_norm_conformity
- tax_topic_social_approval_reward
