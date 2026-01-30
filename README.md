# 🛡️ Smart CCTV Person Card System

## 📌 Overview
The **Smart CCTV Person Card System** is a privacy-aware intelligent surveillance framework that transforms raw CCTV video streams into **structured, searchable person-level summaries** called **Person Cards**.

Instead of manually reviewing hours of CCTV footage, the system automatically extracts meaningful information such as **entry time, exit time, presence duration, dress attributes, and optional face snapshots**, while strictly avoiding identity recognition.

This project emphasizes **system design, modular architecture, ethical surveillance, and real-world deployability**.

---

## 🎯 Problem Statement
Traditional CCTV systems continuously record video but fail to provide actionable insights.  
Security personnel must manually scan long video footage, which is:

- Time-consuming  
- Error-prone  
- Inefficient in crowded or long-duration environments  

There is a need for a system that **summarizes human activity instead of storing raw video**.

---

## 💡 Proposed Solution
This project introduces the concept of a **Person Card**.

A **Person Card** is a structured data record representing one person’s presence in a surveillance area during a specific time window.

Each Person Card contains:
- System-generated Person ID (no real identity)
- Entry and exit time
- Total presence duration
- Dress color attributes
- Optional face snapshot (only if visible)
- Confidence metrics

This approach converts surveillance from **video-centric** to **data-centric** analysis.

---

## 🧠 System Architecture
The system follows a **modular, layered architecture**:

1. Video Ingestion  
2. Person Detection (YOLOv3-Tiny)  
3. Optional Face Detection (Haar Cascade)  
4. Dress Color Analysis  
5. Entry–Exit Time Logic  
6. Person Card Generation  
7. Database Storage  
8. Review & Access Layer  

Detailed system flow is documented in:
---

## 🗂️ Project Structure

smart_cctv/
├── ai/                 # AI perception modules
│   ├── person_detection/
│   ├── face_detection/
│   └── dress_analysis/
├── core/               # Core logic & intelligence
│   ├── entry_exit/
│   └── person_card_schema.py
├── config/             # Configuration files
├── db/                 # Database schema
├── docs/               # System documentation
├── ingest/             # Video ingestion layer
├── logs/               # System logs
├── scripts/            # Startup / utility scripts
├── storage/            # Evidence storage (faces)
├── ui/                 # Future user interface
└── README.md---

## 🪪 Person Card Design
Each Person Card represents **one person per camera per day** and includes:

- Person ID (system-generated)
- Camera ID and date
- Entry time and exit time
- Duration of presence
- Dress color attributes (upper & lower)
- Face image reference (if visible)
- Confidence score
- Review status

The schema definition is available in:core/person_card_schema.py---


## 🗄️ Database Design
The system uses **SQLite** (upgradeable to other databases) with a normalized schema:

- person_cards  
- face_images  
- dress_attributes  
- system_logs  

Database schema file:db/schema.sql
---

## 🔐 Privacy & Ethical Design
This project follows **privacy-by-design principles**:

- ❌ No face recognition  
- ❌ No identity inference  
- ❌ No personal identifiers stored  
- ✅ Minimal data collection  
- ✅ Configurable data retention  

Detailed policy:docs/privacy_policy.md---

## 🚀 Implementation Status
✔ Complete system architecture  
✔ AI model integration prepared  
✔ Entry–exit detection logic defined  
✔ Person Card schema finalized  
✔ Database schema completed  
✔ Privacy and compliance documented  

This repository represents a **stable v1.0 release**, suitable for academic review, portfolio use, and future real-world deployment.

---

## 🔮 Future Enhancements
- Multi-camera non-biometric re-identification  
- Edge AI optimization  
- Real-time monitoring dashboard  
- Crowd analytics and heatmaps  
- Cloud-based scalability  

---

## 👤 Author
**Gokulanand**  
Independent system design & engineering project  

Built entirely using **Linux (Termux) on mobile**, demonstrating real-world constraints, discipline, and ethical system design.

---

## 📜 License
This project is licensed under the **MIT License**.  
See the `LICENSE` file for details.

---

## 🏁 Final Note
This project prioritizes **thinking, architecture, and ethics over raw accuracy metrics**.  
It demonstrates how intelligent surveillance systems can be built responsibly, transparently, and deployably.
