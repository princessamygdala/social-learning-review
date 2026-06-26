# Bai et al. (2022)

- **study_id:** `a72ee534eb86c7c7b_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Bai, X., Fiske, S. T., & Griffiths, T. L. (2022). Globally inaccurate stereotypes can result from locally adaptive exploration. *Psychological Science, 33*(5), 671–684. https://doi.org/10.1177/09567976211045929
- **citation_short:** Bai et al. (2022)
- **doi:** 10.1177/09567976211045929
- **publication_type:** peer-reviewed journal
- **year:** 2022.0
- **field_of_study:** Psychology
- **affiliations_raw:** Department of Psychology, Princeton University; 2Princeton School of Public and International Affairs,; University; and 3Department of Computer Science, Princeton University; ether people’s choices are motivated by factors; mited-capacity human minds create shortcuts via; School of Public and International Affairs; University, Department of Psychology and; mitations, and information deficits; laborators from four groups; emails: xb2@princeton.edu
- **code_url:** https://osf.io/2kv5r/

## Computational level
- **study_focus:** Stereotype learning / social exploration learning -- How locally adaptive exploratory sampling (Thompson sampling) in a multi-armed bandit setting with equally rewarding social groups produces inaccurate group stereotypes as a by-product of reward maximization.
- **study_focus_short:** Stereotype learning / social exploration learning -- How locally adaptive
- **learning_mode_description:** - Learning mode: Learning from one's own reward outcomes of interacting with members of social groups about which group to exploit for future interactions (and incidentally forming impressions about each group's reward value).   - Learning from:     - Source type (non-social): self       - (The agent's own choices and experienced binary outcomes)     - Source content (non-social): outcome       - (Binary reward: helped = 1, not helped = 0)   - Learning about:     - Target type (social): group (four fictional social groups)     - Target content (social): state (expected reward/utility of each group -- i.e., group stereotypes/impressions)
- **task_description:** Participants played a 40-round online game ("Explore Toma City") in which they chose one person from one of four fictional social groups each round and received binary feedback (1 point if helped, 0 if not). After 40 rounds, they estimated each group's reward probability and rated groups on warmth and competence.
- **task_paradigm:** Multi-armed bandit
- **players:** Single agent (participant), multi-target (4 fictional social groups: Tufa, Aima, Reku, Weki)
- **n_players:** multi-target (3+)
- **partner_type:** unclear
- **stimuli:** Fictional group labels with associated symbols (Fire, Gold, Rock, Water), binary reward feedback, text-based stereotypical descriptions (prior bias condition only)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Experiment 1 (identical reward, no prior bias): Self-select participants had lower Herfindahl scores (more concentrated choices) than random-meet participants (b = -0.226, 95% CI [-0.306, -0.146]; Cohen's d = 1.15)   - Experiment 1 (identical reward, no prior bias): Self-select participants had larger reward-estimation SD than random-meet participants (b = 11.354, 95% CI [7.387, 15.321]; Cohen's d = 1.14)   - Experiment 1: Individual-level correlation between choice concentration and reward estimation SD (r(98) = -0.605)   - Experiment 1: Self-select participants perceived greater warmth/competence differences between groups (b = 0.768, 95% CI [0.366, 1.170]; Cohen's d = 0.77)   - Experiment 2: Self-select vs. random-meet on Herfindahl score (b = -0.163, 95% CI [-0.189, -0.138]; Cohen's d = 1.06)   - Experiment 2: Self-select vs. random-meet on reward estimation SD (b = 4.113, 95% CI [2.845, 5.382]; Cohen's d = 0.43)   - Experiment 2: Yoke-both vs. random-meet on reward estimation SD (b = 5.464, 95% CI [4.194, 6.734]; Cohen's d = 0.55)   - Experiment 2: Yoke-choice-only vs. random-meet on reward estimation SD (b = 3.927, 95% CI [2.658, 5.196]; Cohen's d = 0.43)   - Experiment 2: Yoke-both > self-select on reward estimation SD (b = 1.351, 95% CI [0.081, 2.621])   - Experiment 2: Yoke-choice-only < yoke-both on reward estimation SD (b = -1.537, 95% CI [-2.807, -0.266])   - Experiment 2: Individual-level correlation between choice concentration and reward estimation SD (r(2003) = -0.397)   - Warmth-competence dispersion correlated with reward estimation SD: Exp 1 r(397) = .566; Exp 2 r(2003) = .553
- **effect_size:** - Main Results:   - Experiment 1 (identical reward, no prior bias): Self-select participants had lower Herfindahl scores (more concentrated choices) than random-meet participants (b = -0.226, 95% CI [-0.306, -0.146]; Cohen's d = 1.15)   - Experiment 1 (identical reward, no prior bias): Self-select participants had larger reward-estimation SD than random-meet participants (b = 11.354, 95% CI [7.387, 15.321]; Cohen's d = 1.14)   - Experiment 1: Individual-level correlation between choice concentration and reward estimation SD (r(98) = -0.605)   - Experiment 1: Self-select participants perceived greater warmth/competence differences between groups (b = 0.768, 95% CI [0.366, 1.170]; Cohen's d = 0.77)   - Experiment 2: Self-select vs. random-meet on Herfindahl score (b = -0.163, 95% CI [-0.189, -0.138]; Cohen's d = 1.06)   - Experiment 2: Self-select vs. random-meet on reward estimation SD (b = 4.113, 95% CI [2.845, 5.382]; Cohen's d = 0.43)   - Experiment 2: Yoke-both vs. random-meet on reward estimation SD (b = 5.464, 95% CI [4.194, 6.734]; Cohen's d = 0.55)   - Experiment 2: Yoke-choice-only vs. random-meet on reward estimation SD (b = 3.927, 95% CI [2.658, 5.196]; Cohen's d = 0.43)   - Experiment 2: Yoke-both > self-select on reward estimation SD (b = 1.351, 95% CI [0.081, 2.621])   - Experiment 2: Yoke-choice-only < yoke-both on reward estimation SD (b = -1.537, 95% CI [-2.807, -0.266])   - Experiment 2: Individual-level correlation between choice concentration and reward estimation SD (r(2003) = -0.397)   - Warmth-competence dispersion correlated with reward estimation SD: Exp 1 r(397) = .566; Exp 2 r(2003) = .553
- **learning_from:** Self; own binary reward outcomes from interacting with group members.
- **learning_about:** Group; expected reward/utility of each of 4 social groups (group-level stereotypes/impressions).  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Thompson sampling for Beta-Bernoulli multi-armed bandit (K=4 arms; prior Beta(alpha, b) per arm; Bayesian posterior update; sample from posterior, select argmax). No free parameters fitted to individual data -- the model is a normative/computational-level account used for simulation.
- **model_family:** Bayesian
- **model_class:** Other
- **all_models_tested:** - {"name": "Thompson sampling (Beta-Bernoulli MAB)", "family": "Bayesian bandit / Thompson sampling", "n_params": "2 per arm (alpha, b) -- not fitted; simulation-based", "metric": "qualitative comparison with human behavior"} - {"name": "Random sampling", "family": "Uniform random", "n_params": 0, "metric": "qualitative comparison"} - {"name": "Dynamic programming (finite-horizon optimal)", "family": "Dynamic programming / Bellman", "n_params": "N/A -- exact solution", "metric": "qualitative comparison (supplement only)"}
- **model_mb_mf:** MB (Bayesian model-based -- maintains posterior distributions over reward probabilities and samples from them)
- **model_params:** - alpha_k: success count (number of rewarding interactions with group k); initial value = 1 (no prior bias) or 10 (prior bias condition for one group) - b_k: failure count (number of non-rewarding interactions with group k); initial value = 1 - theta_k: sampled expected reward probability for group k, drawn from Beta(alpha_k, b_k) - K = 4 (number of groups/arms) - T = 40 (number of rounds) - Ground truth reward probabilities: theta = {0.9, 0.9, 0.9, 0.9} (identical) or {0.1, 0.3, 0.5, 0.9} (different)  Note: No parameters were fitted to individual human data. The model was simulated and qualitative predictions were compared to human behavioral patterns.
- **social_param:** None explicitly social -- the groups are social (fictional social groups), but the model parameters are standard bandit parameters (alpha, b per arm). The social aspect is in the interpretation: arms represent social groups, and the resulting posterior beliefs represent group stereotypes/impressions. [S] tagging: The arm identities (groups) carry social meaning but alpha_k and b_k are generic Bayesian count parameters.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Qualitative comparison of model predictions with human behavioral data (no formal model fitting or quantitative model comparison metric applied). The paper compares Thompson sampling vs. random sampling vs. dynamic programming at the simulation level, and compares qualitative behavioral patterns across experimental conditions.
- **how_model_fit:** simulate-and-compare (model simulated, qualitative predictions compared to aggregate human data; no individual-level parameter fitting)
- **data_type_fit_to:** choice behavior (partner selection patterns) and self-report ratings (reward estimations, warmth/competence ratings) -- but note the model was not formally fitted to these data; rather, aggregate patterns were compared.  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** Experiment 1: N = 399 (8 conditions, ~50 per cell; 2 reward x 2 strategy x 2 prior bias); Experiment 2: N = 2,005 (4 conditions, ~500 per cell; self-select, yoke-both, yoke-choice-only, random-meet). Total N = 2,404 across both experiments. Online adult participants via Amazon Mechanical Turk CloudResearch. Experiment 1 demographics by condition (from supplement): ~50-56% female, ~79-83% White, ~70-83% aged 20-40.
- **population_category:** healthy adults
- **population_age_range:** 20–40
- **ecological_validity:** Low-to-moderate. Uses a fictional city and fictional social groups (Tufa, Aima, Reku, Weki) to avoid pre-existing biases, which increases internal validity but reduces ecological validity. The 40-round binary reward game is highly simplified compared to real-world intergroup encounters. Interactions are not face-to-face; the "social" groups are abstract labels. The task isolates exploratory sampling from other processes (motivation, emotion, real social dynamics). Authors acknowledge this abstractness and call for more naturalistic follow-up studies.
- **eligibility_flag:** FLAG -- The paper uses a computational model (Thompson sampling) and human behavioral data, and learning occurs over time (40 sequential rounds). However, the model is not fitted to individual participant data; it is used as a normative/simulation-level account whose qualitative predictions are compared to aggregate human behavior. This is a simulate-and-compare approach rather than traditional computational modeling with parameter estimation. The "social" context involves fictional, abstract groups rather than real social interactions. The paper is borderline on "uses computational modeling" in the sense of fitting models to human data -- it uses computational modeling in the sense of generating predictions from a formal model. Include but flag as: **model not fitted to individual data; simulate-and-compare only**.
- **concerns:** - No individual-level model fitting -- Thompson sampling is used as a normative benchmark, not fitted to each participant's choices. - No formal model comparison metric (BIC, AIC, etc.) -- comparison is qualitative. - No parameter recovery, model recovery, or posterior predictive checks. - The "social" aspect is minimal -- groups are abstract fictional labels with no real social interaction, faces, or social cues. - Yoked design in Experiment 2 has a potential confound acknowledged by authors: non-random assignment due to sequential arrival (approximately 8-hour gap between conditions). - No formal test of whether Thompson sampling specifically (vs. other exploration algorithms) best accounts for individual human behavior.
- **limitations_reported:** Limited our analysis to individual-level stereotypes, which differ from collective stereotypes on which society has consensus"; "Future work could include contextual bandits to examine whether people learn mappings between features"; "Transmission of information between agents and across generations could be another mechanism"; "Stereotypes about social groups are not unidimensional -- future work could test how this paradigm applies to the emergence of complex stereotype contents"; "Future experiments should examine behaviors among participants who do not speak English or who do not work online"; yoked design "yields one potential confound to random assignment -- the time of arrival" (supplement); "Our operationalization is more abstract than prior work. We do not have any concrete traits" (supplement).
- **limitations_categorized:** Limited ecological validity; task simplicity; limited generalizability (online English-speaking sample only); abstract operationalization of stereotypes; individual-level only (not collective stereotypes); potential confound in yoked design; no formal model fitting to individual data.
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** unclear
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `model_comparison_metric`: LOW -- No formal quantitative model comparison metric used; qualitative comparison only. - `how_model_fit`: MEDIUM -- Described as "simulate-and-compare" but this is not a standard fitting approach; the model was never fitted to individual data. - `social_param`: MEDIUM -- No explicitly social parameter; the social content is in the interpretation of arm identities as social groups. - `winning_model`: MEDIUM -- Thompson sampling is described as the "primary model" but was not selected via formal model comparison on human data. - `eligibility_flag`: MEDIUM -- Borderline on computational modeling criterion (simulate-and-compare rather than fit-to-data).
- **cannot_find:** - Individual-level fitted parameter values (not reported because no individual fitting was done) - Formal model comparison statistics (BIC, AIC, etc.) -- not applicable to this paper's approach - Effect sizes for simulation comparisons (simulations compared qualitatively, not with formal effect sizes)
- **other_notes:** This paper is primarily a computational/theoretical analysis using Thompson sampling as a normative model to explain how inaccurate stereotypes can emerge from adaptive exploration, supported by two large behavioral experiments. The contribution is theoretical -- demonstrating that a standard exploration algorithm (Thompson sampling) in a multi-armed bandit framework with equally rewarding groups produces biased sampling and biased impressions as a by-product. The experiments confirm qualitative predictions but do not involve standard computational modeling practices (parameter fitting, model comparison). The paper is highly cited and influential in the social learning / computational social cognition literature. The approach is closest to "rational analysis" (Anderson, 1991) -- explaining a psychological phenomenon as an optimal solution to an environmental problem. The supplement confirms dynamic programming (exact optimal solution) produces even more extreme bias than Thompson sampling.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = general
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_D_group_structure_identity
- tax_domain_G_uncertainty_volatility
- tax_mod_experiential
- tax_mod_social_info_search
- tax_model_MB
- tax_model_bayesian
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = D_group_structure_identity
- tax_rr_domain_D_group_structure_identity
- tax_rr_domain_G_uncertainty_volatility
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_precision
- tax_rr_primary_topic = stereotype_updating
- tax_rr_secondary_topic = exploration_exploitation
- tax_rr_topic_exploration_exploitation
- tax_rr_topic_stereotype_updating
- tax_topic_exploration_exploitation
- tax_topic_stereotype_updating
