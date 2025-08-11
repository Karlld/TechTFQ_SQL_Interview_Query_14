```sql

WITH RECURSIVE serial_nums AS (SELECT MIN(serial_no) AS serial_no,
							         MAX(serial_no) AS max_serial_no
							  FROM invoice
							  
							  UNION ALL
							  
							  SELECT serial_no+1 AS serial_no,
							         max_serial_no
							  FROM serial_nums 
							  WHERE serial_no < max_serial_no),
							  
				matched_no AS (SELECT s.serial_no AS serial_num,
				                      i.serial_no AS inv_num
			                      FROM serial_nums AS s
				                  LEFT JOIN invoice AS i ON s.serial_no = i.serial_no)
	 
	 SELECT serial_num AS missing_serial_no
	     FROM matched_no 
	     WHERE inv_num ISNULL
	     ORDER BY serial_num;

```

| missing_serial_no |
|-------------------|
| 330116 |
| 330117 |
| 330118 |
| 330119 |
| 330123 |
| 330124 |
