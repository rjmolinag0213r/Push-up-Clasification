
# 📄 Push-Up Pose Estimation and Counter – Documentation

This Python script uses OpenCV and MediaPipe to detect push-up movements through webcam input. It calculates key body angles to classify the current pose and counts valid push-up repetitions.

---

## 📦 Dependencies

Install the following packages (for Jupyter or Colab):

```bash
%pip install opencv-python-headless
%pip install mediapipe
%pip install matplotlib
```

If you're running outside of Jupyter (e.g., in VS Code), install the full OpenCV:

```bash
pip install opencv-python mediapipe matplotlib
```

---

## 🧠 Modules and Functions

### `calculateAngle(a, b, c)`
Calculates the angle (in degrees) between three 2D points.

- **Params:** `a`, `b`, `c` - Pose landmarks (shoulder, elbow, wrist, etc.)
- **Returns:** The angle between the points

---

### `classifyPose(landmarks, output_image)`
Classifies the current body pose using joint angles.

- **Params:**
  - `landmarks`: List of pose landmarks
  - `output_image`: Frame to display the classification text
- **Returns:**
  - `output_image`: Frame with the pose label overlaid
  - `label`: A string label representing the classified pose

#### Pose Logic:
- `Push-Up Start Position`: Arms extended, shoulders around 70–80°, elbows ~170°
- `Push-Up Down Position`: Arms bent, shoulders around 15–25°, elbows ~50°

---

## 🔄 Main Loop

1. Captures webcam frames.
2. Converts each frame to RGB for MediaPipe processing.
3. Extracts pose landmarks.
4. Uses `classifyPose()` to determine current pose.
5. If a full push-up motion is detected (down → up), increments a repetition counter.
6. Displays:
   - **Pose label** (e.g., "Push-Up Down Position")
   - **Repetition counter** (e.g., "Push-Ups: 5")

For Jupyter:
- Uses `matplotlib.pyplot` to render the frame inline.
- Uses `clear_output(wait=True)` to simulate live video.

---

## 🖥️ Running Options

### ▶️ In Jupyter/Colab:
- Keep `matplotlib` for inline image display.
- Avoid using `cv2.imshow()` as it will not work in notebook environments.

### ▶️ In VS Code or Standalone Python:
- Replace `plt.imshow()` and `plt.show()` with:

```python
cv2.imshow("Push-Up Tracker", frame)
if cv2.waitKey(1) & 0xFF == ord('q'):
    break
```

---

## 🔚 Ending
At the end, the webcam is safely released using `cap.release()`.

---

## 📝 Customization Ideas

- Add a goal tracker (e.g., stop at 10 reps)
- Add sound feedback using `playsound`
- Export performance logs (date, reps) to CSV
- Display average time per push-up

---
