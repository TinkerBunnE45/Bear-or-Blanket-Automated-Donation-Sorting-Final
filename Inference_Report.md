 Inference Report: Project Jumpstart## Success Cases

* Folded Blankets: The model excelled at identifying folded blankets due to the strong geometric edges (HOG features).
* Standard Bears: Bears with visible facial features (eyes/nose) were identified with high confidence.

## Failure Cases: The "White Teddy Bear"

* Why it failed: The white bear was misclassified as a blanket. Its long, fluffy fur created a texture (LBP) nearly identical to white fleece blankets. Without visible "semantic features" (eyes) in the profile shot, the AI defaulted to the majority class (Blanket).

## Comparison with Baseline

| Approach | Accuracy | Speed |
|---|---|---|
| Manual Sorting | N/A | ~2 hours per bin |
| Simple CNN | 55% | 0.02s |
| Our ResNet50 System | 67.6% | 0.08s |

## Key Learnings## What Worked Well

   1. Transfer Learning: ResNet50 allowed us to reach 67% accuracy with only 400 images.
   2. Data Augmentation: Including "scrunched" blanket photos helped the model learn real-world textures.
   3. Class Weighting: Using weights (1.0 vs 2.0) prevented the model from ignoring teddy bears.

## Challenges Faced

* Class Imbalance: 125 more blankets than bears. Fix: Implemented class_weight in Keras.
* Texture Overlap: Fleece vs. Fur. Fix: Used multi-angle shots to help the AI find shape-based clues.

## What We'd Do Differently

   1. Hard Example Mining: Specifically collect more photos of white fluffy items to fix the "White Bear" error.
   2. Dataset Balance: Gather 125 more "scrunched" bear photos for a perfect 1:1 ratio.
   3. 3D Profiling: Implement a "multi-view" check where the AI looks at three angles before deciding.

