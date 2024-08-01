<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Speech Recognition with Python</title>
</head>
<body>

<h1>Speech Recognition with Python</h1>

<p>This repository demonstrates how to perform speech recognition using Python's <code>speech_recognition</code> library</p>

<h2>Prerequisites</h2>

<p>Ensure you have the following installed:</p>
<ul>
    <li>Python 3.x</li>
    <li><code>speech_recognition</code> library</li>
</ul>

<p>Install the <code>speech_recognition</code> library using pip:</p>

<pre><code>pip install SpeechRecognition
</code></pre>

<p>You will also need a Bing Speech API key, which you can obtain from the <a href="https://portal.azure.com/">Microsoft Azure Portal</a>.</p>

<h2>Setup</h2>

<ol>
    <li>Clone this repository:</li>
</ol>

<pre><code>git clone https://github.com/Brianhuynh97/Speech_recognition.git
cd Speech_recognition
</code></pre>

<ol start="2">
    <li>Obtain your Bing Speech API key from the Azure Portal.</li>
    <li>Place your audio file (e.g., <code>audio.wav</code>) in the project directory.</li>
    <li>Update the <code>speech_recognition_example.py</code> file with your Bing Speech API key:</li>
</ol>

<pre><code>import speech_recognition as sr

# Initialize recognizer class (for recognizing the speech)
recognizer = sr.Recognizer()

# Use an audio file as the source
with sr.AudioFile('path_to_your_audio_file.wav') as source:
    audio = recognizer.record(source)  # Record the audio from the file

try:
    # Use the Bing Speech API to recognize the audio
    key = 'your_bing_api_key_here'  # Replace with your actual Bing Speech API key
    text = recognizer.recognize_bing(audio, key=key)
    print("Recognized text:", text)
except sr.UnknownValueError:
    print("Bing Speech could not understand the audio")
except sr.RequestError as e:
    print(f"Could not request results from Bing Speech service; {e}")
except TypeError as e:
    print(f"TypeError: {e}")
</code></pre>

<h2>Running the Code</h2>

<p>Run the script using Python:</p>

<pre><code>python speech_recognition_example.py
</code></pre>

<h2>Troubleshooting</h2>

<ul>
   
