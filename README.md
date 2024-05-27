# knowledge_retrieval_LLM_chatbot_v2
LLM based chatbot that takes a document as an input (currently in txt, docx or pdf format) and answers questions about document content while retaining memory of the conversation. Works interactively from the command line.


## Overview
The application leverages GPT 3.5 model that is accessed through OpenAI API.  In this version of the app, the app accepts a content file as input that contains content that the app users are interested in. The content input file can be in .txt, .docx or .pdf format. The app allows the user to ask questions about the document by typing the questions in command line.

For additional requirements,  app is designed to handle multiple questions about the same topic in succession (i.e. retain memory of the conversation).  The app is also tailored to answer questions on the topic contained in the input document. If asked about significantly unrelated topics (e.g. “Give me a recipe for a cheesecake”), the app may respond by saying ``The question is not relevant to the domain of interest.``.

## How to Run This Application
The code for this application is contained in the root directory - file `app.py`.  This application is designed to run from command line.  Navigate to the folder where the app.py is saved and then run:
```
python app.py --content_text_file path_to_file/content_file.txt

```
where `path_to_file/content_file.txt` should be the location for the file with content.

## Application Dependencies
The dependencies for this application are described in the `requirements.txt` file located in the root directory.  From the same directory, from the command line run:
```
python -m pip install -r requirements.txt
```
to install all the required python libraries.

## Setting Environmental Variables
Environmental variables needed to authenticate OpenAI connection are located in .env file:
```
OPENAI_API_KEY="your_api_key"
OPENAI_DEPLOYMENT_NAME="your_openai_model_name"

```

## Example of Use
The root directory contains a content text file named `Software_Engineering_Practices.txt`.

Here is an example of the app use with the two sample text files as an input:
```
$ python3 app.py --content_text_file Software_Engineering_Practices.txt

Please ask your question about the document. If you want to stop type 'exit'.
what is the purpose of this document?
Answering question: what is the purpose of this document?
Here is the response: 

The purpose of this document is to provide the teams responsible for the development of Medical Imaging Algorithms in the Personalized HealthCare (PHC) Imaging group with high-level principles and concepts making up the software engineering practices. It aims to ensure that code development is uniform, well-documented, and compliant with Roche Quality Management System policies. 

Please ask your question about the document. If you want to stop type 'exit'.
what is in scope?      
Answering question: what is in scope?
Here is the response: 

The scope of this document includes rule-based and Machine Learning (ML) based algorithm development life cycle, high-level guidelines for coding standards, high-level guidelines on documentation associated with each algorithm, version control process, and roles and responsibilities within the PHC Imaging group. 

Please ask your question about the document. If you want to stop type 'exit'.
exit
You ended the program.  Goodbye!
```


## Author and Acknowledgments
All the code in this repo was created by the author of this repo, Alexander Arefolov. 
