# 04. User Pain Points (14, sourced)

Each item: the complaint, the evidence, and one final solution in the proposed app. Evidence is from public Reddit threads, Team-BHP and App Store reviews. Quotes are as reported in the research; links are the sources.

---
### 1. Charger shows "available" but is broken or offline (most-reported)
**Evidence:** An MG Windsor owner drove to a Vrindavan charger shown as "Available"; it was not working and gave no warning (r/CarsIndia, Feb 2026: https://www.reddit.com/r/CarsIndia/comments/1r2r276/). On a Team-BHP Mumbai-Goa trip, a faulted 180kW charger showed "available" and several cars drove to the same dead spot (https://www.team-bhp.com/news/mumbai-goa-and-back-my-mahindra-xev-9s-charging-stops-and-more).
**Solution:** Every session and check-in updates status. Show "last confirmed working: X hours ago" and a one-tap "not working" report that flags the charger for everyone.

### 2. Forced to keep 3-4 apps, none trusted
**Evidence:** "I now have 3-4 EV charging apps on my phone because I don't fully trust any one of them" (r/CarsIndia link above). r/2ChargeEV: a separate folder of charging apps on the phone (https://www.reddit.com/r/2ChargeEV/comments/1mpw9h0/).
**Solution:** One app for all networks and self-listed stations, one login, one payment method.

### 3. Money stuck in multiple wallets, minimum top-ups
**Evidence:** r/2ChargeEV: Rs 500 minimum top-up per app, Rs 200 used, Rs 300 left stranded. BE.6 owner: Tata session stuck, wallet loaded on a second phone, "money stuck in both apps" (https://www.reddit.com/r/mahindrabe6/comments/1kpe6wg/). Tata EZ Charge App Store review: wallet balance delays, stuck funds (https://apps.apple.com/in/app/tata-power-ez-charge/id1496350476).
**Solution:** No wallet. Pay per session by UPI, exact billed amount only.

### 4. Broken chargers stay broken for months, no accountability
**Evidence:** r/CarsIndia: a BPCL Ionage charger broken since January; another offline 81 days until escalated through a helpline (https://www.reddit.com/r/CarsIndia/comments/1j7v94r/ev_owners_take_action_report_broken_bpcl_ionage/).
**Solution:** Public downtime counter on each listing ("down since 12 days") and an automatic notification to the owner on every broken report.

### 5. Payment and app failures at the charger when battery is low
**Evidence:** r/EVIndia highway trip: Adani charger empty, balance loaded in the app, repeated errors, user had to move on (https://www.reddit.com/r/EVIndia/comments/1rcff69/). Statiq App Store review (19/11/2025): "constant errors, failed payments, random glitches" (https://apps.apple.com/in/app/statiq-ev-charging-stations/id1520534378).
**Solution:** QR on the charger: scan, pay by UPI, done. Payment is the check-in and the session starts automatically.

### 6. Session fails to start, handshake errors, stuck sessions
**Evidence:** Tata EZ Charge review: session fails to initiate ("SOC not connected") or stops unexpectedly. Team-BHP tips thread: charging may not start on the first attempt, 60-second timeouts, 2-3 tries needed (https://www.team-bhp.com/forum/electric-cars/277640-long-journey-ev-charging-tips.html).
**Solution:** The app detects a failed start, retries, and never marks the port "occupied" for a failed session, so occupancy data stays clean.

### 7. No idea of wait time (45-minute queues on highways)
**Evidence:** r/EVIndia Delhi-Moradabad: "both guns occupied with waiting time of 45 mins, so I moved." Team-BHP: 3 cars queued at one working charger.
**Solution:** Live session tracking (start time, vehicle, charger power) gives "port free in ~20 min", plus a 30-40 minute slot booking.

### 8. Charging to 100% hogs fast chargers
**Evidence:** Team-BHP Mumbai-Goa: an XEV 9E kept charging to 100% while cars queued; a BHPian suggested a price hike after 80%. Charging 80-100% takes about as long as 40-80%.
**Solution:** A nudge at 80% when others are waiting or booked ("2 users waiting, charging slows after 80%"). Booked slots also limit hogging.

### 9. Pricing opacity
**Evidence:** r/CarsIndia: Rs 1,000 buys 35 kWh on one network and 53 on another; Tata about Rs 20/kWh vs Jio-bp Rs 16/kWh; Tata adds GST at wallet top-up (https://www.reddit.com/r/CarsIndia/comments/1ee94gj/).
**Solution:** Show Rs/kWh for every nearby charger up front, and a cost estimate for the user's car ("15-80% = about Rs 240").

### 10. Ghost chargers (listed but not at that location)
**Evidence:** BE.6 owner: "first charger wasn't even present at the location mentioned in PlugShare"; locals redirected them to a charger dead for 15 days.
**Solution:** Self-listing requires a photo and a GPS-verified pin. "Last check-in" recency shows the charger exists and works.

### 11. No electricity or power cuts at stations
**Evidence:** r/EVIndia: two stops had no electricity. BE.6 owner: power went out mid-session at Tata Umreth and the session stuck in the app.
**Solution:** A separate "no power" status, reported by on-site users and inferred from failed sessions.

### 12. Connector and vehicle incompatibility (esp. two-wheelers)
**Evidence:** r/EVIndia, Sept 2026: an Ather Rizta owner installed the ElectriVa app, added Rs 100, plugged in and nothing charged; ElectriVa does not work with Ather (https://www.reddit.com/r/EVIndia/comments/1wrnjeq/). Ola uses Type 6, Ather Type 7, no standard (https://www.reddit.com/r/EVsOfIndia/comments/1wgwsfz/).
**Solution:** Save the vehicle once. The app shows only compatible chargers. Car vs bike is built into every listing.

### 13. Wrong charging-time estimates
**Evidence:** Statiq App Store review: the app showed 9 hours for a full charge; the car went 15-100% in about 1 hour.
**Solution:** Estimate from the selected car (battery size) and charger kW, not a generic timer.

### 14. Support is dead when stranded
**Evidence:** Tata EZ Charge review (Dec 2025): "helpline performance very bad, never got a reply till now." r/EVIndia: "Adani has the worst app and customer support."
**Solution:** A community layer (on-site users and queue visible) plus owner ratings and response tracking, so bad operators are visible.

---
## Pattern
The concept directly answers pain points **1, 2, 3, 5, 7, 10, 12, 13**, which are among the most repeated.

## Honest limits
- Solutions 1, 4 and 11 depend on **user density**: crowdsourced data only works once enough people use the app.
- Solution 6 needs **CPO integration** for machine-verified session data.
- This is a qualitative sample of public posts, not a statistical survey. It shows what kinds of problems occur, not how often.
