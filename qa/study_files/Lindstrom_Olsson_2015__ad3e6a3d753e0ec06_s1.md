# Lindstrom & Olsson (2015)

- **study_id:** `ad3e6a3d753e0ec06_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Lindstrom, B., & Olsson, A. (2015). Mechanisms of social avoidance learning can explain the emergence of adaptive and arbitrary behavioral traditions in humans. *Journal of Experimental Psychology: General*, *144*(3), 688-703. http://dx.doi.org/10.1037/xge0000071
- **citation_short:** Lindstrom & Olsson (2015)
- **doi:** 10.1037/xge0000071
- **publication_type:** peer-reviewed journal
- **year:** 2015.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** Institutet(KI),Institutionenförkliniskneurovetenskap(CNS), Onagenerallevel,itisclearthatmanycomplexsocialbehav-; etherwith(b)therewardingpropertiesofavoidingathreateningpunishment,couldexplain; Department of Clinical Neuro- adaptive and nonadaptive human behavior; ethefundamentalimportanceofsociallearningforcomplexsocialbehaviors; DepartmentofClinicalNeuroscience,DivisionofPsychology,; DivisionofPsychology,KarolinskaInstitutet,Sweden; eth,1978;Griffin,2004;Hoppitt&Laland,2013); mpiricalsupportforourmodel,includingthe2
- **code_url:** 

## Computational level
- **study_focus:** Social avoidance learning; social transmission of avoidance behaviors under threat of punishment; emergence and maintenance of behavioral traditions through behavior copying (BC) and rewarding punishment omission (RPO).
- **study_focus_short:** Social avoidance learning
- **learning_mode_description:** - Learning mode: Learning from observing another individual's action choices about which actions to avoid under threat of punishment   - Learning from:     - Source type (social): other (demonstrator)       - In Experiment 4: chain of real participants     - Source content (social): action/policy (observed action choices between two options)   - Learning about:     - Target type (non-social): world (which action is safe vs. punished)     - Target content (non-social): action/policy (which action to choose to avoid punishment)
- **task_description:** Participants first observed 20 choices (but not their consequences) made by a demonstrator between two abstract fractal stimuli, then made 20 choices themselves between the same stimuli under the belief that certain choices might result in mild electric shocks. Across four experiments, the design varied whether punishment was omitted (Exp 1), reward was omitted instead (Exp 2), random shocks were delivered (Exp 3), or real participant chains were used (Exp 4).
- **task_paradigm:** Observational learning task
- **players:** Single agent (participant), single demonstrator (computerized in Exp 1-3; real prior participant in Exp 4). Experiment 4: multi-agent transmission chain (5 generations x 10 chains, N=50).
- **n_players:** network (5+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract fractals (red/green color hue), mild electric shocks (100 ms DC-pulse), "$" symbol for reward condition (Exp 2).
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Main Results:   - Exp 1 (punishment omission): Strong behavior copying under threat of punishment (beta = 3.66, SE = 1.14, 95% CI [1.46, 5.89])   - Exp 2 (reward omission): No significant copying when reward was omitted instead (beta = 0.35, SE = 0.42, 95% CI [-0.48, 1.17])   - Exp 3 (random punishment): Significant copying even when demonstrated action was randomly punished (beta = 0.75, SE = 0.28, 95% CI [0.2, 1.3])   - Exp 4 (transmission chain): Behavior transmitted across 5 generations (beta = 3.22, SE = 1.1, 95% CI [1.06, 5.36]); intergenerational correlation r(48) = .35   - RPO parameter correlated with P(A): r(23) = -0.49   - Social learning rate correlated with P(A): r(23) = 0.59   - Stronger repeat-choice tendency under punishment threat vs. reward omission (Exp 1 vs. Exp 2 interaction: beta = 5.30, SE = 1.71, z = 4.09)
- **effect_size:** beta = 3.66 (Exp 1); beta = 0.35 (Exp 2, n.s.); beta = 0.75 (Exp 3); beta = 3.22 (Exp 4); r = .35 (intergenerational transmission); r = -0.49 (RPO-P(A) correlation); r = 0.59 (social LR-P(A) correlation)
- **learning_from:** Other (demonstrator); observed action choices (no outcome information visible).
- **learning_about:** World; which action to select to avoid punishment.  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** RL with behavior copying and rewarding punishment omission: Q(t+1) = Q(t) + alpha_I * delta(t), where delta(t) = R(t) - Q(t); social learning: Q(t+1) = Q(t) + alpha_O * delta(t), where delta(t) = 1 - Q(t); action selection via Softmax with temperature gamma (scaling RPO). Three parameters: alpha_I (individual learning rate), alpha_O (social learning rate), gamma (RPO sensitivity/inverse temperature).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** [{"name": "RL with BC + RPO (individual-level model)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "MLE"}]
- **model_mb_mf:** MF
- **model_params:** - alpha_I (individual/asocial learning rate): regulates sensitivity to prediction errors from own experience. [Fitted values reported in Supplemental Table 1, not accessible.] - alpha_O [S] (social/observational learning rate): regulates how strongly observed actions of demonstrator affect expected action values. [Fitted values reported in Supplemental Table 1, not accessible.] - gamma (inverse temperature / RPO sensitivity): scales reinforcement value of successfully avoiding punishment; lower values = stronger RPO influence, more exploitative behavior. [Fitted values reported in Supplemental Table 1, not accessible.]
- **social_param:** alpha_O [S]: social learning rate determining the strength of behavior copying from the demonstrator's observed actions.
- **social_param_name:** alpha_O
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** MLE (maximum-likelihood estimation for individual parameter fitting); no formal model comparison between competing models reported.
- **how_model_fit:** individual-level-fit (maximum-likelihood optimization, fit individually to each participant's trial-by-trial choices)
- **data_type_fit_to:** choice behavior  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (behavioural study only)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=120 total (Exp 1: N=25 [18 women]; Exp 2: N=20 [9 women]; Exp 3: N=25 [17 women]; Exp 4: N=50 [25 women]). Plus agent-based simulations (N=100 agents per group).
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low-moderate. Uses abstract fractal stimuli and electric shock as punishment currency, which is far from naturalistic social norms and taboos. The transmission chain (Exp 4) captures some aspects of intergenerational cultural transmission but is limited to 5 generations and binary choices. The authors acknowledge that experimental tests are restricted to brief timescales and a single punishment currency (electric shocks). The computerized demonstrator in Exp 1-3 removes natural variability in social information.
- **eligibility_flag:** 
- **concerns:** (1) Only one model tested -- no formal model comparison with alternative models (e.g., model-based RL, conformity models). (2) Supplement referenced for parameter estimates (Supplemental Table 1) and sensitivity analyses but supplement not accessible for verification. (3) Mean fitted parameter values not reported in main text. (4) The "threat of punishment" is an auxiliary assumption not explicitly modeled -- participants were simply instructed they might receive shocks. (5) Agent-based simulation uses fixed parameter values rather than fitted; correspondence between simulation and experimental models is qualitative rather than quantitative.
- **limitations_reported:** The experimental investigation is limited to a specific timescale (brief) and a punishment currency (electric shocks); the discrepancy between theoretical scope and experimental investigations is acknowledged; the model represents the simplest computational implementation and alternative representational accounts (model-based RL) could produce identical behavioral predictions; the agent-based model did not include heritable traits or strategic interaction; network-based transmission biases were not modeled; the focus on direct observation excludes verbal/symbolic social learning; results may not generalize to situations with external rewards.
- **limitations_categorized:** limited ecological validity; task simplicity; limited generalizability (single punishment currency, brief timescale); no model comparison with alternatives; no strategic interaction modeled; no network structure; narrow social information channel (observation only)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM confidence -- mean fitted values referenced in Supplemental Table 1 which is not accessible from the main text - winning_model formula: HIGH confidence -- equations explicitly provided in the Appendix (Equations 1-5) - wc_guidelines Rule 8: MEDIUM confidence -- qualitative model validation performed but no formal posterior predictive check - learning_mode target_type: MEDIUM confidence -- categorized as "world" (which action is safe) but could also be interpreted as learning about the demonstrator's policy; the paper frames it as learning which action avoids punishment rather than learning about the demonstrator per se
- **cannot_find:** - Mean fitted parameter values (reported in Supplemental Table 1, not in main text) - Detailed sensitivity analysis results (in supplemental material online) - Individual-level model fit statistics (e.g., log-likelihood values per participant) - Supplement not accessible for coordinate/parameter verification
- **other_notes:** This paper combines agent-based simulation modeling (macro-level group dynamics, N=100 agents) with four behavioral experiments (micro-level individual behavior). The simulation component is not fitted to data but rather demonstrates proof-of-principle for how BC and RPO interact at scale. The experimental RL model is fitted to individual participants. The paper is primarily behavioral -- no neuroimaging. The "social agent" in Exp 1-3 is a computerized demonstrator (automated system), which should be noted. Experiment 4 uses real prior participants as demonstrators. The paper provides a clear computational account linking individual reinforcement learning mechanisms to emergent cultural phenomena. Supplement available at http://dx.doi.org/10.1037/xge0000071.supp but content not directly accessible from the .txt file.
- **re_extract_flag:** false (main text fully accessible; supplement referenced but not available -- key missing items flagged above)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_action_observation
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- tax_domain_A_influence_transmission
- tax_domain_F_affective_moral
- tax_mod_action_observation
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_domain_F_affective_moral
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_social_weight
- tax_rr_primary_topic = norm_conformity
- tax_rr_secondary_topic = threat_fear
- tax_rr_topic_norm_conformity
- tax_rr_topic_threat_fear
- tax_topic_norm_conformity
- tax_topic_threat_fear
