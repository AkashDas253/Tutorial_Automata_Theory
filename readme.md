## Finite Automata  
Finite Automata (FA) are computational models used to recognize patterns in input strings. They are the most restricted type of automata and accept **only regular languages**. Regular languages can be expressed using **regular expressions** with operators like **OR (+)**, **Concatenation (.)**, and **Kleene Closure (*)**, e.g., `a*b*`, `(a+b)`.  

### Types of Finite Automata  
1. **Deterministic Finite Automata (DFA):**  
   - For every state and input symbol, there is exactly one transition.  

2. **Non-Deterministic Finite Automata (NDFA):**  
   - For a given state and input symbol, there can be **zero, one, or more transitions**.  

#### Notes:  
- DFA and NDFA accept the same languages.  
- DFA and NDFA have equivalent computational power.  
- The number of states in NDFA is less than or equal to that in its equivalent DFA.  
- For an NDFA with $n$-states, the corresponding DFA can have up to $2^n$ states.  
- Every NDFA can be converted into an equivalent DFA.  

---

## Identities of Regular Expressions  
1. $\Phi + R = R + \Phi = R$  
2. $\Phi * R = R * \Phi = \Phi$  
3. $\epsilon * R = R * \epsilon = R$  
4. $\epsilon* = \epsilon$  
5. $\Phi* = \epsilon$  
6. $\epsilon + RR* = R*R + \epsilon = R*$  
7. Compound identities:  
   - $(a+b)* = (a* + b*)* = (a*b*)* = (a*+b)* = (a+b*)* = a*(ba*)* = b*(ab*)*$  

---

## Advanced Finite State Machines  
### **Moore Machine:**  
- Output depends only on the **current state**.  

### **Mealy Machine:**  
- Output depends on the **current state** and the **current input symbol**.  

---

## Pushdown Automata (PDA)  
Pushdown Automata are more powerful than FA due to their use of a **stack as extra memory**. They are used to recognize **Context-Free Languages (CFLs)**.  

### Types of Pushdown Automata  
1. **Deterministic PDA (DPDA):**  
   - Single transition per input and state.  

2. **Non-Deterministic PDA (NPDA):**  
   - Multiple transitions for a given input and state.  

#### Notes:  
- **Power of NPDA > DPDA.**  
- Not all NPDAs can be converted to equivalent DPDAs.  
- Languages accepted by DPDA are called **Deterministic Context-Free Languages (DCFLs)**.  
- DCFLs are a subset of **Non-Deterministic Context-Free Languages (NCFLs)**.  

---

## Linear Bounded Automata (LBA)  
Linear Bounded Automata have a **finite tape** and are used to recognize **Context-Sensitive Languages (CSLs)**.  
- **Power hierarchy:** FA < PDA < LBA < TM.  

---

## Turing Machines (TM)  
Turing Machines are the most powerful computational models, with an **infinite tape**. They accept **Recursive Enumerable Languages (RELs)**.  

### Characteristics of Turing Machines  
- Can move in both directions on the tape.  
- Do not accept $\epsilon$.  
- Halt in a non-final state if the string is not part of the language.  

### Types of Turing Machines  
1. **Deterministic TM (DTM):**  
   - Single transition for each input and state.  
2. **Non-Deterministic TM (NTM):**  
   - Multiple transitions for each input and state.  

#### Notes:  
- Language accepted by DTM, NTM, and Multi-Tape TM is the same.  
- Computational power of DTM = NTM = Multi-Tape TM.  
- Every NTM can be converted into a corresponding DTM.  

---

## Chomsky Hierarchy of Languages  
| **Grammar Type**   | **Production Rules**                                                                                                                                  | **Language Accepted**          | **Automata**             | **Closed Under**                                    |  
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------|---------------------------|----------------------------------------------------|  
| **Type-3**          | $A → a$ or $A → aB$ ($A, B \in N$, $a \in T$)                                                                                                | Regular                       | Finite Automata          | Union, Intersection, Complementation, Concatenation, Kleene Closure |  
| **Type-2**          | $A → \rho$ ($A \in N$, $\rho \in (T \cup N)*$)                                                                                                | Context-Free                 | Pushdown Automata        | Union, Concatenation, Kleene Closure               |  
| **Type-1**          | $α → β$ ($α, β \in (T \cup N)*, len(α) \leq len(β)$, $α$ has at least one non-terminal)                                                        | Context-Sensitive            | Linear Bounded Automata  | Union, Intersection, Complementation, Concatenation, Kleene Closure |  
| **Type-0**          | $α → β$ ($α, β \in (T \cup N)*$, $α$ contains at least one non-terminal)                                                                      | Recursive Enumerable         | Turing Machine           | Union, Intersection, Concatenation, Kleene Closure |  

---

## Decidable and Undecidable Problems  
- **Decidable Language:** A language for which a Turing machine can decide acceptance or rejection (e.g., checking if a number is prime).  
- **Semi-Decidable Language:** A language for which a Turing machine accepts valid strings but may loop indefinitely for invalid strings.  
- **Undecidable Problem:** Problems for which no Turing machine or algorithm can give a definitive yes/no answer (e.g., checking ambiguity of a CFG).  

---

## Countability in Automata  
- Set of all strings over a finite alphabet is **countable**.  
- Subsets of countable sets are either finite or countable.  
- The set of all Turing Machines is **countable**.  
- The set of all languages not recursive enumerable is **uncountable**.  