# Constructors and Destructors in C++

---

## Aim  

To study and implement the concepts of **constructors and destructors in C++**, including:  

- Default constructor  
- Parameterized constructor (inside and outside the class)  
- Copy constructor  
- Destructor  

---

## Tools Used  

- **VS Code** or any other **online C++ compiler**  

---

## Theory  

### 🔹 Default Constructor  

- A constructor that takes no parameters.  
- It provides default initialization or takes input during object creation.  

**Syntax:**  
```cpp
class ClassName {
public:
    ClassName() {
        // body of default constructor
    }
};
```

**Algorithm for the Program (Default constructor)**  

1. Start  
2. Define a student class with:  
   - Data members: roll_no, name, and fee.  
   - A default constructor to input values for name, roll_no, and fee.  
   - A display() function to show these values.  
3. Inside the constructor:  
   1. Prompt the user to enter the student’s name and read it.  
   2. Prompt the user to enter the student’s roll number and read it.  
   3. Prompt the user to enter the student’s fee and read it.  
4. In the main() function:  
   1. Create an object s of class student.  
      - When the object is created, the constructor is automatically executed to take the input.  
   2. Call the display() function of object s to show the student details.  
5. End  

---

### 🔹 Parameterized Constructor  

- A constructor that takes arguments to initialize objects with user-defined values.  

**Syntax:**  
```cpp
class ClassName {
public:
    ClassName(type1 arg1, type2 arg2, ...) {
        // body of parameterized constructor
    }
};
```

**Algorithm for the Program (Parameterized constructor)**  

1. Start  
2. Define a class construct with:  
   - Data members: dd (day), mm (month), yy (year).  
   - A parameterized constructor that takes three arguments (a, b, c) and assigns them to dd, mm, and yy.  
   - A member function display() to print the date in the format dd/mm/yy.  
3. In the main() function:  
   1. Declare three integer variables: d, m, y.  
   2. Prompt the user to enter today’s date.  
   3. Read values of d, m, and y from the user.  
   4. Create an object date of class construct and pass the values (d, m, y) to the constructor.  
   5. The constructor initializes the object with these values.  
   6. Call the display() function of the object date to print the date.  
4. End  

---

### 🔹 Copy Constructor  

- A constructor that initializes a new object as a copy of an existing object.  

**Syntax:**  
```cpp
class ClassName {
public:
    ClassName(const ClassName &obj) {
        // body of copy constructor
    }
};
```

**Algorithm (Copy constructor)**  

1. Start  
2. Define a class student with:  
   - Data members: name (string), age (integer).  
   - A parameterized constructor that assigns n to name and a to age.  
   - A copy constructor that takes a reference object s and copies its values into the current object.  
   - A function display() to print the values of name and age.  
3. In the main() function:  
   1. Create object s with values `"Barkha", 20`.  
   2. Call s.display() to show details of s.  
   3. Create another object copyC by passing s to the copy constructor.  
   4. The copy constructor copies name and age of s into copyC.  
   5. Print the message `"Copy Constructor called!"`.  
   6. Call copyC.display() to show the copied values.  
4. End  

---

### 🔹 Destructor  

- A special member function that is automatically invoked when an object goes out of scope.  
- Used for cleanup.  

**Syntax:**  
```cpp
class ClassName {
public:
    ~ClassName() {
        // body of destructor
    }
};
```

**Algorithm (Destructor)**  

1. Start  
2. Define a class Date with:  
   - Data members: d, m, year initialized with default values.  
   - A constructor Date() that prints `"Constructor called"` whenever an object is created.  
   - A destructor ~Date() that prints `"Destructor called"` whenever an object is destroyed.  
3. In the main() function:  
   1. Create four objects: d1, d2, d3, d4.  
      - For each creation, the constructor is executed and `"Constructor called"` is printed.  
   2. Run a for loop four times (i = 0 to 3):  
      - In each iteration, create a temporary object temp.  
      - When the loop iteration ends, temp goes out of scope → destructor is executed and `"Destructor called"` is printed.  
   3. After the loop finishes, execution reaches the end of main().  
   4. At program termination, objects d4, d3, d2, d1 go out of scope in reverse order of creation.  
      - For each, the destructor is executed and `"Destructor called"` is printed.  
4. End  

---

### 🔹 Constructor Inside the Class  

- A constructor can be defined directly inside the class body.  

**Syntax:**  
```cpp
class ClassName {
public:
    ClassName(parameters) {
        // constructor body
    }
};
```

**Algorithm (Constructor inside class)**  

1. Start  
2. Define a class Student with:  
   - Data members:  
     - roll_no (integer)  
     - name (string)  
     - fee (long integer)  
   - A constructor inside the class Student(int r, string n, long f) that:  
     - Assigns r to roll_no.  
     - Assigns n to name.  
     - Assigns f to fee.  
   - A member function display() that prints name, roll_no, and fee.  
3. In the main() function:  
   1. Create an object s of class Student and pass the values `(101, "Barkha", 50000)` to the constructor.  
   2. The constructor initializes the data members with these values.  
   3. Call s.display() to print the student details.  
4. End  

---

### 🔹 Constructor Outside the Class  

- A constructor can be declared inside the class but defined outside using scope resolution operator `::`.  

**Syntax:**  
```cpp
class ClassName {
public:
    ClassName(parameters); // constructor declaration
};

ClassName::ClassName(parameters) {
    // constructor body
}
```

**Algorithm (Constructor outside class)**  

1. Start  
2. Define a class Student with:  
   - Data members:  
     - roll_no (integer)  
     - name (string)  
     - fee (long integer)  
   - A constructor declaration Student(int r, string n, long f); inside the class.  
   - A member function display(); declaration inside the class.  
3. Define the constructor outside the class using Student::Student(int r, string n, long f) that:  
   - Assigns r to roll_no.  
   - Assigns n to name.  
   - Assigns f to fee.  
4. Define the member function display() outside the class using Student::display() that:  
   - Prints name, roll_no, and fee.  
5. In the main() function:  
   1. Create an object s of class Student with values `(101, "Barkha", 50000)`.  
   2. The constructor is automatically called and initializes the object’s data members.  
   3. Call s.display() to print the student details.  
6. End  

---

## Outcomes  

- Understood the concept of **constructors** and their types (default, parameterized, copy).  
- Learned how constructors are automatically invoked at the time of object creation.  
- Understood the role of **destructors** in memory/resource management.  
- Practiced writing constructors **inside and outside the class**.  
- Observed the difference between constructor and destructor execution order.  

---

## Applications of Constructors  

1. **Initialization of objects** at the time of creation without requiring separate function calls.  
2. **Code reusability** – same initialization logic can be applied across multiple objects.  
3. **Copying objects** safely using copy constructors (useful in file handling, dynamic memory management).  
4. **Encapsulation of initialization** – ensures objects are always created in a valid state.  
5. Widely used in **real-world applications** like:  
   - Database connection initialization  
   - Game development (initializing player stats, objects, and environments)  
   - GUI frameworks (widgets/windows auto-initialized)  
   - File handling classes (auto-open files when object created)  

---
