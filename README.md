# Debt Payoff

**AppADay 189 | Utility | Shipped November 12, 2026**

Live: https://augustineiacopelli.github.io/appaday-189-debt-payoff/
Portfolio: https://augustineiacopelli.github.io/appaday/

Compare the debt snowball and the debt avalanche side by side. Enter each debt with its balance, APR, and minimum payment, add any extra amount you can pay each month, and see your debt free date, how many months each plan takes, the total interest each one costs, the order your debts get paid off, and a chart of your total balance falling over time.

## What it does

The hero card at the top shows the month and year you will be debt free, what you owe today, the months to go, and how much the avalanche saves over the snowball. Each debt card shows its share of your total balance. The two strategy cards show months to debt free, a bar splitting what you pay between principal and interest, total interest, total paid, and a timeline of when each debt is paid off. The cheaper plan is marked Lowest cost. The chart plots both plans, with avalanche as a solid line over a shaded area and snowball as a dashed line.

Snowball pays the smallest balance first. Avalanche pays the highest APR first. Both pay every minimum each month, put the extra payment on the target debt, and roll each paid off debt's minimum into the next target.

Mortgages can carry escrow. Tap Escrow on any debt and enter the taxes and insurance portion of the payment. Minimum stays the full payment from your statement, only the principal and interest part pays down the loan, and the escrow amount never rolls over to other debts once the mortgage is paid off, because taxes and insurance continue. Escrow is left out of interest and total paid.

If a minimum payment does not cover a debt's first month of interest, the app says so and tells you the smallest minimum that would. If a plan cannot finish within 100 years, the app shows a clear message instead of numbers.

## How it works

The math runs in whole cents, with APR held in basis points and interest compounded monthly. The simulation is a pure function that returns months, total interest, payoff order with payoff months, a monthly total balance series, and a never pays off flag. It stops at a 1200 month cap. The chart is hand drawn SVG with no libraries.

Your debts and extra payment are saved in this browser's localStorage and come back when you reload. Clear all asks you to confirm on the page before it erases anything. Nothing leaves your device.

## Built with

A single self contained `index.html` of HTML, CSS, and vanilla JavaScript, with no build step and no dependencies. It carries the AppADay home screen icon tags and the shared Save to Phone script.

## Notes

These are estimates. They assume fixed APRs, monthly compounding, no new charges, no fees, and a fixed escrow amount.

Part of [AppADay](https://augustineiacopelli.github.io/appaday/), one complete web app shipped every day.
