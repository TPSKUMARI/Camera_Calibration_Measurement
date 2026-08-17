# Camera Calibration and Measurement

This project helps you calibrate a USB camera and then use it to measure distance in millimeters.

## Project idea

The workflow is simple:

1. Calibrate the camera using a known distance.
2. Save the calibration result in `calibration.json`.
3. Use the saved value to measure distances from live camera frames.

## Files

- `camera_calibrate.py` - calibrates the camera by capturing frames and measuring pixel distance between two selected points.
- `camera_measure.py` - loads the saved calibration and measures the distance between two clicked points in real time.
- `calibration.json` - stores the camera calibration values.

## How it works

### Calibration

Run:

```bash
python camera_calibrate.py
```

- The camera opens in live view.
- Press Enter to capture a frame.
- Click two points on the image.
- Enter the actual distance between those points in millimeters.
- Repeat the process a few times to get an average calibration value.

The result is saved in `calibration.json` as `pixels_per_mm`.

### Measurement

Run:

```bash
python camera_measure.py
```

- The script loads the saved camera calibration.
- Press Enter to capture a live frame.
- Click two points on the image.
- The program calculates the distance in millimeters.

## Requirements

- Python 3
- OpenCV (`cv2`)
- A USB camera connected to the system

## Notes

- Camera index is set to `1` in the scripts, which usually works for the first external USB camera.
- If your camera is different, you may need to change the camera index value.

## Example use case

This can be useful for:

- measuring object lengths
- checking real-world dimensions from camera footage
- simple machine vision calibration tasks
