# Sign Language Detection

This project implements a real-time sign language detection system using a webcam. It leverages hand tracking and classification to recognize specific hand gestures and map them to predefined labels.

## Project Structure

```
Sign-Language-detection/
├── datacollection.py       # Script for collecting training data
├── test.py                 # Script for testing the trained model
├── Model/
│   ├── keras_model.h5      # Pre-trained Keras model for classification
│   ├── labels.txt          # Labels corresponding to the gestures
```

### File Descriptions

- **`datacollection.py`**:

  - Captures hand gestures using a webcam and saves them as images for training purposes.
  - The images are cropped and resized to a fixed size (`300x300`) and saved in the specified folder.

- **`test.py`**:

  - Uses a pre-trained model (`keras_model.h5`) to classify hand gestures in real-time.
  - Displays the detected gesture label on the screen along with the cropped and processed hand image.

- **`Model/keras_model.h5`**:

  - A pre-trained Keras model used for gesture classification.

- **`Model/labels.txt`**:
  - A text file containing the labels corresponding to the gestures recognized by the model.

## Requirements

- Python 3.x
- OpenCV
- NumPy
- cvzone
- TensorFlow/Keras

Install the required dependencies using:

```bash
pip install opencv-python numpy cvzone tensorflow
```

## Usage

### 1. Data Collection

To collect training data for new gestures:

1. Update the `folder` variable in `datacollection.py` to specify the folder where images will be saved.
2. Run the script:
   ```bash
   python datacollection.py
   ```
3. Press the `s` key to save the current frame as an image.

### 2. Testing the Model

To test the pre-trained model:

1. Ensure the `keras_model.h5` and `labels.txt` files are in the `Model/` directory.
2. Run the script:
   ```bash
   python test.py
   ```
3. The script will display the detected gesture label in real-time.

## How It Works

1. **Hand Detection**:

   - Both scripts use the `cvzone.HandTrackingModule` to detect hands in the webcam feed.

2. **Image Preprocessing**:

   - The detected hand is cropped and resized to a fixed size (`300x300`) while maintaining the aspect ratio.

3. **Classification**:
   - The processed image is passed to the pre-trained model (`keras_model.h5`) for classification.
   - The predicted label is displayed on the screen.

## Labels

The following gestures are recognized by the pre-trained model:

1. Hello
2. I love you
3. No
4. Okay
5. Please
6. Thank you
7. Yes

## Future Improvements

- Add support for more gestures.
- Improve the accuracy of the model by collecting more training data.
- Implement a GUI for easier interaction.

## License

This project is licensed under the MIT License. Feel free to use and modify it as needed.
