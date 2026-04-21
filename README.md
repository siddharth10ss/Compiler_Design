# Compiler Design Lab

A collection of experiments covering all major phases of a compiler — from lexical analysis to code optimization. Implemented in C, Python, and Lex/Yacc.

---

## Experiments

| # | Topic | Files |
|---|-------|-------|
| 1 | Lexical & Syntax Analysis using Lex/Yacc | `simple.l`, `simple.y` |
| 2 | Regular Expression to NFA | `re_to_nfa.c` |
| 3 | NFA to DFA Conversion | `nfa_to_dfa.c` |
| 4 | Left Recursion Removal & Left Factoring | `left_recursion.py`, `left_factoring.py` |
| 5 | FIRST and FOLLOW Sets | `first_follow.py` |
| 6 | LL(1) Predictive Parser | `ll_1.c` |
| 7 | Shift-Reduce Parsing | `shift reduce parsing.py` |
| 8 | Leading and Trailing Sets (Operator Precedence) | `leading_trailing.py` |
| 9 | LR(0) Item Sets Construction | `LR0.py` |
| 10 | Intermediate Code Generation (Postfix to Prefix) | `intermediate_code.py`, `postfix_to_prefix.py` |
| 11 | Three Address Code — Quadruple, Triple, Indirect Triple | `Quad_triple.py` |
| 12 | Simple Code Generator | `simple_codegenerator.py` |
| 13 | DAG (Directed Acyclic Graph) for Basic Blocks | `DAG.py` |
| 14 | Dataflow Analysis | `dataflow_analysis.py` |
| 15 | Stack-based Operations | `stack.py` |

---

## Setup & Requirements

- **Python 3.x** — for all `.py` experiments
- **GCC** — for C-based experiments (`Experiment_2`, `Experiment_3`, `Experiment_6`)
- **Flex & Bison** — for `Experiment_1`

### Install Flex & Bison (Linux/Codespace)

```bash
sudo apt update
sudo apt install flex bison -y
```

---

## Running Experiments

### Experiment 1 — Lex/Yacc Compiler

```bash
cd Experiment_1
yacc -d simple.y
flex simple.l
gcc y.tab.c lex.yy.c -o compiler -lfl
./compiler
```

### Experiment 2 — RE to NFA (C)

```bash
cd Experiment_2
gcc re_to_nfa.c -o re_to_nfa
./re_to_nfa
```

### Experiment 3 — NFA to DFA (C)

```bash
cd Experiment_3
gcc nfa_to_dfa.c -o nfa_to_dfa
./nfa_to_dfa
```

### Experiment 4 — Left Recursion & Left Factoring

```bash
cd Experiment_4
python left_recursion.py
python left_factoring.py
```

> Grammar is read from `grammar_input.txt`. Use `->` for productions, `|` for alternatives, and `#` for epsilon.

### Experiment 5 — FIRST and FOLLOW

```bash
cd Experiment_5
python first_follow.py
```

### Experiment 6 — LL(1) Parser (C)

```bash
cd Experiment_6
gcc ll_1.c -o ll1
./ll1
```

### Experiments 7–15 — Python Scripts

```bash
cd Experiment_<N>
python <script_name>.py
```

> Some experiments read from an `input.txt` file in the same folder. Edit it to test different inputs.

---

## Grammar File Format (Experiments 4 & 5)

```
E -> E + T | T
T -> T * F | F
F -> ( E ) | id
```

- Use `#` to represent **epsilon (ε)**
- Use `->` to separate LHS from RHS
- Use `|` for multiple productions

---

## Topics Covered

- Finite Automata (NFA, DFA)
- Context-Free Grammars
- Top-down Parsing (LL(1))
- Bottom-up Parsing (Shift-Reduce, LR(0))
- Operator Precedence Parsing
- Intermediate Code Generation
- Three Address Code Representations
- DAG-based Optimization
- Dataflow Analysis
