# FinalProject-OS_FaichaiGroup

This project compares I/O performance and processing efficiency between single-thread and multi-thread approaches using audio analysis from the BirdNET-Lite model.

---

## 🔧 Setup Instructions

1. **Download the Repository**
   - Click the green **Code** button.
   - Select **Download ZIP** to get the full repository.

2. **Extract the ZIP**
   - After extracting, the folder should look like this:
     ```
     FinalProject-OS_FaichaiGroup-main/
     ├── BirdNET-Lite.zip
     ├── README.md
     ├── processing_unit_test.ipynb
     ├── read_write_test.ipynb
     └── sample.wav
     ```

3. **Note:** You do **not** need to unzip `BirdNET-Lite.zip`.
   - For your reference, it contains the following:
     ```
     BirdNET-Lite/
     ├── analyze.py
     ├── Audio_example/
     ├── Audio_result/
     ├── model/
     └── requirements.txt
     ```

---

## ▶️ Running on Google Colab

### 🔁 I/O Comparison Test

1. Open `read_write_test.ipynb` on [Google Colab](https://colab.research.google.com).
2. Import the `sample.wav` file into the Colab environment.
3. Run cells to test I/O behavior and logging.
4. **To change the processing unit** (e.g., CPU, GPU):
   - Click `Runtime` > `Change runtime type`.
   - Select `Hardware accelerator: CPU/GPU/TPU` as needed.

---

### 🧵 Processing Unit Comparison

1. Open `processing_unit_test.ipynb` in Google Colab.
2. Upload and extract `BirdNET-Lite.zip`.
3. **Run the following setup commands before proceeding**:
   ```python
   !pip uninstall -y jax jaxlib tensorflow tflite-runtime numpy
   !pip cache purge
   !pip install soundfile resampy numpy==1.24.4 tensorflow==2.15.0
4. Follow the sequence of cells to run audio analysis with:
   - Single-thread
   - Multi-thread using `ThreadPoolExecutor`
5. **To change runtime type (e.g., to GPU/CPU)**:
   - Go to `Runtime` > `Change runtime type`.
   - Choose your desired hardware accelerator.
6. **To change the thread size**:
   - Find the line:
     ```python
     with ThreadPoolExecutor(max_workers=4) as executor:
     ```
   - Adjust `max_workers` (e.g., `2` for 2 files processed in parallel).

---
> ⚠️ **Note:** Processing time and performance results may vary depending on your internet connection and the current load on Google Colab's servers.
---

Sec1 - Faichai Group
