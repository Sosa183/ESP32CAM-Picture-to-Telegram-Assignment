# ESP32-CAM Telegram Photo Bot  
Using Arduino IDE & Telegram Bot API  
Based on Random Nerd Tutorials – “Telegram: ESP32-CAM Take and Send Photo”

---

## 📌 Project Overview

This project uses an **ESP32-CAM AI Thinker** module to take photos and send them directly to a smartphone using **Telegram**.  

After setting up a Telegram bot and flashing the ESP32-CAM with Arduino IDE, you can remotely control the device using simple Telegram commands:

- `/start` — Display available commands  
- `/photo` — Capture and send a real-time photo  
- `/flash` — Toggle the ESP32-CAM built-in LED flash  

This allows remote monitoring from anywhere with internet access.





Albert:  NOTES FOR CSN150

# Purpose
The purpose of this project was to set up an ESP32-CAM that connects to a Telegram bot, receives remote commands, and sends photos through the Telegram API. This assignment demonstrates IoT communication, Arduino programming, API usage, and documenting the setup process in a GitHub repository.

---

## Equipment Used
- ESP32-CAM AI Thinker board  
- OV2640 camera module  
- FTDI USB-to-Serial adapter  
- Jumper wires  
- USB cable  
- Windows PC with Arduino IDE  
- 2.4 GHz Wi-Fi network  
- Smartphone with Telegram installed  

---

## Tools Used (Arduino, GPT-x, etc.)
- Arduino IDE 2.x  
- ESP32 Board Package  
- UniversalTelegramBot library  
- ArduinoJson library  
- Telegram App  
  - BotFather (created bot + token)  
  - IDBot (@myidbot) for CHAT_ID  
- Telegram Bot API (`getUpdates`)  
- GitHub (repository + documentation)  
- ChatGPT (GPT-x) for debugging and documentation help  

---

## Steps I Followed
1. Created a Telegram bot using **BotFather** and saved the bot token.  
2. Used **@myidbot** to obtain my Telegram **CHAT_ID**.  
3. Verified bot messages using the API URL:  
   `https://api.telegram.org/bot<YOUR_TOKEN>/getUpdates`  
4. Installed the ESP32 board package in Arduino IDE.  
5. Installed the **UniversalTelegramBot** and **ArduinoJson** libraries.  
6. Configured the sketch with my Wi-Fi credentials, bot token, and chat ID.  
7. Added the Telegram HTTPS root certificate and used `clientTCP.setCACert()`.  
8. Fixed missing braces in the `loop()` function that caused compile errors.  
9. Connected ESP32-CAM to FTDI, enabled programming mode, and uploaded code.  
10. Tested commands in Telegram: `/start`, `/flash`, and `/photo`.  

---

## Problems / Solutions

### **Bot not responding**
**Cause:** Messaging BotFather instead of my bot, or the bot wasn’t activated.  
**Solution:** Opened the correct bot link from BotFather → pressed **Start** → resent commands.

### **`getUpdates` returned empty results**
**Cause:** Bot chat had no messages yet.  
**Solution:** Sent “hi” and `/start` to the bot, refreshed the API URL.

### **Compilation error: `expected '}' at end of input`**
**Cause:** Missing closing bracket in `loop()`.  
**Solution:** Restored full, proper loop structure from the tutorial.

---

## Final Report
This project successfully connected the ESP32-CAM to a Telegram bot, allowing remote image capture and LED flash control. I learned how to integrate IoT hardware with messaging APIs, troubleshoot Arduino code, work with HTTPS on microcontrollers, and document a full workflow using GitHub. The ESP32-CAM now responds to `/start`, `/photo`, and `/flash`, demonstrating reliable remote communication suitable for IoT-based monitoring systems.

---
