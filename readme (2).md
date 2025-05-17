# Stock Editor Application

A comprehensive inventory management system built with Qt/C++ that helps you manage product inventory with barcode scanning capability.

[Application Screenshot](stock editor ui.png)

## Features

- **Inventory Management**: Add, edit, and remove products with full details
- **Barcode Integration**: Use standard 13-digit barcodes for product identification
- **Stock Tracking**: Monitor and update stock levels of all products
- **Price Management**: Set and modify product prices with validation
- **Data Persistence**: Save and load inventory data from files
- **User-Friendly Interface**: Clean interface with intuitive controls and icons

## Requirements

- Qt 5.12 or higher
- C++11 compatible compiler
- Qt Creator 4.8 or higher (recommended for development)

## Installation

### Building from Source

1. Clone the repository:
```bash
git clone https://github.com/yourusername/stock-editor.git
cd stock-editor
```

2. Open the project in Qt Creator:
```bash
qtcreator stock-editor.pro
```

3. Configure the project for your kit and build

### Binary Installation

Pre-built binaries are available for:
- Windows 10/11
- macOS 10.14+
- Ubuntu 20.04+

Download the latest release from the [Releases](https://github.com/yourusername/stock-editor/releases) page.

## Usage

### Managing Inventory

#### Opening an Inventory File
1. Click the "Open" button in the toolbar or select "File" > "Open" from the menu
2. Select your inventory file (tab-delimited text format)
3. The application will load all items into the view

#### Adding New Items
1. Click the "Add" button in the toolbar or select "Edit" > "Add" from the menu
2. Enter the product details in the dialog:
   - Barcode (must be exactly 13 digits)
   - Description (product name)
   - Stock amount (quantity in inventory)
   - Price (in your local currency)
3. Click "OK" to add the item to inventory

#### Editing Items
1. Click the "Change" button in the toolbar or select "Edit" > "Change" from the menu
2. Enter the barcode of the item you wish to modify
3. Update the item details (description, stock, price)
4. Click "OK" to save changes

#### Removing Items
1. Click the "Remove" button in the toolbar or select "Edit" > "Remove" from the menu
2. Enter the barcode of the item you wish to delete
3. Confirm the deletion when prompted

#### Saving Inventory
1. Click the "Save" button in the toolbar or select "File" > "Save" from the menu
2. Select the file location to save your inventory data

### Data Format

The application uses a tab-delimited text file format with the following structure:
```
Barcode     Description     Stock     Price
6000112500187     Milk 1L     50     15.99
...
```

## Project Structure

The application consists of several key components:

- `MainWindow`: Main application window with toolbar and menu options for inventory management
- `Item`: Class representing a product with barcode, description, stock level, and price
- `ItemList`: Container class that manages a collection of items with lookup functionality
- `ChangeItemDialog`: Dialog used for both adding new items and editing existing ones

### Key Classes

#### MainWindow
The central class that coordinates the UI and handles user interactions. It contains:
- File operations (open/save)
- Item operations (add/change/remove)
- Display of inventory in a text view

#### Item
Represents a single inventory item with:
- 13-digit barcode validation
- Product description
- Stock level tracking
- Price information

#### ItemList
Manages the collection of inventory items:
- Stores items in a QMap with barcode as the key
- Provides search functionality
- Handles file I/O operations

#### ChangeItemDialog
Dialog for item input and validation:
- Input fields for all item properties
- Input validation logic
- Can be used for both adding and editing items

## Input Validation

The application includes validation to ensure data integrity:

- **Barcode**: Must be exactly 13 digits
- **Description**: Cannot be empty
- **Stock**: Must be between 0 and 2000
- **Price**: Must be between 0 and 10,000

## Customization

### Icon Customization

To change the icons used in the application, modify the icon paths in `mainwindow.cpp`:

```cpp
QIcon icon1("path/to/your/icon.png");
exitAction->setIcon(icon1);
```

## Data File Format

The application reads and writes tab-delimited text files with the following format:
```
barcode<tab>description<tab>stock<tab>price
```

For example:
```
6000112500187	Milk 1L	50	15.99
6001007166450	Bread Brown	45	18.50
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Planned Features

- Barcode scanner integration
- Image support for products
- Advanced search capabilities
- Export to CSV/Excel
- Multiple currency support
- User authentication

## Acknowledgments

- Icons from [source/attribution]
- Qt framework for the cross-platform UI
- Inspiration from professional inventory management systems
