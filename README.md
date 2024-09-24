
# Transcriber App

This project is a simple **Streamlit** application called **Transcriber**, which allows users to upload an audio file, transcribe it using OpenAI's Whisper API, and download the transcription as a Word document.

## Features

- Upload audio files (`mp3`, `wav`, `m4a`).
- Transcribe the audio using OpenAI's Whisper API.
- Display the transcription in Markdown format.
- Convert the transcription to a Word document.
- Download the Word document.

## Prerequisites

Before running the app, ensure you have the following:

1. **Python 3.7+** installed.
2. An **OpenAI API key**. Sign up at [OpenAI](https://beta.openai.com/signup/) to get your API key.

## Installation Instructions

### Step 1: Clone the Repository

Clone the repository or download the source code:

```bash
git clone https://github.com/kaljuvee/transcriber.git
cd transcriber
```

### Step 2: Create a Virtual Environment

Create a Python virtual environment to isolate the project dependencies:

```bash
# For Windows
python -m venv venv

# For macOS/Linux
python3 -m venv .venv
```

Activate the virtual environment:

```bash
# For Windows
venv\Scripts\activate

# For macOS/Linux
source venv/bin/activate
```

### Step 3: Install Dependencies

Install the necessary Python dependencies from the `requirements.txt` file:

```bash
pip install -r requirements.txt
```

### Step 4: Install System Packages (for `ffmpeg`)

For handling audio files, `ffmpeg` is required. Create a `packages.txt` file in the root directory with the following content to ensure `ffmpeg` is installed (this is especially important for deployment to Streamlit Cloud):

Create the `packages.txt` file:
```txt
ffmpeg
```

Alternatively, if you're setting this up locally:

#### On Ubuntu/macOS:
```bash
sudo apt update
sudo apt install ffmpeg
```

#### On Windows:
You can install `ffmpeg` by following instructions from [ffmpeg.org](https://ffmpeg.org/download.html) or use a package manager like [chocolatey](https://chocolatey.org/).

```bash
choco install ffmpeg
```


### Step 5: Run the Streamlit App

Finally, run the Streamlit app:

```bash
streamlit run Home.py
```

### Step 6: Set Up OpenAI API Key

- Once the app is running, it will open a browser window where you can set your OPENAI_API_KEY and upload your audio files and start transcribing!

## Deployment on Streamlit Cloud

To deploy this app on **Streamlit Cloud**, ensure the following files are in the root directory:

1. `transcriber.py`: The main app script.
2. `requirements.txt`: For Python dependencies.
3. `packages.txt`: To install `ffmpeg` in the cloud environment.

Deploy the app to **Streamlit Cloud** by following these steps:

1. Create a new Streamlit Cloud project.
2. Push the project to GitHub.
3. Link the GitHub repository to your Streamlit Cloud workspace.
4. Streamlit Cloud will automatically detect the `packages.txt` and `requirements.txt` files and install the necessary dependencies.

Once deployed, the app will be live, and you can share the link.

## Project Structure

```bash
transcriber-app/
│
├── transcriber.py        # Main Streamlit app code
├── requirements.txt      # Python dependencies
├── packages.txt          # System packages for ffmpeg
└── README.md             # Instructions
```

## Troubleshooting

- **Missing OpenAI API Key**: Ensure you've set your OpenAI API key correctly in either the script or as an environment variable.
- **ffmpeg not found**: If you're facing issues with ffmpeg not being found, ensure it is correctly installed and in your system path.
- **Dependency issues**: If any Python packages fail to install, try running `pip install` for that specific package or ensure your virtual environment is activated.
