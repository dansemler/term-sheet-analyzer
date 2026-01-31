# VC Term Sheet Analyzer

An interactive tool for analyzing venture capital term sheets, comparing nominal vs. effective valuations, and understanding how liquidation preferences, participation rights, and other provisions impact founder economics.

## Why This Tool Exists

When founders negotiate term sheets, headline valuations can be misleading. A "$20M pre-money valuation" might actually imply a much lower effective valuation once you account for liquidation preferences, participation rights, and cumulative dividends.

This tool makes these hidden economics visible—helping founders, advisors, lawyers, and board members understand what a term sheet *actually* means at different exit scenarios.

## Features

### Full Analysis
- Input any term sheet parameters (investment, valuation, preferences, participation)
- See real-time calculations of nominal vs. effective valuations
- Visualize payout distributions across exit values
- Understand key thresholds like indifference value

### Compare Term Sheets
- Side-by-side comparison of two different term sheets
- See which structure favors founders at any given exit value
- Identify crossover points where one deal becomes better than another

### Scenario Analysis
- Model probability-weighted exit scenarios (upside, base, downside)
- Calculate expected value for founders under each structure
- **Value Transfer metric**: See how much $ flows from founders to VCs beyond their nominal ownership percentage
- Compare structures to pick the most favorable terms

### Sensitivity Analysis
- See how founder outcomes change across a range of exit multiples
- Export data to CSV for further analysis
- Visualize effective valuation as a percentage of nominal valuation

## Key Concepts

| Term | Definition |
|------|------------|
| **Nominal Valuation** | The headline pre-money/post-money based on simple ownership percentage |
| **Effective Valuation** | The actual implied valuation accounting for preferences and participation |
| **Liquidation Preference** | Amount investors receive before common shareholders (e.g., 2x on $5M = $10M paid first) |
| **Participating Preferred** | "Double dip" — investor gets preference PLUS pro-rata share of remaining proceeds |
| **Non-Participating** | Investor chooses preference OR conversion to common, not both (more founder-friendly) |
| **Indifference Value** | Exit value where VC is indifferent between taking preference or converting |
| **Value Transfer** | Amount VC receives beyond their nominal pro-rata ownership share |

## The Math

Based on formulas from Woronoff & Rosen's paper "Effective vs. Nominal Valuations in Venture Capital Investing":

**Nominal Valuation:**
- Post-Money = Investment ÷ VC Ownership %
- Pre-Money = Post-Money − Investment

**Effective Valuation:**
- Effective Post-Money = Investment ÷ (VC Payout ÷ Exit Value)
- Effective Pre-Money = Effective Post-Money − Investment

**Indifference Value:**
- Indifference = Total Liquidation Preference ÷ VC Ownership %

## Quick Start

1. Download `vc-term-sheet-analyzer.html`
2. Open in any modern web browser
3. No installation or server required—it's fully self-contained

## Deployment

### GitHub Pages
```bash
# Create a new repo, add the HTML file, then:
git add vc-term-sheet-analyzer.html
git commit -m "Add VC term sheet analyzer"
git push origin main
# Enable GitHub Pages in repo Settings > Pages
```

### Netlify
1. Go to [netlify.com](https://netlify.com)
2. Drag and drop the HTML file
3. Get your public URL instantly

## Example: Why This Matters

Consider two term sheets for a $10M investment at $40M pre-money ($50M post, 20% VC ownership):

| Structure | Terms |
|-----------|-------|
| **A** | 1x non-participating preferred |
| **B** | 2x participating preferred |

At a $100M exit:
- **Structure A**: Founder receives $80M (80%)
- **Structure B**: Founder receives $64M (64%)

The "same" $40M pre-money valuation yields **$16M less** for founders under the participating structure.

Using probability-weighted scenarios (20% upside, 50% base, 30% downside), Structure A delivers **$84M expected value** vs. **$68M for Structure B**—a $16M difference that's invisible in the headline valuation.

## Tech Stack

- Vanilla JavaScript (no framework dependencies)
- [Chart.js](https://www.chartjs.org/) for visualizations
- [Tailwind CSS](https://tailwindcss.com/) for styling
- Fully client-side (no server required)

## Contributing

Contributions welcome! Some ideas for enhancements:
- Additional preference structures (e.g., capped participation, senior/junior tranches)
- Multiple investor rounds with different terms
- Option pool impact modeling
- Anti-dilution provision analysis

## License

MIT License — free to use, modify, and distribute.

## Acknowledgments

Based on the framework from "Effective vs. Nominal Valuations in Venture Capital Investing" by Victor Woronoff and Mark Rosen.

---

*Built to help founders understand what they're actually signing.*
