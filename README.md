# 🎯 Interview Questions - Blog Task

## 1. What are some differences between interfaces and types in TypeScript?

Interfaces and Types both help us describe the shape of object but they also have some defferences.

- The Declaration style of interface and type is different. for example-
  
  Interface:
    ```
    interface User {
      id: number;
      name: string;
      email: string
    }
    ```
  Type:
    ```
    type User = {
      id: number;
      name: string;
      email: string
    }
    ```
- Type is more flexible then Interface.
- Interface can be extanded but types cannot be extanded.
- We can not change a type after it's created but we can add new fields to an existing interface.
- Types supports creating a new name for a type while Interface provides a way to define entities.
- Interface supports the use of an object but type does not inherently support the use of an object.

## 2. What is the use of the keyof keyword in TypeScript? Provide an example.

The `keyof` operator in typescript is used to extract keys from an existing object type and create a new union type based on those keys. for example -

```
 type Vehicle = {
        bike: string;
        car: string;
        ship: string;
  }
  type Owner = keyof Vehicle;
```
in this example, `Owner` becomes a new type:
```
type Owner = "bike" | "car" | "ship";
```
We can see that by using the `keyof` operator we did'nt have to declear the types of Owner manually. insted just by using the `keyof` operator we are able to extract all keys from Vehicle and use it for the Owner type.

We use `keyof` because it helps with type safety, it also works well with generics. and one of the most important reason to use `keyof` because it reduces repetition.