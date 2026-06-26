# Realpe-Gomez et al. (2018)

- **study_id:** `a2c08d3018fe4637d_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Realpe-Gomez, J., Andrighetto, G., Nardin, L. G., & Montoya, J. A. (2018). Balancing selfishness and norm conformity can explain human behavior in large-scale Prisoner's Dilemma games and can poise human groups near criticality. *Physical Review E*, 97(4), 042321.
- **citation_short:** Realpe-Gomez et al. (2018)
- **doi:** 10.1103/PhysRevE.97.042321
- **publication_type:** peer-reviewed journal
- **year:** 2018.0
- **field_of_study:** Cognitive science
- **affiliations_raw:** Institute of Cognitive Sciences and Technologies, National Research Council, Rome, 00185 Italy; mpirical and fieldwork evidence is velop here an analytically-tractable model in which the; Centre for Theoretical Physics, Strada Costiera 11, 34151, Trieste, Italy; Laboratory, NASA Ames Research Center, Moffett Field, CA 94035, USA; Institute of Cognitive Sciences and Technologies,; University of Technology, Cottbus, 03046 Germany; mity can explain human behavior in large-scale; centreview), mostofthesemodelsaretheoretical; emails: john.realpe@gmail.com
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning; norm conformity learning; social norm influence on cooperation in social dilemmas
- **study_focus_short:** Cooperation learning · norm conformity learning
- **learning_mode_description:** - Learning mode: Learning from one's own and neighbors' cooperation/defection outcomes about optimal cooperation strategy balancing selfish payoffs and social norm compliance   - Learning from:     - Source type (non-social): self       - Source content (non-social): outcome (material payoffs from PD game)     - Source type (social): other (neighbors in network)       - Source content (social): action/policy (cooperation/defection decisions of neighbors)   - Learning about:     - Target type (non-social): self       - Target content (non-social): action/policy (own cooperation probability)     - Target type (social): group (social norm compliance level)       - Target content (social): state (norm salience; group cooperation norm)
- **task_description:** Participants played a repeated weak Prisoner's Dilemma game with all their neighbors on a virtual network (either a 25x25 lattice or a heterogeneous network) for 52 rounds, choosing to cooperate or defect with the same action against all opponents, receiving payoffs of 7 ECUs for mutual cooperation, 10 ECUs for defection against a cooperator, and 0 ECUs when facing a defector.
- **task_paradigm:** Prisoner's dilemma
- **players:** Multi-agent (625 on lattice; 604 on heterogeneous network), network-based interactions (4 neighbors on lattice; 2-16 on heterogeneous network)
- **n_players:** network (5+)
- **partner_type:** human (live)
- **stimuli:** Abstract binary choice (cooperate/defect), monetary payoffs in Experimental Currency Units (ECUs), information about neighbors' actions and normalized payoffs
- **method:** behavioural
- **method_full:** behavioural (re-analysis of existing experimental data from Garcia-Lazaro et al., 2012)
- **main_result:** - Main Results:   - Model quantitatively reproduces decay of global cooperation from ~60% to ~35% over 52 rounds on both network topologies   - Model reproduces moody conditional cooperation (MCC) rule: probability of cooperation as a function of neighbors' cooperation, conditioned on own previous action   - Human groups found to be poised near a critical point in the model's phase diagram (relative Euclidean distance to critical line: 3% for heterogeneous network, 11% for lattice)   - Network topology does not significantly affect cooperation dynamics, consistent with absence of network reciprocity
- **effect_size:** Relative distance to critical point: delta = 0.03 (heterogeneous network), delta = 0.11 (square lattice); no standard effect sizes (Cohen's d, r, etc.) reported; model fit is assessed visually and via Bayesian inference
- **learning_from:** Self (own payoffs) and others (neighbors' cooperation/defection actions); source: self + other (neighbors in network)
- **learning_about:** Own cooperation strategy (self); social norm salience and compliance (group)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Norm-augmented EWA (Experience Weighted Attraction): x(t+1) = x(t)^(1-alpha) / [x(t)^(1-alpha) + (1-x(t))^(1-alpha) * exp(-beta * Delta_U[x(t)])], where Delta_U[x] = aKx^2 + (bK + 2h)x - h; 4 effective parameters (alpha, A, x_0, y_0) in the mean-field single-agent model
- **model_family:** Utility / EV
- **model_class:** PE learning
- **all_models_tested:** [{"name": "Norm-augmented EWA (full model with MCC, self-consistency, social influence)", "family": "EWA + normative", "n_params": 4, "metric": "Bayesian inference (pomp PMCMC)"}] - Note: The paper does not formally compare multiple competing models via model comparison metrics. It presents one model and validates it against experimental data. References to MCC behavioral rule and reinforcement learning models (Horita et al.) are discussed qualitatively but not formally compared in this paper.
- **model_mb_mf:** MB/MF hybrid (EWA combines model-free reinforcement learning and model-based belief learning with equal weight)
- **model_params:** - alpha (memory decay): controls exponential discount of past events; alpha_hat = 0.263 (heterogeneous network), 0.4417 (lattice) - beta (bounded rationality / inverse temperature): success in choosing optimal strategy; small beta assumed - h [S] (norm weight): relative influence of normative vs selfish considerations in utility - w_C [S] (self-consistency weight): set to 1; agent's own norm compliance increases norm salience - w_O [S] (social influence weight): norm salience increases with number of compliant peers - w_I [S] (MCC interaction weight): social influence stronger when aligned with self-consistency - a = h*w_I/K [S] (effective MCC parameter) - b = (h*w_O + Delta_I_C)/K [S] (effective social influence + payoff parameter) - Effective parameters: A_hat = 1.16 (heterogeneous), 1.413 (lattice); x_0_hat = -0.24 (heterogeneous), 0.0483 (lattice); y_0_hat = -0.71 (heterogeneous), -0.4346 (lattice)
- **social_param:** h (norm weight): weights relative influence of normative vs selfish motivations; w_O (social influence): norm salience increases with number of cooperating peers; w_I (MCC interaction): social influence conditional on own cooperation (moody conditional cooperation)
- **social_param_name:** h
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** No formal model comparison metric (no BIC/AIC/LOOIC). Bayesian inference via particle Markov chain Monte Carlo (PMCMC) using R package pomp; model validated by visual fit to experimental cooperation dynamics and MCC rule.
- **how_model_fit:** individual-level-fit (mean-field representative agent parameters estimated from aggregate experimental data via Bayesian inference)
- **data_type_fit_to:** choice behavior (cooperation rates over time; moody conditional cooperation probabilities)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 625 (square lattice experiment) + N = 604 (heterogeneous network experiment); from Garcia-Lazaro et al. (2012) experiments conducted in Zaragoza
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate-low. Laboratory-based large-scale network game with real monetary incentives, but abstract PD framing with binary choices; no face-to-face interaction; participants only see actions and payoffs of virtual neighbors. Large scale (600+ participants) is more ecologically valid than typical small-group experiments.
- **eligibility_flag:** The paper presents a computational model fitted to existing human behavioral data from a social learning context (cooperation dynamics over 52 rounds). However, the model is primarily a *theoretical physics model* validated against existing experimental data rather than a new behavioral experiment. The learning occurs over time (52 rounds) and involves social context (neighbors' behavior). The paper meets inclusion criteria but should be noted as a modeling/theory paper applying to existing data.
- **concerns:** - The paper does not conduct new experiments; it re-analyzes data from Garcia-Lazaro et al. (2012). - No formal model comparison against alternative models (only qualitative discussion of how the model differs from MCC rule and Horita et al.'s RL models). - The mean-field approximation reduces all individual heterogeneity to a single representative agent. - Parameter beta is left undetermined; only products beta*a, beta*b, beta*h are estimated. - No parameter recovery or model recovery analyses performed. - No posterior predictive checks beyond visual comparison of model trajectories to data.
- **limitations_reported:** Clearly, more theoretical and empirical work is needed to reach solid conclusions"; the model relies on mean field approximation that neglects individual heterogeneity; the adiabatic approximation may not capture the initial transient regime well; experiments with varying payoff matrices are needed to more directly address findings; the model is restricted to static networks; it may be difficult to observe signatures of criticality in experimental setups with human groups of fixed size.
- **limitations_categorized:** limited generalizability; model simplification (mean-field approximation); task simplicity; limited ecological validity; no formal model comparison; no parameter recovery
- **preregistered:** No
- **wc_rule1:** 
- **wc_rule2:** No
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 3.5
- **wc_total:** 3.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - doi: MEDIUM confidence (not explicitly printed as DOI string in extracted text; inferred from journal, year, volume) - effect_size: LOW confidence (no standard effect sizes reported; only relative distance to critical point and visual fit) - all_models_tested: MEDIUM (only one model is formally presented; alternatives discussed but not formally tested) - model_comparison_metric: LOW (no formal model comparison metric used)
- **cannot_find:** - Exact DOI string (not in extracted text; would need publisher lookup) - Formal effect sizes (Cohen's d, r, beta, etc.) -- paper uses physics-style validation (visual fit, Bayesian posterior) - Formal model comparison results (no BIC/AIC/etc.) - Parameter beta exact fitted value (only products beta*a, beta*b, beta*h estimated) - Code/data availability statement
- **other_notes:** This paper is from a statistical physics / complex systems perspective rather than a traditional cognitive neuroscience or behavioral economics perspective. It uses mean-field theory and phase diagram analysis, which is unusual in the social learning literature. The model is an extension of Experience Weighted Attraction (EWA) learning with a normative component incorporating self-consistency, social influence, and moody conditional cooperation. The experimental data analyzed is from Garcia-Lazaro et al. (2012, PNAS). The finding that human groups poise near criticality is the paper's most novel contribution.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_A_influence_transmission
- tax_domain_C_exchange_interdependence
- tax_mod_cultural_network
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_model_MB
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_social_weight
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
