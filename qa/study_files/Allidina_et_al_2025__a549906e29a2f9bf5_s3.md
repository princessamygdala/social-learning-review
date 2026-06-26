# Allidina et al. (2025)

- **study_id:** `a549906e29a2f9bf5_s3`
- **on_website:** YES

> Check each field below against the paper. Log errors in `field_verification.csv`.

## Identification
- **citation:** Allidina, S., Mack, M. L., & Cunningham, W. A. (2025). Experience shapes the granularity of social perception: Computational insights into individual and group-based representations. *Journal of Experimental Psychology: General*, *154*(8), 2257–2271. https://doi.org/10.1037/xge0001770
- **citation_short:** Allidina et al. (2025)
- **doi:** 10.1037/xge0001770
- **publication_type:** peer-reviewed journal
- **year:** 2025.0
- **field_of_study:** Psychology
- **affiliations_raw:** labilityofinformationaboutothersshapedthesementalrepresentations:Wheninformationcould; ethatthisdifferencewasmostpronouncedinthosewhoheldmoreracistattitudes,measuredinan; lable on the Open methodology, visualization, and writing–original draft; ethat preventing them from being updated (Allidina & Cunningham,; labletodrawuponforagiventarget,andsimplymustchoose Fazioetal; DepartmentofPsychology,TheOhioStateUniversity,Lazenby; ethatavoidanceunderconditionsofapproach-contingent; ethetarget,failingwhichtheywillrelyonstereotypes; emails: allidina.1@osu.edu
- **code_url:** https://osf.io/uj9e7/

## Computational level
- **study_focus:** Social categorization learning — how feedback structure (approach-contingent vs. full feedback) and individual differences in prejudice interact to shape the formation of group-based vs. individuated social representations.
- **study_focus_short:** Social categorization learning
- **learning_mode_description:** - Learning mode: Learning from interaction outcomes (under partial vs. full feedback) about social group members' cooperativeness, with prejudice attitudes moderating representation granularity   - Learning from:     - Source type (social): other (alien group members)     - Source content (non-social): outcome (cooperation/defection; +1/-1 points with real monetary bonus)   - Learning about:     - Target type (social): other (individual alien group members) / group (alien social groups)     - Target content (social): state (mental state; cooperativeness/character trait) + stimulus (category membership)
- **task_description:** Participants learned about two groups of alien people (6 per group) who could help or harm them, with cooperation rates varying within and between groups. Participants were randomly assigned to partial feedback (approach-contingent: information only if they chose to interact) or full feedback (outcome revealed regardless of choice). After the task, they rated aliens' cooperativeness and completed prejudice/personality questionnaires.
- **task_paradigm:** Approach-avoidance
- **players:** Single agent (participant), multi-target (12 aliens across 2 groups; 6 per group with varying cooperation rates)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Alien faces with distinctive features, varying in skin color (green/blue = group membership) and individual identity; binary feedback (+1/-1 points translating to real money); questionnaires (Symbolic Racism Scale, Internal/External Motivation to Respond Without Prejudice, Social Justice Scale, Need for Closure)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Participants differentiated good and bad groups (main effect of group: χ² = 463.88, p < .001) and showed sensitivity to within-group variation (group × alien type: χ² = 381.38, p < .001)   - Four-way interaction of group × alien type × trial number × feedback condition (χ² = 5.13, p = .024): full feedback participants better learned within-group variation by end of task   - Three-way interaction of group × alien type × feedback condition on person-based clusters (b = 0.028, SE = 0.012, t = 2.27, p = .024): partial feedback participants formed fewer person-based clusters for the bad group   - Partial feedback: good–bad contrast for extreme aliens: b = 0.63, SE = 0.088, t = 7.22, p < .001; for neutral aliens: b = 0.39, SE = 0.088, t = 4.47, p < .001   - Full feedback: no significant good–bad differences in person-based clusters   - Symbolic racism × feedback condition interaction on person-based clusters (b = 0.14, SE = 0.064, t = 2.15, p = .032): higher racism predicted fewer person-based clusters in partial feedback only   - Internal motivation × condition interaction (b = −0.077, SE = 0.035, t = −2.20, p = .029): lower internal motivation predicted fewer person-based clusters in partial feedback   - Social justice orientation × group × alien type × condition four-way interaction (b = −0.033, SE = 0.014, t = −2.27, p = .024)   - Need for closure: suggestive main effect (b = −0.15, SE = 0.08, t = −1.89, p = .06), no interaction with condition   - Cluster-rating relationship: three-way interaction of group × alien type × person clusters on cooperativeness ratings (χ² = 10.08, p = .006)
- **effect_size:** Unstandardized regression coefficients reported (b values as listed above). No standardized effect sizes (Cohen's d, r², η²) reported.
- **learning_from:** Other (alien group members); cooperation/defection outcome feedback (real monetary consequences); approach-contingent vs. full feedback manipulation
- **learning_about:** Other (individual aliens) and group (alien social groups); cooperativeness traits and category membership  ---  #### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** SUSTAIN (3 individually fit params: η, d, initial attention; 3 group-level fixed params: β, τ, r)
- **model_family:** Connectionist (SUSTAIN/ALCOVE)
- **model_class:** Category learning
- **all_models_tested:** [{"name": "SUSTAIN", "family": "Network category learning model", "n_params": 6, "metric": "log likelihood (MLE)"}] - Note: Only one model tested. In Study 3, β, τ, and r were fixed to group-level estimates from an initial fit to aid parameter recovery; η, d, and initial attention were fit per participant.
- **model_mb_mf:** N/A (not RL; category learning model)
- **model_params:** - r: attentional weighting parameter [fixed to group value] - β: cluster competition parameter [fixed to group value] - d: decisional consistency parameter [individually fit] - τ: threshold for creating a new cluster [fixed to group value] - η: learning rate for cluster, attention weight, and connection weight updating [individually fit] - initial attention [S]: initial attention to group vs. identity dimensions [individually fit] - Mean fitted values in Supplemental Table 2 (not accessible) - Average clusters formed: 7.92 total (0.96 group-based, 6.85 person-based, 0.12 neither)
- **social_param:** Initial attention weight [S] — controls relative attention to group membership (skin color) vs. individual identity dimensions; this is the key social parameter as it governs whether the model represents targets by group or by individual features.
- **social_param_name:** initial attention
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Log likelihood (MLE); no model comparison across different model architectures.
- **how_model_fit:** individual-level-fit (3 params per person; 3 params fixed at group level from initial fit)
- **data_type_fit_to:** choice behavior (trial-by-trial approach/avoid decisions)  ---  #### IMPLEMENTATION LEVEL

## Implementation level
- **fmri_model_type:** none
- **contrast:** 
- **key_regions:** 
- **coordinates_peak:** N/A (no neuroimaging)
- **analysis_type:** N/A  ---  #### QUALITY
- **analysis_type_clean:** N/A
- **has_coordinates:** False
- **has_neural:** False

## Quality
- **sample_size:** N = 382 (after exclusions from 399 recruited via Prolific; 5 excluded for fast latency, 9 for slow latency, 3 for same response on >85% trials)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low — artificial alien groups, online task, no real social interaction; approach-contingent feedback structure mimics real-world selective information access; prejudice measures taken in separate context relate to artificial task behavior.
- **eligibility_flag:** 
- **concerns:** Only one model tested (no model comparison); individual differences effects for prejudice are described as "tentative" and "preliminary" by authors (e.g., symbolic racism interaction p = .032 with sensitivity to exclusion criteria — p = .059 with alternative exclusion); supplement not accessible so fitted parameter values cannot be verified; no formal parameter recovery or model recovery checks; no simulation studies prior to fitting.
- **limitations_reported:** These studies were not preregistered"; conducted on US-based online participants (Prolific/MTurk); generalizability to non-WEIRD populations not assessed; artificial social groups — "the increased complexity of motivations surrounding real social groups could result in altered category representations"; only examined helping/harming behaviors; design choices about relative salience of features and within/between-group variation likely influenced mean individuation; prejudice effects "should be considered preliminary and replicated in future work"; unclear whether effects reflect general category-based processing or race-specific processing.
- **limitations_categorized:** limited ecological validity; no preregistration; limited generalizability; task simplicity; WEIRD sample; preliminary individual differences effects; no parameter recovery; single model (no model comparison)
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** Partial
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 5.0
- **wc_total:** 5.0

## Context flags
- **ctx_copresence:** no
- **ctx_observability:** yes
- **ctx_audience:** no
- **ctx_joint_setting:** yes

## QC / extraction notes
- **flagged_fields:** - model_params: MEDIUM confidence — exact fitted parameter values reported only in Supplemental Table 2 which is not accessible - effect_size: LOW confidence — no standardized effect sizes reported; only unstandardized regression coefficients and chi-square tests - social_param: MEDIUM confidence — initial attention weight identified as social parameter based on inference from model description; not explicitly labeled "social parameter" by authors - wc_guidelines Rule 5 (Study 3): MEDIUM — authors mention fixing parameters for "parameter recoverability" but no formal recovery analysis described
- **cannot_find:** - Mean fitted parameter values (in Supplemental Table 2, not accessible) - Standardized effect sizes (not reported) - Exact model formulas (authors refer to Love et al., 2004 for full mathematical details) - Supplemental Table 1 (approach rates by group/type)
- **other_notes:** - Supplement not accessible (referenced at https://doi.org/10.1037/xge0001770.supp but no file in papers folder). Supplement reportedly contains: parameter values (Table 2), approach rates (Table 1), and cooperation rating analyses. - The SUSTAIN model is from cognitive psychology (Love et al., 2004) and is novel to the social domain in this application. It is not a standard RL model — it is a cluster-based network model of category learning. - Studies 1 and 2 are nearly identical (hypothetical vs. real money); results are presented together in the paper. - The paper explicitly states data and code are available at https://osf.io/uj9e7/. - This paper is a strong candidate for the review as it applies computational modeling to understand social categorization and individuation processes — a novel intersection of category learning and social cognition.
- **re_extract_flag:** false (full text accessible; supplement not accessible but flagged)

## Taxonomy / categorization (active codes only)
- pop_healthy_adults
- rr_pop_healthy_adults
- rr_tax_mod_experiential
- spec_context = partly
- spec_depth = parametric
- spec_locus = source+target
- spec_source = partly
- spec_target = social
- tax_domain_D_group_structure_identity
- tax_mod_experiential
- tax_mod_social_info_search
- tax_param_social_weight
- tax_popclass_healthy
- tax_rr_domain = D_group_structure_identity
- tax_rr_domain_D_group_structure_identity
- tax_rr_model_connectionist_category
- tax_rr_model_family = connectionist_category
- tax_rr_param_learning_rate
- tax_rr_primary_topic = stereotype_updating
- tax_rr_secondary_topic = intergroup_bias
- tax_rr_topic_intergroup_bias
- tax_rr_topic_stereotype_updating
- tax_topic_intergroup_bias
- tax_topic_stereotype_updating
