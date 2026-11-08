# Sorting Station Automation Project

An automated industrial sorting station simulation designed to identify, categorize, and redirect parts (lids and bases made of green plastic or metal) using a Siemens S7-1200 PLC and Factory I/O[cite: 4].

## 📺 Demo Video
Watch the sorting station in action: [Click here to watch the demo on YouTube](https://youtu.be/VM9NxF4LwKA?si=YmtraZE7GlT4-t0d)

---

## 🛠️ System Overview & How It Works
1. **Emitter:** Automatically spawns workpieces onto the main belt conveyor[cite: 3].
2. **Detection:** A **Vision Sensor** (configured in digital mode) scans each incoming part to identify its material and structure (Metal Base, Green Plastic Base, or Lids)[cite: 3].
3. **Sorting & Routing:** As the part moves down the line, automated **Pivot Arm Sorters** and conveyor lines activate to route the part into its designated path[cite: 3].
4. **Counting & Display:** IEC Counters track throughput metrics (total items, metal bases, plastic bases, and lids), displaying the live counts on the control panel's digital indicators[cite: 3].

---

## 📋 I/O Table (Inputs & Outputs)

| Address | Tag Name | Type | Description |
| :--- | :--- | :--- | :--- |
| `%I0.0` | `Start Button` | Input | Initiates the automated cycle |
| `%I0.1` | `Emergency Button` | Input | Safety stop override |
| `%I0.2` | `Stop Button` | Input | Halts system operation |
| `%I0.3` | `Reset Button` | Input | Resets counter displays |
| `%I0.5` | `Vision 1` | Input | Vision sensor digital bit 1 |
| `%I0.6` | `Vision 2` | Input | Vision sensor digital bit 2 |
| `%I0.7` | `Vision 3` | Input | Vision sensor digital bit 3 |
| `%I1.0` | `Vision 4` | Input | Vision sensor digital bit 4 |
| `%I1.1` | `Count Sensor 2` | Input | Retroreflective tracking sensor |
| `%Q0.0` | `Conveyor 1` | Output | Main transport belt |
| `%Q0.1` | `Running Light` | Output | Green stack light indicator |
| `%Q0.2` | `Stand By` | Output | Amber stack light indicator |
| `%Q0.3` | `Stop Light` | Output | Red stack light indicator |
| `%Q1.0` | `Sorter 1` | Output | Pivot arm actuator for line diversion |

---

## ⚙️ Requirements & Software
To open and run this project, you will need:
* **Factory I/O** (Version 2.5.10 or newer)[cite: 8]
* **Siemens TIA Portal** (V16 / V17 / V18 or compatible with `.zap20` archives)
* **PLCSIM** (or a physical Siemens S7-1200 PLC)

---

## 🚀 How to Open and Run the Project

1. **Download the Project:** Clone this repository or download it as a ZIP file and extract it.
2. **Open the Control Program:** 
   * Open **TIA Portal**.
   * Go to **Project** -> **Retrieve** and select the `Assigment SEM3.zap20` file to load the PLC program[cite: 9].
3. **Compile & Simulate:** 
   * Compile the code and start **PLCSIM** (ensure simulation support with blocks is enabled).
4. **Open the Factory I/O Scene:**
   * Launch **Factory I/O**.
   * Open the scene file `Assigment SEM3.factoryio`[cite: 9].
   * In Factory I/O, open **Drivers**, select **Siemens S7-1200/S7-1500**, and connect to PLCSIM.
5. **Run:** Press **Play** in Factory I/O and press the green **Start** button on the virtual control panel[cite: 3]!

---

## 👤 Author
* **Muhamad Syafiq Adam Bin Shamsul Azuan**[cite: 4]
