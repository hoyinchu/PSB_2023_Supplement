# PSB_2023_Supplement

Supplementary Material for the PSB 2023 Submission "Using Association Rules to Understand the Risk of Adverse Pregnancy
Outcomes in a Diverse Population"

## supplementary_compressed_tables
---
This directory include the tables containing detailed breakdown of each described high-risk subgroups in the main text. All numbers presented in these tables are a subset of the numbers from combined_disparity_df.csv. They are included here for ease of understanding when reading the main text.

- subgroup_risk_table.tsv: The confidence, LR+, fisher p value and gini coefficient (disparity measure) associated with each high risk subgroup
- subgroup_omitted_table.tsv: Includes metrics relating to change in APO prevalence / disparity if these high-risk subgruoups are omitted from the cohort
- prevalence_by_race_table.tsv: Breakdown of the prevalence of APO in each race/ethnic group in each high-risk subgroups
- omission_by_race_table.tsv: Breakdown of the prevalence of APO in each race/ethnic group if these high-risk subgroups are omitted


## combined_disparity_df.csv
---

Column name explanations:

rule: A short text representation of the association rule with some baseline metrics including confidence (conf) and support (supp)

lhs: The antecedent (left-hand side) of the rule. This defines the subgroup.

rhs: The consequent (right-hand side) of the rule

lhs_size: Number of attributes in the antecedent

rhs_size: Number of attributes in the consequent

lhs_count: The number of participants with attributes specified in the antecedent

rhs_count: The number of participants with attributes specified in the consequent

full_count: The number of participants with attributes specified both the consequent and antecedent

num_transactions: Total number of participants

confidence: The confidence measure of the rule. Equals full_count/lhs_count

support: The support measure of the rule. Equals full_count/num_transactions

lift: The lift measure of the rule. Equals confidence/(rhs_count/num_transactions)

OR: The odds ratio of the rule. See paper for precise definition.

OR_95CI_lower: The lower number of the 95-percent confidence interval of the OR

OR_95CI_upper: The higher number of the 95-percent confidence interval of the OR

RR: Risk Ratio of the rule

RR_95CI_lower: The lower number of the 95-percent confidence interval of the RR

RR_95CI_upper: The higher number of the 95-percent confidence interval of the RR

LR+: The positive likeluhood-ratio of the rule

LR+_95CI_lower: The lower number of the 95-percent confidence interval of the LR+

LR+_95CI_upper: The higher number of the 95-percent confidence interval of the LR+

fisher_pval: The unadjusted p-value of the rule if a fisher exact test is applied. See paper for precise definition.

{attribute}_lhs_filter: Indicates which attribute is present in the lhs

{attribute}_rhs_filter: Indicates which attribute is present in the rhs

cur_Race_{group}: The proportion of individuals in this race that satisfy this rule

cur_overall_prob: The proportion of indivudals regardless of race that satisfy this rule. Same as confidence.

cur_overall_Prob_std: The standard deviation of the prevalence of the APO across race.

cur_overall_gini_coefficient: The gini coefficient of the prevalence of the APO across race. This is dispairty measure used in the paper.

cur_overall_coef_var: The gini coefficient of variation of the prevalence of the APO across race. 

pre_Race_{group}: The prevalence of the APO in this race group prior to omitting this subgroup.

pre_Race_{group}: The prevalence of the APO in this race group prior to omitting this subgroup.

cur_overall_{metric}: The metric (e.g. prevalence (prob), gini coefficient) for the current subgroup (as denoted by lhs)

pre_overall_{metric}: The metric (e.g. prevalence (prob), gini coefficient) of the cohort before this subgroup is omitted

post_overall_{metric}: The metric (e.g. prevalence (prob), gini coefficient) of the cohort after this subgroup is omitted

change_omitted_overall_{relative/absolute}_{metric}: The absolute/relative change in the metric (e.g. prevalence (prob), gini coefficient) if the subgroup is omitted from the cohort

change_isolate_overall_{relative/absolute}_{metric}: The absolute/relative change in the metric (e.g. prevalence (prob), gini coefficient) if we are only looking at the current subgroup

