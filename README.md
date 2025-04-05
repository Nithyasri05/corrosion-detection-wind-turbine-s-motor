# corrosion-detection-wind-turbine-s-motor
Thermal image-based corrosion detection using YOLOv5

# 🛠️ Corrosion Detection in Wind Turbine's Motor

This project uses **YOLOv5** for real-time corrosion detection in wind turbine motors through thermal images. On detecting high corrosion, the system triggers a **Twilio SMS alert** to notify the user.

---

## 📁 Download Project Files

Due to file size limitations, the full project is hosted on Google Drive.

🔗 [Download Corrosion Detection Project](https://drive.google.com/file/d/1dRSazutQMpAZNlan2v3Gv8AoCl-tZdiW/view?usp=sharing
)

---

## 🚀 Features

- YOLOv5 for object detection
- Real-time video stream (from webcam or video)
- Thermal image dataset (preprocessed)
- SMS alerts via Twilio API
- Conf-threshold configuration
- Easy-to-modify detection pipeline

---

## 🧪 Dataset Details

- ~2187 thermal images
- Resolution: 224x224
- Augmentation applied via Roboflow
- Corrosion classification: High, Medium, Low

---

🧰 Installation
1. Clone or Download

git clone https://github.com/Nithyasri05/corrosion-detection-wind-turbine-s-motor.git
cd corrosion-detection

Or extract the ZIP you downloaded from the Google Drive link.

2. Install Required Packages

pip install -r requirements.txt

3. Run the Project

python detect.py --weights best.pt --source 0 --conf-thres 0.4 --view-img

--------------------------------------------------------------------------------------------------------------------
📲 Twilio Setup for SMS Notification
Step 1: Create Twilio Account
Visit Twilio Signup

Verify email & phone

Get your Account SID, Auth Token, and Trial Number

Step 2: Install Twilio Library

pip install twilio

Step 3: Insert Your Twilio Credentials in detect.py
Find the following lines in detect.py:

from twilio.rest import Client

account_sid = 'YOUR_ACCOUNT_SID'
auth_token = 'YOUR_AUTH_TOKEN'
client = Client(account_sid, auth_token)

message = client.messages.create(
    from_='+1TWILIO_NUMBER',
    body='High corrosion detected!',
    to='+91YOUR_PHONE_NUMBER'
)

-----
