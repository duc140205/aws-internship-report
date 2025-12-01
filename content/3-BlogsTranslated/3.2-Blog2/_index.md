
---
title: "Blog 2"
date: "2025-09-09"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# AWS Savings Plans: How to Implement an Effective Chargeback Strategy

by Alonso de Cosio and Ketan Kumar | on 28 FEB 2025 | in [Amazon Athena](https://aws.amazon.com/blogs/aws-cloud-financial-management/category/analytics/amazon-athena/), [AWS Cloud Financial Management](https://aws.amazon.com/blogs/aws-cloud-financial-management/category/aws-cloud-financial-management/), [AWS Cost and Usage Report](https://aws.amazon.com/blogs/aws-cloud-financial-management/category/aws-cloud-financial-management/aws-cost-and-usage-report/), [Best Practices](https://aws.amazon.com/blogs/aws-cloud-financial-management/category/post-types/best-practices/), [Technical How-to](https://aws.amazon.com/blogs/aws-cloud-financial-management/category/post-types/technical-how-to/) | [Permalink](https://aws.amazon.com/blogs/aws-cloud-financial-management/aws-savings-plans-how-to-implement-an-effective-chargeback-strategy/) | [Share](https://aws.amazon.com/blogs/aws-cloud-financial-management/aws-savings-plans-how-to-implement-an-effective-chargeback-strategy/)

As organizations grow, managing cloud infrastructure can become increasingly complex, requiring advanced financial strategies to ensure cost optimization. [AWS Savings Plans](https://aws.amazon.com/savingsplans/) provide a flexible pricing model that offers significant savings on AWS services in return for a commitment to a consistent amount of usage, measured in USD per hour, over a one or three year term. In many cases, multiple Savings Plans are adopted, either by individual teams committing directly or by FinOps teams prioritizing specific accounts. While these strategies can lead to substantial savings, they also add complexity when ensuring a fair and effective chargeback process.

In this article, we will show you how to define a chargeback mechanism that allocates Savings Plans purchased in the management account, linked accounts or both to recipient accounts of Savings Plan discounts. You can identify accounts that received Savings Plans discounts and the appropriate amount to chargeback to them based on their specific usage.

## Understanding Savings Plans Discount Sharing
AWS allows customers to [share Savings Plan discounts across accounts](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/ri-turn-off.html) within the same [AWS Organization](https://aws.amazon.com/organizations/). TSavings plan hourly commitment fees are charged to the account that made the purchase, however, when sharing is enabled, the discounts may apply to multiple accounts within the organization. Savings Plan discounts are first applied to all eligible usage in the account the Savings Plan is purchased. If there is excess commitment for which there is no eligible on-demand usage, then the unused commitment is utilized by other linked accounts within the AWS Organizaiton.

While [sharing maximizes savings](https://docs.aws.amazon.com/savingsplans/latest/userguide/sp-applying.html#calc-bills-sp), it may require additional efforts to properly allocate the shared benefit across the organization. Accounts that benefit from Savings Plan discounts are not responsible to pay a Savings Plan commitment fee. As a result, the account incurring the cost of the commitment may not be the sole beneficiary of the savings. This shared benefit requires careful cost allocation to ensure that accounts are charged fairly based on their actual usage of the Savings Plan.

Now that we understand how Savings Plans operate and how sharing affects them, let’s explore a chargeback strategy for using data from the [Cost and Usage Report (CUR) 2.0](https://docs.aws.amazon.com/cur/latest/userguide/table-dictionary-cur2.html).

## Prerequisites
Create an [AWS Data Export](https://aws.amazon.com/aws-cost-management/aws-data-exports/) with CUR 2.0 and configure [AWS Glue](https://aws.amazon.com/glue/) to catalogue the data. This allows you to use [Amazon Athena](https://aws.amazon.com/athena/) to run queries and analyze CUR 2.0 data. In order to accomplish this, you need to do the following:

**1. Configure CUR 2.0 with AWS Data Export:**
1. Sign in to the [AWS Management console](https://aws.amazon.com/console/)
2. Navigate to AWS Billing and Cost Management. Select Data Export and click Create to begin setting up your export.
  
 ![Figure 1 - Create Data Exports](/images/3-BlogsTranslated/3.2-Blog2/1.png)
 <p style="text-align:center; font-size:0.9em; color:gray;"><em>Figure 1 - Create Data Exports</em></p>
3. Select <b>Standard data export</b>, provide your export a name and for select <b>CUR 2.0</b> as the data table type.
  
 ![Figure 2 - Configure export](/images/3-BlogsTranslated/3.2-Blog2/2.png)
 <p style="text-align:center; font-size:0.9em; color:gray;"><em>Figure 2 - Configure export</em></p>

4. Enabling <b>Include resource IDs</b> and <b>Split cost allocation data</b> are optional
5. Select Time granularity as <b>Hourly</b>
6. Set <b>Parquet</b> as the compression format, and select <b>Overwrite existing data export file</b> for file versioning.

![Figure 3 - Configure export delivery options](/images/3-BlogsTranslated/3.2-Blog2/3.png)
<p style="text-align:center; font-size:0.9em; color:gray;"><em>Figure 3 - Configure export delivery options</em></p>

7. Specify the destination Amazon S3 bucket and a path prefix where CUR 2.0 data should be stored.
8. Complete the setup by selecting <b>Create</b>.

**2. Configure AWS Glue to Query CUR Data**
1. Navigate to <b>AWS Glue</b> console and select <b>Data Catalog > Crawlers</b> to initiate the process of cataloging the CUR 2.0 data.
2. Click on <b>Create Crawler</b> and assign a unique crawler name.

![Figure 4 - Create AWS Glue Crawler](/images/3-BlogsTranslated/3.2-Blog2/4.png)
<p style="text-align:center; font-size:0.9em; color:gray;"><em>Figure 4 - Create AWS Glue Crawler</em></p>

3. For the question <b>Is your data already mapped to Glue tables?</b> select Not yet
4. Click Add a data source, select S3, and specify the Amazon S3 location from step 1, where your CUR 2.0 data is exported, using the format: `s3://<bucket-name>/<prefix>/<export-name>/data/`

![Figure 5 - Create S3 data source for CUR crawler](/images/3-BlogsTranslated/3.2-Blog2/5.png)
<p style="text-align:center; font-size:0.9em; color:gray;"><em>Figure 5 - Create S3 data source for CUR crawler</em></p>

5. Click <b>Add an S3 data source</b> and then click <b>Next</b>
6. Click <b>Create new IAM role</b> which will create the new AWS Glue role on your behalf. This role allows Glue to access the S3 bucket where CUR2.0 files are stored.
7. Create a target database by clicking <b>Add database</b>. Provide a database name and click <b>Create database</b>
8. Navigate back to the AWS Glue console and select the database created in the previous step. Set the crawler schedule to <b>On demand</b> to run only when required.
9. Confirm your settings and select <b>Create Crawler</b>.
10. Once the crawler is ready, select it and click <b>Run</b>. This will process and catalog the data, creating tables accessible by Amazon Athena.

## Using CUR 2.0 for Savings Plans Chargeback
Once the above per-requisites are configured, use the following query to identify the linked accounts that received Savings Plan discounts. The **Effective Cost** olumn provides the cost corresponding to the amount of the Savings Plan commitment that was used by linked accounts. This would be the amount that you would use to chargeback individual linked accounts.

1. Navigate to <b>Amazon Athena</b> console to run a query. Review [details](https://docs.aws.amazon.com/cur/latest/userguide/cur-ate-run.html) on running SQL queries in Athena.
2. Copy the query below into your Query editor. Ensure to update the <b>Table Name</b> in the query.

```sql
select
    DATE_FORMAT(bill_billing_period_start_date, '%Y-%m-%d') as "Date",
    line_item_usage_account_id as "Account Id",
    savings_plan_offering_type as "Savings Plan Type",
    split_part(savings_plan_savings_plan_a_r_n, '/', 2) AS "Saving Plan ID",
    savings_plan_payment_option as "Savings Plan Payment Option",
    line_item_line_item_type as "Item Type",
    sum(
        case
            when line_item_line_item_type = 'SavingsPlanCoveredUsage' then 0
            else savings_plan_recurring_commitment_for_billing_period
        end
    ) + sum(
        case
            when line_item_line_item_type = 'SavingsPlanCoveredUsage' then 0
            else savings_plan_amortized_upfront_commitment_for_billing_period
        end
    ) as "Savings Plan Fee",
    sum(
        case
            when line_item_line_item_type = 'SavingsPlanCoveredUsage' then 0
            else savings_plan_recurring_commitment_for_billing_period
        end
    ) + sum(
        case
            when line_item_line_item_type = 'SavingsPlanCoveredUsage' then 0
            else savings_plan_amortized_upfront_commitment_for_billing_period
        end
    ) - sum(savings_plan_used_commitment) as "Unused commitment",
    sum(
        case
            when line_item_line_item_type = 'SavingsPlanRecurringFee' then 0
            else savings_plan_savings_plan_effective_cost
        end
    ) as "Effective Cost",
    sum(
        case
            when line_item_line_item_type = 'SavingsPlanRecurringFee' then 0
            else line_item_unblended_cost
        end
    ) - sum(
        case
            when line_item_line_item_type = 'SavingsPlanRecurringFee' then 0
            else savings_plan_savings_plan_effective_cost
        end
    ) - (
        sum(
            case
                when line_item_line_item_type = 'SavingsPlanCoveredUsage' then 0
                else savings_plan_recurring_commitment_for_billing_period
            end
        ) + sum(
            case
                when line_item_line_item_type = 'SavingsPlanCoveredUsage' then 0
                else savings_plan_amortized_upfront_commitment_for_billing_period
            end
        ) - sum(savings_plan_used_commitment)
    ) as "Savings"
from
    <Table Name>
where
    line_item_line_item_type in ('SavingsPlanCoveredUsage', 'SavingsPlanRecurringFee')
    and bill_billing_period_start_date = DATE_TRUNC('month', CURRENT_DATE) - INTERVAL '1' month
group by
    bill_billing_period_start_date,
    line_item_usage_account_id,
    savings_plan_offering_type,
    savings_plan_savings_plan_a_r_n,
    savings_plan_payment_option,
    line_item_line_item_type
order by
    sum(savings_plan_savings_plan_effective_cost) desc;
```

To understand this better, let’s break down two critical components found in the AWS CUR 2.0:

- **SavingsPlanRecurringFee**: This is the field in the output where <span style="color:red;">Item Type = 'SavingsPlanRecurringFee'</span>. It represents the cost that the purchasing account is obligated to pay for the Savings Plan commitment. This is a fixed cost, regardless of whether the full commitment was utilized. Depending on the Savings Plan type, this amount may be reflected as either unblended or amortized amount.

- **SavingsPlanCoveredUsage**: This is the field in the output where <span style="color:red;">Item Type = 'SavingsPlanCoveredUsage'</span>. It represents the actual usage of the Savings Plan, showing how much of the committed Savings Plan has been applied to usage across the organization. This usage can be spread across multiple accounts, depending on the organization’s structure and workload distribution.

To perform Savings Plan chargebacks, it is crucial to use the  **Effective Cost** column associated to each linked account. This column provides the cost that corresponds to the portion of the Savings Plan commitment that was used by each linked account. The goal is to ensure that each linked account receives a Savings Plan fee according to the benefits it received from the Savings Plan.

It is also important to validate the **Unused Commitment** column for rows with <span style="color:red;">SavingsPlanRecurringFee</span>. If the value in this column is greater than $0, it indicates that the Savings Plan is not fully utilized. While this under-utilization may indicate potential savings loss, it is important to validate. Organizations may deliberately purchase Savings Plan commitments that slightly exceed expected usage, as the overall savings from the discount can still outweigh the cost of the unused portion, providing a net savings benefit for the organization.

## Example
In the table below, the Savings Plan Type is <span style="color:red;">No Upfront</span>. The monthly recurring fee is charged to Account ID A as we see the associated ‘SavingsPlanRecurringFee’ field. Eligible usage in Account ID A gets the discount first as it is the account where the Savings Plan is purchased. Out of the $12,410.68 monthly commitment, $8,363.12 is the effective cost to be charged back to Account ID A. Account B used $1,361.26 out of the total recurring commitment, which would be Account B’s chargeback value. We can also observe that unused commitment is $0 and sum of effective cost matches with the recurring fee, which signifies that the Savings Plan is fully utilized.

![Figure 6 - Example report to show distribution of savings plans benefits among accounts](/images/3-BlogsTranslated/3.2-Blog2/6.jpg)
<p style="text-align:center; font-size:0.9em; color:gray;"><em>Figure 6 - Example report to show distribution of savings plans benefits among accounts</em></p>

Let’s see another example:

In the table below, we observe the Savings Plan Type is <span style="color:red;">All Upfront</span>, which corresponds to the amortized portion of the upfront payment for the billing period. The data shows that the Savings Plan was purchased in Account ID A and was fully utilized by Account ID A, as the ‘Unused Commitment’ is $0. In this case since there is only one account that is getting the benefit of the Savings Plan and the recurring fee matches with the effective cost.

![Figure 7 - Example report showing consumption of savings plan benefits by purchasing account](/images/3-BlogsTranslated/3.2-Blog2/7.jpg)
<p style="text-align:center; font-size:0.9em; color:gray;"><em>Figure 7 - Example report showing consumption of savings plan benefits by purchasing account</em></p>

## Conclusion
In this article, we discussed the impact Savings Plan sharing has on it’s usage. When sharing is enabled, there can be accounts that receive the benefit of Savings Plan discounts without having to pay a Savings Plan fee. The account that makes the purchase is solely obligated to pay the Savings Plan fee.

We used a targeted query in AWS Cost and Usage report 2.0 to design a chargeback mechanism that allows us to identify all the beneficiaries of Savings Plan discounts and proportion of the recurring fee they can be charged. Using this strategy, you can now use internal company specific chargeback mechanisms to chargeback accounts accurately based on the usage and therefore the savings they received, rather than just charging the account that holds the Savings Plan. This method allows for a fair and transparent distribution of both the costs and the benefits of the Savings Plans, helping to align financial responsibility with actual usage.

This strategy fosters transparency, accountability, and encourages thoughtful cloud usage across teams. By ensuring that all accounts are charged according to the Savings Plan benefits they receive, you promote a cost-conscious culture within your organization.

TAGS: [Chargeback](https://aws.amazon.com/blogs/aws-cloud-financial-management/tag/chargeback/), [Cost Allocation](https://aws.amazon.com/blogs/aws-cloud-financial-management/tag/cost-allocation/), [Savings Plans](https://aws.amazon.com/blogs/aws-cloud-financial-management/tag/savings-plans/), [Showback](https://aws.amazon.com/blogs/aws-cloud-financial-management/tag/showback/)

<table>
  <tr>
    <td style="vertical-align:top; width:110px; text-align:center;">
      <img src="/images/3-BlogsTranslated/3.2-Blog2/alonso.jpg" alt="Alonso de Cosio" style="width:100px; border-radius:8px; display:block; margin:0 auto 8px auto;"/>
      <div style="font-weight:bold; margin-top:4px;">Alonso de Cosio</div>
    </td>
    <td style="vertical-align:top; padding-left:20px;">
      Alonso de Cosio is a <b>Principal Technical Account Manager</b> at <b>AWS</b>. In his role, he provides advocacy and strategic technical guidance to help customers plan and build solutions using AWS best practices. He is passionate about building modular and scalable enterprise systems on AWS using <b>serverless</b> technologies. Beyond work, Alonso enjoys spending time with his wife and dog, as well as going to the beach and traveling.
    </td>
  </tr>
</table>

<table>
  <tr>
    <td style="vertical-align:top; width:110px; text-align:center;">
      <img src="/images/3-BlogsTranslated/3.2-Blog2/ketan.jpg" alt="Ketan Kumar" style="width:100px; border-radius:8px; display:block; margin:0 auto 8px auto;"/>
      <div style="font-weight:bold; margin-top:4px;">Ketan Kumar</div>
    </td>
    <td style="vertical-align:top; padding-left:20px;">
      Ketan is a <b>Senior Technical Account Manager</b> at <b>AWS</b>, based out of <b>Dublin, Ireland</b>. In his role, he provides strategic technical guidance to help customers use AWS best practices to plan and build solutions. He is dedicated to empowering customers to develop scalable, resilient, and cost-effective architectures.<br/>
      In his free time, Ketan enjoys spending time with his wife and family, traveling, playing video games, and watching movies.
    </td>
  </tr>
</table>