# 💧 Water Level Indicator (Conductivity Based)

This project is a simple water level detection system that uses **LED indicators** to show the water level remotely.  
It is designed mainly for large tanks (e.g., 2–3 tons), but here it is demonstrated with a **0.5 L plastic bottle** as a small-scale prototype.

## 🧰 Components
- 1× 0.5 L plastic bottle (for the demo)
- 1× thick copper wire (1–2 mm) – **main electrode (anode)**
- 4× level probe wires (sensor electrodes)
- 4× NPN transistors (e.g., BC547/2N3904, etc.)
- 4× LEDs
- 1× On/Off switch
- 1× 9 V battery + battery clip
- Wooden board (for mounting)
- Silicone (for sealing and mechanical fixing)
- Soldering materials, small wires

## 🛠 Mechanical Assembly
- All electronic components are soldered and mounted on a **wooden board**.
- The plastic bottle is **glued with silicone** to the side of the board for stability and waterproofing.
- Small holes are drilled in the bottle at different heights. **Probe wires** are inserted through these holes and sealed with silicone.
- A **thick copper wire** is placed at the very bottom of the bottle, serving as the **main electrode**.

## ⚙️ How It Works
When water reaches a certain level inside the bottle (or tank), a conductive path is formed between the **main electrode** (at the bottom, connected to the battery’s + terminal) and the **probe** at that height.  
This small current triggers the **base** of the corresponding NPN transistor. Once triggered, the transistor conducts and the corresponding LED lights up.

As the water level rises, more probes are activated, turning on more LEDs sequentially.

Basic connection logic:
- **Main electrode (bottom copper wire)** → 9 V **+** terminal
- **LED anode** → main electrode
- **LED cathode** → transistor **collector**
- **Transistor emitter** → switch → 9 V **–** (GND)
- **Level probe** → transistor **base**

## 🔌 Power Supply
- Powered by a 9 V battery.  
For long-term use, a 5 V DC adapter can be used (with minor wiring changes).

## 💡 Notes & Improvements
- This version uses **no resistors**, so LED current is limited only by the water's conductivity and transistor characteristics.  
- For safer and more controlled operation, adding series resistors to LEDs and base resistors to transistors is recommended.
- For long-term use, replace copper wires with **stainless steel electrodes** to prevent corrosion.
- For more stability in large tanks, shielded cables and waterproof connectors are recommended.

## ⚠️ Warnings
- If used in drinking water applications, choose food-safe electrode and sealing materials.
- This circuit is only for **indication purposes**. If you want to control a pump or valve, add an **isolated relay/MOSFET driver**.

