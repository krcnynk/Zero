![[../z_fluff/obamna.gif]]

Imperative programming
describing _how_ a program operates, step by step.
```c
#include <iostream>
int main() {
    int a, b;
    std::cin >> a >> b;
    std::cout << "Sum: " << a + b << std::endl;
    return 0;
}

```
Procedural programming
derivation of imperative programming, adding to it the feature of functions
```c
#include <iostream>
void readInput(int &a, int &b) {
    std::cout << "Enter two numbers: ";
    std::cin >> a >> b;
}
int calculateSum(int a, int b) {
    return a + b;
}
void displayResult(int sum) {
    std::cout << "Sum: " << sum << std::endl;
}
int main() {
    int a, b;
    readInput(a, b);
    int sum = calculateSum(a, b);
    displayResult(sum);
    return 0;
}

```
Functional programming
In functional programming, functions are treated as **first-class citizens**, meaning that they can be assigned to variables, passed as arguments, and returned from other functions. (also like a variable disappear)
```c
#include <iostream>
#include <functional>
// Pure function to calculate the sum of two integers
int calculateSum(int a, int b) {
    return a + b;
}
// Function to read input from the user
std::pair<int, int> readInput() {
    int a, b;
    std::cout << "Enter two numbers: ";
    std::cin >> a >> b;
    return {a, b};
}
// Function to display the result
void displayResult(int sum) {
    std::cout << "Sum: " << sum << std::endl;
}
int main() {
    auto inputs = readInput();
    int sum = calculateSum(inputs.first, inputs.second);
    displayResult(sum);
    return 0;
}

```
Declarative programming
describing _what_ the program should accomplish rather than _how_ to accomplish it
```c
#include <iostream>
#include <vector>
#include <numeric>
int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};

    // Using std::accumulate to declaratively sum the elements
    int sum = std::accumulate(numbers.begin(), numbers.end(), 0);

    std::cout << "Sum: " << sum << std::endl;
    return 0;
}

```
Object-oriented programming
objects react with each other, they have attributes and methods
```c
#include <iostream>
// Define a Calculator class
class Calculator {
public:
    // Constructor
    Calculator(int a, int b) : num1(a), num2(b) {}

    // Method to calculate the sum
    int calculateSum() const {
        return num1 + num2;
    }
private:
    int num1, num2;
};
int main() {
    int a, b;

    // Read input from the user
    std::cout << "Enter two numbers: ";
    std::cin >> a >> b;

    // Create a Calculator object
    Calculator calc(a, b);

    // Calculate and display the sum
    std::cout << "Sum: " << calc.calculateSum() << std::endl;

    return 0;
}

```
