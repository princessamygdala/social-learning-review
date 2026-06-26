# Maier et al.

- **study_id:** `ab7787bb0688efa95_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Maier, M., Cheung, V., & Lieder, F. (accepted/preprint). Learning from outcomes shapes reliance on moral rules versus cost-benefit reasoning. *Nature Human Behaviour*. Preprint available at https://osf.io/4up5z/
- **citation_short:** Maier et al.
- **doi:** 10.1038/s41562-025-02271-w
- **publication_type:** preprint (accepted for peer-reviewed journal, nature human behaviour)
- **field_of_study:** Philosophy
- **affiliations_raw:** mit sacrificial harm was based on CBR, it is unclear In the remainder of this Article, we formalize this hypothesis; ether it met the utilitarian criterion to produce the best conse- and test it in four experiments; ether moral rules take precedence over the crucial general norm against killing; Department of Experimental Psychology, University College London, London, UK; Department of Psychology, University of California, Los Angeles,; ethical theories of deontology quences of previous decisions; Institute for Intelligent Systems, Tübingen, Germany; ether to rely on moral rules or CBR is ofte
- **code_url:** https://osf.io/4up5z

## Computational level
- **study_focus:** Moral learning / metacognitive strategy selection learning. How people learn from the consequences of past moral decisions to adjust reliance on moral rules versus cost-benefit reasoning (CBR).
- **study_focus_short:** Moral learning / metacognitive strategy selection learning
- **learning_mode_description:** - Learning mode: Learning from the moral consequences of one's own past decisions about which decision strategy (moral rules vs. cost-benefit reasoning) to rely on in future moral dilemmas   - Learning from:     - Source type (non-social): self       - Moral evaluation of outcomes of own decisions     - Source content (non-social): outcome       - Consequences of own moral decisions (good vs. bad outcomes)   - Learning about:     - Target type (non-social): self       - Own decision strategies / meta-control system     - Target content (non-social): action/policy       - Which decision strategy (moral rules vs. CBR) to deploy in future moral dilemmas
- **task_description:** Participants face a series of 13 realistic moral dilemmas, each requiring a choice between a moral rule option and a cost-benefit reasoning (CBR) option. After each choice, participants observe the outcome (good or bad, deterministically assigned by condition: CBR Success vs. Rule Success) and rate it morally before proceeding to the next dilemma.
- **task_paradigm:** Moral strategy-selection task
- **players:** Single agent (participant), no interactive partner. Two between-subject conditions (CBR Success, Rule Success).
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Text-based realistic moral dilemma vignettes (adapted from historical events), text-based outcome descriptions (good/bad displayed in green/red), moral rightness ratings (0-100 scale), moral evaluation of outcomes (-100 to +100 scale).
- **method:** online / behavioural
- **method_full:** Behavioural / online
- **main_result:** - Main Results:   - Experiment 1: Participants in CBR Success condition increased CBR choices over trials (b = 0.208, z = 3.66, p < .001); Rule Success condition decreased CBR choices (b = -0.203, z = -3.63, p < .001)   - Experiment 1: Transfer to OUS Sacrificial Harm Subscale between conditions (d = 0.56)   - Experiment 2: Replication of learning effect on choices (CBR Success: b = 0.15, z = 2.61; Rule Success: b = -0.12, z = -2.16)   - Experiment 2: Transfer to OUS Sacrificial Harm (d = 0.42), DCS Deontology (d = 0.17), incentive-compatible donation (d = 0.17)   - Experiment 2: Model-based metacognitive learning best explained 78.9% of CBR Success participants; model-based behavioral learning best explained 61.7% of Rule Success participants   - Experiment 2: Evidence for model-based metacognitive learning from outcome probability ratings (F(1,756) = 17.28, p < .001)   - Experiment 3: Replication with N = 834; transfer to OUS (d = 0.52), DCS Deontology (d = 0.20)   - Experiment 4: Transfer across separate experiments (avg ~2 hr delay); moderation by metacognitive learning evidence for OUS (b = 0.81, t = 7.79), DCS (b = -0.62, t = 4.82), donations (b = 8.69, t = 4.06)   - At least 95% of participants showed some form of learning from consequences across all experiments
- **effect_size:** - Main Results:   - Experiment 1: Participants in CBR Success condition increased CBR choices over trials (b = 0.208, z = 3.66, p < .001); Rule Success condition decreased CBR choices (b = -0.203, z = -3.63, p < .001)   - Experiment 1: Transfer to OUS Sacrificial Harm Subscale between conditions (d = 0.56)   - Experiment 2: Replication of learning effect on choices (CBR Success: b = 0.15, z = 2.61; Rule Success: b = -0.12, z = -2.16)   - Experiment 2: Transfer to OUS Sacrificial Harm (d = 0.42), DCS Deontology (d = 0.17), incentive-compatible donation (d = 0.17)   - Experiment 2: Model-based metacognitive learning best explained 78.9% of CBR Success participants; model-based behavioral learning best explained 61.7% of Rule Success participants   - Experiment 2: Evidence for model-based metacognitive learning from outcome probability ratings (F(1,756) = 17.28, p < .001)   - Experiment 3: Replication with N = 834; transfer to OUS (d = 0.52), DCS Deontology (d = 0.20)   - Experiment 4: Transfer across separate experiments (avg ~2 hr delay); moderation by metacognitive learning evidence for OUS (b = 0.81, t = 7.79), DCS (b = -0.62, t = 4.82), donations (b = 8.69, t = 4.06)   - At least 95% of participants showed some form of learning from consequences across all experiments
- **learning_from:** Self; outcomes (moral consequences) of one's own moral decisions.
- **learning_about:** Self; own decision strategy (reliance on moral rules vs. cost-benefit reasoning).  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Model-based metacognitive learning (Beta-Bernoulli Bayesian updating over strategy-outcome probabilities; 2 params: α [prior precision], τ [inverse temperature])  Note: There is no single "winning model" across all participants. In the CBR Success condition, the model-based metacognitive learning model (MB-M) best explains the majority (74-87% across experiments). In the Rule Success condition, the model-based behavioral learning model (MB-B) best explains the majority (50-62%). The authors use Bayesian model averaging rather than selecting a single winning model.
- **model_family:** MB/MF hybrid
- **model_class:** PE learning
- **all_models_tested:** - {"name": "MB-M (Model-Based Metacognitive)", "family": "Bayesian belief updating (Beta-Bernoulli)", "n_params": 2, "metric": "Marginal likelihood (bridge sampling) + BMS"} - {"name": "MF-M (Model-Free Metacognitive)", "family": "Q-learning", "n_params": 2, "metric": "Marginal likelihood (bridge sampling) + BMS"} - {"name": "C-M (Constant Metacognitive / No Learning)", "family": "Constant probability", "n_params": 1, "metric": "Marginal likelihood (bridge sampling) + BMS"} - {"name": "MB-B (Model-Based Behavioral)", "family": "Bayesian belief updating (Beta-Bernoulli)", "n_params": 2, "metric": "Marginal likelihood (bridge sampling) + BMS"} - {"name": "MF-B (Model-Free Behavioral)", "family": "Q-learning", "n_params": 2, "metric": "Marginal likelihood (bridge sampling) + BMS"} - {"name": "C-B (Constant Behavioral / No Learning)", "family": "Constant probability", "n_params": 1, "metric": "Marginal likelihood (bridge sampling) + BMS"}
- **model_mb_mf:** MB (the winning model, MB-M, is explicitly model-based). The model-free metacognitive alternative (MF-M) was also tested but explained far fewer participants.
- **model_params:** - α (prior precision for Beta distribution): Controls strength of prior belief; higher α = slower learning. Prior: Gamma(shape = 2.57, rate = 0.54). No mean fitted values reported. - τ (inverse decision temperature): Controls determinism of strategy selection via softmax. Prior: Lognormal(0, 1.4). No mean fitted values reported.
- **social_param:** None. No parameters are specifically social; learning occurs over moral decision strategies (rules vs. CBR), not over social agents or social information.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Marginal likelihood estimated via bridge sampling; Bayesian model selection (BMS) with exceedance probabilities; family-level inference using spm_compare_families; inclusion Bayes factors for metacognitive vs. behavioral learning families.
- **how_model_fit:** Individual-level fit (models fitted separately for each participant using Stan/RStan with bridge sampling for marginal likelihoods)
- **data_type_fit_to:** Choice behavior (binary: CBR option vs. rule option on each trial)  ---  ### IMPLEMENTATION LEVEL

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
- **sample_size:** Total N = 2,328 across 4 experiments. Experiment 1: N = 387 (after exclusions; M_age = 42.2, SD = 13.3; 194 female, 191 male). Experiment 2: N = 380 (M_age = 42.9, SD = 13.2; 192 female, 188 male). Experiment 3: N = 834 (M_age = 43.4, SD = 14.2; 424 female, 410 male). Experiment 4: N = 727 (M_age = 39.43, SD = 13.15; 366 female, 361 male). All recruited via Prolific, primarily UK-based.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate. Authors developed realistic moral dilemmas based on historical events (adapted from Korner & Deutsch, 2023) to address criticisms of trolley-problem-style dilemmas. Outcomes were deterministic (100% manipulation), which limits ecological validity. However, outcomes were pre-tested as plausible; 83% of participants found outcomes plausible, 67% found them informative about the real world. Transfer to incentive-compatible donation decisions and to a separate experiment increases ecological validity. However, deterministic outcome schedules (CBR always succeeds or always fails) are unrealistic.
- **eligibility_flag:** Borderline eligibility. The paper uses computational modeling and human behavioral data, and learning occurs over time (13 trials). However, the learning context is arguably not "social" in the sense required by the review: participants learn from their own moral decision outcomes, not from social agents, social feedback, or social observation. The moral dilemmas involve other people, but the learning mechanism itself is non-social (individual RL over one's own outcomes). Flag: "Learning mechanism is non-social (individual metacognitive RL from own outcomes); moral dilemmas involve others but no social learning source (no observation, imitation, or social feedback).
- **concerns:** - No mean fitted parameter values are reported for any model - Deterministic outcome manipulation (100% success/failure) limits generalizability - The authors acknowledge that model-based vs. model-free distinction is confounded: model-free model learns from continuous moral evaluations while model-based learns from binary good/bad outcomes - No neuroimaging data to examine neural mechanisms - The paper title in the file ("Metacognitive Learning from Consequences of Past Choices Shapes Moral Decision-Making") differs from the manuscript title ("Learning From Outcomes Shapes Reliance on Moral Rules Versus Cost-Benefit Reasoning")
- **limitations_reported:** Our experiments were not optimized for this comparison [model-based vs. model-free], and our models also differed along another dimension"; "the model-free model learns from continuous moral evaluations, whereas the model-based model learns only about the probabilities of binary events"; "there is a possibility of rationalization" in the model-based behavioral measure; "we did not find any relationships with stable individual differences" predicting metacognitive learning; "it remains unclear which types of people are more likely to engage in metacognitive moral learning"; "follow-up research could test how stable the moral learning induced by our paradigm is over time"; "the two experiments were still conducted relatively close together in time"; "our experiments focused on learning from consequences" and other learning signals (e.g., social) remain unexplored.
- **limitations_categorized:** Model comparison confounds; limited ecological validity (deterministic outcomes); potential rationalization artifacts; lack of neural data; limited individual difference predictors; temporal stability unknown; narrow learning signal (consequences only, no social signals); limited generalizability of reinforcement schedule.
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Partial
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** Yes
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.0
- **wc_total:** 8.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `learning_mode` (MEDIUM): classified as non-social learning; the moral dilemmas involve social content (harm to others), but the learning mechanism itself is individual (no social agent as information source) - `winning_model` (MEDIUM): no single winning model; MB-M dominates CBR Success, MB-B dominates Rule Success; authors use Bayesian model averaging - `model_params` (LOW): no mean fitted parameter values reported for any model - `doi` (MEDIUM): not reported; manuscript is a preprint accepted at Nature Human Behaviour - `eligibility_flag` (MEDIUM): borderline social learning — the learning is about moral decision strategies involving others, but the learning mechanism is non-social
- **cannot_find:** - Mean fitted parameter values (α, τ) for any model - DOI (preprint, not yet published at time of writing) - Supplement was embedded in the main text file; no separate supplement file found
- **other_notes:** - The paper reports 4 experiments with a total N = 2,328, making this one of the larger studies in the review - The filename ("Metacognitive Learning from Consequences of Past Choices Shapes Moral Decision-Making") differs from the actual manuscript title ("Learning From Outcomes Shapes Reliance on Moral Rules Versus Cost-Benefit Reasoning") - The Supplementary Information was included at the end of the main text file (starting at line 2280) - The paper is explicitly described as distinct from social learning: "Unlike social learning, it involves neither imitation nor observational learning and does not require instruction or social feedback" (lines 100-102) - The paper explicitly states: "Unlike social learning, which can propagate bias and prejudice, moral learning from the consequences of past decisions can ground people's subjective sense of right and wrong in the objective reality" (lines 1205-1206)
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = general
- spec_locus = source
- spec_source = social
- spec_target = social
- tax_domain_F_affective_moral
- tax_mod_experiential
- tax_model_MB
- tax_model_MF
- tax_model_bayesian
- tax_model_q_learning
- tax_model_rescorla_wagner
- tax_param_precision
- tax_popclass_healthy
- tax_rr_domain = F_affective_moral
- tax_rr_domain_F_affective_moral
- tax_rr_model_MB_MF_hybrid
- tax_rr_model_family = MB_MF_hybrid
- tax_rr_param_MB_MF_balance
- tax_rr_param_learning_rate
- tax_rr_primary_topic = moral_harm
- tax_rr_topic_moral_harm
- tax_topic_moral_harm
