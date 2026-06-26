# Guennouni (2022)

- **study_id:** `a0cbdcc9dfd3eb389_s4`
- **on_website:** NO — DROPPED (verify below)
- **why_not_on_website:** FLAG: This chapter fits HMMs to archival Trust Game data (King-Casas et al., 2008, and a BPD study; N=381 games total). It does not collect new behavioral data. It is a descriptive modeling exercise — the HMMs are not models of a learning process but rather unsupervised characterizations of behavioral patterns. Borderline eligible: uses computational modeling and human behavioral data, but the "learning" component is the HMM identifying latent states rather than modeling a learning process per se.

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Guennouni, I. (2022). Strategic inference in social interaction: An experimental and computational account [Doctoral dissertation, University College London]. Chapter 3.
- **doi:** Not available
- **publication_type:** thesis
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** mitted in accordance with the requirements for the degree; ethenusedtobuildandupdatestructuredrepresentations; Department of Experimental Psychology; universityoranyotherinstitution,this; University College London; mittedforadegree; etheuse
- **code_url:** 

## Computational level
- **study_focus:** Descriptive characterization of investor and trustee behavior in repeated Trust Game using Hidden Markov Models
- **study_focus_short:** Descriptive characterization of investor and trustee behavior in repeated Trust
- **learning_mode_description:** - Learning mode: Learning to maintain cooperative behavior (trustworthiness signaling) through repeated trust game interactions, with a cognitive intervention targeting reaction to trust violations     - Learning from:       - Source type (social): other (artificial HMM investor agent modeled on human behavior)       - Source content (social): action/policy (investment amounts) + outcome (net gains from cooperation)     - Learning about:       - Target type (social): other (artificial investor)       - Target content (social): state (mental state — cooperative intentions / trust level)
- **task_description:** Participants (N=318) played as trustees in two 15-round repeated Trust Games against HMM artificial investor agents, with a pre-programmed defection (very low investment) in each game. Between games, participants received either a cognitive intervention promoting non-impulsive responses to defection, or a control (anagrams). A third phase involved 7 rounds of a Prisoner's Dilemma.
- **task_paradigm:** Trust game
- **players:** Single agent (participant as trustee), single target (HMM artificial investor agent); also repeated Prisoner's Dilemma against Tit-for-Tat agent
- **n_players:** single agent (1)
- **partner_type:** computer (algorithmic)
- **stimuli:** Trust game interface (investment/return decisions), emotion self-report grid (valence × arousal), Prisoner's Dilemma payoff matrix, intervention text
- **method:** behavioural (archival data analysis)
- **main_result:** - Condition × Game-number interaction: F(1,314.2) = 26.9, p < .001 — intervention group returned higher percentages post-intervention while control group returned lower   - Main effect of Condition: F(1,315.31) = 9.52, p = 0.002   - Pre-defection trials: Condition × Game-number interaction F(1,317.99) = 17.1, p < .001 — intervention increased returns even before defection   - Post-defection: intervention prevented decrease in returns (ΔM = -0.01, ns) while control showed significant decrease (ΔM = 0.07, p < .001)   - HMM analysis: intervention group less likely in lowest-return state post-defection (22% vs 43%, χ²(1) = 14.70, p < .001)   - No transfer to Prisoner's Dilemma game   - Emotion valence decreased post-intervention (ΔM = 0.11, 95% CI [0.05, 0.18], t = 3.72, p < .001)
- **effect_size:** F(1,314.2) = 26.9 for key interaction; χ²(1) = 14.70 for HMM state comparison post-defection
- **learning_from:** Other (artificial investor agent); investment behavior as signal of trust/cooperation
- **learning_about:** Other (artificial investor agent); latent cooperative state; how to maintain cooperative relationships  ### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** 5-state HMM for investors (3-state used for parsimony); 4-state HMM for trustees (3-state used). Transition functions depend on investor's net return (for investor model) and investment received (for trustee model).
- **model_family:** Hidden Markov Model
- **model_class:** Descriptive state-space model (of participant trustee behavior)
- **all_models_tested:** [{"name": "HMM-inv (investment only)", "family": "HMM", "n_params": "varies by states", "metric": "BIC"},   {"name": "HMM-ctrl (post-control contrast)", "family": "HMM", "n_params": "varies", "metric": "BIC"},   {"name": "HMM-coax (post-intervention contrast)", "family": "HMM", "n_params": "varies", "metric": "BIC"},   {"name": "HMM-prepost (pre vs post)", "family": "HMM", "n_params": "varies", "metric": "BIC"},   {"name": "HMM-full (three-level contrast)", "family": "HMM", "n_params": "varies", "metric": "BIC"}]   Each tested with 2–7 states. Best: HMM-inv 6-state (BIC=44,813); HMM-full 5-state (BIC=45,525). HMM-full selected for interpretive power.
- **model_mb_mf:** N/A (descriptive, not RL)
- **model_params:** d (depth of planning), IA_self (disadvantageous inequity aversion / "envy"), IA_other (advantageous inequity aversion / "guilt"), Z (endowment consideration); γ (discount factor)
- **social_param:** Latent trustee states (1–5) encode levels of cooperative behavior / trustworthiness [S]; transition function modulated by investment (proxy for partner's trust) [S]
- **social_param_name:** Latent trustee states
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (for model selection); likelihood-ratio test (for comparing nested models)
- **how_model_fit:** group-level-fit (HMM fitted to pooled trustee data across participants)
- **data_type_fit_to:** choice behavior (trustee returns as proportion of received investment)  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ### QUALITY

## Quality
- **sample_size:** 381 games (93 from King-Casas et al., 2008; 288 from BPD/ASPD project); includes healthy and clinical (BPD, ASPD) participants
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Moderate. Larger sample than most trust game studies. Cognitive intervention mimics therapeutic components (from MBT/DBT traditions). But artificial HMM opponent, online setting, and short intervention duration limit generalizability.
- **eligibility_flag:** FLAG: This chapter fits HMMs to archival Trust Game data (King-Casas et al., 2008, and a BPD study; N=381 games total). It does not collect new behavioral data. It is a descriptive modeling exercise — the HMMs are not models of a learning process but rather unsupervised characterizations of behavioral patterns. Borderline eligible: uses computational modeling and human behavioral data, but the "learning" component is the HMM identifying latent states rather than modeling a learning process per se.
- **concerns:** Artificial agent opponent; short single-session intervention; no transfer to Prisoner's Dilemma; self-reported emotions via valence-arousal grid may not have been well understood by participants (low arousal after defection unexpected); no clinical sample tested; HMM fitted at group level may miss individual differences; emotion measurement differed between conditions (valence/arousal vs speed/magnitude)
- **limitations_reported:** "Assuming the AI agents used in the various experiments have a pre-determined way of making decisions and are not learning to adapt to us misses the effect of the opponent's learning"; "HMM models rely on the Markovian assumption: that the policies in each state and the transition probability between states depend only on the current latent state. This does not necessarily map well to many real-world domains"; "in fitting HMM models, we implicitly assume that all people to which we fit the model behave in the same way"; "these models have not yet been tested in more naturalistic contexts"; "humans actively gather information from their environment and are not passive recipients" — experiments force repeated interaction rather than allowing partner choice.
- **limitations_categorized:** Artificial opponents (no adaptive learning); Markov assumption violation; no individual differences in HMM; limited ecological validity; no naturalistic testing; no active partner selection; limited generalizability from economic games to real social interaction  ---  ## Summary Assessment  This thesis contains 5 empirical/computational chapters. The three chapters with human behavioral data AND computational modeling AND temporal learning in a social context are Chapters 2, 4, and 5. Chapter 3 is a descriptive modeling exercise of archival data. Chapter 6 is pure simulation.  Key strengths: Novel application of HMM strategy-switching analysis (Ch. 2); creative use of HMM-based artificial agents for controlled social interaction experiments (Ch. 4–5); large sample in Ch. 5 (N=318); sophisticated POMDP framework linking social preferences to planning depth (Ch. 6).  Key concerns: All experiments use artificial computer opponents rather than human partners; no neuroimaging data; HMMs are group-level descriptive models rather than cognitive process models of learning; no parameter recovery or model recovery checks across any chapter; no preregistration reported; data/code availability not mentioned.
- **preregistered:** Not reported
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

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** eligibility_flag (MEDIUM — automated opponent)
- **cannot_find:** Individual-level model parameters; effect sizes (Cohen's d); preregistration status; data/code availability; exact n per condition
- **other_notes:** This chapter primarily develops the tools (HMM agents) used in Chapters 4–6. Not a standalone study in the traditional sense.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- _(taxonomy layer not generated for dropped studies)_
