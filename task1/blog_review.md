# Blog Review

## Blog Title

Can Your Camera Tell if You're Bored in Class?

## Author

Samiksha Patil

## Summary

Facial Emotion Recognition using MediaPipe
The research explains a Facial Emotion Recognition (FER) pipeline using Computer Vision, AI and Google’s MediaPipe. A camera captures the face, and MediaPipe Face Mesh represents it using 468 precise 3D landmarks. Each landmark has x, y and z coordinates, giving a mathematical representation of facial expressions and allowing even subtle changes to be captured.
Stage 1 :- Face and Landmark Detection: The system finds the face and places 468 landmarks on it. The actual image is not necessary after extracting these coordinates, so facial information can be represented as 468 × 3 = 1,404 numbers.
Stage 2 :- Normalization: Facial coordinates vary because of head pose, camera angle, distance and face size. Procrustes Analysis applies rotation, scaling and translation to align faces to the same position and size. This lets the model concentrate on expressions rather than individual facial structure.
Stage 3 :-Feature Extraction: Three approaches are discussed. Geometric Feature Engineering manually measures distances and movements using domain knowledge, such as FACS (Facial Action Coding System) and its Action Units. It is interpretable but tedious and may miss texture-based expressions. Deep Learning on Raw Coordinates directly feeds coordinates to a neural network. A difference vector (Δ) can be created by subtracting a neutral face from an emotional face, leaving mainly the expression-related change. The third approach uses MediaPipe’s 52 pre-calculated blendshape scores, avoiding manual measurements and training a separate network for basic feature extraction.
Stage 4 :- Classification: Extracted features are classified using Random Forest, SVM (Support Vector Machine), CNN (Convolutional Neural Network), GNN (Graph Neural Network), or MLP (Multilayer Perceptron).
Thus, the overall pipeline is Camera → Face Detection → 468 Landmarks → Normalization → Feature Extraction → Classification → Emotion Prediction.

