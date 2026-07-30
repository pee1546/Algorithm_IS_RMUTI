## บทที่ 3: โครงสร้างข้อมูลแบบสแตก (Stack Data Structure)

### 3.1 คุณลักษณะและหลักการของสแตก
* **หลักการ**: **LIFO (Last-In, First-Out)** คือ "เข้าทีหลัง ออกก่อน"
* **การเข้าถึง**: ทำได้เพียงปลายด้านเดียวเท่านั้น เรียกว่า **TOP** (Top of Stack)
* **ตัวชี้ (Stack Pointer: SP / TOP)**:
  * ถ้าสแตกว่างเปล่า ค่า `TOP = 0` (หรือ `-1` ขึ้นกับ Index ภาษา)

### 3.2 การดำเนินการหลักบนสแตก (Stack Operations)
1. **Push(ITEM)**: การนำข้อมูลใส่ลงสแตก
   * *เงื่อนไขต้องระวัง*: ตรวจสอบ **STACK OVERFLOW** (เมื่อ `TOP == MAX`)
   * *ขั้นตอน*:
     1. `TOP = TOP + 1`
     2. `STACK[TOP] = ITEM`
2. **Pop(ITEM)**: การนำข้อมูลออกจากสแตก
   * *เงื่อนไขต้องระวัง*: ตรวจสอบ **STACK UNDERFLOW** (เมื่อ `TOP == 0`)
   * *ขั้นตอน*:
     1. `ITEM = STACK[TOP]`
     2. `TOP = TOP - 1`

### 3.3 การแปลงนิพจน์พีชคณิต (Infix to Postfix Conversion)
* **รูปแบบนิพจน์**:
  * **Infix**: Operator อยู่กลางระหว่าง Operand เช่น $A + B$
  * **Postfix (Reverse Polish)**: Operator อยู่หลัง Operand เช่น $AB+$
  * **Prefix**: Operator อยู่หน้า Operand เช่น $+AB$
* **ลำดับความสำคัญของตัวดำเนินการ (Operator Precedence)**:
  1. วงเล็บ `()`
  2. ยกกำลัง `^` หรือ `**` (Precedence = 3)
  3. คูณ / หาร `*`, `/` (Precedence = 2)
  4. บวก / ลบ `+`, `-` (Precedence = 1)
* **กฎการแปลงนิพจน์ Infix $
ightarrow$ Postfix โดยใช้ Stack (`opst`)**:
  1. ถ้าเจอ **Operand** $
ightarrow$ ส่งไปที่ Output ทันที
  2. ถ้าเจอ **Operator**:
     * ถ้า `opst` ว่าง หรือ Operator Input มี Precedence **สูงกว่า** ตัวบนสุดใน `opst` $
ightarrow$ **PUSH** ลง `opst`
     * ถ้า Operator Input มี Precedence **น้อยกว่าหรือเท่ากับ** ตัวบนสุดใน `opst` $
ightarrow$ **POP** ตัวใน `opst` ออกไป Output จนกว่าจะเจอตัวที่เล็กกว่า หรือเจอ `(` หรือสแตกว่าง แล้วจึง **PUSH** Operator Input ลงไป
  3. ถ้าเจอ **วงเล็บเปิด `(`** $
ightarrow$ **PUSH** ลง `opst` ทันที
  4. ถ้าเจอ **วงเล็บปิด `)`** $
ightarrow$ **POP** ตัวดำเนินการใน `opst` ไปไว้ Output เรื่อยๆ จนกว่าจะเจอ `(` (ทิ้งวงเล็บทั้งคู่)
  5. เมื่ออ่าน Input หมด $
ightarrow$ **POP** ตัวดำเนินการที่เหลือทั้งหมดใน `opst` ออกไปไว้ที่ Output

### 3.4 การหาผลลัพธ์จากนิพจน์ Postfix (Postfix Evaluation)
* **ขั้นตอน**:
  1. สแกนนิพจน์ Postfix จากซ้ายไปขวา
  2. ถ้าเจอ **Operand** $
ightarrow$ **PUSH** เข้า Stack
  3. ถ้าเจอ **Operator** $
ightarrow$ **POP** ข้อมูล 2 ตัวออกจาก Stack
     * ให้ $A$ = ข้อมูลที่ Pop ตัวที่สอง (Operand 1)
     * ให้ $B$ = ข้อมูลที่ Pop ตัวแรก (Operand 2)
     * คำนวณ $	ext{Result} = A 	ext{ Operator } B$
     * **PUSH** Result กลับเข้า Stack
  4. ค่าสุดท้ายที่เหลือใน Stack คือคำตอบ

### 3.5 การเขียนโปรแกรมแบบเรียกตัวเอง (Recursion)
* **แนวคิด**: การแก้ปัญหาโดยเรียกใช้ฟังก์ชันตัวเองซ้ำ เช่น แฟกทอเรียล $n! = n 	imes (n-1)!$ โดยมี Base Case คือ $0! = 1$
* คอมพิวเตอร์จะใช้ **Stack** ภายในระบบเพื่อเก็บค่า Local Variables และ Return Address ของฟังก์ชันแต่ละรอบ

---