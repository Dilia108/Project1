PODCAST Project - Alex , Ankita,Oli,Dilia

Setup Instructions (Text → Podcast Audio Project)
✅ Step 1: Create your project folder

Create a new folder on your computer where all your project files will live. This keeps everything organized in one place.

✅ Step 2: Set up a virtual environment

Create a virtual environment for your project. This is like a separate workspace where all your project dependencies (libraries) will be installed without affecting your system.we created a conda enviorement .

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

Note: for the moment all parts are inside the same notebook.

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
Handling errors carefully 

Specific Steps followed for the Project : PDF TO PODCAST GENERATOR
1. Configuration
A PodcastConfig dataclass defines all settings: which AI models to use (GPT-4o for scripting, TTS-1-HD for audio, Whisper for transcription), the four host names mapped to distinct OpenAI voices (nova, shimmer, coral, sage), and output file paths.
2. PDF Loading
The user uploads a PDF. The PDFContent class validates that the file exists, is a proper PDF, has pages, and contains extractable text. It uses pypdf to read and concatenate all page text into a single string.
3. Script Generation
The raw PDF text is sent to GPT-4o via the Chat Completions API. A system prompt instructs the model to rewrite the content as a natural 3–5 minute podcast conversation between four hosts, each with a defined personality (Ankita is enthusiastic, Oli asks questions, Alex gives facts, Dilia summarizes). Every line must follow the format HostName: dialogue.
4. Script Parsing
The generated script is parsed line by line using a regex pattern that matches HostName: text. Each matched line is stored as a dictionary with speaker and line fields, producing an ordered list of dialogue segments.
5. Audio Generation
Each dialogue segment is sent individually to OpenAI's TTS API, using the voice assigned to that host. Each segment is saved as a separate .mp3 file. Once all segments are generated, pydub concatenates them in order (with 300ms silence between each) into a single final podcast .mp3 file.
6. Transcription
The final combined audio file is sent to OpenAI's Whisper API, which transcribes the speech back to text. This serves as a verification/accessibility output.
7. Error Handling
Each stage has its own custom exception class (PDFLoadError, ScriptGenerationError, AudioGenerationError, TranscriptionError). API-specific errors (authentication failures, rate limits, connection issues) are caught and translated into user-friendly messages.
8. Gradio UI
A web interface is built with Gradio, offering a file uploader for the PDF, a text field for the episode title, a dropdown to choose the TTS model quality, and a generate button. Results are streamed progressively — status updates appear at each step, and once complete, the UI displays the audio player, generated script, and Whisper transcription in separate tabs.
