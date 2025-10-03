# Dhyan_VSD_RISC-V_SoC_Tapeout_week2


## Week 2 Task – BabySoC Fundamentals & Functional Modelling

### Objective

The goal of this task is to develop a solid understanding of **System-on-Chip (SoC) fundamentals** and apply these concepts through functional modeling of the **BabySoC** using **simulation tools** like **Icarus Verilog** and **GTKWave**. By engaging with these tools and the BabySoC model, you will get hands-on experience in designing, simulating, and verifying essential SoC components.

In this write-up, I will cover:

1. What is a **System-on-Chip (SoC)**?
2. Components of a typical **SoC**: **CPU, memory, peripherals, interconnects**.
3. Why **BabySoC** is a simplified model for learning SoC concepts.
4. The role of **functional modeling** before the **RTL** and **physical design** stages.

---

### 1. **What is a System-on-Chip (SoC)?**

A **System-on-Chip (SoC)** is an integrated circuit that combines all the essential components of a computer or embedded system onto a single chip. Traditionally, a computer or embedded system would require several chips (e.g., processor, memory, communication interfaces), but with SoCs, these components are integrated into a single, compact chip. SoCs are used in a wide variety of electronic devices like smartphones, tablets, wearables, and IoT devices, where space, power, and efficiency are critical.

#### **Key Features of SoCs:**

* **Compact Design**: SoCs are designed to be small in size, allowing for miniaturized devices such as smartphones and wearables.
* **Power Efficiency**: Combining multiple components on one chip reduces power consumption, making SoCs ideal for battery-powered devices.
* **High Performance**: The integration of all key components enables faster data processing and lower latency.
* **Cost-Effective**: Manufacturing a single chip is often cheaper than fabricating multiple discrete components, reducing the overall cost.

#### **Typical Components of an SoC:**

1. **CPU (Central Processing Unit)**: The heart of the SoC, responsible for processing data, executing instructions, and managing system tasks. In modern SoCs, CPUs are often multi-core for better multitasking and performance.
2. **Memory**: This includes **RAM** (for temporary data storage) and **ROM/Flash** (for permanent storage of the system's firmware or operating system).
3. **Peripherals**: These include input/output interfaces such as **USB**, **HDMI**, **UART**, **I2C**, and **SPI**, which allow the SoC to communicate with external devices.
4. **Interconnects**: These are the pathways (buses) through which different components of the SoC communicate. They include high-speed connections like **AXI** or **AMBA**, which ensure data is transferred efficiently between components.

SoCs are fundamental in modern electronics, powering everything from smartphones to autonomous vehicles and edge computing devices.

---

### 2. **Why BabySoC is a Simplified Model for Learning SoC Concepts**

The **BabySoC** is a simplified, educational version of a typical SoC, designed to help learners understand key SoC concepts without the complexity of industrial-grade SoCs. BabySoC incorporates a minimal set of components, specifically focused on the **CPU**, **PLL (Phase-Locked Loop)**, and **DAC (Digital-to-Analog Converter)**. The primary goal of BabySoC is to enable the understanding of how these individual components interact in an SoC environment, paving the way for more complex designs later on.

#### **Key Components of BabySoC:**

1. **RVMYTH (RISC-V Core)**: This is a simple RISC-V based CPU that forms the central processing unit of the BabySoC. RISC-V is an open-source architecture that allows for easy customization and experimentation, making it ideal for educational purposes.
<img width="1248" height="698" alt="image" src="https://github.com/user-attachments/assets/109fdb13-d1f4-4a0e-a5cc-1b9d0d3df2ae" />


2. **PLL (Phase-Locked Loop)**: The PLL ensures that the system’s clock is stable and synchronized. It takes an input signal and adjusts its output to match the reference frequency. This is particularly important in SoC designs where components may operate at different frequencies. The BabySoC uses the PLL to synchronize the operation of the CPU and the DAC.
<img width="885" height="535" alt="image" src="https://github.com/user-attachments/assets/a5d8035c-f915-43e3-acc3-ca434f021e3a" />


3. **DAC (Digital-to-Analog Converter)**: The DAC converts the digital data processed by the CPU into analog signals. This component is crucial for interfacing with the real world, as many devices (e.g., speakers, displays) require analog input. BabySoC uses a **10-bit DAC**, which provides a balance between accuracy and complexity, converting 1024 discrete digital values into corresponding analog outputs.
<img width="600" height="556" alt="image" src="https://github.com/user-attachments/assets/c53bfa4b-e9fb-4753-88fb-e37fb3264409" />


#### **Why is BabySoC Simplified?**

* **Educational Focus**: BabySoC is designed for **hands-on learning**. It helps students and engineers understand how individual components (CPU, PLL, DAC) interact in an SoC, without overwhelming them with the complexities of more advanced SoC designs.
* **Simulation-Friendly**: By using **Icarus Verilog** for simulation and **GTKWave** for waveform analysis, BabySoC allows users to simulate the interaction between its components, check for functional correctness, and visualize how signals evolve over time.
* **Real-World Analog Integration**: The inclusion of a DAC in BabySoC gives learners an opportunity to explore digital-to-analog conversion, a concept that is often critical in multimedia and sensor systems in real-world applications.

---

### 3. **The Role of Functional Modeling Before RTL and Physical Design**

Before jumping into **Register Transfer Level (RTL)** design or **physical design**, functional modeling plays a crucial role in SoC design. Functional modeling allows for **early verification** of the system's behavior, ensuring that all components will work together correctly once implemented in hardware.

#### **Why Functional Modeling?**

* **Early Detection of Errors**: Functional modeling helps identify and resolve bugs early in the design process, reducing the risk of costly mistakes later.
* **Testing Without Hardware**: It allows designers to test the behavior of the SoC without needing physical hardware, which is particularly useful in the early stages of design when hardware is not yet available.
* **Better Understanding of Component Interaction**: Modeling allows designers to simulate how the CPU, memory, interconnects, and peripherals will behave together in the system. For BabySoC, this means ensuring that the CPU correctly interacts with the PLL and DAC, and that the digital signals are appropriately converted to analog.
* **Reduced Design Time**: By addressing functional issues early, functional modeling reduces the time spent on testing and debugging at the RTL or physical design stages, making the overall design process more efficient.

#### **How Functional Modeling Works with Tools like Icarus Verilog and GTKWave**

* **Icarus Verilog**: This is an open-source simulator for Verilog, a hardware description language used to model and simulate digital circuits. By writing a high-level description of the BabySoC, designers can simulate its behavior, test various scenarios, and ensure the components are functioning as expected.
* **GTKWave**: This tool is used to visualize the output of Verilog simulations. By plotting signal transitions and waveforms, GTKWave provides insights into the timing, synchronization, and correctness of the SoC’s operation.

Functional modeling with these tools helps ensure that the design is sound and ready for the next stages of RTL coding and physical design.

<img width="867" height="1305" alt="image" src="https://github.com/user-attachments/assets/227b1a23-df37-4268-af3d-378caf97c33a" />

---

### 4. **Conclusion**

Understanding **System-on-Chip (SoC)** design is essential for anyone looking to work in embedded systems or modern computing platforms. The **BabySoC** offers a simplified yet powerful introduction to SoC architecture, helping learners grasp core concepts like **digital-to-analog conversion**, **clock synchronization**, and **functional modeling**. By using simulation tools like **Icarus Verilog** and **GTKWave**, BabySoC enables hands-on learning and testing of the interactions between the CPU, PLL, and DAC.

Through the **functional modeling** approach, BabySoC offers a platform for exploring the complex world of SoC design, enabling learners to visualize the internal operations of an SoC and understand how components work together to achieve the desired output. As a result, BabySoC serves as an effective educational tool, providing the foundation for more advanced SoC designs in the future.

---

### **References**

* **Fundamentals of SoC Design**: [GitHub Repository](https://github.com/hemanthkumardm/SFAL-VSD-SoCJourney/tree/main/11.%20Fundamentals%20of%20SoC%20Design)
* **Icarus Verilog**: [Official Website](http://iverilog.icarus.com/)
* **GTKWave**: [Official Website](http://gtkwave.sourceforge.net/)

---


### Project Structure
- src/include/ - Contains header files (*.vh) with necessary macros or parameter definitions.
- src/module/ - Contains Verilog files for each module in the SoC design.
- output/ - Directory where compiled outputs and simulation files will be generated.

### Setup and Prepare Project Directory
Clone or set up the directory structure as follows:
```txt
VSDBabySoC/
├── src/
│   ├── include/
│   │   ├── sandpiper.vh
│   │   └── other header files...
│   ├── module/
│   │   ├── vsdbabysoc.v      # Top-level module integrating all components
│   │   ├── rvmyth.v          # RISC-V core module
│   │   ├── avsdpll.v         # PLL module
│   │   ├── avsddac.v         # DAC module
│   │   └── testbench.v       # Testbench for simulation
└── output/
└── compiled_tlv/         # Holds compiled intermediate files if needed
```
### 🛠️ Cloning the Project

To begin, clone the VSDBabySoC repository using the following command:

```bash
cd ~/VLSI

git clone https://github.com/manili/VSDBabySoC.git

cd ~/VLSI/VSDBabySoC/

root@spatha-VirtualBox:~/VLSI$ ls VSDBabySoC/
images  LICENSE  Makefile  README.md  src

spatha@spatha-VirtualBox:~/VLSI$ ls VSDBabySoC/src/module/
avsddac.v  avsdpll.v  clk_gate.v  pseudo_rand_gen.sv  pseudo_rand.sv  rvmyth_gen.v  rvmyth.tlv  rvmyth.v  testbench.rvmyth.post-routing.v  testbench.v  vsdbabysoc.v
```
### TLV to Verilog Conversion for RVMYTH

Initially, you will see only the `rvmyth.tlv` file inside `src/module/`, since the RVMYTH core is written in TL-Verilog.

To convert it into a `.v` file for simulation, follow the steps below:

<strong>🔧 TLV to Verilog Conversion Steps</strong>

```bash
# Step 1: Install python3-venv (if not already installed)
sudo apt update
sudo apt install python3-venv python3-pip

# Step 2: Create and activate a virtual environment
cd ~/VLSI/VSDBabySoC/
python3 -m venv sp_env
source sp_env/bin/activate

# Step 3: Install SandPiper-SaaS inside the virtual environment
pip install pyyaml click sandpiper-saas

# Step 4: Convert rvmyth.tlv to Verilog
sandpiper-saas -i ./src/module/*.tlv -o rvmyth.v --bestsv --noline -p verilog --outdir ./src/module/
```
 ![Alt Text](Images/1.png)

✅ After running the above command, rvmyth.v will be generated in the src/module/ directory.

You can confirm this by listing the files:

```bash
spatha@spatha-VirtualBox:~$ cd VLSI/VSDBabySoC/
spatha@spatha-VirtualBox:~/VLSI/VSDBabySoC$ ls src/module/
avsddac.v  avsdpll.v  clk_gate.v  pseudo_rand_gen.sv  pseudo_rand.sv  rvmyth_gen.v  rvmyth.tlv  rvmyth.v  testbench.rvmyth.post-routing.v  testbench.v  vsdbabysoc.v
```

#### Note 
To use this environment in future sessions, always activate it first:
```bash
spatha@spatha-VirtualBox:~$ source sp_env/bin/activate
```
To exit:
```bash
spatha@spatha-VirtualBox:~$ deactivate
```

### Simulation Steps

#### <ins>Pre-Synthesis Simulation</ins>

Run the following command to perform a pre-synthesis simulation:

```bash
cd ~/VLSI/VSDBabySoC/

mkdir -p output/pre_synth_sim

iverilog -o ~/VLSI/VSDBabySoC/output/pre_synth_sim/pre_synth_sim.out -DPRE_SYNTH_SIM -I ~/VLSI/VSDBabySoC/src/include -I ~/VLSI/VSDBabySoC/src/module ~/VLSI/VSDBabySoC/src/module/testbench.v
```

Then run:
```bash
cd output/pre_synth_sim

./pre_synth_sim.out
```

Explanation:

- DPRE_SYNTH_SIM: Defines the PRE_SYNTH_SIM macro for conditional compilation in the testbench.
- The resulting pre_synth_sim.vcd file can be viewed in GTKWave.

#### Viewing Waveform in GTKWave

After running the simulation, open the VCD file in GTKWave: 

```bash

cd ~/VLSI/VSDBabySoC/

gtkwave output/pre_synth_sim/pre_synth_sim.vcd

```
Drag and drop the CLK, reset, OUT (DAC), and RV TO DAC [9:0] signals to their respective locations in the simulation tool

 ![Alt Text](Images/today4.jpg)

In this picture we can see the following signals:

**CLK**: This is the input CLK signal of the RVMYTH core. This signal comes from the PLL, originally.

**reset**: This is the input reset signal of the RVMYTH core. This signal comes from an external source, originally.

**OUT**: This is the output OUT signal of the VSDBabySoC module. This signal comes from the DAC (due to simulation restrictions it behaves like a digital signal which is incorrect), originally.

**RV_TO_DAC[9:0]**: This is the 10-bit output [9:0] OUT port of the RVMYTH core. This port comes from the RVMYTH register #17, originally.

**OUT**: This is a real datatype wire which can simulate analog values. It is the output wire real OUT signal of the DAC module. This signal comes from the DAC, originally. 

This can be viewed by changing the Data Format of the signal to Analog → Step

#### Viewing DAC output in analog mode

Drag and drop the CLK, reset, OUT (DAC) (as analog step), and RV TO DAC [9:0] signals to their respective locations in the simulation tool 

![Alt Text](Images/today5.jpeg)

![Alt Text](Images/today6.jpg)


### Trouble shooting tips

   - Module Redefinition: If you encounter redefinition errors, ensure modules are included only once, either in the testbench or in the command line.
   - Path Issues: Verify paths specified with -I are correct. Use full paths if relative paths cause errors.

## Why Pre-Synthesis and Post-Synthesis?

1. **Pre-Synthesis Simulation**: 
   - Focuses only on verifying functionality based on the RTL code.
   - Zero-delay environment, with events occurring on the active clock edge.

2. **Post-Synthesis Simulation (GLS)**:
   - Uses the synthesized netlist (gate-level) to simulate both functionality and timing.
   - Identifies timing violations and potential mismatches (e.g., unintended latches).
   - Helps verify dynamic circuit behavior that static methods may miss.
