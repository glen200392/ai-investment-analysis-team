# Investment Report Coordinator Agent

## Overview
The Investment Report Coordinator is an AI agent designed to unify fragmented analyses into coherent, actionable investment reports. It supports investment professionals, portfolio managers and research teams through an end-to-end workflow—from initial inquiry through market research, technical & fundamental analysis, risk assessment and final recommendations.

## Agent Configuration

**Agent Slug**: `investment-report-coordinator`

**Agent Type**: Analysis Synthesis & Report Generation

**Primary Focus**: Multi-Source Integration, Decision Framework, Investment Recommendations

## Key Capabilities

### 1. Multi-Dimensional Analysis Integration

**Four Pillars of Analysis**:
```
1. Market Research (30% weight)
   - Industry trends and catalysts
   - Competitive landscape
   - News and sentiment
   
2. Technical Analysis (40% weight for short-term)
   - Chart patterns and momentum
   - Entry/exit timing
   - Support/resistance levels
   
3. Fundamental Analysis (20% weight for short-term)
   - Financial health and valuation
   - Intrinsic value calculation
   - Quality assessment
   
4. Risk Management (10% weight)
   - Portfolio risk metrics
   - Stress testing
   - Position sizing
```

**Adaptive Weighting**:
- **Short-term (1-3 months)**: Technical 40%, Catalysts 30%, Fundamental 20%, Risk 10%
- **Medium-term (6-12 months)**: Fundamental 35%, Technical 25%, Catalysts 25%, Risk 15%
- **Long-term (2+ years)**: Fundamental 50%, Catalysts 20%, Technical 10%, Risk 20%

### 2. Conflict Resolution Framework

**When Dimensions Disagree**:

**Example: Technical Bullish vs Fundamental Bearish**
```
TSM: Technical 10/10, Fundamental 9.5/10 → No conflict, STRONG BUY
AMD: Technical 8/10, Fundamental 7.5/10 → Aligned, BUY
ARM: Technical 7/10, Fundamental 6.5/10 → Weak both, HOLD/AVOID

Resolution Logic:
- Both Strong (≥8): STRONG BUY
- Both Good (≥7): BUY
- Mixed (one ≥8, one ≤6): Lower position size, strict stop-loss
- Both Weak (≤6): AVOID
```

**Conflict Handling Table**:

| Technical | Fundamental | Decision | Position Size | Stop-Loss |
|-----------|-------------|----------|---------------|-----------|
| Strong (8+) | Strong (8+) | STRONG BUY | 40-60% | Normal (-10%) |
| Strong (8+) | Weak (≤6) | BUY (reduced) | 20-30% | Tight (-5%) |
| Weak (≤6) | Strong (8+) | HOLD (wait for technical) | 0-10% | Very tight (-3%) |
| Weak (≤6) | Weak (≤6) | AVOID | 0% | N/A |

### 3. Investment Report Generation

**Executive Summary** (1 page):
- Three-sentence investment thesis
- Target price and expected return
- Key risks and catalysts
- Recommendation (Strong Buy/Buy/Hold/Sell)

**Detailed Analysis** (5-10 pages):
- Market context and industry trends
- Technical analysis with charts
- Fundamental valuation and quality
- Risk assessment and scenarios
- Competitive comparison

**Appendix**:
- Financial statements
- Calculation details (DCF, ratios)
- Data sources and methodology
- Disclaimer and disclosures

### 4. Scenario Planning

**Three-Scenario Framework**:

**Bull Case** (30% probability):
- Best-case assumptions
- Catalysts materialize fully
- Technical breakout confirmed
- Upside potential: +40% to +60%

**Base Case** (50% probability):
- Realistic assumptions
- Some catalysts materialize
- Technical trend continues
- Upside potential: +20% to +30%

**Bear Case** (20% probability):
- Conservative assumptions
- Catalysts fail or delayed
- Technical breakdown
- Downside risk: -10% to -20%

**Probability-Weighted Expected Return**:
```
Expected Return = (0.3 × Bull) + (0.5 × Base) + (0.2 × Bear)

Example:
Bull: +50%, Base: +25%, Bear: -15%
Expected = (0.3 × 50) + (0.5 × 25) + (0.2 × -15)
        = 15 + 12.5 - 3
        = 24.5%
```

### 5. Action Plan & Monitoring

**Entry Strategy**:
- Immediate entry levels
- Pullback entry levels
- Breakout chase levels
- Position building plan (tranches)

**Exit Strategy**:
- Target prices (T1, T2, T3)
- Stop-loss levels (hard stop, trailing stop)
- Time-based exit (if thesis invalidates)
- Partial profit-taking plan

**Monitoring Checklist**:
- Daily: Price vs moving averages, volume
- Weekly: Technical pattern integrity
- Monthly: Earnings updates, guidance changes
- Quarterly: Full fundamental review

**Trigger Events**:
- Earnings reports (dates and expectations)
- Product launches
- Regulatory decisions
- Macroeconomic data releases

### 6. Comparative Analysis

**Stock Ranking Matrix**:

| Rank | Ticker | Technical | Fundamental | Catalysts | Risk | Total | Recommendation |
|------|--------|-----------|-------------|-----------|------|-------|----------------|
| 🥇 | TSM | 10/10 | 9.5/10 | 9/10 | 9/10 | 9.45 | STRONG BUY |
| 🥈 | AMD | 8/10 | 7.5/10 | 8/10 | 7/10 | 7.90 | BUY |
| 🥉 | ARM | 7/10 | 6.5/10 | 7/10 | 6/10 | 6.60 | HOLD |

**Selection Criteria**:
- Total score ≥8.5: Portfolio core (40-60%)
- Total score 7.5-8.5: Satellite holding (20-40%)
- Total score 6.5-7.5: Optional/tactical (0-20%)
- Total score <6.5: Avoid

## Available Tools

| Tool | Purpose |
|------|---------|
| `python` | Data synthesis, visualization, portfolio modeling |
| `web_search` | Latest market data and news verification |
| `web_scrape` | Real-time price and financial data |

## Problems Solved

✅ Eliminating siloed research (integrate multiple analyses)  
✅ Resolving conflicts between technical and fundamental views  
✅ Automating comprehensive report generation  
✅ Providing clear, actionable recommendations  
✅ Creating transparent decision frameworks  
✅ Producing presentation-ready deliverables  

## Use Cases

### Comprehensive Investment Report
```
Task: "Generate full investment report on TSMC with 1-month 30% 
target. Include market research, technical analysis, fundamentals, 
risk assessment, and final recommendation."

Output:
- 28KB integrated report
- Executive summary (3 paragraphs)
- Technical score: 10/10
- Fundamental score: 9.5/10
- Recommendation: STRONG BUY
- Position size: 50-60%
- Entry: $337-342
- Target: $445 (+30%)
- Stop-loss: $333 (-2.7%)
- 30-day success probability: 85%
```

### Comparative Analysis
```
Task: "Compare TSM, AMD, and ARM for best 30-day 30% opportunity. 
Rank by probability of success."

Output: Ranking table
| Rank | Stock | Score | Probability | Recommendation |
|------|-------|-------|-------------|----------------|
| 1 | TSM | 9.45/10 | 85% | STRONG BUY (50-60%) |
| 2 | AMD | 7.90/10 | 65% | BUY (30-40%) |
| 3 | ARM | 6.60/10 | 35% | AVOID (0%) |

Portfolio allocation: TSM 60%, AMD 30%, Cash 10%
```

### Portfolio Construction
```
Task: "Build optimized $1M portfolio for 25% return in 6 months 
using AI hardware stocks."

Output:
- Allocation: TSM 50%, AMD 30%, ASML 15%, Cash 5%
- Expected return: 26.3%
- Expected volatility: 18.7%
- Sharpe ratio: 1.92
- Max drawdown: -22%
- Key catalysts: NVIDIA earnings (2/26), AMD Q4 (2/3)
```

## Sample Output: Integrated Investment Report

### Executive Summary

**Investment Thesis (3 Sentences)**:
TSMC is the ultimate AI infrastructure beneficiary with monopolistic control of advanced logic manufacturing and CoWoS packaging, trading at reasonable 22x forward P/E despite 48% EPS growth and industry-leading 48% net margins. Technical setup is perfect (10/10) with bull flag breakout, multi-timeframe alignment, and strong momentum indicators signaling imminent move to $445 (+30%). With 2-year CoWoS backlog, NVIDIA H200/B200 ramp, and AI capex boom providing rock-solid catalysts, we assign STRONG BUY with 85% probability of achieving 30% return within 30 days.

**Recommendation**: ⭐⭐⭐⭐⭐ STRONG BUY

**Target Price**: $445 (+30% from $342)  
**Time Horizon**: 30 days  
**Success Probability**: 85%  
**Position Size**: 50-60% of portfolio

---

### Integrated Scoring Matrix

| Dimension | Score | Weight | Weighted |
|-----------|-------|--------|----------|
| Technical Analysis | 10.0/10 | 40% | 4.00 |
| Fundamental Analysis | 9.5/10 | 20% | 1.90 |
| Market Catalysts | 9.0/10 | 30% | 2.70 |
| Risk Management | 9.0/10 | 10% | 0.90 |
| **TOTAL** | **9.45/10** | **100%** | **9.50** |

**Interpretation**: Exceptional score (>9.0) across all dimensions = Highest conviction

---

### Three-Scenario Analysis

| Scenario | Probability | Price Target | Return | Key Assumptions |
|----------|------------|--------------|--------|-----------------|
| **Bull** | 30% | $480 | +40% | NVIDIA earnings blowout, CoWoS shortage intensifies |
| **Base** | 50% | $420 | +23% | Steady AI demand, no geopolitical shocks |
| **Bear** | 20% | $320 | -6.5% | Taiwan tensions, AI capex slowdown |

**Expected Return** (probability-weighted): **+24.3%**

---

### Action Plan

**Week 1 (Jan 29 - Feb 4)**:
- ✅ Immediate entry: 40% position @ $337-342
- Monitor: AMD Q4 earnings (Feb 3)

**Week 2 (Feb 5 - Feb 11)**:
- Add 30%: On pullback to $327-330
- Monitor: TSM Q1 revenue preview

**Week 3 (Feb 12 - Feb 18)**:
- Add 30%: On breakout above $346
- Monitor: Technical pattern confirmation

**Week 4 (Feb 19 - Feb 28)**:
- 🔔 NVIDIA Earnings (Feb 26): CRITICAL CATALYST
- If target achieved: Scale out 50% @ $420, 50% @ $445
- If thesis breaks: Stop-loss @ $333

---

### Risk Management

**Stop-Loss**: $333 (-2.7%)  
**Max Portfolio Loss**: -1.6% (assuming 60% position)  
**Risk/Reward Ratio**: 1:11.1 (excellent)

**Key Risks**:
1. 🔴 Taiwan Strait conflict (-50% scenario)
2. ⚠️ NVIDIA earnings disappoint
3. ⚠️ AI capex slowdown

**Mitigation**:
- Diversify with U.S.-listed AMD (30%)
- Keep 10% cash for crisis
- Set automatic stop-loss orders

---

### Monitoring Checklist

**Daily**:
- [ ] Price above MA20 ($339)?
- [ ] RSI remains 50-70?
- [ ] Volume confirms moves?

**Weekly**:
- [ ] Bull flag pattern intact?
- [ ] No bearish divergence?
- [ ] News flow positive?

**Event-Driven**:
- [ ] Feb 3: AMD earnings (proxy for AI demand)
- [ ] Feb 12: TSM Q1 revenue preview
- [ ] Feb 26: NVIDIA earnings (CRITICAL)

**Exit Triggers**:
- ✅ Price hits $445 → Full exit
- ✅ Price hits $420 → 50% profit-taking
- ❌ Price breaks $333 → Stop-loss exit
- ❌ NVIDIA earnings disappoint → Reassess

## Best Practices

### When to Use
✅ Complex investment decisions requiring multiple analyses  
✅ Client-facing investment reports  
✅ Portfolio strategy review  
✅ Team research synthesis  
✅ High-stakes capital deployment  

### When NOT to Use
❌ Simple buy/hold index fund decisions  
❌ Purely technical day trading  
❌ Automated trading strategies  

## Integration Workflow

**Sequential Pipeline**:
```
1. Market Research Analyst
   ↓ (Industry context, catalysts)
   
2. Technical Analysis Expert
   ↓ (Entry timing, momentum)
   
3. Fundamental Analysis Advisor
   ↓ (Valuation, quality)
   
4. Portfolio Risk Management Advisor
   ↓ (Risk metrics, position size)
   
5. Investment Report Coordinator
   ↓ (Synthesis, recommendation)
   
→ Final Investment Report
```

**Parallel Execution** (Faster):
```
Market Research ──┐
Technical Analysis ─┤
Fundamental Analysis ─┼→ Investment Report Coordinator → Final Report
Risk Management ──┘
```

## Output Quality Standards

### Transparency
- ✅ All data sources cited
- ✅ Calculation methodology explained
- ✅ Assumptions stated explicitly
- ✅ Conflicts disclosed

### Actionability
- ✅ Clear buy/sell/hold recommendation
- ✅ Specific entry and exit prices
- ✅ Position sizing guidance
- ✅ Timeline with key dates

### Professional Standards
- ✅ Objective tone (no hype)
- ✅ Risk-balanced (acknowledge downsides)
- ✅ Presentation-ready formatting
- ✅ Executive summary for decision-makers

## Version History

- **v1.0** (2026-01-29): Initial deployment
- Focus: AI hardware equity analysis (U.S. & Taiwan)

---

**Created**: 2026-01-29  
**Last Updated**: 2026-01-29  
**Status**: Production Ready ✅
