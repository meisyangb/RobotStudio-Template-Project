# RobotStudio Template Project

[![GitHub](https://img.shields.io/badge/GitHub-RobotStudio--PickPlace-blue)](https://github.com/meisyangb/RobotStudio-PickPlace)

## Overview

This is an ABB RobotStudio Pick and Place project template. It provides a complete foundation for developing robotic pick and place applications using ABB industrial robots.

## Project Structure

```
abbgithub/
├── ABB_Pick&Place_v1.0.rssln          # RobotStudio Solution File
├── Stations/
│   └── ABB_Pick&Place_v1.0.rsstn      # RobotStudio Station File
├── Libraries/
│   └── VentosaTool.rslib              # Custom Tool Library (Vacuum Gripper)
├── Backups/
│   └── Controller_Pick_Place_1/       # Controller Backup Files
│       ├── RAPID/
│       │   └── TASK1/
│       │       └── PROGMOD/
│       │           ├── CalibData.mod  # Calibration Data Module
│       │           └── Module1.mod    # Main Program Module
│       └── SYSPAR/                    # System Parameters
│           ├── EIO.cfg                # I/O Configuration
│           ├── MOC.cfg                # Motion Configuration
│           ├── SIO.cfg                # Serial I/O Configuration
│           └── SYS.cfg                # System Configuration
└── Systems/
    └── Controller_Pick_Place_1/       # Virtual Controller System
```

## Features

- 🤖 **Complete Pick and Place Solution**: Ready-to-use template for pick and place operations
- 🛠️ **Custom Tool Library**: Includes vacuum gripper (VentosaTool) configuration
- 📋 **RAPID Programs**: Pre-configured RAPID modules with calibration data
- ⚙️ **System Configurations**: Complete I/O, motion, and system parameter setups
- 💾 **Backup Support**: Full controller backup for easy restoration

## Requirements

- ABB RobotStudio 2020 or later
- RobotWare 6.x or later
- Virtual Controller license (for simulation)

## Quick Start

1. **Clone the Repository**
   ```bash
   git clone https://github.com/meisyangb/RobotStudio-PickPlace.git
   ```

2. **Open in RobotStudio**
   - Open RobotStudio
   - Select `File` > `Open` > `Solution`
   - Navigate to `abbgithub/ABB_Pick&Place_v1.0.rssln`

3. **Load the Station**
   - The station file `ABB_Pick&Place_v1.0.rsstn` will load automatically
   - Virtual controller will start with pre-configured settings

4. **Run the Program**
   - Switch to `Auto` mode
   - Press the `Play` button to start the simulation

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests.

## Push Restrictions

Please read [.github/PUSH_LIMITS.md](.github/PUSH_LIMITS.md) for push requirements and limitations.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

For questions or support, please open an issue on GitHub.

---

**Note**: This is a template project. Please customize it according to your specific application requirements.
