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


df = pd.read_csv("/content/neutral_facebook_posts.csv")

def get_sentiment(text):
    analysis = TextBlob(str(text))
    polarity = analysis.sentiment.polarity
    if polarity > 0:
        return "positive"
    elif polarity < 0:
        return "negative"
    else:
        return "neutral"

df["Sentiment"] = df["message"].apply(get_sentiment)

neutral_df = df[df["Sentiment"] == "neutral"]

print("Neutral posts:")
print(neutral_df)

neutral_df.to_csv("neutral_facebook_posts.csv", index=False, encoding="utf-8")
print("✅ Neutral posts saved to neutral_facebook_posts.csv")
```
<H3>OUTPUT:</H3>
<img width="587" height="96" alt="image" src="https://github.com/user-attachments/assets/dcf43334-ff96-460f-bce5-48b383145788" />
