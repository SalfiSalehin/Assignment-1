# Access Modifiers in TypeScript OOP

## Introduction

Access modifiers provide access to and modification of class properties or methods. There are four access modifiers in TypeScript: public, private, protected, readonly. These modifiers can be used to provide encapsulation, security, and clean code structures.

## Detailed Body

### 1. Public Modifier

The public modifier allows properties and methods to be accessed from anywhere, including inside the class, subclasses, and outside the class. It's the default access modifier for TypeScript.

Code Example :

class Student {
    public name: string = "Rakib";
}

const student = new Student();
console.log(student.name); // Rakib


### 2. Private Modifier

The private modifier makes a property or method private. Not directly accessible from outside the class or its subclasses.

Code Example :

class BankAccount {
    private balance: number = 5000;

    getBalance(): number {
        return this.balance;
    }
}

const account = new BankAccount();
console.log(account.getBalance()); // 5000
console.log(account.balance); // Error

### 3. Protected Modifier

The protected keyword is used to declare attributes that can be accessed from inside the class and its subclasses, but not from outside.

Code Example :

class Employee {
    protected name: string = "Alice";
}

class Manager extends Employee {
    displayName(): void {
        console.log(this.name);
    }
}

const manager = new Manager();
manager.displayName(); // Alice


### 4. Readonly Modifier

The readonly modifier prevents a property from being re-assigned after it is initialized. It can be set at declaration time or in the constructor.

Code Example :

class Product {
    readonly productId: number;

    constructor(id: number) {
        this.productId = id;
    }
}

const product = new Product(101);
console.log(product.productId); // 101
product.productId = 202; // Error


## Conclusion

Access modifiers are crucially needed for the implementation of encapsulation in TypeScript OOP, public means that it can be accessed anywhere, private means that it can be accessed only in the declaring class, protected means that it can be accessed within the subclass, and readonly means that it can not be reassigned. Selecting the right modifier is helpful in organization, maintainability and protection of data.