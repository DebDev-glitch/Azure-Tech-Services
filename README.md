# Azure-Tech-Services
#rest-client
Language Detection Tool
This Python script provides a simple interface for detecting the language of input text using an AI service. It leverages the Text Analytics API to analyze user-provided text and return the detected language.

Table of Contents
Requirements
Environment Variables
Usage
Code Overview
Error Handling
License
Requirements
To run this script, you need:

Python 3.x
dotenv library for managing environment variables
Access to a Text Analytics API (like Azure's Text Analytics)
You can install the required library using pip:

bash
Copy code
pip install python-dotenv
Environment Variables
Before running the script, set up the following environment variables:

AI_SERVICE_ENDPOINT: The endpoint URL for the AI service.
AI_SERVICE_KEY: The subscription key for authenticating requests to the AI service.
You can create a .env file in the same directory as the script with the following content:

plaintext
Copy code
AI_SERVICE_ENDPOINT=YOUR_AI_SERVICES_ENDPOINT
AI_SERVICE_KEY=YOUR_AI_SERVICES_KEY
Replace YOUR_AI_SERVICES_ENDPOINT and YOUR_AI_SERVICES_KEY with your actual endpoint and key.

Usage
Clone or download this repository.
Navigate to the script's directory.
Set up your .env file with the necessary API details.
Run the script:
bash
Copy code
python language_detection.py
Enter text when prompted. The script will analyze the input and display the detected language. Type "quit" to exit the program.
Code Overview
The main components of the script include:

Main Function: Loads environment variables, captures user input, and calls the GetLanguage function for language detection.
GetLanguage Function:
Constructs a JSON payload with the input text.
Makes an HTTPS POST request to the language detection API.
Handles the response and extracts the detected language from the JSON response.
Error Handling
The script includes basic error handling to capture and display exceptions that may occur during execution, such as issues with network requests or problems loading environment variables.
