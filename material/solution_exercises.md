# Typescript exercises solution from basic to advanced

### 1. Introduction to TypeScript

```typescript
// File: app.ts
let message: string = "Hello, TypeScript!";
console.log(message);
```

### 2. TypeScript Basics

```typescript
// Function with type annotations
function addNumbers(num1: number, num2: number): number {
  return num1 + num2;
}
console.log(addNumbers(5, 3));

// Interface
interface Car {
  make: string;
  model: string;
  year: number;
}

function displayCarDetails(car: Car): void {
  console.log(`Make: ${car.make}, Model: ${car.model}, Year: ${car.year}`);
}

const myCar: Car = { make: "Toyota", model: "Camry", year: 2020 };
displayCarDetails(myCar);
```

### 3. Advanced TypeScript Features

```typescript
// Generic function
function getFirstElement<T>(arr: T[]): T {
  return arr[0];
}
console.log(getFirstElement([1, 2, 3]));

// Enum
enum DayOfWeek {
  Monday,
  Tuesday,
  Wednesday,
  Thursday,
  Friday,
  Saturday,
  Sunday,
}

function getDayType(day: DayOfWeek): string {
  return day >= DayOfWeek.Monday && day <= DayOfWeek.Friday
    ? "Weekday"
    : "Weekend";
}

console.log(getDayType(DayOfWeek.Saturday));
```

### 4. Working with Modules

```typescript
// Exporting module
export function greet(name: string): string {
  return `Hello, ${name}!`;
}
```

```typescript
// Importing module
import { greet } from "./greeting";

console.log(greet("Alice"));
```

### 5. Handling Complex Data Functions

```typescript
// Array operations
const numbers: number[] = [1, 2, 3, 4, 5];
const squaredNumbers = numbers.map((num) => num * num);
console.log(squaredNumbers);

class ShoppingCartItem {
  constructor(
    public name: string,
    public price: number,
    public quantity: number
  ) {}

  getTotalPrice(): number {
    return this.price * this.quantity;
  }
}

const item1 = new ShoppingCartItem("Laptop", 1000, 2);
console.log(item1.getTotalPrice());
```

### 6. Advanced Data Handling

```typescript
// JSON parsing
const jsonStr: string = '{"name": "John", "age": 30}';
const jsonObj: { name: string; age: number } = JSON.parse(jsonStr);
console.log(jsonObj);

// Using lodash
import * as _ from "lodash";

const users = [
  { name: "John", age: 30 },
  { name: "Alice", age: 25 },
  { name: "Bob", age: 35 },
];

const sortedUsers = _.sortBy(users, "age");
console.log(sortedUsers);
```

### 7. Testing and Debugging TypeScript Code

```typescript
// Unit test with Jest
// File: app.test.ts
import { addNumbers } from "./app";

test("adds 1 + 2 to equal 3", () => {
  expect(addNumbers(1, 2)).toBe(3);
});
```

### 8. Deploying TypeScript Applications

```cmd
tsc --project tsconfig.json --outDir dist --removeComments --sourceMap false
```

### 9. Best Practices and Tips

```typescript
// Refactored code
// Instead of:
function calculateTotalPrice(
  price: number | null,
  quantity: number | null
): number {
  if (price === null || quantity === null) {
    return 0;
  }
  return price * quantity;
}

// Use:
function calculateTotalPrice(
  price: number | null,
  quantity: number | null
): number {
  return price && quantity ? price * quantity : 0;
}
```
