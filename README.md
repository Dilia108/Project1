Introduction & Problem (Alex)
Hi everyone. We are Ankita, Dalia, Alex and Oli.

Today we're presenting our Podcast Studio, an AI-powered system that transforms written content into podcast episodes automatically. We built this in one day as a group of four people, most of us coming from non-technical backgrounds, which is exactly what inspired the content of our first podcast episode.

The problem we wanted to solve is simple: not everyone learns the same way. A lot of people absorb information better through audio than through reading, but creating podcast content manually takes hours. Writers, educators, and learners don't have time for that.
We focused specifically on beginners entering the world of AI and technology. People who feel overwhelmed, who wonder if they belong here. Our podcast studio takes any text or article and converts it into a natural, engaging audio episode in seconds, making content accessible to anyone, anywhere, even on the go."

Demo (Ankita)
Live walkthrough:

Open the interface at https://14122211075fc67b4d.gradio.live/
"Here is our Gradio interface. You can either paste a URL from any article, or paste text directly."
Paste the podcast text into the field
Click Generate Podcast
"The system first extracts the content, then sends it to OpenAI GPT to transform it into a natural spoken script, and finally OpenAI TTS converts that script into audio."
Play the generated audio


Technical choices (Dilia)
For the tech stack we used Python, Gradio for the interface, OpenAI GPT-4o-mini for the script transformation, and OpenAI TTS for the audio generation.
We also used HuggingFace to scrape article text from URLs but in the end we decided to create ourselves a script, save it in a PDF and upload it manually.

The pipeline is clean and modular - three separate files each handling one job: data processing, LLM transformation, and audio generation, all connected through a main file.

We experienced different types of issues ranking from API Key issues, when eventhough we had credits VS Code would not recognize it and blocked the podcast creation.

Takeaways (Olalla)
The biggest technical challenge was setting up the environment correctly: File paths, dependencies, and API configurations took longer than expected.
But from this, we also learned an interesting trick: when hitting API rate limits, adding a sleep timer in Python lets the system wait and retry automatically instead of crashing.

Another unexpected issue - creating a shareable link to the podcast became an unexpected blocker due to excessive protection from the anti-virus.

All in all, the biggest takeaway is that even as beginners, we built a fully functional AI pipeline in one day, and that if we can anybody can also do it.
That is exactly the message we want to transmit with our first podcast episode. (edited) 14122211075fc67b4d.gradio.liveGradioClick to try out the app!
