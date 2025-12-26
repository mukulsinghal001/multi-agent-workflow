# Multi-Agent Framework Demo - Usage Guide

Welcome to the Multi-Agent Framework Demo! This guide will help you get started with using the demo version to experience the full capabilities of the framework.

## 🚀 Quick Start

### 1. Install Prerequisites

```bash
# Install Python 3.8+
# Install required packages
pip install pyspark gemini-cli

# Set up PySpark kernel
python -m spylon-kernel install
```

### 2. Run Your First Demo

```bash
# Navigate to the demo directory
cd multi-agent-demo

# Run with the default demo task
gemini run --config cli_config.yaml --task task_demo.txt
```

### 3. Review Results

```bash
# Check the generated run directory
ls runs/

# Read the final report
cat runs/YYYYMMDD_hhmmss_goal/report.md

# Review the full transcript
cat runs/YYYYMMDD_hhmmss_goal/transcript.md
```

## 📖 Understanding the Framework

### Agent Roles

| Agent | Purpose | When It Runs |
|-------|---------|---------------|
| **Senior Director** | Strategic oversight | Beginning and end of each run |
| **Data Strategist** | Hypothesis generation | Stage 1 - After goal is set |
| **Lead Analyst** | Data analysis | Stage 2 - Hypothesis testing |
| **Lead Data Scientist** | Statistical modeling | Stage 2 - Advanced analysis |
| **Lead Researcher** | Market research | Stage 3 - External validation |
| **Lead Report Writer** | Report generation | Stage 4 - Synthesis |

### Workflow Stages

```
GOAL SET → HYPOTHESIS → ANALYSIS → RESEARCH → REPORT → REVIEW → (ITERATE)
```

## 🎯 Common Use Cases

### 1. Customer Acquisition Analysis

**Goal Example:**

```
GOAL: Identify high-potential customer segments in underperforming regions and develop targeted acquisition strategies.
```

**Expected Output:**

- Customer segment analysis by region
- Acquisition channel effectiveness
- Competitive benchmarking
- Strategic recommendations

### 2. Customer Retention Study

**Goal Example:**

```
GOAL: Reduce customer churn by 20% in the next quarter by identifying key drivers and developing targeted retention programs.
```

**Expected Output:**

- Churn analysis by customer segment
- Engagement pattern identification
- Retention strategy recommendations
- Implementation roadmap

### 3. Product Performance Analysis

**Goal Example:**

```
GOAL: Improve product portfolio performance by identifying top-performing categories and optimization opportunities.
```

**Expected Output:**

- Product category analysis
- Sales performance trends
- Pricing strategy insights
- Portfolio optimization recommendations

## 🔧 Customizing Your Demo

### Create Custom Business Goals

Edit `task_demo.txt` with your own generic business scenarios:

```bash
# Open the task file
nano task_demo.txt

# Add your goal
GOAL: [Your generic business objective here]

# Save and exit (Ctrl+X, Y, Enter)
```

### Modify Agent Configurations

Adjust agent parameters in `cli_config.yaml`:

```yaml
agents:
  SeniorDirector:
    temperature: 0.2  # More conservative
    top_k: 30
  
  DataStrategist:
    temperature: 0.6  # More creative
    top_p: 0.95
```

### Explore Data Repository

Review the generic data schemas in `data_repository_demo.md`:

```bash
# View available data feeds
cat data_repository_demo.md

# See field dictionaries and analytical use cases
```

## 📊 Analyzing Results

### Understanding the Transcript

The `transcript.md` file contains:

- **Agent conversations**: How agents collaborate
- **Hypothesis generation**: Initial ideas and rationale
- **Analysis results**: Data findings and insights
- **Research findings**: External validation
- **Iteration history**: Feedback and refinements

### Reading the Report

The `report.md` file includes:

- **Executive Summary**: Key insights and recommendations
- **Methodology**: How the analysis was conducted
- **Findings**: Detailed results and patterns
- **Recommendations**: Actionable strategies
- **Appendices**: Supporting data and references

## 🎓 Learning Tips

### For Beginners

1. Start with simple, clear goals
2. Review the transcript to understand agent collaboration
3. Study the hypothesis generation process
4. Examine the analytical code patterns
5. Learn from the report structure

### For Intermediate Users

1. Experiment with different goal formulations
2. Modify agent configurations for different outcomes
3. Analyze how hypotheses are generated from goals
4. Study the iterative refinement process
5. Compare different report outputs

### For Advanced Users

1. Test edge cases and complex scenarios
2. Analyze guardrail enforcement
3. Study agent interaction patterns
4. Experiment with different data configurations
5. Contribute improvements to the demo

## 🛠️ Troubleshooting

### Common Issues

**Issue: Framework not starting**

```bash
# Check Python environment
python --version

# Verify dependencies
pip list | grep pyspark
pip list | grep gemini
```

**Issue: No output generated**

```bash
# Check task file format
cat task_demo.txt

# Verify goal starts with "GOAL:"
```

**Issue: Slow performance**

```bash
# Reduce data complexity
# Simplify business goal
# Adjust agent configurations
```

### Debugging Tips

```bash
# Enable verbose logging
gemini run --verbose --config cli_config.yaml --task task_demo.txt

# Check intermediate files
ls -la runs/YYYYMMDD_hhmmss_goal/

# Review agent logs
cat runs/YYYYMMDD_hhmmss_goal/agent_logs.txt
```

## 📈 Advanced Usage

### Batch Processing

```bash
# Run multiple goals sequentially
for goal in goals/*.txt; do
    gemini run --config cli_config.yaml --task $goal
    sleep 60  # Avoid rate limiting
done
```

### Custom Data Integration

```bash
# Add your own generic data feeds
# Follow the pattern in data_repository_demo.md
# Ensure all data is generic and privacy-compliant
```

### Performance Optimization

```bash
# Adjust agent configurations for speed vs. quality
# Lower temperature for faster, more deterministic results
# Higher temperature for more creative but slower results
```

## 🤝 Community Resources

### Getting Help

- **GitHub Issues**: Report bugs and request features
- **Documentation**: Review README.md and contributing guidelines
- **FAQ**: Check common questions and answers
- **Discussions**: Join community conversations

### Sharing Your Work

```bash
# Share your demo results (remove any sensitive info)
git clone your-fork
cd your-fork
# Add your example goals and results
git add examples/
git commit -m "Added example: [description]"
git push origin main
```

## 🚨 Important Reminders

1. **Demo Only**: All outputs are illustrative, not real business insights
2. **Generic Data**: No real company names, brands, or proprietary information
3. **Privacy First**: Designed for safe public sharing
4. **Educational Purpose**: For learning and testing only
5. **No Production Use**: Not intended for real business decisions

## 📚 Additional Resources

- [README.md](README.md) - Complete project overview
- [CONTRIBUTING.md](CONTRIBUTING.md) - How to contribute
- [data_repository_demo.md](data_repository_demo.md) - Generic data schemas
- [Gemini.md](Gemini.md) - Framework workflow
- [guardrails_demo.md](guardrails_demo.md) - Safety guidelines

---

**Need More Help?**

- Check the [FAQ](FAQ.md)
- Review the [documentation](README.md)
- Open a GitHub issue
- Join the community discussion

**Happy Exploring!** 🎉
