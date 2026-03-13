# Awesome Options Analytics [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of tools, libraries, data providers, and resources for options analytics, volatility research, and derivatives trading. Inspired by the [awesome](https://github.com/sindresorhus/awesome) project.

Contributions welcome. See [Contributing](#contributing).

---

## Contents

- [APIs and Data Providers](#apis-and-data-providers)
- [Python Libraries](#python-libraries)
- [Options Pricing and Greeks](#options-pricing-and-greeks)
- [Volatility Analysis](#volatility-analysis)
- [Gamma Exposure (GEX)](#gamma-exposure-gex)
- [Open Source Projects](#open-source-projects)
- [Educational Resources](#educational-resources)
- [Communities](#communities)
- [Market Data Sources](#market-data-sources)
- [Contributing](#contributing)

---

## APIs and Data Providers

- [FlashAlpha](https://flashalpha.io) - Options analytics API providing GEX (gamma exposure), DEX (delta exposure), VEX (vanna exposure), CHEX (charm exposure), full greeks, open interest, and AI-powered narrative analysis across equities and indices. Offers both REST endpoints and a Python client.
- [CBOE DataShop](https://datashop.cboe.com) - Historical and real-time options data directly from the exchange, including VIX data, settlement prices, and implied volatility indexes.
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

- [gex-explained](https://github.com/dmacthedestroyer/gex-explained) - Community repository explaining GEX calculation methodology, notation, and interpretation.
- [SpotGamma](https://spotgamma.com) - Commercial platform specializing in gamma exposure, charm, vanna, and options flow analysis. Publishes educational content on GEX methodology.
- [Squeezemetrics White Paper](https://squeezemetrics.com/monitor/download/pdf/white_paper.pdf) - "The Implied Order Book" — influential paper on dealer gamma positioning and market microstructure.

### Academic Papers

- [Hedging the Lottery](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2739491) - Relevant academic work on options market maker hedging dynamics.
- [Equity Volatility and Dealer Gamma](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3848436) - Research on the relationship between dealer gamma exposure and realized equity volatility.
- [Has Options Trading Informed Equity Prices?](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1101337) - Pan and Poteshman (2006) on information in options order flow.

### Tools

- [FlashAlpha](https://flashalpha.io) - Production API providing GEX, DEX (delta exposure), VEX (vanna exposure), and CHEX (charm exposure) by strike, expiration, and aggregate. Includes narrative summaries.
- [OpenBB](https://openbb.co) - Open-source investment research platform with options flow and GEX visualization capabilities via community extensions.

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
