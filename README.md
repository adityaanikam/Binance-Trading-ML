# Binance-Trading-ML
# Binance Trading Account Analysis

## Overview
This project analyzes historical trade data from various Binance trading accounts over a 90-day period to evaluate performance, calculate key financial metrics, and rank the top performing accounts. The analysis includes ROI, PnL, Sharpe Ratio, Maximum Drawdown, and other critical trading metrics.

## Features
- Data processing of nested JSON trade histories
- Calculation of key financial metrics:
  - Return on Investment (ROI)
  - Profit and Loss (PnL)
  - Sharpe Ratio
  - Maximum Drawdown (MDD)
  - Win Rate
  - Position Analysis (Long/Short)
- Risk-adjusted performance scoring
- Portfolio ranking algorithm
- Comprehensive performance reporting

## Requirements
```python
pandas>=1.5.0
numpy>=1.20.0
```

## Project Structure
```
├── analysis_script.py       # Main analysis script
├── requirements.txt         # Project dependencies
├── output/
│   ├── top_20_accounts.csv # Top performing accounts
│   └── analysis_report.md  # Detailed findings
```

## Installation
1. Clone the repository:
```bash
git clone https://github.com/adityaanikam/binance-trading-analysis.git
cd binance-trading-analysis
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

## Usage
1. Place your data file (`TRADES_CopyTr_90D_ROI.csv`) in the project directory

2. Run the analysis:
```bash
python analysis_script.py
```

3. Check the output files in the `output/` directory

## Data Format
Input CSV should contain:
- `Port_IDs`: Unique identifier for each trading account
- `Trade_History`: JSON string containing trade details including:
  - time: Timestamp in milliseconds
  - symbol: Trading pair
  - side: BUY/SELL
  - price: Execution price
  - quantity: Trade amount in quote currency
  - realizedProfit: Profit/Loss from the trade

## Methodology

### Performance Metrics
- **ROI**: Cumulative profit relative to investment
- **PnL**: Absolute profit/loss
- **Win Rate**: Proportion of profitable trades
- **Sharpe Ratio**: Risk-adjusted return measure
- **MDD**: Maximum peak-to-trough decline

### Scoring System
```python
Score = (
    ROI * 0.4 +
    PnL * 0.3 +
    Win_Rate * 0.2 +
    Sharpe_Ratio * 0.1
)

Risk_Adjusted_Score = Score * (1 + Win_Rate) / (1 - abs(Max_Drawdown))
```

## Output Files
1. `top_20_accounts.csv`: Contains top performing accounts with metrics
2. `analysis_report.md`: Detailed analysis findings and methodology

## Results
The analysis produces:
- Ranked list of top 20 trading accounts
- Performance metrics for each account
- Risk analysis and position breakdowns
- Trading pattern insights

## Limitations
- Analysis limited to 90-day period
- Results specific to market conditions during the period
- Past performance may not predict future results

## Contributing
Feel free to submit issues, fork the repository, and create pull requests for any improvements.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Author
Aditya Nikam


- Data provided by Binance
- Analysis methodology based on standard financial metrics and risk management practices
