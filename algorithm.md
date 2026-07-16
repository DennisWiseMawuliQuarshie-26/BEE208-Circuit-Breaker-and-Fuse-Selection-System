Start.
Display the project title.
Ask the user to enter the number of circuits.
Repeat until all circuits have been processed.
 Enter:
   - Circuit Name
   - Supply Voltage
   - Total Load Power

Validate the inputs.
 If voltage or power is less than or equal to zero:
   - Display an error message.
   - Request the user to enter the values again.

Calculate Load Current.
   Load Current = Total Power / Supply Voltage

Calculate Design Current.
   Design Current = Load Current × 1.25

Compare the design current with the standard breaker ratings.

Select the nearest suitable standard rating.

If the design current exceeds 63 A:
    - Display a warning message.

Display the protection report.

Save the report into **protection_report.txt**.

Repeat for the next circuit.
16. S.
