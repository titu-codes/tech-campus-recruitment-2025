Plan
Input and Output: We will receive a date in the format YYYY-MM-DD as an argument. The output will be saved to a file in the format output/output_YYYY-MM-DD.txt.
Efficient Processing: Given the file's size (1 TB), we need to read it line by line instead of loading it entirely into memory. This ensures that memory usage stays manageable.
Date Filtering: The logs are in the format YYYY-MM-DD HH:MM:SS LOG_LEVEL Message, so we can simply check if the log starts with the target date to determine if it should be included.
Approach
1. Line-by-line processing: Read the log file line by line.
2. Date matching: For each line, check if it starts with the specified date.
3. Write to output: If the line matches the date, write it to the output file.
4. Error handling: Ensure proper handling of missing or incorrect files, as well as invalid command-line arguments.


Explanation of the Code:
1. Input Handling: The script takes a date string (YYYY-MM-DD) as a command-line argument.
2. Directory Creation: If the output directory (output/) does not exist, it will be created using os.makedirs().
3. File Processing: The log file is opened for reading line by line. Each line is checked to see if it starts with the target date. If it does, the line is written to the output file.
4. Error Handling: If the log file is not found or an unexpected error occurs, a message is printed.
5. Date Validation: A helper function ensures that the input date is in the correct YYYY-MM-DD format before proceeding.
6. Efficiency: This approach minimizes memory usage by reading the file line by line and directly writing relevant entries to disk.

search for logs from 2024-12-01 and output them into a file named output/output_2024-12-01.txt. 
**python extract_logs.py 2024-12-01**
