# SE4041 – Mobile Application Design & Development  
## Practical 02 – Collections & Control Flow in Swift

**Duration:** 2 Hours  
**Module:** SE4041 – Mobile Application Design & Development  
**Practical Type:** Self-Guided  
**Language:** Swift

---

## 1. Practical Overview

In Practical 01, you worked with individual values such as strings, numbers, Booleans, operators, and optionals.

In real applications, however, we usually need to work with **many values at the same time**.

For example:

- a list of student marks,
- a collection of unique cities,
- student IDs mapped to names,
- products stored using product codes,
- multiple records that must be processed one by one.

Swift provides three important collection types for this purpose:

- **Array**
- **Set**
- **Dictionary**

Once data is stored in collections, we also need to make decisions and repeat operations. Therefore, this practical also introduces:

- `if / else if / else`
- `switch`
- ranges
- `for-in`
- `while`
- `repeat-while`
- `break`
- `continue`

These topics directly follow the content of Lecture 03. :chatgpt-content-reference{index="1"}

---

## 2. Learning Objectives

By the end of this practical, you should be able to:

1. Create and modify arrays.
2. Create and use sets.
3. Perform basic set operations.
4. Create and update dictionaries.
5. Safely retrieve values from dictionaries.
6. Decide whether an array, set, or dictionary is suitable for a problem.
7. Write `if / else if / else` statements.
8. Use `switch` statements.
9. Use closed and half-open ranges.
10. Write `for-in`, `while`, and `repeat-while` loops.
11. Use `break` and `continue`.
12. Combine collections and control flow in a complete Swift program.

These outcomes match the learning objectives of Lecture 03. :chatgpt-content-reference{index="2"}

---

## 3. Practical Environment

You may complete this practical using either:

### Option 1 – Xcode Playground

Open:

**Xcode → File → New → Playground**

Create a blank Swift Playground.

### Option 2 – Swift Playgrounds

Create a new Swift Playground and complete the same exercises.

---

## 4. Exercise 0 – GitHub Setup

Before beginning:

1. Log in to GitHub.
2. Accept the GitHub Classroom assignment provided by your instructor.
3. Open or clone your repository.
4. Create the following files.

```text
SE4041-Practical-02/
│
├── Exercise01.swift
├── Exercise02.swift
├── Exercise03.swift
├── Exercise04.swift
├── Exercise05.swift
├── Exercise06.swift
├── FinalChallenge.swift
│
└── screenshots/
```

Commit your work regularly.

Suggested commit messages:

```text
Complete array exercises
Complete set and dictionary exercises
Complete control flow exercises
Complete Practical 02 final challenge
```

---

## 5. Exercise 01 – Arrays

### Suggested Time: 20 Minutes

An **array** stores multiple values of the same type in a specific order.

An array:

- keeps its items in order,
- allows duplicate values,
- uses an index to access values,
- starts indexing from `0`.

This is the ordered collection introduced in Lecture 03. :chatgpt-content-reference{index="3"}

---

### Step 1 – Create an Array

Create `Exercise01.swift`.

Enter:

```swift
var marks = [72, 65, 48, 90, 55]

print(marks)
```

Expected output:

```text
[72, 65, 48, 90, 55]
```

---

### Step 2 – Access Array Elements

Try:

```swift
print(marks[0])
print(marks[2])
print(marks[4])
```

Remember:

```text
First element  -> index 0
Second element -> index 1
Third element  -> index 2
```

The lecture specifically highlights that array indices start at `0`, and accessing an invalid index causes an **index out of range** crash. :chatgpt-content-reference{index="4"}

---

### Step 3 – Useful Array Properties

Try:

```swift
print(marks.count)
print(marks.isEmpty)
print(marks.first)
print(marks.last)
```

Observe the output.

`first` and `last` return optional values because the array might be empty.

---

### Step 4 – Modify an Array

Because `marks` is declared using `var`, you can change it.

```swift
marks[2] = 52

print(marks)
```

Now add new values:

```swift
marks.append(88)
marks.insert(60, at: 1)

print(marks)
```

Remove values:

```swift
marks.removeLast()
marks.remove(at: 1)

print(marks)
```

Arrays support operations such as `append`, `insert`, and `remove`, but modifying them requires `var`. :chatgpt-content-reference{index="5"}

---

### Step 5 – Useful Array Methods

Try:

```swift
let marks = [72, 65, 48, 90, 55]

print(marks.max()!)
print(marks.min()!)
print(marks.contains(90))
print(marks.sorted())
print(marks.sorted(by: >))
```

Then calculate the total:

```swift
let total = marks.reduce(0, +)

print(total)
```

And the average:

```swift
let average = Double(total) / Double(marks.count)

print(average)
```

---

### Activity 1

Create an array containing the names of **five modules** you are currently studying.

Your program should:

1. Display the entire array.
2. Display the first module.
3. Display the last module.
4. Add one new module.
5. Display the number of modules.
6. Check whether `"SE4041"` exists in the array.

---

## 6. Exercise 02 – Sets

### Suggested Time: 15 Minutes

A **Set** stores unique values.

Unlike an array:

- a set does not guarantee order,
- duplicate values are not stored,
- values are unique,
- membership checking is efficient.

Lecture 03 describes a set as an **unordered, unique collection**. :chatgpt-content-reference{index="6"}

---

### Step 1 – Create a Set

```swift
var towns: Set = ["Malabe", "Kandy", "Galle"]
```

Print it:

```swift
print(towns)
```

You may notice that the order is not always the same.

That is normal.

---

### Step 2 – Insert Values

Try:

```swift
towns.insert("Jaffna")
towns.insert("Kandy")
```

Print:

```swift
print(towns)
print(towns.count)
```

Even though `"Kandy"` was inserted again, it appears only once.

Sets automatically enforce uniqueness. :chatgpt-content-reference{index="7"}

---

### Step 3 – Check Membership

```swift
print(towns.contains("Kandy"))
print(towns.contains("Colombo"))
```

---

### Step 4 – Remove an Item

```swift
towns.remove("Galle")

print(towns)
```

---

### Step 5 – Set Operations

Create:

```swift
let swiftClass: Set = ["Amal", "Nimali", "Ruwan"]
let kotlinClass: Set = ["Nimali", "Ruwan", "Sanduni"]
```

Try:

```swift
print(swiftClass.union(kotlinClass).sorted())
print(swiftClass.intersection(kotlinClass).sorted())
print(swiftClass.subtracting(kotlinClass).sorted())
print(swiftClass.symmetricDifference(kotlinClass).sorted())
```

These operations mean:

```text
union
Everyone who appears in either set.

intersection
People appearing in both sets.

subtracting
People in the first set but not the second.

symmetricDifference
People appearing in only one of the two sets.
```

These exact operations are introduced in Lecture 03. :chatgpt-content-reference{index="8"}

---

### Activity 2

Create two sets:

```text
mobileDevelopmentStudents
gameTechnologyStudents
```

Add at least four names to each set.

Make sure at least **two students appear in both sets**.

Display:

1. All students.
2. Students taking both modules.
3. Students taking only Mobile Development.
4. Students taking only one of the modules.

---

## 7. Exercise 03 – Dictionaries

### Suggested Time: 20 Minutes

A **dictionary** stores values as:

```text
Key -> Value
```

Example:

```text
Student Name -> Mark
```

Unlike an array, you do not access a value using its position.

Instead, you use its **key**.

---

### Step 1 – Create a Dictionary

```swift
var marks = [
    "Amal": 72,
    "Nimali": 65,
    "Ruwan": 48
]
```

Print:

```swift
print(marks)
```

---

### Step 2 – Retrieve a Value

Try:

```swift
print(marks["Amal"])
```

You may see:

```text
Optional(72)
```

Why?

Because Swift cannot guarantee that the key exists.

A dictionary lookup therefore returns an **optional**. :chatgpt-content-reference{index="9"}

---

### Step 3 – Safely Retrieve a Value

Use nil-coalescing:

```swift
print(marks["Amal"] ?? 0)
```

Try a key that does not exist:

```swift
print(marks["Kasun"] ?? 0)
```

---

### Step 4 – Use Optional Binding

```swift
if let mark = marks["Nimali"] {
    print("Nimali scored \(mark)")
} else {
    print("Student not found")
}
```

This connects directly with the optionals you learned in Practical 01.

---

### Step 5 – Add and Update Values

Add a student:

```swift
marks["Sanduni"] = 90
```

Update:

```swift
marks["Amal"] = 75
```

Remove:

```swift
marks["Ruwan"] = nil
```

Print:

```swift
print(marks)
```

Lecture 03 shows that the same dictionary syntax can add, update, or remove key-value pairs. :chatgpt-content-reference{index="10"}

---

### Activity 3 – Phone Book

Create a dictionary containing:

```text
Name -> Phone Number
```

Add at least four contacts.

Your program should:

1. Add a new contact.
2. Update one phone number.
3. Remove one contact.
4. Search for a contact using `if let`.
5. Display `"Contact not found"` if the key does not exist.

---

## 8. Choosing the Correct Collection

Before continuing, make sure you understand when each collection should be used.

| Requirement | Best Choice |
|---|---|
| Ordered list | Array |
| Duplicate values allowed | Array |
| Unique values | Set |
| Very fast membership checking | Set |
| Key-value relationship | Dictionary |
| Access using ID/name | Dictionary |

Lecture 03 uses examples such as marks in exam order for arrays, unique towns for sets, and phone numbers looked up by student name for dictionaries. :chatgpt-content-reference{index="11"}

---

## 9. Exercise 04 – `if`, `else if`, and `else`

### Suggested Time: 10 Minutes

Control flow allows your program to make decisions.

Consider:

```swift
let mark = 68

if mark >= 75 {
    print("Distinction")
} else if mark >= 50 {
    print("Pass")
} else {
    print("Fail")
}
```

Expected:

```text
Pass
```

Conditions are tested from top to bottom, and the first matching condition is executed. :chatgpt-content-reference{index="12"}

---

### Activity 4

Create:

```swift
let attendance = 78
```

Use `if / else if / else` to display:

```text
90 or above -> Excellent attendance
80 to 89    -> Good attendance
70 to 79    -> Acceptable attendance
Below 70    -> Low attendance
```

Test your program using different values.

---

## 10. Exercise 05 – `switch` and Ranges

### Suggested Time: 15 Minutes

Swift's `switch` statement is useful when one value can match several possible cases.

Example:

```swift
let grade = "B"

switch grade {
case "A":
    print("Excellent")

case "B", "C":
    print("Good")

case "D":
    print("Needs Work")

default:
    print("Unknown Grade")
}
```

Expected:

```text
Good
```

In Swift:

- `break` is not normally required,
- a `switch` must cover every possible case,
- `default` can be used for remaining values. :chatgpt-content-reference{index="13"}

---

### Using Ranges in a Switch

Try:

```swift
let mark = 68

switch mark {
case 75...100:
    print("Distinction")

case 50..<75:
    print("Pass")

case 0..<50:
    print("Fail")

default:
    print("Invalid Mark")
}
```

Expected:

```text
Pass
```

Notice the difference:

```swift
75...100
```

includes both `75` and `100`.

But:

```swift
50..<75
```

includes `50`, but stops before `75`.

Lecture 03 specifically uses ranges inside `switch` because they are cleaner than long chains of `else if`. :chatgpt-content-reference{index="14"}

---

### Activity 5 – Temperature Description

Create:

```swift
let temperature = 27
```

Use a `switch` and ranges to display:

```text
Below 0   -> Freezing
0...15    -> Cold
16...25   -> Moderate
26...35   -> Warm
Above 35  -> Hot
```

Test your program using at least three temperatures.

---

## 11. Exercise 06 – Loops

### Suggested Time: 20 Minutes

Loops repeat a block of code.

Swift provides several loop types.

---

### Part A – `for-in`

Use `for-in` when you know what collection or range you want to iterate through.

```swift
for i in 1...5 {
    print("Week \(i)")
}
```

Expected:

```text
Week 1
Week 2
Week 3
Week 4
Week 5
```

`for-in` can iterate over ranges, arrays, sets, dictionaries, and strings. :chatgpt-content-reference{index="15"}

---

### Loop Through an Array

```swift
let names = ["Amal", "Nimali", "Ruwan"]

for name in names {
    print(name)
}
```

---

### Using `enumerated()`

Sometimes you need both:

- the index,
- and the value.

```swift
let names = ["Amal", "Nimali", "Ruwan"]

for (index, name) in names.enumerated() {
    print("\(index): \(name)")
}
```

---

### Part B – `while`

Use `while` when you do not know exactly how many repetitions are required.

```swift
var balance = 1000
var week = 0

while balance > 0 {
    balance -= 300
    week += 1
}

print("Ran out in week \(week)")
```

A `while` condition is checked **before** the loop body, so the body may run zero times. :chatgpt-content-reference{index="16"}

---

### Part C – `repeat-while`

A `repeat-while` loop runs the body first and checks the condition afterwards.

```swift
var attempts = 0

repeat {
    attempts += 1
    print("Attempt \(attempts)")
} while attempts < 3
```

Expected:

```text
Attempt 1
Attempt 2
Attempt 3
```

The important difference is that a `repeat-while` loop runs at least once. :chatgpt-content-reference{index="17"}

---

## 12. `break` and `continue`

Consider:

```swift
let marks = [72, -1, 65, 48, 90]

for mark in marks {

    if mark < 0 {
        continue
    }

    if mark == 90 {
        break
    }

    print(mark)
}
```

`continue` means:

> Skip the rest of the current repetition and move to the next one.

`break` means:

> Stop the loop completely.

This distinction is explicitly covered in Lecture 03. :chatgpt-content-reference{index="18"}

---

### Activity 6

Create:

```swift
let marks = [72, -1, 55, 43, 90, 88]
```

Loop through the marks.

Requirements:

- Ignore negative marks using `continue`.
- Stop processing if you find `90`.
- Print every valid mark processed before the loop stops.

---

## 13. Putting Collections and Control Flow Together

Consider:

```swift
let names = ["Amal", "Nimali", "Ruwan", "Sanduni"]
let marks = [72, 45, 48, 90]

let passMark = 50

var passedStudents: [String] = []

for (index, mark) in marks.enumerated() {

    if mark >= passMark {

        passedStudents.append(names[index])

        print("\(names[index]): \(mark) - Pass")

    } else {

        print("\(names[index]): \(mark) - Fail")
    }
}

print("Passed Students: \(passedStudents)")
```

This example combines:

- arrays,
- loops,
- `enumerated()`,
- `if`,
- `append()`.

It closely follows the integrated worked example in Lecture 03. :chatgpt-content-reference{index="19"}

---

## 14. Knowledge Check

Before attempting the final task, make sure you can answer these questions.

1. What is the main difference between an array and a set?
2. Why does an array allow duplicates?
3. Why does a set ignore duplicate values?
4. How do you access an array item?
5. How do you access a dictionary value?
6. Why does dictionary lookup return an optional?
7. What is the difference between `...` and `..<`?
8. When should you use `if`?
9. When can `switch` be clearer than `if / else if`?
10. What is the difference between `for-in` and `while`?
11. What is the main difference between `while` and `repeat-while`?
12. What does `continue` do?
13. What does `break` do?

---

## 15. Final Practical Task – Student Performance Manager

### Suggested Time: 30 Minutes

Create:

```text
FinalChallenge.swift
```

This is the task you must complete and submit.

---

### Scenario

You have been asked to create a simple Swift program to process student results for a module.

The system should store student marks, determine grades, identify passed students, and display useful summary information.

---

### Requirements

### Part A – Store Student Marks

Create a dictionary:

```swift
var studentMarks: [String: Int] = [
    "Amal": 72,
    "Nimali": 45,
    "Ruwan": 68,
    "Sanduni": 90,
    "Kasun": 38
]
```

You may use different names and marks if you wish.

---

### Part B – Display All Students

Use a loop to display every student and their mark.

Example:

```text
Amal - 72
Nimali - 45
Ruwan - 68
...
```

Because dictionary order is not guaranteed, you may sort the keys before displaying them.

---

### Part C – Determine Grade

For each student's mark, use a `switch` statement and ranges.

Use:

```text
80...100 -> A
75..<80  -> A-
70..<75  -> B+
65..<70  -> B
60..<65  -> B-
55..<60  -> C+
45..<55  -> C
40..<45  -> C-
0..<40   -> F
```

This grading structure follows the worked example provided in Lecture 03. :chatgpt-content-reference{index="20"}

Output should look similar to:

```text
Amal - 72 - B+
Nimali - 45 - C
Ruwan - 68 - B
Sanduni - 90 - A
Kasun - 38 - F
```

---

### Part D – Passed Students

Create an empty array:

```swift
var passedStudents: [String] = []
```

A student passes when:

```text
Mark >= 50
```

Loop through the dictionary.

If a student has passed:

```swift
passedStudents.append(name)
```

At the end, print all passed students.

---

### Part E – Unique Grades

Create a `Set<String>` to store all grades that appeared.

Example:

```swift
var gradesAwarded: Set<String> = []
```

As each grade is calculated, add it to the set.

At the end display:

```text
Grades Awarded:
["A", "B", "B+", "C", "F"]
```

The order does not matter.

---

### Part F – Average Mark

Calculate the total of all marks.

Then calculate:

```text
Average = Total / Number of Students
```

Convert to `Double` where necessary.

Example:

```text
Class Average: 62.6
```

---

### Part G – Highest and Lowest Marks

Find and display:

```text
Highest Mark
Lowest Mark
```

You may use:

```swift
max()
min()
```

on an array of dictionary values.

---

### Expected Output

Your output should be similar to:

```text
==================================
      STUDENT PERFORMANCE
==================================

Amal - 72 - B+
Kasun - 38 - F
Nimali - 45 - C
Ruwan - 68 - B
Sanduni - 90 - A

----------------------------------

Passed Students:
Amal
Ruwan
Sanduni

----------------------------------

Grades Awarded:
A
B
B+
C
F

----------------------------------

Class Average: 62.6
Highest Mark: 90
Lowest Mark: 38
```

Your exact ordering may be different unless you sort the names.

---

## 16. Additional Challenge

If you finish early, add the following.

### Search for a Student

Create:

```swift
let searchName = "Amal"
```

Use optional binding:

```swift
if let ...
```

to search the dictionary.

If the student exists:

```text
Amal's mark is 72
```

Otherwise:

```text
Student not found
```

---

### Count Passes and Fails

Create:

```swift
var passCount = 0
var failCount = 0
```

Update these values while processing the students.

Display:

```text
Passed: 3
Failed: 2
```

---

## 17. Submission Requirements

Your repository should contain:

```text
Exercise01.swift
Exercise02.swift
Exercise03.swift
Exercise04.swift
Exercise05.swift
Exercise06.swift
FinalChallenge.swift
```

Also include:

```text
screenshots/
```

Recommended screenshots:

```text
01-Collections.png
02-Control-Flow.png
03-Final-Challenge.png
```

The final screenshot must clearly show your final program output.

---

## 18. GitHub Submission

Before finishing:

```bash
git status
git add .
git commit -m "Complete SE4041 Practical 02"
git push
```

Open your GitHub repository and confirm that the files have been uploaded successfully.

---

## 19. Final Submission Checklist

Before completing the practical, confirm that:

- [ ] Arrays have been used.
- [ ] Sets have been used.
- [ ] Dictionaries have been used.
- [ ] Dictionary optionals have <!-- The remaining checklist items and timing plan were reconstructed because the available conversation export ends here. -->
- [ ] The final challenge contains a dictionary of student marks.
- [ ] Grades are calculated using `switch` and ranges.
- [ ] Passed students are stored in an array.
- [ ] Unique grades are stored in a set.
- [ ] The average, highest, and lowest marks are displayed.
- [ ] Screenshots have been included.
- [ ] All required files have been committed and pushed to GitHub.

---

## 20. Timing Plan for the 2-Hour Session

> **Editorial note:** This timing plan is reconstructed, not a verbatim copy of the original conversation. The suggested times within the original exercises total 130 minutes before setup and submission. Use the consolidated schedule below to fit the practical into 120 minutes.

| Section | Approx. Time |
| --- | ---: |
| Environment and GitHub setup | 5 min |
| Exercise 01 – Arrays | 15 min |
| Exercise 02 – Sets | 10 min |
| Exercise 03 – Dictionaries and collection choice | 15 min |
| Exercise 04 – `if / else if / else` | 10 min |
| Exercise 05 – `switch` and ranges | 10 min |
| Exercise 06 – Loops, `break`, and `continue` | 15 min |
| Integrated example and knowledge check | 5 min |
| Student Performance Manager final challenge | 30 min |
| Submission and checklist | 5 min |
| **Total** | **120 min** |

The additional challenge is optional for students who finish early.

