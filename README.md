# DataGen Agent

DataGen Agent is an AI-powered sample data generator built with **LangChain**, **LangGraph**, and **OpenAI**. It can generate mock user data and save it directly into JSON files using tool-calling.

## Features

- Generate sample user data automatically
- Save generated data into a `.json` file
- Read existing JSON files
- Uses tool calling with a ReAct-style agent
- Supports custom:
  - first names
  - last names
  - email domains
  - age ranges 

## Tech Stack

- Python
- LangChain
- LangGraph
- OpenAI GPT
- dotenv
- JSON file handling

## How It Works

### The agent uses three main tools:

generate_sample_users → creates mock user data
write_json → saves data to a JSON file
read_json → reads and returns JSON file contents

### When a user gives a prompt like:

Generate users named John, Jane, Mike and save to users.json

### the agent:
- Generates sample users
- Formats them as structured JSON
- Saves them into the requested file automatically
  
### Installation
#### 1. Clone the repository
```
git clone <your-repo-link>
cd <your-repo-folder>
```
#### 2. Create and activate a virtual environment
```
python3 -m venv venv
source venv/bin/activate
```
#### 3. Install dependencies
```
pip install langchain-openai langchain-core langgraph python-dotenv
#### 4. Add your API key
```

### Create a .env file in the root directory:
```
OPENAI_API_KEY=your_api_key_here
```
## Usage

#### Run the script:
```
python main.py
```
#### Example prompts:

- Generate users named John, Jane, Mike and save to users.json
- Create users with last names Smith, Jones
- Make users aged 25-35 with company.com emails
Example Output
```
{
  "users": [
    {
      "id": 1,
      "firstName": "John",
      "lastName": "Smith",
      "email": "john.smith@example.com",
      "username": "john123",
      "age": 28,
      "registeredAt": "2026-04-05T10:30:00"
    }
  ],
  "count": 1
}
```

## Key Highlights
- Built with a tool-using AI agent
- Handles JSON read/write operations
- Automatically fills missing user-generation details
- Maintains conversation history for smoother interaction

## Future Improvements
- Add support for more data types
- Generate company, product, or transaction data
- Add a web interface
- Improve validation and error handling
- Export to CSV as well as JSON
