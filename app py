import streamlit as st
import pickle

# Load the trained model
# Make sure 'news_model.pkl' is in the same folder
model = pickle.load(open('news_model.pkl', 'rb'))

st.title("Fake News Detector 📰")
st.write("Paste a news article below to check if it is **Real** or **Fake**.")

# Text input for the user
news_text = st.text_area("Enter News Text Here:", height=200)

if st.button("Check News"):
    if news_text:
        # Make a prediction
        prediction = model.predict([news_text])
        
        # 0 = Fake, 1 = True (based on our training labels)
        if prediction[0] == 1:
            st.success("✅ This looks like TRUE News.")
        else:
            st.error("❌ This looks like FAKE News.")
    else:
        st.warning("⚠️ Please enter some text first.")

