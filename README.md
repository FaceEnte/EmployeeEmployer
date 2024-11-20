# Employee and Employer Project

This project implements a simple class hierarchy in Java to represent a `Person`, with two subclasses: `Employee` and `Employer`. The design focuses on avoiding duplication by placing common attributes and methods in the base class.

## Class Hierarchy

### Person
- **Fields**:
    - `String name`
    - `int age`
    - `String address`

- **Constructors**:
    - `public Person(String name, int age, String address)`

- **Methods**:
    - `public String getName()`
    - `public int getAge()`
    - `public String getAddress()`
    - `public void displayInfo()`

### Employee (extends Person)
- **Fields**:
    - `String employeeId`
    - `double salary`

- **Constructors**:
    - `public Employee(String name, int age, String address, String employeeId, double salary)`

- **Methods**:
    - `public String getEmployeeId()`
    - `public double getSalary()`
    - `public void displayInfo()` (overrides the method in `Person` to include employee-specific details)

### Employer (extends Person)
- **Fields**:
    - `String companyName`
    - `String taxId`

- **Constructors**:
    - `public Employer(String name, int age, String address, String companyName, String taxId)`

- **Methods**:
    - `public String getCompanyName()`
    - `public String getTaxId()`
    - `public void displayInfo()` (overrides the method in `Person` to include employer-specific details)

## Example Implementation

### Person.java
```java
public class Person {
    private String name;
    private int age;
    private String address;

    public Person(String name, int age, String address) {
        this.name = name;
        this.age = age;
        this.address = address;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    public String getAddress() {
        return address;
    }

    public void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age + ", Address: " + address);
    }
}
```

### Employee.java
```java
public class Employee extends Person {
    private String employeeId;
    private double salary;

    public Employee(String name, int age, String address, String employeeId, double salary) {
        super(name, age, address);
        this.employeeId = employeeId;
        this.salary = salary;
    }

    public String getEmployeeId() {
        return employeeId;
    }

    public double getSalary() {
        return salary;
    }

    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Employee ID: " + employeeId + ", Salary: " + salary);
    }
}
```

### Employer.java
```java
public class Employer extends Person {
    private String companyName;
    private String taxId;

    public Employer(String name, int age, String address, String companyName, String taxId) {
        super(name, age, address);
        this.companyName = companyName;
        this.taxId = taxId;
    }

    public String getCompanyName() {
        return companyName;
    }

    public String getTaxId() {
        return taxId;
    }

    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Company Name: " + companyName + ", Tax ID: " + taxId);
    }
}
```

### Test Program
```java
public class TestProgram {
    public static void main(String[] args) {
        Employee employee = new Employee("Alice", 30, "123 Main St", "E123", 50000);
        Employer employer = new Employer("Bob", 45, "456 Elm St", "Tech Corp", "TAX456");

        System.out.println("Employee Info:");
        employee.displayInfo();
        
        System.out.println("\nEmployer Info:");
        employer.displayInfo();
    }
}
```

## Getting Started

1. **Create the `Person`, `Employee`, and `Employer` classes**: Implement the fields, constructors, and methods as specified above.
2. **Write a test program**: Implement the `TestProgram` class to create instances of `Employee` and `Employer`, and display their information.
3. **Compile and run the program**: Ensure that you have the necessary Java environment set up to compile and run the program.

## Notes

- Extend the functionality as needed to meet any additional requirements.

Happy coding! 🎉