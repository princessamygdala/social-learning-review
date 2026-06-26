# Morishita et al. (2025)

- **study_id:** `af7418c99b2e431f9_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Morishita, G., Murawski, C., Yadav, N., & Suzuki, S. (2025). Whom do we prefer to learn from in observational reinforcement learning? *PLoS Computational Biology*, *21*(12), e1013143. https://doi.org/10.1371/journal.pcbi.1013143
- **citation_short:** Morishita et al. (2025)
- **doi:** 10.1371/journal.pcbi.1013143
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** 
- **code_url:** 

## Computational level
- **study_focus:** Observational learning -- partner selection preferences based on decision noise level and relationship to imitative vs. reward-based learning styles
- **study_focus_short:** Observational learning -- partner selection preferences based on decision noise
- **learning_mode_description:** - Learning mode: Learning from observing a selected partner's actions and reward outcomes about option values in a three-armed bandit   - Learning from:     - Source type (social): other (selected partner)       - Not joint     - Source content (social): action/policy + outcome       - Not joint   - Learning about:     - Target type (non-social): world (option reward probabilities)       - Not joint     - Target content (non-social): stimulus (option values / reward probabilities)       - Not joint
- **task_description:** Participants first passively observed two simulated partners (high-noise and low-noise) performing a three-armed bandit task, then selected one partner for an observational learning phase in which they observed the partner's choices and outcomes before making their own choice (without seeing their own outcome).
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant), dyadic (one selected simulated partner per block; 2 potential partners observed per block)
- **n_players:** dyadic (2)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract fractals, binary reward feedback (rewarded/not rewarded), human face images (to distinguish partners)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Most participants preferred the low-noise (high-performing) partner over the high-noise partner (b = -1.06 +/- 0.25, t(55) = -4.27, p < 0.001) - Partner performance was the strongest predictor of partner selection (b = 0.759 +/- 0.169), followed by predictability (b = 0.389 +/- 0.161); information gain had no reliable effect (b = -0.142 +/- 0.193) - Participants who preferred low-noise partners showed greater reliance on imitation (action learning weight; Cohen's d = 0.58) - Partner's past action positively influenced participant choices (b = 0.83 +/- 0.06); partner's past reward also influenced choices (b = 1.63 +/- 0.11) - The effect of partner's action was negatively modulated by preference for high-noise partner (interaction b = -1.69 +/- 0.15) - Within-participant: imitation was suppressed when partner was high-noise (action x noise interaction b = -0.375 +/- 0.021)
- **effect_size:** - Partner noise effect on selection: b = -1.06 +/- 0.25 (logistic regression coefficient) - Performance as predictor of selection: b = 0.759 +/- 0.169 (standardized) - Predictability as predictor: b = 0.389 +/- 0.161 (standardized) - Partner action main effect on behavior: b = 0.83 +/- 0.06 - Partner reward main effect on behavior: b = 1.63 +/- 0.11 - Action x partner selection interaction: b = -1.69 +/- 0.15 - Difference in action learning weight by partner preference: Cohen's d = 0.58 - Within-participant action x noise interaction: b = -0.375 +/- 0.021
- **learning_from:** Other (selected partner); partner's actions and reward outcomes in a three-armed bandit task
- **learning_about:** World; option reward probabilities / action values for the three-armed bandit options  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Full model: weighted combination of Action Learning (imitation) and Reward Learning (observational RL), with parameters $\alpha_A$, $\alpha_V$, $w_A$, $\beta$
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Full model", "family": "Weighted Action Learning + Reward Learning (Q-learning)", "n_params": 4, "metric": "WAIC"} - {"name": "Action Learning model", "family": "Action imitation only", "n_params": 2, "metric": "WAIC"} - {"name": "Reward Learning model", "family": "Q-learning (observational)", "n_params": 2, "metric": "WAIC"} - {"name": "Dynamic-weight model", "family": "Weighted Action + Reward with time-varying weight", "n_params": "not specified (>4)", "metric": "WAIC"}
- **model_mb_mf:** MF
- **model_params:** - $\alpha_V$ (learning rate for reward learning, observational value update): constrained [0,1]; mean fitted value not reported in main text - $\alpha_A$ (learning rate for action imitation): constrained [0,1]; mean fitted value not reported in main text - $w_A$ [S] (weight of action learning / imitation vs. reward learning): constrained [0,1]; key social parameter -- higher values indicate greater reliance on imitating the partner's actions; mean fitted value not reported numerically but posterior densities shown in S5 Fig - $\beta$ (inverse temperature): $\geq$ 0; mean fitted value not reported in main text
- **social_param:** $w_A$ -- the weight parameter determining the relative reliance on learning from the partner's actions (imitation) versus the partner's reward outcomes. Higher $w_A$ indicates greater imitation tendency. This was the key parameter distinguishing participants who preferred low-noise vs. high-noise partners (Cohen's d = 0.58).
- **social_param_name:** $w_A$
- **social_param_value:** 0.58
- **social_param_sd:** 
- **social_param_range:** 0–1
- **model_comparison_metric:** WAIC (Widely-applicable Akaike Information Criterion)
- **how_model_fit:** individual-level-fit (Bayesian hierarchical modeling using MCMC in Stan; 4 chains, 1000 warmup + 1000 sampling iterations)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** Pilot: N = 20 (15 females, 4 males, 1 unidentified; age range 18-28, mean 22.5 +/- 2.86); Main: N = 55 (35 females, 20 males; age range 18-29, mean 22.98 +/- 3.25). Combined for exploratory analyses: N = 74 (after excluding 1 pilot participant). All university student sample.
- **population_category:** undergraduates
- **population_age_range:** 18–28
- **ecological_validity:** Laboratory behavioral task using abstract fractal stimuli and simulated (not real) partners. Partners were computer-generated by Q-learning algorithms but participants believed they were previous human participants. Low ecological validity -- real-world observational learning involves richer social cues, repeated interactions, and genuine social agents. The one-shot partner selection per block does not capture dynamic partner preference updating that occurs in real life.
- **eligibility_flag:** 
- **concerns:** - Partners were simulated agents (Q-learning algorithms), not real humans -- participants were deceived about this. While no participants reported suspicion, this limits generalizability to real social interactions. - Decision noise and performance were inherently confounded (low noise = better performance), making it difficult to isolate which factor drove partner preference. - Exploratory analyses (GLMM learning style, model-based individual differences) were not preregistered and combined pilot + main data. - Mean fitted parameter values for the winning model are not reported numerically in the main text (only posterior density plots in supplementary figures). - The within-participant analysis (N=52) required selecting participants who chose both partner types, raising selection bias concerns (acknowledged by authors).
- **limitations_reported:** Decision noise and performance were inherently linked, making it difficult to determine whether participants' preferences were driven by the partner's exploration style or by their observed success; the task structure may not have strongly incentivized exploration, potentially reducing motivation to select the high-noise partner; the within-participant analysis included only a subset of participants who selected both high- and low-noise partners at least once, raising the possibility of selection bias; cognitive load of tracking a high-noise partner was not measured; social and psychological traits (e.g., trustworthiness, ideological alignment) that may impact partner preference were not examined; the one-time partner selection design did not capture how preferences evolve through repeated interactions
- **limitations_categorized:** confounded manipulation; task simplicity; selection bias; unmeasured cognitive factors; limited social dimensions; limited ecological validity
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Yes
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 10
- **wc_total:** 10.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM confidence -- exact mean fitted values not reported numerically in main text; posterior densities shown in supplementary figures (S5 Fig) which are TIFF images not accessible - all_models_tested (dynamic-weight model n_params): LOW confidence -- number of parameters for the dynamic-weight model not specified in the main text; described in S1 Text (DOCX supplement not accessible)
- **cannot_find:** - Mean fitted parameter values for $\alpha_V$, $\alpha_A$, $w_A$, $\beta$ (not reported numerically; only as posterior density plots in S5 Fig, a TIFF file) - Exact number of parameters for the dynamic-weight model (described in S1 Text, a DOCX supplement not accessible) - Exact WAIC values for each model (Fig 3C shows comparison graphically but numerical values not reported in text)
- **other_notes:** - This paper has two studies (pilot N=20 and main preregistered N=55) but they use the same design. The main confirmatory analyses use only the main study (N=55); exploratory analyses combine both (N=74). Given the identical design and that the pilot is not independently analyzed for all outcomes, this is treated as a single study row. - Supplement files listed are DOCX (S1 Text, S2 Text), XLSX (S1 Table, S2 Table), and TIFF (S1-S6 Figs) -- none were available as .txt files and no _Supplements file was found in the papers folder. - Data and code available at https://doi.org/10.5281/zenodo.15386571 - The "social agent" is an automated system (Q-learning algorithm simulating a partner). This should be flagged per inclusion criteria but does not affect eligibility -- participants believed partners were real humans.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_social_info_search
- rr_tax_mod_vicarious_outcome
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- tax_domain_A_influence_transmission
- tax_domain_B_inference_modelling_others
- tax_mod_action_observation
- tax_mod_social_info_search
- tax_mod_vicarious_outcome
- tax_model_MB_MF_hybrid
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_social_weight
- tax_rr_param_temperature
- tax_rr_primary_topic = social_info_use
- tax_rr_secondary_topic = imitation_emulation
- tax_rr_topic_imitation_emulation
- tax_rr_topic_social_info_use
- tax_topic_imitation_emulation
- tax_topic_social_info_use
