# Circuit Breaker and Fuse Selection System

## Group Members and Index Numbers
PRESENTATION FOR GROUP 2.1
NAMES OF MEMBERS	             INDEX NUMBERS	             ROLE/CONTRIBUTIONS
ENYOWU JUSTICE KWAME	            01245565B	             Project Lead
OFOSU DAVID OPOKU	               01243218B	             Algorithm Writer
AMUYAO FESTUS KWETEY	            01244186B	             Pseudocode Writer
MISBAAHU FUSEINI	               01240271B	             Flowchat Designer
RICHMOND AFARI	                  01245919B	             C++ Programmer
EZRA ARMOO ENISON	               01243736B	             C++ Programmer
BENSAH JUNIOR JOSEPH	            01242875B	             Testing Lead
QUARSHIE DENNIS WISE		         01242874B                GitHub Manager
LEMBOE MARVELOUS MARSHAL	      01242579B	             Documentation Lead
MARTIN BABILAH	                  01240920B	             Presentation Lead


## Course Name and Code

Introduction to Computer Programming **(BEE 208)**

## Department and Faculty

ELECTRICALS AND ELECTRONICS ENGINEERING
FACULTY OF ENGINEERING

## Introduction

These design is done in order to prevent damage to electrical circuit and also prevent fire outbreak from electrical fault. In view of that we are Designing a Breaker or Fuse selection system that estimates load current and recommends a suitable protective device rating for small electrical circuit and household.

## Problem Statement

SO many users do not know how to select a suitable circuit breaker or fuse rating for a small electrical load. Some users or technicians choose a rating that is too low, causing frequent tripping. Whiles Others choose a rating that is too high, reducing protection and increasing safety risk such as damage to Gadget or cause fire outbreak.

## Aim and Objective

The aim of this project is to design and implement a C++ program that automates the selection of appropriate circuit breakers and fuses for electrical circuits based on load requirements, ensuring safety, efficiency, and compliance with standard ratings.

### Objective

- To develop a program that accepts user input for circuit parameters (name, supply voltage, and total load power).
- To calculate the load current and design current using standard engineering formulas.
- To compare the design current against a list of standard breaker/fuse ratings and recommend the most suitable device.
- To handle invalid inputs gracefully through validation checks.
- To generate a clear protection report for each circuit, displaying results both on-screen and saving them to a text file.
- To improve readability and maintainability of the code by using structured programming concepts such as loops, conditionals, and functions.
- To ensure the program is beginner-friendly while still meeting professional engineering documentation standards.

## Features of the Application

### User Input Handling

- Accepts multiple circuits in one run.
- Prompts for circuit name, supply voltage, and total load power.
- Validates inputs to ensure only positive values are accepted.

### Automated Calculations

- Computes the load current using I(load) = P / V
- Computes design current using I(design) = I(load) x 1.25
- Applies engineering safety factors automatically

### Protection Device Recommendation

- Compares design current against a list of standard breaker/fuse ratings (6 A, 10 A, 16 A, 20 A, 25 A, 32 A, 40 A, 63 A).
- Selects the smallest suitable rating.
- Provides a warning if design current exceeds available ratings.

### Object-Oriented Design

- Encapsulates circuit details and calculations in a class (CircuitProtection).
- Ensures modularity, reusability, and clean separation of logic.

### Report Generation

- Displays a clear protection report for each circuit on-screen.
- Saves the same report to a text file (protection_report.txt) for documentation.

### Error Handling

- Don't skip invalid circuits instead let the user try again.
- Provides user-friendly error messages.

### Scalability

- Supports multiple circuits in one execution.
- Each circuit is treated independently using separate objects.

This application is a practical engineering tool that combines OOP principles, automated calculations, and file handling to make circuit protection selection efficient, accurate, and well-documented.

## C++ Concepts

- Input and Output like `#include<iostream>`
- Variables and data types such as int, double, and string e.g. `double LoadCurrent`
- Operators and expressions
- Conditional statement
- Loops
- Functions
- Arrays or vectors
- Classes and Objects
- File handling
- Input validation
- Comment and readable code

## How to Run the Programme

1. Run the executable.
2. Enter the number of circuits to assess.
3. For each circuit, enter:
   - circuit name
   - supply voltage in volts
   - total load power in watts
4. The program will display the protection report and save it to protection_report.txt.

## Algorithm

1. Start
2. Display a welcome message and project title.
3. Ask the user how many circuits need to be assessed.
4. For each circuit:
   - input the circuit name, supply voltage, and total power
   - check whether the voltage and power values are positive
   - if invalid, ask the user to re-enter the values
   - calculate load current using I = TotalPower/SupplyVoltage
   - calculate design current using I(design) = LoadCurrent x 1.25
   - compare the design current with standard protection ratings
   - select the smallest standard rating that is greater than or equal to the design current
   - display and save the protection report
5. Save all reports to protection_report.txt.
6. Stop

## Pseudocode
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

## Future Improvements

Possible enhancements for the program include:

- add support for different electrical standards and country-specific breaker ratings
- allow the user to choose between fuse and circuit breaker recommendations
- add error handling for invalid text input and unexpected values
- improve the output format with tables or formatted reports
- save results in CSV or JSON files for easier analysis
- add a graphical user interface (GUI) for easier use
- include safety factors and additional electrical parameters such as cable size and voltage drop
