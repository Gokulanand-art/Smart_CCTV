# 🛡️ Smart CCTV Person Card System

## 🔍 Quick Highlights
- Converts raw CCTV footage into structured **Person Cards**
- Privacy-first design (no face recognition, no identity inference)
- Modular AI-driven system architecture
- Built entirely using Linux (Termux) on mobile
- Designed for real-world deployment, not just academic use

---

## 📌 Overview
The Smart CCTV Person Card System is a privacy-aware intelligent surveillance framework that transforms raw CCTV video streams into structured, searchable person-level summaries called Person Cards.

Instead of manually reviewing hours of CCTV footage, the system automatically extracts meaningful information such as entry time, exit time, presence duration, dress attributes, and optional face snapshots, while strictly avoiding identity recognition.

This project emphasizes system design, modular architecture, ethical surveillance, and real-world deployability.

---

## 🎯 Problem Statement
Traditional CCTV systems continuously record video but fail to provide actionable insights. Security personnel must manually scan long video footage, which is time-consuming, error-prone, and inefficient in crowded or long-duration environments.

There is a need for a system that summarizes human activity instead of storing raw video.

---

## 💡 Proposed Solution
This project introduces the concept of a Person Card.

A Person Card is a structured data record representing one person’s presence in a surveillance area during a specific time window.

Each Person Card contains:
- System-generated Person ID (no real identity)
- Entry and exit time
- Total presence duration
- Dress color attributes
- Optional face snapshot (only if visible)
- Confidence metrics

This approach converts surveillance from video-centric to data-centric analysis.

---

## 🧠 System Architecture
1. Video Ingestion  
2. Person Detection (YOLOv3-Tiny)  
3. Optional Face Detection (Haar Cascade)  
4. Dress Color Analysis  
5. Entry–Exit Time Logic  
6. Person Card Generation  
7. Database Storage  
8. Review & Access Layer  

Detailed flow is documented in docs/system_flow.md.


---

## 🗂️ Project Structure

```
smart_cctv/
├── ai/
│   ├── person_detection/
│   ├── face_detection/
│   └── dress_analysis/
│
├── core/
│   ├── entry_exit/
│   └── person_card_schema.py
│
├── config/
│   └── camera_config.yaml
│
├── db/
│   └── schema.sql
│
├── docs/
│   ├── system_flow.md
│   └── privacy_policy.md
│
├── ingest/
│
├── logs/
│   └── system.log
│
├── scripts/
│   └── start_system.sh
│
├── storage/
│   └── faces/
│
├── ui/
│
└── README.md
```


---

## 🪪 Person Card Design
Each Person Card represents one person per camera per day and includes:
- Person ID (system-generated)
- Camera ID and date
- Entry time and exit time
- Duration of presence
- Dress color attributes
- Face image reference (if visible)
- Confidence score
- Review status

Schema is defined in core/person_card_schema.py.

---

## 🗄️ Database Design
The system uses SQLite (upgradeable) with normalized tables:
- person_cards
- face_images
- dress_attributes
- system_logs

Schema file: db/schema.sql.

---

## 🔐 Privacy & Ethical Design
- No face recognition
- No identity inference
- No personal identifiers stored
- Minimal data collection
- Configurable data retention

Privacy policy is documented in docs/privacy_policy.md.

---

## 🧰 Tech Stack
- Python
- OpenCV
- YOLOv3-Tiny
- Haar Cascade
- SQLite
- Linux (Termux)

---

## ▶️ Demo Status
This repository focuses on system design and architecture.
A runnable demo and live inference pipeline will be added in future iterations.

---

## 🚀 Implementation Status
✔ Complete system architecture  
✔ AI model integration prepared  
✔ Entry–exit detection logic defined  
✔ Person Card schema finalized  
✔ Database schema completed  
✔ Privacy and compliance documented  

This repository represents a stable v1.0 release.

---

## 🔮 Future Enhancements
- Multi-camera non-biometric re-identification
- Edge AI optimization
- Real-time monitoring dashboard
- Crowd analytics and heatmaps
- Cloud-based scalability

---

## 👤 Author
Gokulanand  
Independent system design & engineering project  
Built entirely using Linux (Termux) on mobile.

---

## 📜 License
MIT License

---

## 🏁 Final Note
This project prioritizes thinking, architecture, and ethics over raw accuracy metrics. It demonstrates how intelligent surveillance systems can be built responsibly, transparently, and deployably.
