# TechTFQ_SQL_Interview_Query_14


PROBLEM STATEMENT: In the given input table, some of the invoice are missing,
write a sql query to identify the missing serial no. As an assumption, 
consider the serial no with the lowest value to be the first generated invoice
and the highest serial no value to be the last generated invoice

```sql

DROP TABLE IF EXISTS invoice;

CREATE TABLE invoice ( serial_no  INT,
                       invoice_date	DATE
                      );

INSERT INTO invoice VALUES (330115, to_date('01-Mar-2024','DD-MON-YYYY'));
INSERT INTO invoice VALUES (330120, to_date('01-Mar-2024','DD-MON-YYYY'));
INSERT INTO invoice VALUES (330121, to_date('01-Mar-2024','DD-MON-YYYY'));
INSERT INTO invoice VALUES (330122, to_date('02-Mar-2024','DD-MON-YYYY'));
INSERT INTO invoice VALUES (330125, to_date('02-Mar-2024','DD-MON-YYYY'));

SELECT * FROM invoice;
```

| serial_no | invoice_date |
|-----------|--------------|
| 330115	| 2024-03-01 |
| 330120	| 2024-03-01 |
| 330121	| 2024-03-01 |
| 330122	| 2024-03-02 |
| 330125	| 2024-03-02 |
