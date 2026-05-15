# openlane_sky130_workshop
The OpenLANE SKY130 VSD Workshop is a hands-on workshop for learning complete ASIC physical design flow using open-source VLSI tools and the SKY130 technology.
# Day 1 — Inception of Open-Source EDA, OpenLANE & Sky130 PDK

## Understanding Modern Chip Design

The field of VLSI design focuses on creating highly complex integrated circuits by combining millions of transistors onto a single silicon chip. Traditionally, ASIC development depended heavily on expensive commercial Electronic Design Automation (EDA) tools and proprietary fabrication technologies, limiting access to only large semiconductor companies. With the rise of open-source EDA tools and publicly available Process Design Kits (PDKs), it has now become possible for students, researchers, and hardware enthusiasts to learn and implement complete ASIC design flows using freely accessible resources.

The OpenLANE and Sky130 ecosystem represents one of the biggest milestones in democratizing chip design. It allows designers to move from RTL design all the way to GDSII layout generation using open-source tools and real fabrication technology.

---

## Understanding the QFN-48 Package

When observing an embedded development board or electronic circuit, the visible black component is usually not the actual silicon chip itself. Instead, it is a protective package that contains the silicon die inside it. One commonly used package in ASIC and embedded applications is the **QFN-48 (Quad Flat No-Lead)** package.

The QFN package provides:

- Mechanical protection to the silicon die
- Electrical connections between the chip and PCB
- Better heat dissipation
- Compact size for modern electronic devices

Inside the package, the actual silicon die is mounted at the center. Tiny metallic wires called **bond wires** connect the die pads to the external package pins. These pins allow the chip to communicate with external peripherals, power supplies, clocks, and communication interfaces.

---

## Internal Structure of a Chip

### Pads

Pads are special metallic regions located around the boundary of the silicon die. They serve as communication points between the internal circuitry and the external package pins.

Pads are mainly used for:

- Input signals
- Output signals
- Clock connections
- Power supply connections
- Ground connections

Since pads directly interact with the outside world, they are designed to handle higher voltages and electrostatic discharge protection.

### Core

The central region enclosed by the pads is called the **core**. This is the most important section of the chip because it contains the actual digital logic responsible for computation and data processing.

The core includes:

- Standard cells
- Logic gates
- Arithmetic circuits
- Control units
- Memories
- Processor logic

The performance, power consumption, and area utilization of the chip mainly depend on the core design.

### Die

The complete silicon structure containing both the pads and the core is known as the **die**. The die is manufactured using semiconductor fabrication processes inside specialized factories called foundries.

---

## Foundries and Process Design Kits (PDKs)

A **foundry** is a semiconductor manufacturing facility where integrated circuits are fabricated on silicon wafers. Examples of semiconductor foundries include fabrication companies that manufacture chips for different design organizations.

To manufacture a chip correctly, designers require detailed information about the fabrication technology. This information is provided through a **Process Design Kit (PDK)**.

A PDK contains:

- Design rules
- Standard cell libraries
- Device models
- DRC and LVS rule files
- SPICE models
- Layer information

The **Sky130 PDK** is an open-source 130nm technology node that enables designers to perform real ASIC implementation using publicly available resources.

---

## Intellectual Property (IP) Blocks and Macros

Modern ASICs are extremely complex and are rarely designed completely from scratch. Designers reuse previously verified blocks called **IP blocks (Intellectual Property blocks)** to reduce development time and improve reliability.

Examples of IP blocks include:

- SRAM memories
- PLLs
- UART controllers
- SPI interfaces
- USB controllers
- Processor cores

Some IPs are process-dependent and are known as **Foundry IPs** because they are tightly linked to fabrication technology.

Digital reusable blocks are often referred to as **macros**. These macros help designers integrate large functionalities into System-on-Chip (SoC) architectures efficiently.

---

## Introduction to RISC-V Architecture

RISC-V is an open-source Instruction Set Architecture (ISA) developed to provide a flexible and license-free processor architecture. Unlike proprietary ISAs, RISC-V allows designers to customize and extend processor functionality according to application requirements.

The ISA defines:

- Supported instructions
- Register organization
- Memory access methods
- Arithmetic operations
- Control flow operations

RISC-V has become highly popular in academic research, processor development, and open-hardware communities because of its modular and open nature.

---

## From Software Applications to Hardware

A software program written in a high-level language such as C undergoes multiple transformation stages before it can execute on hardware.

### Software-to-Hardware Flow

1. The C program is compiled into RISC-V assembly instructions.
2. The assembler converts assembly instructions into binary machine code.
3. The processor hardware interprets and executes the binary instructions.
4. The processor itself is implemented using RTL design.
5. RTL is synthesized into logic gates.
6. The physical design flow converts the logic into a manufacturable chip layout.

This complete transformation creates a bridge between software applications and physical silicon implementation.

---

## RTL Design and Hardware Description Languages

RTL (Register Transfer Level) design describes hardware behavior using Hardware Description Languages (HDLs) such as Verilog or VHDL.

RTL design defines:

- Data movement
- Clock behavior
- Sequential logic
- Combinational logic
- Register operations

RTL acts as the foundation of digital hardware design because it represents the functional behavior of the circuit before physical implementation begins.

---

## OpenLANE ASIC Flow

OpenLANE is an automated open-source RTL-to-GDSII ASIC implementation flow built around the Sky130 PDK. It integrates multiple open-source EDA tools into a unified workflow.

### Major Stages of OpenLANE Flow

- RTL synthesis
- Floorplanning
- Power planning
- Placement
- Clock Tree Synthesis (CTS)
- Routing
- Timing analysis
- Physical verification
- GDSII generation

The flow converts a Verilog RTL design into a final physical layout that can be fabricated on silicon.

---

## Open-Source EDA Tools Used in the Flow

The OpenLANE ecosystem use several important open-source tools:
- **Yosys** → RTL synthesis
- **OpenROAD** → Physical design automation
- **Magic** → Layout visualization and DRC
- **Netgen** → LVS verification
- **TritonRoute** → Detailed routing

These tools collectively provide a complete ASIC implementation environment without requiring expensive commercial software licenses.

---

## Importance of Open-Source ASIC Design

The availability of open-source EDA tools and PDKs has significantly transformed VLSI education and research. Students and engineers can now learn real industrial ASIC flows without depending on proprietary resources.

Benefits include:

- Low-cost learning environment
- Industry-level practical exposure
- Better understanding of physical design
- Faster research and innovation
- Community-driven development

The combination of OpenLANE, RISC-V, and Sky130 represents a major advancement toward accessible and collaborative silicon development.
#Lab For picorv32a
```bash
cd /Desktop/work/tools/openlane_working_dir/openLane
./flow.tcl -interactive
package require openlane 9.0
```
![OpenLANE Start](images/openlane-start.png)
