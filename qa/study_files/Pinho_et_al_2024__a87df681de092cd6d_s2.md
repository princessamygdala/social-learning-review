# Pinho et al. (2024)

- **study_id:** `a87df681de092cd6d_s2`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** da Silva Pinho, A., Céspedes Izquierdo, V., Lindström, B., & van den Bos, W. (2024). Youths' sensitivity to social media feedback: A computational account. *Science Advances*, *10*, eadp8775. https://doi.org/10.1126/sciadv.adp8775
- **citation_short:** Pinho et al. (2024)
- **doi:** 10.1126/sciadv.adp8775
- **publication_type:** peer-reviewed journal
- **year:** 2024.0
- **field_of_study:** Neuroscience
- **affiliations_raw:** department of Psychology, University of Amsterdam, Amsterdam, netherlands; mitations in the literature, it is cru-; ether, these findings highlight the; mpirical evidence is lacking; mitation in the field (27,; ether, these results sup-; mit on the posting rate)
- **code_url:** https://osf.io/mt2nv/

## Computational level
- **study_focus:** Social media feedback and mood; how changes in likes affect adolescents' vs. adults' mood in a simulated social media environment.
- **study_focus_short:** Social media feedback and mood
- **learning_mode_description:** - Learning mode: Learning from social media feedback (likes) about posting behavior and mood impact   - Learning from:     - Source type (social): group (anonymous social media audience; experimentally manipulated)       - Source content (social): outcome (number of likes received; high reward vs. low reward)   - Learning about:     - Target type (non-social): self       - Target content (non-social): state (mood / affective state) and action/policy (posting latency)
- **task_description:** Participants scrolled a meme feed and posted memes for 14 minutes in a simulated social media platform. They received real feedback (likes) in a high reward condition (28-34 likes) followed by a low reward condition (6-18 likes), with mood measured at three time points.
- **task_paradigm:** Social media (likes) task
- **players:** Single agent (participant), multi-target (anonymous raters)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Memes (humorous images), number of likes (28-34 in HR; 6-18 in LR), mood slider (1-100 scale)
- **method:** online
- **method_full:** online (experimental)
- **main_result:** - Adolescents' mood was more affected by reduction in likes (T2 mood change: M = -5.96 adolescents vs. M = -2.71 adults; r = 0.17) - Adolescents ended experiment with more negative mood (T3: M = -5.26 vs. M = 1.19; r = 0.18) - No interaction effect of reward condition and age group on posting latencies - Adolescents posted less often (main effect of age group: b = 0.36, z = 2.75) - Effects independent of self-reported problematic social media behavior or social anxiety
- **effect_size:** r = 0.17 (T2 mood difference); r = 0.18 (T3 mood difference); r = 0.12 (T1 baseline, ns)
- **learning_from:** group (anonymous audience); manipulated social feedback (number of likes)
- **learning_about:** self; own mood/affective state and posting behavior  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** Mood-RL simulation model: m(t+1) = m(t) + eta(t) * (delta(t) - m(t)), where delta is generated from the RL model. Not formally fit to Study 2 data — used for simulations/predictions only. Study 2 analyses were model-free (Mann-Whitney U tests, mixed models).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** N/A — Study 2 used model-free analyses (Mann-Whitney U tests, generalized linear mixed models). The mood-RL model was used for simulation predictions only, not formally compared against alternatives on Study 2 data.
- **model_mb_mf:** MF
- **model_params:** For the mood-RL simulation: alpha (from Study 1 results), eta (mood learning rate; held constant across groups), m (current mood), delta (net reward prediction error from RL model). Not fit to Study 2 data.
- **social_param:** alpha [S] — sensitivity to social feedback, taken from Study 1 parameter estimates for simulations
- **social_param_name:** alpha [S]
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** N/A (model-free analyses in Study 2)
- **how_model_fit:** simulate-and-compare (mood-RL simulations used Study 1 parameters to predict Study 2 patterns; empirical analyses were model-free)
- **data_type_fit_to:** N/A (no model fitting to Study 2 data; model-free analysis of mood ratings and posting latencies)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 194 (92 adolescents aged 16-20; 102 adults aged 30-40); recruited via Instagram from English-speaking countries
- **population_category:** mixed
- **population_age_range:** 16–20
- **ecological_validity:** Moderate — used a social media simulator mimicking Instagram features (feed scrolling, posting, receiving likes), but the experimental context is artificial; fixed order of HR then LR conditions may introduce order effects; meme posting is constrained (selecting from 6 pre-rated options).
- **eligibility_flag:** Borderline — Study 2 does not involve computational model fitting to behavioral data. The mood-RL model was used for simulations/predictions only, and empirical analyses were model-free. Flagged as borderline for inclusion criterion "uses computational modeling.
- **concerns:** Fixed order (HR always before LR) may confound reward condition with fatigue or time effects. No formal RL model was fit to Study 2 behavioral data due to insufficient number of trials per participant. Mood-RL model was used for predictions only, with parameters borrowed from Study 1.
- **limitations_reported:** Our experimental study does not focus on or directly measure mood variability"; "the limited number of trials within the subject... would not allow for the implementation of a reinforcement learning model including mood changes"; study was "not designed to test" sex differences and had "small and unbalanced sample sizes.
- **limitations_categorized:** task simplicity; limited trial number; fixed condition order; limited generalizability; underpowered for subgroup analyses
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** Yes
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** 
- **wc_rule10:** Yes
- **wc_score:** 3
- **wc_total:** 3.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** yes
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - Study 2 eligibility: MEDIUM confidence — model was used for simulations only, not fit to Study 2 data - Study 3 coordinates: LOW confidence — no MNI coordinates available (structural volumetric analysis, not voxel-based) - Study 1 age estimates: MEDIUM confidence — participant ages estimated via automated heuristics, not self-reported - Effect sizes for Study 3: LOW confidence — random forest importance coefficients reported but not standard effect sizes - Model formula: MEDIUM confidence — exact mathematical formula not written out in full in the paper; described verbally and in Figure 1 caption (policy update based on alpha, delta, and change in posting latency)
- **cannot_find:** - Exact mathematical formula for the RL model (described verbally and in figure caption but not as a formal equation in the text; based on Lindström et al., 2021) - MNI peak coordinates (structural volumetric analysis used atlas parcellations) - Standard effect sizes for Study 3 brain-behavior associations - Specific AIC values for Study 1 RLd model comparisons between age groups separately (Table S1 has values but only total AIC reported in supplement text)
- **other_notes:** This paper builds on and extends Lindström et al. (2021) RL model of social media engagement. The same computational framework is applied across all three studies. The mood-RL model in Study 2 (m(t+1) = m(t) + eta(t) * (delta(t) - m(t))) draws on Rutledge et al. (2014) and Eldar & Niv (2015) but was used only for simulation, not model fitting. Studies 1 and 2 were preregistered; Study 3 was exploratory. Data and code are available at https://osf.io/m7hw6/.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_depth = parametric
- spec_locus = source+target+context
- spec_source = social
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MB_MF_hybrid
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_topic_social_approval_reward
