# Devaine & Daunizeau (2017)

- **study_id:** `a026a5057e5c402fa_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Devaine, M., & Daunizeau, J. (2017). Learning about and from others' prudence, impatience or laziness: The computational bases of attitude alignment. *PLoS Computational Biology*, *13*(3), e1005422.
- **citation_short:** Devaine & Daunizeau (2017)
- **doi:** 10.1371/journal.pcbi.1005422
- **publication_type:** peer-reviewed journal
- **year:** 2017.0
- **field_of_study:** Psychology
- **affiliations_raw:** ethenvalidatethesepredictionsexperimentallybyprofilingpeople’sattitudesbothbefore; mitateothers’motoractions[11]andmirrortheiremotions[12]whenthisisnotinstrumen-; ethattheyderivefromuncertain(andmostlyimplicit)beliefsabout; Institute(ICM),Paris,France,2 ETH,Zurich,Switzerland; mitativebehaviourautomatically,eveninthe; etheydeterminehowpeoplearbitratebetween; mitsunrestricteduse,distribution,and; labilityStatement:Dataareavailableat; emails: jean.daunizeau@gmail.com
- **code_url:** http://mbb-team.github.io/VBA-toolbox/

## Computational level
- **study_focus:** Attitude alignment; learning about and from others' cost-benefit arbitrage attitudes (prudence, impatience, laziness) through mentalizing; false-consensus bias; social influence bias
- **study_focus_short:** Attitude alignment
- **learning_mode_description:** - Learning mode: Learning from observing another agent's cost-benefit arbitrage choices about the other's covert attitude (cost-susceptibility), and simultaneously updating one's own attitude toward the "best" policy.   - Learning from:     - Source type (social): other (artificial agent impersonating a human)     - Source content (social): action/policy (binary choices in cost-benefit arbitrages)   - Learning about:     - Target type (social): other (artificial agent) + self       - If joint: marked as **joint** (learning about other's attitude informs update of own attitude)     - Target content (social): state (mental state; covert cost-susceptibility trait -- prudence/impatience/laziness) + state (own belief about "best" policy)       - If joint: marked as **joint**
- **task_description:** Participants made cost-benefit arbitrage choices (delay, effort, risk) in Decision phase 1, then predicted an artificial agent's choices in a Prediction phase while receiving feedback, and finally repeated their own choices in Decision phase 2. The artificial agent was calibrated to have the same, different, or noisy cost-susceptibility relative to the participant.
- **task_paradigm:** Probabilistic ToM task
- **players:** Single agent (participant); single social source (artificial agent impersonating a human); between-subject design with 3 subgroups (Same/Different/Noisy conditions counterbalanced across cost types)
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Binary choice alternatives differing in reward and cost (delay: monetary payoff now vs. later; effort: low vs. high grip force for payoff; risk: secure vs. risky lottery); text/numeric displays of options
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - False-consensus bias: Significant interaction between session stage and condition type (F(1,148) = 13.5, p = 2 x 10^-4); performance significantly better in Same than Different condition at beginning of Prediction phase (t(148) = 4.68, p = 10^-5) but not at end (t(148) = -0.6, p = 0.70). - Influence bias: Significant interaction between initial cost-susceptibility and condition type (F(1,97) = 4.7, p = 0.03). Participants' cost-susceptibility drifted toward the observed agent's in the Different condition. - False-consensus validation: Participants' prior mean on Other's cost-susceptibility significantly correlated with their own cost-susceptibility (delay: R^2 = 36.0%, t(49) = 5.3, p = 2 x 10^-6; effort: R^2 = 29.2%, t(49) = 4.5, p = 2 x 10^-5; risk: R^2 = 37.8%, t(49) = 5.5, p = 8 x 10^-7). - Influence bias validation: Change in cost-susceptibility significantly correlated with prediction error (delay: R^2 = 10.1%, t(49) = 2.3, p = 0.01; effort: R^2 = 6.0%, t(49) = 1.8, p = 0.04; risk: R^2 = 26.9%, t(49) = 4.2, p = 5 x 10^-5). - Multiple regression (orthogonalized): Other's estimated trait explained significant variance in updated cost-susceptibility (delay: R^2 = 46.9%; effort: R^2 = 22.6%; risk: R^2 = 71.6%). - Bayesian model comparison: Model m4 (false-consensus + influence) most prevalent (EP = 99.6%, protected EP = 98.4%; frequency = 58.1% +/- 6.3%). - Average influence bias IB-hat significant (t(48) = 4.4, p = 6 x 10^-5, R^2 = 29.3%).
- **effect_size:** - False-consensus ANOVA interaction: F(1,148) = 13.5 - Influence ANOVA interaction: F(1,97) = 4.7 - False-consensus R^2: delay 36.0%, effort 29.2%, risk 37.8% - Influence R^2: delay 10.1%, effort 6.0%, risk 26.9% - Multiple regression R^2: delay 46.9%, effort 22.6%, risk 71.6% - Model m4 exceedance probability: EP = 99.6%, PEP = 98.4% - Average IB-hat: R^2 = 29.3%
- **learning_from:** Other (artificial agent); observed binary choices in cost-benefit arbitrages (social)
- **learning_about:** Other's covert cost-susceptibility trait (social); own belief about "best" policy / own cost-susceptibility (self, non-social updated via social information)
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Bayesian model of attitude alignment (m4: false-consensus + influence biases). Integrates BPL (Bayesian Preference Learner) for mentalizing about Other's cost-susceptibility with a Bayesian belief update on "best" policy that yields both false-consensus (prior on Other derived from own trait) and influence (own trait updated after observing Other). Parameters: sigma_epsilon, sigma_G, Gamma_G, Omega_G, alpha^(s)_1, beta^(s) (Decision), beta^(s) (Prediction), mu^(o,2)_0, Sigma^(o,2)_0. 7 free parameters in full model.
- **model_family:** Bayesian
- **model_class:** Theory of Mind
- **all_models_tested:** [{"name": "m1 (no false-consensus, no influence)", "family": "Bayesian belief updating", "n_params": "9 (BPL prior free + no influence)", "metric": "log-evidence (VB marginal likelihood) + RFX-BMS"}, {"name": "m2 (false-consensus, no influence)", "family": "Bayesian belief updating", "n_params": "7", "metric": "log-evidence + RFX-BMS"}, {"name": "m3 (no false-consensus, influence)", "family": "Bayesian belief updating", "n_params": "9 (BPL prior free + influence)", "metric": "log-evidence + RFX-BMS"}, {"name": "m4 (false-consensus + influence)", "family": "Bayesian belief updating", "n_params": "7", "metric": "log-evidence + RFX-BMS"}, {"name": "Random model (Prediction phase)", "family": "null/random", "n_params": 1, "metric": "log-evidence + RFX-BMS"}, {"name": "Fictitious Play (Prediction phase)", "family": "Bayesian frequency tracker", "n_params": 1, "metric": "log-evidence + RFX-BMS"}, {"name": "Self Preference (Prediction phase)", "family": "projection", "n_params": 0, "metric": "log-evidence + RFX-BMS"}, {"name": "Linear BPL (Prediction phase)", "family": "Bayesian belief updating (linear utility)", "n_params": 2, "metric": "log-evidence + RFX-BMS"}, {"name": "Linear utility (Decision phase)", "family": "linear utility", "n_params": 2, "metric": "log-evidence + RFX-BMS"}, {"name": "Nonlinear utility (Decision phase, winning)", "family": "hyperbolic/exponential/effort-discount utility", "n_params": 2, "metric": "log-evidence + RFX-BMS"}]
- **model_mb_mf:** Bayesian (N/A -- not RL)
- **model_params:** - alpha (cost-susceptibility): controls delay/effort/risk sensitivity; estimated per participant per cost type. Mean fitted: delay 1.4 (SD 1.6) Dec1, 1.2 (1.6) Dec2; effort -0.8 (1.2) Dec1, -0.7 (1.3) Dec2; risk -2.5 (0.9) Dec1, -2.6 (0.9) Dec2 [log-transformed] - beta (inverse temperature): controls stochasticity of choices. Mean fitted: delay 0.1 (0.8) Dec1, 0.1 (0.6) Dec2; effort 0.1 (1.3) Dec1, -0.2 (1.1) Dec2; risk -3.0 (0.8) Dec1, -3.2 Dec2 [log-transformed] - sigma_epsilon: reinforcement noise variance [S -- shapes false-consensus magnitude] - sigma_G: prior variance on "best" policy [S -- shapes false-consensus and influence] - Gamma_G: population mean of innate prior on "best" policy - Omega_G: inter-individual variance of innate prior [S -- shapes influence learning rate lambda] - lambda (learning rate for influence): derived parameter, 0 <= lambda <= 1, function of sigma_epsilon, sigma_G, Omega_G [S] - mu^(o)_0: prior mean on Other's trait (constrained by Eq. 9 in FC models) [S] - Sigma^(o)_0: prior variance on Other's trait [S]
- **social_param:** sigma_epsilon, sigma_G, Omega_G [S]: jointly determine false-consensus bias magnitude and influence learning rate lambda. mu^(o)_0 [S]: prior on Other's cost-susceptibility (derived from own trait via false-consensus). lambda [S]: derived learning rate for attitude alignment.
- **social_param_name:** lambda
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Variational Bayes marginal likelihood (log-evidence); random-effects Bayesian model selection (RFX-BMS) with exceedance probability (EP) and protected exceedance probability (PEP)
- **how_model_fit:** individual-level-fit (variational Laplace approximation via VBA toolbox)
- **data_type_fit_to:** choice behavior  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study)
- **key_regions:** N/A (behavioural study)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 56 (36 females; mean age = 25.0 +/- 4.5 years); 3 excluded from effort tasks (technical issues); 2 more excluded for always choosing same option in effort. Between-subject design: 3 subgroups (~18-19 per group) for Same/Different/Noisy condition assignment.
- **population_category:** healthy adults
- **population_age_range:** M=25.0
- **ecological_validity:** Lab-based behavioural economics paradigm using cost-benefit arbitrages with real monetary incentives; artificial agents impersonating humans (participants believed they were observing a previous participant); adaptive online design optimization enhanced statistical power. Limited ecological validity due to artificial agents and constrained choice contexts. Effort task used real physical grip force (high ecological validity for effort). Only 19% of participants reported awareness of attitude change.
- **eligibility_flag:** The "social agent" is an automated/artificial system (calibrated artificial agents impersonating humans). Flag: artificial_social_agent. Paper remains eligible -- participants believed agent was human.
- **concerns:** Between-subject design may reduce power for detecting condition differences. The artificial agent impersonation limits generalizability to real social interactions. The inverted U-shaped relationship between FCB and IB only reached significance after controlling for age and gender (small effect: R^2 = 6.0%). Influence bias effect sizes substantially smaller than false-consensus effect sizes. Repeated identical choice alternatives in Decision phases 1 and 2 may induce memory/anchoring effects masking influence bias. No parameter or model recovery analyses reported.
- **limitations_reported:** Between-subject design may confound inter-individual differences with condition comparisons; pilot-study-based median split resulted in statistical imbalance; inverted U-shaped FCB-IB relationship evidence not definitive (quadratic effect only significant after controlling for age/gender); effect sizes for influence bias weaker than false-consensus bias; no explicit comparison with alternative explanations that would make qualitatively similar predictions; model cannot distinguish conscious/explicit from unconscious/implicit aspects of mentalizing; model specifies neither when attitude alignment occurs nor how long it lasts; linear vs. nonlinear utility functions for effort inconclusive at group level
- **limitations_categorized:** limited statistical power; between-subject design limitations; weak effect sizes for influence bias; incomplete model validation; no alternative model comparison for qualitative predictions; limited ecological validity (artificial agents); conscious vs. unconscious processing not addressed; temporal dynamics of alignment unspecified; no parameter recovery; no model recovery
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - eligibility_flag (MEDIUM): artificial agents used as social partners, though participants believed they were human - effect_size (HIGH): multiple effect sizes reported directly in text - model_params (MEDIUM): group-level means reported for cost-benefit models only; full model (m4) parameter means not separately reported for the holistic model's meta-parameters (sigma_epsilon, sigma_G, Gamma_G, Omega_G)
- **cannot_find:** Mean fitted values for the holistic model's meta-parameters (sigma_epsilon, sigma_G, Gamma_G, Omega_G) -- these are not reported at the group level in main text or supplement. Individual-level parameter estimates not available in paper (only via external data link).
- **other_notes:** Open-access publication in PLoS Computational Biology. Data publicly available. The paper derives both false-consensus and influence biases from first principles (Bayesian optimality). The BPL model includes a variational-Laplace approximation that could serve as an algorithmic-level implementation for neural investigation. The supplement provides full mathematical derivations of the BPL model and the attitude alignment model, VBA adaptive design details, and model inversion diagnostics including best/worst fit plots.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_mentalizing_inference
- spec_depth = structural
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_mentalizing_inference
- tax_model_bayesian
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_param_social_weight
- tax_rr_primary_topic = mentalizing
- tax_rr_secondary_topic = norm_conformity
- tax_rr_topic_mentalizing
- tax_rr_topic_norm_conformity
- tax_topic_mentalizing
- tax_topic_norm_conformity
