# Chat FreePT

An AI chatbot application built with Flask and ChatterBot for a school assignment.

## Description

This project demonstrates web development, artificial intelligence, and software testing by creating an interactive chatbot with a Bootstrap frontend. Students learn Flask routing, API design, machine learning basics, and responsible AI development practices.

## Getting Started

### Prerequisites

- Python 3.11 or higher
- pip (Python package manager)
- A terminal or command line interface
- A modern web browser (Chrome, Firefox, Safari, or Edge)

### Installation

1. **Clone the repository:**

   ```bash
   git clone <repository-url>
   cd 2027CT.myAIChatbot_Remy.E
   ```

2. **Create a virtual environment (recommended):**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**

   ```bash
   pip install flask chatterbot chatterbot_corpus pyyaml
   ```

4. **Download the spaCy language model:**
   ```bash
   python -m spacy download en_core_web_sm
   ```
   This model enables the chatbot to understand natural language processing.

### Executing the Program

1. **Start the Flask application:**

   ```bash
   python app.py
   ```

2. **Open your browser:**
   Navigate to `http://localhost:5000`

3. **Interact with the chatbot:**
   Type messages in the chat interface and press Enter to receive responses.

## Project Structure

```
├── app.py                          # Main Flask application
├── templates/
│   └── index.html                  # Bootstrap chat interface
├── test_chatbot.py                 # Automated tests (pytest)
├── requirements.txt                # Python dependencies
├── README.md                        # This file
└── IMPROVEMENTS_REPORT.md          # Known issues and suggestions
```

## Testing

### Running Automated Tests

```bash
# Install pytest (if not already installed)
pip install pytest

# Run all tests
pytest test_chatbot.py

# Run tests with verbose output
pytest -v test_chatbot.py

# Run a specific test class
pytest test_chatbot.py::TestCrisisDetection
```

### Manual API Testing (without frontend)

```bash
curl -X POST http://localhost:5000/chat \
  -H "Content-Type: application/json" \
  -d '{"message": "Hello"}'
```

### User Acceptance Testing

| Test ID | Description               | Status  | Notes                             |
| ------- | ------------------------- | ------- | --------------------------------- |
| TC-001  | Normal message response   | ✅ Pass | Chatbot replies to user messages  |
| TC-002  | Empty message handling    | ✅ Pass | System handles blank input safely |
| TC-003  | Message length validation | ✅ Pass | Long messages are processed       |
| TC-004  | Crisis keyword detection  | ✅ Pass | Detects and responds to alerts    |
| TC-005  | Disclaimer visibility     | ✅ Pass | Educational warning is displayed  |
| TC-006  | Message styling           | ✅ Pass | Chat UI displays correctly        |

**Summary:** All 6 test cases passed. The chatbot meets functional and non-functional requirements.

## Help & Troubleshooting

### Common Issues

**Error: `OSError: [E050] Can't find model 'en_core_web_sm'`**

```bash
python -m spacy download en_core_web_sm
```

**Error: `ModuleNotFoundError: No module named 'yaml'`**

```bash
pip install pyyaml
```

**Training takes a long time on first run**
This is normal behaviour—ChatterBot trains on the English corpus (10–30 seconds). Your code is not broken.

**The database file is large**
The `chatbot_database.sqlite3` file stores trained knowledge. Delete it to retrain from scratch, or add it to `.gitignore` to avoid committing it.

## Key Features

- ✅ Conversational AI responses using machine learning
- ✅ Safety features for crisis keyword detection
- ✅ Input sanitisation for security
- ✅ Responsive Bootstrap interface
- ✅ REST API for chat interactions
- ✅ Automated test coverage
- ✅ Educational focus on AI ethics

## Authors

**Contributors:**

- Mr Jones
- [@benpaddlejones](https://github.com/benpaddlejones)

**Student Developer:**

- Remy Ellis
- [@Breakerchap](https://github.com/Breakerchap)

## Version History

- **0.2**
  - Improved test coverage and documentation
  - Enhanced error handling and safety features
  - Optimised chatbot responses
  - See [commit history](#) for details

- **0.1**
  - Initial release
  - Basic Flask application structure
  - ChatterBot integration

## License

This project is licensed under the GNU GPL v3.0 License—see the LICENSE file for details.

## Acknowledgments

- [GitHub Markdown Syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [TempeHS Python Flask Template](https://github.com/TempeHS/TempeHS_Python-Flask_DevContainer)
- [ChatterBot Documentation](https://chatterbot.readthedocs.io/)
- [Flask Documentation](https://flask.palletsprojects.com/)
