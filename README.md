# Practice-Buzz-assignment
Golf player pose estimation

---

## 1. Model Used and Rationale

**Model:** YOLOv8-Pose (Ultralytics)

**Reason for Selection:**  
YOLOv8-Pose installs cleanly and runs reliably in Google Colab without dependency issues. It provides direct human keypoint coordinates (including shoulders, elbows, wrists), making it well-suited for computing joint angles. The model is lightweight, fast, and accurate enough for per-frame pose analysis.

---

## 2. Metric Computed

**Metric:** Elbow joint angle  
(Computed at the elbow using the three points: *shoulder → elbow → wrist*)

**Mathematical Definition:**

\[
\theta = \cos^{-1}\left(\frac{(S - E) \cdot (W - E)}{\|S - E\|\|W - E\|}\right)
\]

where:  
- **S** = shoulder keypoint  
- **E** = elbow keypoint  
- **W** = wrist keypoint  

Angles are expressed in degrees.

---

## 3. Numeric Results

### Per-Frame Elbow Angles

| Frame | Left Elbow (°) | Right Elbow (°) |
|-------|----------------|-----------------|
| frame_1_47.jpg  | 155.2 | 156.6 |
| frame_2_103.jpg | 150.4 | 169.5 |
| frame_3_374.jpg | 7.3   | 73.7  |
| frame_4_619.jpg | 116.6 | 142.8 |
| frame_5_640.jpg | 103.8 | 131.2 |
| frame_6_654.jpg | 95.1  | 134.7 |
| frame_7_686.jpg | 64.3  | 102.4 |
| frame_8_750.jpg | 67.1  | 150.7 |

### Overall Change (First Frame → Last Frame)

- **Left elbow angle:** decreased by **88.1°**  
- **Right elbow angle:** decreased by **5.9°**

---

## 4. Interpretation

The left elbow shows a large decrease in angle across the sequence, indicating a major transition from a nearly straight arm to a highly bent posture and then partially extending again. The right elbow shows a far smaller overall change, suggesting a more stable movement pattern on that side. These angle variations reflect arm motion dynamics within the captured golf-swing sequence, independent of swing-specific domain knowledge.

---

## 5. Pose Observations (Per Frame)

