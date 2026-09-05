# Quantitative Finance Dashboard in R Shiny

An R Shiny application for exploring financial markets, constructing investment portfolios, and producing Bayesian vector autoregression forecasts.

Created by Makar Prikhodko, Ivan Polozov, Askhab Suleimanov, and Gordey Verbiy as a software-engineering course project.

## Features

- Interactive market and instrument views
- Portfolio allocation and optimization workflows
- Historical financial data visualization
- Bayesian VAR model training and forecast plots
- A multi-page Shiny interface with authentication-related UI components

## Project Structure

- `Global.R` — package imports, shared data, and global configuration
- `ui.R` — application shell and page composition
- `server.R` — reactive server logic, portfolio calculations, and BVAR forecasts
- `invest_page.R` — investment-page interface
- `trading_page.R` — trading-page interface
- `data.csv` — bundled market and macroeconomic data

## Requirements

Install R and the packages used by the application:

```r
install.packages(c(
  "shiny",
  "bslib",
  "shinymanager",
  "thematic",
  "shinyWidgets",
  "rusquant",
  "fPortfolio",
  "BVAR",
  "xts"
))
```

Additional transitive packages may be installed automatically.

## Running the App

1. Clone the repository.
2. In `server.R`, replace the historical absolute path used in `read.csv(...)` with a path to the included `data.csv` file. A portable choice is simply:

   ```r
   test <- read.csv("data.csv")
   ```

3. Start the app from RStudio with **Run App**, or from an R console:

   ```r
   shiny::runApp(".")
   ```

## Known Limitation

The original coursework version contains a Windows-specific absolute path for `data.csv`. It must be adjusted before the app can run on another machine.
