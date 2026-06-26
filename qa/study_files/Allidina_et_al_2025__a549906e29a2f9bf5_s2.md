# Allidina et al. (2025)

- **study_id:** `a549906e29a2f9bf5_s2`
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
- **study_focus:** Social categorization learning — replication of Study 1 with real monetary incentives; how people form group-based versus individuated representations of novel social group members.
- **study_focus_short:** Social categorization learning
- **learning_mode_description:** - Learning mode: Learning from interaction outcomes about social group members' cooperativeness to form group-based vs. person-based category representations   - Learning from:     - Source type (social): other (alien group members)     - Source content (non-social): outcome (cooperation/defection; +1/-1 points with real monetary bonus)   - Learning about:     - Target type (social): other (individual alien group members) / group (alien social groups)     - Target content (social): state (mental state; cooperativeness/character trait) + stimulus (category membership)
- **task_description:** Identical to Study 1, except monetary outcomes were real (up to $10 bonus). Participants encountered alien people from two groups and chose to cooperate or avoid; feedback was approach-contingent.
- **task_paradigm:** Approach-avoidance
- **players:** Single agent (participant), multi-target (8 aliens across 2 groups in Phase 1; 8 aliens across 2 groups in Phase 2)
- **n_players:** multi-target (3+)
- **partner_type:** computer (algorithmic)
- **stimuli:** Alien faces with distinctive features, varying in skin color (green/blue = group membership) and individual identity; binary feedback (+1/-1 points translating to real money)
- **method:** online / behavioural
- **method_full:** behavioural / online
- **main_result:** - Main Results:   - Replication of Study 1: main effects of alien group (χ² = 79.91, p < .001) and alien type (χ² = 74.78, p < .001)   - Interaction of group × type (χ² = 214.84, p < .001)   - Group differentiation significant for extreme and early neutral aliens but not late neutral aliens   - SUSTAIN cluster distributions replicated Study 1 pattern (peaks at 2 and 12 clusters)
- **effect_size:** No standardized effect sizes reported (chi-square tests only).
- **learning_from:** Other (alien group members); cooperation/defection outcome feedback (real monetary consequences)
- **learning_about:** Other (individual aliens) and group (alien social groups); cooperativeness traits and category membership  ---  #### ALGORITHMIC LEVEL
- **outcome_modality:** monetary

## Algorithmic level
- **winning_model:** SUSTAIN (6 params: r, β, d, τ, η, initial attention weight)
- **model_family:** Connectionist (SUSTAIN/ALCOVE)
- **model_class:** Category learning
- **all_models_tested:** [{"name": "SUSTAIN", "family": "Network category learning model", "n_params": 6, "metric": "log likelihood (MLE)"}]
- **model_mb_mf:** N/A (not RL; category learning model)
- **model_params:** - r: attentional weighting parameter - β: cluster competition parameter - d: decisional consistency parameter - τ: threshold for creating a new cluster - η: learning rate for cluster, attention weight, and connection weight updating - initial attention: initial attention to group vs. identity dimensions - All 6 parameters fit individually per participant - Mean fitted values in Supplemental Table 2 (not accessible)
- **social_param:** Initial attention weight — controls relative attention to group membership vs. individual identity.
- **social_param_name:** Initial attention weight
- **social_param_value:** 
- **social_param_sd:** 
- **social_param_range:** 
- **model_comparison_metric:** Log likelihood (MLE); no model comparison.
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
- **sample_size:** N = 119 (after exclusions from 146 recruited; Amazon Mechanical Turk; 7 excluded for prior participation in Study 1; same latency/response exclusion criteria as Study 1)
- **population_category:** healthy adults
- **population_age_range:** 
- **ecological_validity:** Low — same artificial alien paradigm as Study 1; real monetary incentives increase engagement but the social context remains artificial.
- **eligibility_flag:** 
- **concerns:** Same as Study 1 — only one model tested; no model comparison; parameter values not accessible in supplement. Study 2 is nearly identical to Study 1 (only difference: real vs. hypothetical money).
- **limitations_reported:** Same as Study 1 (authors discuss all studies together in the Discussion/Constraints on Generality section).
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
