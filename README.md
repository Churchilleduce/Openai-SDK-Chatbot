# CV Chatbot

An AI chatbot that answers questions about your career, skills, and experience, so recruiters and employers can get to know you in seconds. Upload your CV, and the bot speaks as you, in the first person, using only what's actually in it.

![Screenshot](screenshot.png)

## Features
- Answers questions about your work history, skills, and education
- Reads your CV from a PDF and uses it as the source of truth
- Admits when something isn't in the CV instead of making things up
- Clean chat interface built with Gradio
- Easy to customize with your own name, tone, and instructions

## Tech Stack
- Python
- OpenAI Agents SDK
- OpenRouter (model access)
- Gradio (chat interface)
- pypdf (PDF reading)
- uv (package management)

## How It Works
1. `pypdf` extracts the text from your CV.
2. The text is placed in the agent's instructions, so the model knows your background.
3. The agent, built with the OpenAI Agents SDK, answers each question in your voice.
4. Gradio wraps it all in a simple chat window.

## Getting Started

### Prerequisites
- Python 3.10 or newer
- [uv](https://docs.astral.sh/uv/) installed
- An [OpenRouter](https://openrouter.ai) API key

### Setup

1. Clone the repo
   ```
   git clone https://github.com/Churchill-Educe/YOUR-REPO.git
   cd YOUR-REPO
   ```

2. Install dependencies
   ```
   uv sync
   ```

3. Create a `.env` file in the project folder
   ```
   API_TOKEN=your-openrouter-api-key
   ```

4. Add your own CV as a PDF to the `Resources` folder.

5. Open the notebook and update these two things:
   - The CV file path, to match your PDF's name
   - The `name` variable, to your own name

6. Select the `.venv` kernel and run the cells from top to bottom. The chat interface will launch in your browser.

## Customizing
- **Tone:** edit the `instructions` text to make the bot more formal, casual, or concise.
- **Model:** change the model name to any model available on OpenRouter.
- **Extra context:** add a short summary or LinkedIn text alongside your CV for richer answers.

## Project Structure
```
├── Resources/        # Put your CV PDF here
├── chatbot.ipynb     # Main notebook
├── pyproject.toml    # Dependencies
├── .env              # Your API key (never commit this)
└── .gitignore
```

## Troubleshooting
- **Vague answers:** check that your CV text was extracted properly by printing it. Single-column CVs work best.
- **API key not found:** make sure the name in `.env` is exactly `API_TOKEN` and the file is saved in the project folder.
- **Gradio import errors on Windows:** a security policy may be blocking some files. Try moving the project to a simple folder like `C:\dev`, or run it in Google Colab.

## Limitations
- The bot only knows what's in your CV, so it can't answer questions beyond it.
- Answers depend on how cleanly the PDF text is extracted.

## Author
Built by **Churchill Educe**
[LinkedIn](https://www.linkedin.com/in/churchill-educe-888536174)

## License
Free to use and adapt for your own portfolio.