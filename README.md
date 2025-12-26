# Multi-Agent Framework Demo

![Multi-Agent Framework](https://img.shields.io/badge/Framework-Multi--Agent-blue)
![Demo Version](https://img.shields.io/badge/Version-Demo-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

A **safe, company-agnostic demo** of a sophisticated multi-agent framework for data-driven business analysis and strategic decision making.

## 🚀 Quick Start

This demo allows you to experience the full capabilities of a multi-agent framework without exposing any sensitive company information. All brand names, specific data schemas, and business logic have been replaced with generic equivalents.

### Try It Now

1. **Set your business goal** in `task_demo.txt`
2. **Explore the generic data repository** in `data_repository_demo.md`
3. **Run the framework** to see agents collaborate
4. **Review the generated report** with strategic insights

## 📁 Project Structure

```
multi_agent_demo/
├── agents_demo.md              # Generic agent personas and capabilities
├── data_repository_demo.md     # Generic data schemas and analytical use cases
├── Gemini.md                   # Gemini Instructions
├── guardrails_demo.md          # Demo-specific guardrails and compliance rules
├── task_demo.txt               # Example business goals for demonstration
├── cli_config.yaml             # Agent configuration (unchanged)
├── README.md                   # This file
└── run/                       # Generated run directories (created during execution)
```

## 🎯 Key Features

### ✅ Safe for Public Sharing

- **No sensitive data**: All company-specific information removed
- **Generic schemas**: Realistic but anonymized data structures
- **Hypothetical scenarios**: Illustrative business examples
- **Privacy-compliant**: Designed for public GitHub repositories

### ✅ Full Framework Functionality

- **Multi-agent collaboration**: All 6 agent types work together
- **Complete workflow**: From goal setting to final report
- **Iterative refinement**: Strategic review and feedback loops
- **Data analysis**: Generic but realistic analytical patterns

### ✅ Educational Value

- **Learn agent roles**: Understand how each agent contributes
- **See workflow in action**: Experience the staged collaboration process
- **Study guardrails**: Learn about ethical AI and data privacy
- **Experiment safely**: Test different business scenarios

## 🤖 Agent Personas

The framework includes 6 specialized agents that collaborate to solve business problems:

| Agent | Role | Responsibilities |
|-------|------|----------------|
| **Senior Director** | Strategic Leader | Sets vision, clarifies intent, provides final approval |
| **Data Strategist** | Hypothesis Generator | Creates data-backed hypotheses from business goals |
| **Lead Analyst** | Data Engineer | Writes production-ready analytical code |
| **Lead Data Scientist** | ML Strategist | Evaluates modeling opportunities and statistical rigor |
| **Lead Researcher** | Market Intelligence | Conducts secondary research and validates hypotheses |
| **Lead Report Writer** | Storyteller | Synthesizes insights into executive reports |

## 📊 Generic Data Repository

The demo includes a comprehensive generic data repository with 6 data feeds:

| Data Feed | Purpose | Key Metrics |
|-----------|---------|-------------|
| **Customer Data** | Customer profiles and behavior | Demographics, purchase history, engagement |
| **Product Data** | Product catalog and performance | Categories, pricing, sales, ratings |
| **Sales Transactions** | Transaction-level sales data | Amounts, methods, locations, timing |
| **Marketing Campaigns** | Campaign performance | Impressions, clicks, conversions, ROI |
| **Web Analytics** | Website visitor behavior | Sessions, duration, devices, conversions |
| **Competitive Data** | Market positioning | Share of wallet, regional performance |

## 🚀 Example Business Goals

Here are some generic business goals you can use to test the framework:

### 1. Customer Acquisition

```
GOAL: Increase customer acquisition and market share in underperforming regions by identifying high-potential customer segments and developing targeted marketing strategies that leverage competitive insights.
```

### 2. Customer Retention

```
GOAL: Reduce customer churn in underperforming segments by identifying key drivers and developing targeted retention strategies using demo customer data.
```

### 3. Product Innovation

```
GOAL: Identify product innovation opportunities by analyzing customer preferences, purchase patterns, and market trends in the generic product data.
```

### 4. Marketing Optimization

```
GOAL: Optimize marketing spend allocation by analyzing channel performance, customer segment response, and ROI patterns in the demo marketing data.
```

### 5. Market Expansion

```
GOAL: Identify new market expansion opportunities by analyzing regional performance, customer demographics, and competitive positioning using the generic data repository.
```

## 🔧 Technical Requirements

### Prerequisites

- Python 3.8+
- PySpark (for data analysis)
- Gemini CLI (for agent orchestration)
- Basic understanding of data analysis concepts

### Installation

```bash
# Clone the repository
git clone https://github.com/your-repo/multi-agent-demo.git
cd multi-agent-demo

# Install dependencies
pip install pyspark gemini-cli

# Set up your environment
python -m spylon-kernel install
```

## 📖 Usage Examples

### Basic Workflow

```bash
# 1. Define your business goal
echo "GOAL: Increase customer retention in Region North by 15%" > task_demo.txt

# 2. Run the multi-agent framework
gemini run --config cli_config.yaml --task task_demo.txt

# 3. Review the generated report
cat run/YYYYMMDD_hhmmss_retention/report.md
```

### Advanced Usage

```bash
# Customize agent configurations
nano cli_config.yaml

# Add your own generic business scenarios
nano task_demo.txt

# Explore the data repository
nano data_repository_demo.md

# Review guardrails and compliance
nano guardrails_demo.md
```
## 📃 Sample Output

<img width="1418" height="925" alt="image" src="https://github.com/user-attachments/assets/c3c06bad-f982-4e8a-94cd-a91bcf2befb0" />

## 🎓 Learning Resources

### For Beginners

- Start with simple business goals
- Review the generated transcripts to understand agent collaboration
- Study the sample hypotheses and analytical approaches
- Experiment with different goal formulations

### For Developers

- Examine the agent configurations in `cli_config.yaml`
- Study the guardrail implementation in `guardrails_demo.md`
- Review the workflow documentation for integration points
- Test edge cases and error handling

### For Business Users

- Focus on the strategic workflow and agent roles
- Learn how to formulate effective business goals
- Understand the hypothesis-to-insight process
- Study the report structure and content quality

## 🛡️ Guardrails & Compliance

The framework includes comprehensive guardrails to ensure safe and ethical operation:

### Universal Guardrails

- **No Hallucination**: Agents never invent data or sources
- **No Unauthorized Access**: Strict data access controls
- **Privacy Protection**: No PII or sensitive data exposure
- **Version Awareness**: Current and relevant sources only

### Demo-Specific Guardrails

- **Generic Data Only**: No real company names or brands
- **Hypothetical Scenarios**: Illustrative but not actionable
- **Privacy by Design**: Built for public sharing
- **Clear Disclaimers**: All outputs labeled as demo/examples

## 🔄 Iterative Workflow

The framework follows a staged, iterative process:

1. **Initiation**: Load agents and create run directory
2. **Hypothesis Generation**: Data Strategist creates testable hypotheses
3. **Execution**: Analysts write code to test hypotheses
4. **Research**: Researcher finds supporting market data
5. **Reporting**: Report Writer synthesizes insights
6. **Review**: Senior Director provides strategic feedback
7. **Iteration**: Loop back for refinement until approved

## 📈 Sample Outputs

### Hypothesis Example

```
Hypothesis: Customers in Region North who haven't purchased in 90+ days show 25% higher response rates to personalized email campaigns compared to generic promotions.

Rationale: Demo data shows that re-engagement campaigns targeting inactive customers in this region have historically shown better performance.

Data Signals: customer_segment, last_purchase_date, region, campaign_response_rate

Expected Pattern: Higher engagement and conversion rates from personalized vs. generic campaigns
```

### Analytical Code Example

```python
# Analyze customer re-engagement patterns by region
from pyspark.sql import functions as F

customer_engagement = spark.table("customer_data")
    .join(spark.table("marketing_campaigns"), "customer_id")
    .filter("days_since_last_purchase > 90")
    .groupBy("region", "campaign_type")
    .agg(
        F.countDistinct("customer_id").alias("customer_count"),
        F.avg("response_rate").alias("avg_response_rate"),
        F.sum("conversions").alias("total_conversions")
    )
    .orderBy(F.desc("avg_response_rate"))
```

### Report Structure

```
1. Executive Summary
   - Key insights and recommendations
   - Strategic overview

2. Methodology
   - Data sources used
   - Analytical approaches
   - Research methods

3. Regional Analysis
   - Performance by region
   - Growth opportunities
   - Competitive insights

4. Customer Segmentation
   - High-value segments
   - Engagement patterns
   - Retention strategies

5. Strategic Recommendations
   - Prioritized initiatives
   - Implementation roadmap
   - Success metrics
```

## 🤝 Contributing

We welcome contributions to improve the demo framework!

### How to Contribute

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Make your changes
4. Test thoroughly with demo data
5. Submit a pull request

### Contribution Guidelines

- Maintain data privacy and generic content
- Follow existing code patterns and documentation style
- Add tests for new features
- Update documentation as needed
- Ensure all guardrails remain enforced

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Inspired by advanced multi-agent collaboration frameworks
- Designed for educational and demonstration purposes
- Built with privacy and ethical AI principles
- Thanks to all contributors and testers

## 📧 Contact

For questions about this demo:

- Open an issue on GitHub
- Review the documentation
- Check the FAQ section
- Contact the maintainers

---

## 🚨 Important Disclaimers

1. **Demo Only**: All outputs are illustrative and not based on real business data
2. **No Real Insights**: Strategic recommendations are hypothetical examples
3. **Generic Data**: All schemas and data patterns are simplified for demonstration
4. **Educational Purpose**: Designed for learning and testing, not production use
5. **Privacy Compliant**: Contains no sensitive or proprietary information

This demo provides a safe, company-agnostic way to experience the full capabilities of a sophisticated multi-agent framework while maintaining complete data privacy and business confidentiality.




