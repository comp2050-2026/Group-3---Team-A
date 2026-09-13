# the Client Requirements Clarification

# DATE
    2026-09-07

# MEETING PLACE
    Marquarie University Library

# PRESENT:
 - Harrison McLuckie 
 - Cooper Went 
 - Isaac Lynn 
 - Yousef Mustafa 

# APOLOGIES:
- None

# MINUTE TAKER:
- Isaac Lynn

# AGENDA
1. Clarify exact data payloads exchanged between ChargeMate Customer (Team A) and ChargeMate Ops (the Client).
2. Confirm rental, return, and error-handling operational responsibilities with the Client.
3. Finalize SRS artifacts v0.3 – v0.6 for main branch merge.

# DISCUSSION SUMMARY
- the Client confirmed that ChargeMate Customer will receive station location, exact available power bank counts, individual charge status, open return slots, and station online/offline state.
- For rentals, ChargeMate Customer sends power bank ID, station ID, and transaction details; Ops confirms physical release.
- For returns, Customer sends power bank ID and return station ID.
- If a station is full or release fails, clear error messages and nearby station recommendations must be presented.
- Active rentals will show start time, elapsed time, current cost, and return options.

# DECISIONS
- Exact station availability numbers will be displayed to users.
- Cross-station returns and guest/minimal-registration rentals are permitted.
- Approved Pull Request #1 merging SRS baseline versions v0.3 to v0.6.

# ACTIONS
- Yousef: Merge PR #1 (Overall Description, Context Diagram, Stakeholder Q&A v0.3, v0.6).
- Cooper: Apply wording/typo corrections across overall description (v0.4).
- Harrison: Integrate complete SRS Table of Contents and standardise minute layout (v0.5).
- Isaac: Review merged v0.3-v0.6 PRs and audit technical terminology across FR fit criteria.

# NEXT MEETING
    2026-09-11
