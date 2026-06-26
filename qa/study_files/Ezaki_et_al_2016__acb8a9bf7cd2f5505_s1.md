# Ezaki et al. (2016)

- **study_id:** `acb8a9bf7cd2f5505_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Ezaki, T., Horita, Y., Takezawa, M., & Masuda, N. (2016). Reinforcement learning explains conditional cooperation and its moody cousin. *PLoS Computational Biology*, *12*(7), e1005034. https://doi.org/10.1371/journal.pcbi.1005034
- **citation_short:** Ezaki et al. (2016)
- **doi:** 10.1371/journal.pcbi.1005034
- **publication_type:** peer-reviewed journal
- **year:** 2016.0
- **field_of_study:** Psychology
- **affiliations_raw:** InstituteofInformatics,Hitotsubashi,Chiyoda-ku,Tokyo,Japan,4JST,ERATO,KawarabayashiLarge; mits accesstoinformationaboutwhatotherindividualsaredoingsuchthattheycannotexplicitly; DepartmentofBehavioralScience,HokkaidoUniversity,Kita-ku,Sapporo,Japan,6Centerfor; CenterforAdvancedScienceandTechnology,TheUniversityofTokyo,Meguro-ku,Tokyo,; Laboratoryexperimentsusinghumanparticipantshaveshownthat,ingroupsorcontact; CenterforBigDataMathematics,NII,Chiyoda-ku,Tokyo,Japan,; UniversityofBristol,Clifton,Bristol,UnitedKingdom; University,Kita-ku,Sapporo,Japan,7Departmentof; emails: naoki.masuda@bristol.ac
- **code_url:** 

## Computational level
- **study_focus:** Cooperation learning; conditional cooperation and moody conditional cooperation in social dilemma games (prisoner's dilemma and public goods games)
- **study_focus_short:** Cooperation learning
- **learning_mode_description:** - Learning mode: Learning from one's own payoff outcomes about one's own cooperation propensity in repeated social dilemma games   - Learning from:     - Source type (non-social): self       - Not joint     - Source content (non-social): outcome (payoff relative to aspiration level)       - Not joint   - Learning about:     - Target type (social): self (own cooperation probability directed toward others in group/network)       - Not joint     - Target content (social): action/policy (probability of cooperating)       - Not joint
- **task_description:** Simulated agents on a 10x10 square lattice play a repeated two-player Prisoner's Dilemma Game against each of four neighbors (or a repeated Public Goods Game in groups of four) over 25 rounds, updating their cooperation probability via Bush-Mosteller aspiration-based reinforcement learning after each round's payoff.
- **task_paradigm:** Public goods game
- **players:** Multi-agent (100 simulated agents on network; or 4 agents in PGG group), symmetric
- **n_players:** network (5+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract payoff matrix (PDG: R=3, T=5, S=0, P=1); binary cooperation/defection decisions; continuous contributions in PGG
- **method:** behavioural
- **method_full:** behavioural (computational simulation validated against existing human behavioral experiments; no new human data collected)
- **main_result:** - Main Results:   - Bush-Mosteller aspiration learners with aspiration level 0 < A < 1 and moderate-to-high sensitivity beta produce conditional cooperation (CC) patterns matching human behavioral data (positive slope alpha_1 of cooperation probability vs. fraction of cooperative neighbors)   - Moody conditional cooperation (MCC) emerges: players who cooperated last round show CC (positive slope), while players who defected last round show flat or negative slope -- consistent with experimental findings from Grujic et al. (2010, 2012, 2014) and Gracia-Lazaro et al. (2012)   - CC and MCC patterns are robust across network structures (square lattice, regular random graph, complete graph) and persist with up to 50% free riders   - GRIM-like aspiration learning (S < A < P) rather than Pavlov-like (P < A < R) produces patterns consistent with experiments   - CC patterns also found in repeated PGG for appropriate threshold values (0.1 <= X <= 0.4)   - Directional learning rule does NOT produce CC or MCC patterns
- **effect_size:** No traditional effect sizes reported (simulation study). Results are characterized by slopes (alpha_1) and intercepts (alpha_2) of linear fits across parameter space, presented in heat maps rather than as single statistical tests.
- **learning_from:** Self; own payoff outcome (reward relative to aspiration threshold A)
- **learning_about:** Self; own cooperation probability (unconditional propensity to cooperate), which is directed toward social partners  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Bush-Mosteller aspiration learning (parameters: beta [sensitivity], A [aspiration level], epsilon [implementation error]; p_t updated based on stimulus s_{t-1} = tanh[beta(r_{t-1} - A)])
- **model_family:** Agent-based / evolutionary
- **model_class:** PE learning
- **all_models_tested:** [   {"name": "Bush-Mosteller aspiration learning (main model)", "family": "Bush-Mosteller RL", "n_params": 3, "metric": "simulation comparison to behavioral data patterns"},   {"name": "Macy-Flache variant of BM model", "family": "Bush-Mosteller RL (variant)", "n_params": 2, "metric": "simulation comparison"},   {"name": "Noisy GRIM strategy (no RL)", "family": "Conditional strategy", "n_params": 2, "metric": "simulation comparison"},   {"name": "Directional learning", "family": "Reinforcement learning", "n_params": 3, "metric": "simulation comparison"},   {"name": "Cimini-Sanchez model", "family": "Bush-Mosteller RL (conditional)", "n_params": 3, "metric": "analytic/simulation comparison"} ]
- **model_mb_mf:** MF
- **model_params:** - $\beta$ (sensitivity): controls sensitivity of stimulus to reward; range explored 0-2; CC/MCC patterns emerge when $\beta$ > ~0.25. No single fitted value (simulation study). - A (aspiration level): satisfaction threshold; CC/MCC patterns when 0 < A < 1 (GRIM-like regime). No single fitted value. - $\epsilon$ (implementation error): probability of misimplementing intended action; set to 0.2 (default). Not a free parameter. - p_1 (initial cooperation probability): set to 0.5 (default). Not a free parameter. - X (cooperation threshold, PGG only): threshold for binarizing continuous contribution; CC/MCC for 0.1 <= X <= 0.4.
- **social_param:** No explicitly designated social parameter. The aspiration level A implicitly captures social context: when 0 < A < 1 (S < A < P), the learner is sensitive to social outcomes in a way that produces conditional cooperation patterns. The model is notable for NOT requiring any explicit social information (players do not observe others' actions).
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Qualitative pattern matching of simulation outputs to established human behavioral experimental results (CC and MCC slopes from published experiments). No formal statistical model comparison metric (BIC, AIC, etc.).
- **how_model_fit:** simulate-and-compare
- **data_type_fit_to:** choice behavior (cooperation patterns from published behavioral experiments; no new human data fitted)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** No human participants in this study. Simulations used 100 agents (10x10 lattice) over 1,000 simulations for PDG; 4 agents over 25,000 simulations for PGG. Results compared qualitatively to published experiments (e.g., Grujic et al., 2010, N not specified here).
- **population_category:** non-human
- **population_age_range:** 
- **ecological_validity:** Low -- purely computational simulation study. Results are validated only against patterns (slopes) from previously published lab experiments using abstract social dilemma games. No new human behavioral data collected. The social dilemma games themselves (PDG, PGG) are stylized and lack ecological richness.
- **eligibility_flag:** FLAG: (1) No human behavioral data collected in this study -- it is a computational simulation study that compares model outputs to previously published human experimental patterns. (2) The "learning" is simulated, not observed in human participants. (3) Borderline: the paper uses computational modeling and the learning occurs over time in a social context, but no new human data are modeled. May not meet inclusion criterion "Uses human behavioral data" since no participants were tested.
- **concerns:** - No new human data -- this is a simulation study comparing model outputs to qualitative patterns from published experiments - No formal model fitting to individual-level human data; comparison is qualitative (visual pattern matching of slopes) - No parameter recovery, no formal model comparison statistics - Aspiration level A and sensitivity beta are not estimated from data but explored across parameter space - The paper does not distinguish individual differences in strategies - Simulated agents are homogeneous (except for free-rider simulations)
- **limitations_reported:** Examining the possibility of MCC patterns in the repeated PGG with experimental data warrants future research"; "applying the BM model and examining the relevance of noisy GRIM in the existing and new experimental data may be fruitful exercises"; the authors note that their results are based on simulations and validated against published experimental patterns rather than direct fitting to new data.
- **limitations_categorized:** no direct human data fitting; simulation-only validation; limited ecological validity; qualitative rather than quantitative model comparison; no individual differences modeled; no parameter recovery; task simplicity
- **preregistered:** No
- **wc_rule1:** 
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** No
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
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - `eligibility_flag` (MEDIUM): No new human behavioral data collected; purely simulation study. Borderline for inclusion criterion "Uses human behavioral data." - `effect_size` (LOW): No traditional effect sizes; simulation study reports heat maps and slopes across parameter space. - `social_param` (MEDIUM): No parameter is explicitly social; the model's social nature comes from the game structure, not from a parameter that references others' actions. - `model_comparison_metric` (MEDIUM): No formal metric; comparison is qualitative. - `how_model_fit` (HIGH): Clearly simulate-and-compare.
- **cannot_find:** - Formal effect sizes (not applicable to simulation study) - Individual-level parameter estimates (not applicable) - Neural data or coordinates (no neuroimaging)
- **other_notes:** This is a computational/theoretical paper that uses simulations of the Bush-Mosteller aspiration learning model to explain experimentally observed conditional cooperation (CC) and moody conditional cooperation (MCC) patterns in repeated social dilemma games. The key insight is that myopic aspiration learners who do not observe others' actions can nevertheless produce CC and MCC patterns when the aspiration level falls in the GRIM-like regime (S < A < P). The model is simpler and more cognitively plausible than the Cimini-Sanchez (2014) model. No new human data are collected or fitted. The paper should be flagged for eligibility review given the absence of direct human behavioral data fitting.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+context
- spec_target = partly
- tax_domain_C_exchange_interdependence
- tax_mod_active_interaction
- tax_mod_experiential
- tax_mod_multiplayer_live
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_agent_based_evolutionary
- tax_rr_model_family = agent_based_evolutionary
- tax_rr_param_learning_rate
- tax_rr_param_temperature
- tax_rr_primary_topic = cooperation
- tax_rr_secondary_topic = reciprocity
- tax_rr_topic_cooperation
- tax_rr_topic_reciprocity
- tax_topic_cooperation
- tax_topic_reciprocity
