# Project Pseudocode: Circuit Breaker and Fuse Selection System

START

    // Module 1: Program Initialization and Variable Declarations
    PRINT "=================================================="
    PRINT "   CIRCUIT BREAKER AND FUSE SELECTION SYSTEM      "
    PRINT "=================================================="

    DECLARE standardRatings AS ARRAY OF FLOATS = [6.0, 10.0, 16.0, 20.0, 25.0, 32.0, 40.0, 63.0]
    DECLARE numCircuits AS INTEGER
    DECLARE circuitName AS STRING
    DECLARE supplyVoltage, totalPower, loadCurrent, designCurrent, recommendedRating AS FLOAT
    DECLARE protectionStatus AS STRING

    // Module 2: Safe Circuit Count Input Group Validation
    DO
        PRINT "Enter number of circuits to assess: "
        READ numCircuits
        IF numCircuits <= 0 OR INPUT_STREAM_FAILS THEN
            PRINT "[ERROR]: Invalid entry. Please enter a valid number of circuits."
            CLEAR_INPUT_STREAM_FLAGS()
            CLEAR_INPUT_BUFFER()
        END IF
    WHILE numCircuits <= 0 OR INPUT_STREAM_FAILS

    CLEAR_INPUT_BUFFER()

    // Module 3: Sequential Circuit Processing Loop
    FOR i = 0 TO numCircuits - 1 DO
        PRINT "\n>>> Assessing Circuit ", i + 1, " of ", numCircuits, " <<<"

        PRINT "Enter circuit name: "
        READ circuitName

        // Input Filtering Loop for Supply Voltage
        DO
            PRINT "Enter Supply Voltage in volts: "
            READ supplyVoltage
            IF supplyVoltage <= 0 OR INPUT_STREAM_FAILS THEN
                PRINT "[ERROR]: Invalid voltage. Please enter a positive number."
                CLEAR_INPUT_STREAM_FLAGS()
                CLEAR_INPUT_BUFFER()
            END IF
        WHILE supplyVoltage <= 0 OR INPUT_STREAM_FAILS

        // Input Filtering Loop for Total Power
        DO
            PRINT "Enter Total Power in Watts: "
            READ totalPower
            IF totalPower <= 0 OR INPUT_STREAM_FAILS THEN
                PRINT "[ERROR]: Invalid power. Please enter a positive number."
                CLEAR_INPUT_STREAM_FLAGS()
                CLEAR_INPUT_BUFFER()
            END IF
        WHILE totalPower <= 0 OR INPUT_STREAM_FAILS

        CLEAR_INPUT_BUFFER()

        // Module 4: Engineering System Mathematics
        SET loadCurrent = totalPower / supplyVoltage
        SET designCurrent = loadCurrent * 1.25

        // Module 5: Discrete Lookup Array Sizing Logic
        IF designCurrent > 63.0 THEN
            SET recommendedRating = 0.0
            SET protectionStatus = "WARNING: Design current exceeds maximum standard rating (63 A)!"
        ELSE
            FOR EACH rating IN standardRatings DO
                IF rating >= designCurrent THEN
                    SET recommendedRating = rating
                    SET protectionStatus = "Suitable standard rating found"
                    BREAK FOR LOOP
                END IF
            END FOR
        END IF

        // Module 6: Execution Report Generation Phase
        PRINT "----------------------------------------"
        PRINT "Circuit Name: ", circuitName
        PRINT "Supply Voltage: ", supplyVoltage, " V"
        PRINT "Total Power: ", totalPower, " W"
        PRINT "Load Current: ", CONVERT_TO_FIXED_DECIMAL(loadCurrent, 2), " A"
        PRINT "Design Current: ", CONVERT_TO_FIXED_DECIMAL(designCurrent, 2), " A"
        IF recommendedRating > 0 THEN
            PRINT "Recommended Protective Device: ", recommendedRating, " A"
        END IF
        PRINT "Status: ", protectionStatus
        PRINT "----------------------------------------"

        // Module 7: Local File System Logging Persistence
        OPEN FILE "protection_report.txt" IN APPEND MODE
        WRITE TO FILE "\n--- Circuit Record ---"
        WRITE TO FILE "Circuit Name: ", circuitName
        WRITE TO FILE "Supply Voltage: ", supplyVoltage, " V"
        WRITE TO FILE "Total Power: ", totalPower, " W"
        WRITE TO FILE "Load Current: ", CONVERT_TO_FIXED_DECIMAL(loadCurrent, 2), " A"
        WRITE TO FILE "Design Current: ", CONVERT_TO_FIXED_DECIMAL(designCurrent, 2), " A"
        IF recommendedRating > 0 THEN
            WRITE TO FILE "Recommended Device: ", recommendedRating, " A"
        END IF
        WRITE TO FILE "Status: ", protectionStatus
        WRITE TO FILE "----------------------"
        CLOSE FILE

    END FOR

    PRINT "\n[SUCCESS]: Protection selection report saved to protection_report.txt"
    PRINT "Thank you for using our tracking system. Goodbye!"

END