# Guennouni (2022)

- **study_id:** `a0cbdcc9dfd3eb389_s1`
- **on_website:** NO — DROPPED (verify below)
- **why_not_on_website:** Borderline social context — opponent is a pre-programmed computer agent with fixed strategy, not a social agent. Competitive zero-sum games lack cooperative social dimension. However, task explicitly framed as opponent modeling and the work tests opponent model transfer, which is a social cognitive ability. FLAG but do not exclude.

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Guennouni, I. (2022). Strategic inference in social interaction: An experimental and computational account [Doctoral dissertation, University College London]. Chapter 2.
- **doi:** Not available
- **publication_type:** thesis
- **field_of_study:** Behavioural economics / Economics
- **affiliations_raw:** mitted in accordance with the requirements for the degree; ethenusedtobuildandupdatestructuredrepresentations; Department of Experimental Psychology; universityoranyotherinstitution,this; University College London; mittedforadegree; etheuse
- **code_url:** 

## Computational level
- **study_focus:** Opponent model learning and transfer in competitive zero-sum games; strategy inference via iterative reasoning
- **study_focus_short:** Opponent model learning and transfer in competitive zero-sum games
- **learning_mode_description:** - Learning mode: Learning the depth of iterative reasoning of a computer opponent to predict their actions and transfer this knowledge across structurally similar games     - Learning from:       - Source type (non-social): other (computer opponent)         - Note: opponent is a pre-programmed computer agent       - Source content (non-social): action/policy (opponent's action choices conditional on previous round play)     - Learning about:       - Target type (non-social): other (computer opponent)       - Target content (non-social): action/policy (opponent's level of iterative reasoning / strategy type)
- **task_description:** Participants played three sequential zero-sum games (Rock-Paper-Scissors, Fire-Water-Grass, and Numbers/Shootout) against computer opponents with fixed level-k strategies (level-1 or level-2). In Experiment 1 (N=52), participants faced one opponent type across all games; in Experiment 2 (N=50), they faced both opponent types within each game across 4 stages.
- **task_paradigm:** Matching pennies
- **players:** Single agent (participant), single target (computer opponent) in Exp 1; Single agent (participant), multi-target (2 computer opponents: level-1 and level-2) in Exp 2
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Abstract game interfaces (Rock-Paper-Scissors icons, Fire-Water-Grass icons, number selections, penalty shootout interface), win/loss/tie feedback
- **method:** behavioural / online
- **main_result:** - Participants successfully exploited opponent deviations from Nash play across all games (RPS: M = 0.29, t(51) = 7.26, p < .001; FWG: M = 0.45, t(51) = 10.05, p < .001; Numbers: M = 0.31, t(51) = 7.18, p < .001 — Exp 1)   - Early-round (2–6) performance in later games significantly above chance, indicating transfer of opponent knowledge (FWG early: M = 0.24, t(51) = 4.13, p < .001; Numbers early: M = 0.15, t(51) = 3.48, p = .001 — Exp 1)   - HMM analysis of strategy switching: switching model significantly better than non-switching (Exp 1: χ²(6) = 211.09, p < .001; Exp 2: χ²(6) = 70.44, p < .001)   - Evidence of BCH→RL strategy switching: BCH model dominant in early rounds of later games, RL dominant in later rounds
- **effect_size:** - No Cohen's d or r² reported directly; t-statistics and confidence intervals provided for behavioral scores
- **learning_from:** Other (computer opponent); opponent's actions in zero-sum games conditional on previous round play
- **learning_about:** Other (computer opponent); opponent's strategy type / level of iterative reasoning  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** HMM mixture of BCH_BT + RL + Nash (switching between strategies); for individual fit: RL wins by BIC overall, but BCH_BT best in early rounds of later games
- **model_family:** Q-learning
- **model_class:** Multi-strategy: Bayesian type inference + prediction error learning + strategy arbitration
- **all_models_tested:** - Exp 1: [{"name": "Nash (random)", "family": "baseline", "n_params": 0, "metric": "BIC"}, {"name": "RL", "family": "Q-learning", "n_params": 2, "metric": "BIC"}, {"name": "EWA (self-tuning)", "family": "Experience-Weighted Attraction", "n_params": 1, "metric": "BIC"}, {"name": "BCH_NBT", "family": "Bayesian Cognitive Hierarchy", "n_params": 2, "metric": "BIC"}, {"name": "BCH_BT", "family": "Bayesian Cognitive Hierarchy", "n_params": 2, "metric": "BIC"}]   - Exp 2: additionally includes RL_WT, RL_NT, EWA_WT, EWA_NT, BCH_WT, BCH_NT variants (8 models total)   - HMM strategy-switching models (switching vs. non-switching)
- **model_mb_mf:** MB/MF hybrid (BCH is model-based; RL is model-free; HMM captures switching between them)
- **model_params:** - RL: α (learning rate), λ (inverse temperature)   - EWA: λ (inverse temperature; δ and φ self-tuned)   - BCH: θ (probability opponent chooses randomly), λ (inverse temperature)   - HMM: initial state probabilities, transition probabilities (estimated via depmixS4)
- **social_param:** θ (estimated probability that opponent takes a random action — captures uncertainty about opponent's strategic consistency); level-k posterior probabilities (belief about opponent's depth of reasoning)
- **social_param_name:** θ
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** BIC (for individual model fit); AIC and BIC for HMM switching vs non-switching; likelihood-ratio test for HMM comparison
- **how_model_fit:** individual-level-fit (MLE via DEoptim for RL/EWA/BCH; depmixS4 for HMM)
- **data_type_fit_to:** choice behavior  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** 
- **analysis_type:** N/A  ### QUALITY

## Quality
- **sample_size:** Exp 1: N=52 (28 female, 24 male; mean age 31.2); Exp 2: N=50 (21 female, 28 male, 1 unknown; mean age 30.2)
- **population_category:** healthy adults
- **population_age_range:** M=31.2
- **ecological_validity:** Low. Computer opponents with fixed pre-programmed strategies; zero-sum competitive games with no real social interaction; game order not counterbalanced
- **eligibility_flag:** Borderline social context — opponent is a pre-programmed computer agent with fixed strategy, not a social agent. Competitive zero-sum games lack cooperative social dimension. However, task explicitly framed as opponent modeling and the work tests opponent model transfer, which is a social cognitive ability. FLAG but do not exclude.
- **concerns:** Game order not counterbalanced (always RPS→FWG→Numbers/Shootout); practice effects cannot be fully ruled out; computer opponents do not learn/adapt; Experiment 2 had only 10% random noise in opponent play making strategies relatively easy to detect; the "social" nature of facing a computer opponent is minimal.
- **limitations_reported:** "A limitation of the design of both experiments is that the order of the games was not counterbalanced"; "we can't rule out that part of the transfer effects found for early round scores is due to general practice effects, or differences in the difficulty of the games"; participants faced computer agents rather than humans limiting ecological validity.
- **limitations_categorized:** No counterbalancing of conditions; potential practice effects confound; limited ecological validity; computer opponents
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
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** social_param (MEDIUM — θ is not explicitly described as a "social" parameter; it captures strategic uncertainty about opponent); eligibility_flag (MEDIUM — borderline social context)
- **cannot_find:** Effect sizes (Cohen's d, r²); preregistration status; data/code availability
- **other_notes:** Chapter 2 was published as Guennouni & Speekenbrink (2022) in Computational Brain and Behavior. If that published version is in the papers folder, this thesis chapter should be flagged as duplicate_suspected. The HMM switching analysis is particularly novel — it demonstrates BCH→RL strategy switching within games.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- _(taxonomy layer not generated for dropped studies)_
