# Nzela Pay — raw data

Nzela Pay is a fictional mobile money and microfinance company in
Kinshasa. All data in this folder is **synthetic**, generated for
learning purposes. It does not describe real people or a real company.

Period covered: 1 January 2025 to 30 September 2026.
Format: CSV, comma-separated, UTF-8, one header row.

| File | One row per | Columns |
|---|---|---|
| customers.csv | customer | customer_id, signup_date, commune, age_band, occupation, kyc_level |
| agents.csv | agent | agent_id, commune, opened_date, agent_type, float_limit |
| transactions.csv | wallet transaction | txn_id, customer_id, timestamp, txn_type, agent_id, currency, amount, fee, status |
| loans.csv | loan | loan_id, customer_id, disbursed_date, principal, currency, term_days, interest_rate, product |
| repayments.csv | repayment | repayment_id, loan_id, paid_date, amount, currency, channel |
| fx_rates.csv | day | date, usd_to_cdf |

Business notes from the data team:
- `txn_type`: cash_in and cash_out happen at an agent; p2p, bill_pay
  and airtime are done in the app, without an agent.
- `currency`: USD (US dollar) or CDF (Congolese franc).
- `fee`: what Nzela earns on the transaction, in the transaction's
  currency.
- Loans are repaid in weekly instalments: principal x (1 + interest
  rate), split over the number of weeks in the term.
- `usd_to_cdf`: how many Congolese francs one US dollar is worth that
  day.

This raw data has **not** been cleaned. Do not edit these files:
cleaning happens in code, so it can be repeated and checked.
