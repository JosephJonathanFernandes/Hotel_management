# Hotel Management System

[![C/C++ CI](https://github.com/JosephJonathanFernandes/Hotel_management/actions/workflows/c-cpp.yml/badge.svg)](https://github.com/JosephJonathanFernandes/Hotel_management/actions/workflows/c-cpp.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A comprehensive hotel management system built in C that handles customer records, room bookings, billing, and feedback management.

## 📋 Table of Contents

- [Features](#features)
- [Room Types](#room-types)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

## ✨ Features

- **Customer Management**
  - Add new customer records
  - Update customer information (name, age, address, customer ID)
  - Display customer details
  - Unique customer file creation

- **Room Booking System**
  - Four different room types with varying capacities
  - Real-time room availability tracking
  - Multiple room booking support
  - Automatic room allocation based on party size

- **Billing System**
  - Calculate bills based on room type and duration
  - Include additional services (food, beverages, transportation)
  - Automatic tax calculation (40% service charge)
  - Bill generation and storage

- **Customer Feedback**
  - Collect and store customer feedback
  - Append feedback to customer records

- **Check-out Management**
  - Calculate final bills
  - Update room availability
  - Generate itemized receipts

## 🏨 Room Types

| Room Type | Capacity | Price per Night | Features |
|-----------|----------|-----------------|----------|
| **Deluxe** | 10 people | ₹7,000 | Spacious rooms with premium amenities |
| **Standard** | 2 people | ₹6,000 | Comfortable rooms with essential facilities |
| **Suite** | 1 person | ₹9,000 | Luxury suites with exclusive services |
| **Family** | 5 people | ₹8,000 | Family-friendly rooms with extra space |

## 🔧 Prerequisites

- GCC Compiler (MinGW for Windows, GCC for Linux/Mac)
- C Standard Library
- Make (optional, for using Makefile)

## 💻 Installation

### Windows

```bash
# Clone the repository
git clone https://github.com/JosephJonathanFernandes/Hotel_management.git
cd Hotel_management

# Compile the program
gcc -o hotel_management HotelManagement.c -I.

# Run the program
hotel_management.exe
```

### Linux/Mac

```bash
# Clone the repository
git clone https://github.com/JosephJonathanFernandes/Hotel_management.git
cd Hotel_management

# Compile the program
gcc -o hotel_management HotelManagement.c -I.

# Run the program
./hotel_management
```

### Using Makefile

```bash
# Compile
make

# Run
make run

# Clean build artifacts
make clean
```

## 🚀 Usage

1. **Start the Program**: Run the compiled executable
2. **Main Menu**: Choose from the following options:
   - `(1)` - Add new customer record
   - `(2)` - Update customer information
   - `(3)` - Display customer record
   - `(4)` - Check-out and billing
   - `(5)` - Customer feedback
   - `(6)` - Exit program

### Adding a Customer

1. Select option 1 from the main menu
2. Enter customer details:
   - Name (must be unique)
   - Age
   - Address
   - Customer ID
   - Number of people
3. Select room type(s) based on party size
4. System will automatically create a customer file

### Updating Customer Information

1. Select option 2 from the main menu
2. Enter the customer filename
3. Choose what to update (name, age, address, or customer ID)
4. Enter the new information

### Check-out Process

1. Select option 4 from the main menu
2. Enter the customer filename
3. For each room:
   - Enter services cost
   - Enter number of days/nights stayed
4. System calculates and displays total bill with taxes

## 📁 Project Structure

```
Hotel_management/
├── HotelManagement.c      # Main program file
├── task.h                 # Header file with function implementations
├── README.md              # Project documentation
├── LICENSE                # MIT License
├── CONTRIBUTING.md        # Contribution guidelines
├── CODE_OF_CONDUCT.md     # Community standards
├── SECURITY.md            # Security policy
├── Makefile               # Build automation
├── .gitignore             # Git ignore rules
├── .gitattributes         # Git attributes
└── .github/
    └── workflows/
        └── c-cpp.yml      # CI/CD pipeline
```

## 🔒 Security

This project follows security best practices:
- No hardcoded credentials
- Input validation and buffer overflow protection
- Secure file handling

For reporting vulnerabilities, please see [SECURITY.md](SECURITY.md).

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Joseph Jonathan Fernandes**
- GitHub: [@JosephJonathanFernandes](https://github.com/JosephJonathanFernandes)

## 🙏 Acknowledgments

- Built with C programming language
- Uses standard C libraries for file handling and I/O operations
- Inspired by real-world hotel management requirements

## 📞 Support

If you encounter any issues or have questions, please [open an issue](https://github.com/JosephJonathanFernandes/Hotel_management/issues) on GitHub.

---

⭐ Star this repository if you find it helpful!
