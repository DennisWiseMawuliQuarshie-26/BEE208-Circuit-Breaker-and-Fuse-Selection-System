# Circuit Breaker/Fuse Selection System Algorithm

1.  **Start**

2.  Display a welcome message and the project title.

3.  Ask the user how many circuits need to be assessed.

4.  For each circuit:

    -   Input the circuit name.
    -   Input the supply voltage.
    -   Input the total power.
    -   Check whether the supply voltage and total power are positive
        values.
    -   If any value is invalid, ask the user to re-enter the values.
    -   Calculate the load current using:
        `Load Current = Total Power / Supply Voltage`
    -   Calculate the design current using:
        `Design Current = Load Current × 1.25`
    -   Compare the design current with the standard protection ratings.
    -   Select the smallest standard protection rating that is greater
        than or equal to the design current.
    -   Display the protection report.
    -   Save the protection report.

5.  Save all reports to a file named `protection_report.txt`.

6.  **Stop**
