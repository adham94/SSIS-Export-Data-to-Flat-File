# SSIS-Export-Data-to-Flat-File

Build a SSIS package that will query a SQL server table and export  the data into a flat file. 
Can choose where it is delivered or what directory and automate the naming of the file with a date format.
Can schedule this via SQL Job Agent for automated delivery of flat files to customer or Can run it using DTEXEC.EXE Command Line Utility.

-- expression for file name by today date
(DT_WSTR,4)DATEPART("yyyy",GETDATE()) + Right("0"+(DT_WSTR,2)DATEPART("mm",GetDate()),2) + RIGHT("0"+(DT_WSTR,2)DATEPART("dd",GetDate()),2) + "_flatefile.txt"

-- output file path
D:\Project\source\repos\SSIS File

-- run ssis package using DTEXEC.EXE Command Line
C:\Program Files\Microsoft SQL Server\150\DTS\Binn>DTExec.exe /F "C:\Users\muhda\source\repos\FicoXMLExport\FicoXMLExport\Package.dtsx"
