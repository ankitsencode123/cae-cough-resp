# Respiratory Sound Analysis for COPD Detection

Welcome to this project!  
If you've ever been curious about how artificial intelligence can help us understand health conditions, you're in the right place.  
This project focuses on analyzing **respiratory sounds** to detect **Chronic Obstructive Pulmonary Disease (COPD)**.

---

## What's the Big Idea?

We're using a **Deep Convolutional Autoencoder**, a type of deep learning model.  
Rather than training it on both healthy and unhealthy breathing sounds, we train it **only on normal, healthy breathing**.

When the model encounters a sound that doesn’t match its learned pattern — such as a COPD-affected breath — it **fails to reconstruct it accurately**. This results in a **high reconstruction error**, which we use to **flag potential anomalies** in respiratory health.

---

## The Dataset

The model is trained on the **Respiratory Database** available on **Kaggle**.  
Using the `kagglehub` library, the dataset is downloaded automatically — no manual download needed.

It includes:
- Audio files from various individuals
- Labels indicating whether each subject is healthy or affected

---

## How to Get Started

Want to try this out yourself? Here's how:

1. **Set Up Your Environment**  
   Make sure you have Python installed. It's best to use a virtual environment.

2. **Install Dependencies**  
   Run the following command to install required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Code**  
   The main notebook is `cae-cough-resp.ipynb`.  
   Run it top to bottom — it handles:
   - Downloading data
   - Training the model
   - Displaying results

> Note: If you have a CUDA-enabled GPU, training will be significantly faster. Otherwise, it defaults to CPU.

---

## Results

After training and evaluation, the model showed strong performance:

- **Overall Accuracy**: 97.6%  
- **Sensitivity**: 100%  
  (All subjects with COPD were correctly identified.)
- **Specificity**: 83.3%  
  (Most healthy subjects were correctly classified.)
- **AUC Score**: 0.99  
  (Excellent ability to distinguish between healthy and diseased cases.)

The reconstruction error plots clearly separate healthy from COPD-affected subjects, confirming that this approach is effective.

---

Thanks for checking out the project!
