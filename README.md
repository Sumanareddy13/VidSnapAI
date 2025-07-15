🎬 VidSnapAI – AI-Powered Reel Generator
VidSnapAI is a Flask-based SaaS application that turns user-uploaded images and text into engaging vertical video reels using AI voice generation and FFmpeg stitching. It automates the process of converting uploaded visuals and descriptions into  reels.

🚀 Features
🎤 AI Voice Generation: Converts user text into audio using ElevenLabs (or TTS module).

🖼️ Image Upload & Management: Drag-and-drop multiple image files per reel.

🎬 FFmpeg Video Creation: Combines images and audio into vertical 1080x1920 MP4 reels.

🧠 Auto Processing Pipeline: Background script automatically picks new uploads and converts them into reels.

🖥️ Responsive UI: Clean, modern front-end with Bootstrap + custom CSS.

📁 Reel Gallery: Users can view all generated reels in a gallery.

🛠️ Tech Stack
Backend: Python, Flask, UUID, FFmpeg, subprocess

Frontend: HTML, CSS, Bootstrap 5, Dropzone, Jinja2

Tools: Werkzeug, ElevenLabs (TTS), Ginja templating

Media Processing: FFmpeg for video & audio

Hosting Ready: Static file handling, modular structure

📂 Project Structure
graphql
Copy
Edit
VidSnapAI/
│
├── app.py                    # Main Flask app
├── background_processor.py   # Converts uploaded folders into reels
├── text_to_audio.py          # Handles TTS audio generation
├── done.txt                  # Tracks processed folders
├── static/
│   ├── reels/                # Output reels
│   ├── css/                  # All custom CSS files
│   └── images/               # Gallery demo images
├── templates/
│   ├── base.html
│   ├── index.html
│   ├── create.html
│   ├── gallery.html
├── user_uploads/             # Uploaded content (images, desc.txt)
└── README.md                 # You're here!
🧪 How It Works
User uploads images + description through /create.

The desc.txt is converted into an audio.mp3 via ElevenLabs (or any TTS).

Images + audio are stitched into a reel using FFmpeg with proper scaling/padding.

Final output is saved in /static/reels/ and displayed in /gallery.

▶️ Running Locally
Clone the repo

bash
Copy
Edit
git clone https://github.com/yourusername/VidSnapAI.git
cd VidSnapAI
Install dependencies

bash
Copy
Edit
pip install flask
Start the Flask server

bash
Copy
Edit
python app.py
Start the background processor

bash
Copy
Edit
python background_processor.py
🔊 Text-to-Speech Note
The text_to_audio.py uses a custom text_to_speech_file() method that can be backed by ElevenLabs, Google TTS, or any engine of your choice. Be sure to include API credentials if needed.


🧩 Future Improvements
User authentication and history
Audio/music layer selection
Drag-and-drop timeline editor
Integration with Instagram API for direct publishing
