# DATA-ENGINEERING-
CREATING DTATA FRAME USING PYTHON AND USING  SQL WE WILL CREATE TABLE BY ACCECPTING GLOBAL DATA AND WILL IMPORT THEM AND ACCESS / READING THEM &lt;&lt;&lt;&lt;&lt;&lt;
/*CREATEING TABLE AS FOR THE DATA HISTORY MENTIONED ON PDF .
1)THE DESCRIPTION SAID THAT WE NEED TO CATAGORISED DATA ACCORDING TO CONTRY.
2)THE DATA IS AVAIBALABE ON GLOBAL FORM .
3)MY TABLE_NAME IS CONTRY_CUSTOMER_DATA .
4)MY FILE NAME WOULD BE LIKE CONTRY_DATA.CSV(String file name)   */
----------------------------------------
CREATE TABLE CONTRYCUSTOMERDATA 
(
     Customer_Name VARCHAR (255)NOT NULL,
     Customer_id VARCHAR (18) NOT NULL,
     Open_date DATE NOT NULL,
     Last_Consulated_Date DATE NOT NULL,
     Vaccination_id CHAR (5)NOT NULL,
     Dr_name CHAR (255)NOT NULL,
     State CHAR (5)NOT NULL,
     Country CHAR (5) NOT NULL,
     Post_code INT(5)NOT NULL,
     DOB DATE NOT NULL,
     Active_customer CHAR (1) NOT NULL
);

INSERT INTO CONTRYCUSTOMERDATA VALUES ('Alex','123457','20101012','20121013','MVD','Paul','SA','USA',13288,'1991-04-02','A');
INSERT INTO CONTRYCUSTOMERDATA VALUES ('John','123458','20101012','20121013','MVD','TN','LA','USA',10873,'1991-04-02','A');
INSERT INTO CONTRYCUSTOMERDATA VALUES ('Matew','123459','20101012','20121013','MVD','DRt','LA','USA',10303,'1991-04-02','A');
INSERT INTO CONTRYCUSTOMERDATA VALUES ('matt','12345','20101012','20121013','MVD','VIC','BO','USA',10389,'1991-04-02','A');
INSERT INTO CONTRYCUSTOMERDATA VALUES ('jacob','1256','20101012','20121013','MVD','BOC','NJ','USA',10754'1991-04-02','A');
-----------------------------------------
Select * From CONTRYCUSTOMERDATA ;

OUT PUT -
-------------------------------------------
Alex|123457|20101012|20121013|MVD|Paul|SA|USA|10303|1991-04-02|A
John|123458|20101012|20121013|MVD|TN|LA|USA|10303|1991-04-02|A
Matew|123459|20101012|20121013|MVD|DRt|LA|USA|10303|1991-04-02|A
matt|12345|20101012|20121013|MVD|VIC|BO|USA|10303|1991-04-02|A
jacob|1256|20101012|20121013|MVD|BOC|NJ|USA|10303|1991-04-02|A
-------------------------------------------
CREATING DATA FRAME USING PYTHON *************
------------------------------------
GLOBAL_DATA = {
     'Customer_Name':['Alex','John','Mathew','Matt','Jacob'],
     'Customer_id':[123457,123458,123459,12345,1256],
     'Open_date':['20101012','20101012','20101012','20101012','20101012',], 
     'Last_Consulated_Date':['20121013','20121013','20121013','20121013','20121013',], 
     'Vaccination_id':['MVD','MVD','MVD','MVD','MVD',], 
     'Dr_name CHAR':['Paul','Paul','Paul','Paul','Paul',],
     'State':['SA','TN','WAS','BOS','VIS'],
     'Country':['USA','IND','PHIL','NYC','AU'],
     'Post_code':['06031987','06031987','06031987','06031987','06031987',],
     'Active_customer':['A','A','A','A','A'] 
}
df = pd.DataFrame(GLOBAL_DATA)
df
-----
OUTPUT::

Customer_Name	Customer_id	Open_date	Last_Consulated_Date	Vaccination_id	Dr_name CHAR	State	Country	Post_code	Active_customer
0	Alex	123457	20101012	20121013	MVD	Paul	SA	USA	06031987	A
1	John	123458	20101012	20121013	MVD	Paul	TN	IND	06031987	A
2	Mathew	123459	20101012	20121013	MVD	Paul	WAS	PHIL	06031987	A
3	Matt	12345	20101012	20121013	MVD	Paul	BOS	NYC	06031987	A
4	Jacob	1256	20101012	20121013	MVD	Paul	VIS	AU	06031987	A
------------------

**********************************************************
IMPORTING DATA FROM DATABASE AS A CSV FILE 
**********************************************************
SQL> set pagesize 0
SQL> spool c:\CONTRY_DATA.CSV
SQL> Select Customer_Name||','||Customer_id||','||Open_date||','||Last_Consulated_Date DATE||','||Vaccination_id||',
'||Dr_name||','||Country||','||Post||','||DOB||','||Active_customer from CONTRYCUSTOMERDATA;  
SQL> spool off
***********************************************************
Python Program to read and analysing the Data By Using pands )
------------------------------------------------------------

Import pandas as pd
Import numpy as nm

df = pd.read_csv(r"c:\CONTRY_DATA.CSV")
Print(df.head(4))
Desc df
 
