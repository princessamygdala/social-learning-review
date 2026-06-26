# Benistant et al.

- **study_id:** `a6775e847c8afacd3_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Benistant, J., Soltani, A., Moisan, F., & Dreher, J.-C. (n.d.). Computational learning mechanisms of information propagating in social networks. *Manuscript*.
- **citation_short:** Benistant et al.
- **doi:** Not available — not stated in the paper.
- **publication_type:** unclear — likely preprint or manuscript under review (no journal indicated).
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** Laboratory of Neuroeconomics, Institut des Sciences Cognitives Marc Jeannerod, CNRS, Lyon, France; DEPTH) within the Programme Investissements d’Avenir (ANR-16-IDEX-0005) and of the LABEX; Department of Psychological and Brain Sciences, Dartmouth College, Hanover, NH, USA; LABX-0042) of Université de Lyon, within the program Investissements d’Avenir; MITI 2020 CNRS to JCD, and NSF CRCNS grant (BCS2423824) to; CNRS, IESEG School of Management, UMR 9221 - LEM - Lille; Université Claude Bernard Lyon 1, Lyon, France; School, GATE, CNRS, Lyon, France; emails: julien.benistant@univ-lille.fr, dreher@
- **code_url:** 

## Computational level
- **study_focus:** Social network learning — how individuals integrate private and socially propagated information in networked environments, comparing DeGroot averaging vs. reinforcement learning update rules.
- **study_focus_short:** Social network learning
- **learning_mode_description:** - Learning mode: Learning from neighbors' predictions in a social network about the true state of the world (which bag was selected).   - Learning from:     - Source type (social): others (network neighbors)     - Source content (social): action/policy (neighbors' binary predictions about bag identity)   - Learning about:     - Target type (non-social): world (true state — which bag was selected)     - Target content (non-social): state (world state — bag identity)
- **task_description:** Participants assigned to nodes in a social network received a private signal (colored marble drawn from one of two bags) and made an initial prediction about which bag was selected. Over subsequent stages, they observed neighbors' previous predictions and could revise their own prediction. Two datasets were used: Jiang et al. (2023; 7-person networks, 3 update stages, sequential neighbor presentation) and Choi et al. (2023; 40-person networks, 11 update stages, free neighbor sampling, 4 network topologies).
- **task_paradigm:** Social network learning
- **players:** - Dataset 1 (Jiang): Multi-agent (7-person networks), dynamic interaction - Dataset 2 (Choi): Multi-agent (40-person networks), dynamic interaction across 4 network topologies (ER, RF, RGG, SB)
- **n_players:** network (5+)
- **partner_type:** human (live)
- **stimuli:** Colored marbles (blue/yellow or green/red), binary predictions, network topology visualizations.
- **method:** fMRI / behavioural
- **method_full:** Behavioural (computational modeling of two existing behavioural datasets; no new data collection). One dataset (Jiang et al.) included fMRI but the current paper does not analyze neural data.
- **main_result:** - Main Results:   - Dataset 1 (Jiang et al.): W-DG model provided the overall best fit (highest exceedance probability via BMS). ~40% of individual participants were best fit by W-RL, indicating heterogeneity in learning strategies.   - Dataset 2 (Choi et al.): N-DG model provided the overall best fit (highest exceedance probability via BMS). Significant fraction best fit by W-DG or W-RL variants.   - Network topology influenced which model best fit: RF networks favored W-DG; other topologies favored N-DG.   - Simulations: W-DG significantly outperformed W-RL in accuracy for Jiang et al. networks; W-DG significantly outperformed all models except W-RL in consensus. For Choi et al., DG models and W-RL outperformed N-RL in accuracy and consensus.   - Minimum-difference learning rate (where RL ≈ DG) decreases as a power law with increasing number of neighbors.   - Network size increased accuracy but decreased consensus; edge density increased both; no significant model differences for size/density effects.  - Effect sizes: No standard effect sizes (Cohen's d, r, eta-squared, etc.) are reported in the paper. Results are presented as exceedance probabilities, regression contrasts with Bonferroni-corrected p-values, and simulation comparisons. Specific EP values and regression coefficients are shown in figures but not reported numerically in the text for the main comparisons.
- **effect_size:** - Main Results:   - Dataset 1 (Jiang et al.): W-DG model provided the overall best fit (highest exceedance probability via BMS). ~40% of individual participants were best fit by W-RL, indicating heterogeneity in learning strategies.   - Dataset 2 (Choi et al.): N-DG model provided the overall best fit (highest exceedance probability via BMS). Significant fraction best fit by W-DG or W-RL variants.   - Network topology influenced which model best fit: RF networks favored W-DG; other topologies favored N-DG.   - Simulations: W-DG significantly outperformed W-RL in accuracy for Jiang et al. networks; W-DG significantly outperformed all models except W-RL in consensus. For Choi et al., DG models and W-RL outperformed N-RL in accuracy and consensus.   - Minimum-difference learning rate (where RL ≈ DG) decreases as a power law with increasing number of neighbors.   - Network size increased accuracy but decreased consensus; edge density increased both; no significant model differences for size/density effects.  - Effect sizes: No standard effect sizes (Cohen's d, r, eta-squared, etc.) are reported in the paper. Results are presented as exceedance probabilities, regression contrasts with Bonferroni-corrected p-values, and simulation comparisons. Specific EP values and regression coefficients are shown in figures but not reported numerically in the text for the main comparisons.
- **learning_from:** Others (network neighbors); neighbors' binary predictions about the state of the world.
- **learning_about:** World; the true state of the world (which bag of marbles was selected).
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** - Dataset 1 (Jiang et al.): Weighted DeGroot (W-DG): E_i,s = C_i,s-1 * RD_i + sum(RD_j * C_j,s-1) where RD_j = degree_j / sum_degrees. 1 free parameter: β (inverse temperature). - Dataset 2 (Choi et al.): Naive DeGroot (N-DG): E_i,s = (C_i,s-1 + sum(C_j,s-1)) / (N_i + 1). 1 free parameter: β (inverse temperature).
- **model_family:** Opinion pooling
- **model_class:** Belief updating
- **all_models_tested:** 
- **model_mb_mf:** N/A (not RL; descriptive/heuristic averaging model).
- **model_params:** - N-DG: β (inverse temperature) - W-DG: β (inverse temperature) - N-RL: α (learning rate) [S — modulated by social prediction error], β (inverse temperature), γ (initial belief strength) - W-RL: α (learning rate for stage 1) [S], θ (learning rate for later stages, weighted by RD_j) [S], β (inverse temperature), γ (initial belief strength) - Priv. Sig.: β (inverse temperature), γ (initial belief strength)
- **social_param:** - W-DG: RD_j (relative degree centrality weight — not a free parameter but a structural social weighting) [S] - W-RL: θ (learning rate weighted by relative degree centrality of neighbor) [S]; α (learning rate from social prediction error) [S]  Fitted parameter values reported in Table 1 (means and SDs across participants for each dataset — see lines 692-716 above).
- **social_param_name:** - W-DG
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Bayesian Model Selection (BMS) using VBA toolbox — random-effects analysis based on free energy as lower bound for model evidence; exceedance probability (EP) used to identify best-fitting model.
- **how_model_fit:** Individual-level fit (each model fitted to individual participant choice behavior).
- **data_type_fit_to:** Choice behavior (binary predictions about bag identity).

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A (no neuroimaging analysis in this paper).
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** True

## Quality
- **sample_size:** - Dataset 1 (Jiang et al., 2023): N = 209 participants, 40 games each, 7-person networks. - Dataset 2 (Choi et al., 2023): N = 40 participants per group, 4 network types, 6 rounds of 12 stages each. - No new data collected; secondary analysis of two published datasets.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate. The tasks use real-time dynamic interaction between multiple participants in networks (higher ecological validity than typical static/simulated social information paradigms). However, the task is still highly abstract (colored marbles/bag guessing), binary choice, and conducted online in controlled experimental settings. The authors explicitly note that real-world social networks involve asynchronous updating and much larger scale. The free-sampling design in Choi et al. is more naturalistic than the forced-order in Jiang et al.
- **eligibility_flag:** FLAG — This paper does not collect new data; it is a secondary computational modeling analysis of two existing behavioural datasets (Jiang et al., 2023; Choi et al., 2023). It uses computational modeling and human behavioral data, learning occurs in a social context over time. However, note: (a) no new empirical data, (b) the paper reads more like a computational/theoretical comparison than a standard empirical study. Still meets inclusion criteria. Also flag: the "social agents" are real human participants interacting in real time, so this is genuinely social.
- **concerns:** - No new data collected — reanalysis of two published datasets, raising potential double-counting concerns if Jiang et al. (2023) or Choi et al. (2023) are also included in the review. - No standard effect sizes reported (no d, r, eta-squared, etc.) — results are primarily model comparison via exceedance probabilities. - For Choi et al., the order in which participants visited neighbors was not recorded; the three RL variants (random/ascending/descending) are post-hoc assumptions. - No supplement available for this paper; supplementary figures (S1-S7) and tables (S1-S4) are referenced but not accessible. - Publication status unclear (no journal, DOI, or year stated).
- **limitations_reported:** The authors note: the paradigms used binary readouts (blue vs. yellow) which may make DG and RL indistinguishable at moderate learning rates; real-world networks involve asynchronous updating not fully captured; the order in which Choi et al. participants sampled neighbors was not recorded, requiring post-hoc assumptions; working memory demands of DeGroot averaging may be unrealistic in large networks; the study only considers two families of models.
- **limitations_categorized:** Task simplicity (binary readout); limited ecological validity (controlled lab networks vs. real-world); missing data (neighbor sampling order not recorded); cognitive plausibility concerns; limited model space.
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.5
- **wc_total:** 7.5

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** effect_size (MEDIUM — no standard ES reported; results presented as EP and regression contrasts in figures).  ---  ### (6) WINNING MODEL
- **cannot_find:** DOI; journal name; publication year; supplement (referenced but not accessible — Figs S1-S7, Tables S1-S4 unavailable); exact exceedance probability numerical values (shown in figures only); standard effect sizes.
- **other_notes:** This paper is a secondary analysis of Jiang et al. (2023, Nature Neuroscience) and Choi et al. (2023, Management Science). If either of those papers is also in the review corpus, flag for potential double-counting of datasets. The paper provides an important theoretical contribution showing when DeGroot and RL become indistinguishable (power-law relationship between minimum-difference learning rate and degree). No neural data analyzed despite one source dataset (Jiang) being an fMRI study.
- **re_extract_flag:** false (full text read; supplement not available but referenced figures/tables are supplementary to the main findings).

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_cultural_network
- rr_tax_mod_multiplayer_live
- rr_tax_mod_social_info_search
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target+context
- spec_source = partly
- tax_domain_A_influence_transmission
- tax_domain_D_group_structure_identity
- tax_mod_cultural_network
- tax_mod_multiplayer_live
- tax_mod_social_info_search
- tax_model_bayesian
- tax_model_opinion_pooling
- tax_param_learning_rate
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_family = opinion_pooling
- tax_rr_model_opinion_pooling
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = social_network_structure
- tax_rr_topic_social_info_use
- tax_rr_topic_social_network_structure
- tax_topic_social_info_use
- tax_topic_social_network_structure
