# L5Driving – Minimalist Autonomous Navigation Logic

This isn’t a full stack.  
This is everything you actually need — and nothing else.

---

## 🚗 What It Is

A simplified Level 5 driving logic system.

No lidar.  
No giant models.  
No hallucinations.

> Just vector physics, dual-camera input, and predictive collisions.

---

## 🧠 Core Concepts

- **Dual-camera depth emulation** – calculates range with stereo input  
- **Impact prediction vector model** – determines object threat by vector intersection  
- **Simplified decision tree logic** – no ML, just trajectory math  
- **Failsafe-first behavior loop** – system always prioritizes physical integrity over path loyalty

---

## 💸 Why?

Because most L5 systems are overengineered, sensor-heavy, and economically unsustainable.

This model was designed for:

- Edge devices  
- Cheap hardware  
- Reliable fallback navigation  
- AI-optional deployment

---

## 🔧 Components

- `impact_vector_predictor.py`  
- `trajectory_simulator.py`  
- `dualcam_depth_solver.py`

All fully embeddable into low-cost chips.

---

## 🤷 Limitations

- No semantic parsing — pedestrians are just velocity+mass vectors  
- No map preloading — system is live-context only  
- Best paired with hardware redundancy

---

## 🧪 Status

Prototype logic only.  
Proof-of-concept modules in design.

Funding or co-development welcome.  
Because we’d rather crash softly than drift intelligently.

---

📮 bramblestudio.sibyl@gmail.com
