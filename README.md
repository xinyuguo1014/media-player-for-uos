# Media Player for UOS

English | [中文](README.zh.md)

A modern multimedia player built with the Qt framework, designed specifically for UOS (UnionTech OS).

## Project Overview

Media Player for UOS is a feature-rich multimedia player with the following core features:

- **Multimedia Playback**: Supports audio and video playback
- **Intelligent Recommendations**: A machine learning-based music recommendation system
- **Modern UI**: Supports light, dark, and system themes
- **Playlist Management**: Full playlist functionality
- **Keyboard Shortcuts**: Customizable keyboard shortcut settings

### Core Playback Features

- Runs on UOS
- Supports common audio and video formats, including MP3, WAV, MP4, AVI, and MKV
- Volume adjustment
- Playback progress display and seeking
- Variable-speed playback, with audio and video synchronization required at different speeds
- Playback history and search
- Theme switching (light, dark, and system)
- Default playback mode settings (sequential, shuffle, play once, repeat one, and repeat all)
- Default and customizable keyboard shortcuts

### Music Recommendation System

- Combines song audio features with user playback behavior to generate recommendations
- Integrates K-Means clustering, autoencoders, and collaborative filtering algorithms
- Generates personalized music recommendation lists

### User Interface

- Resizable window
- Light, dark, and system themes
- Playback control bar
- Playlist panel
- Settings panel
- Emotion analysis interface

## Project Structure

```text
media-player-for-uos/
├── CMakeLists.txt                  # Project build configuration
├── README.md                       # Project documentation
├── src/                            # Player source code
│   ├── main.cpp                    # Application entry point
│   ├── mainwindow.[cpp/h/ui]       # Main window class
│   ├── playbar.[cpp/h/ui]          # Playback control bar
│   ├── playlist.[cpp/h/ui]         # Playlist
│   ├── setting.[cpp/h/ui]          # Settings panel
│   └── modelchat.[cpp/h/ui]        # Model interaction interface
├── resources/                      # Application resources
│   ├── qss/                        # Stylesheets
│   └── images/                     # Icon assets
├── modules/
│   └── music_recommendation/       # Music recommendation module
│       ├── recommender.py          # Main recommendation algorithm
│       ├── requirements.txt        # Python dependencies
│       └── *.csv                   # Datasets
├── packaging/
│   └── linux/                      # Desktop entry configuration
└── scripts/                        # UOS deployment scripts
```

## Technology Stack

### Frontend Technologies

- **Qt 6.7.2**: Cross-platform application framework
- **C++17**: Primary programming language
- **Qt Widgets**: User interface framework
- **Qt Multimedia**: Multimedia playback framework
- **Qt WebSockets**: Network communication component
- **QSS**: Qt stylesheets
- **CMake**: Project build tool

### Backend Technologies

- **Python 3.8+**: Recommendation algorithm implementation
- **TensorFlow / Keras**: Deep learning framework
- **scikit-learn**: Machine learning library
- **pandas / NumPy**: Data processing libraries
- **FFmpeg**: Multimedia processing tool

## Installation and Deployment

1. Download and extract the source archive from Releases
2. Run `scripts/configure-uos.sh`
3. Run `scripts/install-uos.sh` to build and install the application

### Prerequisites

- UOS or a compatible Linux distribution
- Qt 6 development environment
- Python 3.8+
- FFmpeg

### Build and Install

1. **Clone the repository**

```bash
git clone https://github.com/xinyuguo1014/media-player-for-uos.git
cd media-player-for-uos
```

2. **Configure the project**

```bash
cmake -S . -B build -DCMAKE_BUILD_TYPE=Release
```

3. **Build the project**

```bash
cmake --build build --parallel
```

4. **Install**

```bash
sudo cmake --install build
```

### Install Python Dependencies

```bash
cd modules/music_recommendation
pip install -r requirements.txt
```

## Usage

### Launch the Player

```bash
media-player-for-uos
```

### Basic Controls

- **Play / Pause**: Press Space or use the playback button
- **Volume**: Use the mouse wheel or volume slider
- **Switch Tracks**: Use the previous / next track buttons
- **Switch Themes**: Select a theme in the settings panel

### Music Recommendations

1. Right-click a song in the playlist
2. Select “Recommend Similar Songs”
3. The system will recommend similar music based on the current song
