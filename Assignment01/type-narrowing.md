# What is Type Narrowing in TypeScript?

## Introduction

When I first learned TypeScript, I realized that variables can have more than one possible type by using union types. However, before using methods or properties that belong to a specific type, TypeScript needs to know which type the value actually is. This process is called **type narrowing**. It helps reduce a broad type into a more specific one, making the code safer and preventing runtime errors. TypeScript provides several ways to narrow types, including `typeof`, `instanceof`, and the `in` operator.

## Type Narrowing with Practical Examples

The `typeof` operator is commonly used with primitive types such as strings, numbers, and booleans.

```typescript
function processValue(value: string | number) {
  if (typeof value === "string") {
    return value.toUpperCase();
  }
  return value * 2;
}
```

The `instanceof` operator is useful for checking whether an object is created from a specific class.

```typescript
class Dog {
  bark() {
    return "Woof!";
  }
}

const pet = new Dog();

if (pet instanceof Dog) {
  console.log(pet.bark());
}
```

The `in` operator checks whether an object contains a particular property.

```typescript
type Admin = { name: string; permissions: string[] };
type User = { name: string; email: string };

function printInfo(person: Admin | User) {
  if ("permissions" in person) {
    console.log(person.permissions);
  } else {
    console.log(person.email);
  }
}
```

## Conclusion

Type narrowing is an important feature of TypeScript because it allows me to safely work with different data types. By using `typeof`, `instanceof`, and the `in` operator, I can write code that is more reliable, easier to understand, and less likely to produce errors. I now use type narrowing regularly whenever I work with union types in TypeScript.