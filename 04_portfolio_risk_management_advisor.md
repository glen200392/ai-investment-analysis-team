# Portfolio Risk Management Advisor Agent

## Overview
Portfolio Risk Management Advisor is an AI agent designed to help investors, fund managers and financial advisors quantify and control portfolio risk. Its core purpose is to ingest portfolio holdings and market data, compute advanced risk metrics, run stress and scenario analyses, optimize asset allocation, and deliver actionable recommendations.

## Agent Configuration

**Agent Slug**: `portfolio-risk-management-advisor`

**Agent Type**: Risk Analysis & Portfolio Optimization

**Primary Focus**: Risk Quantification, Stress Testing, Portfolio Optimization

## Key Capabilities

### 1. Risk Metrics Calculation

**Value at Risk (VaR)**:
```
Measures maximum expected loss over time period at confidence level

Methods:
- Historical VaR: Based on historical returns distribution
- Parametric VaR: Assumes normal distribution
- Monte Carlo VaR: Simulates thousands of scenarios

Example: "95% VaR of $50,000 over 1 day"
= 95% confidence that losses won't exceed $50k in one day
```

**Conditional VaR (CVaR / Expected Shortfall)**:
```
Average loss in worst-case scenarios beyond VaR threshold

CVaR > VaR (captures tail risk better)

Example: If 95% VaR = $50k, CVaR might = $75k
= Average loss in worst 5% of scenarios
```

**Volatility & Standard Deviation**:
- Annualized portfolio volatility
- Rolling volatility (30, 60, 90 day)
- Downside deviation (semi-variance)
- Tracking error vs benchmark

**Maximum Drawdown (MDD)**:
```
MDD = (Trough Value - Peak Value) / Peak Value

Measures largest peak-to-trough decline
Example: Portfolio drops from $1M to $700k = -30% MDD
```

**Beta & Correlation**:
- Portfolio beta vs S&P 500
- Correlation matrix between holdings
- Sector concentration risk
- Geographic exposure

**Sharpe Ratio & Sortino Ratio**:
```
Sharpe Ratio = (Portfolio Return - Risk-Free Rate) / Volatility
Sortino Ratio = (Portfolio Return - Risk-Free Rate) / Downside Deviation

Sharpe: Risk-adjusted return (all volatility)
Sortino: Risk-adjusted return (only downside volatility)

Good: Sharpe > 1.0, Sortino > 1.5
Excellent: Sharpe > 2.0, Sortino > 2.5
```

### 2. Stress Testing & Scenario Analysis

**Historical Scenarios**:
- 2008 Financial Crisis (-50% equities)
- 2020 COVID Crash (-35% in 1 month)
- 2022 Tech Selloff (-30% NASDAQ)
- 1987 Black Monday (-22% in 1 day)

**Custom Scenarios**:
- Interest rate shock (+200 bps)
- Taiwan Strait conflict (TSMC -50%, NVDA -30%)
- AI bubble burst (AI stocks -60%)
- Sector-specific crash (semiconductors -40%)

**Sensitivity Analysis**:
- Impact of single position moving ±10%, ±20%, ±30%
- Correlation breakdown scenarios
- Liquidity crisis simulation

### 3. Portfolio Optimization

**Mean-Variance Optimization (Markowitz)**:
```
Maximize: Expected Return - (Risk Aversion × Variance)

Outputs:
- Efficient frontier curve
- Optimal weights for target return
- Minimum variance portfolio
```

**Risk Parity**:
```
Equal risk contribution from each asset
(not equal dollar weights)

Example: 
- 60% Bonds (low vol) + 40% Stocks (high vol)
= Equal risk contribution
```

**Maximum Sharpe Ratio Portfolio**:
```
Find allocation that maximizes:
(Return - Risk-Free Rate) / Volatility

Best risk-adjusted return
```

**Minimum Variance Portfolio**:
```
Lowest possible volatility for any return level

Conservative investors, capital preservation
```

**Black-Litterman Model**:
```
Combines market equilibrium with investor views

Inputs:
- Market cap weights (equilibrium)
- Your views (TSMC +30%, ARM -20%)
- Confidence in views

Output: Optimal allocation incorporating views
```

**Kelly Criterion**:
```
Optimal position size = (p × b - q) / b

where:
p = win probability
q = loss probability (1 - p)
b = win/loss ratio

Example: 60% win prob, 2:1 win/loss ratio
= (0.6 × 2 - 0.4) / 2 = 40% position size
```

### 4. Concentration Risk Analysis

**Position Limits**:
- Single stock max: 10-15%
- Single sector max: 25-30%
- Geographic max: 40-50%

**Herfindahl Index**:
```
HHI = Σ (weight_i)²

HHI = 1.0: Fully concentrated (100% one stock)
HHI = 0.1: Well diversified (10 equal positions)

Target: HHI < 0.2 for diversification
```

**Risk Contribution**:
```
Each position's contribution to total portfolio risk

May differ from weight allocation
(High beta stock = Higher risk contribution)
```

### 5. Liquidity Risk Assessment

**Metrics**:
- Average daily volume vs position size
- Days to liquidate (position / avg volume)
- Bid-ask spread analysis
- Market impact cost estimation

**Stress Scenarios**:
- Normal market: Can exit in 1-3 days
- Stressed market: Exit time doubles
- Crisis: Liquidity evaporates (>10 days)

### 6. Rebalancing Strategies

**Time-Based**:
- Monthly, Quarterly, Annual
- Trade-off: Costs vs drift control

**Threshold-Based**:
- Rebalance when position drifts >5% from target
- More tax-efficient than time-based

**Volatility-Adjusted**:
- Increase equity in low-vol periods
- Reduce equity in high-vol periods

## Available Tools

| Tool | Purpose |
|------|---------|
| `python` | NumPy, pandas, SciPy for calculations, optimization libraries, visualization |

## Problems Solved

✅ Quantifying portfolio risk in multiple dimensions  
✅ Identifying hidden vulnerabilities under stress  
✅ Optimizing asset allocation for risk/return profile  
✅ Producing institutional-grade risk reports  
✅ Making data-driven rebalancing decisions  
✅ Managing tail risk and black swan events  

## Use Cases

### Portfolio Risk Assessment
```
Task: "Analyze my portfolio: 50% TSM, 30% AMD, 20% cash. 
Calculate VaR, max drawdown, and stress test scenarios."

Output:
- 95% VaR (1-day): -$18,500
- 95% VaR (1-month): -$78,000
- Max Drawdown (historical): -32%
- Taiwan Strait Crisis: -$265,000 (-26.5%)
- Sharpe Ratio: 1.85
- Recommendation: Reduce TSM to 40%, increase cash to 30%
```

### Portfolio Optimization
```
Task: "Optimize allocation for $1M portfolio with TSM, AMD, ARM 
targeting 25% annual return with minimal risk."

Output:
- Optimal weights: TSM 55%, AMD 30%, ARM 10%, Cash 5%
- Expected return: 25.3%
- Expected volatility: 18.2%
- Sharpe ratio: 1.92
- Max single position loss: -$82,500 (TSM worst case)
```

### Rebalancing Recommendation
```
Task: "My portfolio drifted from target. Original: TSM 50%, AMD 30%, 
Cash 20%. Current: TSM 60%, AMD 25%, Cash 15%. Should I rebalance?"

Output:
- TSM: 60% → 50% (Sell $100k)
- AMD: 25% → 30% (Buy $50k)
- Cash: 15% → 20% (Add $50k)
- Expected impact: Reduce risk by 3%, minimal return impact
- Tax consideration: Long-term gains on TSM sale
- Recommendation: Rebalance via new contributions if possible
```

## Sample Analysis Output

### Portfolio Risk Report

**Portfolio**: $1,000,000  
**Allocation**: TSM 50%, AMD 30%, ARM 20%

---

**Risk Metrics**:

| Metric | Value | Interpretation |
|--------|-------|----------------|
| Annualized Volatility | 22.4% | High (vs S&P 500: 15%) |
| 95% VaR (1-day) | -$32,100 | Max 1-day loss (95% conf) |
| 95% CVaR (1-day) | -$48,700 | Avg loss in worst 5% days |
| Max Drawdown | -38.2% | Worst peak-to-trough |
| Sharpe Ratio | 1.78 | Good risk-adjusted return |
| Sortino Ratio | 2.45 | Excellent downside protection |
| Beta vs S&P 500 | 1.42 | 42% more volatile than market |

---

**Stress Test Results**:

| Scenario | Portfolio Impact | TSM | AMD | ARM |
|----------|-----------------|-----|-----|-----|
| **2008 Crisis** (-50% stocks) | -$410,000 (-41%) | -50% | -50% | -50% |
| **Taiwan Strait Crisis** | -$265,000 (-26.5%) | -50% | -10% | -5% |
| **AI Bubble Burst** | -$380,000 (-38%) | -40% | -45% | -30% |
| **Tech Sector Crash** | -$350,000 (-35%) | -40% | -40% | -25% |
| **Interest Rate +200bps** | -$120,000 (-12%) | -15% | -10% | -8% |

**Worst Case (Taiwan Crisis)**: -26.5%  
**Probability**: 10-15% over next 12 months

---

**Concentration Risk**:

| Risk Type | Current | Target | Status |
|-----------|---------|--------|--------|
| Single Stock (TSM) | 50% | <40% | ⚠️ Overweight |
| Sector (Semiconductors) | 80% | <60% | 🔴 High Risk |
| Geography (Taiwan) | 50% | <30% | 🔴 High Risk |
| Liquidity Risk | Low | Low | ✅ OK |

**HHI (Concentration)**: 0.38 (Moderately concentrated)

---

**Correlation Matrix**:

|     | TSM | AMD | ARM |
|-----|-----|-----|-----|
| TSM | 1.00 | 0.72 | 0.65 |
| AMD | 0.72 | 1.00 | 0.68 |
| ARM | 0.65 | 0.68 | 1.00 |

**Analysis**: High correlation (0.65-0.72) = Limited diversification benefit

---

**Recommendations**:

🔴 **Critical**:
1. **Reduce TSM to 40%** (Sell $100k)
   - Rationale: Single-stock concentration risk
   - Taiwan geopolitical exposure too high
   
2. **Increase Cash to 30%** (Add $100k from TSM sale)
   - Rationale: Stress test shows -26% to -41% losses
   - Cash buffer for crisis opportunities

⚠️ **Important**:
3. **Add non-correlated assets**
   - Consider: ASML (Europe), Micron (memory)
   - Target: Reduce portfolio correlation

✅ **Optional**:
4. **Set up hedging strategy**
   - Put options on TSM (5% of position)
   - Cost: ~2% annually, limits downside to -15%

---

**Optimized Allocation** (Target Return: 25%, Lower Risk):

| Asset | Current | Optimal | Change |
|-------|---------|---------|--------|
| TSM | 50% | 40% | -10% |
| AMD | 30% | 30% | 0% |
| ARM | 20% | 10% | -10% |
| Cash | 0% | 20% | +20% |

**Expected Outcomes**:
- Return: 24.8% (vs 26.2% current)
- Volatility: 18.5% (vs 22.4% current)
- Sharpe Ratio: 2.05 (vs 1.78 current)
- Max Drawdown: -28% (vs -38% current)

**Trade-off**: Sacrifice 1.4% return for 26% less risk

## Best Practices

### When to Use
✅ Before deploying significant capital  
✅ After major market moves (reassess risk)  
✅ Portfolio review (quarterly minimum)  
✅ Before adding leverage  
✅ When concentration exceeds limits  

### When NOT to Use
❌ Intraday trading (too short-term)  
❌ Fully diversified index funds (limited optimization value)  
❌ Illiquid alternative investments (metrics less reliable)  

## Common Mistakes to Avoid

❌ **Ignoring Tail Risk**: VaR only tells part of story (use CVaR)  
❌ **Over-diversification**: 50+ stocks = Index returns with higher costs  
❌ **Assuming Normal Distribution**: Markets have fat tails  
❌ **Static Allocation**: Risk changes, rebalance regularly  
❌ **Forgetting Correlation**: Diversification fails in crisis (correlations → 1)  

## Integration with Other Agents

| Agent | Purpose | Workflow |
|-------|---------|----------|
| **Fundamental Analysis** | Position sizing | 1. Fundamental: Quality score<br>2. Risk Management: Allocate capital |
| **Technical Analysis** | Entry timing | 1. Risk Management: Target allocation<br>2. Technical: Time entries |
| **Investment Report Coordinator** | Final synthesis | 1. Risk Management: Risk constraints<br>2. Coordinator: Implement |

## Version History

- **v1.0** (2026-01-29): Initial deployment
- Focus: U.S. and Taiwan equity portfolios

---

**Created**: 2026-01-29  
**Last Updated**: 2026-01-29  
**Status**: Production Ready ✅
