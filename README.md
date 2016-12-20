# GuitarTutor
Guitar Tutor allows users to select audio files (currently only supports .wav files) that are then fingerprinted. Guitar Tutor attempts to match the audio fingerprints to real-time audio input through a microphone.
Python Version: 2.7 (It will work fine with Python 2.7)

# Things to keep in mind

It only supports .WAV Files with 16 Bits per sample and a sample rate of 48,000kHz. So you can convert the .wav files to 16 Bits per sample before giving it as an input.

# Packages

The Various Libraries required for this project are listed down below:
PyAudio (v0.2.8): 
Website - http://people.csail.mit.edu/hubert/pyaudio/ 
Python Package Index - https://pypi.python.org/pypi/PyAudio/ 
pip install Pyaudio

Numpy (v1.8.1): 
Website - http://www.numpy.org/ 
Python Package Index - https://pypi.python.org/pypi/numpy/1.8.1/ 
pip install Numpy

MatPlotLib (v1.3.1): 
Website - http://matplotlib.org/ 
Python Package Index - https://pypi.python.org/pypi/matplotlib/1.3.1/ 
pip install Matplotlib

# How to use

Run the audimatch.py Python script in the terminal
Using the GUI, add a .wav file to match in realtime audio (Label, File Selection, and Category)
Press the "Add File" button, feel free to add more files to match (unlimited number)
(Optional) Enter your own values in each of the options input boxes
Press the "Analyze" Button to begin fingerprinting and matching
How It Works

User selects an audio file (.wav) to be matched in realtime audio and gives it a label and category
The file and its attached label and category are added to a list of all of the files to analyze
When the analysis is started, the software produces a fingerprint of each audio file using Fast Fourier Transforms (FFT's) and stores that fingerprint
The microphone is then used to capture realtime audio and produce fingerprints for each slice of the realtime stream
The fingerprints for each of the sound files to search for in the realtime audio and the realtime audio's fingerprint are run through a Linear Least-Squares Minimization to best-match each file to the realtime sound and produce a result displaying how much of each sound was present in the realtime audio.

# The Interface

When the script runs, a TK GUI appears prompting the user to add at least one .wav file containing sounds to match in realtime audio, and has several options to modify how the program analyzes the audio and matches it. If left empty, each option will fallback to a set default. A description of each option is below:

Frequency Bands - An entry to limit the frequency bands the program will scan in the realtime sample. For example, if you know a sound you are trying to match is typically between 300 and 500 Hertz, you can enter 300-500 to search only in that band, durastically reducing the time the program takes to scan a sample of realtime audio for matches.

SampleTime - The amount of time (in seconds) that the script will sample realtime audio to fingerprint for. Default: 4 Seconds

Repeat Analysis - The number of times the program will sample realtime audio, fingerprint it, and scan the fingerprint for the amount of sound from each sound file that is present in the sample. Default: 5 Times
