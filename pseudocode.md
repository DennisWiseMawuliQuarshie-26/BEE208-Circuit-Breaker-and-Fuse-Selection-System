```
START
 Display welcome message
 Display project title
 Ask for number of circuits

IF number of circuits is less than or equal to 0 THEN
    Display error message
    STOP
END IF

Open protection_report.txt for writing

FOR each circuit from 1 to number of circuits DO
    REPEAT
        Read circuit name
        Read supply voltage
        Read total power
    UNTIL supply voltage > 0 AND total power > 0

    loadCurrent = totalPower / supplyVoltage
    designCurrent = loadCurrent * 1.25

    recommendedRating = NONE
    FOR each standard rating in [6, 10, 16, 20, 25, 32, 40, 63] DO
        IF rating >= designCurrent THEN
            recommendedRating = rating
            EXIT loop
        END IF
    END FOR

    Display protection report
    Save protection report to file
 END FOR

 Close file
 Display message that report has been saved
 STOP
