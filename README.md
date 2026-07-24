# AI-SOC
 A complete open-source AI System-on-Chip implementation covering the complete ASIC design flow from RTL development to GDSII generation.  The project demonstrates an industrial RTL-to-GDSII flow using modern open-source EDA tools.

## Objectives

- Design a RISC-V based AI SoC
- Develop reusable RTL modules in Verilog
- Verify the complete design using UVM
- Perform synthesis using Yosys
- Execute physical implementation with OpenLane/OpenROAD
- Generate final GDSII layout
- Verify layout using KLayout DRC/LVS

## Tools

| Stage | Tool |
|--------|------|
| RTL Design | Verilog |
| Functional Verification | UVM |
| Logic Synthesis | Yosys |
| Physical Design | OpenLane |
| Place & Route | OpenROAD |
| Layout Verification | KLayout |

## Repo Structure
```
├── README.md
├── LICENSE
├── .gitignore
│
├── docs/
│   ├── architecture.md
│   ├── project_plan.md
│   ├── verification_plan.md
│   ├── physical_design_flow.md
│   ├── timing_closure.md
│   ├── floorplan.md
│   ├── power_analysis.md
│   ├── routing.md
│   └── final_report.md
│
├── specs/
│   ├── soc_specification.pdf
│   ├── memory_map.md
│   ├── instruction_set.md
│   └── interfaces.md
│
├── rtl/
│   ├── top/
│   │   └── ai_soc_top.v
│   │
│   ├── cpu/
│   │   ├── riscv_core.v
│   │   ├── decoder.v
│   │   ├── alu.v
│   │   ├── register_file.v
│   │   ├── csr.v
│   │   ├── controller.v
│   │   └── pipeline/
│   │
│   ├── accelerator/
│   │   ├── mac_array.v
│   │   ├── systolic_array.v
│   │   ├── activation.v
│   │   ├── pooling.v
│   │   ├── dma.v
│   │   └── controller.v
│   │
│   ├── memory/
│   │   ├── instruction_memory.v
│   │   ├── data_memory.v
│   │   ├── scratchpad.v
│   │   └── cache/
│   │
│   ├── bus/
│   │   ├── axi_interconnect.v
│   │   ├── arbiter.v
│   │   └── decoder.v
│   │
│   ├── peripherals/
│   │   ├── gpio.v
│   │   ├── uart.v
│   │   ├── spi.v
│   │   ├── i2c.v
│   │   ├── timer.v
│   │   └── pwm.v
│   │
│   └── common/
│       ├── defines.vh
│       └── parameters.vh
│
├── tb/
│   ├── interfaces/
│   ├── agents/
│   ├── sequences/
│   ├── scoreboard/
│   ├── coverage/
│   ├── env/
│   ├── tests/
│   ├── pkg/
│   └── top/
│
├── verification/
│   ├── assertions/
│   ├── functional_coverage/
│   ├── formal/
│   ├── reports/
│   └── regression/
│
├── constraints/
│   ├── pin_order.cfg
│   ├── floorplan.tcl
│   ├── pdn.tcl
│   ├── placement.tcl
│   ├── routing.tcl
│   ├── timing.sdc
│   └── clock.sdc
│
├── openlane/
│   ├── config.json
│   ├── scripts/
│   └── runs/
│
├── openroad/
│   ├── scripts/
│   ├── reports/
│   └── logs/
│
├── klayout/
│   ├── drc/
│   ├── lvs/
│   ├── screenshots/
│   └── scripts/
│
├── synthesis/
│   ├── yosys/
│   ├── netlists/
│   ├── reports/
│   └── scripts/
│
├── gds/
│   ├── final/
│   ├── reports/
│   └── screenshots/
│
├── simulation/
│   ├── filelists/
│   ├── scripts/
│   ├── waves/
│   └── logs/
│
├── software/
│   ├── baremetal/
│   ├── firmware/
│   ├── linker/
│   └── tests/
│
├── scripts/
│   ├── build.sh
│   ├── synth.sh
│   ├── verify.sh
│   ├── openlane.sh
│   ├── openroad.sh
│   ├── klayout.sh
│   ├── clean.sh
│   └── regress.sh
│
├── results/
│   ├── synthesis/
│   ├── verification/
│   ├── timing/
│   ├── power/
│   ├── area/
│   └── gdsii/
│
└── images/
    ├── architecture.png
    ├── floorplan.png
    ├── layout.png
    └── chip_render.png

```

## Project Architecture

```
                    +----------------------+
                    |      RISC-V CPU      |
                    +----------+-----------+
                               |
                    +----------+-----------+
                    |    AXI Interconnect  |
                    +----------+-----------+
                               |
      -------------------------------------------------------
      |              |             |            |            |
+-----------+  +-------------+ +--------+ +---------+ +----------+
| AI Engine |  | SRAM/Cache  | | UART   | | SPI/I2C | | GPIO/PWM |
+-----------+  +-------------+ +--------+ +---------+ +----------+
```

---

## Design Flow

```
RTL Design
     │
     ▼
UVM Verification
     │
     ▼
Synthesis (Yosys)
     │
     ▼
Floorplanning
     │
     ▼
Power Planning
     │
     ▼
Placement
     │
     ▼
Clock Tree Synthesis
     │
     ▼
Routing
     │
     ▼
Timing Closure
     │
     ▼
DRC / LVS
     │
     ▼
GDSII
```

---

# AI SoC (RTL → GDSII)

A complete open-source AI System-on-Chip implementation covering the complete ASIC design flow from RTL development to GDSII generation.

The project demonstrates an industrial RTL-to-GDSII flow using modern open-source EDA tools.

---

## Objectives

- Design a RISC-V based AI SoC
- Develop reusable RTL modules in Verilog
- Verify the complete design using UVM
- Perform synthesis using Yosys
- Execute physical implementation with OpenLane/OpenROAD
- Generate final GDSII layout
- Verify layout using KLayout DRC/LVS

---

## Toolchain

| Stage | Tool |
|--------|------|
| RTL Design | Verilog |
| Functional Verification | UVM |
| Logic Synthesis | Yosys |
| Physical Design | OpenLane |
| Place & Route | OpenROAD |
| Layout Verification | KLayout |

---

# Project Architecture

```
                    +----------------------+
                    |      RISC-V CPU      |
                    +----------+-----------+
                               |
                    +----------+-----------+
                    |    AXI Interconnect  |
                    +----------+-----------+
                               |
      -------------------------------------------------------
      |              |             |            |            |
+-----------+  +-------------+ +--------+ +---------+ +----------+
| AI Engine |  | SRAM/Cache  | | UART   | | SPI/I2C | | GPIO/PWM |
+-----------+  +-------------+ +--------+ +---------+ +----------+
```

---

# Design Flow

```
RTL Design
     │
     ▼
UVM Verification
     │
     ▼
Synthesis (Yosys)
     │
     ▼
Floorplanning
     │
     ▼
Power Planning
     │
     ▼
Placement
     │
     ▼
Clock Tree Synthesis
     │
     ▼
Routing
     │
     ▼
Timing Closure
     │
     ▼
DRC / LVS
     │
     ▼
GDSII
```

---

# Repository Structure

```
docs/            Documentation
rtl/             Verilog source files
tb/              UVM Verification Environment
verification/    Assertions & Coverage
constraints/     OpenLane constraints
openlane/        OpenLane configuration
openroad/        OpenROAD scripts
klayout/         DRC/LVS
simulation/      RTL simulations
software/        Firmware & Bare-metal tests
gds/             Final layout
results/         Reports
```

---

# Verification

- UVM Testbench
- Functional Coverage
- Scoreboard
- Assertions
- Regression Testing

---

# Physical Design Flow

- RTL Elaboration
- Logic Synthesis
- Floorplanning
- Power Distribution Network
- Global Placement
- Detailed Placement
- Clock Tree Synthesis
- Global Routing
- Detailed Routing
- Static Timing Analysis
- DRC
- LVS
- GDSII Export
