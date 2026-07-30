# บทที่ 3: โครงสร้างข้อมูลแบบสแตก (Stack Data Structure)[cite: 3]

## 3.1 คุณลักษณะและหลักการ[cite: 3]
* **หลักการ**: **LIFO (Last-In, First-Out)** "เข้าทีหลัง ออกก่อน"[cite: 3]
* **จุดเข้าถึง**: ทำได้ทางปลายด้านเดียวเรียกว่า **TOP** (Top of Stack)[cite: 3]
* **สแตกว่าง**: `TOP = 0` (หรือ `-1`)[cite: 3, 4]

---

## 3.2 การดำเนินการหลักบนสแตก[cite: 3]
1. **Push(ITEM)**: นำข้อมูลใส่ลงสแตก[cite: 3]
   * *ระวัง*: **STACK OVERFLOW** (เมื่อ `TOP == MAX`)[cite: 3]
   * *ขั้นตอน*:
     ```text
     TOP = TOP + 1
     STACK[TOP] = ITEM
     ```[cite: 3]
2. **Pop(ITEM)**: นำข้อมูลออกจากสแตก[cite: 3]
   * *ระวัง*: **STACK UNDERFLOW** (เมื่อ `TOP == 0`)[cite: 3]
   * *ขั้นตอน*:
     ```text
     ITEM = STACK[TOP]
     TOP = TOP - 1
     ```[cite: 3]

---

## 3.3 การแปลงนิพจน์ Infix เป็น Postfix[cite: 3]
* **รูปแบบนิพจน์**:
  * **Infix**: $A + B$[cite: 3]
  * **Postfix (Reverse Polish)**: $AB+$[cite: 3]
  * **Prefix**: $+AB$[cite: 3]
* **ลำดับความสำคัญ (Precedence)**: วงเล็บ `()` > ยกกำลัง `^` (3) > คูณ/หาร `*`, `/` (2) > บวก/ลบ `+`, `-` (1)[cite: 3]
* **กฎการแปลงโดยใช้ Stack (`opst`)**:
  1. ถ้าเจอ **Operand** $\rightarrow$ ส่งไป Output[cite: 3]
  2. ถ้าเจอ **Operator**:
     * ถ้า `opst` ว่าง หรือ Input มี Precedence **สูงกว่า** ตัวบนสุดใน `opst` $\rightarrow$ **PUSH**[cite: 3]
     * ถ้า Input มี Precedence **น้อยกว่าหรือเท่ากับ** ตัวบนสุดใน `opst` $\rightarrow$ **POP** ออกไป Output จนกว่าจะเจอตัวที่เล็กกว่า แล้วจึง **PUSH** Input ลงไป[cite: 3]
  3. เจอ **`(`** $\rightarrow$ **PUSH** ลง `opst`[cite: 3]
  4. เจอ **`)`** $\rightarrow$ **POP** ออกไป Output จนกว่าจะเจอ `(` (ทิ้งวงเล็บทั้งคู่)[cite: 3]

---

## 3.4 การหาผลลัพธ์จากนิพจน์ Postfix[cite: 3]
1. อ่านจากซ้ายไปขวา[cite: 3]
2. เจอ **Operand** $\rightarrow$ **PUSH** ลง Stack[cite: 3]
3. เจอ **Operator** $\rightarrow$ **POP** ข้อมูล 2 ตัวจาก Stack:
   * $A$ = Pop ตัวที่สอง (Operand 1)[cite: 3]
   * $B$ = Pop ตัวแรก (Operand 2)[cite: 3]
   * คำนวณ $\text{Result} = A \text{ Operator } B$ แล้ว **PUSH** ผลลัพธ์กลับเข้า Stack[cite: 3]

---

## 3.5 การเขียนโปรแกรมแบบเรียกตัวเอง (Recursion)[cite: 3]
* การแก้ปัญหาโดยฟังก์ชันเรียกตัวเองซ้ำ เช่น แฟกทอเรียล $n! = n \times (n-1)!$ โดยมี Base Case $0! = 1$[cite: 3]
* คอมพิวเตอร์จะใช้ **Stack** ภายในระบบในการบันทึกค่าและ Return Address[cite: 3]