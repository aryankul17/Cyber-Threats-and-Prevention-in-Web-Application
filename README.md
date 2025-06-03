# Cyber Threats and Prevention in Web Applications

This project demonstrates common cyberattacks on web applications, including **Phishing** and **Keylogging**, with additional reference to **SQL Injection** and **XSS** techniques. It was developed and tested using tools like **XAMPP**, **Kali Linux**, **SET Toolkit**, and **Ngrok** as part of the CSE3502 course.

---

## Files in This Project

| File | Description |
|------|-------------|
| `final_keylogger.py` | Keylogger that captures keystrokes, screenshots, webcam & microphone data, and system info |
| `decrypt.py` | Decrypts encrypted files sent from the keylogger |
| `chrome_passwords.py` | Extracts saved login credentials from Chrome (local access only) |
| `J_COMP_REPORT_19BEC1038_19BLC1172.pdf` | Official university project report |
| `isa_report.pdf` | Advanced reference work with ideas for future expansion |

> Note: Scripts for `sqlinjection.py` and `xss.py` described in the report are **not included** in this repo but are discussed in the documentation.

---

## Project Highlights

- Facebook phishing page clone using **Ngrok + SET Toolkit**
- Keylogger that:
  - Captures **keystrokes**
  - Takes **screenshots** every 5 seconds
  - Records **audio** and **webcam snapshots**
  - Extracts **Wi-Fi credentials** and **system info**
- Encrypts all logs and sends them to an attacker email
- Supports decryption of received logs using `decrypt.py`

---

## How to Run the Keylogger (Safely)

> Use in isolated virtual environments only. This file may be flagged as malicious.

### 1. Setup
- Ensure **Python 3.x** is installed
- Install required packages:
  ```bash
  pip install pynput sounddevice opencv-python requests


### 2. Configure

* Edit `final_keylogger.py` and update:

  * Sender & receiver email
  * App password (Gmail recommended)

### 3. Run Keylogger

```bash
python final_keylogger.py
```

* Logs saved in: `C:/Users/<user>/LOGS`
* Automatically encrypted and emailed every 5 minutes
* Logs deleted from disk after upload

---

### Decrypt Received Logs

Use the decryption script:

```bash
python decrypt.py
```

* Decryption key used in testing (example from report):

  ```
  T2UnFbwxfVlnJ1PWbixcDSxJtpGToMKotsjR4wsSJpM=
  ```

---

## Phishing Workflow 
#### 1. Run Ngrok:

   ```bash
   ./ngrok http 80
   ```
#### 2. Launch SET Toolkit (Social Engineering Toolkit)
#### 3. Use Credential Harvester Attack
#### 4. Send the generated phishing link to a target
#### 5. Credentials are harvested and stored on your local machine

---

## Future Possible Enhancements 

These were demonstrated in peer extensions and can be added to this project:

* **Persistence Mechanism**: Add the keylogger to system startup
* **EXE Conversion & Obfuscation**: Convert `.py` to `.exe` disguised as a media file
* **Malicious URL Detection (ML)**: Use ML models (e.g., Random Forest, Logistic Regression) to detect phishing links
* **Browser Session Hijacking**: Access browser cookies and sessions
* **Port Listener Module**: Record open ports and attempt sniffing

---

## Disclaimer

> This project is for **educational purposes only**.
> Do **not use or distribute** the keylogger or phishing tools in real-world systems. Unauthorized access, surveillance, or data theft is **illegal** and may be punishable under the Information Technology Act and cybercrime laws.

---

