# Flournoy (2018)

- **study_id:** `ae1d06b9cc1a41631_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Flournoy, J. C. (2018). *Adolescent social motives: Measurement and implications* [Doctoral dissertation, University of Oregon]. ProQuest Dissertations & Theses Global (No. 10935841).
- **citation_short:** Flournoy (2018)
- **doi:** Not available (ProQuest Number: 10935841)
- **publication_type:** thesis
- **year:** 2018.0
- **field_of_study:** Philosophy
- **affiliations_raw:** collegestudent(N=230)participantslearnedfoursocial-motive-relevant,; ethevalidityofbehavioronthetaskasameasureofparticularmotivations,; Ethics-RelevantValuesinAdulthood: LongitudinalFindingsfromtheLife; mithSummerProfessionalDevelopmentAward,UniversityofOregon,2015; etheexistenceofmotivationsthatarethoughttobecentraltothis; UniversityofCalifornia,Berkeley,CA,USA; UniversitySchoolofMedicine,2009–2012; UniversityofOregonGraduateSchool
- **code_url:** 

## Computational level
- **study_focus:** Social motive effects on reinforcement learning; how adolescent-relevant social motivational framing (mate-seeking, social status) modulates stimulus salience and learning rate in a probabilistic reinforcement learning task.
- **study_focus_short:** Social motive effects on reinforcement learning
- **learning_mode_description:** - Learning mode: Learning face-word associations where social-motive framing of descriptors (dating/status vs. baseline) modulates reinforcement learning   - Learning from:     - Source type (non-social): world     - Source content (non-social): outcome (probabilistic binary feedback: correct/incorrect + points)   - Learning about:     - Target type (social): other (computer-generated faces)     - Target content (social): state (social descriptors: dating status, popularity)
- **task_description:** Participants view computer-generated faces paired with two descriptors (e.g., Popular vs. Unpopular) and learn which descriptor is probabilistically associated with each face (P = .80) across three conditions: baseline (Hungry/Thirsty), mate-seeking (Dating/Looking), and status (Popular/Unpopular), receiving point-based feedback on each trial across 384 trials.
- **task_paradigm:** Probabilistic reward learning
- **players:** Single agent (participant), no interactive partner; stimuli are computer-generated faces.
- **n_players:** single agent (1)
- **partner_type:** none
- **stimuli:** Computer-generated human faces (3 male, 3 female), text descriptors (Hungry/Thirsty, Dating/Looking, Popular/Unpopular), binary point feedback (0 or 1/5 points).
- **method:** online / behavioural
- **method_full:** behavioural (in-lab and online)
- **main_result:** - Social-motive conditions (Dating/Looking, Popular/Unpopular) enhanced learning relative to baseline (Hungry/Thirsty):   - Dating/Looking vs. Hungry/Thirsty: t(185) = 2.69, D = 0.029, CI_95 = [0.008, 0.051]   - Popular/Unpopular vs. Hungry/Thirsty: t(185) = 4.54, D = 0.047, CI_95 = [0.027, 0.068] - Learning rate (epsilon) was credibly higher in both social conditions vs. baseline (99.5% credible intervals above 0) - No credible age x social-condition interaction on learning enhancement (beta ~ 0 for all contrasts with age) - Older participants showed better overall task performance (beta = 0.17 in adolescent sample) - Noise parameter (xi) negatively associated with PDS across full sample (beta = -0.14, t = -2.55) - Reward modifier (rho) correlated with participant confidence (r = .37, 99.5% CI = [.22, .50]) - Individual differences in social-motive learning enhancement did not correlate with self-report traits or health-related behaviors
- **effect_size:** D = 0.029 (Dating/Looking vs. baseline); D = 0.047 (Popular/Unpopular vs. baseline); beta = 0.17 (age-optimal choices, adolescents); r = .37 (rho-confidence); r = -0.34 (xi-confidence)
- **learning_from:** World; probabilistic binary feedback (correct/incorrect + points) on face-word association choices.
- **learning_about:** Other (social); face-descriptor associations framed as social attributes (dating status, popularity) of computer-generated individuals.  ---  ## ALGORITHMIC LEVEL
- **outcome_modality:** mixed

## Algorithmic level
- **winning_model:** Rescorla-Wagner with 4 condition-specific parameters: learning rate (epsilon), reward modifier/inverse temperature (rho), irreducible noise (xi), right-arrow bias (b); hierarchical Bayesian estimation (3-level: population, sample, individual).
- **model_family:** Rescorla-Wagner
- **model_class:** PE learning
- **all_models_tested:** 1. {"name": "3-level maximal (epsilon, rho, xi, b)", "family": "Rescorla-Wagner", "n_params": "4 per condition x 3 conditions = 12 per individual + hierarchical", "metric": "LOOIC = 134588.73"} 2. {"name": "2-level maximal (epsilon, rho, xi, b)", "family": "Rescorla-Wagner", "n_params": "4 per condition x 3 conditions = 12 per individual + hierarchical", "metric": "LOOIC = 134590.78"} 3. {"name": "3-level without b (epsilon, rho, xi)", "family": "Rescorla-Wagner", "n_params": "3 per condition x 3", "metric": "LOOIC = 135881.48"} 4. {"name": "2-level without b (epsilon, rho, xi)", "family": "Rescorla-Wagner", "n_params": "3 per condition x 3", "metric": "LOOIC = 135891.82"} 5. {"name": "3-level without b, rho (epsilon, xi)", "family": "Rescorla-Wagner", "n_params": "2 per condition x 3", "metric": "LOOIC = 136889.85"} 6. {"name": "2-level without b, rho (epsilon, xi)", "family": "Rescorla-Wagner", "n_params": "2 per condition x 3", "metric": "LOOIC = 136914.50"}
- **model_mb_mf:** MF
- **model_params:** - epsilon (learning rate), per condition k and individual j; transformed to [0,1] via approximate normal CDF. Population priors: mu ~ N(0,5), sigma ~ exponential(1). No mean fitted values reported on constrained scale. - rho (reward modifier / inverse temperature), per condition k and individual j; transformed to [0, inf) via exp(). Scales magnitude of reward. - xi (irreducible noise), per condition k and individual j; transformed to [0,1]. When xi = 1, P = 0.5 (random responding). - b (right-arrow bias), per condition k and individual j; no transformation needed. Encodes bias toward pressing right. - [S] The condition-specific variation in epsilon across social vs. baseline conditions is the key "social" parameter; social-condition learning rates were credibly higher than baseline.
- **social_param:** Condition-specific learning rate differences (epsilon_social - epsilon_baseline): the difference in learning rates between social-motive conditions (Dating/Looking, Popular/Unpopular) and the minimally social baseline (Hungry/Thirsty), reflecting social-motive salience effects on learning.
- **social_param_name:** Condition-specific learning rate differences
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Leave-one-individual-out cross-validation information criterion (LOOIC), estimated via the R package loo.
- **how_model_fit:** individual-level-fit (hierarchical Bayesian; RStan, 6 chains, 1200 warm-up + 334 sampling iterations per chain)
- **data_type_fit_to:** choice behavior (binary left/right button press)  ---  ## IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ## QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 334 (118 male; 4 subsamples: FCA n=39, CA n=65, CSYA n=85, CSYA-O n=145); ages 12.5-25 years. After exclusion of 1 participant >25 years and 6 for inattentive responding. Effective task-completing N varies slightly by analysis due to missing data (~21 missing task data total).
- **population_category:** adolescents
- **population_age_range:** 5–25
- **ecological_validity:** Low. Computer-generated faces with text descriptors in a probabilistic learning task; no real social interaction or consequences. Participants may not perceive the task as relevant to their actual social motives. Author acknowledges that "learning about the popularity of a computer-generated face may not be enhanced by a person's status motives because it is clear that this information is not instrumentally valuable.
- **eligibility_flag:** FLAG -- This is a dissertation. Aim 1 (Chapter III) uses computational modeling with human behavioral data in a social learning context and qualifies. Aim 2 (Chapter IV) examines correlations between task variables and self-report measures without additional computational modeling -- it is ancillary to Aim 1. The "social" element is limited: participants learn face-word associations where words are social descriptors, but there is no social interaction, no learning from social agents, and no social feedback. The task is better characterized as standard reinforcement learning with social stimulus framing rather than truly social learning. Borderline eligibility: the learning is about social attributes of others (dating status, popularity), but the learning process itself is non-social (learning from probabilistic feedback, not from other agents). Flag as borderline social learning.
- **concerns:** - The social manipulation is framing-only (word descriptors on faces); no actual social interaction or social feedback occurs - Cross-sectional design prevents developmental inference - Binary choice outcomes yield low reliability for individual difference measures - Only one stimulus manipulation per motive domain limits generalizability - No comparison of alternative model families (e.g., Bayesian, instance-based learning) - Adolescent and college samples differ on many characteristics beyond age (e.g., all older participants are university students) - The dissertation does not report fitted parameter values on the constrained scale at the population level, only contrasts - Trait-state confound between conditions (Hungry/Thirsty = states; Dating/Popular = more trait-like)
- **limitations_reported:** Learning task may be obviously irrelevant to actual social goals participants have; binary choice outcomes are less reliable indicators of latent constructs than continuously measured behavior; minimal stimulus set examines only a small slice of possible motive-relevant descriptors; social descriptors convey relational/network information confounded with motive relevance; trait-state dimension confounded across conditions; only RW-family models tested; cross-sectional data precludes developmental inference; samples not exchangeable across age; task measures did not correlate with self-report traits, possibly due to low construct validity of one or both measurement approaches; limited generalizability from single manipulation per motive domain.
- **limitations_categorized:** Limited ecological validity; measurement reliability; stimulus generalizability; confounded experimental conditions; limited model space; cross-sectional design; sample non-exchangeability; low convergent validity between task and self-report; task simplicity.
- **preregistered:** No
- **wc_rule1:** Partial
- **wc_rule2:** Partial
- **wc_rule3:** Yes
- **wc_rule4:** Yes
- **wc_rule5:** Yes
- **wc_rule6:** No
- **wc_rule7:** Yes
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Partial
- **wc_score:** 7.0
- **wc_total:** 7.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** no
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - eligibility_flag (MEDIUM): Borderline social learning -- task uses social stimulus framing but learning is from non-social probabilistic feedback - social_param (MEDIUM): No single dedicated social parameter; the "social" component is the condition-level variation in standard RL parameters - model_params (MEDIUM): Population-level fitted values not reported on constrained scales; only contrasts and unconstrained posterior means shown - wc_guidelines Rule 10 (MEDIUM): Dissertation is CC-licensed but explicit data/code repository link not confirmed
- **cannot_find:** - DOI (dissertation has ProQuest number but no DOI) - Exact mean fitted parameter values on constrained scale for population-level estimates - Explicit data/code sharing repository URL (though CC license mentioned)
- **other_notes:** This is a dissertation with two aims. Only Aim 1 (Chapter III) involves computational modeling. Aim 2 (Chapter IV) is correlational analysis of self-report measures and task variables. The dissertation is notable for rigorous Bayesian modeling methodology including simulation, parameter recovery, and model comparison, but the "social" element is limited to stimulus framing rather than genuine social learning. The finding that social-motive framing enhances learning rates but does not interact with age/development is the central contribution.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_adolescents
- pop_healthy_adults
- rr_pop_adolescents
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_target = social
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
