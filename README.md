# Blown Off Course: Modeling Wind Damage and DOT Response in NYC

## What this project is

High winds are a recurring, under-managed threat to New York City's transportation network. Gusts knock out traffic signals, down signs and streetlights, scatter debris across roadways, and force decisions about restricting or closing bridges — yet wind response tends to get far less dedicated planning attention than snow or flooding, even though it happens more often and touches nearly every asset class NYC DOT is responsible for.

This project is a web-based tool that turns that gap into something concrete: a single application with three connected views —

1. **311 Dashboard** — real NYC 311 complaint data from past wind events (Tropical Storm Isaias, Hurricane Sandy, or any custom date range), broken down by responding agency and borough, so you can see who actually handles wind damage and how fast.
2. **Forecast & Alerts** — a live wind-gust forecast from the National Weather Service, run through an internal five-level DOT alert ladder (Routine → Monitor → Advisory → Warning → Extreme), plus a *prediction* of expected damage if nobody responds.
3. **Storm Simulator** — a game-style tool where you play DOT duty commander: allocate a limited budget across crews, pre-storm securing, a public advisory, and bridge/truck-ban thresholds, then watch a storm play out hour by hour and get scored against a "do nothing" baseline.

All three views share one underlying damage model, so the historical data, the live forecast, and the simulated response stay consistent with each other rather than existing as three disconnected demos.

## Why this project exists

NYC DOT's mission is to keep the city moving safely and to maintain its transportation assets, over 6,000 miles of streets and sidewalks and 789 bridges — in a state of good repair. The *Strategic Plan 2016: Safe, Green, Smart, Equitable* commits the agency to exactly the kind of work wind resilience demands: safety (fewer dark intersections and debris hazards), smart operations (using data and forecasts instead of reacting after the fact), climate adaptation (storms intensifying under the plan's own 80x50 framing), and equity (making sure response isn't uneven across boroughs).

Today, wind response appears largely reactive: decisions get made as conditions are observed, without a shared view of what's likely coming, what damage to expect, or how a proposed response compares to doing nothing at all. This project exists to demonstrate what closing that gap could look like — a proactive, data-grounded approach to a hazard that has historically been treated as an afterthought.

## Goals and how success is measured

- **Show what actually happened.** The dashboard should load real 311 data for known wind events and split it cleanly by agency and borough, with no load errors.
- **See it coming.** The Forecast page should pull a live NWS forecast, classify it correctly against the alert ladder, and degrade gracefully to a labeled demo forecast if the live connection fails.
- **Test a response before it's needed.** The simulator should score any plan against a "do nothing" baseline such that no single strategy dominates regardless of storm type — verified by testing that the best budget allocation genuinely changes from a light gale to a hurricane-force mission.
- **Stay internally consistent.** The Forecast page's damage prediction and the simulator's baseline should come from the same underlying model, not two disconnected pieces of logic.
- **Work without live data.** Every external data source has a clearly labeled synthetic fallback, so the full app runs and passes its test suite with zero network access.
- **Be honest about its limits.** Documentation states plainly which numbers are real (311 records, NWS forecasts) and which are illustrative placeholders (asset counts, failure rates, alert thresholds), with a concrete path to real calibration.

## Intended outcome

The deliverable is a working application that demonstrates the full arc of wind-event management in one place: what happened last time, what's about to happen, and what a good response looks like compared to no response at all. It's built as a class/portfolio project rather than a production DOT system — the damage rates and alert thresholds are placeholder assumptions, not validated agency figures — but it's structured so that gap is explicit and fixable: the README and in-app notes point directly at how the illustrative model could be replaced with rates fit to real historical data, turning this from a demonstration into a genuinely useful planning tool.
