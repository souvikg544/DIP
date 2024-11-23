


### **Task 1: Image Segmentation Using Thresholding**  
- **Binary Thresholding** is simple but struggles with uneven lighting.  
- **Adaptive Thresholding** handles varying lighting better by calculating thresholds locally, resulting in more accurate segmentation.  
- **Otsu's Thresholding** provided the clearest segmentation by automatically determining the optimal global threshold, effectively separating objects from the background in well-illuminated images.

---

### **Task 2: Line Detection Using Hough Transform**  
- **Canny Edge Detection** successfully highlighted edges for Hough Transform processing.  
- Optimal thresholds for \((\rho, \theta)\) improved line clarity and reduced false detections.  
- Increasing thresholds reduced noise but missed faint lines, while lower thresholds captured more lines, including noise.  

---

### **Task 3: Circle Detection Using Hough Circle Transform**  
- Preprocessing with smoothing (e.g., Gaussian filter) improved circle detection accuracy.  
- Adjusting radius ranges and accumulator thresholds refined detection by focusing on circles of interest.  
- Larger thresholds reduced false detections but sometimes missed smaller or faint circles.  

---

### **Task 4: Harris Corner Detection**  
- The Harris method effectively detected strong corners in structured images.  
- Lower sensitivity values (\(k\)) over-detected edges, while higher \(k\) values missed subtle corners.  
- Optimal \(k = 0.04\) balanced precision and recall, marking corners clearly and accurately.

### Task 5 : 
QS: **In 100-150 words, explain how the Hough Transform differs when detecting
lines versus circles in an image. Discuss how parameter space and computational complexity vary between these applications**


The Hough Transform adapts differently when detecting lines versus circles, primarily through variations in parameter space representation and computational complexity. For line detection, the transform maps image points to sinusoidal curves in a parametric space defined by line slope (m) and intercept (b), requiring two-dimensional parameter space. In contrast, circle detection demands a three-dimensional parameter space representing circle center coordinates (x, y) and radius (r), significantly increasing computational complexity.
Line detection involves mapping points to sine curves that intersect at potential line parameters, with peak accumulator values indicating line candidates. Circle detection requires more complex voting mechanisms, where each point votes for potential circle centers and radii, necessitating a more extensive parameter search and higher computational overhead. The increased dimensionality in circle detection makes the algorithm substantially more resource-intensive compared to line detection.