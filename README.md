#  Apollo Avatar Assistant: Real-Time Patient Announcer

An AI-powered virtual assistant that deliverslive admission & discharge updates** from hospital systems using a friendly animated avatar.

---

## 🎯 What It Does

- Fetches real-time patient events (admitted/discharge) from hospital DB  
- Announces via **voice + on-screen text** using a talking avatar girl  
- Auto-refreshes every 15 seconds — no manual checks needed  
- Built for internal use at Apollo Hospitals (demo uses **simulated data only**)

---

## 🖼️ Screenshots

### 1. Avatar Delivering Admit/Discharge Update  
![Avatar Announce](https://github.com/Kumarrajasekharreddy/Hospital-Avatar-Real-Time-Patient-Announcer/blob/main/Avatar%20Announce.jpg?raw=true)  
*Friendly avatar speaks:*  
> **“Patient TEST PATIENT A has been discharged. UHID: TEST.A123456. Doctor: DR. AVATAR.”**  
*(All data is synthetic — for demo only)*



### 2. Voice + Text Sync   
(https://github.com/Kumarrajasekharreddy/Avatar-Assistant/blob/main/screenshots/voice-sync.png?raw=true)](https://github.com/Kumarrajasekharreddy/Avatar-Assistant/blob/main/screenshots/voice-sync.png)  
*Converts UHID to speakable format (e.g., A.I.M.S.000123 → “A dot I dot M dot S dot zero zero zero one two three”)
Ensures clear, natural voice output for staff.
*

## 🛠️ Software & Tools Used

| Category          | Tools & Technologies |
|-----------------  |----------------------|
| **Core**          | Python, Pandas       |
| **Avatar Engine** |HeyGen + NVIDIA Omniverse (AI-generated talking avatar) |
| **Voice**         | Browser TTS (real-time synthesis) |
| **DB**            | PostgreSQL (`psycopg2`) |
| **Data Source**   | Simulated hospital DB (Apollo schema) |

---

## 💻 Core Logic 

From `update_avatar()`:
```python
uhid_spoken = ' '.join(list(uhid.upper().replace('.', ' dot ')))
voice_text = f"Patient {status}, {name}, U H I D {uhid_spoken}, under Doctor {doctor}."
