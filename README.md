# Multiple-Excel-Files-into-SQLite-Database
Getting data file names of 10 files 2009-2019 of aapl stock price data and loading into SQlite DB using openyxl, dataset, glob, sqlite3, pandas, and numpy
As suggested in Use Case 1 of the FTE, we need to read the other nine stock files and insert their data into the database. While nine files isn't an undue burden to manually read, we are going to look ahead to the time when we may have 100 log files to read and implement this code using the DRY Principle. DRY stands for

Don't Repeat Yourself So, while we could create an individual cell to read each stock file, for this assignment, do it in one. I'll give you some help to get started.

Reference: https://en.wikipedia.org/wiki/Don%27t_repeat_yourself

Much of computer science and programming is about identifying and exploiting patterns. In this case, we know there is a pattern to how the files are named, and we know (through inspection) that there is a pattern to the columns of data inside.

The file names all start with a year, from 2009 straight to 2019 with no breaks:

- 2009_aapl_data.xlsx 
- 2010_aapl_data.xlsx 
- 2011_aapl_data.xlsx 
- 2012_aapl_data.xlsx 
- 2013_aapl_data.xlsx 
- 2014_aapl_data.xlsx 
- 2015_aapl_data.xlsx 
- 2016_aapl_data.xlsx 
- 2017_aapl_data.xlsx 
- 2018_aapl_data.xlsx 
- 2019_aapl_data.xlsx 

Do we know of anything in Python capable of generating a range of numbers like that?
for x in range(2009, 2020): print(x) 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019  - That should be enough to get you going. Feel free to use code and helper functions from the FTE. I gave you the .ipynb file for a reason :).

Remember,

If you ran the FTE code, it will have already read in 2009 and created the database file. If you start at 2009, depending on the condition above, you may need to handle the table already existing. It is your choice whether or not to use the dataset library. As with many things in life, there are tradeoffs -- some things are easier, some not.

Deliverable:
When you are done, you will have a database table with slightly more than 2500 rows in it. Show this by doing a query that counts rows in the table. import dataset from openpyxl import load_workbook


Summary
In conclusion, we succesfully were able to load the 2009-2019 aapl_data.xslm files into a table. We were able to succesfully load all files with the pattern of the years in order using a slightly differnt method, glob.glob. This method was the cleanest in seting up a table for me in the week of practicing on this dataset, as it made the most sence to use this method for me. We were easily able to pull in all files and read them to a dataframe, which we could run all the desired queries, and also convert into a database at the end to store the data using SQLite. We found a count and printed all rows found when the stock closed lower then 25 ,𝑤ℎ𝑖𝑐ℎ𝑤𝑎𝑠𝑜𝑛𝑙𝑦6𝑑𝑎𝑦𝑠𝑡𝑜𝑡𝑎𝑙.𝑊𝑒𝑤𝑒𝑟𝑒𝑎𝑏𝑙𝑒𝑡𝑜𝑓𝑖𝑛𝑑𝑎𝑙𝑙𝑑𝑎𝑦𝑠𝑖𝑛2017𝑡ℎ𝑎𝑡𝑐𝑙𝑜𝑠𝑒𝑑𝑎𝑏𝑜𝑣𝑒35  a share, and also printed the last 5 found. We successfully converted the table we used into a database using SQLite. We used fetchall to query a search in the DB. We are now setup to do any query we would like. Convientently, we also now have the data in a dataframe with datetime setup for 'date' column and now we also have a database setup with the ability to query and manipulate wither as needed.

References:
Big Data file formats. (2020, April 23). Retrieved from https://luminousmen.com/post/big-data-file-formats.

Lawton, G. (2019, February 22). What to consider when choosing big data file formats. In Seach Business Analytics. Retrieved from https://searchbusinessanalytics.techtarget.com/feature/What-to-consider-when-choosing-big-data-file-formats.

