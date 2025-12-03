# Hotel Management System - Documentation

## Table of Contents

1. [System Overview](#system-overview)
2. [Architecture](#architecture)
3. [Data Structures](#data-structures)
4. [Functions](#functions)
5. [File Format](#file-format)
6. [Error Handling](#error-handling)
7. [Security Considerations](#security-considerations)

## System Overview

The Hotel Management System is a console-based application written in C that manages hotel operations including customer registration, room bookings, billing, and feedback collection.

### Key Features

- **Multi-room booking**: Customers can book multiple rooms of different types
- **Dynamic room allocation**: System tracks available rooms in real-time
- **Flexible billing**: Calculates bills based on room type, duration, and additional services
- **Data persistence**: Customer data stored in individual text files
- **Update capabilities**: Modify customer information after registration

## Architecture

### Program Flow

```
Start
  ↓
Display Menu
  ↓
User Selection
  ↓
┌─────────────────────────────────────┐
│ 1. Add Customer → Create File       │
│ 2. Update → Modify File             │
│ 3. Display → Read File              │
│ 4. Checkout → Calculate Bill        │
│ 5. Feedback → Append to File        │
│ 6. Exit                             │
└─────────────────────────────────────┘
  ↓
Loop until Exit
```

### File Structure

```
Hotel_management/
├── HotelManagement.c      # Main program entry point
├── task.h                 # Function implementations
├── roomtype.txt           # Room availability data
└── [customer_files].txt   # Individual customer records
```

## Data Structures

### Customer Structure

```c
struct customer {
    char cname[50];        // Customer name
    int cage;              // Customer age
    char caddress[100];    // Customer address
    char cten[11];         // Customer ID/tenant number
    int cpnum;             // Number of people
    int Deluxe;            // Number of Deluxe rooms booked
    int Standard;          // Number of Standard rooms booked
    int Family;            // Number of Family rooms booked
    int Suite;             // Number of Suite rooms booked
};
```

### Room Types

| Type     | Capacity | Price (₹/night) |
|----------|----------|-----------------|
| Deluxe   | 10       | 7,000          |
| Standard | 2        | 6,000          |
| Suite    | 1        | 9,000          |
| Family   | 5        | 8,000          |

## Functions

### Core Functions

#### `int fileExists(const char* filename)`
- **Purpose**: Check if a file exists
- **Parameters**: `filename` - Name of file to check
- **Returns**: `-1` if file doesn't exist, `0` if exists
- **Usage**: Validates file existence before operations

#### `void formatFileName(char* fileName)`
- **Purpose**: Format customer name into valid filename
- **Parameters**: `fileName` - Name to format
- **Actions**: 
  - Replaces spaces with underscores
  - Appends `.txt` extension
- **Example**: "John Doe" → "John_Doe.txt"

#### `void addcust(FILE *fp)`
- **Purpose**: Add new customer record
- **Process**:
  1. Validate unique customer name
  2. Collect customer information
  3. Allocate rooms based on party size
  4. Update room availability
  5. Create customer file
- **File Operations**: Creates new customer file, updates `roomtype.txt`

#### `void update(FILE *fp)`
- **Purpose**: Update existing customer information
- **Capabilities**:
  - Modify name
  - Update age
  - Change address
  - Update customer ID
- **Process**:
  1. Read existing file
  2. Create temporary file with updates
  3. Replace original file

#### `void display(FILE *fp)`
- **Purpose**: Display customer record
- **Parameters**: `fp` - File pointer
- **Usage**: Shows complete customer information

#### `void checkout(FILE *fp)`
- **Purpose**: Process customer checkout and generate bill
- **Calculations**:
  - Base cost = (Number of nights × Room rate)
  - Service charges (user input)
  - Tax = 40% of total
  - Final bill = Base + Services + Tax
- **Actions**: Updates room availability, appends bill to customer file

#### `void custfeed(FILE *fp)`
- **Purpose**: Collect and store customer feedback
- **Input**: Multi-line text input (EOF to terminate)
- **Storage**: Appends feedback to customer file

## File Format

### roomtype.txt Format

```
Deluxe:10
Standard:15
Family:8
Suite:5
```

### Customer File Format

```
NAME:John Doe
AGE:35
ADDRESS:123 Main St, City
CUST_ID:C12345
NUMBER_OF_PEOPLE:4
DELUXE:0
STANDARD:0
FAMILY:1
SUITE:0
CUSTOMER FEEDBACK:[feedback text]
TOTAL_BILL: Rs 45600.00/-
```

## Error Handling

### Common Scenarios

1. **File Not Found**
   - Check: File existence validation
   - Action: Display error message, return to menu

2. **Invalid Input**
   - Check: Input validation
   - Action: Prompt user to re-enter

3. **Room Unavailability**
   - Check: Compare requested capacity with available rooms
   - Action: Prompt user to select different room type

4. **Duplicate Customer Name**
   - Check: File existence check
   - Action: Request name modification

### Memory Management

- Dynamic memory allocated for customer structure
- Always freed after use
- NULL pointer checks before dereferencing

## Security Considerations

### Input Validation

- **Buffer Overflow Protection**: Fixed-size buffers with bounds checking
- **Format Specifiers**: Limited input length in `scanf`
  ```c
  scanf(" %49[^\n]", c->cname);  // Max 49 chars + null terminator
  ```

### File Safety

- **Error Checking**: All file operations checked for success
- **File Closure**: Files properly closed after operations
- **Atomic Updates**: Temporary file technique for safe updates

### Data Integrity

- **Unique Identifiers**: Customer name uniqueness enforced
- **Room Tracking**: Consistent room availability updates
- **Transactional**: File updates completed or rolled back

## Usage Examples

### Adding a Customer

```
1. Select option (1) from menu
2. Enter customer name: "John Smith"
3. Enter age: 30
4. Enter address: "123 Oak Street"
5. Enter customer ID: "C001"
6. Enter number of people: 3
7. Select room type: Family (4)
```

### Checking Out

```
1. Select option (4) from menu
2. Enter filename: "John_Smith.txt"
3. For each room:
   - Enter service costs: 2000
   - Enter nights stayed: 3
4. System calculates and displays total bill
5. Bill appended to customer file
```

## Best Practices

### For Users

1. **Unique Names**: Ensure customer names are unique
2. **Backup Data**: Regularly backup customer files
3. **Validate Input**: Double-check entered information
4. **Room Planning**: Plan room allocation before booking

### For Developers

1. **Error Handling**: Check all return values
2. **Memory Management**: Free allocated memory
3. **Input Validation**: Validate all user input
4. **Documentation**: Comment complex logic
5. **Testing**: Test edge cases and error conditions

## Troubleshooting

### Common Issues

**Problem**: "File not found" error
- **Solution**: Ensure filename includes underscores and `.txt` extension

**Problem**: Room allocation fails
- **Solution**: Check `roomtype.txt` for available rooms

**Problem**: Update operation fails
- **Solution**: Verify file permissions and disk space

## Future Enhancements

Potential improvements:
- Database integration for better data management
- Encryption for sensitive customer data
- User authentication system
- Web-based interface
- Reporting and analytics
- Booking history and statistics
- Email notifications
- Payment gateway integration

---

**Last Updated**: December 3, 2025
