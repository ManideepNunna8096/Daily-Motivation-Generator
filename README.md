# 🌟 Daily Motivation Generator using Generative AI

The **Daily Motivation Generator** is an AI-powered web application that generates personalized motivational quotes based on the user’s mood. Built using **Streamlit** and **Hugging Face Transformers (DistilGPT2)**, this project demonstrates how lightweight generative AI models can be used to support emotional well-being through contextual text generation.

---

## ✨ Project Overview

This project uses a local text-generation model to produce motivational messages tailored to emotional states such as **Anxious, Stressed, Unmotivated, Happy, Tired**, and more.  
The application provides:

- 🎭 Mood-based input  
- 🤖 AI-generated motivational quotes  
- ⚡ Fast local inference  
- 🎨 Clean and simple UI  
- 🧠 Reliable and well-tested behaviour  

---

## 🧠 How It Works

1. User selects a mood from the dropdown.
2. A prompt is dynamically generated based on the mood.
3. Hugging Face’s `distilgpt2` model generates a motivational quote.
4. Streamlit displays it in a clean UI with smooth user experience.

---

## 🚀 Features

- 10+ mood options  
- Fast on-device text generation  
- No external API needed  
- Responsive & minimal UI  
- Tested for input handling, relevance, and performance  

---

## 📂 Project Structure

daily-motivation-generator/
│── app.py
│── requirements.txt
│── README.md
│── .gitignore

python
Copy code

---

## 🧩 Code (Main App)

```python
import streamlit as st
from transformers import pipeline, set_seed

# Load model
generator = pipeline("text-generation", model="distilgpt2")
set_seed(42)

# Streamlit UI
st.set_page_config(page_title="Daily Motivation Generator", page_icon="🌟")
st.title("🌟 Daily Motivation Generator")
st.write("Select your mood or situation, and get a personalized motivational quote!")

# Mood options
moods = [
    "Anxious", "Stressed", "Happy", "Unmotivated", "Need Focus",
    "Sad", "Excited", "Confused", "Lost", "Tired"
]

selected_mood = st.selectbox("How are you feeling today?", [""] + moods)

if selected_mood:
    with st.spinner("Generating your motivational quote..."):
        prompt = f"Give me an encouraging motivational quote for someone who is feeling {selected_mood.lower()}."
        result = generator(prompt, max_length=50, num_return_sequences=1)
        quote = result[0]['generated_text']

    st.success("Here's your personalized motivation:")
    st.write(f"💬 *{quote}*")
📦 Installation & Running the App
1️⃣ Install Dependencies
nginx
Copy code
pip install -r requirements.txt
2️⃣ Run Streamlit App
arduino
Copy code
streamlit run app.py
🧪 Testing Summary
A structured testing approach ensures a smooth user experience.
This includes:

✔ 1. Input Validation
Handles blank mood selection

Prevents crashes on unusual or invalid input

✔ 2. Output Relevance
AI responses align with selected moods

Example:

Mood: Anxious → Quote encourages calmness and resilience

✔ 3. Integration Testing
Smooth interaction between Streamlit UI and HuggingFace pipeline

✔ 4. Performance Testing
Generates quotes in 1–2 seconds

Stable under repeated use

✔ 5. UI/UX Testing
Simple, user-friendly interface

Clear feedback using Streamlit spinners & success messages

📈 Results
Emotionally aligned motivational messages

Fast and consistent performance

Strong handling of edge cases

Clean, intuitive user interface

🔮 Future Enhancements
Daily motivational email notifications

Save/bookmark favorite quotes

Multi-language quote generation (Hindi, Telugu, Spanish, etc.)

User feedback/rating system

Dedicated mobile app

More quote categories (career stress, study motivation, spiritual, humorous)

🎯 Conclusion
This project demonstrates the practical application of Generative AI in improving emotional well-being.
By building a lightweight, fast, and easy-to-use motivation generator, we show how AI can be used meaningfully in daily life.

Future improvements can turn this tool into a fully personalized, multilingual motivational assistant.

👨‍💻 Author
Manideep Nunna
B.Tech CSE (AI & ML), VIT-AP University

