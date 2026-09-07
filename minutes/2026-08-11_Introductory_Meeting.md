# MINUTES 2026-08-11

# DATE
    2026-08-11
# MEETING PLACE
    [room name for 2050 class]
# PRESENT:
 - Harrison Mcluckie
 - 
# APOLOGIES:
# MINUTE TAKER:

# AGENDA

# DISCUSSION SUMMARY
# DESCISIONS
What information will ChargeMate Customer receive from ChargeMate Ops about each rental station?
Station location? YES
Number of available power banks? YES
Whether banks are sufficiently charged?Yes
Number of available return slots? YES
Whether the station is online/offline or unavailable? YES
Should ChargeMate Customer receive exact numbers, such as “3 power banks available”, or only a simple available/unavailable status? Exact number
How frequently will station and power bank availability information be updated? Update whenever a rental, return, fault, or station status changes.
When a customer starts a rental, what information does our Customer system need to send to ChargeMate Ops? Send the power bank ID, station ID and rental details needed to record the rental.
What information will ChargeMate Ops send back to confirm that a rental has successfully started and a power bank has been released?Confirm that the rental has started successfully and identify the released power bank.
When a customer returns a power bank, what information does our system send to Ops, and what confirmation will Ops return when the return has been successfully recorded? Send the power bank ID and return station; confirm when the return has been successfully recorded.
Can a customer return a power bank to any ChargeMate station, or only to the station where it was originally rented? Allow customers to return power banks to any operational ChargeMate station with an available return slot.
What should happen if a customer tries to return a power bank but the selected station has no available return slots? Inform the customer and show another nearby station with available return slots.
What should happen if payment/rental authorisation succeeds but the station fails to release a power bank? Inform the customer that the release failed and cancel/reverse the unsuccessful rental or payment authorisation.
What should happen if the customer physically returns the power bank but the system does not recognise or confirm the return? Inform the customer that the return could not be confirmed and provide instructions to contact support/report the issue.
Which system is responsible for determining when a rental becomes overdue and calculating any late fees or additional charges — Customer or Ops? The Customer system should determine overdue rentals and calculate any applicable late fees.
Does ChargeMate Ops manage the pricing, deposit/pre-authorisation, late-fee and rental-duration information that our Customer system displays? Yes. The Customer system should manage and display pricing, deposits/pre-authorisation, late fees and rental-duration information.
Does Ops require the customer to have an account, or can rentals be completed as a guest/minimal-registration user? If customer details are required, what information does Ops need? Allow guest/minimal-registration rentals. Require only necessary contact and payment details.
What rental information should ChargeMate Customer be able to retrieve during an active rental, for example start time, elapsed time, price, return locations or rental status? Show start time, elapsed time, current price, rental status and available return locations.
Are there any error/status messages from ChargeMate Ops that the Customer system must specifically handle or display to the customer?Yes. Show clear messages for unavailable stations/power banks, no return slots, failed release/return and service errors.

# ACTIONS
# NEXT MEETING
    2026-08-18