C1 compliance 


Screen ID
Section / Component Type
Component Name
Input Type / Format
Length / Size
Required
Validation & Logic (C1 Rules)
Trigger / Event
Action / Behavior
EMS-SW-01
Screen Overview
Facility Search Screen
-
-
-
Mobile Only. Used to search for a Facility ID to access data.
App Launch
Display Screen.
EMS-SW-01
Input Item
Facility ID Input
Textbox
6 chars
No
Must be exact match.
Press [Search]
Check if ID exists.
EMS-SW-01
System Logic
ID Validation
-
-
-
Correlation Check: Verify ID against master data.
ID Not Found
Display Error Popup ("ID does not exist").
EMS-SW-01
System Logic
ID Validation (Success)
-
-
-
Correlation Check: ID is valid.
ID Found
Transition to EMS-SW-02 (Pass ID).
EMS-SW-01
Action Item
OK Button
Button
-
-
-
Press [OK] (in Popup)
Close Popup; Return to Input.


















EMS-SW-02
Screen Overview
Power Consumption Confirmation (Current)
-
-
-
Mobile Only. Displays current and daily power totals.
Initial Display
Load data for Facility ID.
EMS-SW-02
Display Item
Facility Name
Text (Read-only)
30 chars
-
Display registered name.
-
Static Display.
EMS-SW-02
Display Item
Location Info
Text (Read-only)
50 chars
-
Display registered city.
-
Static Display.
EMS-SW-02
Display Item
Measurement Target Period
Text
17 chars
-
Format: yyyy/mm/dd hh:00~hh:00.
System Time Update
Display most recent 1-hour block.
EMS-SW-02
Display Item
Cumulative Generation Power
Text
Variable
-
Format: 99999kWh.
API Batch (Hourly)
Display total accumulated value.
EMS-SW-02
Display Item
Current Generation Power
Numeric
Variable
-
3 Decimal places. Logic: Sum of two 30-min API points / 1000.
API Batch (Hourly)
Display real-time value for last hour.
EMS-SW-02
Display Item
Current Self-Consumption
Numeric
Variable
-
3 Decimal places. Logic: (Gen - Sold) sum / 1000.
API Batch (Hourly)
Display real-time value for last hour.
EMS-SW-02
Display Item
Current Usage Power
Numeric
Variable
-
3 Decimal places. Logic: (Self-Cons + Bought) sum / 1000.
API Batch (Hourly)
Display real-time value for last hour.
EMS-SW-02
Display Item
Daily Total Generation
Numeric
Variable
-
3 Decimal places. Logic: Sum of hourly values from 00:00.
API Batch (Hourly)
Update daily sum.
EMS-SW-02
Display Item
Daily Total Self-Consumption
Numeric
Variable
-
3 Decimal places. Logic: Sum of hourly values from 00:00.
API Batch (Hourly)
Update daily sum.
EMS-SW-02
Display Item
Daily Total Usage Power
Numeric
Variable
-
3 Decimal places. Logic: Sum of hourly values from 00:00.
API Batch (Hourly)
Update daily sum.
EMS-SW-02
Navigation
Power Consumption History Button
Button
-
-
-
Press Button
Transition to EMS-SW-03 (Time-period View).
EMS-SW-02
Navigation
Facility Search Button
Button
-
-
-
Press Button
Transition to EMS-SW-01.


















EMS-SW-03
Screen Overview
Power Consumption History
-
-
-
Mobile Only. Graphical history (Time-period/Daily/Monthly).
Initial Display
Load default graph (Time-period).
EMS-SW-03
Input Item
Display Type (Radio)
Radio Button
-
-
Options: Time-period, Daily, Monthly.
Select Option
Switch Graph UI / Input Fields.
EMS-SW-03
Input Item
Date Selection (Time-period)
Textbox / Calendar
YYYY/MM/DD
-
Select specific day.
Press Icon
Open Calendar; Save selection.
EMS-SW-03
Input Item
Month Selection (Daily)
Textbox / Calendar
YYYY/MM
-
Select specific month.
Press Icon
Open Calendar; Save selection.
EMS-SW-03
Input Item
Start Month (Monthly)
Textbox / Calendar
YYYY/MM
-
Default: Jan 1st. Same year only.
Press Icon
Open Calendar; Save selection.
EMS-SW-03
Input Item
End Month (Monthly)
Textbox / Calendar
YYYY/MM
-
Default: Dec 31st. Same year only.
Press Icon
Open Calendar; Save selection.
EMS-SW-03
Action Item
Search Button
Button
-
-
-
Press Button
Fetch data for selected range/date.
EMS-SW-03
Display Item
Graph Area (All Views)
Chart
-
-
Displays Gen, Self-Cons, Usage bars.
Data Fetch
Render Graph.
EMS-SW-03
System Logic
Graph Overflow Handling
-
-
-
-
Graph Width > Screen Width
Enable Horizontal Scroll.
EMS-SW-03
Navigation
Current Value Confirmation Button
Button
-
-
-
Press Button
Transition to EMS-SW-02.

