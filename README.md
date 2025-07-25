# 🏞️ TrekTrail - Personalized Trek Recommendation App

**TrekTrail** is a machine learning-powered Flask web application that recommends treks in India based on your preferences and live weather conditions. The app intelligently matches your input with real trek data to help you discover the best trails suited to your needs.

🔗 **GitHub Repo:** [github.com/Anjaliahlawat14/trektrail](https://github.com/Anjaliahlawat14/trektrail)

---

##  OBJECTIVE

The goal of this project is to assist adventure seekers in discovering ideal treks by combining:

- **User preferences** (difficulty, location, trail length, preferred tags)
- **Live weather data** (temperature, wind speed)
- **Machine learning** to predict the most suitable trek

---

##  MACHINE LEARNING OVERVIEW

- **Model used:** `RandomForestClassifier` (with class weights to handle imbalance)
- **Features considered:** 
  - Difficulty, State, Best Season
  - Trail Length, Tags (multi-label)
  - Weather features (temperature, windspeed, weather code)
- **Encoding:**
  - One-Hot Encoding for categorical features
  - MultiLabelBinarizer for tags
- **Target:** Trail Name (top predicted trek returned with confidence score)

---

##  WHY WEATHER INTEGRATION?

Trek suitability depends heavily on weather. The app uses:
- **Geocoding API**: to get latitude and longitude of user-specified locations
- **Open-Meteo API**: to fetch live temperature and wind speed
- This makes recommendations realistic and seasonally aware.

---

##  WHY MAPS?

- Trek locations are displayed on an **interactive Leaflet map**
- Helps users visualize where the recommended trek is located

---

## FEATURES

- ✅ Predicts treks based on multiple inputs
- ✅ Auto-fills weather data using city input
- ✅ Top-3 trek recommendations with mismatch warnings
- ✅ Interactive map with red markers
- ✅ Supports tag-based filtering
- ✅ Export recommendations as JSON or CSV

---

## LOCAL DEPLOYMENT

### PREREQUISITIES:
- Python 3.7+
- pip
- Flask
- joblib
- gdown
- scikit-learn
- pandas, numpy, requests

### INSTALLATION:

```bash
# Clone the repo
git clone https://github.com/Anjaliahlawat14/trektrail.git
cd trektrail

# Create a virtual environment (optional but recommended)
python -m venv venv
venv\Scripts\activate     # Windows
source venv/bin/activate  # macOS/Linux

# Install dependencies
pip install -r requirements.txt
