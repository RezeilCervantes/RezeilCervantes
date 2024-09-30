- 👋 Hi, I’m @RezeilCervantes
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
RezeilCervantes/RezeilCervantes is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

import 'dart:io';

void main() {
  List<String> inventory = ['apple', 'banana', 'carrot', 'dates'];

  while (true) {
    print(' ');
    print('Please select an operation to do:');
    print('[1] Add New Product in the inventory');
    print('[2] Remove a Product from the inventory');
    print('[3] Display the total number of items in the inventory');
    print('[4] Search for an item and display if it is available or not');
    print('[5] Sort the inventory list alphabetically');
    print('[6] Exit');

    stdout.write('You have selected: ');
    String? option = stdin.readLineSync();

    switch (option) {
      case '1':
        stdout.write('Please enter a product you want to add on the list:');
        String? newProduct = stdin.readLineSync();
        if (newProduct != null && newProduct.isNotEmpty) {
          inventory.add(newProduct);
          print('The updated product list are as follows: $inventory');
        }
        break;

      case '2':
        stdout.write('Please enter a product you want to remove on the list:');
        String? removeProduct = stdin.readLineSync();
        if (removeProduct != null && inventory.contains(removeProduct)) {
          inventory.remove(removeProduct);
          print('Updated Inventory after removal: $inventory');
        } else {
          print('$removeProduct not found in the inventory.');
        }
        break;

      case '3':
        print('Total number of items in inventory: ${inventory.length}');
        break;

      case '4':
        stdout.write('Please enter a product you want to search on the list:');
        String? searchProduct = stdin.readLineSync();
        if (searchProduct != null && inventory.contains(searchProduct)) {
          print('$searchProduct is available in the inventory.');
        } else {
          print('$searchProduct is not available in the inventory.');
        }
        break;

      case '5':
        inventory.sort();
        print('Sorted Inventory: $inventory');
        break;

      case '6':
        print('Exiting the program');
        return;

      default:
        print('Invalid choice. Please select a valid option.');
    }
  }
}




class Calculator {
  // Properties
  double _number1;
  double _number2;

  // Constructor
  Calculator(this._number1, this._number2);

  // Getters
  double get number1 => _number1;
  double get number2 => _number2;

  // Setters
  set number1(double value) {
    _number1 = value;
  }

  set number2(double value) {
    _number2 = value;
  }

  // Methods
  double add() {
    return _number1 + _number2;
  }

  double subtract() {
    return _number1 - _number2;
  }

  double multiply() {
    return _number1 * _number2;
  }

  double divide() {
    if (_number2 == 0) {
      print("Error: Division by zero is not allowed.");
      return double.nan; // Return NaN for division by zero
    } else {
      return _number1 / _number2;
    }
  }
}

void main() {
  // Create an instance of the Calculator class
  Calculator calc = Calculator(10, 5);

  // Set values using setters
  calc.number1 = 15;
  calc.number2 = 3;

  // Call methods and print the results
  print("Number 1: ${calc.number1}");
  print("Number 2: ${calc.number2}");

  print("Addition: ${calc.add()}");
  print("Subtraction: ${calc.subtract()}");
  print("Multiplication: ${calc.multiply()}");
  print("Division: ${calc.divide()}");

  // Test division by zero
  calc.number2 = 0;
  print("Division with zero: ${calc.divide()}");
}
