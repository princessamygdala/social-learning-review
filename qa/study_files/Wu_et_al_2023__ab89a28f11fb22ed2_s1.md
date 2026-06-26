# Wu et al. (2023)

- **study_id:** `ab89a28f11fb22ed2_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Wu, X., Zhu, R., Gong, X., Luo, Y., & Liu, C. (2023). Social incentives foster cooperation through guilt aversion: An effect that diminishes with primary psychopathic traits. *PsyCh Journal*, *12*(3), 389–398. https://doi.org/10.1002/pchj.641
- **citation_short:** Wu et al. (2023)
- **doi:** 10.1002/pchj.641
- **publication_type:** peer-reviewed journal
- **year:** 2023.0
- **field_of_study:** Psychiatry / Computational psychiatry
- **affiliations_raw:** CenterofBrainDisorderandCognitiveSciences, taryincentivesandsocialincentivesonpromotingcooperationinhealthyadultswithvary-; CenterofBrainImaging,BeijingNormal nificantly improved participants’ contributions to the public project—an indicator of; LaboratoryofAffectiveandSocial participants’ decisions would be judged by others, a monetary incentives context where; InstituteforBrain The association between primary psychopathic traits and non-cooperative behaviors is; InstituteofPsychology,ChineseAcademyofSciencesandJohnWiley&SonsAustralia,Ltd; CollegeofPsychology,ShenzhenUniversity, ingprimarypsy
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning; guilt aversion in cooperative decision-making under social vs. monetary incentives, modulated by primary psychopathic traits.
- **study_focus_short:** Cooperation learning
- **learning_mode_description:** - Learning mode: Learning from others' inferred social expectations about how to adjust cooperative contributions via guilt aversion   - Learning from:     - Source type (social): other (anonymous co-players / evaluators)     - Source content (social): state (mental state; inferred second-order beliefs — what others expect of the participant)   - Learning about:     - Target type (non-social): self     - Target content (non-social): action/policy (own contribution level to public goods)
- **task_description:** Participants played a one-shot public goods game (PGG) with three anonymous co-players across 60 rounds in three contexts (social incentives: decisions judged by others; monetary incentives: financial reward/punishment based on relative contribution; control: no additional incentives), deciding how many of 10 tokens to contribute to a public pool (multiplied by 1.6 and split equally).
- **task_paradigm:** Public goods game
- **players:** Single agent (participant), multi-target (3 anonymous co-players per round; separate evaluator group in social incentive condition)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Text cue words ("social evaluation," "monetary incentives," "impunity"), token allocation decisions (0–10), monetary outcomes
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Interaction of context x primary psychopathic traits on contribution (F[2, 114] = 5.595, p < .01)   - Primary psychopathic traits predicted contribution in social incentive context (beta = -2.472, 95% CI [-4.731, -0.214])   - Slope of primary psychopathic traits on contribution in social > monetary context (t[114] = 3.293)   - Interaction of context x primary psychopathic traits on guilt aversion (F[2, 114] = 3.059, p = .050)   - Primary psychopathic traits predicted guilt aversion in social incentive context (t[114] = -2.072)   - Model validation: predicted vs. observed contribution correlation (monetary: r = 0.978; social: r = 0.973; control: r = 0.962)   - Simulated data recovered behavioral effects (main effect of context: F[2, 188] = 131.244, eta-squared = 0.682)   - Anticipated guilt correlated with primary psychopathic traits in social context (r = 0.389)
- **effect_size:** - Main Results:   - Interaction of context x primary psychopathic traits on contribution (F[2, 114] = 5.595, p < .01)   - Primary psychopathic traits predicted contribution in social incentive context (beta = -2.472, 95% CI [-4.731, -0.214])   - Slope of primary psychopathic traits on contribution in social > monetary context (t[114] = 3.293)   - Interaction of context x primary psychopathic traits on guilt aversion (F[2, 114] = 3.059, p = .050)   - Primary psychopathic traits predicted guilt aversion in social incentive context (t[114] = -2.072)   - Model validation: predicted vs. observed contribution correlation (monetary: r = 0.978; social: r = 0.973; control: r = 0.962)   - Simulated data recovered behavioral effects (main effect of context: F[2, 188] = 131.244, eta-squared = 0.682)   - Anticipated guilt correlated with primary psychopathic traits in social context (r = 0.389)
- **learning_from:** Other (anonymous co-players); inferred second-order beliefs (others' expectations of participant's contributions)
- **learning_about:** Self; own cooperative contribution policy (how much to contribute to the public good)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Guilt aversion model (4 params: omega_monetary, omega_social, omega_control, beta); SV = self - omega * anticipated_guilt; anticipated_guilt = E2(Cs) - Cs; softmax choice rule
- **model_family:** Utility / EV
- **model_class:** Utility maximization
- **all_models_tested:** [   {"name": "Self-collective interests integration model", "family": "Utility/value function", "n_params": 4, "metric": "AICc = 258.77, BICc = 267.91, PEP = 0.00"},   {"name": "Guilt aversion model", "family": "Utility/value function (guilt aversion)", "n_params": 4, "metric": "AICc = 215.89, BICc = 225.03, PEP = 1.00"},   {"name": "Combined model", "family": "Hybrid utility (collective + guilt)", "n_params": 7, "metric": "AICc = 223.22, BICc = 240.14, PEP = 0.00"} ]
- **model_mb_mf:** N/A (not RL)
- **model_params:** - omega_monetary [S]: guilt aversion in monetary incentive context; mean = 0.73 (95% CI: 0.689, 0.770); range [0, 1] - omega_social [S]: guilt aversion in social incentive context; mean = 0.57 (95% CI: 0.521, 0.623); range [0, 1] - omega_control [S]: guilt aversion in control context; mean = 0.44 (95% CI: 0.392, 0.501); range [0, 1] - beta: inverse softmax temperature; mean = 6.92 (95% CI: 6.374, 7.471); range [0, 1] (note: fitted mean exceeds stated bound, suggesting bound may be wider in practice)
- **social_param:** omega (omega_monetary, omega_social, omega_control) — magnitude of guilt aversion, reflecting the degree to which participants are averse to the anticipated guilt of disappointing other players by not meeting their inferred expectations. Higher omega = more conformity to others' expectations.
- **social_param_name:** omega_monetary
- **social_param_value:** 0.73
- **social_param_sd:** 
- **social_param_range:** 0–1
- **model_comparison_metric:** AICc, BICc, Protected Exceedance Probability (PEP)
- **how_model_fit:** individual-level-fit (MLE using fmincon in MATLAB with 200 random starting points per participant)
- **data_type_fit_to:** choice behavior (token contribution amounts across 60 rounds)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study)
- **key_regions:** N/A (behavioural study)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 60 (mean age = 21.68 +/- 2.35 years; 19 males, 41 females); all healthy adults, no psychiatric history
- **population_category:** clinical
- **population_age_range:** M=21.68
- **ecological_validity:** Low-to-moderate. Lab-based PGG with anonymous players; one-shot structure with text cue manipulation. Social incentives involved real evaluation by a separate group of participants (enhancing ecological validity somewhat), but interaction was indirect and non-face-to-face. Token-based payoffs rather than naturalistic social situations.
- **eligibility_flag:** Borderline — the PGG is a one-shot game per round (no trial-to-trial learning/updating). The computational model is a static utility model fit across rounds, not a dynamic learning model that updates parameters over time. There is no prediction error or belief updating across trials. The "learning" here is better characterized as static decision-making under different incentive contexts. FLAG: borderline learning-vs-decision-making; no temporal updating or trial-by-trial learning.
- **concerns:** - The model is a static utility function, not a dynamic learning model — there is no trial-to-trial updating of beliefs or parameters. This is closer to a decision-making model than a learning model. - beta parameter stated to have range [0, 1] in the paper but the fitted mean is 6.92, suggesting the actual bound is different or a typo in the main text. - Self-reported beliefs (first-order and second-order) were collected once before the game (not updated across trials), meaning the model uses static belief inputs. - The PGG is described as "one-shot" per round with different anonymous players each round, limiting the scope for learning dynamics.
- **limitations_reported:** One limitation of the present study is that all of the participants were university students, which may limit the generalizability of the findings.
- **limitations_categorized:** Limited generalizability (student sample)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 8.5
- **wc_total:** 8.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** yes
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - eligibility_flag: MEDIUM confidence — borderline learning vs. decision-making. The model is static (no trial-to-trial updating). - beta parameter range: LOW confidence — main text states 0 <= beta <= 1 but fitted mean = 6.92; likely a typo or the stated bound applies to a different parameterization. - learning_mode: MEDIUM confidence — classified as learning from inferred social expectations, but technically this is static belief-based decision-making rather than dynamic learning.
- **cannot_find:** - No data or code sharing information found. - No model recovery / confusion matrix analysis. - No trial-by-trial learning dynamics (beliefs are static, collected once pre-task).
- **other_notes:** This paper uses a guilt aversion utility model rather than a learning model per se. The computational modeling captures how participants weight anticipated guilt (from violating inferred social expectations) in their contribution decisions, varying across incentive contexts. The key finding is that primary psychopathic traits are associated with reduced guilt aversion specifically in the social incentive context. The model is well-validated (parameter recovery, predictive validity) but is fundamentally a static decision model, not a trial-by-trial learning model. The paper draws heavily on Chang et al. (2011) and Gong et al. (2019) for the guilt aversion framework.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- pop_psychopathy
- rr_pop_healthy_adults
- rr_pop_psychopathy
- rr_tax_mod_experiential
- rr_tax_mod_mentalizing_inference
- spec_context = social
- spec_depth = structural
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_mentalizing_inference
- tax_model_utility
- tax_param_social_weight
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = utility_EV
- tax_rr_model_utility_EV
- tax_rr_param_social_weight
- tax_rr_primary_topic = cooperation
- tax_rr_topic_cooperation
- tax_topic_cooperation
