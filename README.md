# Project-Phishing-Email
This is a side project I created in C that allows a user to check if their email is a phishing attempt or not. This program is designed to analyze a text file, typically representing an email message. It scans the text for predefined keywords, tracks their freq and importance based on predefined categories. 


In depth details: 

This program is designed to analyze a text file, typically representing an email message, and determine its "phishiness" by looking for specific keywords and characteristics commonly associated with phishing emails. Here's an explanation of how the program works:

1. **Initialization and File Handling:**
   - The program starts by initializing various variables, including arrays for storing keywords, counters for tracking keyword occurrences, and a score variable to assess the email's phishiness.
   - It opens a file called "email.txt" for reading.

2. **Reading and Displaying the Email:**
   - The program reads the contents of the "email.txt" file character by character and displays the email on the screen as it reads it. This allows the user to see the content of the email.

3. **Scanning for Phishing Keywords:**
   - The program contains three arrays (`poorBait`, `likelyBait`, and `extremeBait`) that hold different keywords or phrases that are indicative of phishing emails. These arrays represent three levels of phishiness, with `poorBait` being the least suspicious and `extremeBait` being the most suspicious.

4. **Keyword Scanning and Counting:**
   - The program scans each line of the email for the presence of keywords from the three arrays using the `scanForStrings` function. The function counts the occurrences of keywords and returns a score based on the level of keywords found (1 for poor, 2 for likely, and 3 for extreme).
   - Additionally, the program checks for misspelled words using the `scanForMisspelling` function, adding to the `misspeltCounter` if a word does not contain any vowels or numbers.

5. **Displaying Keyword Occurrences:**
   - After scanning the entire email, the program displays a summary of the identified keywords, their levels, and the frequency of their occurrences.

6. **Calculating the Overall Phishiness Score:**
   - The program calculates an overall phishiness score by weighting the counts of keywords from different levels (poor, likely, extreme) and adding the count of misspelled words.
   - The score is calculated as follows:
     ```
     score = (poorCounter) + (likelyCounter * 2) + (extremeCounter * 3) + misspeltCounter
     ```

7. **Displaying Phishiness Assessment:**
   - Based on the calculated score, the program provides an assessment of the email's phishiness. There are three possible assessments:
     - If `extremeCounter` is greater than or equal to `likelyCounter`, it is considered extremely likely to be a phishing email.
     - If `likelyCounter` is greater than `poorCounter`, it is considered moderately likely to be a phishing email.
     - If `poorCounter` is greater than or equal to `likelyCounter` and `extremeCounter`, it is considered most likely a legitimate email.

8. **Displaying a Histogram:**
   - The program displays a simple histogram showing the distribution of phishiness levels based on the occurrences of each level (poor, likely, extreme).

9. **Program Termination:**
   - The program returns 0 to indicate successful execution.

Overall, this program provides a basic analysis of the phishiness of an email by identifying certain keywords and characteristics. However, it's important to note that real-world phishing emails can be more sophisticated, and this program's accuracy may vary depending on the complexity of the email being analyzed. 

Enjoy! :)
