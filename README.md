# Password Analyzer

To analyze password strength and it's probability that it can be cracked and give details about the password


Tech Stack used-
```
Python 3.12.4
Libraries used -
    Built in : math, re (regex), hashlib
    External : requests
API : Haveibeenpwned(free, no key required)
```

Project Structure:
```
Password_Analyzer
    |--main.py
    |--checker.py
    |--analyzer.py
    |--Wordlists
        |--password_list.txt
```


Workflow:
```
load wordlist
     |
     \/
input password from user 
     |
     \/
check conditions for input
     |
     \/
analyze(method call)
     |
     \/
check wordlist(method call) 
     |
     \/
check mutation(method call)
     |
     \/
check repeated characters(from weaknesses list)
     |
     \/
check if password is been pawned(api call)
     |
     \/
prints results(method in main)
     |
     \/
prints whole analysis results
```



Installing and running project:-

1. Clone the project from repository:
    Run this command in terminal:
``` git clone repo_link```

2. Create folder Wordlist:
    -download and paste the rockyou.txt file from web "https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt"
    -change file path for File I/O in main.py (in main function wordlist
    variable is loading a file, Here change the file path)

3. Install requests
    Run following command in terminal:
``` pip install requests   ```

4. Run the project in terminal:
``` python main.py  ```

5. Enter the Password to Analyze

Note : rockyou.txt is .gitignore due to its size, You can download it that is mentioned in installation steps


Example Results :

1.
'''
Welcome to the Password Analyzer
Loaded 13830163 words from the wordlist
Enter a password to analyze: P@ssw0rd@2024xyz
========================================
Password: P@ssw0rd@2024xyz
Length: 16
Charset Size: 94
Entropy: 104.87
Strength: Strong
PAWNED : NO
In Wordlist: NO
no issues found
========================================
'''

2.
'''
Welcome to the Password Analyzer
Loaded 13830163 words from the wordlist
Enter a password to analyze: password1111
========================================
Password: password1111
Length: 12
Charset Size: 36
Entropy: 26.05
Strength: Very Weak
PAWNED : YES - SEEN 12694 times in breaches
In Wordlist: NO
No uppercase letters
No special characters
Repeating characters Detected
Mutation of known password is Detected     
========================================
'''
