# Minimal_LTC9111

## Overview

This repository contains a minimal KiCad design project for the Analog Devices LTC9111, an industrial Single-Pair Power over Ethernet (SPoE) Powered Device (PD) controller. The project is compliant with the IEEE 802.3cg standard and is designed for use in building and factory automation, security systems, and traffic control systems.

## Disclaimer

> [!NOTE]
> This project is provided "as is" and without any warranty, express or implied. For more details, please see the [LICENSE](LICENSE) file.

## About the LTC9111

The LTC9111 from Analog Devices is an industrial Single-Pair Power over Ethernet (SPoE) Powered Device (PD) controller. It is compliant with the IEEE 802.3cg standard and is designed for use in building and factory automation, security systems, and traffic control systems.

Key features include:

- **Wide Input Voltage Range:** The device operates with an input voltage from 2.3V to 60V.
- **Serial Communication Classification Protocol (SCCP):** This ensures that full operating voltage is only applied by the Power Sourcing Equipment (PSE) when a valid PD is connected.
- **Polarity Correction:** It drives low-side bridge MOSFETs for polarity correction.
- **Integrated Standby Regulator:** The LTC9111 includes an integrated 3.5V standby regulator.
- **Low Current Consumption:** It has a maximum current of 150µA during classification.
- **External MOSFET Drive:** It drives external N-channel MOSFETs for classification and to isolate output capacitance.
- **Package Options:** The LTC9111 is available in 12-pin MSOP and DFN 4mm × 3mm packages.
- **Temperature Range:** It has an operating junction temperature range of -40°C to +150°C.

## Project Structure

```
minimal_ltc9111/
├── minimal_ltc9111.kicad_sch       # Main schematic file
├── minimal_ltc9111.kicad_pcb       # PCB layout file
├── minimal_ltc9111.kicad_pro       # Project configuration file
├── fp-lib-table                     # Footprint library table
├── sym-lib-table                    # Symbol library table
├── project_jobs_set.kicad_jobset    # Project job settings
├── ibom.config.ini                  # Interactive BOM configuration
├── docs/                            # Documentation files
│   ├── pictures/                    # Images and photos
│   ├── schematics/                  # Schematic PDF exports
│   └── 3d_models/                   # 3D model files
└── KiCAD_Symbols_Generator/         # Submodule for symbol generation from CSV data
```

## Project Features

This design provides a minimal implementation of the LTC9111 with the following features:

- **Power Supply:**
  - VIN: +3.3V
- **Channel Configuration:**
  - Basic protection circuits for the Ethernet twisted pair.
- **Bill of Materials (BOM):**
  - Interactive HTML BOM (`ibom.html`) for easy component identification and sourcing.
- **Libraries:**
  - Comprehensive symbol and footprint libraries integrated as a submodule.
- **3D Model:**
  - Includes a 3D model of the board for better visualization.

## Getting Started

### Prerequisites

- [KiCad EDA](https://www.kicad.org/) version 9.0 or later installed on your system
- Git (for cloning the repository and submodule management)

### Opening the Project

1. **Clone the repository** (including submodules):
   ```bash
   git clone --recursive https://github.com/ionutms/Minimal_LTC9111.git
   ```
   
   If you've already cloned the repository without submodules, initialize them with:
   ```bash
   git submodule init
   git submodule update
   ```

2. **Open the project in KiCad**:
   - Launch KiCad
   - Click "Open Existing Project"
   - Navigate to the cloned repository folder
   - Select the `minimal_ltc9111.kicad_pro` file

3. **Explore the design**:
   - Open the schematic editor to view the circuit design
   - Open the PCB editor to view the board layout
   - Review the symbol and footprint libraries used in the design

### Project Files

- **Main schematic**: `minimal_ltc9111.kicad_sch` - Contains the primary circuit design with the LTC9111 and support components
- **PCB layout**: `minimal_ltc9111.kicad_pcb` - Physical board design file with proper component placement
- **Project configuration**: `minimal_ltc9111.kicad_pro` - KiCad project settings

## Dependencies

This project has the following dependencies:

### 1. KiCAD Symbols Generator

This repository uses [KiCAD_Symbols_Generator](https://github.com/ionutms/KiCAD_Symbols_Generator) as a submodule for custom symbol generation.

To initialize the submodule after cloning this repository:

```bash
git submodule update --init --recursive
```

### 2. 3D Models

This project requires the [3D_Models_Vault](https://github.com/ionutms/3D_Models_Vault) repository for 3D models.

#### Setup for KiCAD 9:

1. Clone the 3D models repository:
   ```bash
   git clone https://github.com/ionutms/3D_Models_Vault.git
   ```

2. In KiCAD 9, add an environment variable:
   - Variable name: `KICAD9_3D_MODELS_VAULT`
   - Variable value: Full path to where you cloned the 3D_Models_Vault repository

## Usage

After setting up the dependencies, open the project in KiCAD 9 to access all features including the 3D models.

## Symbol Generator Submodule

This project includes the KiCAD_Symbols_Generator as a submodule, which provides tools for generating KiCad symbols from CSV data files. For more information on using this tool, see the [KiCAD_Symbols_Generator documentation](minimal_ltc9111/KiCAD_Symbols_Generator/README.md).

## Documentation

The `docs` folder contains:
- Schematic PDF exports
- Images and photos of the design
- 3D model files (GLB and WRL formats)

## Visuals

The following images showcase the PCB design from different perspectives:

![Top View](minimal_ltc9111/docs/pictures/2_minimal_ltc9111_top.png)
*Top View of the PCB*

![Side View](minimal_ltc9111/docs/pictures/1_minimal_ltc9111_side.png)
*Side View of the PCB*

![Bottom View](minimal_ltc9111/docs/pictures/3_minimal_ltc9111_bottom.png)
*Bottom View of the PCB*

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## References

- [LTC9111 Datasheet](https://www.analog.com/media/en/technical-documentation/data-sheets/LTC9111.pdf)
- [KiCad EDA](https://www.kicad.org/)
