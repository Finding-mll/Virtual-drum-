# Virtual Drums README

## Project Overview

The Virtual Drums project uses computer vision techniques to detect the presence of a green object within designated regions of the video feed from a webcam. When the green object is detected in these regions, corresponding drum sounds (high hat and snare) are played. This allows users to play virtual drums by simply waving a green object in front of their webcam.

## Installation

1. **Clone the Repository:**
   ```
   git clone <repository_url>
   cd <repository_directory>
   ```

2. **Install Required Libraries:**
   This project requires several Python libraries, including `numpy`, `opencv-python`, and `pygame`. You can install them using pip:
   ```
   pip install numpy opencv-python pygame
   ```

3. **Prepare Assets:**
   Ensure you have the following files in the appropriate directories:
   - Drum sounds:
     - `./sounds/high_hat_1.ogg`
     - `./sounds/snare_1.wav`
   - Drum images:
     - `./images/high_hat.png`
     - `./images/snare_drum.png`

## Usage

1. **Run the Script:**
   ```
   python main.py
   ```

2. **Using the Virtual Drums:**
   - Hold a green object and wave it within the designated regions on your webcam feed to play the drums.
   - The high hat region is on the left side of the screen, while the snare drum region is on the right.
   - The title "Virtual Drums" will appear at the top of the screen.
   - Press 'Q' to exit the application.

## Project Structure

- `main.py`: Main script containing the entire code.
- `./sounds/`: Directory containing drum sound files.
- `./images/`: Directory containing drum image files.

## Code Explanation

### Importing Libraries
```python
import numpy as np
import time
import cv2
from pygame import mixer
```

### Functions

- **`play_beat(detected, sound)`**: Plays the corresponding drum beat if a green object is detected in the region.
- **`detect_in_region(frame, sound)`**: Checks if green color is present in the specified region of the frame and triggers `play_beat`.

### Initial Setup
- Initialize Pygame mixer.
- Define HSV ranges for detecting green color.
- Obtain input from the webcam.
- Define regions for the high hat and snare drum.

### Main Loop
- Continuously capture frames from the webcam.
- Detect green objects in the specified regions.
- Play corresponding drum sounds if green objects are detected.
- Display the video feed with either the regions highlighted or drum images overlaid.

### Exit and Cleanup
- Release the webcam and destroy all OpenCV windows on exiting.

## Notes
- Ensure your webcam is properly connected and recognized by the system.
- Adjust the HSV values for detecting green color if necessary, depending on lighting conditions and the shade of green object used.

## Troubleshooting
- If no sound is played, check if the sound files are correctly placed in the `./sounds/` directory.
- If the script fails to start, ensure all required libraries are installed and compatible with your Python version.
- Adjust the green color detection ranges if the object is not being recognized.

## License
This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Contributing
Feel free to submit issues and pull requests to contribute to this project. For major changes, please open an issue first to discuss what you would like to change.

## Acknowledgements
This project was inspired by the potential to use computer vision for interactive applications. Special thanks to the developers of the libraries and tools used in this project.

---

Feel free to customize this README to better fit your project's details and specific requirements.
