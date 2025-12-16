# Wearable ECG for Subject Identification using Deep Learning
## 📌 Overview
The science of biometric recognition leverages statistical techniques to uniquely identify individuals based on their physical and behavioral characteristics. This approach provides secure and effective alternatives to traditional authentication methods, addressing critical issues in access control.
Among the many biometric identifiers—such as fingerprints, facial features, retinal structures, or voice—each must be tamper‑proof, timeless, and unique to reliably represent a person. However, these traits often face limitations due to the technologies and instruments required for acquisition.
The electrocardiogram (ECG) signal has emerged as a promising biometric attribute thanks to its subject‑dependent features, ease of acquisition via wearable devices, and resilience against falsification. Recent advances in wearable technology have enabled ECG monitoring outside laboratory settings, greatly enhancing accessibility.
At the same time, Deep Neural Networks (DNNs) have proven highly effective in extracting and discriminating individual features from ECG signals, without requiring specialist medical evaluation. 

## Aim
This project explores the use of the Polar H10 chest strap as a wearable sensor for accessible ECG acquisition, with the goal of performing subject identification among a group of volountary participants.

📂 Dataset
- 15 subjects (23 ± 3 years old) with no cardiovascular diseases
- Data have been acquired with Polar H10 chest strap in two conditions:
  * Rest dataset (≥120 s, seated)
  * Task dataset (≥150 s: rest → jumping jacks → recovery)

🛠 Pre‑processing Pipeline
- Interpolation for variable sampling frequency
- Baseline wander removal (median filters)
- Normalization & band‑pass filtering (0.667–65 Hz)
- Segmentation & cleaning (peak detection, resampling, noise removal)
- Segment merging (concatenation of 12 segments, smoothing)
- Spectrogram generation (Tukey window, replicated to 42×42 images)
  
⚙️ Deep Learning Models
- Fully‑Connected NN (Dense NN) → lightweight, fast, good on rest data
- Recurrent NN (RNN) → captures temporal dynamics, best overall performance
- 2D CNN → spectrogram‑based, underperformed, requires further investigation
