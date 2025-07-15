# 📊 AWK Command Guide (TCS IPA Revision)

`awk` is a powerful text-processing tool in UNIX used to **search, filter, and format** data — often used for pattern scanning and reports.

---

## 🧠 Basic Syntax

```bash
awk 'pattern { action }' filename
```

- `pattern`: Condition to match (optional).
- `action`: Operation to perform on matched lines.

---

## 📌 Common Built-in Variables

| Variable | Description |
|----------|-------------|
| `$0`     | Entire current line |
| `$1`, `$2`, ... | First, second, etc. field |
| `NR`     | Current line number |
| `NF`     | Number of fields in current line |

---

## 📘 Examples

### 1. 🔍 Print entire file

```bash
awk '{ print }' data.txt
```
> 📎 Prints each line in the file.

---

### 2. 📦 Print first column of a CSV file

```bash
awk -F "," '{ print $1 }' file.csv
```
> `-F ","` sets comma as delimiter.

---

### 3. 🔢 Print line number and line

```bash
awk '{ print NR, $0 }' file.txt
```

---

### 4. 🔎 Match lines containing a pattern

```bash
awk '/apple/ { print }' fruits.txt
```
> Prints lines containing the word "apple".

---

### 5. 🧮 Sum of a column

```bash
awk '{ sum += $2 } END { print "Total:", sum }' marks.txt
```
> Adds the second column of all rows and prints the total.

---

### 6. 📈 Average of a column

```bash
awk '{ total += $3 } END { print "Average:", total/NR }' scores.txt
```

---

### 7. 🧹 Filter lines with condition (e.g. score > 50)

```bash
awk '$2 > 50 { print $1, $2 }' scores.txt
```

---

## 🛠️ Use Case Example File: `students.txt`

```
John 78
Aman 43
Riya 88
Tina 60
```

### 👉 Command:

```bash
awk '$2 >= 60 { print $1 " passed with " $2 }' students.txt
```

### ✅ Output:

```
John passed with 78
Riya passed with 88
Tina passed with 60
```

---

## 📝 Tip

Use `awk` for:
- Field-wise filtering
- Report generation
- Text extraction and summarization

---

👨‍💻 Made by Vishwash Patel | 🧪 Ideal for TCS IPA final revision
