# C# Test Average and Division Project

## 📌 Project Overview

This project is a simple **C# Windows Forms** application that demonstrates how to calculate the average of three test scores, handle errors using `try-catch`, and understand the difference between integer division and double division.

## 🧮 Calculating the Average of Three Tests

The program declares three test variables and an `Average` variable:

```csharp
double test1, test2, test3, Average;
 
 
 ##eg2
 # Integer Division vs. Double Division – C#

Two short, separate examples showing how variable type affects the result of `/` in C#.

```csharp
int x = 7, y = 3;
MessageBox.Show(((double)x / y).ToString());

double x = 7, y = 3;
MessageBox.Show((x/y).ToString());
```

*(These are two separate examples, not run together — `x` and `y` can't be declared twice in the same scope.)*

## Example A – `int` with a cast

```csharp
int x = 7, y = 3;
MessageBox.Show(((double)x / y).ToString());
```

- `x` and `y` are declared as `int`, so normally `x / y` would use **integer division**, which drops the decimal part (`7 / 3` would give `2`).
- `(double)x` **casts** `x` to a `double` before the division. Because one side of the `/` is now a `double`, C# performs the division as a decimal (floating-point) calculation.
- Result: `7 / 3` → `2.333333333333333`

## Example B – both variables already `double`

```csharp
double x = 7, y = 3;
MessageBox.Show((x/y).ToString());
```

- `x` and `y` are declared as `double` from the start, so no cast is needed.
- `x / y` is already decimal division.
- Result: same value, `2.333333333333333`

## Why this matters

| Types in `x / y` | Division used | `7 / 3` result |
|---|---|---|
| `int / int` | Integer division | `2` (decimal part discarded) |
| `(double)int / int` | Decimal division | `2.333...` |
| `double / double` | Decimal division | `2.333...` |

This is a common C# gotcha: dividing two `int` values truncates the result, even when the numbers involved are conceptually decimal. Casting at least one operand to `double` (or declaring the variables as `double` to begin with) avoids the truncation.

