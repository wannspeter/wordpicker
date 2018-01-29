# wordpicker

OPEN DOCX FILE FOR SCREENSHOTS OF FRONT END
----------------------------------------------------------------------------------------------------
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
1. wordpicker.zip contains the source code of the web application. Download and Open it.
2. Add postgres super user details to pickwords.java to allow it create its database and tables
3. Run the web application in eclipse with a jetty or create a war file to run in your jetty server

PROCESS FLOW OF WEB APPLICATION
1. Wordpicker connects to postgress database.
2. Captures url from post data coming from form.
3. Gets source code of url.
4. Words are captured from html source code. 
5. filters out some common non noun and verbs.
6. maps out the words to get there frequency.
7. Retrieves existing words in database and saves them in an array.
8. Compares new words with those in array and updates there frequency in database for matches found.
9. if no matches found, a salted hash key is generated for each word.
10. The salted hash is used to encrypt the word.
11. The encrypted word is encrypted again by postgres before being saved in database. The salted hash and frequency are saved without encryption.
12. Words are displayed to the front end user with the one having the highest frequency being the biggest.
13. The admin page retrieves words from database, decrypts them and displays them according to frequency.

--------------------------------------------------------------------------------------------------------

WANNS PETER | wannspeter@gmail.com | +256 756 141496  



