# Radell et al. (2016)

- **study_id:** `ac0d19c94aa17f8df_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Radell, M. L., Sanchez, R., Weinflash, N., & Myers, C. E. (2016). The personality trait of behavioral inhibition modulates perceptions of moral character and performance during the trust game: Behavioral results and computational modeling. *PeerJ*, *4*, e1631. https://doi.org/10.7717/peerj.1631
- **citation_short:** Radell et al. (2016)
- **doi:** 10.7717/peerj.1631
- **publication_type:** peer-reviewed journal
- **year:** 2016.0
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** DepartmentofPharmacology,Physiology&Neuroscience,NewJerseyMedicalSchool,Rutgers,TheState; College,Rutgers,TheStateUniversityofNewJersey—Newark,Newark,NJ,UnitedStates; Laboratory,VANewJerseyHealthCareSystem,EastOrange,NJ,UnitedStates; UniversityofNewJersey—Newark,Newark,NJ,UnitedStates; ethe‘‘biases’’engenderedbypriorinformation(Fareri,; UniversityofNewJersey,Newark,NJ,UnitedStates; mitted5October2015 self-reportquestionnaire; DepartmentofPsychology,Rutgers,; emails: Milen.Radell@va.gov
- **code_url:** 

## Computational level
- **study_focus:** Trust learning; how the personality trait of behavioral inhibition (BI) modulates implicit trust of partners with varying moral reputations, and how initial trust biases and learning rates account for behavioral differences in the trust game.
- **study_focus_short:** Trust learning
- **learning_mode_description:** - Learning mode: Learning from partners' reciprocation outcomes about partners' trustworthiness during a trust game, modulated by prior biographical information and personality (behavioral inhibition)   - Learning from:     - Source type (social): other (fictional partner)     - Source content (non-social): outcome (monetary reciprocation or defection)   - Learning about:     - Target type (social): other (fictional partner)     - Target content (social): state (mental state; trustworthiness/cooperativeness)
- **task_description:** Participants played a trust game with three fictional partners (portrayed via biographies as trustworthy, untrustworthy, or neutral). On each of 72 trials, participants chose to keep $1 or share $3 with a partner; if shared, the partner reciprocated with 50% probability regardless of biography.
- **task_paradigm:** Trust game
- **players:** Single agent (participant), multi-target (3 fictional partners: good, bad, neutral)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Faces (NimStim neutral white male faces), biographical text descriptions, binary monetary outcomes ($0 or $1.50 on share trials)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - Inhibited participants made significantly more "keep" responses with the neutral partner than uninhibited participants (F(1,111) = 5.049, p = .027, η²p = .044) - AMBI score significantly predicted "keep" responses for the neutral partner (β = .279, p = .012; R² = .344 for regression model) - Pre-game trust ratings showed the biography manipulation was effective: good > neutral > bad (F(1.69, 191.28) = 216.561, η²p = .657) - Computational modeling: θ_Neutral was significantly lower for inhibited than uninhibited participants (F(1,110) = 7.104, p = .009, η²p = .061) - No significant differences in learning rate (α) or temperature (β) between BI groups (all F < 1, all p > .600)
- **effect_size:** - Trust ratings partner main effect: η²p = .657 - Trust ratings time main effect: η²p = .194 - Trust ratings partner × time interaction: η²p = .383 - BI effect on keep responses (neutral partner): η²p = .044 - Regression: AMBI → keep (neutral partner): β = .279; model R² = .344 - θ values: good > neutral (r² = .21); good > bad (r² = .48); neutral > bad (r² = .26) - BI main effect on θ values: η²p = .058 - BI effect on θ_Neutral: η²p = .061
- **learning_from:** Other (fictional partner); partner's reciprocation/defection outcomes
- **learning_about:** Other (fictional partner); partner's trustworthiness  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** RW with 3 initial trust values and shared learning rate and temperature: "3θ, free α, β" (5 params: θ_Good, θ_Bad, θ_Neutral, α, β)
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** - {"name": "All free", "family": "Rescorla-Wagner", "n_params": 12, "metric": "AIC"} - {"name": "3θ, fixed α, β", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC"} - {"name": "3θ, free α, β", "family": "Rescorla-Wagner", "n_params": 5, "metric": "AIC"} - {"name": "3θ, free α, fixed β", "family": "Rescorla-Wagner", "n_params": 4, "metric": "AIC"} - {"name": "3θ, fixed α, free β", "family": "Rescorla-Wagner", "n_params": 4, "metric": "AIC"} - {"name": "LG (Fareri et al., 2012)", "family": "Rescorla-Wagner", "n_params": 3, "metric": "AIC"} - {"name": "Random", "family": "Baseline", "n_params": 0, "metric": "negLLE"}
- **model_mb_mf:** MF
- **model_params:** - θ_Good: initial trust estimate for good partner [S], constrained 0–1. Inhibited mean higher than θ_Neutral and lower than uninhibited (exact fitted values not reported individually) - θ_Bad: initial trust estimate for bad partner [S], constrained 0–1 - θ_Neutral: initial trust estimate for neutral partner [S], constrained 0–1. Significantly lower for inhibited vs. uninhibited participants (η²p = .061) - α: learning rate (α_gain = α_loss), constrained 0–1 - β: inverse temperature, constrained 0–1
- **social_param:** θ_Good, θ_Bad, θ_Neutral — initial trust estimates for each partner reflecting prior social information (biography-based beliefs about trustworthiness). θ_Neutral was the key differentiator between inhibited and uninhibited participants.
- **social_param_name:** θ_Good
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** AIC (Akaike Information Criterion); Friedman's ANOVA on AIC across models with Bonferroni-corrected Wilcoxon signed ranks post-hoc tests
- **how_model_fit:** individual-level-fit (grid search over parameter space for each participant; best-fit parameter combination minimizing negative log-likelihood)
- **data_type_fit_to:** choice behavior (keep vs. share decisions, trial-by-trial)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (behavioural study only)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 114 (73 female, 41 male; mean age 21.4 years, SD = 5.0); 44 classified as inhibited (AMBI ≥ 16), 70 as uninhibited
- **population_category:** healthy adults
- **population_age_range:** M=21.4
- **ecological_validity:** Low ecological validity — partners were fictional (computer-controlled), always white males, participants likely aware partners were not real; biographies were simplified text; no real monetary stakes described; lab-based task with limited social interaction
- **eligibility_flag:** 
- **concerns:** - The "3θ, free α, β" and "3θ, fixed α, free β" models were statistically tied for best fit (p = .017 did not survive Bonferroni correction at .0033); the authors chose the 5-parameter model based on theoretical interest rather than statistical superiority - Grid search with step size 0.05 for the winning model may miss optimal parameter values - No parameter recovery or model recovery analyses - No posterior predictive checks - Partners were computer-controlled; ecological validity limited - Inhibited males underrepresented (9 of 31 males) - Mean fitted parameter values not reported (only group comparisons via ANOVA)
- **limitations_reported:** Partners were always white and male, limiting exploration of partner appearance effects on trust; partners were computer-controlled and participants were likely aware; inhibited males were underrepresented and study may have lacked power to detect gender effects; the selected model could be considered preliminary and should be tested on different data sets; no neuroimaging data to examine neural substrates
- **limitations_categorized:** limited ecological validity; limited stimulus diversity; sample composition bias; no neural data; model selection uncertainty; task simplicity
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 6.0
- **wc_total:** 6.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM — some effect sizes reported as η²p and r²; β from regression reported but not all standardized - model_params fitted values: LOW — mean fitted parameter values per group not reported, only ANOVA comparisons on estimated parameters - winning_model selection: MEDIUM — two models statistically tied; selection based on theoretical interest
- **cannot_find:** - Exact mean fitted parameter values (θ, α, β) per BI group — not reported in text - Code for computational modeling — not shared
- **other_notes:** - Supplement contains raw dataset (uploaded as supplemental files) but no additional modeling details or equations beyond what is in the main text - The model equations are clearly specified in the paper (Equations 1–4) - This paper is purely behavioral; the discussion section speculates about neural substrates (caudate, hippocampus, amygdala, insula, cingulate) based on prior literature but no neuroimaging was conducted in this study - Partners were automated/fictional — flagged but not excluded per instructions
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_anxiety
- pop_healthy_adults
- rr_pop_anxiety
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = source+target
- spec_source = social
- spec_target = social
- tax_domain_C_exchange_interdependence
- tax_mod_experiential
- tax_mod_instructed
- tax_model_MF
- tax_model_rescorla_wagner
- tax_popclass_clinical
- tax_popclass_healthy
- tax_rr_domain = C_exchange_interdependence
- tax_rr_domain_C_exchange_interdependence
- tax_rr_model_family = rescorla_wagner
- tax_rr_model_rescorla_wagner
- tax_rr_param_learning_rate
- tax_rr_param_valence_asymmetry
- tax_rr_primary_topic = trust
- tax_rr_topic_trust
- tax_topic_trust
