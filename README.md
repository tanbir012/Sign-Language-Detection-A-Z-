# Sign Language Detection (A–Z)

**Description**
Real-time Sign Language Detection (A–Z) using MediaPipe for hand landmarks + a classifier (Neural Network). Collects video frames, extracts landmarks, trains a model and exposes a Streamlit demo to test live webcam predictions.

**Features**
- MediaPipe Hands for landmark extraction
- Data collection script (per-letter)
- Landmark feature extraction & dataset saving (CSV / NPZ)
- Keras model training (saved to model/sl_model.h5)
- Streamlit app for real-time inference

**Dataset**
You can collect your own using `data_collection.py` (recommended) or use existing ASL datasets.

**How to run**
1. Install requirements: `pip install -r requirements.txt`
2. Collect data:
   `python data_collection.py --letter A --samples 300`
3. Extract landmarks / build dataset:
   `python extract_landmarks.py --data_dir ./collected_data --out dataset.npz`
4. Train model:
   `python train_model.py --data dataset.npz --out model/sl_model.h5`
5. Run demo:
   `streamlit run streamlit_app.py`

**Author**
Tanbir — AI/ML Developer Intern, CTTC BBSR
