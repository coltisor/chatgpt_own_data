# Use ChatGPT with your own data

This project is a Python implementation that enables us to use our own data to interact with the GPT-3.5-turbo model. 

It uses [LangChain](https://www.langchain.com/) to create a vector database from text files, queries it with a prompt, and obtains a response from the GPT model. 

## Usage

Clone the repository, and make sure you have Python3 and pip3 on your machine. 

After that install the following packages:

```
pip3 install langchain openai chromadb pymupdf tiktoken
```

We should also obtain an OpenAI API key from [the OpenAI website](https://platform.openai.com/account/api-keys) and store it in the `constants.py` file in the root directory of the repository:

```
OPENAI_API_KEY = "your API key"
```

For this project, I used a fake LinkedIn profile as the source data, see `data/linkedin.txt` file.

You can replace it with any data you wish by adding you own text files to the `/data` folder.

To run the project use the following terminal command:

```
python3 app.py "What is my name?"
```

## Examples

```
python3 app.py "What is my name?"
# Response: Your name is Victor Lastname.


python3 app.py "What company do I currently work for?"
# Response: You currently work for Company Name in City, Country.


python3 app.py "Who is the last person that gave me a recommendation on Linkedin?"
# Response: The last person who gave you a recommendation on LinkedIn is Firstname, Lastname.
            

python3 app.py "What are the languages I speak, and how to say 'Hello' in those languages?"
# Response: Based on the provided information, the languages you speak are: 
            English: "Hello", 
            Romanian: "Salut", 
            Russian: "Привет" (Privet), 
            Ukrainian: "Привіт" (Privit).
            
            
python3 app.py "What was the first meeting I had in 2023?"                  
# Response: The first meeting you had in 2023 was titled "2023 fresh start: Next steps + milestones"
            and it took place on January 4th, 2023 from 14:30 to 15:15.
            
            
python3 app.py "List all my 1 to 1 meetings with Colleague Name"
# Response: Here are your 1 to 1 meetings with Colleague Name:
            
            1. Meeting: 1to1 Victor | Colleague Name
              - Date: 2023-03-15
              - Start Time: 13:00:00
              - End Time: 13:30:00
              - Participants: email1, email2
            
            Please note that this is the only 1 to 1 meeting with 
            Colleague Name that is mentioned in the provided context.
            
            
python3 app.py "Based on my calendar, when was the HiddenName project first and last mentioned?"
# Response: The HiddenName project was first mentioned on 2023-06-20 15:00:00 and last mentioned on 2023-06-29.
```
