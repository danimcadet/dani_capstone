JUST TESTING THAT I CAN DO THIS WITH RANDOM NOTES.

# Building Base Table

This repository is part of the Capstone project for the DDA9 program. The purpose of this repository is to build a base table that combines various datasets.

## Description

The following steps outline how to build the base table:

### Step 1: Import Files

Import the following files into a dataframe that are located at `C:\\Users\\dmcad\\Desktop\\DDA9\\Capstone` on the computer:

1. `carnegie_basic.csv` as `carnegie_full`
2. `ef2021d.csv` as `finance_full`
3. `emi.xlsx` as `emi_full`
4. `hd2021.csv` as `character_full`
5. `smi22.csv` as `socmo_full`

### Step 2: Create Base Dataframe

Create a new dataframe called `base` that follows the following merge rules:

1. Join on `Institution` in `emi_full` and `INSTNM` in `character_full`
2. Join `character_full` and `finance_full` on `UNITID`
3. Join on `Institution` in `socmo_full` and `INSTNM` in `character_full`

### Step 3: Select Columns

`base` should only hold the following columns:

1. From `emi_full`:
    1. `Institution` (renamed to `school`)
    2. `Control` (renamed to `control`)
    3. `Economic Mobility Index` (renamed to `emi`)
    4. `Low-income PEP Percentile Rank` (renamed to `pep_pell`)
2. From `character_full`:
    1. `UNITID` (renamed to `unitid`)
    2. `INSTNM` (match_check)
    3. `STABBR` (renamed to `state`)
    4. `ZIP` (renamed to `zip`)
    5. `LONGITUD` (renamed to `long`)
    6. `LATTITUDE` (renamed to `lat`)
    7. `NPRICURL` (renamed to `calc_url`)
    8. `HBCU` (renamed to `hbcu`)
    9. `LOCALE` (renamed to `setting`)
    10. `C21BASIC` (renamed to `c21basic`)
    11. `C21IPUG` (renamed to `c21ipug`)
    12. `INSTSIZE` (renamed to `size`)
3. From `finance_full`:
    1. `UNITID`
    2. `RET_PCF` (renamed to `retention`)
4. From `socmo_full`:
    1. `Institution`
    2. `Average Debt` (renamed to `coa`)
    3. `Endowment (in M)` (renamed to `endowment`)

## Requirements

- Python 3.7 or higher
- Pandas
- Numpy
