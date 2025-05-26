🔐 Bluetooth-Based Real-Time Spam & Threat Detection System
This project is a Python-based application that listens to messages received over Bluetooth, detects spam, phishing, and suspicious content using trusted sender/domain lists and keyword matching, and visualizes threats in real time.

📌 Features
- 🔗 Real-time Bluetooth message monitoring via COM port (`pyserial`)
- 📡 Bluetooth Low Energy (BLE) device scanning using `bleak`
- 🧠 Smart threat detection using:
- Untrusted senders
- Suspicious domains
- Malicious/phishing keywords
- 🧾 Supports JSON and plain text message formats
- 📊 Threat visualization using bar charts (`matplotlib`)
- ⛔ Dynamic sender and domain blocking
- 🧠 Priority keyword recognition for critical messages (e.g., OTP, bank)
- 👤 Interactive CLI interface for message review and sender blocking


💻 How to Run
1. Clone the Repository
git clone <your-repository-link>
cd <repo-folder>

2. ⬇️Install Required Libraries
Make sure Python-3 is installed. Then install dependencies:
       pip install pyserial bleak matplotlib numpy

3. Set Bluetooth Port
In main.py, set the serial port name as per your system:
			PORT = "COM4"  # Windows example
			# or
			PORT = "/dev/ttyUSB0"  # Linux example

4. Connect Bluetooth Device
			Ensure your Bluetooth device (e.g., phone, sensor) is paired and sending data to the correct serial port.

5. Run the Application
				python main.py


📨 Message Format
The system supports two main formats:
✅ JSON Format (Recommended)
		{
		  "sender": "example@phish.com",
		  "subject": "Reset Your Account",
		  "content": "Click here to reset your password"
		}

✅ Plain Text Format (Comma-Separated)
		example@phish.com, Reset Your Account, Click here to reset your password

* If none of the above formats match, the system treats it as a basic SMS.


🚨 Threat Detection Logic
Messages are flagged as spam or phishing if:
			✉️ Sender is not in the trusted list
			🌐 Domain is suspicious or unknown
			🧠 Message contains malicious or suspicious keywords
			🔐 Message is marked important if it contains high-priority words like "OTP", "bank", "account"


🛠️ Components and Functionality
🔄 Serial Bluetooth Reading
		Continuously listens to the Bluetooth COM port and reads incoming messages in real-time.
📶 BLE Device Scanning
		Uses the bleak library to detect nearby BLE devices and display their MAC addresses.


🧠 Message Parsing
			Parses incoming JSON or CSV messages and extracts key information: sender, subject, content.


🛡️ Threat Detection
Compares message details with:
		✅ Trusted sender list (trusted_senders)
		🔒 Trusted domain list (trusted_domains)
		⚠️ Suspicious keyword list (spam_keywords)


⛔ Blocking Mechanism
After showing a suspicious message, user is prompted to:
	Block the sender
	Block the domain


📊 Visualization
At the end of the session, a bar chart is displayed showing the number of:
		Untrusted sender messages
		Suspicious domain messages
		Keyword-detected threats

 
 🧭 How to Use the CLI
While Running
You can type the following commands:
		ok – Review the latest message details
		view blocked – Display all messages blocked
		Ctrl + C – Exit the program
On Suspicious Message
		You'll be prompted:

Do you want to block the sender/domain? (Yes/No)


📊 Threat Categories Visualization
The following categories are plotted in a bar chart:
		Untrusted Senders
		Suspicious Domains
		Spam/Phishing Keywords
Example Chart:
(A matplotlib chart appears when the script exits)


📂 File Structure
bash
Copy
Edit
bluetooth-threat-detection/
│
├── main.py                # Main program
├── requirements.txt       # (Optional) dependencies
└── README.md              # Documentation

🧾 Future Enhancements
		🧭 Integrate with a smartwatch for real-world testing
		🌍 Add online database support (e.g., Firebase or SQLite)
		📲 Android app version for mobile notifications
		🕵️‍♂️ Advanced ML-based message classification
		🛜 Web dashboard for logs and reports
