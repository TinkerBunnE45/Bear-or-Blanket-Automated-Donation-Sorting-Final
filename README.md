# Bear-or-Blanket-Automated-Donation-Sorting-Final
Bear or Blanket?(AutomatedDonation Sorting)​
<img width="1654" height="816" alt="image" src="https://github.com/user-attachments/assets/772448a2-6f6d-42ca-b966-3b6bb9327022" />

Team Members: ​

Kala Hayes: Get the dataset and set up the environment/test document
Zaha Muhammad: Created Presentation
Andy Nguyen Role: Created demo video
Tirimisiyu Tewogbola: test document​
Yolanda Armstrong: test document​

Problem & Solution
The Problem: Charities like VA Jumpstart receive massive amounts of mixed donations. Sorting "Essential Bedding" (blankets) from "Comfort Items" (teddy bears) is a manual bottleneck that delays the delivery of move-in kits to homeless veterans.

Our Solution: An AI-powered classifier using ResNet50 that automatically identifies and sorts blankets and bears, even when they are crumpled or scrunched in a donation bin.
Impact: Reduces manual sorting time by over 50%, ensuring veterans transitioning into housing receive their essential bedding on their very first night.

Task: Binary Image Classification
* Model: ResNet50 (Transfer Learning)
* Framework: TensorFlow / Keras
* Key Libraries: tensorflow, opencv-python, matplotlib, numpy, scikit-learn

System Architecture
[Input Photo] → [Resizing (224x224)] → [ResNet50 Base] → [GlobalAveragePooling] → [Dense Layer] → [Softmax Output]

Dataset

* Source: Hybrid (Custom-shot photos of folded/rolled/crumbled items + Roboflow Universe).
* Size: 400 total images.
* Classes: teddy_bear, blanket.
* Split: Train: 320 images, Val: 80 images.
* Preprocessing: Resizing, Data Augmentation (random rotation, zoom, horizontal flip), and Normalization.

Results

| Metric | Value |
|---|---|
| Accuracy | 67.6% |
| Precision | 71.2% |
| Recall | 65.4% |
| Inference Time | 0.08s per image |


