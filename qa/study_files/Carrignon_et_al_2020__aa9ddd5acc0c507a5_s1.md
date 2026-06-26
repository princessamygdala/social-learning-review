# Carrignon et al. (2020)

- **study_id:** `aa9ddd5acc0c507a5_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Carrignon, S., Brughmans, T., & Romanowska, I. (2020). Tableware trade in the Roman East: Exploring cultural and economic transmission with agent-based modelling and approximate Bayesian computation. *PLoS ONE*, *15*(11), e0240414. https://doi.org/10.1371/journal.pone.0240414
- **citation_short:** Carrignon et al. (2020)
- **doi:** 10.1371/journal.pone.0240414
- **publication_type:** peer-reviewed journal
- **year:** 2020.0
- **field_of_study:** Psychology
- **affiliations_raw:** University,Aarhus,Denmark,3CASE,BarcelonaSupercomputingCentre,Barcelona,Spain,4Department; CenterfortheDynamicsofSocialComplexity(DySoC),UniversityofTennessee,Knoxville,TN,United; UniversityofTennessee,Knoxville,TN,UnitedStatesofAmerica,5SchoolofInformation; labilityofreliablecommercialinformationisconsideredakeyfeatureofinter-; labilityofreliablecommercialinformationisconsideredaconditionfor; InstituteofAdvancedStudies,AarhusUniversity,Aarhus,Denmark; UniversityofTennessee,Knoxville,TN,UnitedStatesofAmerica; ethesignificantlimitationsimposedbythethen-currenttrans-; emails: scarrign@utk.edu
- **code_url:** https://osf.io/s5mdw/

## Computational level
- **study_focus:** Social transmission of economic strategies (cultural transmission of trading strategies among agents in a competitive market; independent learning vs. social learning of buying strategies)
- **study_focus_short:** Social transmission of economic strategies (cultural transmission of trading
- **learning_mode_description:** - Learning mode: Agents (sets of traders at settlements) may copy or independently innovate economic strategies (tableware buying value-lists) from other agents   - Learning from:     - Source type (social): other (traders at other settlements)       - In independent learning model: Source type (non-social): self (own innovation)     - Source content (social): action/policy (economic buying strategies — value vectors assigned to goods)   - Learning about:     - Target type (non-social): world (tableware market; which goods to value)     - Target content (non-social): action/policy (buying/trading strategy for tableware goods)
- **task_description:** An agent-based model simulates 500 agents (each representing traders at one urban settlement) trading five types of tableware over 500 years (200 BC to AD 300) in the eastern Mediterranean. Agents produce, trade, and consume goods, and may update their buying strategies through independent innovation, unbiased social learning (random copying), or success-biased social learning (copying more successful agents), with approximate Bayesian computation used to evaluate which mechanism best reproduces archaeological distribution patterns.
- **task_paradigm:** Stereotype learning task
- **players:** Multi-agent (500 simulated settlement-agents), symmetric
- **n_players:** 
- **partner_type:** human (live)
- **stimuli:** Archaeological ceramic tableware distribution data (presence/absence of 5 ware types: ESA, ESB, ESC, ESD, ITS across 178 sites from the ICRATES database), agent-based model simulations
- **method:** behavioural
- **method_full:** behavioural (computational modeling with agent-based simulation; no human participants)
- **main_result:** - Main Results:   - Independent Learning model best explains archaeological tableware distribution data (Bayes Factor K = 1.96 vs. Unbiased Social Learning; K = 23.5 vs. Success-biased Social Learning)   - Success-biased social learning is not a viable theory for tableware trade patterns   - Independent learning posterior parameters: economic interactions 1.5-3.4/year (75% HDR); cultural interactions once every 3.6-7.9 years (75% HDR); innovation rate 8.8%-51% (75% HDR)   - Posterior distributions for Independent Learning and Unbiased Social Learning are very similar except for rate of social learning parameter
- **effect_size:** Bayes Factor: Independent vs. Unbiased = 1.96; Independent vs. Success-biased = 23.5; Unbiased vs. Success-biased = 12
- **learning_from:** Other agents' economic strategies (social learning models); own innovation (independent learning model). Source: other / self.
- **learning_about:** Optimal tableware buying strategy (value vectors for goods). Target: world (market goods).  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Independent Learning (innovation only; no cultural transmission; parameters: t, $\omega$, $\mu$, $\mu_{max}$)
- **model_family:** Agent-based / evolutionary
- **model_class:** Other
- **all_models_tested:** - {"name": "Independent Learning", "family": "Agent-based cultural evolution (innovation only)", "n_params": 4, "metric": "ABC Bayes Factor"} - {"name": "Unbiased Social Learning", "family": "Agent-based cultural evolution (random copying)", "n_params": 6, "metric": "ABC Bayes Factor"} - {"name": "Success-biased Social Learning", "family": "Agent-based cultural evolution (success-biased copying)", "n_params": 6, "metric": "ABC Bayes Factor"}
- **model_mb_mf:** N/A (not RL)
- **model_params:** - t: total number of economic interactions (prior: U(50,1000); posterior 75% HDR: 750-1700) - $\omega$: number of economic interactions per cultural interaction (prior: U(1,50)) - CI: total number of cultural interactions (derived: t x $\omega^{-1}$; posterior 75% HDR: 63-140) - $\mu$: rate of innovation (prior: U(0,1); posterior 75% HDR: 0.088-0.51) - $\mu_{max}$: variance of innovation (prior: U(0,10)) - $\lambda$ [S]: rate of social learning (prior: U(0,1); not used in winning Independent Learning model) - $\lambda_{str}$ [S]: strength of social learning bias (prior: U(0,10); not used in winning Independent Learning model) - N: total number of agents (fixed: 500) - n_good: number of types of goods (fixed: 3-6 depending on period)
- **social_param:** $\lambda$ (rate of social learning) and $\lambda_{str}$ (strength of social learning bias) — both present only in the social learning models, not in the winning Independent Learning model. These parameters govern the probability and strength of strategy copying between agents.
- **social_param_name:** $\lambda$
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Approximate Bayesian Computation (ABC) with Population Monte Carlo (PMC); Bayes Factor computed from ABC posterior likelihoods
- **how_model_fit:** simulate-and-compare (ABC-PMC: 13 decreasing epsilon steps, 500 accepted simulations per step; total simulation runs: 206,902 for Independent Learning, 564,211 for Unbiased, 1,267,560 for Success-biased)
- **data_type_fit_to:** Archaeological distribution data (presence/absence of ceramic tableware at 178 sites across 50 time bins)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A (no neuroimaging)  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 500 simulated agents (representing urban settlements); empirical data from 178 archaeological sites with 8730 datable ceramic entries from the ICRATES database. No human behavioral participants.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** High ecological validity for an archaeological modeling study: the model is grounded in a large, well-curated empirical dataset (ICRATES) covering 500 years and 178 sites across the eastern Mediterranean. However, agents represent aggregated settlement-level behavior rather than individual decision-makers, and the model simplifies many aspects of ancient trade (e.g., transport costs, geographic distance, political factors).
- **eligibility_flag:** FLAGGED — Does not meet inclusion criteria. This study uses computational modeling and learning occurs over time, but it does NOT use human behavioral data (it uses archaeological ceramic distribution data and agent-based simulations). The "agents" are simulated settlement-level entities, not human participants. The learning context is social (cultural transmission of economic strategies), but there are no human participants generating behavioral data. Flag: "No human behavioral data; archaeological/simulation study only.
- **concerns:** - No human participants — agents are simulated settlement-level entities fitted to archaeological data, not human behavior - The "social learning" studied is cultural transmission at a civilization-wide scale over centuries, not individual-level social learning as typically studied in computational psychiatry - The winning model (Independent Learning) actually has NO social learning component — it is pure innovation/independent change - Model comparison uses Bayes Factors from ABC which provide relative rather than absolute model evidence - Very wide posterior distributions suggest limited identifiability of parameters
- **limitations_reported:** the credible parameter ranges are wide, this is not unexpected in a study of an economic system that functioned two millennia ago where very little information is available that would enable narrowing prior distributions of parameters"; "the high dimensionality, the noise and the low resolution of the dataset made summarising the data and comparing it with the simulation a challenge"; "no one model would be able to match the data correctly" due to averaging across periods with different numbers of competing wares; "the assumption used here that each ware was a commodity for which a distinct demand existed is not appropriate" may affect results; results revealed little about the role of ITS specifically
- **limitations_categorized:** Limited parameter identifiability; low data resolution; model simplification; questionable assumptions about demand structure; limited generalizability; aggregation across heterogeneous time periods
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** Yes
- **wc_rule3:** Yes
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
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - eligibility_flag: HIGH confidence — paper clearly uses archaeological data and simulated agents, not human behavioral data - learning_mode: MEDIUM confidence — the "social" aspect is cultural transmission between simulated settlement-agents, not interpersonal social learning - model_params (posterior values): HIGH confidence — directly reported in text and figures - wc_guidelines Rule 8: MEDIUM confidence — ABC implicitly checks model fit but no explicit posterior predictive check section
- **cannot_find:** No human behavioral data metrics; no neuroimaging data; no individual-level parameters; no supplement was available (supporting information consists of S1 Fig, S2 Fig, and S1 File with source code, all referenced but not included as separate documents)
- **other_notes:** This is an archaeological computational modeling study applying cultural evolution / cultural transmission theory to explain ceramic tableware distribution patterns in the Roman eastern Mediterranean (200 BC - AD 300). While it formally models social learning strategies (independent learning, unbiased social learning, success-biased social learning), the "learners" are simulated agents representing settlements, not human participants. The paper is methodologically rigorous within its domain (archaeology + cultural evolution) but falls outside the typical scope of a computational psychiatry/psychology systematic review of social learning. The winning model is the Independent Learning model, which paradoxically contains NO social learning — it suggests traders changed strategies independently rather than through copying. Supplement not accessible as a separate file (supporting figures and code are referenced but stored on OSF).
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_cultural_network
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source
- spec_source = social
- spec_target = partly
- tax_domain_A_influence_transmission
- tax_mod_cultural_network
- tax_mod_experiential
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_agent_based_evolutionary
- tax_rr_model_family = agent_based_evolutionary
- tax_rr_param_social_weight
- tax_rr_primary_topic = cultural_transmission
- tax_rr_topic_cultural_transmission
- tax_topic_cultural_transmission
