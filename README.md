# Azure-Tech-Services
#REST-CLIENT
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



#sdk-client
Language Detection Tool with Azure SDK
This Python script provides a simple interface for detecting the language of input text using Azure's Text Analytics API. It utilizes the Azure SDK for Python to interact with the service and return the detected language for user-provided text.

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
The Azure SDK for Python
dotenv library for managing environment variables
You can install the required libraries using pip:

bash
Copy code
pip install azure-ai-textanalytics python-dotenv
Environment Variables
Before running the script, set up the following environment variables:

AI_SERVICE_ENDPOINT: The endpoint URL for the Azure Text Analytics service.
AI_SERVICE_KEY: The subscription key for authenticating requests to the service.
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
Creates an instance of TextAnalyticsClient using the provided endpoint and key.
Calls the detect_language method to analyze the input text and return the detected primary language.
Error Handling
The script includes basic error handling to capture and display exceptions that may occur during execution, such as issues with network requests or problems loading environment variables.


# Image Analysis Project

This project uses the Azure AI Vision services to analyze and manipulate images, including extracting image captions, tags, identifying objects and people, and removing backgrounds. This is accomplished using Python, the Azure AI Vision SDK, and various image processing libraries.

## Features

- **Image Analysis**: Captions, dense captions, tags, object detection, and people detection in images.
- **Background Removal**: Removes the background of an image or creates a foreground matte using Azure's background removal service.
- **Image Annotation**: Highlights and labels detected objects and people in the image.

## Prerequisites

1. **Azure AI Services**: You need an active Azure subscription and an Azure Cognitive Services resource with Vision API enabled. 
2. **Python 3.x**: The code is compatible with Python 3.x.
3. **Required Python Libraries**: Install the following Python packages:
   ```bash
   pip install azure-ai-vision matplotlib pillow requests python-dotenv
Clone the Repository Clone or download this repository to your local machine.

Environment Variables In the root directory, create a .env file with the following variables:
AI_SERVICE_ENDPOINT=your_azure_ai_services_endpoint
AI_SERVICE_KEY=your_azure_ai_services_key
Image Place your image file in a folder named images in the root directory and name it street.jpg. You can also specify another image filename as a command-line argument.
To run the image analysis and background removal, use:
python your_script_name.py
Or, specify an image filename:
python your_script_name.py path_to_your_image.jpg
Functions Overview
AnalyzeImage: Analyzes the image for various visual features and displays results such as captions, dense captions, tags, detected objects, and people.
BackgroundForeground: Removes the background or generates a foreground matte for the image. Saves the processed image as background.png.
Output Files
The following output files are generated:

objects.jpg: Displays detected objects with bounding boxes.
people.jpg: Highlights detected people in the image with bounding boxes.
background.png: The image with the background removed.
Error Handling
If an error occurs, especially a HttpResponseError, it will print the status code, reason, and error message for troubleshooting.

Dependencies
Azure AI Vision SDK: Communicates with Azure's AI Vision API.
Pillow: Used for image processing and bounding box drawing.
Matplotlib: Displays and saves annotated images.
Requests: Makes HTTP requests for background removal.
Troubleshooting
Ensure your Azure endpoint and key are correct in the .env file and that your image file exists in the specified path. Also, verify the correct permissions for your Azure resource and subscription.


#Hiking Assistant with Azure OpenAI

This project implements a hiking assistant chatbot using the Azure OpenAI service. The assistant, named "Forest," helps users discover hiking trails nearby and offers nature insights about the trails. It is set up to provide suggestions for hikes near Rainier National Park if no specific location is given.

Features
Conversational Interface: Interact with "Forest" through a chat-style interface where you can ask for hiking suggestions.
Customizable Recommendations: If no area is specified, Forest defaults to recommending hikes near Rainier National Park.
Diverse Hiking Options: Forest suggests three hikes with varying lengths for a tailored experience.
Local Nature Facts: Get interesting facts about the local flora and fauna on each hike.
Requirements
Python 3.x
Azure OpenAI Service: An active subscription with access to an OpenAI deployment on Azure.
Setup Instructions
Clone the Repository:

bash
Copy code
git clone <repository-link>
cd <repository-name>
Install Dependencies:

Install Python dependencies using pip:
bash
Copy code
pip install openai python-dotenv
Create an .env File:

In the root directory of your project, create a .env file with the following configuration:

plaintext
Copy code
AZURE_OAI_ENDPOINT="your_azure_openai_endpoint"
AZURE_OAI_KEY="your_azure_openai_key"
AZURE_OAI_DEPLOYMENT="your_azure_openai_deployment_name"
Replace your_azure_openai_endpoint, your_azure_openai_key, and your_azure_openai_deployment_name with the values provided by your Azure account.

Run the Application:

Start the application by running:

bash
Copy code
python main.py
Enter prompts to receive hiking recommendations from "Forest."

Code Overview
main.py: This file contains the main application logic for interacting with the Azure OpenAI API.
load_dotenv(): Loads environment variables from the .env file.
AzureOpenAI: Connects to the Azure OpenAI endpoint using the provided credentials.
system_message: Initializes the chatbot personality with background and context for hiking recommendations.
Main Loop: Accepts user input, generates a response through the OpenAI model, and prints the chatbot's response.
Example Usage
plaintext
Copy code
Enter the prompt (or type 'quit' to exit): Can you suggest a hike for me?
Sending request for summary to Azure OpenAI endpoint...

Summary: Here are three fantastic hikes for you near Rainier National Park...
Error Handling
The code includes basic error handling, printing any exceptions that occur during execution.
