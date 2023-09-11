## Download House Financial Disclosure Reports

This Python script fetches and processes financial disclosure reports from the website of the United States House of Representatives. The primary goal of this tool is to automate the retrieval and preliminary processing of these reports, making them easily accessible for further analysis.

### Overview:
Here is a step-by-step breakdown of the script's functionality:

1. **Importing required libraries:** 
   - Utilizes the following libraries: `datetime`, `wget`, `pandas`, `zipfile`, `xmlutils`, and `os.path`.

2. **Getting the current date and year:** 
   - Determines the current year and date using the `datetime` library.

3. **Downloading the ZIP file:** 
   - Uses the `wget` library to fetch the ZIP file containing the financial disclosure reports for the present year directly from the U.S. House of Representatives' website.

4. **Extracting the XML file:** 
   - Employs the `zipfile` library to extract the XML content from the recently downloaded ZIP file.

5. **Converting XML to CSV:** 
   - Makes use of the `xmlutils` library to transform the XML file into a more manageable CSV format.

6. **Getting the last 10 days' data and sorting the list:** 
   - Uses the `pandas` library to:
     - Load the CSV data.
     - Filter records from the past 40 days (despite the "last 10 days" name, the script actually extracts the last 40 days of data).
     - Sort these records by their filing date in descending order.
     - Save this processed data into a new CSV file.

7. **Getting the document IDs:** 
   - Extracts document IDs from the sorted CSV, storing them in a list for easy access.

8. **Downloading the PDF files:** 
   - Again, taps into the `wget` library to download the PDF files for each document ID.
   - Only downloads if the PDF does not already reside on the user's local machine, ensuring no redundant downloads.

9. **Cleaning up files:** 
   - Deletes any intermediate files created during the process. This includes the initial ZIP file, XML content, and all generated CSV files, ensuring a clean workspace post-execution.

10. **Completion Notification:** 
   - Upon successful execution, the script proudly announces its completion with a "DONE!!!" message.

### How to Use:
1. Ensure you have all the mentioned libraries installed in your Python environment.
2. Clone or download the script from this GitHub repository.
3. Execute the script in your preferred Python environment or terminal.
4. Once the script completes, you should have the desired PDFs downloaded in the specified directory.

### Notes:
- Always ensure you have the required storage space available, especially if running this script frequently, as financial disclosure reports can be sizable.
- Regularly check the U.S. House of Representatives' website structure. If they undergo any structural changes to their site or the way reports are stored, the script might need adjustments.
