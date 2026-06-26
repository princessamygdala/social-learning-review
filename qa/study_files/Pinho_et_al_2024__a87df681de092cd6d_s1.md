# Pinho et al. (2024)

- **study_id:** `a87df681de092cd6d_s1`
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
- **study_focus:** Social media feedback learning; sensitivity to social feedback (likes) on Instagram across developmental groups (adolescents vs. adults).
- **study_focus_short:** Social media feedback learning
- **learning_mode_description:** - Learning mode: Learning from social media feedback (likes) about optimal posting behavior (engagement policy)   - Learning from:     - Source type (social): group (anonymous social media audience)       - Source content (social): outcome (number of likes received on posts)   - Learning about:     - Target type (non-social): self       - Target content (non-social): action/policy (posting latency / engagement policy)
- **task_description:** Participants' real Instagram posting behavior was modeled from trace data. The RL model estimated how the number of likes received on each post influenced the latency until the next post, capturing sensitivity to social feedback.
- **task_paradigm:** Social media (likes) task
- **players:** Single agent (Instagram user), multi-target (anonymous social media audience)
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Real Instagram posts and likes (trace data); number of likes per post, posting timestamps
- **method:** behavioural
- **method_full:** behavioural (computational analysis of Instagram trace data)
- **main_result:** - Adolescents showed a significantly higher learning rate (sensitivity to likes) than adults (M alpha = 0.0009 vs. M alpha = 0.0006; d = 0.08) - No significant age difference in effort cost parameter (M C = 81 vs. M C = 78; d ~ 0) - Results survived robustness checks (outlier removal, non-parametric tests) - RL model with diminishing utility (RLd) fit best (AIC comparison; Table S1)
- **effect_size:** d = 0.08 (learning rate age difference); r = -0.12 (non-parametric test)
- **learning_from:** group (anonymous audience); social feedback (likes on Instagram posts)
- **learning_about:** self; own posting policy/engagement behavior  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RL foraging model (3 params: alpha, C, rho); RLd variant with utility exponent d also tested and fit better but main results reported for basic RL model.
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "Null model (fixed posting strategy)", "family": "null/baseline", "n_params": 1, "metric": "AIC"} - {"name": "RL model", "family": "Rescorla-Wagner (average reward rate)", "n_params": 3, "metric": "AIC"} - {"name": "RLd model (exponential utility)", "family": "Rescorla-Wagner (average reward rate)", "n_params": 4, "metric": "AIC"}
- **model_mb_mf:** MF
- **model_params:** - alpha (learning rate) [S]: sensitivity to social media feedback (likes). Adolescents M = 0.0009; Adults M = 0.0006 - C (effort cost sensitivity): effort associated with posting. Adolescents M = 81; Adults M = 78 - rho (initial policy): initial posting latency - d (utility exponent; RLd model only): diminishing marginal utility of likes (0 <= d <= infinity)
- **social_param:** alpha (learning rate) [S] — captures sensitivity to social feedback (likes); the key developmental difference parameter. Higher alpha = greater sensitivity to social media likes.
- **social_param_name:** alpha
- **social_param_value:** 0.0009
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (Akaike Information Criterion)
- **how_model_fit:** individual-level-fit (MLE per user)
- **data_type_fit_to:** choice behavior (posting latencies / inter-post intervals)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** N/A (no neuroimaging in Study 1)
- **coordinates_peak:** 
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 16,613 (7,718 adolescents aged 13-19; 8,895 adults aged 30-39); 1,724,926 total Instagram posts
- **population_category:** mixed
- **population_age_range:** 13–19
- **ecological_validity:** High ecological validity — uses real Instagram trace data (posting timestamps and likes) from naturalistic social media behavior over a 6-month period. However, age groups were estimated from heuristics rather than verified; data from 2014-2015 may not reflect current Instagram dynamics.
- **eligibility_flag:** 
- **concerns:** Age of participants was estimated using automated heuristics and manual verification rather than directly reported. Data collected 2014-2015 may not generalize to current social media environments. Effect size for learning rate difference is small (d = 0.08). The RL model is adapted from Lindström et al. (2021) and applied to a different dataset rather than being newly developed.
- **limitations_reported:** Adults may be less responsive to likes compared to adolescents if their social media audience is smaller and less reflective of their broader social group outside social media"; the study focuses only on likes as a social feedback metric, which is only one of many social media affordances; self-reported screen time measures are unreliable; the study cannot establish causation.
- **limitations_categorized:** limited ecological validity (single affordance: likes only); potential confound (audience size differences); limited generalizability (data from 2014-2015); small effect size
- **preregistered:** Yes
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 8.5
- **wc_total:** 8.5

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
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = partly
- tax_domain_E_self_in_social_context
- tax_mod_experiential
- tax_model_MF
- tax_model_rescorla_wagner
- tax_param_learning_rate
- tax_popclass_developmental
- tax_popclass_healthy
- tax_rr_domain = E_self_in_social_context
- tax_rr_domain_E_self_in_social_context
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_primary_topic = social_approval_reward
- tax_rr_topic_social_approval_reward
- tax_topic_social_approval_reward
