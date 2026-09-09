# NovaTech Q Exploration Log

**Student Name:** Alfin Wijaya Rahardja
**Date:** September 9, 2026

## Q Exploration Questions

For each question, record Q's answer and cross-check against your dashboard.

| # | Question Asked | Q's Answer (summarize) | Dashboard Visual Used to Cross-Check | Dashboard Shows | Match? | Notes |
|---|---------------|----------------------|--------------------------------------|-----------------|--------|-------|
| 1 | Which campaign channel has the highest conversion rate? | Marketing Funnel — Funnel Stage by Channel | Identifies Direct Mail (53.0% response/conversion), followed by Paid Social (40.3%), Partner Referral (34.3%), and Email (8.7%). | Marketing Funnel — Response Rate by Campaign Channel | Direct Mail leads with 53.0% response rate; Email has the lowest at 8.7%. | YES | Q maps "conversion rate" to campaign_response (or funnel_stage = Closed Won rate). If Q initially asks to disambiguate "conversion", selecting response rate yields 53.0%. |
| 2 | What is the average deal size by company size? | Displays average deal_value grouped by company_size_tier: Enterprise has the highest average deal value, followed by Mid-Market and SMB. | Sales Pipeline — 
Closed Won Revenue by Industry & Company Tier | Enterprise accounts yield the highest average deal value within the $0.71M total won pipeline. | YES | Q successfully averages deal_value per company_size_tier. |
| 3 | What is the average resolution time for critical vs. low-priority tickets? | Shows 61.3 hours for critical priority tickets vs. 58.4 hours for low priority tickets. | Customer Health — Average Resolution Time (Hours) by Product Area & Priority | Critical priority: 61.3 hours; Low priority: 58.4 hours (difference: 2.9 hours - 5.0% longer for critical). | YES | Resolution times are closely clustered near ~58 hours across priority levels, though critical issues in Analytics Dashboard peak around 102 hours. |
| 4 | What are the top 10 accounts by support ticket volume, and what is their total deal revenue? | The dashboard's Customer Health sheet doesn't have a visual that breaks down ticket volume or deal revenue at the account level — the visuals are aggregated by product area, priority, customer tier, and industry. | Customer Health - None | Customer Health - None | VALID | It is a valid finding that Q cannot answer this question |
| 5 | Are there any campaigns where we spent more than we earned back? | Yes — in fact, all 6 campaigns are spending significantly more than they're earning back. This is a notable finding from the Marketing Funnel sheet of the **NovaTech Executive Performance Dash | Marketing Funnel — NovaTech Executive Performance Dashboard (with the Campaign Channel filter expanded to include all channels) | Every campaign bar displays campaign_spend exceeding revenue_attributed (e.g., NovaPulse Launch: $2.42M spend vs. $394.2K revenue). | YES | Demonstrates Q's ability to evaluate comparative conditions (campaign_spend > revenue_attributed). |

## Reflection (include in written summary)

- Where did Q agree with the dashboard? Single-Domain Aggregations and Rankings, Dimensional Segmentations, 

- Where did Q disagree or struggle? Why? 
Grain and Visual Scope Limitations (Account-Level Details): Q struggled on Question 4 (identifying the top 10 accounts by support ticket volume alongside their total deal revenue) because the dashboard visuals were pre-aggregated at higher categorical grains (product area, priority, customer tier, and industry) rather than broken down at the individual account level (account_id).
Cross-Entity Multi-Metric Joins: Querying across distinct entity boundaries (CRM deal revenue combined with support ticket counts at the account level) requires complex multi-table joins and appropriate grain alignment. Because no pre-built account-level summary table existed on the Customer Health sheet to cross-check against, Q could not resolve the dual-metric ranking, documenting this as an intentional and valid finding.

- When would you use Q vs. the dashboard to answer a business question?
Use QuickSight Q / Quick Chat for:
1. Ad-Hoc and Comparative Inquiries: Fast, natural language interrogations such as comparative evaluations ("Are there any campaigns where we spent more than we earned back?") that do not require building dedicated charts.
2. Unplanned Dimensional Slicing: Quickly asking for specific cross-sections (e.g., critical vs. low-priority ticket resolution times) without manually resetting or reconfiguring visual filters on a live report.
3. Self-Service Exploration for Non-Technical Users: Enabling executives to ask plain-English questions directly without navigating complex menus or knowing underlying schema names.

Use the Published Dashboard for:
1. Standardized Executive Monitoring: Tracking fixed, auditable core KPIs ($1.13M marketing revenue, $0.71M won revenue, 63.13% win rate, 67-day sales velocity) within a curated layout.
2. Contextual Decision-Making: Reviewing structured, 4-part analytical text annotations (Performance Summary, Divergence, Impact, Recommendation) alongside visual charts to understand operational drivers.
3. Cross-Sheet Workflows and Guided Navigation: Utilizing one-click visual filtering and cross-sheet navigation actions to drill methodically from macro customer health indicators into detailed pipeline risk.