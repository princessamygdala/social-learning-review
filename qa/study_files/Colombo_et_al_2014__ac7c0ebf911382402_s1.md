# Colombo et al. (2014)

- **study_id:** `ac7c0ebf911382402_s1`
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
- **study_focus:** Norm learning; social vs. non-social feedback effects on associative learning of a tipping norm.
- **study_focus_short:** Norm learning
- **learning_mode_description:** - Learning mode: Learning from positive/negative feedback (social facial expressions or non-social symbols) about whether one's tipping action conforms to a social norm.   - Learning from:     - Source type (social in social condition; non-social in non-social condition): world (feedback from environment/task)       - Social condition: feedback is happy/angry facial expressions       - Non-social condition: feedback is tick/cross marks     - Source content (non-social): outcome (positive or negative feedback signal)   - Learning about:     - Target type (social): world (social norm)     - Target content (social): state (social norm of tipping -- what percentage to tip)
- **task_description:** Participants played a "Tipping Game" where they imagined being diners in an unfamiliar country. On each trial, they saw the quality of service (good/bad), received a bill, chose a tip percentage (0-100%), and received probabilistic positive or negative feedback (happy/angry face or tick/cross) indicating whether their tip was above or below the underlying social norm.
- **task_paradigm:** Norm learning
- **players:** Single agent (participant), no interactive partner (feedback from task environment).
- **n_players:** single agent (1)
- **partner_type:** human (recorded)
- **stimuli:** Restaurant bills (numerical), service quality labels (good/bad), facial expressions (happy/angry from JAFFE database) or tick/cross marks as feedback.
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Social feedback led to significantly higher tipping than non-social feedback in blocks 2 and 3 (MANCOVA: Block 2 F(1,1557)=20.53, eta-p-squared=0.013; Block 3 F(1,1557)=5.65, eta-p-squared=0.004)   - Block 1 difference was not significant (F(1,1557)=2.53, eta-p-squared=0.002)   - More participants displayed learning in the social group (12/20) than the non-social group (7/19)   - Social group tipped more by 1%, 4.9%, and 8.2% closer to the norm in blocks 1, 2, and 3 respectively   - Significant difference in economic weight parameter w_econ between groups (p=0.019, independent two-tailed t-test)   - Effect sizes were small (authors' own assessment)
- **effect_size:** - Main Results:   - Social feedback led to significantly higher tipping than non-social feedback in blocks 2 and 3 (MANCOVA: Block 2 F(1,1557)=20.53, eta-p-squared=0.013; Block 3 F(1,1557)=5.65, eta-p-squared=0.004)   - Block 1 difference was not significant (F(1,1557)=2.53, eta-p-squared=0.002)   - More participants displayed learning in the social group (12/20) than the non-social group (7/19)   - Social group tipped more by 1%, 4.9%, and 8.2% closer to the norm in blocks 1, 2, and 3 respectively   - Significant difference in economic weight parameter w_econ between groups (p=0.019, independent two-tailed t-test)   - Effect sizes were small (authors' own assessment)
- **learning_from:** World; probabilistic positive/negative feedback on tipping action (social: facial expressions; non-social: tick/cross marks).
- **learning_about:** Social norm of tipping (what percentage to tip given service quality).  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Rescorla-Wagner with modified reward signal: Q-learning with softmax action selection; reward = tanh(w_out * r_out - w_econ * r_econ); 4 parameters: alpha, tau, w_out, w_econ.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Rescorla-Wagner with economic/outcome weights", "family": "Rescorla-Wagner", "n_params": 4, "metric": "maximum likelihood"}] - Note: Only one model was tested. No model comparison was performed.
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate, 0 <= alpha <= 1): Social mean = 0.24, Non-social mean = 0.20 - tau (inverse temperature, positive): Social mean = 93.2, Non-social mean = 78.8 - w_out (outcome weight, 0 <= w_out <= w_max): Social mean = 4.43, Non-social mean = 3.82 - w_econ [S] (economic weight, 0 <= w_econ <= 10; sensitivity to economic cost of tipping): Social mean = 0.004, Non-social mean = 0.038
- **social_param:** w_econ -- economic weight parameter capturing sensitivity to the economic cost of tipping. Lower values indicate less concern about spending money on tips (more generous). The significant difference in w_econ between social and non-social groups (p=0.019) was the key finding: social feedback reduced sensitivity to economic costs.
- **social_param_name:** w_econ
- **social_param_value:** 0.004
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A -- only one model tested; maximum likelihood used for fitting.
- **how_model_fit:** individual-level-fit (MLE fitted to each participant individually)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only; authors suggest future fMRI work to examine striatal dopamine system and mentalizing networks)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=40 (20 social condition [7 females], 20 non-social condition [10 females]); 1 excluded from non-social condition for not understanding the task; final N=39. University of Edinburgh students, all lived in UK 1+ year.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate -- the Tipping Game simulates a real-world social norm learning situation (tipping) with facial expression feedback, which is more ecologically valid than abstract category learning tasks. However, monetary units were fictional, no actual person benefited from tips, and feedback was probabilistic/artificial.
- **eligibility_flag:** 
- **concerns:** Small effect sizes (authors acknowledge); only one model tested (no model comparison); high inter-individual variability; fictional monetary units (no real stakes); feedback structure made learning especially hard due to high noise; cannot disentangle social vs. emotional dimensions of facial expressions.
- **limitations_reported:** Some neurodevelopmental disorders, including autism, Asperger syndrome and schizophrenia, are known to affect the relative power of social vs. non-social feedback"; "previous experiments suggest that males and females process some types of social reward differently" and personality traits were not fully measured in Experiment 2; "the feedback structure made the learning task especially hard" due to high noise in state-action-reward mapping and feedback reliability being independent of distance from norm; "the stimuli that we used in the social condition of our task did not help us to determine whether the behavioral effects we observed depended on social rather than on only the emotional dimension of facial expressions.
- **limitations_categorized:** Limited generalizability (clinical populations not tested); potential gender confound; task difficulty/noise structure; confound between social and emotional cues; limited ecological validity (fictional stakes).
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
- spec_depth = general
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
