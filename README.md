# ECON-3916-Problem-Set-3
The Number Nobody Can Reproduce

Overview

In this problem set, I used Python, DuckDB, SQL, and regression analysis to investigate how data processing decisions can affect business results.

Phase 1: JOIN and Revenue

I simulated 3,000 customers and their orders. I found that the average revenue per West customer was about $809.40, but it increased to $1,216.86 after joining the customers and orders tables.

This happened because customers with multiple orders appeared multiple times. I also created a row-count check to warn about possible JOIN problems.

Phase 2: Missing Data and Window Functions

I introduced missing region values for approximately 15% of customers. In my simulation, 405 customers had missing regions.

I compared SQL filters with and without IS NULL and learned how missing values can be silently excluded. I also used a window function to calculate regional averages while keeping all 3,000 customer rows.

Phase 3: Causal Inference

I simulated a programme with a true effect of $20.

The naive estimate was $186.35, while controlling for account size gave an estimate of $21.27. Adding support tickets changed the estimate to -$23.55.

This showed me that choosing the right control variables is important for causal analysis.

Phase 4: AI SQL Reviewer

I used GPT-6 to generate a Python function called review_query().

I tested it on my SQL queries and found that it detected potential JOIN duplication, aggregation problems, and NULL filtering.

The reviewer was useful, but it also produced warnings for filters that could be intentional. This showed me why AI-generated code still needs testing and human judgment.

Key Takeaway

This problem set helped me understand that a SQL query can run successfully but still produce misleading results. Checking the unit of observation, missing data, and control variables is important before reporting results.
