# Overview 

I developed a column design pipeline in Python to evaluate whether a selected column
meets Eurocode 3 design requirements with user input Design Variables:
Axial Force Above the Column, NEd
Column Load Conditions, FA, FB, FC & FD
Column Connections and Effective Length Factor from EN 1993-1-1 5.3.2.(1)
Steel Grade, fy
And Trial UC Section where Section Properties are imported from UC_Clean.csv which
contains all standard UC Sections from the Steel Blue Book (BS EN 10365: 2017)

## Testing of column_design.py

To ensure validity within the code I tested column_design.py with the variables from my Column Design Hand Calculations using the same design variables. 

![image](https://github.com/user-attachments/assets/38b6e5fd-3cfb-41f8-96ad-cb4babf42f22)
#### Figure 1 - User Input Design Variables

![image](https://github.com/user-attachments/assets/1ec3ff37-b215-4683-b3ad-544eafe8b1f8)
![image](https://github.com/user-attachments/assets/c4fb8eda-9876-48e3-ad00-d93ed91512bb)
#### Figures 2 & 3 - column_design.py Testing Results

![image](https://github.com/user-attachments/assets/abcae6e6-d7e3-4947-ab01-ed3d3c192681) 
#### Figure 4 - Column Design Hand Calculation Results

The minor discrepancies between the column hand calculation outputs are attributable to rounding, this test confirms that column_design.py can be reliably reused for future column sizing and optimisation tasks without the need to manually repeat calculations.
Furthermore, unlike manual methods prone to rounding and input error, the column_design.py ensures consistent calculation across multiple design variables and optimisations.

## Repository Structure

column_design.py
The Column Design Pipeline
UC_Clean.csv
A clean file of the UC Section Sizes from the SCI Steel Blue Book (BS EN 10365: 2017)
Sections cover UK National Annex dimensional and mass tables, guaranteeing compliance with UK practice

## Tools 

Python (Spyder)
- pandas
- math

## How I Used

I first used column_design.py to optimise my Second Floor to Roof column - this improved structural efficiency and reduced embodied carbon within my design.
I then used column_design.py to design my First to Second Floor and Ground to First Floor Columns, choosing the smallest section size within design limits.

## How to Use

Run column_design.py and enter the design variables and a trail UC section.
column_design.py will then complete checks for AXIAL BUCKLING RESISTANCE
LATERAL TORSIONAL BUCKLING
MINOR AXIS MOMENT CAPACITY
AND the COMBINED INTERACTION Check

The trial column will then PASS or FAIL the test

If PASS: to optimise the column reduce the section size and test again.

If FAIL: increase the UC section size and test again.
