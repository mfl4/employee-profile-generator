# employee-profile-generator

A small Python workshop project from the **Python Basics** course. This folder
contains a hands-on exercise that focuses on **strings**: concatenation,
compound assignment, type conversion, f-strings, and string slicing.

## Contents

| File           | Description                                                     |
| -------------- | --------------------------------------------------------------- |
| `main.py`      | The sample program that builds and slices employee profiles.    |
| `LICENSE`      | CC0 1.0 Universal public domain dedication.                     |
| `.gitignore`   | Standard Python ignore rules for version control.               |

## Getting started

1. Make sure you have Python 3 installed.
2. Run the program from the project folder:

   ```bash
   python main.py
   ```

## What `main.py` does

The script assembles employee information from separate pieces of text and
numbers, then extracts parts of an employee code using slicing.

```python
first_name = 'John'
last_name = 'Doe'
full_name = first_name + ' ' + last_name
address = '123 Main Street'
address += ', Apartment 4B'
employee_age = 28
employee_info = full_name + ' is ' + str(employee_age) + ' years old'
print(employee_info)

experience_years = 5
experience_info = 'Experience: ' + str(experience_years) + ' years'
print(experience_info)
position = 'Data Analyst'
salary = 75000
employee_card = f'Employee: {full_name} | Age: {employee_age} | Position: {position} | Salary: ${salary}'
print(employee_card)

employee_code = 'DEV-2026-JD-001'
department = employee_code[0:3]
print(department)
year_code = employee_code[4:8]
print(year_code)
initials = employee_code[9:11]
print(initials)
last_three = employee_code[-3:]
print(last_three)
```

### Key concepts

- **Concatenation** (`+`): joins strings, e.g. `first_name + ' ' + last_name`
  produces `'John Doe'`.
- **Compound assignment** (`+=`): appends text to an existing string, e.g.
  `address += ', Apartment 4B'`.
- **Type conversion** (`str()`): converts a number to text so it can be joined
  with strings, e.g. `str(employee_age)`.
- **f-strings** (`f'...'`): embed variables directly inside a string using
  `{}` placeholders, which is cleaner than manual concatenation.
- **Slicing** (`[start:stop]`): extracts a substring by index. `stop` is
  exclusive, and negative indexes count from the end.

### String slicing breakdown

For `employee_code = 'DEV-2026-JD-001'`:

| Index positions | Slice              | Result   |
| --------------- | ------------------ | -------- |
| `[0:3]`         | department         | `DEV`    |
| `[4:8]`         | year code          | `2026`   |
| `[9:11]`        | initials           | `JD`     |
| `[-3:]`         | last three chars   | `001`    |

## Expected output

```
John Doe is 28 years old
Experience: 5 years
Employee: John Doe | Age: 28 | Position: Data Analyst | Salary: $75000
DEV
2026
JD
001
```

## Learning goals

- Combine strings using concatenation and the `+=` operator.
- Convert numbers to strings with `str()` before joining them.
- Format text cleanly using f-strings.
- Extract substrings with slicing, including negative indexes.

## License

Released under [CC0 1.0](LICENSE), placing the work in the public domain.
