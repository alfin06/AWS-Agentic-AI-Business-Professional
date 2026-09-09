# NovaTech Data Verification Log

**Student Name:** Alfin Wijaya Rahardja 
**Date:** September 8, 2026

## Instructions

Query each pre-indexed knowledge base using Quick Chat. For each question, record the expected answer (from the data dictionary), Q's actual response, and whether they match. Minimum 6 entries (2 per data knowledge base).

## Verification Log

| # | Knowledge Base | Question Asked | Expected Answer | Q's Actual Answer | Match? | Notes |
|---|----------------|---------------|-----------------|-------------------|--------|-------|
| 1 | NovaTech CRM Deals | What is the total count of closed deals and how many were won versus lost? | 499 total deals: 315 Won, 184 Lost | Total Closed Deals: 499, Won: 315, Lost: 184 | PASS | Row count and deal outcomes match the CRM data dictionary. |
| 2 | NovaTech CRM Deals | How many unique sales reps and sales managers are there in the CRM data? | 30 sales reps and 6 sales managers. | Unique Sales Reps: 30, Unique Sales Managers: 6 | PASS | Confirmed against CRM fields sales_rep and sales_manager. |
| 3 | NovaTech Marketing Campaigns | What is the total row count and the overall campaign response rate? | 2,240 rows and a 27.19% response rate (609 responded). | Total Rows: 2,240, Overall Campaign Response Rate: 27.19% (609 responses out of 2,240) | PASS | Matches row count and calculated mean of campaign_response |
| 4 | NovaTech Marketing Campaigns | How many records in the marketing campaigns data have a missing annual income? | 24 rows have missing (null) annual income | There are 24 records with a missing (null) annual income in the marketing campaigns data. That's roughly 1% of the total 2,240 records. | PASS | Confirms known null count in annual_income (1.1% of records). |
| 5 | NovaTech Support Tickets | What is the total number of support tickets and how many are critical priority? | 3,000 total tickets, with exactly 50 critical priority tickets. | Total Support Tickets: 3,000, Critical Priority Tickets: 50 (~1.7% of total) | PASS | Matches distribution: 1,500 low, 1,050 medium, 400 high, 50 critical. |
| 6 | NovaTech Support Tickets | How many tickets are unresolved or have a missing ticket resolved date? | 59 tickets have a missing/null ticket_resolved_date | There are 59 tickets that are either unresolved (Is Resolved = 0) or have a missing ticket resolved date. | PASS | Validates 2.0% unresolved ticket rate documented in data dictionary |
| 7 | NovaTech Reference Documents | | | | | |

## Cross-Check

Pick one fact from above and confirm it independently in the QuickSight dataset preview.

- **Fact verified:** Total closed deal count and outcome breakdown (Won vs. Lost) in the CRM deals dataset.
- **Chat said:** Total Closed Deals: 499, Won: 315, Lost: 184
- **QuickSight shows:** The dataset preview for novatech_crm_deals.csv indicates 499 total rows; filtering or viewing the distribution on deal_stage displays 315 rows for "Won" and 184 rows for "Lost"
- **Consistent?** Yes
