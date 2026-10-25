# 05. Solution Design

## Concept
A single app that combines:
1. **Self-listed stations** placed by latitude and longitude.
2. **Car selection** that produces a charging-time estimate.
3. **Payment as check-in** so status data is created without manual entry.
4. **Slot booking** of a port for 30-40 minutes.

Design status: concept. Not built, not user-tested.

## 1. Station owner journey (self-listing)
- Owner drops a pin (lat-long), enters charger type, power (kW) and connectors, and uploads a photo.
- GPS-verified pin plus photo reduces ghost listings (pain point 10).
- Hosting models already exist at Kazam and Bolt.Earth, so this is a proven pattern. The differentiator is focus on tier-2 and tier-3 cities where larger players have little data.
- Owner can also update port status (backup data source) and receives booking notifications and broken-charger reports.

## 2. Driver journey
1. Open app. Location is read from the phone (standard feature).
2. Choose a vehicle once (car or bike). It is saved; the last vehicle is the default.
3. See compatible chargers only, with Rs/kWh and an estimated cost for this car.
4. Optionally book a 30-40 minute slot.
5. At the charger: scan the QR, pay by UPI. Payment starts the session and counts as check-in.
6. App tracks the session, estimates time remaining, and sends "charging complete".

## 3. The central design problem: data entry friction
The user raised it directly: users will not enter details every time they charge. The answers, in order of preference:
1. **Payment = check-in.** Scanning and paying starts the session with no typing. ElectricPe and Statiq were cited in the research as tracking sessions through payment.
2. **QR on each charger.** Scan, vehicle already saved, optional battery %, about 10 seconds.
3. **Return value for the user.** Charging-complete alert, queue position ("1 person waiting after you"), live cost estimate. The user benefits, so entry is not a chore.
4. **Owner-side updates** as a second source.
5. **Long term:** cheap OCPP-enabled smart chargers supplied to stations so status is automatic. Kazam and Bolt.Earth went this route.

Manual entry stays optional.

## 4. Time estimate logic
- Inputs: vehicle battery size and max charge speed (from a vehicle database), charger power.
- Output: estimated time. On integrated stations, SoC (battery %) may be available from the charger. On self-listed stations it is **not**, so the app uses the user's start tap and optional battery % and computes locally.
- Labelled in the UI as **"user reported / estimated"**, not charger-verified.

## 5. Booking logic
- A booking reserves a port for 30-40 minutes.
- On self-listed stations there is no technical enforcement. The owner gets a notification and must honor it. Enforcement is operational: no-show fee and a rating system are needed (open design item).
- On integrated stations (for example Tata's own network), booking exists today inside that network.

## 6. Status model
Beyond free/occupied: available, charging, faulted, **no power** (pain point 11), unverified/stale (no recent check-in). Failed sessions never mark a port occupied.

## 7. Trust features
- "Last confirmed working" timestamp.
- One-tap "not working" report.
- Public downtime counter and owner notification.
- Owner rating and response tracking.

## Open items
- No-show fee design and dispute handling.
- Owner onboarding incentive.
- Vehicle database source.
- Whether payment partners allow the QR-to-session flow on self-listed chargers (not verified in this research).
