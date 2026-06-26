# Guennouni (2022)

- **study_id:** `a0cbdcc9dfd3eb389_s2`
- **on_website:** NO — DROPPED (verify below)
- **why_not_on_website:** FLAG: Social agent is an automated HMM system, not a human partner. However, the HMM was trained on human behavioral data and participants were not told the opponent was a computer. Qualifies with flag.

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Guennouni, I. (2022). Strategic inference in social interaction: An experimental and computational account [Doctoral dissertation, University College London]. Chapter 4.
- **doi:** Not available
- **publication_type:** thesis
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** mitted in accordance with the requirements for the degree; ethenusedtobuildandupdatestructuredrepresentations; Department of Experimental Psychology; universityoranyotherinstitution,this; University College London; mittedforadegree; etheuse
- **code_url:** 

## Computational level
- **study_focus:** Trust learning; effect of emotion cues on social inference and cooperative behavior in repeated Trust Game
- **study_focus_short:** Trust learning
- **learning_mode_description:** - Learning mode: Learning to infer the hidden state of an artificial investor (modeled as HMM) from their investment behavior and optional emotion cues, and adapting return behavior accordingly     - Learning from:       - Source type (social): other (artificial investor agent modeled on human behavior)       - Source content (social): action/policy (investment amounts) + state (emotional cues to latent trust state)     - Learning about:       - Target type (social): other (artificial investor)       - Target content (social): state (mental state — trust level / cooperative disposition)
- **task_description:** Human participants played as trustees in a repeated Trust Game (2 blocks of 50 rounds) against an artificial HMM-based investor agent. In one block, emoji cues displayed the investor's latent state (happy/neutral/unhappy); in the other, no cues were given. Order was counterbalanced.
- **task_paradigm:** Trust game
- **players:** Single agent (participant as trustee), single target (HMM artificial investor agent)
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Gamified trust game interface (seeds/tomatoes metaphor), emoji emotion cues (happy/neutral/unhappy landowner images), investment amounts
- **method:** behavioural / online
- **main_result:** - Main effect of emotion display condition on percentage returns: F(1,58.07) = 6.39, p = 0.01 — higher returns when emotions shown   - Order × Condition interaction: F(1,58.1) = 6.52, p = 0.01; when emotions shown second (after hidden), returns significantly higher in emotion condition (ΔM = 0.04, 95% CI [0.02, 0.06], z = 3.79, p < .001)   - Three-way Order × Condition × Investor State interaction: F(2,5742) = 9.95, p < .001; emotion display led to differentiated coaxing behavior — trustees returned more when investor in low-trust state   - No effect of emotion display on HMM investor behavior (ruling out confound)
- **effect_size:** F(1,58.07) = 6.39 for condition effect; F(2,5742) = 9.95 for three-way interaction
- **learning_from:** Other (artificial investor agent); investment amounts and emotion cues as signals of latent trust state
- **learning_about:** Other (artificial investor agent); latent trust state (cooperative disposition)  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** 3-state HMM investor agent (low-trust, medium-trust, high-trust) with truncated discretized Gaussian response function; transition function depends on investor's net return
- **model_family:** Hidden Markov Model
- **model_class:** Descriptive state-space model (used to program artificial agent, not fitted to participant behavior in this chapter)
- **all_models_tested:** HMM models with 2–6 states tested on archival investor data (Chapter 3); best: 5-state but 3-state used for parsimony. No model comparison on participant behavior in this chapter.
- **model_mb_mf:** N/A (HMM is a descriptive model, not an RL model)
- **model_params:** - HMM investor: μ_s, σ_s (mean and SD of truncated Gaussian response per state s); β_0,s,s', β_1,s,s' (multinomial logistic regression coefficients for state transitions as function of net return)   - No model parameters fitted to participant trustee behavior
- **social_param:** The latent trust states (low-trust, medium-trust, high-trust) encode the social variable of interest — trust level [S]
- **social_param_name:** The latent trust states
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (for HMM model selection on archival data)
- **how_model_fit:** group-level-fit (HMM fitted to pooled investor data from archival Trust Game dataset, then used to create artificial agent)
- **data_type_fit_to:** choice behavior (investment data from archival dataset)  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ### QUALITY

## Quality
- **sample_size:** N=60 (29 male, 30 female, 1 preferred not to say; age M=28.7, SD=8.52)
- **population_category:** healthy adults
- **population_age_range:** M=28.7 (SD=8.52)
- **ecological_validity:** Low-moderate. Gamified framing (farmer/landowner), but interaction with artificial agent not a real social partner. Emotion cues were emojis not real facial expressions. 50-round blocks give more data than typical trust games.
- **eligibility_flag:** FLAG: Social agent is an automated HMM system, not a human partner. However, the HMM was trained on human behavioral data and participants were not told the opponent was a computer. Qualifies with flag.
- **concerns:** Artificial agent opponent (not human); emoji cues are simplified representations of emotion; no computational modeling of participant behavior (only investor agent is modeled); no measure of participant emotion; stable equilibrium may prevent observation of cooperation breakdown; within-subjects design may carry over effects.
- **limitations_reported:** "One potential limitation of this study is the absence of emotion measurement of the participants' reaction to both the investments and the emotional cues"; "in the presence of a stable equilibrium, the investor's state would not change throughout the game" preventing measurement of cooperation repair; heterogeneity in participant reactions not captured.
- **limitations_categorized:** No participant emotion measurement; limited ecological validity; artificial opponent; potential ceiling effect in cooperation
- **preregistered:** Not reported
- **wc_rule1:** Yes
- **wc_rule2:** Partial
- **wc_rule3:** No
- **wc_rule4:** Partial
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Partial
- **wc_rule10:** Partial

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** model_class (MEDIUM — HMM not fitted to participant behavior; used only for agent); winning_model (MEDIUM — no model of participant behavior); eligibility_flag (MEDIUM — automated opponent)
- **cannot_find:** Model comparison for participant behavior; effect sizes (Cohen's d); preregistration status; data/code availability
- **other_notes:** This chapter primarily tests a behavioral manipulation (emotion cues) rather than computational modeling of participant behavior. The HMM is used to create the artificial agent, not to model the human participant. Linear mixed-effects models used for behavioral analysis.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- _(taxonomy layer not generated for dropped studies)_
