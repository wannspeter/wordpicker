# wordpicker

BEST WAY TO STORE AND MANAGE KEYS
- Through physically securing encryption systems so access should only be granted to those with adequate knowledge and intergrity.
- Encryption keys should be stored on separate machines from the data they are used to unlock.
- Having audit logs to show who accessed what data and when.
- Maintaining secure and frequently updated off-site back up of encryption keys
- Giving encryption keys a lifecycle so that they are set to expires after a given time
- Master keys should require multi-factor authentication different from other keys.
- Putting in place key recovery procedures because accidental data loss in nearly inevitable

------------------------------------------------------------------------------------------------------

SETTING UP
Step 1. wordpicker.zip contains the source code of the web application. Download and Open it.
Step 2. Add postgres super user details to pickword.java to allow it create its database and tables
Step 3. Run the web application in eclipse with a jetty or create a war file to run in your jetty server

PROCESS FLOW OF WEB APPLICATION
1. Wordpicker connects to postgress database
2. Captures url from post data coming from form
3. Gets source code of url
4. Words are captured from html source code 
5. filters out some common non noun and verbs 
6. maps out the words to get there frequency
7. Retrieves existing words in database and saves them in an array.
8. Compares new words with those in array and updates there frequency in database of matches found
9. if they don't, a salted hash key is generated for each word
10. The salted hash is used to generate an encryption for the word
11. The encrypted word is encrypted by postgres before being saved in database with the salted hash and frequency
12. Words are displayed to the front end user with the one having the highest frequency being the biggest.
13. Admin page retrieves words from database, decrypts them and displays them according to frequency.



