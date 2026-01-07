## Hardware research for real time gait learnin
This report evaluates the **Hiwonder MechDog**, **NavBot-EG01**, **Petoi Bittle**, and the **RealAnt** for our specific use case: online Reinforcement Learning (RL) with a tethered power supply and offloaded computation (Serial/WiFi).

Date: 7 Jan 2026

Stay tuned for updates.

---

### 1. Hiwonder MechDog (Robust Research Entry)

The MechDog is a "Pro-sumer" educational robot. Its metal mechanical linkages make it significantly more durable than typical plastic hobby kits, which is vital for the erratic movements of early-stage RL.

* **Durability:** **High.** The legs use **hard aluminum alloy** and a linkage system rather than direct-servo attachment. This protects the servo shafts from lateral impact during falls.
* **Changing Parts:** **Easy.** It uses standard Hiwonder coreless servos (HPS-0618SG) and modular brackets. Replacement servos and metal frames are widely available as individual spares.
* **Programming SDK:** **Excellent.** Python-friendly with a dedicated ESP32 controller. It supports Arduino and Python natively, and the [Official Wiki](https://wiki.hiwonder.com/projects/MechDog/en/latest/) provides full schematics and API documentation.
* **Cost:** **~$299 (Standard) to ~$519 (Ultimate)**.
* **Reference:** [Hiwonder MechDog Official Page](https://www.hiwonder.com/products/mechdog)

---

### 2. NavBot-EG01 (The Open-Source Specialist)

The EG01 is a community-driven project designed specifically for developers who want a low-cost, Python-first platform.

* **Durability:** **Medium.** The frame is typically 3D printed or lightweight plastic. While it handles its own weight well, repeated high-velocity "faceplants" during RL may require re-printing or re-tightening parts.
* **Changing Parts:** **Very Easy.** Since it is fully open-source, you can 3D print your own replacement parts. It uses off-the-shelf ESP32 boards and hobby servos.
* **Programming SDK:** **Best for Python.** It was built using Python as the primary language. The [NavBot GitHub](https://github.com/fuwei007/Navbot-EG01) includes complete mechanical designs (STP), PCB layouts, and motion control code.
* **Cost:** **~$100–$199** (varies by DIY vs. Pre-assembled).
* **Reference:** [NavBot-EG01 GitHub Repository](https://github.com/fuwei007/Navbot-EG01)

---

### 3. Petoi Bittle (Agile Bionic Platform)

Bittle is a high-speed, injection-molded robot. It is the most "bionic" in its movement but requires specific care for RL training.

* **Durability:** **High.** The high-performance plastic is flexible and absorbs shock well. However, for RL, you **must** use the metal-gear "Alloy" servos to prevent internal gear stripping.
* **Changing Parts:** **Moderate.** Parts are proprietary. While you can buy spares from Petoi, you cannot easily substitute third-party legs or frames without modification.
* **Programming SDK:** **Extensive.** Uses the "OpenCat" framework. While the core is C++, there are excellent Python wrappers and a dedicated [RL Gym environment](https://github.com/ger01d/opencat-gym) created by the community.
* **Cost:** **~$260–$320**.
* **Reference:** [Petoi Bittle Documentation Hub](https://docs.petoi.com/)

---

### 4. RealAnt (The RL Research Standard)

The RealAnt was designed by Ote Robotics specifically as a physical benchmark for RL algorithms like SAC and TD3.

* **Durability:** **Designed for Abuse.** It is a minimal frame designed to be "tethered." It lacks a shell, making it easy to cool the servos and manage power cables.
* **Changing Parts:** **Moderate.** Uses high-end **Dynamixel AX-12A** servos. These are expensive to replace but much harder to break than standard PWM servos. 3D models for the frame are open-source.
* **Programming SDK:** **Research Ready.** Specifically designed to work with OpenAI Gym/Farama Gymnasium. The [RealAnt-RL GitHub](https://github.com/AaltoVision/realant-rl) provides the exact PyTorch implementations for learning to walk.
* **Cost:** **~$350 (DIY) to ~$450 (Assembled)**.
* **Reference:** [Ote Robotics RealAnt GitHub](https://github.com/OteRobotics/realant)

---

### General direction

* **For pure research/speed of learning:** Get the **RealAnt**. It has the most established RL software stack.
* **For durability and out-of-the-box use:** Get the **Hiwonder MechDog**. The metal linkages and integrated IMU provide the most stable hardware for the price.
* **For extreme budget/DIY:** Build the **NavBot-EG01**.

---

[Demonstration of the RealAnt robot learning to walk](https://www.google.com/search?q=https://www.youtube.com/watch%3Fv%3D1-S_qE6P_Yk)
This video illustrates how a tethered, low-cost quadruped can effectively learn complex locomotion gaits in real-time using the algorithms and platforms mentioned in this report.inforcement Learning Research](https://www.youtube.com/watch?v=-jqykPcQ5bs)
This video showcases how robots like the RealAnt and Bittle are used in actual research labs to learn walking gaits from scratch using RL.
