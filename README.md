# ABAP-Project
# SAP ABAP ALV Report – Bank Details

This project is an **ABAP ALV Grid Report** developed in SAP ECC to display and manage customer bank account details and transaction history using **Custom Tables and Structures**.

---

## Project Overview

This report allows users to:
- Display bank account details from the master table.
- Filter accounts using a selection range.
- View transaction history of a selected account via hotspot click.
- Delete transactions interactively using confirmation popups.

---

## Components Used

| Object Type | Name | Description |
|--------------|------|-------------|
| Transparent Table | `ZBANK_MASTER1` | Bank Master Table |
| Transparent Table | `ZBANK_HISTORY1` | Bank Transaction History |
| Structure | `ZSTR_BANK_ALV` | Combined Structure for ALV Display |
| Report | `ZBANK_ALV` | Main ABAP Report Program |

---

## Screenshots

### Dictionary Tables
- `ZBANK_MASTER1` – Bank Master Data  
- `ZBANK_HISTORY1` – Transaction History  

### Report Outputs
- **Selection Screen:** Choose account range.  
- **Main ALV Display:** View bank details.  
- **Transaction ALV:** View transaction details by clicking on an Account No.

---

## Technologies Used
- ABAP Programming
- ALV Grid Display (`REUSE_ALV_GRID_DISPLAY`)
- Data Dictionary Objects (Tables, Structures)
- Function Modules (POPUP_TO_CONFIRM)
- SE11 / SE38 / SE80 Transactions

---

## How to Run
1. Create the Data Dictionary tables (`ZBANK_MASTER1`, `ZBANK_HISTORY1`) and structure (`ZSTR_BANK_ALV`).
2. Copy the code from `ABAP_Code/Bank_ALV_Report.abap` into a report (`ZBANK_ALV`) in SE38.
3. Activate and execute.
4. Enter an account number range and display the ALV results.

---

