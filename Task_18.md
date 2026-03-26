## **Task 18: Linux System Troubleshooting — The Command Line Murders**

### **Description**

The core objective of this task was to resolve "The Command Line Murders," a sophisticated Linux troubleshooting scenario hosted on **SadServers**. This task simulates a real-world forensic investigation within a Linux environment, requiring the use of advanced CLI utilities to process unstructured data. The challenge involved navigating a dense directory structure, performing complex pattern matching across hundreds of files, and using logical deduction to identify a specific "murderer" based on a trail of digital evidence left in system logs and membership records.

### **Detailed Process**

- **Scene Investigation & Evidence Gathering:** I began by exploring the `clmystery` directory. I used `cat instructions` to understand the parameters of the case. My first technical action was to extract "Clues" from the primary crime scene report. I utilized `grep` with the `-i` flag (case-insensitive) to find leads:

  ```bash
  grep -i "CLUE" crimescene
  ```

  This revealed a key piece of evidence: the perpetrator was a male, over 6 feet tall, and held memberships in four specific organizations (AAA, Delta SkyMiles, Library, and the Museum of Bash History).

- **Suspect Filtering via Data Intersection:** The most technically demanding part of the task was finding the intersection of four large membership files located in the `memberships/` directory. To avoid manual searching, I chained `sort` and `uniq` to find the names appearing in all four lists:

  ```bash
  cat AAA Delta_SkyMiles Terminal_City_Library Museum_of_Bash_History | sort | uniq -c | grep "4 "
  ```

  The `uniq -c` command counted occurrences, and `grep "4 "` filtered for names that appeared exactly four times (once in each list), narrowing the suspect pool from hundreds to just a few dozen.

- **Witness Interviews & File Parsing:** I identified a witness named "Annabel" in the `people` file. Using `grep`, I found her address and then navigated to the corresponding street file in the `streets/` directory. To read the specific line of her interview without opening the entire file, I used a `head` and `tail` combination:

  ```bash
  # To read line 179 specifically
  head -n 179 streets/Buckingham_Place | tail -n 1
  ```

- **Final Forensic Correlation:** The final clue involved a vehicle description (a Blue Honda with a license plate containing "L337"). I combined `grep` for the car make with a regular expression for the plate:
  ```bash
  grep -A 5 "L337" vehicles | grep "Make: Honda" -B 1
  ```
  By cross-referencing the owner of this vehicle with my previously filtered list of 4-club members, I successfully identified **Jeremy Bowers** as the culprit. I submitted the solution by echoing the name into the `mysolution` file, which was verified by an `md5sum` check.

### **Technical Skills Gained**

- ** Advanced File Navigation:** Mastery of `ls -R`, `cd`, and `tree` for mapping complex, multi-layered directory hierarchies.
- ** Text Processing Pipeline:** Professional use of `grep`, `sed`, and `awk` to filter, transform, and extract specific data points from large text blocks.
- ** Stream Redirection:** Deep understanding of using pipes (`|`) to connect modular commands, allowing for high-speed data analysis without temporary files.
- ** Forensic Logic:** Developing a systematic approach to system audits, treating terminal data as a sequence of traceable events.

---
