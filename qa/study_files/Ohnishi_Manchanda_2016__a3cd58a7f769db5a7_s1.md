# Ohnishi & Manchanda (2016)

- **study_id:** `a3cd58a7f769db5a7_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Ohnishi, H., & Manchanda, P. (2016). Consumers' social learning about videogame consoles through multiple website browsing. *Working paper (preliminary version)*.
- **citation_short:** Ohnishi & Manchanda (2016)
- **doi:** Not available (preliminary working paper, no DOI reported).
- **publication_type:** preprint / working paper (marked "preliminary version – please do not circulate," august 2016).
- **year:** 2016.0
- **field_of_study:** Psychology
- **affiliations_raw:** Section 5 contains the preliminary results and we conclude in Section 6; mited information at the beginning, consumers were driven to search; Section 2 reviews the literature and discusses; section 3, we describe the data; Section 4; ether to
- **code_url:** 

## Computational level
- **study_focus:** Consumer social learning about product quality (videogame consoles) via online community browsing and its relationship to purchase decisions.
- **study_focus_short:** Consumer social learning about product quality (videogame consoles) via online
- **learning_mode_description:** - Learning mode: Learning from aggregated online community interactions and product review websites about videogame console quality to inform purchase decisions.   - Learning from:     - Source type (social): group (other consumers on community websites)     - Source content (social): state (aggregated opinions/information about product quality)     - *Second source:* Source type (non-social): world (product review websites); Source content (non-social): state (product information/quality signals)   - Learning about:     - Target type (non-social): world (product quality of videogame consoles)     - Target content (non-social): state (perceived product quality beliefs — cognitive and social)  ---  ### 4. COMPUTATIONAL PROBLEM  How do consumers update beliefs about product quality through dual learning processes — social learning (community-based browsing) and reason-based learning (non-community website browsing) — and how do these beliefs differentially predict purchase decisions? (Prediction / evaluation)
- **task_description:** Consumers in a Japanese clickstream panel browse videogame-related websites (community-based and non-community) over a 9-month pre-launch period (April–December 2006). Their pageview behavior is modeled as reflecting dual learning processes (social and cognitive), and product ownership (Wii, PS3, both, or other) is observed via a post-launch survey.
- **task_paradigm:** Consumer review-browsing task
- **players:** Single agent (consumer), multi-target (2 products: Wii, PS3; passive social environment via community websites).
- **n_players:** multi-target (3+)
- **partner_type:** none
- **stimuli:** Videogame website pageviews, TV advertising GRPs, public relations events, product prices.
- **method:** behavioural
- **method_full:** Behavioural (clickstream panel data + survey; no neuroimaging).
- **main_result:** - Main Results:   - Wii PRs have largest positive impact on community-based pageviews (β = 0.048, 99% HPDI significant)   - PS3 console GRPs positively correlated with community-based pageviews (β = 0.001, 95% HPDI significant)   - Social belief positively predicts purchase choice utility (β = 0.000070, 95% HPDI significant)   - Cognitive belief has negative linear effect on purchase (β = −0.000336, 99% HPDI significant) but positive quadratic effect (β = 0.000024, 95% HPDI significant), suggesting risk-taking/U-shaped relationship   - Cumulative PRs positively predict purchase (β = 0.003479, 95% HPDI significant)   - Note: Only preliminary results reported; full model results "have not been obtained yet" (authors' own words)
- **effect_size:** - Main Results:   - Wii PRs have largest positive impact on community-based pageviews (β = 0.048, 99% HPDI significant)   - PS3 console GRPs positively correlated with community-based pageviews (β = 0.001, 95% HPDI significant)   - Social belief positively predicts purchase choice utility (β = 0.000070, 95% HPDI significant)   - Cognitive belief has negative linear effect on purchase (β = −0.000336, 99% HPDI significant) but positive quadratic effect (β = 0.000024, 95% HPDI significant), suggesting risk-taking/U-shaped relationship   - Cumulative PRs positively predict purchase (β = 0.003479, 95% HPDI significant)   - Note: Only preliminary results reported; full model results "have not been obtained yet" (authors' own words)
- **learning_from:** 
- **learning_about:** 
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Bivariate Bayesian learning model (dual process: cognitive + social beliefs, correlated updating) combined with multivariate probit purchase choice. Preliminary estimation only — full model not yet fitted.
- **model_family:** Bayesian
- **model_class:** Belief updating
- **all_models_tested:** 
- **model_mb_mf:** Bayesian (model-based belief updating).  ---  ### 7. ALL MODELS TESTED  - Single-process Bayesian learning (reason-based only) — described but not formally compared - Bivariate Bayesian learning (cognitive + social) — proposed full model, not yet fully estimated - Preliminary model: Hierarchical Bayes regression for pageviews + hierarchical Bayes multivariate probit for purchase choice (this is what was actually estimated)  No formal model comparison was conducted. The paper describes a progression from simpler to more complex models but reports only preliminary results from a simplified version.  ---  ### 8. MODEL COMPARISON
- **model_params:** - c⁰_j: initial prior belief mean about product j quality - σ²_C0: variance of initial cognitive belief - σ²_c0: variance of initial belief mean across consumers - σ²_C: signal noise variance (cognitive) - σ²_D: signal noise variance (social) - d⁰_j: social belief offset [S] - ω: weight combining cognitive and social beliefs into overall quality [S] (0 ≤ ω ≤ 1) - θ₁, θ₂: coefficients on quality belief (linear, quadratic) in utility - γ₁ (Price), γ₂ (CumAd), γ₃ (CumPR): utility function coefficients - δ: complementarity parameter between products - β₀, β₁, β₂: coefficients for seasonal, TV ads, PRs in pageview equations - σ₁², σ₂², ρ₁₂: persistent taste parameters
- **social_param:** ω — weight parameter determining relative contribution of social vs. cognitive belief to overall quality belief (Q_ijT = ω·C_ijT + (1−ω)·D_ijT); d⁰_j — social belief offset from cognitive belief.  ---  ### 9. NEUROIMAGING
- **social_param_name:** ω
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** None reported. No formal model comparison (BIC, AIC, etc.) was conducted.
- **how_model_fit:** Group-level fit / hierarchical Bayes estimation (simulated maximum likelihood described for full model; MCMC with 50,000 runs and 25,000 burn-ins for preliminary model).
- **data_type_fit_to:** Choice behavior (purchase decisions) + browsing behavior (pageview counts).

## Implementation level
- **fmri_model_type:** None.
- **contrast:** N/A.
- **key_regions:** N/A.
- **coordinates_peak:** N/A.
- **analysis_type:** N/A.
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 1,078 panelists (from 7,053 survey respondents who owned videogame consoles and visited videogame websites ≥2 pageviews during April–December 2006). Demographics: Japanese consumers; no age/gender breakdown reported for analysis sample.
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Relatively high ecological validity — uses real-world clickstream data from actual browsing behavior and real purchase outcomes, not a laboratory task. However, the "social learning" is inferred from community website pageview counts (a proxy), not from actual social interactions or content. The study cannot distinguish passive browsing from active social exchange.  ---  ### 12. ELIGIBILITY FLAG
- **eligibility_flag:** "Borderline inclusion — preliminary working paper with incomplete results; social learning is consumer browsing of community websites (marketing definition), not social learning in computational psychiatry sense; dynamic Bayesian model proposed but not estimated; borderline learning-vs-information-aggregation.
- **concerns:** - Only preliminary results reported; the proposed bivariate Bayesian learning model was never actually estimated on data. - "Social learning" is operationalized as community website pageview counts — an extremely coarse proxy with no information about actual social content or interactions. - Cannot determine when purchases occurred (only post-hoc survey of ownership). - No model validation, no parameter recovery, no model comparison. - The paper is explicitly marked as a preliminary draft not intended for circulation. - Effect sizes are very small in magnitude (β coefficients on order of 10⁻⁴ to 10⁻³), making practical significance unclear.  ---  ### 14. WILSON & COLLINS CHECKLIST  1. **Design a good experiment:** Partial — uses naturalistic clickstream data (not an experiment), but the data capture relevant browsing and purchase behavior. 2. **Design good models:** Partial — describes single vs. bivariate learning models, but no formal comparison was conducted. 3. **Simulate, simulate, simulate:** No — no simulation of model predictions before fitting. 4. **Fit the parameters:** Partial — preliminary model estimated via hierarchical Bayes MCMC; full model not yet fitted. 5. **Check parameter recovery:** No. 6. **Check model recovery:** No. 7. **Fit real data and compare models:** No — no formal model comparison. 8. **Validate the winning model:** No — no posterior predictive checks or model validation. 9. **Analyze the winning model:** Partial — posterior means and HPDIs reported for preliminary model. 10. **Report results transparently:** No — no data or code sharing mentioned; results are preliminary.
- **limitations_reported:** 
- **limitations_categorized:** 
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** No
- **wc_rule9:** Partial
- **wc_rule10:** No
- **wc_score:** 2.0
- **wc_total:** 2.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - `winning_model`: LOW confidence — the proposed full model was never estimated; only a preliminary simplified version was run. - `effect_size`: LOW confidence — only Bayesian posterior means with HPDIs reported; no standardized effect sizes. - `learning_mode`: MEDIUM confidence — "social learning" is defined differently here (marketing/consumer behavior) than in computational psychiatry. - `model_params`: MEDIUM confidence — full parameter list described for proposed model, but fitted values only available for preliminary model.
- **cannot_find:** Full model estimation results; standardized effect sizes; DOI; formal model comparison statistics; parameter recovery; sample demographics beyond nationality.
- **other_notes:** This is a marketing/consumer behavior working paper that uses "social learning" in the sense of consumers browsing community websites about products. It does not involve learning from observing others' choices, outcomes, or mental states in the cognitive science sense. The bivariate Bayesian learning framework is mathematically interesting but was never fully estimated. The paper was marked as a preliminary draft in August 2016 and may never have been published in final form. Supplement not available (none found).
- **re_extract_flag:** false (full text was accessible, but results are inherently incomplete per authors).

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_social_info_search
- spec_depth = parametric
- spec_locus = source
- tax_domain_A_influence_transmission
- tax_mod_social_info_search
- tax_model_bayesian
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = A_influence_transmission
- tax_rr_domain_A_influence_transmission
- tax_rr_model_bayesian
- tax_rr_model_family = bayesian
- tax_rr_param_social_weight
- tax_rr_primary_topic = social_info_use
- tax_rr_topic_social_info_use
- tax_topic_social_info_use
