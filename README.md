# 👗 Fashion MNIST End-to-End Classifier

A deep learning project that trains a **CNN** on the [Fashion MNIST](https://github.com/zalandoresearch/fashion-mnist) dataset and deploys it as a **Streamlit** web app inside a **Docker** container.

---

## 📁 Project Structure

```
├── app/
│   ├── main.py                    # Streamlit web application
│   ├── Dockerfile                 # Docker configuration
│   ├── requirements.txt           # Python dependencies
│   ├── config.toml                # Streamlit server config
│   └── trained_model/
│       └── trained_fashion_mnist_model.h5
├── model_training_notebook/
│   └── Fashion_MNIST_model_training.ipynb
└── test_images/                   # Sample test images
```

---

## 🧠 Model Architecture

A **Sequential CNN** built with TensorFlow/Keras:

- Conv2D(32) → MaxPool → Conv2D(64) → MaxPool → Conv2D(64) → Flatten → Dense(64) → Dense(10)
- **Optimizer**: Adam | **Loss**: Sparse Categorical Crossentropy | **Epochs**: 5
- **Test Accuracy**: ~90.1%

**10 Classes**: T-shirt/top · Trouser · Pullover · Dress · Coat · Sandal · Shirt · Sneaker · Bag · Ankle boot

---

##  Getting Started

### Run Locally

```bash
cd app
pip install -r requirements.txt
streamlit run main.py
```
Open `http://localhost:8501`

### Run with Docker

```bash
cd app
docker build -t fashion-mnist-classifier .
docker run -p 80:80 fashion-mnist-classifier
```
Open `http://localhost`

---

## 🖼️ How It Works

1. **Upload** a fashion item image (JPG/PNG) via the Streamlit UI
2. Image is **preprocessed** — resized to 28×28, converted to grayscale, normalized
3. Click **Classify** — the CNN predicts the category
4. **Prediction** is displayed on screen

---

## 🔧 Tech Stack

**TensorFlow 2.15** · **Streamlit 1.30** · **NumPy 1.26** · **Pillow** · **Docker (Python 3.10-slim)** · **Google Colab (T4 GPU)**
