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

root@dhyan:/home/VLSI/VSDBabySoC# ls
images  LICENSE  Makefile  README.md  src

root@dhyan:/home/VLSI/VSDBabySoC/src/module# ls
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

✅ After running the above command, rvmyth.v will be generated in the src/module/ directory.

You can confirm this by listing the files:

```bash
root@dhyan:/home/VLSI/VSDBabySoC/src/module# ls
avsddac.v  avsdpll.v  clk_gate.v  pseudo_rand_gen.sv  pseudo_rand.sv  rvmyth_gen.v  rvmyth.tlv  rvmyth.v  testbench.rvmyth.post-routing.v  testbench.v  vsdbabysoc.v
```

#### Note 
To use this environment in future sessions, always activate it first:
```bash
root@dhyan:~# source sp_env/bin/activate
```
To exit:
```bash
root@dhyan:~# deactivate
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

<img width="1656" height="934" alt="Screenshot From 2025-10-02 12-10-14" src="https://github.com/user-attachments/assets/1dd8edac-081f-4db6-91f3-8f372447c21e" />

<img width="1651" height="699" alt="Screenshot From 2025-10-02 12-12-04" src="https://github.com/user-attachments/assets/88be9ba3-1085-4df4-9c0b-aa5bb85e46ce" />

In this picture we can see the following signals:

**CLK**: This is the input CLK signal of the RVMYTH core. This signal comes from the PLL, originally.

**reset**: This is the input reset signal of the RVMYTH core. This signal comes from an external source, originally.

**OUT**: This is the output OUT signal of the VSDBabySoC module. This signal comes from the DAC (due to simulation restrictions it behaves like a digital signal which is incorrect), originally.

**RV_TO_DAC[9:0]**: This is the 10-bit output [9:0] OUT port of the RVMYTH core. This port comes from the RVMYTH register #17, originally.

**OUT**: This is a real datatype wire which can simulate analog values. It is the output wire real OUT signal of the DAC module. This signal comes from the DAC, originally. 

This was viewed by changing the Data Format of the signal to Analog → Step


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



## VSDBabySoC Post-Synthesis Simulation    

Post-synthesis simulation is a critical step in the digital design flow, providing insights into both the functionality and timing of the synthesized design. 

Unlike pre-synthesis simulation, which focuses solely on verifying the functionality based on the RTL code, post-synthesis simulation uses the synthesized netlist to ensure that the design behaves correctly in terms of both logic and timing.

Key aspects of post-synthesis simulation include:

**Functionality and Timing Verification**: It checks the design's functionality and timing using the gate-level netlist, helping identify timing violations and potential mismatches such as unintended latches.

**Dynamic Circuit Behavior**: Post-synthesis simulation can reveal dynamic circuit behaviors that static methods might miss, ensuring the design operates correctly under real-world conditions.

**Identifying Issues**: It helps in identifying issues that may not be apparent in pre-synthesis simulations, such as glitches or race conditions due to the actual gate delays.

The first step in the design flow is to synthesize the generated RTL code, followed by simulating the result. This process helps uncover more about the code and its potential bugs. In this section, we will synthesize our code and then perform a post-synthesis simulation to look for any issues. Ideally, the post-synthesis and pre-synthesis (modeling section) results should be identical, confirming that the synthesis process has not altered the original design behavior.

#### Why do pre-synthesis simulation? Why not just do post-synthesis simulation?
Pre-synthesis simulation is crucial for verifying the logical functionality of a digital design before it undergoes synthesis. It allows designers to detect and correct logical errors, such as incorrect operator usage or unintended latch inference, early in the development process. This type of simulation focuses solely on the high-level behavior of the design, enabling faster iterations and design exploration without the constraints of gate-level details. On the other hand, post-synthesis simulation, or gate-level simulation, is essential for timing verification and ensuring that the synthesized design meets real-world performance requirements. It accounts for gate delays and helps identify any synthesis-induced issues, providing a final validation of both functionality and timing before the design is implemented in hardware. Together, these simulations ensure a robust and reliable digital design.

Here is the step-by-step execution plan for running the  commands manually:
---
### **Step 1: Load the Top-Level Design and Supporting Modules**
- Launch the yosys synthesis tool from your working directory.
```bash
root@dhyan:/home/VLSI/VSDBabySoC# yosys
```

 
- Read the main vsdbabysoc.v RTL file into the yosys environment.
```bash
yosys> read_verilog src/module/vsdbabysoc.v 
```


- The following cp commands copy essential header files from the src/include directory into the working directory. These include:

  **sp_verilog.vh** – contains Verilog definitions and macros

  **sandpiper.vh** – holds integration-related definitions for SandPiper

  **sandpiper_gen.vh** – may include auto-generated or tool-generated parameters

```bash
root@dhyan:~# cd ~/VLSI/VSDBabySoC
root@dhyan:/home/VLSI/VSDBabySoC# cp -r src/include/sp_verilog.vh .
root@dhyan:/home/VLSI/VSDBabySoC# cp -r src/include/sandpiper.vh .
root@dhyan:/home/VLSI/VSDBabySoC# cp -r src/include/sandpiper_gen.vh .
root@dhyan:/home/VLSI/VSDBabySoC# ls
images  LICENSE  Makefile  output  README.md  sandpiper_gen.vh  sandpiper.vh  sp_env  sp_verilog.vh  src
```

- Read the rvmyth.v file with the include path using -I option.
```bash
yosys> read_verilog -I ~/VLSI/VSDBabySoC/src/include/ ~/VLSI/VSDBabySoC/src/module/rvmyth.v
```

- Read the clk_gate.v file with the include path using -I option.
  
```bash
yosys> read_verilog -I ~/VLSI/VSDBabySoC/src/include/ ~/VLSI/VSDBabySoC/src/module/clk_gate.v
```


 ### **Step 2: Load the Liberty Files for Synthesis**
Inside the same yosys shell, run:
```bash
yosys> read_liberty -lib ~/VLSI/VSDBabySoC/src/lib/avsdpll.lib 
yosys> read_liberty -lib ~/VLSI/VSDBabySoC/src/lib/avsddac.lib 
yosys> read_liberty -lib ~/VLSI/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```


### **Step 3: Run Synthesis Targeting `vsdbabysoc`**
```bash
yosys> synth -top vsdbabysoc
```


### **Step 4: Map D Flip-Flops to Standard Cells**

```bash
yosys> dfflibmap -liberty ~/VLSI/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```


### **Step 5: Perform Optimization and Technology Mapping**
```bash
yosys> opt
yosys> abc -liberty ~/VLSI/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.lib -script +strash;scorr;ifraig;retime;{D};strash;dch,-f;map,-M,1,{D}
```

| Step           | Purpose                                                              |
| -------------- | -------------------------------------------------------------------- |
| `strash`       | Structural hashing (reduces logic redundancy)                        |
| `scorr`        | Sequential sweeping for redundancy removal                           |
| `ifraig`       | Incremental FRAIGing (logic equivalence checking and optimization)   |
| `retime;{D}`   | Move registers across combinational logic to optimize timing         |
| `strash`       | Re-run structural hashing after retiming                             |
| `dch,-f`       | Delay-aware combinational optimization with fast mode                |
| `map,-M,1,{D}` | Map logic to gates minimizing area (`-M,1`) and retime-aware (`{D}`) |



### **Step 6: Perform Final Clean-Up and Renaming**

```bash
yosys> flatten
yosys> setundef -zero
yosys> clean -purge
yosys> rename -enumerate
```
| **Command**         | **Purpose / Usage**                                                                    |
| ------------------- | -------------------------------------------------------------------------------------- |
| `flatten`           | Flattens the entire design hierarchy into a single-level netlist.                      |
| `setundef -zero`    | Replaces all undefined (`x`) logic values with logical `0` to avoid simulation issues. |
| `clean -purge`      | Removes all unused wires, cells, and modules; `-purge` makes it more aggressive.       |
| `rename -enumerate` | Renames internal wires and cells to unique, numbered names for consistency.            |



### **Step 7: Check Statistics**
```bash
yosys> stat
```

13. Printing statistics.
```shell
=== vsdbabysoc ===

   Number of wires:               4736
   Number of wire bits:           6210
   Number of public wires:        4736
   Number of public wire bits:    6210
   Number of ports:                  7
   Number of port bits:              7
   Number of memories:               0
   Number of memory bits:            0
   Number of processes:              0
   Number of cells:               5920
     $scopeinfo                      8
     avsddac                         1
     avsdpll                         1
     sky130_fd_sc_hd__a2111oi_0     10
     sky130_fd_sc_hd__a211o_2        1
     sky130_fd_sc_hd__a211oi_1      26
     sky130_fd_sc_hd__a21boi_0       4
     sky130_fd_sc_hd__a21o_2         1
     sky130_fd_sc_hd__a21oi_1      672
     sky130_fd_sc_hd__a221o_2        1
     sky130_fd_sc_hd__a221oi_1     163
     sky130_fd_sc_hd__a22o_2         4
     sky130_fd_sc_hd__a22oi_1      123
     sky130_fd_sc_hd__a311oi_1       4
     sky130_fd_sc_hd__a31o_2         1
     sky130_fd_sc_hd__a31oi_1      344
     sky130_fd_sc_hd__a32oi_1        2
     sky130_fd_sc_hd__a41oi_1       26
     sky130_fd_sc_hd__and2_2        12
     sky130_fd_sc_hd__and3_2         1
     sky130_fd_sc_hd__clkinv_1     597
     sky130_fd_sc_hd__dfxtp_1     1144
     sky130_fd_sc_hd__lpflow_inputiso0p_1      1
     sky130_fd_sc_hd__mux2i_1       12
     sky130_fd_sc_hd__nand2_1      839
     sky130_fd_sc_hd__nand3_1      249
     sky130_fd_sc_hd__nand3b_1       1
     sky130_fd_sc_hd__nand4_1       41
     sky130_fd_sc_hd__nor2_1       403
     sky130_fd_sc_hd__nor3_1        35
     sky130_fd_sc_hd__nor4_1         2
     sky130_fd_sc_hd__o2111ai_1     20
     sky130_fd_sc_hd__o211a_1        1
     sky130_fd_sc_hd__o211ai_1      49
     sky130_fd_sc_hd__o21a_1         6
     sky130_fd_sc_hd__o21ai_0      866
     sky130_fd_sc_hd__o21ba_2        1
     sky130_fd_sc_hd__o21bai_1      18
     sky130_fd_sc_hd__o221a_2        1
     sky130_fd_sc_hd__o221ai_1       7
     sky130_fd_sc_hd__o22ai_1      155
     sky130_fd_sc_hd__o2bb2ai_1      1
     sky130_fd_sc_hd__o311ai_0       2
     sky130_fd_sc_hd__o31ai_1        3
     sky130_fd_sc_hd__o32ai_1        1
     sky130_fd_sc_hd__o41ai_1        1
     sky130_fd_sc_hd__or2_2         12
     sky130_fd_sc_hd__or3_2          1
     sky130_fd_sc_hd__or4_2          1
     sky130_fd_sc_hd__xnor2_1       13
     sky130_fd_sc_hd__xor2_1        32
```

### **Step 8: Write the Synthesized Netlist**
```bash

yosys> write_verilog -noattr ~/VLSI/VSDBabySoC/output/post_synth_sim/vsdbabysoc.synth.v
```
<img width="1258" height="826" alt="image" src="https://github.com/user-attachments/assets/a615391e-dd9b-4f8d-9a7d-aba0a2ac457b" />

<img width="1523" height="473" alt="Screenshot From 2025-10-02 12-36-47" src="https://github.com/user-attachments/assets/d53eaa09-6903-435a-bd2b-63254e103245" />


## POST_SYNTHESIS SIMULATION AND WAVEFORMS
---

### **Step 1: Compile the Testbench**

Before running the iverilog command, copy the necessary standard cell and primitive models:
These files must be present in the same directory as the testbench (src/module) to resolve all module references during compilation.

```bash
root@dhyan:/home/VLSI/VSDBabySoC# cp -r ~/VLSI/sky130RTLDesignAndSynthesisWorkshop/my_lib/verilog_model/sky130_fd_sc_hd.v .
root@dhyan:/home/VLSI/VSDBabySoC# cp -r ~/VLSI/sky130RTLDesignAndSynthesisWorkshop/my_lib/verilog_model/primitives.v .
```

To ensure that the synthesized Verilog file _(vsdbabysoc.synth.v)_ is available in the src/module directory for further processing or simulation, you can copy it from the output directory to the src/module directory. Here is the step to do that:
```bash
root@dhyan:/home/VLSI/VSDBabySoC# cp -r ~/VLSI/VSDBabySoC/output/post_synth_sim/vsdbabysoc.synth.v ~/VLSI/VSDBabySoC/src/module/
```

Run the following `iverilog` command to compile the testbench:
```bash
root@dhyan:/home/VLSI/VSDBabySoC# iverilog -o /home/spatha/VLSI/VSDBabySoC/output/post_synth_sim/post_synth_sim.out -DPOST_SYNTH_SIM -DFUNCTIONAL -DUNIT_DELAY=#1 -I /home/spatha/VLSI/VSDBabySoC/src/include -I /home/spatha/VLSI/VSDBabySoC/src/module /home/spatha/VLSI/VSDBabySoC/src/module/testbench.v
```
| **Option / Argument**                                                      | **Purpose / Description**                                                            |
| -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| `iverilog`                                                                 | Icarus Verilog compiler used to compile Verilog files into a simulation executable.  |
| `-o /home/spatha/VLSI/VSDBabySoC/output/post_synth_sim/post_synth_sim.out` | Specifies the output binary file for simulation.                                     |
| `-DPOST_SYNTH_SIM`                                                         | Defines the macro `POST_SYNTH_SIM` (used in testbench to switch simulation modes).   |
| `-DFUNCTIONAL`                                                             | Defines `FUNCTIONAL` to use behavioral models instead of detailed gate-level timing. |
| `-DUNIT_DELAY=#1`                                                          | Assigns a unit delay of `#1` to all gates for post-synthesis simulation.             |
| `-I /home/spatha/VLSI/VSDBabySoC/src/include`                              | Adds the `include` directory to the search path for `\`include\` directives.         |
| `-I /home/spatha/VLSI/VSDBabySoC/src/module`                               | Adds the `module` directory to the include path for additional module references.    |
| `/home/spatha/VLSI/VSDBabySoC/src/module/testbench.v`                      | Specifies the testbench file as the top-level design for simulation.                 |

#### ❗Note - You may encounter this error:
```bash
root@dhyan:/home/VLSI/VSDBabySoC# iverilog -o /home/spatha/VLSI/VSDBabySoC/output/post_synth_sim/post_synth_sim.out -DPOST_SYNTH_SIM -DFUNCTIONAL -DUNIT_DELAY=#1 -I /home/spatha/VLSI/VSDBabySoC/src/include -I /home/spatha/VLSI/VSDBabySoC/src/module /home/spatha/VLSI/VSDBabySoC/src/module/testbench.v
/home/spatha/VLSI/VSDBabySoC/src/module/sky130_fd_sc_hd.v:74452: syntax error
I give up.
```
_To resolve this : Update the syntax in the file sky130_fd_sc_hd.v at or around line 74452._

```bash
nano sky130_fd_sc_hd.v
```
###### Change:
```bash
`endif SKY130_FD_SC_HD__LPFLOW_BLEEDER_FUNCTIONAL_V
```
###### To:
```bash
`endif // SKY130_FD_SC_HD__LPFLOW_BLEEDER_FUNCTIONAL_V
```


---
### **Step 2: Navigate to the Post-Synthesis Simulation Output Directory**
```bash
cd output/post_synth_sim/
```
---
### **Step 3: Run the Simulation**

```bash
./post_synth_sim.out
```
---
### **Step 4: View the Waveforms in GTKWave**

```bash
gtkwave post_synth_sim.vcd
```
---
<img width="1655" height="956" alt="Screenshot From 2025-10-02 23-09-14" src="https://github.com/user-attachments/assets/e27ed85c-8e77-4e53-8919-987d597f8cb4" />


## Comparing Pre-Synthesis and Post-Synthesis Output

To ensure that the synthesis process did not alter the original design behavior, the output from the pre-synthesis simulation was compared with the post-synthesis simulation.

Both simulations were run using GTKWave, and the resulting waveforms were observed.

<img width="1651" height="699" alt="Screenshot From 2025-10-02 12-12-04" src="https://github.com/user-attachments/assets/fbe5430a-0541-4fba-a57e-96b55468bf5f" />


<img width="1655" height="956" alt="Screenshot From 2025-10-02 23-09-14" src="https://github.com/user-attachments/assets/e27ed85c-8e77-4e53-8919-987d597f8cb4" />

✅ _The outputs match exactly, confirming that the functionality is preserved across the synthesis flow._

_This validates that the synthesized netlist is functionally equivalent to the RTL design._
