# Awesome Options Analytics [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of tools, libraries, data providers, and resources for options analytics, volatility research, and derivatives trading. Inspired by the [awesome](https://github.com/sindresorhus/awesome) project.

Options analytics spans a wide problem space: computing and interpreting options greeks (delta, gamma, theta, vega, vanna, charm), modeling the implied volatility surface and volatility smile, calculating gamma exposure (GEX) and dealer positioning to understand market microstructure, analyzing 0DTE and intraday options flow, fitting stochastic volatility models such as Heston and SABR, and applying systematic risk and position-sizing frameworks like the Kelly Criterion. This list collects the tools, data providers, libraries, papers, and communities relevant to each of these areas.

Contributions welcome. See [Contributing](#contributing).

---

## Contents

- [APIs and Data Providers](#apis-and-data-providers)
- [Python Libraries](#python-libraries)
- [Options Pricing and Greeks](#options-pricing-and-greeks)
- [Volatility Analysis](#volatility-analysis)
- [Gamma Exposure (GEX)](#gamma-exposure-gex)
- [Dealer Positioning and Market Microstructure](#dealer-positioning-and-market-microstructure)
- [0DTE and Intraday Options](#0dte-and-intraday-options)
- [Kelly Criterion and Position Sizing](#kelly-criterion-and-position-sizing)
- [Options Screeners](#options-screeners)
- [Open Source Projects](#open-source-projects)
- [Educational Resources](#educational-resources)
- [Communities](#communities)
- [Market Data Sources](#market-data-sources)
- [Contributing](#contributing)

---

## APIs and Data Providers

- [FlashAlpha](https://flashalpha.com) - Options analytics API providing a live options screener (filter/rank by GEX, VRP, IV, greeks, harvest scores, and custom formulas), GEX (gamma exposure), DEX (delta exposure), VEX (vanna exposure), CHEX (charm exposure), full greeks, open interest, 0DTE analytics, and AI-powered narrative analysis across equities and indices. Offers REST endpoints and SDKs in Python, JavaScript, .NET, Java, Go, plus an MCP server.
- [CBOE DataShop](https://datashop.cboe.com) - Historical and real-time options data directly from the exchange, including VIX data, settlement prices, and implied volatility indexes.
- [Helium MCP](https://heliumtrades.com/mcp-page/) ([GitHub](https://github.com/connerlambden/helium-mcp)) - AI-powered options analytics via MCP server — proprietary ML models for options fair value pricing, probability ITM calculations, top-ranked trading strategies with risk/reward analysis, and live stock/ETF/crypto data with AI-generated bull/bear cases. Also includes news bias scoring across 5,000+ sources. 9 tools, 50 free queries, no signup.
- [OptionMetrics](https://optionmetrics.com) - Academic and institutional-grade historical options data (IvyDB), widely used in finance research for implied volatility surfaces and standardized greeks.
- [ORATS](https://orats.com) - Options data API with earnings forecasts, volatility surface data, backtesting tools, and historical greeks.
- [Polygon.io](https://polygon.io/docs/options) - Real-time and historical options data REST and WebSocket API. Aggregates, trades, quotes, and snapshots for US equity options.
- [Tradier](https://developer.tradier.com) - Brokerage API with options chains, greeks, market data, and order management. Free sandbox tier available.
- [Schwab Developer (formerly TD Ameritrade)](https://developer.schwab.com) - Options chain API with greeks, implied volatility, and real-time quotes for TD/Schwab account holders.
- [Interactive Brokers API](https://interactivebrokers.github.io) - TWS API and Client Portal API providing options data, greeks, and order routing for IB account holders.
- [Alpaca Markets](https://alpaca.markets/docs/api-references/market-data-api/option-data/) - Options market data and trading API with free and paid tiers.
- [Market Data App](https://api.marketdata.app) - Options chain and historical data API with a generous free tier.

## Python Libraries

- [flashalpha](https://pypi.org/project/flashalpha/) - Official Python client for the FlashAlpha API. Provides convenient access to GEX, DEX, VEX, greeks, OI data, and narrative analysis with pandas integration.
- [QuantLib-Python](https://pypi.org/project/QuantLib/) - Python bindings for the QuantLib quantitative finance library. Covers a wide range of pricing models, term structures, and volatility surfaces.
- [py_vollib](https://pypi.org/project/py_vollib/) - Fast Black-Scholes, Black-76, and implied volatility calculations using LetsBeRational under the hood.
- [py_vollib_vectorized](https://pypi.org/project/py_vollib_vectorized/) - Vectorized (NumPy-compatible) wrapper around py_vollib for high-throughput greeks computation.
- [mibian](https://pypi.org/project/mibian/) - Options pricing library for Black-Scholes, Merton, Garman-Kohlhagen, and related models.
- [options](https://pypi.org/project/options/) - Lightweight library for options pricing and greeks computation.
- [yfinance](https://pypi.org/project/yfinance/) - Yahoo Finance market data downloader. Includes options chains with basic greeks and implied volatility.
- [pandas-ta](https://pypi.org/project/pandas-ta/) - Technical analysis library built on pandas, useful for computing realized volatility and volatility-related indicators on underlying price series.
- [pydantic-settings](https://pypi.org/project/pydantic-settings/) - Commonly used for configuration management in options analytics pipelines.
- [arch](https://pypi.org/project/arch/) - Autoregressive conditional heteroskedasticity (ARCH/GARCH) models for realized volatility and volatility forecasting.
- [scipy](https://pypi.org/project/scipy/) - Foundational scientific computing library used extensively for numerical options pricing and optimization.

## Options Pricing and Greeks

### Black-Scholes and Analytical Models

- [py_vollib](https://pypi.org/project/py_vollib/) - Implements Black-Scholes and Black-76 with fast implied volatility solving via LetsBeRational.
- [QuantLib](https://www.quantlib.org) - Comprehensive C++ library (with Python bindings) covering Black-Scholes-Merton, analytical barrier options, Asian options, and more.
- [black-scholes-rs](https://github.com/hayden4r4/black-scholes-rust) - Rust implementation of Black-Scholes with Python bindings via PyO3, designed for performance-critical greeks computation.

### Binomial and Lattice Models

- [QuantLib](https://www.quantlib.org) - Includes CRR (Cox-Ross-Rubinstein), Jarrow-Rudd, and other lattice models for American-style options pricing.

### Monte Carlo Pricing

- [QuantLib](https://www.quantlib.org) - Provides Monte Carlo engines for path-dependent options and exotic derivatives.
- [finmc](https://pypi.org/project/finmc/) - Fast Monte Carlo simulation framework for financial derivatives pricing.

### Implied Volatility Solvers

- [LetsBeRational](http://www.jaeckel.org/LetsBeRational.pdf) - Peter Jaeckel's near-exact rational function approximation for Black-Scholes implied volatility (paper and reference implementation).
- [py_vollib](https://pypi.org/project/py_vollib/) - Wraps LetsBeRational for production-grade IV solving.

## Volatility Analysis

### Volatility Surface and Smile

- [QuantLib](https://www.quantlib.org) - Supports SVI parameterization, SABR model calibration, and volatility surface interpolation.
- [pysabr](https://github.com/ynouri/pysabr) - Python implementation of the SABR (Stochastic Alpha Beta Rho) volatility model, widely used for vol smile interpolation.
- [ssvi](https://github.com/vpatryshev/ssvi) - Surface SVI (SSVI) implementation for arbitrage-free volatility surface parameterization.
- [volatility-surface](https://github.com/cantaro86/Financial-Models-Numerical-Methods) - Jupyter notebooks covering vol surface construction and SVI calibration from the book "Financial Models with Numerical Methods."

### Realized Volatility

- [arch](https://pypi.org/project/arch/) - GARCH-family models for realized and forecasted volatility. Supports EGARCH, TARCH, and HAR-RV.
- [realized](https://realized.oxford-man.ox.ac.uk) - Oxford-Man Institute Realized Library: daily realized volatility measures for major indices.
- [pandas-ta](https://pypi.org/project/pandas-ta/) - Includes Garman-Klass, Parkinson, Rogers-Satchell, and Yang-Zhang realized volatility estimators.

### VIX and Variance

- [CBOE VIX Methodology](https://www.cboe.com/tradable_products/vix/vix_whitepapers/) - Official CBOE white paper on VIX calculation methodology.
- [vixcentral.com](http://vixcentral.com) - VIX futures term structure visualization tool, updated daily.

## Gamma Exposure (GEX)

Gamma Exposure (GEX) measures the aggregate gamma held by market makers on a given underlying, used to infer dealer hedging flows and potential pinning or amplification effects on price.

### References and Methodology

- [gex-explained](https://github.com/FlashAlpha-lab/gex-explained) - Explains GEX from first principles: the formula, dealer hedging regimes (positive vs negative gamma), the gamma flip level, call wall, put wall, and how to compute GEX from a raw options chain. Includes runnable Python code and sample data.
- [SpotGamma](https://spotgamma.com) - Commercial platform specializing in gamma exposure, charm, vanna, and options flow analysis. Publishes educational content on GEX methodology.
- [Squeezemetrics White Paper](https://squeezemetrics.com/monitor/download/pdf/white_paper.pdf) - "The Implied Order Book" — influential paper on dealer gamma positioning and market microstructure.

### Academic Papers

- [Hedging the Lottery](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2739491) - Relevant academic work on options market maker hedging dynamics.
- [Equity Volatility and Dealer Gamma](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3848436) - Research on the relationship between dealer gamma exposure and realized equity volatility.
- [Has Options Trading Informed Equity Prices?](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1101337) - Pan and Poteshman (2006) on information in options order flow.

### Tools

- [FlashAlpha](https://flashalpha.com) - Production API providing GEX, DEX (delta exposure), VEX (vanna exposure), and CHEX (charm exposure) by strike, expiration, and aggregate. Includes narrative summaries.
- [flashalpha-examples](https://github.com/FlashAlpha-lab/flashalpha-examples) - Self-contained Python scripts and notebooks demonstrating GEX dashboards, IV rank scanning, 3D volatility surface visualization, dealer positioning analysis, and Kelly Criterion position sizing using the FlashAlpha API.
- [OpenBB](https://openbb.co) - Open-source investment research platform with options flow and GEX visualization capabilities via community extensions.

## Dealer Positioning and Market Microstructure

Dealer positioning analysis focuses on inferring how market makers' hedging obligations — driven by their options inventory — create predictable, measurable pressure on underlying prices. The key exposures tracked are GEX (gamma), DEX (delta), VEX (vanna), and CHEX (charm), each of which drives hedging flows under different market conditions.

### References and Papers

- [Squeezemetrics White Paper](https://squeezemetrics.com/monitor/download/pdf/white_paper.pdf) - "The Implied Order Book." Foundational paper linking dealer gamma exposure to realized volatility and directional flow. Describes the DIX (dark index) and GEX framework.
- [Equity Volatility and Dealer Gamma](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3848436) - Academic study on the relationship between aggregate dealer gamma positioning and subsequent realized equity volatility.
- [The Term Structure of Variance Swap Rates and Optimal Variance Swap Investments](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1340670) - Egloff, Leippold, Wu (2010). Relevant to understanding variance risk premium and dealer variance exposure.
- [Demand-Based Option Pricing](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1354694) - Garleanu, Pedersen, Poteshman (2009). Documents how end-user demand for options drives prices away from no-arbitrage values, providing a microstructure basis for dealer positioning effects.

### Tools and Data

- [FlashAlpha](https://flashalpha.com) - Provides GEX, DEX, VEX, and CHEX profiles by strike and expiration for equities and indices, along with aggregate positioning summaries and AI narrative analysis. REST API and Python client.
- [gex-explained](https://github.com/FlashAlpha-lab/gex-explained) - Walkthrough of dealer hedging regimes, the gamma flip level, and the mechanics behind positive and negative gamma environments.
- [SpotGamma](https://spotgamma.com) - Commercial platform tracking dealer gamma, charm, vanna, and options flow with a focus on SPX/SPY and major indices.

---

## 0DTE and Intraday Options

Zero-days-to-expiration (0DTE) options — contracts expiring the same day they are traded — have grown to represent a substantial and growing share of total SPX options volume. Their short lifespan creates distinct dynamics: rapid theta decay, concentrated gamma near the money, and large intraday hedging flows that can move the underlying.

### Papers and Research

- [The 0DTE Puzzle](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4524445) - Empirical analysis of 0DTE SPX options volume, who trades them, and their effect on intraday volatility.
- [Intraday Pricing and the Overnight Effect](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3879125) - Research on intraday options pricing patterns and the behavior of short-dated implied volatility.
- [Has Options Trading Informed Equity Prices?](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1101337) - Pan and Poteshman (2006). Classic paper on options order flow informativeness, foundational for understanding intraday options-to-equity signal transmission.

### Tools and Data

- [CBOE DataShop](https://datashop.cboe.com) - Source for historical SPX and SPXW intraday trade and quote data, including 0DTE contracts.
- [Thetadata](https://thetadata.net) - Tick-level historical options data provider with good coverage of short-dated and 0DTE contracts.
- [FlashAlpha](https://flashalpha.com) - Exposure summaries include zero-DTE contribution breakdowns (DEX, GEX) to isolate 0DTE dealer hedging pressure from longer-dated positioning.
- [Polygon.io](https://polygon.io/docs/options) - Intraday and real-time options data via REST and WebSocket API, suitable for building 0DTE flow monitors.

---

## Kelly Criterion and Position Sizing

The Kelly Criterion provides a mathematically optimal fraction of capital to allocate to a bet given an edge and a payoff distribution. Applied to options, it must account for the non-linear payoff structure, the role of implied vs realized volatility in defining edge, and the practical need for fractional Kelly to manage drawdown.

### Papers and References

- [A New Interpretation of Information Rate](https://archive.org/details/bstj35-4-917) - Kelly (1956). The original paper introducing the Kelly Criterion.
- [Optimal Growth and the Kelly Criterion](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2230900) - Overview of Kelly-based portfolio growth theory and its application to leveraged and derivative positions.
- [Fortune's Formula](https://www.amazon.com/Fortunes-Formula-Scientific-Betting-Casinos/dp/0809045990) - William Poundstone. Accessible account of the Kelly Criterion's development and application in markets.
- [The Kelly Criterion in Blackjack, Sports Betting, and the Stock Market](https://www.cambridge.org/core/books/handbook-of-asset-and-liability-management/kelly-criterion-in-blackjack-sports-betting-and-the-stock-market/3C9B7960D8456ACE73498B5BD38A33B5) - Thorp (2006). Comprehensive treatment of Kelly in financial markets including derivatives.

### Tools

- [flashalpha-examples](https://github.com/FlashAlpha-lab/flashalpha-examples) - Includes a Kelly Criterion position sizing notebook (`06_kelly_sizing.py`) that integrates greeks and IV data from the FlashAlpha API to compute optimal sizing fractions.
- [FlashAlpha `fa.kelly()`](https://flashalpha.com) - API endpoint for Kelly-optimal position sizing given options greeks, implied volatility, and a realized volatility estimate.
- [Riskfolio-Lib](https://github.com/dcajasn/Riskfolio-Lib) - Portfolio optimization library covering Kelly and entropy-based risk measures applicable to options portfolios.

---

## Options Screeners

Options screeners filter and rank contracts or underlyings by metrics like implied volatility, open interest, greeks, dealer exposure, or custom expressions. A good screener lets you compose filters on the stock, expiry, strike, and individual contract level in a single query.

### APIs and Tools

- [FlashAlpha Live Screener](https://flashalpha.com/docs/lab-api-screener) - Live options screener API. Filter/rank symbols across your universe by gamma exposure (GEX), variance risk premium (VRP), IV, greeks, harvest scores, dealer flow risk, and custom formulas. Supports cascading filters on expiries, strikes, and contracts. Data refreshes every 5-10 seconds from an in-memory store. SDKs in Python, JavaScript, .NET, Java, Go, plus an MCP tool.
- [FlashAlpha Max Pain](https://flashalpha.com/docs) - Max pain analysis API with dealer alignment overlay (gamma flip, call/put walls), pain curve, OI breakdown by strike, expected move context, pin probability scoring, and multi-expiry calendar. Converging/diverging dealer alignment signals when max pain acts as a true price magnet vs. being overridden by directional flow.
- [FlashAlpha Screener Cookbook](https://flashalpha.com/docs/lab-api-screener-cookbook) - Worked recipes: harvestable VRP scans, negative-gamma alerts, vol-scanner setups, 0DTE call-seller screens, and custom formula rankings.
- [flashalpha-examples `10_live_options_screener.py`](https://github.com/FlashAlpha-lab/flashalpha-examples) - Runnable Python examples: harvestable VRP setups, IV premium ranking, cascading strike/contract filters, risk-adjusted harvest scores.
- [MarketChameleon](https://marketchameleon.com) - Commercial options screener covering unusual activity, earnings, and IV rank.
- [Barchart Options Screener](https://www.barchart.com/options/screener) - Free options screener with filters for volume, OI, IV, delta, and more.
- [Cboe LiveVol](https://www.livevol.com) - Professional options analytics platform with custom screening.

### Screening Strategies

- **Harvestable VRP** - Filter for positive-gamma names with `vrp_regime = harvestable`, `dealer_flow_risk <= 40`, `harvest_score >= 65`. Captures short-vol setups where implied richness is durable.
- **Negative gamma alert** - Filter for `regime = negative_gamma` and `dealer_flow_risk >= 50`. Identifies names where hedging flows amplify price moves.
- **IV premium ranking** - Rank by the formula `atm_iv - rv_20d` to find names where implied is richest vs trailing realized.
- **Cascading 0DTE call seller** - Filter `expiries.days_to_expiry = 0`, `contracts.type = C`, `contracts.delta >= 0.3`, `contracts.oi >= 1000` to surface high-probability short-call candidates.
- **Risk-adjusted harvest** - Compute `harvest_score / (dealer_flow_risk + 1)` as a formula to rank setups by expected reward per unit of hedging-flow risk.

---

## Open Source Projects

- [OpenBB](https://github.com/OpenBB-finance/OpenBBTerminal) - Open-source investment research platform. Includes options chain data, IV surface visualization, and extensible data connectors.
- [QuantLib](https://github.com/lballabio/QuantLib) - Industry-standard open-source quantitative finance library (C++ with Python, R, and Java wrappers).
- [Riskfolio-Lib](https://github.com/dcajasn/Riskfolio-Lib) - Portfolio optimization library that includes risk measures relevant to options portfolio management.
- [PyAlgoTrade](https://github.com/gbeced/pyalgotrade) - Python algorithmic trading library with backtesting support.
- [FinancePy](https://github.com/domokane/FinancePy) - Python finance library covering options, bonds, credit derivatives, and more with a focus on practical implementation.
- [tf-quant-finance](https://github.com/google/tf-quant-finance) - Google's TensorFlow-based quantitative finance library with GPU-accelerated options pricing and calibration.
- [Volatility3](https://github.com/volatilityfoundation/volatility3) - Note: this is a memory forensics tool, not finance — included as a naming caution for researchers.
- [optopsy](https://github.com/michaelchu/optopsy) - Options backtesting library for Python, designed for systematic options strategy testing.

## Educational Resources

### Books

- [Option Volatility and Pricing](https://www.mheducation.com/highered/product/option-volatility-pricing-advanced-trading-strategies-techniques-natenberg/9780071818773.html) - Sheldon Natenberg. The standard reference for options traders on pricing, volatility, and risk management.
- [Dynamic Hedging](https://www.wiley.com/en-us/Dynamic+Hedging%3A+Managing+Vanilla+and+Exotic+Options-p-9780471152804) - Nassim Nicholas Taleb. Deep treatment of practical options risk management and hedging.
- [The Volatility Surface](https://www.wiley.com/en-us/The+Volatility+Surface%3A+A+Practitioner%27s+Guide-p-9780471792512) - Jim Gatheral. The definitive reference on implied volatility surface modeling.
- [Options, Futures, and Other Derivatives](https://www.pearson.com/en-us/subject-catalog/p/options-futures-and-other-derivatives/P200000005938) - John C. Hull. Standard academic and practitioner textbook on derivatives.
- [Paul Wilmott on Quantitative Finance](https://www.wiley.com/en-us/Paul+Wilmott+on+Quantitative+Finance%2C+3+Volume+Set%2C+2nd+Edition-p-9780470018705) - Comprehensive multi-volume reference on quantitative methods in finance.

### Courses and Lecture Notes

- [QuantLib Notebooks](https://github.com/lballabio/QuantLib-SWIG/tree/master/Python/examples) - Official example notebooks for QuantLib Python bindings.
- [Financial Models with Numerical Methods](https://github.com/cantaro86/Financial-Models-Numerical-Methods) - Jupyter notebook collection covering Black-Scholes, Heston, stochastic volatility, and vol surface modeling.
- [Cornell Financial Engineering Lecture Notes](https://people.orie.cornell.edu/mru8/orie5251/) - Graduate-level options pricing and derivatives course materials.

### Papers

- [The Pricing of Options and Corporate Liabilities](https://www.jstor.org/stable/1831029) - Black and Scholes (1973). The original Black-Scholes paper.
- [Theory of Rational Option Pricing](https://www.jstor.org/stable/3003143) - Merton (1973). Extension of Black-Scholes, introducing continuous dividends and barrier options.
- [A Closed-Form Solution for Options with Stochastic Volatility](https://www.jstor.org/stable/2962344) - Heston (1993). The Heston stochastic volatility model.
- [Arbitrage-Free SVI Volatility Surfaces](https://arxiv.org/abs/1204.0646) - Gatheral and Jacquier (2014). SSVI construction ensuring no calendar spread or butterfly arbitrage.

## Communities

- [r/options](https://www.reddit.com/r/options/) - Reddit community for options trading discussion, strategies, and education.
- [r/algotrading](https://www.reddit.com/r/algotrading/) - Algorithmic trading community covering systematic options strategies, backtesting, and quantitative research.
- [r/thetagang](https://www.reddit.com/r/thetagang/) - Community focused on premium selling strategies: covered calls, cash-secured puts, spreads, and iron condors.
- [r/quant](https://www.reddit.com/r/quant/) - Quantitative finance community including volatility modeling, derivatives research, and academic discussion.
- [Quantocracy](https://quantocracy.com) - Curated aggregator of quantitative trading and research blog posts, including frequent options and volatility content.
- [QuantConnect Community](https://www.quantconnect.com/forum) - Algorithmic trading community centered around the QuantConnect backtesting platform. Options strategy forums and shared algorithms.
- [Wilmott Forums](https://forum.wilmott.com) - Long-running quantitative finance forum covering derivatives pricing, volatility, and financial engineering.
- [Nuclear Phynance](http://www.nuclearphynance.com) - Forum for quantitative finance practitioners focused on derivatives and risk.
- [Elitetrader Options](https://www.elitetrader.com/et/forums/options.23/) - Practitioner forum with active options strategy and market microstructure discussion.

## Market Data Sources

### Free

- [Yahoo Finance Options](https://finance.yahoo.com) - Free options chains with basic greeks via the website and yfinance Python library.
- [CBOE Free Data](https://www.cboe.com/market_statistics/) - CBOE publishes free daily market statistics including options volume, VIX, and put/call ratios.
- [Nasdaq Options](https://www.nasdaq.com/market-activity/options-analytics) - Options analytics and chain data from Nasdaq.
- [Barchart Options](https://www.barchart.com/options) - Free options chains, IV rank, IV percentile, and skew data with limited historical depth.

### Paid and Institutional

- [OptionMetrics IvyDB](https://optionmetrics.com) - Standardized end-of-day options data used widely in academic research.
- [ORATS](https://orats.com) - Historical and real-time options data with earnings history, IV surface, and backtesting API.
- [CBOE DataShop](https://datashop.cboe.com) - Official exchange data including historical options trades, quotes, and settlement data.
- [Refinitiv (LSEG)](https://www.lseg.com/en/data-analytics) - Institutional market data terminal and API with comprehensive options data.
- [Bloomberg](https://www.bloomberg.com/professional/solution/data-and-content/) - Industry-standard terminal with full options chains, vol surfaces, and derivatives analytics.
- [Intrinio](https://intrinio.com) - Options data API with end-of-day and real-time tiers.
- [Polygon.io](https://polygon.io/docs/options) - Real-time and historical US equity options data via REST and WebSocket API.
- [Thetadata](https://thetadata.net) - Historical options data provider focused on tick-level and end-of-day data for systematic traders.

---

## Contributing

Contributions are welcome. To add a resource:

1. Fork this repository.
2. Add your resource to the appropriate section in alphabetical order within that section, or propose a new section if warranted.
3. Follow the existing format: `- [Name](url) - Description.`
4. Ensure the resource is real, maintained, and genuinely useful to the options analytics community.
5. Submit a pull request with a brief explanation of why the resource belongs on the list.

Please do not submit self-promotional links without disclosure, broken links, or resources of marginal quality.

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related or neighboring rights to this work.
