🔐 Bluetooth-Based Spam & Threat Detection System
A real-time Python-based Bluetooth message scanner that detects spam, phishing, and suspicious content using sender trust validation, domain filtering, keyword analysis, and MAC address tracking. Includes a built-in visualizer for detected threats.

📌 Features
Bluetooth Message Listening via Serial Port (pyserial)

MAC Address Filtering using bleak

Flexible Message Parsing (JSON or plain text)

Threat Detection based on:

Untrusted Senders

Suspicious Domains

Phishing/Spam Keywords

Interactive Message Handling

Block suspicious senders/domains

View blocked message logs

Threat Visualization with bar charts (matplotlib)

Priority Message Handling for bank/OTP/payment-related texts

📁 Code Structure
Module	Description
scan_ble_devices()	Scans BLE devices and retrieves MAC address
extract_fields()	Parses incoming message into sender, subject, content
detect()	Applies detection logic for sender/domain/keywords
main()	Manages serial input, detection, and interaction loop
visualization()	Summarizes detected threats in a bar chart

🧪 Threat Detection Logic
Untrusted Sender: Not in the approved list

Suspicious Domain: Matches known spam domains

Phishing Keywords: Looks for trigger words like click, win, urgent, reset

Important Terms Whitelist: Allows OTP/payment texts even without proper headers

📈 Visualization Example
Generates a bar chart showing counts of:

Untrusted Sender

Suspicious Domain

Keyword Detected

🔧 Requirements
Install dependencies before running:

bash
Copy
Edit
pip install pyserial bleak matplotlib numpy
▶️ How to Run
Connect Bluetooth sender to COM4 (or update PORT)

Ensure messages follow one of:

JSON format: {"sender": "...", "subject": "...", "content": "..."}

Plain text: sender, subject, content

Run:

bash
Copy
Edit
python main.py
Use ok to view message, view blocked to list blocked ones

🚀 Future Scope
💡 Develop a custom smartwatch to test and deploy the script directly on wearable hardware

🌐 Integrate client-server model with internet support for remote monitoring

🔒 Enhance security via encryption or authentication

🧪 Comprehensive testing with diverse real-world message datasets

🌐 Design a web-based interface for user-friendly message review

📦 Repository Info
Branch: main

Key Functionalities:

Bluetooth scanning and MAC filtering

Real-time message parsing and detection

Dynamic blocking & logging

Spam threat visualization
