# Download House Financial Disclosure Reports
 
The following Python script is used to download and process financial disclosure reports from the website of the United States House of Representatives. The script performs the following steps:

Importing required libraries: The script imports the datetime, wget, pandas, zipfile, xmlutils, and os.path libraries.

Getting the current date and year: The script uses the datetime library to retrieve the current date and year.

Downloading the ZIP file: The script uses the wget library to download the ZIP file containing the financial disclosure reports for the current year from the website of the US House of Representatives.

Extracting the XML file: The script uses the zipfile library to extract the XML file from the downloaded ZIP file.

Converting XML to CSV: The script uses the xmlutils library to convert the extracted XML file to a CSV file.

Getting the last 10 days' data and sorting the list: The script uses the pandas library to read the CSV file, filter the records to include only those from the last 40 days, sort the filtered records by the filing date in descending order, and write the sorted records to a new CSV file.

Getting the document IDs: The script retrieves the document IDs from the sorted CSV file and stores them in a list.

Downloading the PDF files: The script uses the wget library to download the PDF files for each document ID in the list, if the file does not already exist on the local system.

Cleaning up files: The script removes the intermediate files generated during the processing, including the ZIP file, the XML file, and the CSV files.

Printing 'DONE!!!': The script displays a message indicating that the process has completed successfully.