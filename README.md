# internbot
This is the gemini powered telegram bot

Core Features:
1. User Registration:
   - Saves first_name, username, and chat_id (plus phone_number when provided) in MongoDB.
   - Prompts the user with a contact button for phone number registration.

2. Gemini-Powered Chat:
   - Processes user text messages via the Gemini API.
   - Saves full conversation history (user input and bot response with timestamps) in MongoDB.

3. Image/File Analysis:
   - Accepts images/files (JPG, PNG, PDF), downloads them locally, uploads the file to Gemini,
     and starts a chat session with the media attached so that Gemini can analyze the image content.
   - Replies with Gemini’s analysis and stores file metadata in MongoDB.

4. Web Search:
   - On the `/websearch` command, prompts for a query, retrieves top links via the googlesearch module,
     and uses Gemini to generate a summary.
   
Bonus Features added:
   - `/sentiment`: Performs sentiment analysis on provided text.
   - `/translate`: Auto-translates text into a specified target language.

Execution Speed:
   - Asynchronous programming with async/await and run_in_executor ensures minimal API latency.
   - Efficient MongoDB operations via Motor provide fast, non-blocking DB storage.

Required Environment Variables:
   - TELEGRAM_TOKEN, MONGO_URI, GEMINI_API_KEY
