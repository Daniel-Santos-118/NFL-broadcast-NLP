# NFL-broadcast-NLP
NLP model that will ultimately be used for event prediction for NFL games, based on data from broadcast

## Key Features
- **Model Type:** Hybrid Machine Learning Model
- **Purpose:** Real-time prediction of live prop bets and NFL stats.
- **Integration:** Mobile application with live audio transcription and prediction capabilities.

---

## Data Sources
The model uses two primary datasets:

1. **Detailed NFL Play-by-Play Data 2009-2018**  
   [Link to Dataset](https://www.kaggle.com/datasets/maxhorowitz/nflplaybyplay2009to2016/suggestions?status=pending&yourSuggestions=true)

2. **Football Commentary Data Set**  
   [Link to Dataset](https://www.kaggle.com/datasets/patzshane/football-commentary-data-set-college-and-nfl)

### Data Preprocessing
#### Football Commentary Data Set:
- Removed older and college game transcripts.
- Split play-by-play segments using regex.
- Extracted features using **BERT** and regex, saved in `.json` format.

Splits:
- **Training Set (80%):** 675 files  
- **Validation Set (10%):** 85 files  
- **Test Set (10%):** 84 files  

#### Detailed NFL Play-by-Play Data 2009-2018:
- Eliminated unnecessary stats.
- Converted data from `.csv` to `.json` format.

---

## Model Architecture
The model employs a hybrid structure combining text and numerical data processing with a late fusion architecture.

### 1. **Textual Data Layer**
- Tokenization and de-noising of input text.
- Transfer Learning: Fine-tuned **BERT** model for meaningful feature extraction.
- Feature Mapping: Rule-based assignments, ML-based predictions, and static metadata.
- Includes layers for binary and multi-class classification.

### 2. **Numerical Data Layer**
- Processes numerical play-by-play data using a **feed-forward neural network**.

### 3. **Fusion Model Layer**
- Combines outputs from the Textual and Numerical Data Layers in a late fusion architecture.
- Uses concatenation followed by dense layers for integrated prediction.

### 4. **Time-Series Layer**
- Incorporates a **Time-BERT-like transformer** for sequence-based prop bets and predictions.

---

## Training
- **Loss Function:** Binary Cross-Entropy Loss
- **Evaluation Metrics:**
  - Accuracy
  - Precision/Recall (for rare events)
  - ROC-AUC (for multi-class predictions)

---

## Deployment
A robust pipeline is planned for deployment to ensure real-time processing and predictions:

1. **Real-Time Transcription:** Extract transcripts from live broadcasts.
2. **Data Analysis:** Process and analyze the data to make predictions.
3. **User Interface:** Integrate the predictions into a user-friendly app interface for bettors.

---

## Acknowledgements
Special thanks to the contributors and the Kaggle community for providing the datasets essential for this project.

