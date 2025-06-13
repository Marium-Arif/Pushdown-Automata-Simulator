# Pushdown-Automata-Simulator

A C++-based terminal program that processes Context-Free Grammars (CFGs) by eliminating null productions, unit productions, and useless productions, converting them to Greibach Normal Form (GNF), and finally simulating a Pushdown Automaton (PDA) to test input strings.

---

## 🎯 Features

* ✅ Null production removal (`?` as null symbol)
* ✅ Unit production elimination
* ✅ Useless production removal
* ✅ Conversion to **GNF** (Greibach Normal Form)
* ✅ Stack-based **PDA simulation** with backtracking
* ✅ Accepts multiple test strings in a session

---

## 🧠 How It Works

### 🧹 Grammar Cleanup

* Removes productions like `A -> ?`
* Replaces unit productions like `A -> B`
* Discards unreachable or infinite recursive rules

### 🔁 GNF Conversion

* Converts all CFG rules to GNF: `A -> aα` where `a` is a terminal, `α` is a string of non-terminals
* Handles left-recursion by introducing new non-terminals (e.g., `V2`)

### 🤖 PDA Simulation

* Uses a **stack** (`$` as initial marker)
* Recursively simulates transitions based on GNF rules
* Accepts or rejects input strings based on final stack state and string match

---

## 🧪 Example CFG Input Format

```
S->aSb|bT|a|b
T->aT|a|b
```

Use `?` to represent null (epsilon) if needed:

```
A->?
```

---

## 🚀 How to Run

1. Compile:

```bash
g++ -o pda_simulator yourfilename.cpp
```

2. Run:

```bash
./pda_simulator
```

3. Enter CFG and test strings when prompted.

---

## 🧾 Sample Output

```
Enter The Number Of lines in Context Free Grammar
2
S->aSb|bT|a|b
T->aT|a|b
Enter number of Test Strings to Check: 2
abaab
string accepted
abba
string not accepted
```

---

## 🧱 File Overview

* **Main file**: contains all logic for

  * CFG transformation
  * Stack-based PDA simulator
  * User I/O

---

## 📌 Notes

* Supports both terminal (a-z) and binary (0-1) input symbols
* All CFG rules must follow the format: `A->something`
* Nested transitions (like `A->B00`) will be transformed to GNF and handled via new rules

---

## 🛡 License

This project is released under the **MIT License**.

---

Happy Parsing! 🧠📚
