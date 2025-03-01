# DIY Wi-Fi Patch Antenna (2.4 GHz)

## 📡 Overview
This guide covers the step-by-step process of designing, fabricating, and testing a **low-cost 2.4 GHz Wi-Fi patch antenna** using PCB etching. 

---

## 🛠 Materials & Tools
| **Item** | **Purpose** | **Estimated Cost** |
|---------|-------------|--------------------|
| **FR4 Copper-Clad PCB (1.6mm)** | Substrate for antenna | ₹100 |
| **Ferric Chloride (FeCl3) Solution** | PCB etching | ₹100 |
| **SMA Connector (Female)** | RF connection | ₹50 |
| **Laser Printer + Glossy Paper** | Toner transfer for etching | ₹0 (if available) |
| **Iron (for heat transfer)** | Press toner onto PCB | ₹0 (if available) |
| **Drill (Hand Drill or Dremel)** | Making SMA connector hole | ₹100 |
| **Soldering Iron & Flux** | Attaching SMA connector | ₹100 |

---

## 📏 Design Calculations
For a **2.4 GHz** rectangular microstrip patch on **FR4 (εr ≈ 4.4, height = 1.6 mm)**:

- **Patch Width (W):**
  ```
  W = c / (2 * f_0 * sqrt((εr + 1) / 2))

  c=3×108 m/s (speed of light)
  f0​=2.45 GHz
  εr​=4.4 (FR4 substrate)

  ```
  ✅ **W ≈ 38 mm**

- **Patch Length (L):**
  ```
  L = c / (2 * f_0 * sqrt(εeff)) - 2 * ΔL

  εeff​≈4.0
  ΔL≈1.5 mm (edge effect correction)

  ```
  ✅ **L ≈ 29 mm**

- **Ground plane:** Should be slightly larger than the patch (e.g., **50 mm × 40 mm**).
- **Feed point:** **1.5 mm from the patch edge** for impedance matching.

---

## 🏗 Fabrication Steps
### 1️⃣ Print Antenna Layout
- Use **KiCad/AutoCAD** to design a 2D layout.
- Print on **glossy paper** using a **laser printer**.

### 2️⃣ Transfer to PCB
- Place printout on copper-clad board.
- Heat with **iron (~150°C for 5 minutes)** to transfer toner.

### 3️⃣ Etching
- Immerse in **FeCl3 solution (~10 min)** until exposed copper dissolves.
- Rinse with water & clean excess toner using **acetone**.

### 4️⃣ Drilling & Soldering
- Drill **SMA connector hole** using a hand drill.
- Solder the **SMA connector** for RF connection.

---

## 📊 Testing & Tuning
### ✅ Using a Vector Network Analyzer (VNA)
- **Check S11 (Return Loss):** Should be **below -10 dB at 2.4 GHz**.
- **VSWR (Voltage Standing Wave Ratio):** Ideal **1.5:1 or lower**.
- **Tweak the feed point if needed** to improve matching.

### ✅ DIY Testing Without VNA
- **Use an ESP8266 or RTL-SDR** to check signal strength at different angles.
- **Wi-Fi Signal Strength App (e.g., NetSpot, Wireshark)** to measure range.

---

## 🚀 Optional Upgrades
✅ **Add a Reflector (10mm Below Patch)** → Boosts Gain  
✅ **Use Rogers RT5880 (εr = 2.2) Instead of FR4** → Higher Efficiency  
✅ **Try a Dual-Band Design (2.4 GHz & 5 GHz)** → Compact Wi-Fi Antennas  

---



# DIY mmWave (5G) Patch Antenna (28 GHz)

## 📡 Overview
This guide covers the design, fabrication, and testing of a **28 GHz mmWave patch antenna** for 5G applications. Due to the high frequency, precise fabrication is required, typically using **Rogers RT5880** or other low-loss substrates.

---

## 🛠 Materials & Tools
| **Item** | **Purpose** | **Estimated Cost** |
|---------|-------------|--------------------|
| **Rogers RT5880 (εr ≈ 2.2, h = 0.254mm)** | Low-loss substrate for mmWave | ₹500+ |
| **Photolithography Kit** | High-precision PCB etching | ₹1000+ |
| **SMA/K Connector (2.92mm, 50Ω)** | High-frequency RF connection | ₹500 |
| **Drill (Micro Drill 0.5mm)** | Connector mounting | ₹200 |
| **Vector Network Analyzer (VNA, 40 GHz)** | Testing S-parameters | ₹5000+ (rental available) |
| **Waveguide Adapter (WR-28)** | Optional for testing | ₹3000 |

---

## 📏 Design Calculations
For a **28 GHz rectangular microstrip patch antenna** on **Rogers RT5880 (εr ≈ 2.2, height = 0.254 mm):**

- **Patch Width (W):**
  ```
  W = c / (2 * f_0 * sqrt((εr + 1) / 2))
  ```
  ✅ **W ≈ 4.2 mm**

- **Patch Length (L):**
  ```
  L = c / (2 * f_0 * sqrt(εeff)) - 2 * ΔL
  ```
  ✅ **L ≈ 3.8 mm**

- **Ground plane:** **6 mm × 6 mm** (to reduce edge effects).
- **Feed point:** **Microstrip line matched to 50Ω (0.2 mm width).**

---

## 🏗 Fabrication Steps
### 1️⃣ Design Layout
- Use **HFSS, CST Studio, or KiCad** for simulation and layout.
- Print the design on a transparency film for photolithography.

### 2️⃣ Photolithography Etching
- **Expose the Rogers PCB to UV light** through the transparency mask.
- Develop and **etch using ammonium persulfate** for precise feature sizes.

### 3️⃣ Drilling & Soldering
- Drill a **0.5 mm hole for SMA/K connector**.
- **Solder using low-temperature solder** to avoid substrate damage.

---

## 📊 Testing & Tuning
### ✅ Using a Vector Network Analyzer (VNA)
- **Check S11 (Return Loss):** Below **-10 dB at 28 GHz**.
- **VSWR (Voltage Standing Wave Ratio):** Target **≤1.5:1**.
- **Adjust feed or ground size** if needed.

### ✅ Radiation Pattern Measurement
- **Anechoic chamber recommended**.
- Use a **horn antenna and spectrum analyzer**.

---

## 🚀 Optional Upgrades
✅ **Add an Array Configuration (2×2, 4×4)** → Boosts Gain  
✅ **Use a Dielectric Lens on Top** → Beamforming  
✅ **Try a Dual-Band Design (28 GHz & 60 GHz)** → Multi-frequency  

---


# DIY Wearable Textile Antenna

## 📡 Overview
This guide covers the design, fabrication, and testing of a **wearable textile antenna** for IoT, medical, or smart clothing applications. The antenna operates in the **2.4 GHz ISM band** (Wi-Fi, Bluetooth) and is made using **conductive fabric** for flexibility.

---

## 🛠 Materials & Tools
| **Item** | **Purpose** | **Estimated Cost** |
|---------|-------------|--------------------|
| **Conductive Fabric (ShieldIt, Zelt)** | Radiating & ground plane | ₹500+ |
| **Non-Conductive Fabric (Cotton, Felt, Neoprene)** | Dielectric substrate | ₹200 |
| **Adhesive Spray or Conductive Thread** | Attachment method | ₹300 |
| **SMA Connector (50Ω)** | RF connection | ₹500 |
| **Scissors, Cutter, Ruler** | Shaping materials | ₹100 |
| **Vector Network Analyzer (VNA)** | Testing return loss | ₹5000+ (rental available) |

---

## 📏 Design Calculations
For a **2.4 GHz rectangular patch antenna** on **3 mm thick cotton fabric (εr ≈ 1.8):**

- **Patch Width (W):**
  ```
  W = c / (2 * f_0 * sqrt((εr + 1) / 2))
  ```
  ✅ **W ≈ 38 mm**

- **Patch Length (L):**
  ```
  L = c / (2 * f_0 * sqrt(εeff)) - 2 * ΔL
  ```
  ✅ **L ≈ 29 mm**

- **Ground Plane:** **40 mm × 40 mm**.
- **Feed point:** **Inset-fed or microstrip line matched to 50Ω**.

---

## 🏗 Fabrication Steps
### 1️⃣ Design Layout
- Use **HFSS, CST Studio, or KiCad** for simulation and layout.
- Print and cut out the patch and ground plane from **conductive fabric**.

### 2️⃣ Assembly
- Attach the **patch to the dielectric fabric** using **adhesive spray** or sew with **conductive thread**.
- **Ground plane on the backside**.
- **Insert SMA connector** and attach via conductive stitching.

---

## 📊 Testing & Tuning
### ✅ Using a Vector Network Analyzer (VNA)
- **Check S11 (Return Loss):** Below **-10 dB at 2.4 GHz**.
- **VSWR (Voltage Standing Wave Ratio):** Target **≤1.5:1**.
- **Adjust feed position or length** if needed.

### ✅ Radiation Pattern Measurement
- **Test in an anechoic chamber or open space**.
- Use a **horn antenna and spectrum analyzer**.

---

## 🚀 Optional Upgrades
✅ **Flexible Dipole or Fractal Design** → Better conformability  
✅ **Dual-Band (2.4 GHz & 5 GHz)** → Wi-Fi enhancement  
✅ **Integration with E-Textiles** → Smart clothing applications  

---


