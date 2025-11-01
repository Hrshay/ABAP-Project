# SAP CDS View + ABAP ALV Integration Project

This project demonstrates how to integrate a **Core Data Services (CDS) View** in SAP HANA with an **ABAP ALV Report**.  
It joins custom **Bank Master Data** with **Sales Order Data (VBAK)** and displays the combined result using ALV Grid.

---

## Project Overview

### Objective
To create a parameterized CDS view that joins two data sources (`zbank_master1_co` and `vbak`)  
and visualize the results in an ALV grid from an ABAP report.

---

## Components

| Object Type | Name | Description |
|--------------|------|-------------|
| CDS View | `ZC_BANK_VBAK_JOIN` | Joins bank and sales order data |
| SQL View | `ZSV_BANKJOIN` | Underlying SQL view |
| ABAP Report | `ZREP_BANK_VBAK_ALV` | Reads CDS output and displays ALV grid |

---

## CDS View Code (ZC_BANK_VBAK_JOIN)

```abap
@AbapCatalog.sqlViewName: 'ZSV_BANKJOIN'
@AccessControl.authorizationCheck: #NOT_REQUIRED
@EndUserText.label: 'Bank VBAK Join'

define view ZC_BANK_VBAK_JOIN
    with parameters P_KUNNR : kunnr
as select from zbank_master1_co as BANK
left outer join vbak
on BANK.kunnr = vbak.kunnr
{
   key BANK.kunnr,
   key BANK.account_no,
       BANK.name,
       BANK.bank_name,
       BANK.bank_city,
       BANK.bank_country,
       BANK.address,
       BANK.phone_no,
       BANK.email,
       BANK.branch,
       BANK.balance,
       BANK.status,
       vbak.vbeln,
       vbak.erdat
}
where BANK.kunnr = :P_KUNNR;
