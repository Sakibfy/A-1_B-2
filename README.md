🎯 TypeScript Insights: Understanding keyof and any | unknown | never Types
TypeScript, a superset of JavaScript, offers powerful static typing features that improve code safety, readability, and maintainability. In this post, we’ll explore two important TypeScript concepts often discussed in interviews: the keyof keyword and the differences between any, unknown, and never.

🔑 1. What is the Use of the keyof Keyword in TypeScript?
The keyof keyword is used to extract the property names (keys) of a given type as a union of string literal types.

✅ Why Use keyof?
It provides a way to write safer, more generic functions by ensuring only valid property names are used.

📌 Example:
ts
Copy
Edit
type Person = {
  name: string;
  age: number;
  isActive: boolean;
};

function getValue<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}

const person: Person = {
  name: "Alice",
  age: 30,
  isActive: true,
};

const personName = getValue(person, "name"); // string
const personAge = getValue(person, "age");   // number
Here, K extends keyof T ensures that the key parameter is one of the actual keys of the object type T. This reduces bugs and improves developer experience with better autocompletion and type checking.

🚫 2. Difference Between any, unknown, and never in TypeScript
Understanding these three fundamental types helps avoid unsafe code and improves type safety.

📌 any — Turn Off Type Checking
Use Case: When you want to opt-out of type checking.

Behavior: Disables all TypeScript safety.

ts
Copy
Edit
let value: any = 42;
value = "hello";        // No error
value.someMethod();     // No error at compile time, but will crash at runtime
🔴 Risk: any defeats the purpose of using TypeScript.

📌 unknown — Safe Alternative to any
Use Case: When a value’s type isn’t known at declaration but you don’t want to lose type safety.

Behavior: Requires type checking before usage.

ts
Copy
Edit
let input: unknown = "test";

if (typeof input === "string") {
  console.log(input.toUpperCase()); // Safe
}
✅ Benefit: Encourages proper type checking and prevents runtime errors.

📌 never — Represents the Impossible
Use Case: For functions that never return (e.g., they throw or loop forever).

Behavior: Indicates unreachable code or failure scenarios.

ts
Copy
Edit
function throwError(message: string): never {
  throw new Error(message);
}
It also appears in exhaustive checks:

ts
Copy
Edit
type Shape = "circle" | "square";

function handleShape(shape: Shape) {
  switch (shape) {
    case "circle":
      // ...
      break;
    case "square":
      // ...
      break;
    default:
      const _exhaustiveCheck: never = shape; // Error if a new case is added
  }
}
✅ Benefit: Guarantees your code handles all possible cases.

🧠 Final Thoughts
keyof improves generic function safety by narrowing inputs to known keys.

Understanding the differences between any, unknown, and never is crucial for writing safe, predictable TypeScript code.