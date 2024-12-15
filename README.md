*PDF to Audio V1 has no GUI interface but uses OPENAI model along with Chunks and Delay to reduced TTS API Error*

Overview

This Python script extracts text from a PDF, summarizes it using OpenAI's GPT-3.5-turbo, and converts the summarized text into an MP3 audiobook using Google Text-to-Speech (gTTS). It is designed to make lengthy documents more accessible in audio format.

Features

Extract Text: Reads PDF files and extracts their content.
Summarize Content: Summarizes the extracted text for concise audio output.
Generate Audiobook: Converts the summarized text to an MP3 file.
Retry Mechanism: Handles errors like rate limits during audio generation.
Requirements

Python Libraries:
PyPDF2: For reading and extracting PDF text.
gTTS: For converting text to audio.
openai: For using OpenAI GPT API.
OpenAI API Key:
Obtain an API key from OpenAI.
Set it as an environment variable: OPENAI_API_KEY.
Internet Connection: Required for GPT-3.5-turbo and gTTS.
Installation

Install Dependencies: Run the following command to install required libraries:
pip install PyPDF2 gTTS openai
Set Up OpenAI Key: Set your API key as an environment variable:
Windows: set OPENAI_API_KEY=your_api_key
Mac/Linux: export OPENAI_API_KEY=your_api_key
Usage

Prepare Input and Output Paths:
Place the PDF file in an accessible directory.
Edit the script to define the pdf_path (path to the input PDF) and output_audio_path (path for the MP3 file).
Example:

pdf_path = "path/to/your/file.pdf"
output_audio_path = "output.mp3"
Run the Script: Execute the script in Python. The script will:
Extract text from the PDF.
Summarize the text using OpenAI's GPT-3.5-turbo.
Convert the summary to an audio file.
Output

The script generates an MP3 file at the specified location, containing the summarized audio version of the PDF.

Troubleshooting

Text Extraction Issues: Ensure the PDF is not encrypted or scanned without OCR.
OpenAI API Errors: Check the API key and usage limits.
Audio Generation Errors: Retry logic handles rate limits; check the internet connection for persistent errors.
Customization

Summarization Length: Adjust the chunk_size and max_tokens for shorter or more detailed summaries.
Offline Text-to-Speech: Replace gTTS with pyttsx3 for offline conversion.



**PDF to Audio V1 has a GUI interface along with Chunks and Delay to reduced TTS API Error**

Overview

The Audiobook Converter application is a Python-based GUI tool that converts PDF documents into audiobooks. It extracts text from a PDF, processes the text for readability, and uses text-to-speech (TTS) libraries to generate an MP3 audio file. The application is equipped with a simple and intuitive graphical interface for easy interaction.

Features

Text Extraction: Extracts text from PDF files, handling multi-page documents efficiently.
Text Processing: Preprocesses the text to ensure readability, splitting it into manageable chunks.
TTS Conversion: Supports multiple TTS libraries for speech synthesis (e.g., gTTS and pyttsx3).
GUI: User-friendly interface built with Tkinter.
Audio Playback: Allows users to play the generated audio directly from the application.
Download Functionality: Saves the generated audio to a user-specified location.
Requirements

Python Libraries
The following Python libraries are required to run the application:

PyPDF2: For extracting text from PDF files.
gTTS: For generating audio from text (Google Text-to-Speech).
pyttsx3: An offline TTS option for speech synthesis.
tkinter: For the graphical user interface (part of the Python standard library).
subprocess: For audio playback and merging audio chunks.
os, shutil, and time: Standard libraries for file handling and process management.
Install the required libraries with:

pip install PyPDF2 gtts pyttsx3
Usage

Run the Script: Launch the application by running the Python script:
python audiobook_converter.py
Select a PDF File:
Click the "Select PDF File" button.
Choose a PDF file from your local machine. The file will be copied into the application's working directory.
Generate Audiobook:
The application will extract text, process it, and convert it into an MP3 file.
Progress is displayed during the conversion process.
Play Audiobook:
Click the "Play Audiobook" button to listen to the generated audio directly.
Download Audiobook:
Save the generated MP3 file to your desired location by clicking "Download Audiobook."
Close the App:
Click the "Close App" button to exit the application.
Features in Detail

Text-to-Speech Libraries
gTTS (Google Text-to-Speech): Utilized for generating audio chunks. Provides high-quality online TTS conversion.
pyttsx3: An alternative for offline TTS synthesis in case gTTS is unavailable.
Chunk Processing
Text is split into manageable chunks to avoid rate limits or memory issues.
Chunks are processed with delays to ensure reliability.
Output Management
Temporary audio chunks are combined using ffmpeg to create the final MP3 file.
Temporary files are cleaned up automatically.
Troubleshooting

TTS Library Issues:
Ensure gTTS and pyttsx3 are installed correctly.
Use pyttsx3 for offline TTS if gTTS is unavailable.
PDF Issues:
Check if the PDF is not encrypted or scanned without OCR.
Ensure the file contains text that can be extracted.
FFmpeg Errors:
Install ffmpeg on your system if audio concatenation fails.
On macOS/Linux, install via the package manager (e.g., brew install ffmpeg).
GUI Issues:
Ensure the Tkinter library is correctly installed.
Customization

TTS Settings:
Adjust chunk size (CHUNK_SIZE) and chunk delay (CHUNK_DELAY) to optimize for your needs.
UI Customization:
Modify fonts, colors, and layout in the AudiobookConverter class.




**PDF to Audio Converter V3 has GUI interface but without Chunks and Delay to reduced TTS API Error**


Overview

The Audiobook Converter is a Python-based application that converts PDF files into audiobooks. It provides a user-friendly graphical interface (GUI) built with Tkinter. The application utilizes text-to-speech (TTS) libraries such as gTTS and pyttsx3 to create high-quality audio files from the text extracted from PDF documents.

Features

PDF to Audiobook Conversion: Converts the text content of PDF files into an audiobook in MP3 format.
Dual TTS Libraries: Supports both Google Text-to-Speech (gTTS) for online conversion and pyttsx3 for offline processing.
Graphical User Interface: Intuitive UI for easy navigation and file selection.
Download & Play Options: Play the audiobook directly or download it to your local system.
Cross-Platform Compatibility: Works on Windows, macOS, and Linux.
Requirements

Python Libraries
tkinter
gtts (Optional for online TTS)
pyttsx3 (Optional for offline TTS)
PyPDF2
shutil
subprocess
Additional Tools
ffmpeg (for merging audio chunks if required).
Installation

Install Python 3.6 or later.
Clone the repository:
git clone https://github.com/your-repository/audiobook-converter.git
cd audiobook-converter
Install dependencies:
pip install gtts pyttsx3 PyPDF2
Install ffmpeg:
For Windows: Download from https://ffmpeg.org and add it to the PATH.
For macOS/Linux: Use your package manager (e.g., brew install ffmpeg).
Usage

Run the application:
python audiobook_converter.py
Follow these steps in the GUI:
Click "Select PDF File" to upload a PDF.
Wait for the conversion process to finish.
Click "Play Audiobook" to listen to the audio.
Click "Download Audiobook" to save the MP3 file to your system.
Close the application:
Click "Close App" to exit the program.
Troubleshooting

No audio generated: Ensure that either gtts or pyttsx3 is installed. If using gtts, ensure you have an active internet connection.
ffmpeg errors: Confirm ffmpeg is installed and accessible from your system's PATH.
PDF extraction fails: Ensure the PDF contains readable text (not just images).
Customization

Chunk Size: Modify the CHUNK_SIZE attribute in the code to change the size of text processed at once.
UI Appearance: Update fonts and colors in the AudiobookConverter class to customize the interface.
Additional Formats: Extend the _text_to_speech_* methods to support other TTS libraries or formats.



*PDF to Audio Converter V4*

This project is a Python script that converts chapters from a PDF workbook into audio files using text-to-speech (TTS) technology. The audio is generated for each chapter and saved as an MP3 file.

Prerequisites:

Before running the script, you will need to install the required libraries:

pyttsx3 - For text-to-speech conversion.
PyPDF2 - For reading PDF files and extracting text.
You can install these libraries using pip:

pip install pyttsx3 PyPDF2
How It Works:

Chapter Data:
The script processes a pre-defined set of chapters, with each chapter having a specific range of pages defined in the chapter_dict. Each entry in the dictionary contains the chapter name and the start and end page numbers of that chapter.
Text Extraction:
The PdfReader from the PyPDF2 library is used to read the PDF. The text from the specified pages (defined in chapter_dict) is extracted from the PDF and stored as a string.
Text-to-Speech Conversion:
The extracted text is converted into speech using the pyttsx3 library. The text is saved as an MP3 file named after the chapter.
Features:

Converts PDF chapters to MP3 audio files.
Supports multiple chapters with defined page ranges.
Each chapter is saved as a separate MP3 file with the name of the chapter.
How to Run:

Download the Python script and the required PDF file: NISM Series VIII- Equity Derivatives Certification Examination Workbook - May 2023.pdf.
Make sure you have the required libraries installed (use pip install pyttsx3 PyPDF2).
Run the script:
python script_name.py
The script will generate MP3 files for each chapter in the same directory where the script is located.
File Naming Convention:

Each audio file will be named based on the chapter name, with spaces replaced by underscores. For example, the "Basics of Derivatives" chapter will be saved as Basics_of_Derivatives.mp3.

Sample Output:

Basics_of_Derivatives.mp3
Understanding_the_Index.mp3
Introduction_to_Forwards_and_Futures.mp3
Troubleshooting:

If the text extraction does not work well, ensure that the PDF is not encrypted or in an unusual format (e.g., scanned images). For scanned PDFs, consider using an OCR (Optical Character Recognition) tool to extract text.
Ensure that the TTS engine is correctly set up. You may need to adjust the TTS voice and speech rate based on your system's settings.
