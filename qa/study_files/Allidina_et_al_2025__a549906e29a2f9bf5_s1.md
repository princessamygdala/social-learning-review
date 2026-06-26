# Allidina et al. (2025)

- **study_id:** `a549906e29a2f9bf5_s1`
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
- **study_focus:** Social categorization learning — how people form group-based versus individuated (person-based) representations of novel social group members through experience with approach-contingent feedback.
- **study_focus_short:** Social categorization learning
- **learning_mode_description:** - Learning mode: Learning from interaction outcomes about social group members' cooperativeness to form group-based vs. person-based category representations   - Learning from:     - Source type (social): other (alien group members)     - Source content (non-social): outcome (cooperation/defection; +1/-1 points)   - Learning about:     - Target type (social): other (individual alien group members) / group (alien social groups)     - Target content (social): state (mental state; cooperativeness/character trait) + stimulus (category membership)
- **task_description:** Participants encountered alien people belonging to two visually distinct groups (green vs. blue skin) one at a time and chose whether to cooperate with each alien. If they chose to cooperate, the alien either gave or took 1 point; if they chose not to cooperate, no information was provided (approach-contingent feedback). Cooperation rates varied both within and between groups. Phase 1 included extreme aliens; Phase 2 replaced extreme aliens with neutral ones.
- **task_paradigm:** Approach-avoidance
- **players:** Single agent (participant), multi-target (8 aliens across 2 groups in Phase 1; 8 aliens across 2 groups in Phase 2)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Alien faces with distinctive features (face shape, eyes, mouth, nose), varying in skin color (green/blue = group membership) and individual identity; binary feedback (+1/-1 points)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Participants learned to differentiate good and bad groups (main effect of group: Study 1 χ² = 49.23, p < .001)   - Interaction of alien group and alien type (Study 1: χ² = 80.75, p < .001): group differentiation was larger for extreme aliens than neutral aliens   - SUSTAIN cluster distribution showed peaks at 2 clusters (group-based) and 12 clusters (fully individuated)   - Participants with 2 clusters could not distinguish neutral members across groups; those with >2 clusters correctly differentiated extreme but not neutral members
- **effect_size:** No standardized effect sizes reported for Study 1 (chi-square tests from multilevel logistic regression only); no Cohen's d, r, or β values reported.
- **learning_from:** Other (alien group members); cooperation/defection outcome feedback
- **learning_about:** Other (individual aliens) and group (alien social groups); cooperativeness traits and category membership  ---  #### ALGORITHMIC LEVEL
- **outcome_modality:** points

## Algorithmic level
- **winning_model:** SUSTAIN (6 params: r, β, d, τ, η, initial attention weight)
- **model_family:** Connectionist (SUSTAIN/ALCOVE)
- **model_class:** Category learning
- **all_models_tested:** [{"name": "SUSTAIN", "family": "Network category learning model", "n_params": 6, "metric": "log likelihood (MLE)"}] - Note: Only one model tested (SUSTAIN). No model comparison performed.
- **model_mb_mf:** N/A (not RL; category learning model)
- **model_params:** - r: attentional weighting parameter - β: cluster competition parameter - d: decisional consistency parameter - τ: threshold for creating a new cluster - η: learning rate for cluster, attention weight, and connection weight updating - initial attention: initial attention to group vs. identity dimensions - All 6 parameters fit individually per participant - Note: Mean fitted values reported in Supplemental Table 2 (not accessible). [S] social parameter: initial attention weight (governs relative attention to group vs. identity dimensions)
- **social_param:** Initial attention weight — controls whether the model attends more to group membership (skin color) vs. individual identity dimensions when forming category representations.
- **social_param_name:** Initial attention weight
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Log likelihood (MLE); no model comparison across different models was performed.
- **how_model_fit:** individual-level-fit
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
- **sample_size:** N = 77 (after exclusions from 97 recruited; Amazon Mechanical Turk; exclusion criteria: latency <150ms on >15% trials, latency >5000ms on >15% trials, same response on >85% trials)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low — entirely artificial alien groups with no real-world social implications; online task; approach-contingent feedback structure mimics real-world selective information sampling but lacks ecological complexity.
- **eligibility_flag:** 
- **concerns:** Only one computational model tested (no model comparison); hypothetical monetary outcomes in Study 1 (no real incentive); parameter values only in supplement (not accessible); no formal model validation or parameter recovery reported for Studies 1–2.
- **limitations_reported:** Authors report: "These studies were not preregistered"; conducted on US-based online participants; artificial social groups limit generalizability to real-world categories; design choices (salience of individuating vs. group features, within/between-group variation) may have influenced mean individuation levels; only examined helping/harming behaviors, not other social dimensions; generalizability to non-WEIRD populations not assessed.
- **limitations_categorized:** limited ecological validity; no preregistration; limited generalizability; task simplicity; WEIRD sample
- **preregistered:** No
- **wc_rule1:** Yes
- **wc_rule2:** No
- **wc_rule3:** No
- **wc_rule4:** Yes
- **wc_rule5:** No
- **wc_rule6:** No
- **wc_rule7:** No
- **wc_rule8:** Partial
- **wc_rule9:** Yes
- **wc_rule10:** Yes
- **wc_score:** 4.5
- **wc_total:** 4.5

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
