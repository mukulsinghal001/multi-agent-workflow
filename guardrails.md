# Agent Guardrails 🛑
*Enforced rules for all agents in the hypothesis-to-insight workflow. Violations must be caught at prompt or orchestration level.*

---

## 🔐 **Universal Guardrails**
*(Apply to ALL agents)*

1. **No Hallucination**
   - Never invent data, metrics, report names, or source URLs.
   - If uncertain, state: `"Insufficient evidence to conclude"` or `"Requires validation"`.
   - Cite sources explicitly using `[Source Name, Year]` format.

2. **No Unauthorized Data Access**
   - You **MUST NOT** perform web searches to retrieve content from internal documents (e.g., `data_repository_demo.md`).
   - Internal data access is ONLY via:
     - Provided context in the prompt
     - Structured reference files
     - Approved RAG retrieval from vetted internal knowledge base

3. **Privacy & Compliance**
   - Never reference PII, raw user IDs, or confidential information unless explicitly provided and anonymized.
   - For sensitive hypotheses, default to privacy-safe assumptions.
   - Reject sources older than 12 months unless foundational (e.g., industry standards).

4. **Version Awareness**
   - When citing reports, include year (e.g., *"Gartner Market Trends 2024"*).
   - Reject outdated sources that may no longer be relevant.

---

## 🎯 **Role-Specific Guardrails**

### **DataStrategist**
- ✅ **DO**: Generate hypotheses grounded in `data_repository_demo.md` schema (e.g., available columns, data types).
- ❌ **DO NOT**: Propose hypotheses requiring data not described in the schema.
- ⚠️ **Flag**: If goal is vague, request clarification — *never guess intent*.

### **LeadResearcher**
- ✅ **DO**: Use web search **only** for *external* secondary research (reports, news, public data).
- ❌ **DO NOT**: Search the web for internal demo documents — these must come via context/RAG.
- ✅ **DO**: Triangulate with ≥2 independent sources for high-confidence claims.
- ❌ **DO NOT**: Cite vendor blogs as primary evidence — only for hypothesis generation.

### **LeadAnalyst**
- ✅ **DO**: Write PySpark/SQL optimized for production (partitioning, broadcast joins).
- ❌ **DO NOT**: Use `.collect()`, `toPandas()`, or non-deterministic UDFs in final code.
- ✅ **DO**: Reference `data_repository_demo.md` for column semantics — *never assume*.
- ❌ **DO NOT**: Generate fake sample data — use `df.limit(5).show()` pattern for validation.

### **LeadDataScientist**
- ✅ **DO**: Recommend modeling only when (a) hypothesis implies prediction, and (b) data supports it.
- ❌ **DO NOT**: Propose black-box models for client-facing insights — prefer interpretable models.
- ✅ **DO**: Specify statistical assumptions (e.g., "Requires normal distribution for regression").
- ❌ **DO NOT**: Claim significance without confidence intervals or p-values.

### **LeadReportWriter**
- ✅ **DO**: Structure reports using consulting frameworks (Issue Tree, SWOT) when strategic depth is needed.
- ❌ **DO NOT**: Introduce new hypotheses or data not validated by prior agents.
- ✅ **DO**: Attribute all insights to originating agent (e.g., *"Per LeadResearcher's findings…"*).
- ❌ **DO NOT**: Use marketing fluff — stay evidence-based and data-driven.

---

## 🧪 **Validation Protocol**
- All agents must self-audit output against these guardrails before submission.
- Orchestrator will reject outputs violating **Universal Guardrails**.
- Human-in-the-loop required for:
  - Hypotheses involving sensitive data domains
  - Model proposals with extreme performance claims
  - Reports with strategic business recommendations

---

## 📋 **Demo-Specific Guardrails**

### **Data Privacy in Demo Mode**
- ❌ **DO NOT**: Include any real company names, brands, or proprietary information
- ✅ **DO**: Use generic placeholders (e.g., "Company X", "Product Category A")
- ❌ **DO NOT**: Reference specific geographic locations that could identify real businesses
- ✅ **DO**: Use generic regions (e.g., "Region North", "Urban Area")

### **Hypothesis Generation in Demo**
- ✅ **DO**: Create realistic but generic business hypotheses
- ❌ **DO NOT**: Use real market data or competitive intelligence
- ✅ **DO**: Base hypotheses on the generic data repository schema
- ❌ **DO NOT**: Make claims about real industry performance

### **Reporting in Demo Mode**
- ✅ **DO**: Generate comprehensive but generic business reports
- ❌ **DO NOT**: Include real financial figures or market share data
- ✅ **DO**: Use illustrative examples and hypothetical scenarios
- ❌ **DO NOT**: Present demo outputs as real business insights

---

## 🎓 **Demo Usage Guidelines**

### **For Educators & Trainers**
- Clearly label all demo outputs as "DEMO/EXAMPLE ONLY"
- Explain the difference between demo data and real business data
- Use demo to teach framework concepts, not specific business strategies
- Encourage users to create their own generic business scenarios

### **For Developers & Testers**
- Use demo data to test framework functionality and agent interactions
- Verify that all guardrails are properly enforced in demo mode
- Test edge cases and error handling with generic scenarios
- Ensure no real data can accidentally be exposed through demo interfaces

### **For Business Users**
- Understand that demo outputs are illustrative, not actionable
- Use demo to evaluate framework capabilities and agent collaboration
- Create test scenarios that match your business domain (without real data)
- Focus on process understanding rather than specific insights

---

## 🚨 **Guardrail Violation Examples**

### **❌ VIOLATION: Hallucination**
**Bad**: "According to our internal Q3 2024 report, customer churn increased by 15% due to pricing changes."
**Good**: "Analysis of demo customer data suggests potential churn patterns that would require validation with real data."

### **❌ VIOLATION: Real Data Exposure**
**Bad**: "Nike customers in New York show higher engagement than Adidas customers in Los Angeles."
**Good**: "In our demo scenario, customers in Region A show different engagement patterns than customers in Region B."

### **❌ VIOLATION: Unsubstantiated Claims**
**Bad**: "Our analysis proves that email campaigns generate 35% higher ROI than social media."
**Good**: "Based on the demo data patterns, email campaigns appear to show higher engagement metrics, which would need to be validated with real campaign data."

### **❌ VIOLATION: Specific Geographic References**
**Bad**: "Customers in zip code 90210 have the highest lifetime value."
**Good**: "Customers in the 'Urban High-Income' segment show higher lifetime value patterns in the demo data."

---

## ✅ **Guardrail-Compliant Examples**

### **Hypothesis Generation**
**Good**: "Customers in the 'Frequent Buyer' segment who haven't purchased in 60+ days may respond to targeted re-engagement campaigns (based on demo purchase frequency patterns)."

### **Data Analysis**
**Good**: "Analysis of demo transaction data shows that customers who purchase from multiple product categories have 20% higher average order value (would require validation with real data)."

### **Market Research**
**Good**: "Industry reports suggest that personalized marketing campaigns typically show 15-25% higher engagement rates, which aligns with patterns observed in our demo data analysis."

### **Final Reporting**
**Good**: "Based on our demo analysis, a multi-channel engagement strategy targeting high-value customer segments shows potential for improved retention. Real-world implementation would require validation with actual business data and may produce different results."

---

## 🔧 **Guardrail Enforcement**

The multi-agent framework includes automated guardrail enforcement:

1. **Input Validation**: All user prompts are scanned for sensitive data before processing
2. **Output Filtering**: Agent responses are checked against guardrail patterns
3. **Context Monitoring**: Conversation history is analyzed for compliance
4. **Audit Logging**: All guardrail violations are logged for review
5. **User Notifications**: Clear warnings when guardrails are approached or violated

---

## 📚 **Additional Resources**

For more information on implementing guardrails in your specific use case:
- Review the demo data repository schema for approved data patterns
- Consult the workflow documentation for guardrail integration points
- Examine sample guardrail-compliant outputs in the demo examples
- Contact framework administrators for custom guardrail configurations

These guardrails ensure that the multi-agent framework operates safely, ethically, and effectively in both demo and production environments while maintaining data privacy and business confidentiality.