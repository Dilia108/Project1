PODCAST Project - Alex , Ankita,Oli,Dilia

Setup Instructions (Text → Podcast Audio Project)
✅ Step 1: Create your project folder

Create a new folder on your computer where all your project files will live. This keeps everything organized in one place.

✅ Step 2: Set up a virtual environment

Create a virtual environment for your project. This is like a separate workspace where all your project dependencies (libraries) will be installed without affecting your system.

✅ Step 3: Activate the virtual environment

Turn on (activate) the virtual environment so that any libraries you install are stored inside this project only.
You’ll know it’s active when your terminal shows the environment name.

✅ Step 4: Install required libraries

Install all the necessary tools your project needs, including:

Backend support (FastAPI or similar)
User interface (Gradio)
AI integration (OpenAI or similar)
Environment variable handling (python-dotenv)
✅ Step 5: Create your project files

Inside your project folder, create the main files needed for your app, such as:

A main application file (to run everything)
A file for handling AI processing
A file for converting text to audio
A file for storing dependencies
A hidden file for API keys
✅ Step 6: Set up your API key securely

Create a special configuration file (called .env) and store your API key there.
This allows your app to connect to the AI service securely.

⚠️ Important:
Never upload this file to GitHub or share it publicly.

✅ Step 7: Connect your project to the API key

Make sure your application reads the API key from the environment file so it can use AI services for:

Text processing
Audio generation
✅ Step 8: Save your dependencies

Generate a list of all installed libraries so that anyone else can easily run your project with the same setup.


