

## Introduction

TypeScript offers two very useful methods to define types: type aliases and interface. They both contribute to making objects shapeable,code easier to read,maintain and type safe. While they may appear to be similar but there are some differences.

## Detailed Body

### 1. Type Alias

An alias for a type can be used to define a new name for any type, such as primitive types, objects, unions, tuples, and function types.

Code Example :

type User = {
    name: string;
    age: number;
};

type Status = "active" | "inactive";

type ID = string | number;


In the following, User is an object type and Status, ID are union types.

### 2. Interface

The main purpose of an interface is to specify the structure or contract of objects and classes.

Code Example :

interface User {
    name: string;
    age: number;
}

interface Employee extends User {
    salary: number;
}


The extends keyword is used to extend the properties from a parent interface to a child interface.

### 3. Core Differences

The only difference is that interfaces can have merging of declarations, and type aliases can't.

Code Differences: 

interface Person {
    name: string;
}

interface Person {
    age: number;
}


These declarations are all automatically merged into a single interface by TypeScript.But, if i repeat the same type alias, it will be an error.
One of the key differences is that type aliases can directly represent union types, intersection types and tuples, while interfaces cannot.


### 4. When is One the right option?

When defining an object's structure, a class contract, and when declaration merging is helpful, select interface. Use type to deal with unions, intersections, tuples, primitives or other more complicated types.

## Conclusion

The type and interface are important features of TypeScript. They offer type safety and increase the maintainability of applications. Interfaces are especially useful when it comes to defining class contracts in object-oriented programming. Type aliases provide more flexibility when it comes to constructing complex types.