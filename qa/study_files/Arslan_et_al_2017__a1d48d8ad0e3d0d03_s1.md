# Arslan et al. (2017)

- **study_id:** `a1d48d8ad0e3d0d03_s1`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Arslan, B., Taatgen, N. A., & Verbrugge, R. (2017). Five-year-olds' systematic errors in second-order false belief tasks are due to first-order theory of mind strategy selection: A computational modeling study. *Frontiers in Psychology*, *8*, 275. https://doi.org/10.3389/fpsyg.2017.00275
- **citation_short:** Arslan et al. (2017)
- **doi:** 10.3389/fpsyg.2017.00275
- **publication_type:** peer-reviewed journal
- **year:** 2017.0
- **field_of_study:** Psychology
- **affiliations_raw:** etheyareabletopassfirst-orderToMtasks?The children around the age of 5 are able to pass first-order false; section: orderfalsebeliefreasoning,childrencanrevisetheirwrongfirst-orderreasoningstrategy; etheperspectiveofanotheragent(first-orderToM)butalsousethisToMrecursivelybytaking; InstituteofArtificialIntelligence,UniversityofGroningen,Groningen,Netherlands; UniversityofHuddersfield,UK we conducted with 72 5- to 6-year-old children; UniversityofWaterloo,Canada provide any answer); UniversityofAmsterdam,Netherlands; etheirstrategytoahigherlevel; emails: b.arslan@rug.nl
- **code_url:** https://figshare.com/s/7c3146ad85b3e7a57cd4

## Computational level
- **study_focus:** Mentalizing learning; reasoning about others' beliefs; theory of mind strategy selection and revision in second-order false belief tasks
- **study_focus_short:** Mentalizing learning
- **learning_mode_description:** - Learning mode: Learning to select the correct level of theory of mind reasoning strategy (zero-order, first-order, second-order) for false belief tasks through experience and feedback   - Learning from:     - Source type (non-social): self       - Not joint     - Source content (non-social): outcome (feedback "Correct/Wrong" on strategy application)       - Not joint   - Learning about:     - Target type (social): other (story character's beliefs about another character's beliefs)       - Not joint     - Target content (social): state (mental state; second-order false beliefs)       - Not joint
- **task_description:** Children (5-6 years old) heard modified second-order false belief stories with three possible answer locations (enabling distinction among zero-order, first-order, and second-order ToM strategies) and answered second-order false belief questions (e.g., "Where does Ayla think that Murat will look for the chocolate?"). No feedback was given in the empirical study; computational models simulated learning from repeated Correct/Wrong feedback.
- **task_paradigm:** Probabilistic ToM task
- **players:** Single agent (child participant), reasoning about two story characters (dyadic story characters)
- **n_players:** dyadic (2)
- **partner_type:** human (live)
- **stimuli:** Illustrated second-order false belief stories (audio + drawings on laptop screen), three story types: "Three locations" (3 stories) and "Three goals" (14 stories)
- **method:** behavioural
- **method_full:** behavioural
- **main_result:** - 17% of second-order false belief answers were correct; 83% were wrong - Of wrong answers, 65% were first-order ToM answers and 29% were zero-order ToM answers (remaining 6% "I don't know") - Chi-square goodness-of-fit confirmed unequal distribution of wrong answer types: X²(2, N=119) = 64.76, p < .001 - Instance-based learning model correctly predicted predominance of first-order errors; reinforcement learning model did not - Control question accuracy: 95-96%; first-order false belief accuracy: 81% (Three locations), 93% (Three goals); second-order: 17% for both
- **effect_size:** - X²(2, N=119) = 64.76 (goodness-of-fit test for distribution of wrong answer types) - X²(1, N=144) = 3.88 (difference between story types for first-order false belief accuracy) - No Cohen's d, r, or other standardized effect sizes reported
- **learning_from:** Self; feedback ("Correct/Wrong") on one's own answer to a false belief question
- **learning_about:** Other (story characters); second-order mental state attribution (what character A thinks character B believes)  ---  ### ALGORITHMIC LEVEL
- **outcome_modality:** unclear

## Algorithmic level
- **winning_model:** Instance-based learning model (ACT-R cognitive architecture); strategy chunks in declarative memory; activation-based retrieval; explicit strategy increment on negative feedback. Base-level activation: B_i = ln(n/(1-d)) - d*ln(L); parameters: n (presentations), L (lifetime of chunk), d (decay; default 0.5). Retrieval threshold = -5; instantaneous noise = 0.1 (default values except retrieval threshold and noise).
- **model_family:** Cognitive architecture (ACT-R/IBL)
- **model_class:** Other
- **all_models_tested:** [   {"name": "Instance-based learning model (ACT-R)", "family": "Instance-based learning", "n_params": 2, "metric": "qualitative prediction match to empirical data"},   {"name": "Reinforcement learning model (ACT-R)", "family": "Reinforcement learning (utility updating)", "n_params": 1, "metric": "qualitative prediction match to empirical data"} ]
- **model_mb_mf:** N/A (cognitive architecture, not standard RL)
- **model_params:** - Retrieval threshold: -5 (set arbitrarily low so all story facts can be retrieved) - Instantaneous noise (s): 0.1 (for instance-based learning model; 0.5 in sensitivity analysis) - Decay parameter (d): ACT-R default (0.5) - Initial zero-order chunk activation: 6 - For RL model: utility noise = 3; initial utilities = 100 (zero-order), 25 (first-order), 5 (second-order); learning rate α (ACT-R default); reward R = 20 for correct, 0 for wrong
- **social_param:** No explicitly social free parameter. The social component is embedded in the strategy level (zero-order vs first-order vs second-order ToM reasoning), which determines the depth of mental state attribution. This is structural rather than parametric.
- **social_param_name:** 
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Qualitative comparison of model predictions to empirical data (proportion of zero-order vs first-order wrong answers). No formal quantitative model comparison metric (BIC/AIC/etc.) was used.
- **how_model_fit:** simulate-and-compare (100 virtual children x 100 repetitions = 10,000 simulations per model; predictions compared qualitatively to empirical proportions)
- **data_type_fit_to:** choice behavior (children's answer types: zero-order / first-order / second-order)  ---  ### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** N/A (no neuroimaging)
- **key_regions:** N/A (no neuroimaging)
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  ### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N=72 (36 female; M_age = 5.7 years, SE = 0.05, range: 5.0-6.8 years); from original sample of 79 children, 7 excluded for giving correct answers on both second-order questions. Predominantly upper-middle-class Dutch families from a single primary school ("Excellence school") in Groningen, Netherlands.
- **population_category:** children
- **population_age_range:** 
- **ecological_validity:** Low-moderate. Lab-based task using illustrated stories presented on a laptop; stories are simplified representations of social reasoning scenarios. No real-time social interaction; children reason about fictional characters. However, authors discuss parallels to everyday life scenarios (hide-and-seek, deception situations) where children might receive implicit ToM feedback.
- **eligibility_flag:** Borderline: empirical validation is cross-sectional (no learning observed in participants); learning occurs only in computational simulations. Also: participants are children (5-6 years), not a clinical or adult sample typically seen in computational psychiatry.
- **concerns:** - No formal quantitative model comparison (no BIC, AIC, likelihood, or similar metric); models are compared by qualitative pattern matching of predictions to data - No model fitting to individual participant data; simulation parameters are mostly ACT-R defaults - The empirical study is cross-sectional (pre-test only); the training study that would test learning predictions (predictions 2 and 3) was described as ongoing but not reported - Single school sample (Excellence school, upper-middle-class) limits generalizability - No standardized effect sizes reported beyond chi-square - ACT-R models contain hard-coded reasoning rules (production rules) that assume children can perfectly execute second-order reasoning once the correct strategy is selected, which is acknowledged as a simplification
- **limitations_reported:** The school's success comes from their adaptive education...these educational and socioeconomic differences might be a possible explanation for the different results" (re: contrast with de Villiers et al. findings); "selecting the correct strategy is not the whole story in children's development of second-order false belief reasoning. When children select the correct second-order ToM strategy, they might still make mistakes for different reasons, such as lack of efficiency in applying reasoning rules and internal or external distraction"; "we believe that our experimental results, which show that 29% of the wrong answers were still based on a zero-order strategy, as opposed to the 0% predicted by our instance-based learning model...is related to a working memory bottleneck or to distraction"; "further research is needed in which children's everyday life experiences are investigated" (to validate assumptions about experience with different ToM strategy levels)
- **limitations_categorized:** limited generalizability (single school, high SES); model simplification (perfect execution assumed once strategy selected); incomplete model validation (only cross-sectional data; training study results not yet reported); sample homogeneity; ecological validity (lab-based false belief stories)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** Yes
- **wc_rule3:** Yes
- **wc_rule4:** No
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Partial
- **wc_rule10:** Yes
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** yes
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** no

## QC / extraction notes
- **flagged_fields:** - effect_size: MEDIUM confidence — only chi-square statistics reported; no standardized effect sizes (d, r, etc.) - model_comparison_metric: LOW confidence — no formal quantitative metric used; comparison is qualitative - eligibility_flag: MEDIUM confidence — borderline inclusion; learning occurs in models but empirical data is cross-sectional - model_params: MEDIUM confidence — some parameter values stated (retrieval threshold, noise, initial activations), but learning rate α for RL model uses unspecified ACT-R default - social_param: MEDIUM confidence — no explicit social parameter exists; social component is structural
- **cannot_find:** - Formal model comparison metric (BIC, AIC, etc.) — not used in this paper - Standardized effect sizes (Cohen's d, r, etc.) — not reported - Learning rate α exact value for RL model — described as ACT-R default but numerical value not stated - Individual-level model fits — not performed - Parameter recovery / model recovery analyses — not performed
- **other_notes:** The paper explicitly discusses Marr's levels, noting that their models operate at the algorithmic level while Goodman et al. (2006) operated at the computational level only. The authors mention an ongoing training study (Arslan et al., 2015a) that would test the learning predictions but do not report its full results. The ACT-R model code is shared on Figshare. The supplement contains only sensitivity analyses (different utility values, different noise values) showing the qualitative predictions are robust to parameter changes.
- **re_extract_flag:** false

## Taxonomy / categorization (active codes only)
- pop_children
- rr_pop_children
- rr_tax_mod_experiential
- rr_tax_mod_instructed
- spec_context = social
- spec_depth = parametric
- spec_locus = target
- spec_target = social
- tax_domain_B_inference_modelling_others
- tax_mod_experiential
- tax_mod_instructed
- tax_param_decay
- tax_popclass_developmental
- tax_rr_domain = B_inference_modelling_others
- tax_rr_domain_B_inference_modelling_others
- tax_rr_model_cognitive_architecture
- tax_rr_model_family = cognitive_architecture
- tax_rr_param_PE_signal
- tax_rr_param_learning_rate
- tax_rr_primary_topic = mentalizing
- tax_rr_topic_mentalizing
- tax_topic_mentalizing
