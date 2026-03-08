# ✈️ Altitude Hold Controller using Cascade PID (3DOF Aircraft)

This project demonstrates the **design and simulation of an altitude hold autopilot** using a **cascade PID control architecture** for a **3-DOF longitudinal aircraft model** in MATLAB/Simulink.

The controller automatically maintains the desired aircraft altitude by adjusting the **pitch angle and elevator deflection** through nested feedback loops.

---

## 📌 Project Overview

The system uses a **cascade control architecture** consisting of two control loops:

- 🔹 **Outer Loop:** Altitude PID Controller  
- 🔹 **Inner Loop:** Pitch PID Controller  

The altitude reference is compared with the actual aircraft altitude to generate an altitude error. The altitude PID controller processes this error and generates a **pitch reference**. The pitch PID controller then generates an **elevator command**, which drives the aircraft model. The updated aircraft altitude is fed back into the system to reduce error.

This nested control structure improves system stability and disturbance rejection compared to single-loop altitude control.

---

## 🧰 Software Requirements

To run this simulation the following software is required:

| Software | Requirement |
|--------|--------|
| MATLAB | R2020a or later |
| Simulink | Required |
| Aerospace Blockset | Required |

⚠️ The simulation relies on the **3DOF longitudinal aircraft model** provided by the Aerospace Blockset.

---

## ⚙️ Control Architecture

The controller operates using a **cascade PID structure**.

1️⃣ Altitude reference is compared with measured altitude.  
2️⃣ Altitude PID controller generates a pitch reference.  
3️⃣ Pitch PID controller generates elevator deflection.  
4️⃣ Aircraft model responds to elevator input.  
5️⃣ Updated altitude is fed back to the controller.

This approach separates the fast and slow dynamics of the system:

- 🛫 The **inner pitch loop** stabilizes fast aircraft pitch dynamics.  
- 📏 The **outer altitude loop** regulates the slower altitude dynamics.

---

## 📊 Simulation Outputs

The model produces time-domain plots for the following variables:

- 📈 Angle of Attack (α)
- 📈 Pitch Angle (θ)
- 📈 Pitch Rate (q)
- 📈 Aircraft Altitude (h)

These responses are used to evaluate the performance of the altitude hold controller.

---

## 🎯 Expected System Behavior

When the altitude reference changes from **2000 m to 2200 m**, the system response typically shows:

✔ Aircraft pitching upward  
✔ Smooth altitude increase  
✔ Moderate overshoot  
✔ System settling at the commanded altitude  
✔ Pitch angle returning close to equilibrium  

---

## 🔧 Parameter Modifications

Users can experiment with system behavior by modifying the following parameters within the Simulink model.

### 1️⃣ Altitude Reference Step Block

Modify:
- Final Value
- Step Time

### 2️⃣ PID Controller Gains

Modify the gains inside the controller blocks:

| Gain | Effect |
|-----|------|
| Kp | Faster response |
| Ki | Removes steady-state error |
| Kd | Improves damping |

Adjusting these parameters allows users to observe different system responses such as faster response, increased overshoot, or improved damping.

---

## 🧪 Example Experiments

Possible experiments include:

🔹 Increasing the altitude command (e.g., **2000 m → 2500 m**)  
🔹 Reducing altitude PID gains to observe slower response  
🔹 Increasing derivative gain to reduce overshoot  
🔹 Modifying controller gains to study system stability  

---

## ⚠️ Limitations

- The model represents **3DOF longitudinal aircraft dynamics only**
- Roll and yaw dynamics are not included
- Throttle-based altitude control is not implemented
- Wind disturbances are not modeled

---

## 🚀 Future Improvements

Possible extensions of this project include:

- ✈️ Full **6DOF aircraft modeling**
- 📊 **Vertical speed hold** control mode
- 🌬 Wind disturbance modeling
- 🖥 FlightGear visualization
- 🔌 Hardware-in-the-loop testing

---

## 👨‍💻 Author

**Likith Kumar B M**  
B.Tech – Electrical and Electronics Engineering  
CHRIST (Deemed to be University)
