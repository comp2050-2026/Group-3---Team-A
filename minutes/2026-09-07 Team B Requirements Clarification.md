# Team B Requirements Clarification

## Header

- **Date:** 7 September 2026
- **Present:** Yousef, Harrison, Cooper
- **Apologies:** Isaac
- **Minute taker:** Yousef

## Agenda

- Clarify information exchanged between ChargeMate Customer and ChargeMate Ops.
- Confirm rental, return and error-handling responsibilities.

## Discussion Summary

Team B confirmed that ChargeMate Customer will receive:

- Station location.
- Exact number of available power banks.
- Power bank charge status.
- Exact number of available return slots.
- Station online/offline status.

Availability will update whenever a rental, return, fault or station status changes.

For rentals, ChargeMate Customer will send the power bank ID, station ID and rental details. ChargeMate Ops will confirm the rental and released power bank.

For returns, the system will send the power bank ID and return station. Customers may return to any operational station with an available return slot.

If a return station is full, the customer will be shown another nearby station.

If a rental release or return fails, the customer will receive a clear error message and support instructions where required.

Guest or minimal-registration rentals will be supported.

Active rentals will show start time, elapsed time, current price, status and available return locations.

## Decisions

- Exact station availability will be shown to customers.
- Cross-station returns are allowed.
- Guest/minimal-registration rentals are allowed.
- Failed rentals and returns must be handled clearly.
- Active rental information must be available to customers.

## Actions

- Team A to update requirements using the confirmed information.
- Team A and Team B to confirm who owns pricing, late-fee and rental-duration rules.
- Team A and Team B to confirm the exact rental details exchanged when a rental starts.

## Next Meeting

- **Date:** To be confirmed