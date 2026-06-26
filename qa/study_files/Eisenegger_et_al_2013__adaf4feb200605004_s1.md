# Eisenegger et al. (2013)

- **study_id:** `adaf4feb200605004_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Eisenegger, C., Pedroni, A., Rieskamp, J., Zehnder, C., Ebstein, R., Fehr, E., & Knoch, D. (2013). DAT1 polymorphism determines L-DOPA effects on learning about others' prosociality. *PLoS ONE*, *8*(7), e67820. https://doi.org/10.1371/journal.pone.0067820
- **citation_short:** Eisenegger et al. (2013)
- **doi:** 10.1371/journal.pone.0067820
- **publication_type:** peer-reviewed journal
- **year:** 2013.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** DepartmentofPsychology,UniversityofBasel,Basel,Switzerland,3CenterforEconomicPsychology,DepartmentofPsychology,UniversityofBasel,Basel,; FacultyofBusinessandEconomics,QuartierUNIL-Dorigny,UniversityofLausanne,Lausanne,Switzerland,5DepartmentofPsychology,NationalUniversity; Institute,DepartmentofPsychology,UniversityofCambridge,Cambridge,UnitedKingdom,2DivisionofSocialandAffective; LaboratoryforSocialandNeuralSystemsResearch,DepartmentofEconomics,UniversityofZurich,Zurich,Switzerland; etheraninteractionpartnerhasaprosocialoraselfish; lable, one has to learn this,; labilityofthe; UniversityG; em
- **code_url:** 

## Computational level
- **study_focus:** Prosocial learning / learning about others' prosociality; pharmacogenetic modulation of social reinforcement learning via dopamine (L-DOPA x DAT1 polymorphism interaction)
- **study_focus_short:** Prosocial learning / learning about others' prosociality
- **learning_mode_description:** - Learning mode: Learning from a partner's reciprocation/non-reciprocation about the partner's prosocial preferences   - Learning from:     - Source type (social): other (interaction partner, player B)     - Source content (social): outcomes (repayment or non-repayment of trust)   - Learning about:     - Target type (social): other (interaction partner, player B)     - Target content (social): state (mental state; prosocial vs. selfish personality/preferences)
- **task_description:** In a repeated trust-game variant, participants (player A) decided how much of a 10 MU endowment to transfer to a pre-recorded player B over 20 rounds; transfers were tripled but had a 20% chance of being "lost," and player B could either equalize payoffs or keep everything. Participants were paired with either a prosocial partner (repaying 14/20 rounds) or a selfish partner (repaying 6/20 rounds) and had to learn the partner's type through trial-and-error.
- **task_paradigm:** Trust game
- **players:** Single agent (participant as player A), dyadic (pre-recorded player B; prosocial or selfish type)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Monetary transfer decisions, binary social feedback (repayment or no repayment), monetary outcomes
- **method:** behavioural
- **method_full:** Behavioural (pharmacogenetic: L-DOPA vs. placebo, double-blind, parallel group)
- **main_result:** 
- **effect_size:** 
- **learning_from:** Other (player B); social feedback — repayment or non-repayment of transfers
- **learning_about:** Other (player B); prosocial vs. selfish preferences/personality  ---  ## 3. MAIN RESULTS & EFFECT SIZES  - Subjects successfully learned partner type over time: significant round x partner type interaction (F(10.2, 198) = 10.20, p < .001, partial eta-squared = 0.049)- Three-way interaction L-DOPA x DAT1 x partner type on total earnings (F(1, 176) = 4.65, p < .032, partial eta-squared = 0.026)- When paired with prosocial partner: L-DOPA x DAT1 interaction on earnings (F(1, 89) = 9.66, p < .003, partial eta-squared = 0.098)- L-DOPA improved learning in 10/10R genotype (placebo: 260.2 MUs vs. L-DOPA: 270.9 MUs; Z = 2.022, p < .043)- L-DOPA impaired learning in 9/10R genotype (placebo: 265.7 MUs vs. L-DOPA: 249.3 MUs; Z = 1.961, p < .050)- No dopaminergic effects when facing selfish partner (all p > .454)- No dopaminergic effects on learning rate parameter (all p > .316)- L-DOPA x DAT1 interaction on sensitivity parameter (F(1, 89) = 7.923, p < .006, partial eta-squared = 0.082)- L-DOPA decreased probability of choosing best option by 8.6 percentage points in 9/10R carriers; increased by 13.3 percentage points in 10/10R carriers- Controlling for side effects, L-DOPA x DAT1 interaction on earnings with prosocial partner remains significant (F(1, 86) = 7.76, p < .007, partial eta-squared = 0.083)---  ## 4. ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Reinforcement learning model with learning rate (alpha) and sensitivity/inverse temperature parameter (theta) [MEDIUM — formula details are in Materials S1, which is not accessible]
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** Referenced in Figure S2 (BIC values of different models employed) — details in Materials S1 which is not accessible. At minimum, a standard RL model was tested; the paper states multiple models were compared via BIC but specifics are unavailable.
- **model_mb_mf:** MF (model-free)
- **model_params:** - alpha (learning rate): determines how strongly feedback changes subjective value of transfer options. No mean fitted value reported in main text. [HIGH for description, cannot_find for values] - theta (sensitivity / inverse temperature): specifies exploration-exploitation trade-off. No mean fitted value reported in main text. Dopaminergic modulation was found on this parameter. [HIGH for description, cannot_find for values]
- **social_param:** No explicitly social parameter — the model is a standard RL model applied to social feedback. The sensitivity parameter (theta) was the parameter modulated by the pharmacogenetic manipulation.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (referenced in Figure S2)
- **how_model_fit:** Individual-level fit (implied by parameter-level analyses per subject and ANOVA on individual parameters)
- **data_type_fit_to:** Choice behavior (transfer decisions)---  ## 5. IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** None (behavioural study only)
- **contrast:** 
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ## 6. PAPER QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 200 (205 recruited, 5 excluded: 3 nausea, 2 did not understand instructions); all healthy males; mean age 23.5 years (SD = 3.6). L-DOPA group: n = 99; placebo group: n = 101. DAT1 genotype breakdown: 10/10R = 96, 9/10R = 88, other genotypes excluded from analyses. Prosocial partner: n = 101; selfish partner: n = 99.
- **population_category:** healthy adults
- **population_age_range:** M=23.5
- **ecological_validity:** Moderate. The task is a novel social interaction paradigm akin to a repeated trust game, which captures aspects of learning about others' prosociality in repeated interactions. However, player B's decisions are pre-recorded (eliminating strategic interaction), which reduces ecological validity. Lab-based, with monetary incentives.
- **eligibility_flag:** 
- **concerns:** - Supplement (Materials S1) not accessible — contains full model specification, model comparison details (Figure S2), and potentially parameter recovery/simulation information. This limits ability to fully evaluate the computational modeling. - The exact RL model formula is not provided in the main text. - Mean fitted parameter values are not reported in the main text. - The list of all models compared is not available (only referenced in Figure S2 in Materials S1). - Authors acknowledge the effect may reflect a general probabilistic learning mechanism rather than being specific to social contexts. - Only male participants — limited generalizability. - Pre-recorded partner decisions eliminate real social interaction.
- **limitations_reported:** The pharmacogenetic effect may not be uniquely related to social interactions but may rather reflect a relatively broad probabilistic learning mechanism that guides behavior both in social and non-social contexts; whether the effect is uniquely social or general is a topic for further studies; players might have relied upon a cognitive mentalizing system on top of neural reward circuitry when making inferences about player B's intentions.
- **limitations_categorized:** Limited generalizability (males only); limited ecological validity (pre-recorded partner); unclear social specificity; no neuroimaging; supplement not accessible for full model evaluation
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Partial
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - all_models_tested: LOW — details only in inaccessible Materials S1 - winning_model formula: MEDIUM — described verbally but exact formula in Materials S1 - model_params (fitted values): MEDIUM — no mean fitted values in main text - WC rules 2, 3, 5, 6: MEDIUM — may be addressed in Materials S1 - social_param: MEDIUM — no explicitly social parameter; standard RL applied to social context
- **cannot_find:** - Exact model formula (in Materials S1) - Full list of competing models (in Materials S1 / Figure S2) - Mean fitted parameter values for alpha and theta - Parameter recovery analysis - Model recovery analysis - Simulation details
- **other_notes:** This is a PLoS ONE open-access paper from 2013. The supplement (Materials S1, a .doc file) is referenced for the full RL model specification and BIC comparison of models (Figure S2). The supplement is not available in the papers folder. The paper provides a pharmacogenetic approach (L-DOPA x DAT1 genotype) to studying dopaminergic modulation of social reinforcement learning. The key finding is that dopamine effects on learning about others' prosociality follow an inverted-U relationship modulated by genetically determined baseline striatal dopamine levels, affecting the sensitivity/exploitation parameter rather than the learning rate.
- **re_extract_flag:** true — Materials S1 (supplement) not accessible; contains critical model specification, model comparison (Figure S2), and potentially simulation/recovery details. Extraction is incomplete for algorithmic-level fields.

## Taxonomy / categorization (active codes only)
- pharma_dopamine
- pop_healthy_adults
- rr_pharma_dopamine
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_PE_signal
- tax_param_temperature
- tax_popclass_healthy
- tax_popclass_pharmacological
- tax_rr_domain = F_affective_moral
- tax_rr_domain_C_exchange_interdependence
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = prosocial_altruism
- tax_rr_secondary_topic = trust
- tax_rr_topic_prosocial_altruism
- tax_rr_topic_trust
- tax_topic_prosocial_altruism
- tax_topic_trust
