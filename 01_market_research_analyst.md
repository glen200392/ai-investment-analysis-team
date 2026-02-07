# Market Research Analyst Agent

## Overview
Market Research Analyst is an AI agent specialized in U.S. and Taiwan equity markets. Its core purpose is to cut through information overload by continuously gathering, analyzing and synthesizing economic data, news and sentiment into clear, actionable intelligence for traders, portfolio managers and financial professionals.

## Agent Configuration

**Agent Slug**: `market-research-analyst`

**Agent Type**: Research & Analysis

**Primary Focus**: Market Intelligence, Industry Analysis, News Aggregation

## Key Capabilities

### 1. Real-time Data Aggregation
- Bloomberg, Reuters, CNBC (U.S. markets)
- 鉅亨網, 工商時報 (Taiwan markets)
- SEC filings and regulatory announcements
- Company press releases and earnings calls

### 2. Macroeconomic Analysis
- GDP growth and economic indicators
- Inflation trends (CPI, PPI, PCE)
- Interest rate environment and Fed policy
- Employment data and labor market conditions
- Central bank policy analysis (Fed, ECB, BoJ)

### 3. Sector & Industry Analysis
- Technology sector trends (AI, semiconductors, cloud)
- Financial sector health (banking, fintech)
- Manufacturing and supply chain dynamics
- Consumer behavior and retail trends

### 4. Sentiment Analysis
- News headline sentiment scoring
- Social media signal processing
- Institutional positioning analysis
- Retail investor sentiment tracking

### 5. Event Impact Assessment
- Earnings release analysis
- Policy change implications
- Geopolitical event impact
- M&A and corporate action effects

### 6. Automated Report Generation
- Python-powered data visualization
- Statistical summaries and trend analysis
- Cross-market comparisons (U.S. vs Taiwan)
- Industry benchmark reports

## Available Tools

| Tool | Purpose |
|------|---------|
| `web_search` | Fresh market news and developments |
| `web_scrape` | Article text and data table extraction |
| `python` | Data processing, visualization, sentiment analysis |
| `bash` | File and system operations |

## Problems Solved

✅ Information overload across multiple markets  
✅ Slow manual data processing and reporting  
✅ Lack of timely, structured market insights  
✅ Difficulty correlating U.S. and Taiwan market movements  
✅ Fragmented news sources requiring manual aggregation

## Use Cases

### Daily Market Brief
```
Task: "Generate today's market brief covering U.S. and Taiwan equity markets, 
highlighting key movers, economic data releases, and sector trends."

Output: Structured report with:
- Market overview (indices, volume, breadth)
- Top gainers/losers with catalyst analysis
- Economic data interpretation
- Sector rotation analysis
- Tomorrow's key events
```

### Industry Deep Dive
```
Task: "Analyze the AI hardware industry - chips, servers, cooling, power, 
and networking equipment. Identify recent catalysts and growth trends."

Output: Comprehensive report with:
- Value chain breakdown
- Major players and market share
- Recent earnings and announcements
- Supply chain bottlenecks
- Growth forecasts and TAM analysis
```

### Event Impact Analysis
```
Task: "Assess the impact of NVIDIA's latest earnings report on the 
semiconductor supply chain in Taiwan."

Output: Detailed analysis of:
- NVIDIA earnings key metrics
- Implications for TSMC, ASE, and suppliers
- Order visibility and capacity utilization
- Stock price reaction and analyst revisions
```

## Sample Workflow

**Input**: "Research AI hardware industry and recent catalysts"

**Process**:
1. Web search for recent news (NVIDIA, AMD, TSMC, ASML)
2. Extract key data points (earnings, orders, capacity)
3. Analyze trends and identify catalysts
4. Generate visualizations (charts, tables)
5. Synthesize into executive summary

**Output**: 
- 26KB industry research report
- 5 professional visualizations
- Catalyst timeline calendar
- Investment opportunity matrix

## Integration with Other Agents

Market Research Analyst works best when combined with:

| Agent | Purpose | Workflow |
|-------|---------|----------|
| **Technical Analysis Expert** | Chart patterns and momentum | 1. Market Research identifies catalysts<br>2. Technical Analysis confirms entry timing |
| **Fundamental Analysis Advisor** | Financial health validation | 1. Market Research screens opportunities<br>2. Fundamental validates with DCF/ratios |
| **Investment Report Coordinator** | Synthesis and final recommendations | 1. Market Research provides context<br>2. Coordinator integrates all analyses |

## Performance Metrics

**Speed**: 
- Daily brief generation: 2-3 minutes
- Industry deep dive: 10-15 minutes
- Event impact analysis: 5-7 minutes

**Accuracy**:
- Data sourcing: Official sources + tier-1 financial media
- Citation: All data points traceable to source
- Timeliness: Real-time news aggregation within 5 minutes

**Coverage**:
- U.S. markets: S&P 500, NASDAQ, major sectors
- Taiwan markets: TAIEX, semiconductor supply chain
- Global macro: Fed, ECB, BoJ policy

## Best Practices

### When to Use
✅ Starting a new research project (gather context first)  
✅ Daily market monitoring routines  
✅ Event-driven research (earnings, policy changes)  
✅ Industry trend analysis  
✅ Competitor intelligence gathering  

### When NOT to Use
❌ Pure technical analysis (use Technical Analysis Expert)  
❌ Financial modeling (use Fundamental Analysis Advisor)  
❌ Portfolio optimization (use Portfolio Risk Management Advisor)  
❌ Trade execution decisions (need combined analysis)

### Optimization Tips

1. **Be Specific**: "AI hardware industry in Taiwan" > "tech stocks"
2. **Time Bounds**: "Last 30 days" > "recent" 
3. **Scope**: Define geographic focus (U.S. vs Taiwan vs global)
4. **Output Format**: Specify desired deliverable (brief, deep dive, chart)

## Example Prompts

### Excellent Prompts ✅
```
"Research the AI hardware industry supply chain. Focus on semiconductors, 
advanced packaging (CoWoS), HBM memory, and cooling systems. Identify 
bottlenecks, major players, recent earnings, and Q1 2026 catalysts. 
Generate visualizations for capacity allocation and market forecasts."
```

### Poor Prompts ❌
```
"Tell me about tech stocks"
(Too vague - no industry, geography, or time frame specified)
```

## Output Quality

### Data Sourcing
- ✅ Primary sources: Company filings, earnings calls
- ✅ Secondary sources: Bloomberg, Reuters, industry reports
- ✅ All data points time-stamped and cited

### Analysis Depth
- Executive summary (2-3 paragraphs)
- Detailed findings (5-10 key points)
- Supporting data (tables, charts)
- Implications and outlook

### Professional Standards
- Objective tone (no hype or fear-mongering)
- Transparent methodology
- Clear distinction between facts and analysis
- Actionable insights prioritized

## Limitations

⚠️ **Not Financial Advice**: Provides research, not investment recommendations  
⚠️ **Historical Data**: Analysis based on past/present, not predictive  
⚠️ **Scope**: Does not perform technical analysis or financial modeling  
⚠️ **Coverage**: Strongest in U.S. and Taiwan markets; limited emerging markets  

## Version History

- **v1.0** (2026-01-29): Initial deployment with U.S. and Taiwan market coverage
- Focus areas: AI hardware, semiconductors, technology sector

## Contributing

To enhance Market Research Analyst capabilities:
1. Add new data sources (financial APIs, news feeds)
2. Expand geographic coverage (Europe, Asia)
3. Improve sentiment analysis algorithms
4. Add real-time alert functionality

---

**Created**: 2026-01-29  
**Last Updated**: 2026-01-29  
**Status**: Production Ready ✅
