# 📱 Campus Companion: Navigation App for Visually Impaired Students

## 🎯 Problem Statement
Navigating a large university campus can be challenging for visually impaired students. Current digital maps lack accessibility-first design and real-time route adjustment based on environment or accessibility obstacles (e.g., blocked paths, stairs, construction).

## 🧠 Goal
Design a product that provides safe, intuitive, and accessible campus navigation for visually impaired users, leveraging voice assistance, GPS, and haptic feedback.

---

## 🗺️ Key Features (MVP)
- Voice-guided turn-by-turn navigation
- Campus map with accessibility metadata (e.g., ramps, elevators)
- Emergency help/panic button
- Haptic feedback for turns or alerts

---

## 👥 Target Users
- Visually impaired students at large public universities

---

## 📝 User Stories

### Student User
- As a student who is blind, I want to receive audio directions so I can get to class independently.
- As a user, I want to avoid stairs and use accessible paths so I can navigate safely.
- As a user, I want to press one button for emergency help if I feel unsafe or lost.

---

## 📃 Product Requirement Document (PRD)

### Overview
- Product: Campus Companion
- Owner: Zaina
- Status: MVP Planning

### Objective
Build an accessible campus navigation prototype for Android/iOS with voice guidance and emergency response.

### Success Metrics
- 90%+ task completion rate in navigation tests
- 4.5/5 average usability score from visually impaired testers

### Timeline
- Week 1: Wireframes + Voice Nav Testing
- Week 2: MVP Build (Streamlit prototype + GPS routing)
- Week 3: Usability Testing

---

## 🔧 Tech Stack (Prototype)
- Streamlit or Flask (Python-based MVP)
- OpenStreetMap + campus overlay
- pyttsx3 or gTTS for voice
- Optional: Raspberry Pi + GPS module for IoT demo

---

## 💻 MVP Python Code (Streamlit Prototype)
```python
import streamlit as st
import pyttsx3

# Initialize Text-to-Speech Engine
engine = pyttsx3.init()

def speak(text):
    engine.say(text)
    engine.runAndWait()

# UI
st.title("Campus Companion Navigation")
st.subheader("Voice-Guided Campus Navigation for Visually Impaired Users")

# Input Destination
destination = st.selectbox("Choose your destination:", [
    "Library",
    "Cafeteria",
    "Main Lecture Hall",
    "Student Union",
    "Dorms"
])

# Simulated Directions
directions = {
    "Library": ["Turn right from main gate", "Walk straight for 200 meters", "Library will be on your left"],
    "Cafeteria": ["Turn left from main gate", "Continue for 150 meters", "Cafeteria will be on your right"],
    "Main Lecture Hall": ["Go straight from main gate", "Climb the ramp", "Lecture Hall is ahead"],
    "Student Union": ["Turn right", "Pass the Library", "Union is the next building"],
    "Dorms": ["Turn left", "Pass the Cafeteria", "Dorms are on the left past the parking lot"]
}

# Trigger Navigation
if st.button("Start Navigation"):
    st.success(f"Starting guidance to {destination}")
    for step in directions[destination]:
        st.write(step)
        speak(step)
```

---

## 🎨 Mockups / Wireframes
TBD — You can add images or Figma links in a `/mockups/` folder or GitHub Pages site.

---

## 🧪 Next Steps
- [x] Build voice navigation demo
- [ ] Design emergency alert button
- [ ] Gather feedback from accessibility testers

---

## 📂 Deployment on GitHub

1. Create a new GitHub repository named `campus-companion`.
2. Add the following file structure:
   ```
   campus-companion/
   ├── app.py               # The Streamlit app code
   ├── requirements.txt     # Dependencies
   ├── README.md            # Project documentation
   └── mockups/             # Optional UI mockups
   ```

3. **requirements.txt**:
   ```
   streamlit
   pyttsx3
   ```

4. **README.md** content:
   ```markdown
   # 📱 Campus Companion

   A voice-guided campus navigation tool designed for visually impaired students.

   ## 🚀 Features
   - Real-time voice directions
   - Accessible path mapping
   - Emergency alert feature (Coming Soon)

   ## 📦 Tech Stack
   - Streamlit, pyttsx3

   ## 🛠️ Run Locally
   ```bash
   git clone https://github.com/yourusername/campus-companion.git
   cd campus-companion
   pip install -r requirements.txt
   streamlit run app.py
   ```

   ## 🤝 Contributing
   PRs and accessibility feedback welcome!
   ```

5. Push your code to GitHub using:
   ```bash
   git init
   git remote add origin https://github.com/yourusername/campus-companion.git
   git add .
   git commit -m "Initial commit"
   git push -u origin master
   ```

---

## 💡 Want to contribute?
Open an issue or submit a pull request! Feedback on accessibility, UI/UX, or routing logic is welcome.

> "Accessibility isn’t a feature. It’s a foundation."
