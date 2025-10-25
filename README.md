<H3>ENTER YOUR NAME:SIVAKUMAR R</H3>
<H3>ENTER YOUR REGISTER NO:212223230209</H3>
<H3>DATE:25.10.2025</H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:<H3>
Perform sentiment analysis using your Facebook data and filter the data that has only Positive feedback for the code given in the following link.
<H3>Program:</H3>
```python
import pandas as pd
from textblob import TextBlob

# Load Facebook data (CSV or Excel)
# If it's an Excel file, use pd.read_excel("facebook_data.xlsx")
df = pd.read_csv("/content/neutral_facebook_posts.csv")

# Assuming your text column is named 'message'
# If it's different, change it accordingly
def get_sentiment(text):
    analysis = TextBlob(str(text))
    polarity = analysis.sentiment.polarity
    if polarity > 0:
        return "positive"
    elif polarity < 0:
        return "negative"
    else:
        return "neutral"

# Apply sentiment analysis
df["Sentiment"] = df["message"].apply(get_sentiment)

# Filter only neutral posts
neutral_df = df[df["Sentiment"] == "neutral"]

# Display results
print("Neutral posts:")
print(neutral_df)

# Save filtered data
neutral_df.to_csv("neutral_facebook_posts.csv", index=False, encoding="utf-8")
print("✅ Neutral posts saved to neutral_facebook_posts.csv")
```
### Output:
<img width="629" height="108" alt="image" src="https://github.com/user-attachments/assets/7f395b14-fe84-43e1-ad8e-90cc6f01c92c" />

<H3>Inference:</H3>
Perform sentiment analysis using your Facebook data and filter the data that has only Positive feedback for the code given in the following link.
