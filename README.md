# Cookie Sales Analysis & Data Modeling in Power BI

## Descrierea proiectului
Un proiect practic de analiză a vânzărilor de biscuiți/prăjituri (**Cookie Sales**), axat pe construirea unui model de date relațional, crearea de coloane și măsuri calculate în DAX și vizualizarea KPI-urilor cheie pentru performanța clienților și profitabilitate.

---

## 1. Setul de date & Arhitectura modelului (Star Schema)
Modelul conectează trei tabele principale prin relații de tip **1:N** (*One-to-Many*):

* **Customers:** Tabel de dimensiune ce conține date despre clienți (`Customer ID`, `Name`, `Address`, `City`, `State`, etc.).
* **Orders:** Tabel de fapte ce înregistrează tranzacțiile individuale (`Order ID`, `Customer ID`, `Product`, `Units Sold`, `Date`, `Revenue`, `Cost`).
* **Cookie Types:** Tabel de dimensiune/nomenclator cu tipurile de prăjituri (`Cookie Type`, `Revenue Per Cookie`, `Cost Per Cookie`).

---

## 2. Calcule DAX & Logică de Business
* **Coloană calculată (*Calculated Column*):** `Profit = Orders[Revenue] - Orders[Cost]` – adăugată la nivel de rând în tabelul `Orders` pentru determinarea mecanică a profitului per comandă.
* **Măsuri explicite (*Measures*):** Utilizarea funcțiilor de agregare și iterare (`SUM`, `COUNT`, `DISTINCT`, `CALCULATE`, precum și funcții de timp/date și operatori logici `IF`).
* **Analiză clienți:** Calculul clienților unici (`DISTINCT`) și numărarea volumului total de comenzi (`Count of Orders`).

---

## 3. Vizualizări & Dashboard
* **Grafice de bare (*Clustered Bar / Column Charts*):** Compararea unităților vândute per client (*Total number of Units Sold după Name*) și analiza numărului de comenzi.
* **Tabele sintetice (*Matrix/Table Visuals*):** Centralizarea vânzărilor, costurilor, veniturilor și a profitului total per client (*Total Profit*, *Distinct of Customers*, *Revenue - Cost*).
