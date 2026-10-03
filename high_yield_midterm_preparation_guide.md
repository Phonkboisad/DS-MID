# CSE 2321: Data Structures Midterm High-Yield Question Bank
**Target Score:** 25+ / 30 Marks  
**Coverage:** Chapter 1 (Introduction & Strings), Chapter 2 (Arrays, Sorting & Searching), Chapter 3 (Linked Lists)  
*(Stacks from Chapter 4 are omitted as per your midterm syllabus)*

---

## Exam Structure & Strategy (30 Marks Total)

The midterm exam consists of 3 mandatory multi-part questions (10 marks each):
* **Question 1 (Chapter 1):** Elementary Data Organization + Flowchart + Loop Complexity / Big-$O$ + Naive Pattern Matching.
* **Question 2 (Chapter 2):** Array Storage Theory + 2D/3D Address Calculation + Bubble Sort Pass Tracing / Binary Search Tracing + Complexity Table.
* **Question 3 (Chapter 3):** Array vs. Linked List Comparison + Fast/Slow Pointer or $O(1)$ Deletion Algorithm + `INFO`/`LINK`/`AVAIL` Table Manipulation + Doubly Linked List Operations.

---

# CHAPTER 1: Introduction, Complexity & String Processing (~10 Marks)

---

### Question 1.1: Elementary Data Organization & Primary Key Identification (2 Marks)
*Appeared in:* **Spring 2026 [Q1.a]**, **Spring 2024 [Q1.a]**, **Autumn 2023 [Q1.a]**, **Spring 2023 [Q1.a]**, **Autumn 2022 [Q1.a]**, **Spring 2022 [Q1.a]**

#### Past Exam Variations:
1. **Book Record (Spring 2026, Spring 2023, Spring 2022):**
   > A library maintains a book list containing the following data for each book:  
   > `Name of Authors`, `Title of Book`, `Edition`, `Publisher's Name`, `Year`, `ISBN`  
   > *i)* State the entities, attributes, and entity set of the list.  
   > *ii)* Which attribute can serve as the *primary key* for the list? Explain why.

2. **Student Record (Spring 2024, Autumn 2022):**
   > A professor keeps a class list containing: `Name`, `ID Number`, `Section`, `Total Marks`, `Final Grade`.  
   > *i)* State the entities, attributes, and entity set of the list.  
   > *ii)* Identify the primary key.

3. **Employee Record (Autumn 2023):**
   > A company maintains an employee database containing: `Employee ID`, `Name`, `Department`, `Salary`, `Joining Date`.  
   > *i)* State the entities, attributes, and entity set.  
   > *ii)* Identify the primary key.

#### Key Answer Framework:
* **Entity:** An individual item or object having concrete properties (e.g., A single book, a single student, a single employee).
* **Entity Set:** The collection/set of all similar entities (e.g., The entire collection of books in the library).
* **Attributes:** The characteristics or fields describing each entity (e.g., `ISBN`, `Title`, `Author`).
* **Primary Key:** The attribute that uniquely identifies each entity in the entity set with no duplicate or null values (e.g., `ISBN`, `ID Number`, `Employee ID`).

---

### Question 1.2: Flowcharts & Basic Algorithms (2–3 Marks)
*Appeared in:* **Spring 2026 [Q1.b]**, **Autumn 2025 [Q1.b]**, **Spring 2025 [Q1.b]**, **Spring 2024 [Q1.b]**, **Autumn 2023 [Q1.b]**, **Spring 2023 [Q1.b]**, **Autumn 2022 [Q1.b]**, **Spring 2022 [Q1.b]**

#### High-Yield Flowchart Tasks:
1. **Binary Search Algorithm Flowchart:**  
   * Repeated in Spring 2026, Spring 2024, Autumn 2023, Autumn 2022, Spring 2022.
   * *Components:* Start $\rightarrow$ Initialize $\text{BEG} = 1, \text{END} = N, \text{LOC} = 0 \rightarrow$ Loop condition while $\text{BEG} \le \text{END} \text{ and } \text{DATA}[\text{MID}] \ne \text{ITEM} \rightarrow \text{MID} = \lfloor (\text{BEG} + \text{END}) / 2 \rfloor \rightarrow$ Branch left/right $\rightarrow$ End.
2. **Linear Search Flowchart:**  
   * Repeated in Autumn 2025, Spring 2025, Spring 2023, Spring 2022.
3. **Remove Duplicates from a Sorted Array In-Place:**  
   * Appeared in Spring 2026 [Q1.b OR].
   * Uses two pointers: $i$ (slow/write pointer) and $j$ (fast/read pointer).
4. **Find the Second Largest Element / Smallest Element:**  
   * Autumn 2025 [Q1.b OR], Spring 2025 [Q1.b OR], Spring 2023 [Q1.b OR].
5. **Check whether a given number $N$ is Prime:**  
   * Spring 2024 [Q1.b OR].

---

### Question 1.3: Loop Time Complexity & Asymptotic Analysis (2 Marks)
*Appeared in:* **Spring 2026 [Q1.c]**, **Autumn 2025 [Q1.a]**, **Spring 2025 [Q1.c]**, **Spring 2024 [Q1.c]**, **Autumn 2023 [Q1.c]**, **Spring 2023 [Q1.c]**, **Spring 2022 [Q1.c]**

#### Must-Solve Code Snippets:
1. **Multiplication/Division in Loop Step:**
   ```c
   // Spring 2026 Q1(c)(i)
   int i = 1, count = 0;
   while (i < n) {
       i = i * 3;
       count++;
   }
   // Complexity: O(log_3 n) = O(log n)
   ```
2. **Nested Loop with Logarithmic Inner Bound:**
   ```c
   // Spring 2026 Q1(c)(ii)
   for (int i = 0; i < n; i++) {
       for (int j = n; j > 0; j = j / 2) {
           count++;
       }
   }
   // Outer loop runs n times; inner loop runs log_2 n times.
   // Total Complexity: O(n log n)
   ```
3. **Square Root Condition Loop:**
   ```c
   // Autumn 2023 Q1(c)(ii)
   for (i = 0; i * i < n; i++) {
       for (j = 1; j * j <= n; j++) {
           sum += i * j;
       }
   }
   // Outer loop runs sqrt(n) times; inner loop runs sqrt(n) times.
   // Total Complexity: O(sqrt(n) * sqrt(n)) = O(n)
   ```
4. **Theory Questions:**
   * Why is Big-$O$ notation preferred over measuring execution time in clock seconds? *(Clock time depends on hardware, OS load, compiler optimizations, and background processes; Big-$O$ provides an invariant machine-independent asymptotic upper bound).* [Autumn 2025 Q1.a]
   * Identifying curves on a growth graph: label $O(1), O(\log n), O(n), O(n \log n), O(n^2), O(2^n), O(n!)$. [Autumn 2025 Q1.a]

---

### Question 1.4: String Operations & Naive Pattern Matching (2.5–3 Marks)
*Appeared in:* **Spring 2026 [Q1.d]**, **Autumn 2025 [Q1.c]**, **Spring 2025 [Q1.d]**, **Spring 2024 [Q1.d]**, **Autumn 2023 [Q1.d]**, **Spring 2023 [Q1.d]**, **Autumn 2022 [Q1.d]**, **Spring 2022 [Q1.d]**

#### Exact Numerical Problems from Past Papers:
1. **Spring 2026:**
   * Text $T = \text{"wxwwxwwxxwxxwxw"}$, Pattern $P = \text{"wxxw"}$.
   * Calculate character comparisons $C$ to find the first occurrence index using Naive Pattern Matching.
2. **Autumn 2025:**
   * Text $T = \text{"abaaaccacaaaexx"}$, Pattern $P = \text{"aac"}$.
   * Find comparisons $N$ step-by-step.
   * State best-case and worst-case examples for $|P| = 4, |T| = 10$.
     * *Best-Case example:* $T = \text{"AAAAA..."}$, $P = \text{"BBBB"}$ (Mismatch on 1st character $\rightarrow |T| - |P| + 1$ comparisons).
     * *Worst-Case example:* $T = \text{"AAAAAAAAAA"}$, $P = \text{"AAAB"}$ (Mismatch on last character $\rightarrow (|T| - |P| + 1) \times |P|$ comparisons).
3. **Spring 2025 & Spring 2024:**
   * Text $T = \text{"cbcddcddcdccccddd"}$, Pattern $P = \text{"ccd"}$.
4. **Autumn 2023 (String Primitives):**
   * $S_1 = \text{"GLADIATOR"}$, $S_2 = \text{"DESH"}$, $S_3 = \text{"BAN"}$ (1-indexed).
   * Evaluate in order:
     * $L = \text{LENGTH}(S_3)$
     * $S_4 = \text{DELETE}(S_1, 4, L + 3)$
     * $S_5 = S_3 \,||\, S_2$
     * $S_5 = \text{INSERT}(S_5, 4, S_4)$
     * $\text{INDEX}(S_5, \text{"NGL"})$

---

# CHAPTER 2: Linear Arrays, 2D/3D Arrays, Sorting & Searching (~10 Marks)

---

### Question 2.1: Array Concepts & Memory Representation (1–2 Marks)
*Appeared in:* **Spring 2026 [Q2.a]**, **Autumn 2025 [Q2.a]**, **Spring 2025 [Q2.a]**, **Spring 2024 [Q2.a]**, **Autumn 2023 [Q2.a]**, **Autumn 2022 [Q2.a]**

1. **Definition & Memory Representation:**
   * What is a linear array? How is it represented in computer memory?  
     $$\text{Address}(\text{LA}[K]) = \text{Base}(\text{LA}) + w \cdot (K - \text{Lower Bound})$$
   * Explain Row-Major Order vs. Column-Major Order with a schematic diagram.
2. **Array Operations Algorithms:**
   * Write an algorithm to insert an element $\text{ITEM}$ at the $K$-th position of a linear array $\text{LA}$ of size $N$.  
     *(Show the downward shifting loop from $N$ down to $K$; state time complexity $O(N)$).*
   * What is a Sparse Matrix? Explain 3-tuple / coordinate representation (`Row`, `Col`, `Value`) for memory optimization.

---

### Question 2.2: 2D & 3D Array Address Calculations (2.5–3 Marks)
*Guaranteed numerical problem appearing in EVERY past paper.*

#### Standard Formulas:
* **2D Array $A(L_1:U_1, L_2:U_2)$:**
  * Lengths: $R = U_1 - L_1 + 1$, $C = U_2 - L_2 + 1$
  * Total Elements: $N = R \times C$
  * **Row-Major Order:**
    $$\text{Address}(A[J, K]) = \text{Base}(A) + w \cdot [(J - L_1) \cdot C + (K - L_2)]$$
  * **Column-Major Order:**
    $$\text{Address}(A[J, K]) = \text{Base}(A) + w \cdot [(K - L_2) \cdot R + (J - L_1)]$$

* **3D Array $B(L_1:U_1, L_2:U_2, L_3:U_3)$ (Row-Major Order):**
  * Lengths: $D_1 = U_1 - L_1 + 1$, $D_2 = U_2 - L_2 + 1$, $D_3 = U_3 - L_3 + 1$
  * Effective indices: $E_1 = J - L_1$, $E_2 = K - L_2$, $E_3 = L - L_3$
  * Total Elements: $N = D_1 \times D_2 \times D_3$
  * **Address Formula:**
    $$\text{Address}(B[J, K, L]) = \text{Base}(B) + w \cdot [E_1 \cdot D_2 \cdot D_3 + E_2 \cdot D_3 + E_3]$$

#### Exact Past Exam Problems to Solve:
1. **Spring 2026 [Q2.b]:**
   * Array $A(10:15, 13:20)$, $\text{Base} = 200$, $w = 4$ words.
   * *i)* Find length of each dimension and total elements.
   * *ii)* Find address of $A[13, 17]$ in row-major order.
2. **Autumn 2025 [Q2.b] & Spring 2025 [Q2.b]:**
   * Array $A(4:12, 7:14)$, $\text{Base} = 300$ (or $500$), $w = 8$ bytes (or $4$ bytes).
   * Find address of $A[6, 10]$ in row-major order.
3. **Spring 2024 [Q2.b] (3D Array):**
   * Array $B(1:8, -5:5, -10:5)$, $\text{Base} = 150$, $w = 4$ words.
   * Calculate effective indices $E_1, E_2, E_3$ and the address of $B[2, -3, 2]$ in row-major order.
4. **Spring 2023 [Q2.b] & Spring 2022 [Q2.b] (3D Array):**
   * Array $A(3:10, 1:10, -3:10)$ or $A(5:10, 1:10, -2:10)$.

---

### Question 2.3: Bubble Sort Tracing & Algorithm (3.5–4 Marks)
*Appeared in:* **Spring 2026 [Q2.c]**, **Autumn 2025 [Q2.c]**, **Spring 2025 [Q2.c]**, **Spring 2024 [Q2.c]**, **Autumn 2023 [Q2.c]**, **Spring 2023 [Q2.c]**, **Autumn 2022 [Q2.d]**, **Spring 2022 [Q2.c]**

#### Past Exam Target Strings:
Trace the Bubble Sort pass-by-pass, explicitly writing out the list after every pass and counting:
* Total Comparisons ($C$)
* Total Interchanges/Swaps ($D$)
1. **Spring 2026:** String $\text{"ROBOT"}$
2. **Autumn 2025:** String $\text{"CANDLE"}$
3. **Spring 2025:** String $\text{"BRIDGE"}$
4. **Spring 2024:** String $\text{"STRUCTURES"}$
5. **Spring 2023:** String $\text{"CHITTAGONG"}$
6. **Spring 2022:** String $\text{"MORALITY"}$

#### Algorithm Modification Variation:
* **Modified Early-Exit Bubble Sort:**  
  Write the Bubble Sort algorithm using a boolean flag/swap variable to terminate early if the array is already sorted in pass $K$ ($O(n)$ best-case time). *(Spring 2024 Q2.c OR, Autumn 2023 Q2.c OR).*

---

### Question 2.4: Binary Search Intermediate Trace & Time Complexity (1.5–4 Marks)
*Appeared in:* **Spring 2026 [Q2.c OR, Q2.d]**, **Autumn 2025 [Q2.c OR]**, **Spring 2025 [Q2.c OR, Q2.d]**, **Spring 2024 [Q2.d]**, **Autumn 2023 [Q2.d]**, **Autumn 2022 [Q2.d OR]**

1. **Step-by-Step Binary Search Trace:**
   * Given sorted list: $[10, 15, 22, 28, 34, 41, 47, 56, 63, 70, 78, 85, 92]$
   * Trace the search for $\text{ITEM} = 41$ and $\text{ITEM} = 79$ by displaying a table of $\text{BEG}$, $\text{END}$, and $\text{MID} = \lfloor (\text{BEG} + \text{END}) / 2 \rfloor$ at each step.
2. **Complexity Summary Table (Repeated in Spring 2026, Spring 2025, Spring 2024):**
   Write down the worst-case and average-case time complexities:
   * **Binary Search:** Worst Case $= O(\log n)$, Average Case $= O(\log n)$
   * **Linear Search:** Worst Case $= O(n)$, Average Case $= O(n)$
   * **Bubble Sort:** Worst Case $= O(n^2)$, Average Case $= O(n^2)$

---

# CHAPTER 3: Linked Lists (~10 Marks)

---

### Question 3.1: Array vs. Linked List Comparison (2 Marks)
*Appeared in:* **Spring 2026 [Q3.a]**, **Autumn 2025 [Q3.a]**, **Spring 2025 [Q3.a]**

#### Complete Model Comparison Table:
| Criterion | Array | Singly Linked List |
| :--- | :--- | :--- |
| **Memory Allocation** | Static / Contiguous memory block; fixed size defined at declaration. | Dynamic; non-contiguous heap memory; nodes allocated as needed. |
| **Insertion & Deletion** | Inefficient ($O(n)$) due to extensive element shifting. | Efficient ($O(1)$) if pointer to position is known; only pointers are relinked. |
| **Search Efficiency** | Highly efficient ($O(1)$ random access by index; $O(\log n)$ with binary search on sorted array). | Slower ($O(n)$ linear traversal required; random access / binary search not possible). |
| **Memory Overhead** | Low (stores only data elements). | Higher (each node requires extra memory for `next` / `prev` pointers). |

---

### Question 3.2: Single-Pass & Efficient Linked List Algorithms (3–4 Marks)
*Appeared in:* **Spring 2026 [Q3.b]**, **Autumn 2025 [Q3.b]**, **Spring 2025 [Q3.b]**

#### High-Yield Algorithmic Questions:
1. **$O(1)$ Deletion Without Head Pointer (Spring 2026 Q3.b):**
   > You are given only a pointer to a node (not the head pointer) in a non-empty singly linked list. Write a C/C++ function to delete that node in $O(1)$ time. Under what condition does your approach fail, and why?
   * *Code:*
     ```c
     void deleteNode(Node* ptr) {
         if (ptr == NULL || ptr->next == NULL) return; // Failure condition
         Node* temp = ptr->next;
         ptr->info = temp->info;      // Copy data from successor
         ptr->next = temp->next;      // Bypass successor
         free(temp);                  // Free successor memory
     }
     ```
   * *Failure Condition:* Fails if `ptr` is the **last node (tail)**, because there is no successor to copy data from, and the previous node's link cannot be updated to `NULL` without traversing from the head.

2. **Fast and Slow Pointer Technique (Find Middle Node in Single Pass):**
   * Repeated in Spring 2026 [Q3.b OR], Autumn 2025 [Q3.b], Spring 2025 [Q3.b OR].
   * *Logic:* Two pointers (`slow` and `fast`) initialized to `head`. Move `slow` by 1 step (`slow = slow->next`) and `fast` by 2 steps (`fast = fast->next->next`). When `fast` reaches the end (`fast == NULL` or `fast->next == NULL`), `slow` points precisely to the middle node.
   * *Time Complexity:* $O(n)$ with exactly $\lfloor n/2 \rfloor$ steps (single traversal). Space Complexity: $O(1)$.

3. **Insert at Arbitrary Position $pos$ (Autumn 2025 Q3.c):**
   * Insert at beginning ($pos = 1$): $O(1)$
   * Insert at end ($pos = n + 1$): $O(1)$ if tail pointer maintained, else $O(n)$
   * Insert at intermediate position: $O(n)$ traversal
   * Handle invalid positions: $pos < 1$ or $pos > \text{length} + 1$.

---

### Question 3.3: Pointer Table Tracing (`INFO`, `LINK`, `START`, `AVAIL`) (2–4 Marks)
*Appeared in:* **Spring 2026 [Q3.c, Q3.d]**, **Spring 2025 [Q3.c, Q3.d]**

#### Standard Exam Problem:
Given the following sorted linked list stored across parallel arrays:

| Index | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **`INFO`** | | | 41 | 129 | | 9 | 123 | 78 | 194 | 231 | 62 | 145 |
| **`LINK`** | 2 | 5 | 11 | 12 | 0 | 3 | 4 | 7 | 10 | 0 | 8 | 9 |

$$\text{START} = 6, \quad \text{AVAIL} = 1$$

#### Current List Traversal:
$$\text{Node } 6 (9) \rightarrow 3 (41) \rightarrow 11 (62) \rightarrow 8 (78) \rightarrow 7 (123) \rightarrow 4 (129) \rightarrow 12 (145) \rightarrow 9 (194) \rightarrow 10 (231) \rightarrow 0$$
$$\text{Available Free List: } 1 \rightarrow 2 \rightarrow 5 \rightarrow 0$$

#### Tasks:
1. **Insertion:** Add a new integer $XX$ (e.g., student ID digits $26$) while maintaining sorted order.
   * Allocate cell from `AVAIL`: Node index becomes $1$, $\text{AVAIL}$ updates to $2$.
   * Set $\text{INFO}[1] = 26$.
   * Insert between Node $6$ ($9$) and Node $3$ ($41$):
     * $\text{LINK}[6] = 1$
     * $\text{LINK}[1] = 3$
2. **Deletion:** Delete value $123$ (Node $7$) from the list.
   * Predecessor is Node $8$ ($78$), successor is Node $4$ ($129$).
   * Bypass Node $7$: $\text{LINK}[8] = \text{LINK}[7] = 4$.
   * Return Node $7$ to the free list:
     * $\text{LINK}[7] = \text{AVAIL}$
     * $\text{AVAIL} = 7$
3. **Conversion to Two-Way (Doubly) Linked List:**
   * Introduce a new parallel array `BACK` (or `PREV`) of size 12.
   * Traverse from `START`:
     * $\text{BACK}[\text{START}] = 0$
     * For each step: $\text{BACK}[\text{LINK}[P]] = P$

---

### Question 3.4: Doubly Linked List Address Pointer Tracing (2 Marks)
*Appeared in:* **Autumn 2025 [Q3.b OR]**

Given reading list with 5 books:
| Book Title | Node Address | Previous Address | Next Address |
| :--- | :---: | :---: | :---: |
| Book C | 1502 | 3071 | 4096 |
| Book A | 2005 | NULL | 3071 |
| Book B | 3071 | 2005 | 1502 |
| Book E | 2810 | 4096 | NULL |
| Book D | 4096 | 1502 | 2810 |

#### Sequence:
$$\text{Book A (2005)} \rightleftharpoons \text{Book B (3071)} \rightleftharpoons \text{Book C (1502)} \rightleftharpoons \text{Book D (4096)} \rightleftharpoons \text{Book E (2810)}$$

#### Tasks:
1. Draw the schematic doubly linked list diagram showing data, previous, and next pointers.
2. Insert a new book "Book F" (with an assigned address, e.g., 5000) directly after "Book C" and update links:
   * $\text{Next}(1502) = 5000$, $\text{Prev}(5000) = 1502$
   * $\text{Next}(5000) = 4096$, $\text{Prev}(4096) = 5000$
3. Delete "Book B" (Node 3071) and update links:
   * $\text{Next}(2005) = 1502$
   * $\text{Prev}(1502) = 2005$

---

# 25+ Marks Guaranteed "Must-Master" Checklist

To score at least **25 out of 30**, ensure you can perform the following six calculations and code implementations with zero errors:

- [ ] **Address Calculation:** Practice 2D row-major formula and 3D effective indices formula ($E_1, E_2, E_3$). *(Guaranteed 2.5–3 Marks)*
- [ ] **Bubble Sort Tracing:** Manually trace a 6-letter word (`ROBOT` or `CANDLE`) pass-by-pass, recording total comparisons $C$ and swaps $D$. *(Guaranteed 3.5–4 Marks)*
- [ ] **Linked List Table Tracing:** Practice inserting an ID number and deleting a node using `INFO`, `LINK`, `START`, and `AVAIL` arrays. *(Guaranteed 2–4 Marks)*
- [ ] **Naive Pattern Matching:** Trace pattern matching for given $T$ and $P$ and count character comparisons step-by-step. *(Guaranteed 3 Marks)*
- [ ] **Algorithms & Flowcharts:**
  - Binary Search flowchart. *(3 Marks)*
  - Single-pass Fast/Slow pointer algorithm to find the middle of a linked list. *(3–4 Marks)*
  - $O(1)$ node deletion function and its failure condition. *(2 Marks)*
- [ ] **Theory:** Entity/Attribute/Primary Key identification + Array vs. Linked List comparison table. *(4 Marks combined)*