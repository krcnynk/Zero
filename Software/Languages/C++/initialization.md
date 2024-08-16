Status: **Editing**

Tags:[[C++]]

# initialization
```
int x(10); // Direct Init
int y = 10; // Copy init
int z{10}; // Uniform init
int a; //Default init (built-in types are undefined, user defined default constructor)
int b{};// Value init (built-in set to zero, user defined default constructor)
std::vector<int> vec{1, 2, 3}; // List init
int arr[3] = {1, 2, 3}; // Aggregate init
int* ptr = new int(10); // Dynamic init
MyClass() : x(10) {} // Constructor init

auto add = []->int(int a,int b) { return a+b; }; 
int x = add(5,3); // Lambda init
```

# References