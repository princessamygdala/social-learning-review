# Realpe-Gomez et al. (2018)

- **study_id:** `a23346253c62b30ea_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Realpe-Gomez, J., Andrighetto, G., Nardin, L. G., & Montoya, J. A. (2018). Balancing selfishness and norm conformity can explain human behavior in large-scale Prisoner's Dilemma games and can poise human groups near criticality. *Physical Review E*. (Note: The paper lists affiliations including NASA Ames, ISTC-CNR Rome, and Universidad de Cartagena. The exact journal/volume/year should be confirme
- **citation_short:** Realpe-Gomez et al. (2018)
- **doi:** Not explicitly stated in the extracted text. `cannot_find`: DOI not found in the full text.
- **publication_type:** peer-reviewed journal---
- **year:** 2018.0
- **field_of_study:** Cognitive science
- **affiliations_raw:** Institute of Cognitive Sciences and Technologies, National Research Council, Rome, 00185 Italy; mpirical and fieldwork evidence is velop here an analytically-tractable model in which the; Centre for Theoretical Physics, Strada Costiera 11, 34151, Trieste, Italy; Laboratory, NASA Ames Research Center, Moffett Field, CA 94035, USA; Institute of Cognitive Sciences and Technologies,; University of Technology, Cottbus, 03046 Germany; mity can explain human behavior in large-scale; centreview), mostofthesemodelsaretheoretical; emails: john.realpe@gmail.com
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning / norm conformity learning -- how humans balance selfish reward maximization and social norm compliance in repeated large-scale Prisoner's Dilemma games, and whether this learning dynamic poises groups near criticality.
- **study_focus_short:** Cooperation learning / norm conformity learning -- how humans balance selfish
- **learning_mode_description:** - Learning mode: Learning from own and neighbors' cooperative/defective actions and payoffs about optimal cooperation strategy balancing selfishness and norm conformity   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (own material payoffs)     - Source type (social): group (neighbors in network)       - Source content (social): action/policy (neighbors' cooperation/defection decisions)   - Learning about:     - Target type (non-social): self       - Target content (non-social): action/policy (own cooperation probability)     - Target type (social): group (social norm salience)       - Target content (social): state (norm salience / perceived descriptive norm)
- **task_description:** Participants played a repeated weak Prisoner's Dilemma game with all their network neighbors for 52 rounds on either a 25x25 square lattice (K=4, N=625) or a heterogeneous network (K=2-16, N=604), making a single cooperate/defect decision per round applied to all neighbors, with payoffs of 7 ECU for mutual cooperation, 10 ECU for defecting against a cooperator, and 0 ECU otherwise.
- **task_paradigm:** Prisoner's dilemma
- **players:** Multi-agent (625 or 604 participants), network-structured interactions (4 neighbors on lattice; 2-16 on heterogeneous network).
- **n_players:** network (5+)
- **partner_type:** human (live)
- **stimuli:** Abstract binary choice (cooperate/defect), monetary payoffs in ECU, information about neighbors' actions and normalized payoffs from previous round.
- **method:** behavioural
- **method_full:** Behavioural (computational modeling of existing experimental data from Garcia-Lazaro et al., 2012).
- **main_result:** - The norm-augmented EWA model quantitatively reproduces the global cooperation decay from ~60% to ~35% over 52 rounds in both network conditions - The model reproduces the Moody Conditional Cooperation (MCC) rule: probability of cooperation is near-linear in fraction of cooperating neighbors, with a gap between cooperators and defectors - Bayesian parameter inference places the human group at relative Euclidean distance of 3% (heterogeneous network) and 11% (square lattice) from the critical line in the model's phase diagram - Self-consistency (w_C), social influence (w_O), and moody conditional cooperation (w_I) parameters all play qualitatively essential roles -- removing any one contradicts experimental observations - No effect sizes reported in the conventional sense (Cohen's d, r, etc.); the paper reports model-data agreement visually and via Bayesian parameter estimation
- **effect_size:** No conventional effect sizes reported. Model fit assessed via Bayesian inference (posterior parameter distributions) and visual comparison of model predictions vs. experimental data (Figures 2a-d). Relative distance to criticality: delta = 0.03 (heterogeneous) and delta = 0.11 (lattice).
- **learning_from:** Self (own payoffs) and group (neighbors' actions/cooperation fraction).
- **learning_about:** Self (own cooperation strategy) and group (social norm salience).---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Norm-augmented EWA with mean field approximation. x(t+1) = x(t)^(1-alpha) / [x(t)^(1-alpha) + (1-x(t))^(1-alpha) * exp(-beta * Delta_U[x(t)])], where Delta_U[x] = aKx^2 + (bK + 2h)x - h. Effective 4 parameters: alpha, A, x_0, y_0.
- **model_family:** Utility / EV
- **model_class:** PE learning
- **all_models_tested:** Only one model is formally tested/fitted. The paper compares qualitatively against: - [{"name": "Norm-augmented EWA (mean field)", "family": "EWA/hybrid RL", "n_params": 4, "metric": "Bayesian inference (pomp/pMCMC)"}] - The paper discusses but does not formally compare: pure RL models (Horita et al., 2017), MCC behavioral rule (Grujic et al., 2010), evolutionary dynamics models (Cimini & Sanchez, 2014; Vilone et al., 2014), conditional cooperation models. These are discussed as qualitative baselines but not subjected to formal model comparison.
- **model_mb_mf:** MB/MF hybrid (EWA combines model-free reinforcement learning and model-based belief learning with equal weight).
- **model_params:** - alpha: memory decay parameter (alpha ~ 0.263 for heterogeneous network, alpha ~ 0.442 for lattice) -- controls exponential discounting of past events - beta: bounded rationality / inverse temperature parameter (not independently identified; only beta*a, beta*b, beta*h estimated) - h [S]: norm weighting parameter -- relative weight of normative vs. selfish considerations - w_C [S]: self-consistency parameter (set to 1) -- norm salience increases when agent complied with norm - w_O [S]: social influence parameter -- norm salience increases with fraction of compliant peers - w_I [S]: moody conditional cooperation parameter -- social influence modulated by own prior cooperation - Effective parameters: A (~ 1.16 heterogeneous, ~ 1.41 lattice), x_0 (~ -0.24 heterogeneous, ~ 0.048 lattice), y_0 (~ -0.71 heterogeneous, ~ -0.43 lattice)
- **social_param:** h [S] (norm weight: relative influence of social norm compliance vs. selfish payoff maximization); w_I [S] (moody conditional cooperation: social influence conditional on own cooperation); w_O [S] (social influence: norm salience from peers' behavior).
- **social_param_name:** h
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Bayesian inference via particle Markov chain Monte Carlo (pMCMC) using the R package pomp. No formal model comparison metric (BIC, AIC, etc.) reported -- only one model is fitted.
- **how_model_fit:** Group-level fit via Bayesian inference (posterior parameter estimation using partially observed Markov process framework; pomp package). Parameters inferred from aggregate experimental data (global cooperation dynamics + MCC slopes/intercepts from Garcia-Lazaro et al., 2012).
- **data_type_fit_to:** Choice behavior (cooperation rates over time; conditional cooperation probabilities).---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A -- no neuroimaging.
- **key_regions:** N/A -- no neuroimaging.
- **coordinates_peak:** N/A -- no neuroimaging.
- **analysis_type:** N/A (no neuroimaging).---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=625 (square lattice experiment) and N=604 (heterogeneous network experiment); data from Garcia-Lazaro et al. (2012). The paper models data from these two experiments.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Limited ecological validity. The task is a stylized economic game (Prisoner's Dilemma) played on virtual networks in a laboratory. Decisions are binary (cooperate/defect) with abstract monetary payoffs. However, the large sample size (625 and 604 participants playing simultaneously) and the 52-round duration provide more realistic group dynamics than typical small-group experiments. The network structure adds some ecological realism.
- **eligibility_flag:** The paper uses computational modeling on human behavioral data in a social context with learning over time (52 rounds of repeated PD). However, the authors did not collect their own data -- they model existing experimental data from Garcia-Lazaro et al. (2012). The primary contribution is theoretical (statistical physics model + mean field analysis + criticality). The "learning" is modeled at the aggregate/representative-agent level via a mean field approximation, which is a simplification of individual-level learning. **Flag: The paper is primarily a theoretical/computational physics paper that fits a single model to existing aggregate experimental data. No formal model comparison is conducted (only one model tested). The learning is modeled at the group level via a representative agent, not at the individual level.**
- **concerns:** - No formal model comparison: only one model is fitted. The paper discusses alternative models qualitatively but does not compare them quantitatively using model selection criteria (BIC, AIC, etc.). - The mean field approximation reduces a multi-agent system to a single representative agent, losing individual heterogeneity. - The parameter beta is not independently identifiable -- only products beta*a, beta*b, beta*h are estimated. - The paper models aggregate-level data from Garcia-Lazaro et al. (2012) rather than collecting new data or fitting individual-level behavior. - The adiabatic (slow adaptation) approximation and mean field approximation are strong assumptions. - The claim of "near criticality" (3% and 11% distance) lacks a formal statistical test of whether this is significantly closer than expected by chance. - No parameter recovery or model recovery analysis. (HIGH)
- **limitations_reported:** More theoretical and empirical work is needed to reach solid conclusions"; machine learning techniques could provide complementary data-driven analysis; experiments varying model parameters (e.g., payoff matrices) are needed; the mean field model neglects individual heterogeneity; the adiabatic approximation may not capture initial transient dynamics well; the model is restricted to static networks; the equal weighting of model-free and model-based RL is a simplification; the connection between group-level criticality and brain-level criticality is an open question.
- **limitations_categorized:** Limited ecological validity; model simplicity (mean field approximation); parameter identifiability; no model comparison; no parameter recovery; reliance on secondary data; strong analytical assumptions (adiabatic approximation); limited generalizability (static networks only); no formal statistical test of criticality claim.
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** No
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 4.0
- **wc_total:** 4.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** 
- **cannot_find:** 
- **other_notes:** 
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_multiplayer_live
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_decay
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = utility_EV
- tax_rr_model_utility_EV
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = cooperation
- tax_rr_topic_cooperation
- tax_rr_topic_norm_conformity
- tax_topic_cooperation
- tax_topic_norm_conformity
