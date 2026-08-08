# 🏋️ AI Real-Time GYM Coach

<p align="center">
  <strong>Real-Time Exercise Analysis • Intelligent Form Correction • AI Voice Coaching</strong>
</p>

<p align="center">
  An AI-powered virtual fitness coach that uses Computer Vision, Pose Estimation, and Generative AI to analyze workouts in real time and provide personalized coaching feedback.
</p>

<p align="center">

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Pose%20Estimation-0097A7?style=for-the-badge&logo=google)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Groq](https://img.shields.io/badge/Groq-LLM-F55036?style=for-the-badge)
![WebRTC](https://img.shields.io/badge/WebRTC-Real--Time%20Video-333333?style=for-the-badge&logo=webrtc&logoColor=white)

</p>

---

## 🚀 Overview

**AI Real-Time GYM Coach** is a computer-vision-powered virtual fitness assistant designed to provide **real-time exercise analysis and intelligent coaching** through a standard webcam.

Unlike conventional workout applications that simply count repetitions, this system analyzes **body posture, joint angles, movement patterns, exercise phases, and workout state** to understand how an exercise is being performed.

The application combines:

> **Pose Estimation + Computer Vision + Exercise-Specific Analytics + Generative AI + Voice Interaction**

to create an interactive digital fitness coach capable of monitoring workouts and delivering contextual feedback while the user exercises.

---

## 🎯 Problem

Most fitness applications tell users **what exercise to perform**, but provide limited feedback on **how the exercise is being performed**.

Incorrect form can reduce exercise effectiveness and potentially increase the risk of injury.

AI Real-Time GYM Coach addresses this gap by transforming a normal webcam into an intelligent workout-monitoring system capable of:

- Detecting human body landmarks
- Understanding exercise movements
- Counting repetitions and sets
- Evaluating exercise form
- Detecting form deviations
- Providing contextual coaching
- Delivering real-time voice feedback

---

# ✨ Core Features

<table>
<tr>
<td width="50%">

### 🎥 Real-Time Pose Analysis

- Live camera-based workout monitoring
- Human pose landmark detection
- Real-time skeleton visualization
- Continuous movement tracking
- Automatic pose-loss detection

</td>

<td width="50%">

### 🏋️ Exercise Intelligence

- Exercise-specific movement analysis
- Automatic repetition counting
- Set tracking
- Exercise phase detection
- Form evaluation

</td>
</tr>

<tr>
<td>

### 🤖 AI Coaching

- Context-aware coaching
- Form correction feedback
- Set completion feedback
- Workout encouragement
- Pose-loss guidance

</td>

<td>

### 🔊 Voice Interaction

- AI-generated coaching messages
- Text-to-speech feedback
- Hands-free workout experience
- Proactive coaching during exercise

</td>
</tr>

<tr>
<td>

### 📊 Workout Tracking

- Live repetition counter
- Current set progress
- Completed set tracking
- Exercise-specific metrics
- Workout history

</td>

<td>

### 🎯 Personalized Workouts

- Select exercise
- Configure sets
- Configure repetitions
- Start/stop workout sessions
- Track individual workout progress

</td>
</tr>
</table>

---

# 🏋️ Supported Exercises

| Exercise | Rep Tracking | Form Analysis | Key Metrics |
|---|:---:|:---:|---|
| 🦵 **Squats** | ✅ | ✅ | Knee Angle, Back Angle, Squat Depth |
| 💪 **Push-ups** | ✅ | ✅ | Elbow Angle, Body Alignment, Hip Position |
| 💪 **Biceps Curls** | ✅ | ✅ | Elbow Angle, Shoulder Stability, Swing Detection |
| 🏋️ **Shoulder Press** | ✅ | ✅ | Elbow Angle, Arm Extension, Back Arch |
| 🦵 **Lunges** | ✅ | ✅ | Front Knee Angle, Torso Angle, Balance |

---

# 🧠 How It Works

The system transforms raw webcam frames into meaningful workout intelligence through a multi-stage computer vision pipeline.

```text
                    ┌───────────────────┐
                    │    Webcam Feed    │
                    └─────────┬─────────┘
                              │
                              ▼
                    ┌───────────────────┐
                    │   WebRTC Stream   │
                    └─────────┬─────────┘
                              │
                              ▼
                    ┌───────────────────┐
                    │   OpenCV Frame    │
                    │    Processing     │
                    └─────────┬─────────┘
                              │
                              ▼
                    ┌───────────────────┐
                    │ MediaPipe Pose    │
                    │    Landmarker     │
                    └─────────┬─────────┘
                              │
                              ▼
                 ┌──────────────────────────┐
                 │ Pose Landmark Extraction │
                 └────────────┬─────────────┘
                              │
                              ▼
              ┌───────────────────────────────┐
              │ Exercise-Specific Detector   │
              │                               │
              │ Squat │ Push-up │ Curl │      │
              │ Press │ Lunge                 │
              └───────────────┬───────────────┘
                              │
                ┌─────────────┴─────────────┐
                ▼                           ▼
       ┌─────────────────┐        ┌─────────────────┐
       │ Form Analysis   │        │ Rep / Set       │
       │ & Joint Angles  │        │ Tracking        │
       └────────┬────────┘        └────────┬────────┘
                │                          │
                └────────────┬─────────────┘
                             ▼
                   ┌─────────────────────┐
                   │ Workout State       │
                   │ & Event Detection   │
                   └──────────┬──────────┘
                              │
                              ▼
                   ┌─────────────────────┐
                   │   Groq AI Coach     │
                   │ Contextual Feedback │
                   └──────────┬──────────┘
                              │
                              ▼
                   ┌─────────────────────┐
                   │ Text-to-Speech      │
                   └──────────┬──────────┘
                              │
                              ▼
                         🔊 Coaching
```

---

# 🔬 Computer Vision Pipeline

The vision pipeline is designed around **landmark-based biomechanical analysis** rather than simple image classification.

### 1. Frame Acquisition

The webcam continuously provides video frames through a WebRTC stream.

### 2. Pose Estimation

MediaPipe detects the user's body landmarks from each frame.

### 3. Landmark Analysis

Relevant body joints are extracted and used to calculate exercise-specific measurements.

### 4. Exercise Detection

Each supported exercise has a dedicated detector responsible for interpreting its movement pattern.

### 5. Form Evaluation

Joint angles, alignment, movement states, and exercise-specific conditions are analyzed.

### 6. Repetition & Set Tracking

The detector maintains the exercise state and determines when a valid repetition or set has been completed.

### 7. Coaching

Detected workout events are passed to the AI coaching layer to generate contextual feedback.

---

# 📐 Exercise Form Analysis

The system uses **joint-angle and positional relationships** to understand movement.

For example, squat analysis can consider:

```text
Hip ───── Knee
          │
          │
        Ankle
```

and evaluate parameters such as:

- Knee angle
- Back angle
- Squat depth
- Movement phase

Similar biomechanical metrics are used for other exercises to create exercise-specific form analysis.

This approach allows the system to move beyond simple **"rep counting"** toward actual **movement understanding**.

---

# 🤖 Generative AI Coaching

The coaching layer adds an intelligent feedback system on top of the deterministic computer-vision pipeline.

```text
Exercise Detector
       │
       ▼
Workout Event
       │
       ├── Rep Completed
       ├── Set Completed
       ├── Form Issue
       ├── Workout Started
       ├── Workout Completed
       └── Pose Not Detected
       │
       ▼
   AI Coach
       │
       ▼
Contextual Feedback
       │
       ▼
 Text-to-Speech
       │
       ▼
 🔊 User
```

The AI coach is designed to provide **short, actionable, and context-aware feedback** rather than generic fitness responses.

---

# 🏗️ System Architecture

```text
┌───────────────────────────────────────────────────────┐
│                    Streamlit UI                       │
│                                                       │
│  Workout Selection • Live Metrics • Workout History  │
└───────────────────────────┬───────────────────────────┘
                            │
                            ▼
┌───────────────────────────────────────────────────────┐
│                 Real-Time Video Layer                 │
│                     WebRTC + OpenCV                   │
└───────────────────────────┬───────────────────────────┘
                            │
                            ▼
┌───────────────────────────────────────────────────────┐
│                   Pose Estimation                      │
│                  MediaPipe Landmarker                 │
└───────────────────────────┬───────────────────────────┘
                            │
                            ▼
┌───────────────────────────────────────────────────────┐
│              Exercise Detection Layer                 │
│                                                       │
│  Squat • Push-up • Biceps Curl • Shoulder Press      │
│  • Lunges                                             │
└───────────────────────────┬───────────────────────────┘
                            │
                            ▼
┌───────────────────────────────────────────────────────┐
│              Workout Intelligence                     │
│                                                       │
│  Form Analysis • Rep Counting • Set Tracking          │
│  Exercise State • Workout Events                      │
└───────────────────────────┬───────────────────────────┘
                            │
                            ▼
┌───────────────────────────────────────────────────────┐
│                  AI Coaching Layer                    │
│                       Groq LLM                        │
└───────────────────────────┬───────────────────────────┘
                            │
                            ▼
┌───────────────────────────────────────────────────────┐
│                Voice Feedback Layer                   │
│                    Text-to-Speech                     │
└───────────────────────────────────────────────────────┘
```

---

# 🛠️ Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| **Application** | Python | Core application logic |
| **UI** | Streamlit | Interactive web interface |
| **Pose Estimation** | MediaPipe | Human pose landmark detection |
| **Computer Vision** | OpenCV | Frame processing & visualization |
| **Real-Time Video** | WebRTC | Live camera streaming |
| **AI / LLM** | Groq | Contextual coaching generation |
| **Numerical Processing** | NumPy | Mathematical & landmark calculations |
| **Video Processing** | PyAV | Video frame handling |
| **Voice** | TTS Pipeline | Spoken coaching feedback |
| **Persistence** | Local Repository | Workout history & state |

---

# 📂 Project Architecture

```text
AI-Gym-Coach/
│
├── LandingPage/
│
├── Main App/
│   │
│   ├── main.py
│   │
│   ├── detectors/
│   │   ├── squat.py
│   │   ├── pushup.py
│   │   ├── biceps_curl.py
│   │   ├── shoulder_press.py
│   │   └── lunges.py
│   │
│   ├── services/
│   │   ├── auth/
│   │   ├── coaching/
│   │   ├── config/
│   │   ├── persistence/
│   │   ├── state/
│   │   ├── tracking/
│   │   ├── ui/
│   │   └── vision/
│   │
│   ├── ml_models/
│   │   └── pose_landmarker_full.task
│   │
│   └── static/
│       └── style.css
│
├── .gitignore
├── packages.txt
├── requirements.txt
└── README.md
```

The architecture follows a modular design where **exercise detection, vision processing, coaching, state management, persistence, and UI** are separated into dedicated components.

---

# 📊 Real-Time Workout Dashboard

During an active session, users can monitor:

```text
┌─────────────────────────────┐
│       CURRENT WORKOUT       │
├─────────────────────────────┤
│ Exercise:       Squat       │
│                             │
│ Repetitions:       08       │
│ Current Set:       02       │
│ Sets Completed:    01       │
│                             │
│ Knee Angle:       91°       │
│ Back Angle:       12°       │
│ Depth:          GOOD ✓      │
└─────────────────────────────┘
```

The interface is designed to keep important workout information visible without interrupting the exercise experience.

---

# 🔄 User Workflow

### Step 01 — Configure Workout

Select the desired exercise and specify the target number of sets and repetitions.

### Step 02 — Start Workout

Activate the camera and begin real-time pose detection.

### Step 03 — Perform Exercise

The system continuously analyzes body landmarks and movement.

### Step 04 — Receive Feedback

The AI coach provides contextual feedback based on workout events and detected conditions.

### Step 05 — Track Progress

Repetitions, sets, and exercise-specific metrics are updated in real time.

### Step 06 — Review History

Completed workout sessions can be reviewed through the workout history interface.

---

# 💡 Engineering Highlights

This project demonstrates practical implementation of several real-world AI engineering concepts:

- **Real-time computer vision**
- **Human pose estimation**
- **Landmark-based biomechanics**
- **State-machine-based repetition tracking**
- **Exercise-specific algorithm design**
- **Real-time video streaming**
- **Generative AI integration**
- **Text-to-speech interaction**
- **Modular software architecture**
- **Session and workout state management**

---

# 🔮 Future Roadmap

### 🧠 AI & Computer Vision

- [ ] Advanced form scoring
- [ ] Personalized form thresholds
- [ ] More exercise detectors
- [ ] Improved pose robustness
- [ ] Exercise recognition from arbitrary movements

### 📊 Fitness Intelligence

- [ ] Long-term progress analytics
- [ ] Personalized workout recommendations
- [ ] Performance trend visualization
- [ ] Adaptive workout difficulty
- [ ] Fitness performance scoring

### 🛡️ Safety

- [ ] Injury-risk estimation
- [ ] Liveness detection
- [ ] Incorrect posture warnings
- [ ] Fatigue detection

### 🌐 Product Expansion

- [ ] Mobile application
- [ ] User accounts and cloud synchronization
- [ ] Multi-user profiles
- [ ] Wearable integration
- [ ] Heart-rate monitoring
- [ ] Cloud-based workout history

---

# 🌟 Project Vision

> **From counting repetitions to understanding movement.**

AI Real-Time GYM Coach aims to make intelligent fitness guidance accessible without requiring expensive personal training.

By combining **computer vision with generative AI**, the project explores how everyday cameras can become intelligent interfaces for understanding human movement and delivering personalized assistance.

---

## 📄 License

This project is developed for **educational, research, and learning purposes**.