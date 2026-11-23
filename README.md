# Handex Academy: SQL Analytics Case Study

An online course platform (Handex Academy) needs real numbers for its next
investment round: who earns, who owes, which course is dead? This project
answers 16 business questions from the CEO, finance, marketing and product
teams using **Oracle SQL**.

## Data model

Tables: `category`, `instructor`, `course`, `student`, `enrollment`,
`payment`, `review`.

Key points:
- One enrollment can have several payments (installments)
- Some enrollments have no payment (debtors)
- Some courses are ARCHIVED or have no enrollments

## Questions covered

| # | Topic | Techniques |
|---|-------|------------|
| 1 | Catalog status per category | LEFT JOIN, filter in ON clause |
| 2 | Monthly cash flow (last 12 months) | GROUP BY, date functions |
| 3 | Instructor revenue | multiple LEFT JOINs, NVL |
| 4 | Courses with no enrollments | NOT EXISTS |
| 5 | Course completion rate | CTE, conditional aggregation |
| 6 | Debtors: no payment | NOT EXISTS |
| 7 | Debtors: partial payment | GROUP BY, HAVING |
| 8 | Biggest payment per student | ROW_NUMBER |
| 9 | Top course per category | ROW_NUMBER over aggregate |
| 10 | Most loyal student | RANK (ties kept) |
| 11 | Monthly bestseller | ROW_NUMBER, tie-break |
| 12 | Courses with 3+ reviews | HAVING |
| 13 | Above-average courses | scalar subquery |
| 14 | Audience by age group | CTE, CASE |
| 15 | Inactive students (3 months) | correlated NOT EXISTS |
| 16 | Best course per instructor | ROW_NUMBER |

## Rules followed

- All dates are relative to `sysdate` (no hardcoded dates)
- Revenue is calculated from `payment.amount`, not `course.price`
- Money and percentages are rounded to 2 decimals
- CANCELLED enrollments are excluded where it makes business sense

## How to run

Run `queries/handex_academy_queries.sql` in Oracle SQL Developer, SQL*Plus
or any Oracle 12c+ database that has the tables above.

## Author

Your Name · [LinkedIn](#)
