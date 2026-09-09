ESP32 Audio Spectrum Visualizer with OLED Display
Project Overview
This project transforms an ESP32-C3 microcontroller into a real-time audio spectrum analyzer that visualizes sound frequencies as animated bar graphs on a compact 128x64 OLED display. Using Fast Fourier Transform (FFT) algorithms, the system processes analog audio input, separates it into frequency bands, and displays dynamic visual feedback of the sound spectrum.

Key Features
Real-Time Audio Processing: Samples audio at 4 kHz and performs FFT analysis every cycle

16-Band Spectrum Visualization: Displays frequency distribution as smooth animated bars

Noise Filtering: Skips low-frequency DC noise for cleaner visualization

Smooth Animation: Built-in smoothing algorithm prevents flickering and creates fluid transitions

Compact Display: 0.96" OLED screen with clear monochrome graphics

Low-Latency Response: Optimized for live audio input

Hardware Requirements
Component	Specification
Microcontroller	ESP32-C3 (or any ESP32 variant)
Display	128x64 OLED (SSD1306, I²C interface)
Audio Input	Analog sound sensor/microphone module
Connections	I²C (SDA, SCL) + Analog input
Pin Configuration
Audio Input: GPIO 4 (analog)

I²C SDA: GPIO 7

I²C SCL: GPIO 6

Technical Implementation
Signal Processing Pipeline
Sampling: 64 audio samples captured at 4 kHz

FFT Processing: Converts time-domain signal to frequency-domain data

Frequency Binning: Maps 16 frequency bands from FFT output

Amplitude Scaling: Maps raw values to display heights (0–64 pixels)

Smoothing: Exponential moving average (EMA) for stable visuals

Algorithm Details
Windowing: Hamming window reduces spectral leakage

DC Removal: Eliminates DC offset for accurate frequency analysis

Smoothing Factor: 0.2 (adjustable) balances responsiveness vs. stability

Frequency Resolution: ~62.5 Hz per bin (at 4 kHz sampling)

Visual Design
Bars: 16 vertical bars, each 7 pixels wide with 1-pixel spacing

Gradient Effect: Bars rise from bottom to top, showing amplitude

Refresh Rate: ~10 ms per frame for smooth real-time performance

Applications
Music visualization for audio systems

Sound level monitoring in environments

Audio frequency education and experiments

Interactive art installations with sound responsiveness

DIY spectrum analyzer for audio equipment testing
