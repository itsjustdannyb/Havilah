# Kidney Stone Detection with Detection Transformer (DETR)

Approximately 10% of people will get a kidney stone in their lifetime (National Kidney Foundation). Current diagnosis relies on radiologists manually marking out stones in medical image scans, small stones are often missed, but cause recurrent pain.
Havilah detects kidney stones in CT scans using a finetuned Facebook's Detection Transformer (DETR) model, with visualization of cross-attention maps for interpretability.

## App

The app is available [here](https://datican-test.netlify.app)

## Test Images

Download these sample images to test the model (available in media folder):

- test_img.jpg
- test_img_1.jpg

## Features

- 🏥 **Kidney Stone Detection**: Identifies kidney stones in medical images with bounding boxes
- 🔍 **Attention Visualization**: Shows cross-attention map for the highest confidence detection
- 📊 **Confidence Scores**: Displays detection confidence percentages
- 🖥️ **Web Interface**: Simple, user-friendly interface for uploading and analyzing images
- 🚀 **FastAPI Backend**: Efficient server implementation with GPU support

## Dataset

The dataset consists of CT scans containing kidney stones from kaggle. It is available [here](https://www.kaggle.com/datasets/safurahajiheidari/kidney-stone-images)

## How It Works

The application uses a fine-tuned DETR (Detection Transformer) model to:

1. Process input medical images
2. Detect kidney stones with bounding boxes
3. Generate attention maps showing where the model "looks" when making predictions
4. Display results with confidence scores and visualization overlays

## Technologies Used

### Backend

- Python 3.9+
- FastAPI (web framework)
- PyTorch (deep learning)
- HuggingFace Transformers (DETR implementation)

### Frontend

- HTML
- CSS
- JavaScript

### Deployment

The model was deployed on huggingface spaces avaialble [here](https://huggingface.co/spaces/bamswastaken/kidney-detr-datican)

- Docker (containerization)
- Uvicorn (ASGI server)

## Installation

### Prerequisites

- Python 3.9+
- pip
- Docker (optional)

### Local Setup

1. **Clone the repository:**

   ```bash
   git clone https://github.com/datican-run-undergraduates-competition/Havilah.git
   cd Havilah
   ```

2. **Install Python dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

3. **Run the FastAPI server:**

   ```bash
   uvicorn app:app --reload
   ```

4. **Open `index.html` in your browser** to access the web interface.

### Docker Setup (optional)

1. **Build the Docker image:**

   ```bash
   docker build -t havilah .
   ```

2. **Run the container:**

   ```bash
   docker run -p 8000:8000 havilah
   ```

3. **Access the web interface** at `http://localhost:8000`

## Usage

1. Click **"Choose file"** to select a medical image (ultrasound, CT scan, etc.)
2. Click **"Inspect"** to analyze the image
3. **View results:**
   - Detection bounding boxes
   - Confidence scores
   - Cross-attention heatmap overlay

## File Structure

```
Havilah/
├── media/               # Folder containing images
├── notebooks/           # Folder containing Jupyter notebook for model training
│   └── playground.ipynb # notebook
├── app.py               # FastAPI backend and detection logic
├── data.py              # The dataset for the model
├── engine.py            # The model
├── utils.py             # Utility functions
├── train.py             # Training script
├── index.html           # Web interface
├── script.js            # Frontend functionality
├── style.css            # Styling
├── Dockerfile           # Docker configuration
├── requirements.txt     # Python dependencies
└── README.md            # This file
```

## Model Details

The application uses a fine-tuned version of Facebook's DETR (Detection Transformer) model, specifically adapted for kidney stone detection, the models are available on huggingface:

- **Base Model**: `facebook/detr-resnet-50`
- **Fine-tuned Version**: `bamswastaken/datican-detr-v2`
- **Input**: Medical images (ultrasound, CT scans)
- **Output**: Bounding boxes with confidence scores and attention maps

## License

MIT License

## Team

- [Bamilosin Daniel Eniola](https://github.com/itsjustdannyb)

## Acknowledge

A huge thanks to Datican and RUNACOSS for organizing this hackathon, we really learned a lot.
All Glory to Almighty GOD!

---
