# Multi-Agent Framework - Demo Version

This document describes a generic multi-agent framework workflow that can be used for demonstration purposes. All company-specific references have been removed and replaced with generic examples.

## Core Concepts

*   **Goal**: A statement or question that will need to be analyzed and reported on.
*   **WorkItem**: A task to be completed by an agent. It has a `description` and a `result`.
*   **Run**: Manages the state for a given `Goal`. It tracks all `WorkItem`s and other necessary state.
*   **Agent Persona**: A definition of an agent's capabilities, expertise, and personality, stored as a heading in the `agents_demo.md` file.

## Run Directory & Artifacts

Each run will have a unique directory inside the `runs` directory. The directory name will be prefixed with a timestamp in the format `YYYYMMDD_hhmmss_<short_goal>`, where `<short_goal>` is a brief, 10-20 character version of the goal that best describes it.

Within this directory, the following files will be generated:

*   **`transcript.md`**: A detailed log of all agent interactions. This includes not just the results of each `WorkItem`, but also the detailed internal monologue, discussions, and step-by-step reasoning of the agents as they perform their tasks.
*   **`report.md`**: The final, user-facing report. This is a comprehensive document that leads with a strong executive summary and includes detailed sections on methodology, analysis, insights, and strategic recommendations.

## Staged Workflow

### 1. Initiation
*   The user provides a `task_demo.txt` file with a business goal.
*   All Agent Personas from `agents_demo.md` are loaded.
*   A `Run` is initiated, and its unique directory is created.

### 2. Stage 1: Data Strategy & Hypothesis Generation
**Agents**: 'DataStrategist'

**Process**: The 'DataStrategist' analyzes the goal and leverages the 'data_repository_demo.md' to frame data-backed hypotheses. Each hypothesis must include:
- Clear rationale
- Data signals and sources
- KPI/metric lens
- Expected patterns
- Data availability or gaps

**Output**: A comprehensive list of data-backed hypotheses recorded as 'WorkItems' in 'transcript.md'

### 3. Stage 2: Execution & Analysis
**Agents**: 'LeadAnalyst', 'LeadDataScientist'

**Process**: Worker Agents execute the WorkItems in sequence. All actions, including the agent's internal reasoning, data gathered, and code generated, are logged to 'analysis_code.py'.

**Output**: A list of completed WorkItems with their detailed results and analytical code logged in 'analysis_code.py'.

### 4. Stage 3: Market & Secondary Research
**Agents**: 'LeadResearcher'

**Process**: The Research Agent executes secondary market research to support the hypotheses created by the Data Strategist. Research findings are logged in 'transcript.md'.

**Output**: Detailed market research output logged under 'transcript.md'.

### 5. Stage 4: Synthesis & Reporting
**Agents**: 'LeadReportWriter'

**Process**: The Report-Writer Agent synthesizes the entire 'transcript.md' to construct the initial draft in the 'report.md'.

**Output**: A draft 'report.md' file ready for review.

### 6. Stage 5: Strategic Review & Feedback
**Agents**: 'SeniorDirector'

**Process**: The SeniorDirector agent reviews the generated report.md against the strategic objectives defined in Stage 1.

1. **Approval Path**: If the report meets strategic objectives, the run is considered complete.
2. **Revision Path**: If the report requires revision, the SeniorDirector provides specific feedback requesting additional information, deeper analysis, or clarification.

**Output**: Either final approval of the 'report.md' or a list of feedback points and new requirements.

### 7. Iteration Loop
*   If strategic feedback is provided, the process loops back to **Stage 2: Execution & Analysis**.
*   All agents incorporate the SeniorDirector feedback and create new `WorkItem`s to address them.
*   The workflow proceeds through **Stage 3 (Research)** and **Stage 4 (Reporting)** again, generating a revised `report.md`.
*   This iterative process continues until the SeniorDirector gives final approval in **Stage 5**.

## Execution Trigger

To initiate a demo run, the user will provide a prompt starting with the key phrase `GOAL:` followed by a generic business objective.

## Example Demo Goals

Here are some generic business goals that can be used for demonstration:

1. **Customer Retention**: "GOAL: Increase customer retention rates in underperforming regions by identifying key drivers of churn and developing targeted retention strategies."

2. **Market Expansion**: "GOAL: Identify new market opportunities for product expansion by analyzing customer demographics, purchase patterns, and regional performance."

3. **Campaign Optimization**: "GOAL: Optimize marketing campaign performance by analyzing channel effectiveness, customer segment response, and ROI across different regions."

4. **Product Innovation**: "GOAL: Develop data-driven product recommendations by analyzing customer preferences, market trends, and competitive positioning."

5. **Operational Efficiency**: "GOAL: Improve operational efficiency by identifying process bottlenecks, resource allocation patterns, and performance metrics across business units."

## Demo Workflow Example

### Sample Goal
```
GOAL: Increase customer engagement and sales in regions with below-average performance by identifying key customer segments and developing targeted marketing strategies.
```

### Expected Demo Process

1. **Data Strategist** generates hypotheses like:
   - "Customers in Region X who haven't purchased in 90+ days respond best to personalized email campaigns"
   - "High-value customers in Region Y show 30% higher engagement with featured products"
   - "Mobile users in Region Z have 20% higher conversion rates when targeted with location-based offers"

2. **Lead Analyst** writes PySpark code to test these hypotheses using the demo data repository:
   ```python
   # Example: Analyze customer engagement by region and segment
   from pyspark.sql import functions as F
   
   customer_engagement = spark.table("customer_data")
   .join(spark.table("sales_transactions"), "customer_id")
   .groupBy("region", "customer_segment")
   .agg(
       F.countDistinct("transaction_id").alias("transaction_count"),
       F.sum("transaction_amount").alias("total_spend"),
       F.avg("transaction_amount").alias("avg_transaction_value")
   )
   .orderBy("region", F.desc("total_spend"))
   ```

3. **Lead Researcher** finds supporting market research:
   - Industry benchmarks for customer engagement metrics
   - Regional market trends and consumer behavior studies
   - Best practices for personalized marketing campaigns

4. **Lead Report Writer** synthesizes findings into a comprehensive report with:
   - Executive summary of key insights
   - Regional performance analysis
   - Customer segment recommendations
   - Strategic marketing recommendations

5. **Senior Director** reviews and provides feedback for refinement

## Demo Benefits

This generic workflow allows users to:

- Understand the multi-agent framework capabilities without exposing sensitive data
- Experiment with different business scenarios using generic data structures
- Learn how agents collaborate to solve complex business problems
- Generate sample reports and analyses for educational purposes
- Test the framework's adaptability to various business domains


The demo version maintains all the core functionality while ensuring complete data privacy and business confidentiality.
