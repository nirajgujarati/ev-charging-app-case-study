# 06. Technical Feasibility

## Protocols
| Item | What it is | Relevance |
|---|---|---|
| OCPP | Protocol between a charger and its management system | Gives real-time connector status (available, charging, faulted), session start time and kWh delivered, and sometimes SoC |
| OCPI | Roaming and data-exchange API between CPOs and platforms | Lets an aggregator read other networks' data with partnership |
| UEI | Unified Energy Interface, built on the Beckn protocol | An open network that could let one app reach many CPOs without one-by-one deals. Described in the research as emerging, not yet universal |

Example of an OCPI-style provider: IONAGE offers real-time APIs to authorized partners (https://apidoc.ionage.in/).

## What data is available and where
| Source | Data | Condition |
|---|---|---|
| Integrated CPO station | Live status, session, kWh, maybe SoC | Needs partnership or OCPI access |
| Self-listed station | Only what users and owners report | No OCPP connection; "user reported" |
| Payment event | Session start and end | Needs payment-flow integration |

## What is easy
- Location by lat-long, map display, filters by connector and power.
- Vehicle-based time estimate (battery size, charger kW).
- Self-listing form with photo and GPS pin.

## What is hard
- **Commercial, not technical:** CPO partnerships and data quality.
- SoC is not provided by all chargers or vehicles, especially two-wheelers. The app then shows an estimate, not a live value.
- Booking enforcement on self-listed chargers is operational.
- Data trust depends on user density.

## Honest limits
- Live data on self-listed chargers is user-reported, not machine-verified, and must be labelled.
- Nothing in this study was implemented or load-tested.

## Suggested minimal prototype (not built)
Map, station listing with GPS pin and photo, vehicle select, estimate, and a check-in flow. About 2-3 days of work as a rough estimate.
