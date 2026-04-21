<H3>ENTER YOUR NAME : Prashanth K </H3>
<H3>ENTER YOUR REGISTER NO: 212223230152 </H3>
<H3>DATE: 21.04.2026 </H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:<H3>
The objective of this project is to perform sentiment analysis on extracted Facebook text data using Python and to count the number of occurrences of my name in the dataset. This experiment helps in understanding text processing, sentiment classification, and basic natural language processing techniques.
<H3>Program:</H3>
  
```
from textblob import TextBlob
import matplotlib.pyplot as plt

# Read Facebook-like text data
with open("facebook_data.txt", "r", encoding="utf-8") as file:
    comments = file.readlines()

positive = 0
neutral = 0
negative = 0
positive_comments = []

name = "Stephen"
name_count = 0

# Process each comment
for comment in comments:
    analysis = TextBlob(comment)
    polarity = analysis.sentiment.polarity

    # Sentiment classification
    if polarity > 0:
        positive += 1
        positive_comments.append(comment.strip())
    elif polarity < 0:
        negative += 1
    else:
        neutral += 1

    # Count name occurrences
    name_count += comment.lower().count(name.lower())

# Display sentiment counts
print("Sentiment Analysis Results:")
print("Positive Comments:", positive)
print("Neutral Comments:", neutral)
print("Negative Comments:", negative)

print(f"\nNumber of occurrences of '{name}':", name_count)

# Display sample positive feedback
print("\nSample Positive Feedback:")
for c in positive_comments[:2]:
    print("-", c)

# Plot sentiment distribution
sentiments = ["Neutral", "Positive", "Negative"]
counts = [neutral, positive, negative]

plt.bar(sentiments, counts)
plt.title("Facebook Comments Sentiment Distribution")
plt.xlabel("Sentiment")
plt.ylabel("Number of Comments")
plt.show()
```
<H3>Output:</H3>

<img width="771" height="533" alt="image" src="https://github.com/user-attachments/assets/abca9120-db53-436d-afc0-820de33997c8" />

<H3>Inference:</H3>

From this project, I learned how social media text data can be analyzed using sentiment analysis techniques. I understood how to preprocess text data, apply sentiment polarity scoring using Python libraries, and count specific word occurrences efficiently. This experiment improved my understanding of Natural Language Processing and real-world data analysis using Python.
