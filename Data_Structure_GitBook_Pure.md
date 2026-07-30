# คู่มือสรุปเนื้อหาและเตรียมตัวสอบ: วิชาโครงสร้างข้อมูลและอัลกอริทึม (Data Structure and Algorithm)
## สรุปเจาะลึก Slide บทที่ 1 - 5 (สาขาวิชาระบบสารสนเทศ คณะบริหารธุรกิจ)

---

## 📋 สารบัญ (Table of Contents)
1. [บทที่ 1: ความรู้เบื้องต้นเกี่ยวกับโครงสร้างข้อมูลและอัลกอริทึม](#บทที่-1-ความรู้เบื้องต้นเกี่ยวกับโครงสร้างข้อมูลและอัลกอริทึม)
2. [บทที่ 2: โครงสร้างข้อมูลแบบอาร์เรย์ (Array Data Structure)](#บทที่-2-โครงสร้างข้อมูลแบบอาร์เรย์-array-data-structure)
3. [บทที่ 3: โครงสร้างข้อมูลแบบสแตก (Stack Data Structure)](#บทที่-3-โครงสร้างข้อมูลแบบสแตก-stack-data-structure)
4. [บทที่ 4: โครงสร้างข้อมูลแบบคิว (Queue Data Structure)](#บทที่-4-โครงสร้างข้อมูลแบบคิว-queue-data-structure)
5. [บทที่ 5: โครงสร้างข้อมูลแบบลิงค์ลิสต์ (Linked List Data Structure)](#บทที่-5-โครงสร้างข้อมูลแบบลิงค์ลิสต์-linked-list-data-structure)
6. [🎯 สรุปจุดเน้นยอดฮิตที่มักออกสอบประจำ (Exam Highlights & Key Formulas)](#-สรุปจุดเน้นยอดฮิตที่มักออกสอบประจำ-exam-highlights--key-formulas)

---

## บทที่ 1: ความรู้เบื้องต้นเกี่ยวกับโครงสร้างข้อมูลและอัลกอริทึม

### 1.1 ความหมายและเป้าหมายของโครงสร้างข้อมูล
* **นิยาม**: รูปแบบความสัมพันธ์ของข้อมูลที่จัดเก็บอยู่ในหน่วยความจำคอมพิวเตอร์อย่างเป็นระเบียบ เพื่อให้เข้าถึงและจัดการข้อมูลได้อย่างมีประสิทธิภาพ
* **สมการพื้นฐานของโปรแกรม**:
  $$\text{Data} + \text{Algorithms} = \text{Program}$$
* **จุดมุ่งหมายหลัก**:
  1. ใช้พื้นที่หน่วยความจำน้อยที่สุด (Minimizing Memory Utilization / Space Efficiency)
  2. ใช้เวลาในการประมวลผลสั้นที่สุด (Minimizing Processing Time / Time Efficiency)

### 1.2 ลำดับขั้นของข้อมูล (Data Hierarchy)
เรียงลำดับจากขนาดเล็กที่สุดไปใหญ่ที่สุด:
$$\text{Bit} \rightarrow \text{Byte} \rightarrow \text{Field} \rightarrow \text{Record} \rightarrow \text{File} \rightarrow \text{Database}$$
* **Bit (Binary Digit)**: หน่วยที่เล็กที่สุด (0 หรือ 1)
* **Byte**: ตัวอักษร 1 ตัว (8 Bits = 1 Byte เช่น ASCII ของอักขระ 'I' คือ `01001001`)
* **Field**: อักขระหลายตัวรวมกันเป็นความหมาย เช่น `Student_ID`, `Course`
* **Record**: การรวมฟิลด์ที่มีความสัมพันธ์กัน เช่น ข้อมูลของนักศึกษา 1 คน
* **File**: การรวมเรคอร์ดประเภทเดียวกันเข้าด้วยกัน
* **Database**: การรวมไฟล์ข้อมูลที่มีความสัมพันธ์กันเข้าด้วยกัน

### 1.3 ประเภทของโครงสร้างข้อมูล (Types of Data Structures)
แบ่งตามโครงสร้างออกเป็น 2 ประเภทใหญ่:
1. **โครงสร้างข้อมูลทางกายภาพ (Physical Data Structure)**:
   * **ข้อมูลเบื้องต้น (Primitive Data Type)**: ข้อมูลพื้นฐานในภาษาโปรแกรม เช่น Integer, Real/Float, Character, Boolean
   * **ข้อมูลโครงสร้าง (Structure Data Type)**: เกิดจากการนำข้อมูลเบื้องต้นมาประกอบกัน เช่น Array, Record, File
2. **โครงสร้างข้อมูลทางตรรกะ (Logical Data Structure)**:
   * **เชิงเส้น (Linear Data Structure)**: จัดเก็บต่อเนื่องและเข้าถึงตามลำดับ ได้แก่ **Array, Stack, Queue, Linked List**
   * **ไม่เชิงเส้น (Non-Linear Data Structure)**: จัดเก็บไม่ต่อเนื่องและระบุตำแหน่งด้วยความสัมพันธ์/กิ่งก้าน ได้แก่ **Tree, Graph**

### 1.4 การแทนที่ข้อมูลในหน่วยความจำ (Data Representation)
* **Static Memory Representation**:
  * จองพื้นที่แน่ชัดไว้ล่วงหน้า (เช่น Array)
  * *ข้อดี*: เขียนโปรแกรมง่าย เข้าถึงข้อมูลสุ่มได้ไว
  * *ข้อเสีย*: ปรับขนาดไม่ได้ เกิดปัญหาสูญเสียพื้นที่ (ถ้าใช้น้อยกว่าจอง) หรือ Memory Overflow (ถ้าข้อมูลเกิน)
* **Dynamic Memory Representation**:
  * จองพื้นที่ยืดหยุ่นตามความต้องการ ณ เวลาประมวลผล (Runtime) ผ่านตัวชี้ (Pointer)
  * *ข้อดี*: ใช้หน่วยความจำมีประสิทธิภาพสูง ไม่สูญเปล่า
  * *ข้อเสีย*: การเขียนโปรแกรมและจัดการ Pointer ซับซ้อนกว่า

### 1.5 ขั้นตอนการพัฒนาโปรแกรมและวิเคราะห์งาน (SDLC & Job Analysis)
* **SDLC 5 ขั้นตอน**: Plan $\rightarrow$ Design $\rightarrow$ Develop $\rightarrow$ Deploy $\rightarrow$ Maintenance
* **องค์ประกอบการวิเคราะห์โจทย์ (Job Analysis)**:
  1. สิ่งที่โจทย์ต้องการ (Requirement/Goal)
  2. ข้อมูลนำเข้า (Input) & ตัวแปรที่ใช้ (Variables)
  3. ผลลัพธ์ที่ต้องการ (Output)
  4. วิธีการประมวลผล (Processing / Algorithm Steps)

### 1.6 เครื่องมือออกแบบอัลกอริทึม (Algorithm Design Tools)
1. **ผังงาน (Flowchart)**: ใช้สัญลักษณ์มาตรฐานแสดงขั้นตอน
   * `Terminator` (วงกลมมน): เริ่มต้น/สิ้นสุด (START/STOP)
   * `Process` (สี่เหลี่ยมผืนผ้า): คำนวณ/กำหนดค่า
   * `Input/Output` (สี่เหลี่ยมด้านขนาน): รับ/แสดงข้อมูลทั่วไป
   * `Decision` (สี่เหลี่ยมขนมดียกปูน): เปรียบเทียบ/ตัดสินใจ (IF / Case)
   * `Display` / `Printer`: แสดงผลทางจอภาพ / พริ้นเตอร์
   * `Preparation` (หกเหลี่ยม): กำหนดค่าล่วงหน้า (For loop)
   * `Connector` (วงกลม): จุดเชื่อมต่อในหน้าเดียวกัน / `Off-page`: เชื่อมต่อคนละหน้า
   * **โครงสร้าง Flowchart**:
     * แบบลำดับ (Sequential)
     * แบบทางเลือก (Selection: Single IF, Double IF, Multi-IF, Case)
     * แบบวนซ้ำ (Repetition: **Do-While** [ตรวจก่อนทำ], **Repeat-Until** [ทำก่อนตรวจอย่างน้อย 1 ครั้ง], **For** [รู้จำนวนรอบแน่นอน])
2. **รหัสเทียม (Pseudo Code)**: ข้อความภาษาอังกฤษจำลองโครงสร้างโปรแกรม
   * คำสำคัญ: `BEGIN`, `END`, `SET` / `INITIALIZE`, `READ` / `INPUT`, `WRITE` / `PRINT`, `IF-THEN-ELSE-ENDIF`, `CASE-ENDCASE`, `DO WHILE-ENDDO`, `REPEAT-UNTIL`

### 1.7 ประสิทธิภาพของอัลกอริทึมและ Big-O Notation
* **การวัดประสิทธิภาพ**:
  1. **Space Utilization**: พื้นที่หน่วยความจำที่ใช้
  2. **Time Efficiency**: เวลาในการคอมไพล์ (Compile Time) และเวลาประมวลผลจริง (Running Time / $T(n)$)
* **ปัจจัยของข้อมูลนำเข้า**: Worst-case ($T_{worst}(n)$), Average-case ($T_{avg}(n)$), Best-case ($T_{best}(n)$)
* **การเรียงลำดับ อัตราการเติบโตของฟังก์ชัน Big-O (จากเร็วที่สุดไปช้าที่สุด)**:
  $$O(1) < O(\log_2 n) < O(n) < O(n \log_2 n) < O(n^2) < O(n^3) < O(n^k) < O(2^n) < O(n!)$$
* **วิเคราะห์รูปแบบการวนลูป (Loop Analysis)**:
  * **Linear Loop**: `for(i=0; i<n; i++)` $\rightarrow O(n)$
  * **Step Linear Loop**: `for(i=0; i<n; i+=2)` $\rightarrow f(n)=n/2 \rightarrow O(n)$
  * **Logarithmic Loop**: `for(i=1; i<n; i*=2)` หรือ `i/=2` $\rightarrow O(\log_2 n)$
  * **Nested Loop (Independent)**: ลูปนอก $n$ ลูปใน $n \rightarrow O(n^2)$
  * **Nested Loop (Linear Logarithmic)**: ลูปนอก $n$ ลูปใน $\log n \rightarrow O(n \log n)$
  * **Dependent Loop**: ลูปในขึ้นกับ $i \rightarrow 1+2+...+n = \frac{n(n+1)}{2} = \frac{n^2+n}{2} \rightarrow O(n^2)$

---

## บทที่ 2: โครงสร้างข้อมูลแบบอาร์เรย์ (Array Data Structure)

### 2.1 คุณลักษณะของอาร์เรย์
1. **Homogeneous Data Type**: สมาชิกทุกตัวต้องมีประเภทข้อมูลเดียวกัน
2. **Contiguous Memory**: จัดเก็บในหน่วยความจำเรียงติดต่อกัน
3. **Static Structure**: มีขนาดแน่นอน จองพื้นที่ล่วงหน้า
4. **Random Access**: เข้าถึงสมาชิกทุกตัวได้โดยตรงผ่าน Index/Subscript ด้วยเวลา $O(1)$

### 2.2 อาร์เรย์ 1 มิติ (One-Dimensional Array)
* **การคำนวณจำนวนช่อง (Total Elements)**:
  $$\text{Elements} = U - L + 1$$
  *(เมื่อ $U$ คือ Upper Bound, $L$ คือ Lower Bound)*
* **การคำนวณขนาดความจุ (Capacity in Bytes)**:
  $$\text{Capacity} = (U - L + 1) \times \text{Size}$$
* **สูตรคำนวณแอดเดรสตำแหน่ง $A[i]$ ในหน่วยความจำ**:
  $$\text{Loc}(A[i]) = B + C \times (i - L)$$
  * $B$ = Base Address (แอดเดรสเริ่มต้น)
  * $C$ = ขนาดของข้อมูลแต่ละช่อง (Bytes)
  * $i$ = Index ตำแหน่งที่ต้องการหา
  * $L$ = Lower Bound (ตำแหน่งแรกของอาร์เรย์)

> 💡 **ตัวอย่างคำนวณ 1 มิติ**:
> กำหนดให้อาร์เรย์ $A[1:5]$ มี Base Address ($B$) = 2000, ขนาดข้อมูลแต่ละช่อง ($C$) = 1 Byte
> จงหาแอดเดรสของ $A[3]$:
> $$\text{Loc}(A[3]) = 2000 + 1 \times (3 - 1) = 2000 + 2 = 2002$$

### 2.3 อาร์เรย์ 2 มิติ (Two-Dimensional Array)
* **รูปแบบ**: $A[L_1:U_1, L_2:U_2]$ หรือ $A[M, N]$ โดย $M$ = จำนวนแถว (Rows), $N$ = จำนวนคอลัมน์ (Columns)
  * $M = U_1 - L_1 + 1$
  * $N = U_2 - L_2 + 1$
* **จำนวนช่องทั้งหมด**: $M \times N = (U_1 - L_1 + 1) \times (U_2 - L_2 + 1)$
* **รูปแบบการจัดเก็บในหน่วยความจำ**:
  1. **เรียงตามแถวเป็นหลัก (Row Major Order)**: จัดเก็บทีละแถวเรียงกันไป
     $$\text{Loc}(A[i, j]) = B + C \times [(i - L_1) \times N + (j - L_2)]$$
  2. **เรียงตามคอลัมน์เป็นหลัก (Column Major Order)**: จัดเก็บทีละคอลัมน์เรียงกันไป
     $$\text{Loc}(A[i, j]) = B + C \times [(j - L_2) \times M + (i - L_1)]$$

> 💡 **ตัวอย่างคำนวณ 2 มิติ**:
> กำหนดอาร์เรย์ $A[1:5, 1:10]$ ($M=5, N=10$), $B = 1050$, $C = 4$ Bytes จงหาแอดเดรส $A[3, 5]$
> * **Row Major Order**:
>   $$\text{Loc}(A[3, 5]) = 1050 + 4 \times [(3-1) \times 10 + (5-1)] = 1050 + 4 \times (20 + 4) = 1050 + 96 = 1146$$
> * **Column Major Order**:
>   $$\text{Loc}(A[3, 5]) = 1050 + 4 \times [(5-1) \times 5 + (3-1)] = 1050 + 4 \times (20 + 2) = 1050 + 88 = 1138$$

### 2.4 อาร์เรย์ 3 มิติ (Three-Dimensional Array)
* **รูปแบบ**: $A[L_1:U_1, L_2:U_2, L_3:U_3]$ หรือ $A[L, M, N]$
  * $L$ = จำนวนชั้น/ความลึก (Pages) $= U_1 - L_1 + 1$
  * $M$ = จำนวนแถว (Rows) $= U_2 - L_2 + 1$
  * $N$ = จำนวนคอลัมน์ (Columns) $= U_3 - L_3 + 1$
* **จำนวนช่องทั้งหมด**: $L \times M \times N$
* **สูตรหาแอดเดรสตำแหน่ง $A[i, j, k]$**:
  1. **Row Major Order**:
     $$\text{Loc}(A[i, j, k]) = B + C \times [(i - L_1) \times M \times N + (j - L_2) \times N + (k - L_3)]$$
  2. **Column Major Order**:
     $$\text{Loc}(A[i, j, k]) = B + C \times [(i - L_1) \times M \times N + (k - L_3) \times M + (j - L_2)]$$

---

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
* **กฎการแปลงนิพจน์ Infix $\rightarrow$ Postfix โดยใช้ Stack (`opst`)**:
  1. ถ้าเจอ **Operand** $\rightarrow$ ส่งไปที่ Output ทันที
  2. ถ้าเจอ **Operator**:
     * ถ้า `opst` ว่าง หรือ Operator Input มี Precedence **สูงกว่า** ตัวบนสุดใน `opst` $\rightarrow$ **PUSH** ลง `opst`
     * ถ้า Operator Input มี Precedence **น้อยกว่าหรือเท่ากับ** ตัวบนสุดใน `opst` $\rightarrow$ **POP** ตัวใน `opst` ออกไป Output จนกว่าจะเจอตัวที่เล็กกว่า หรือเจอ `(` หรือสแตกว่าง แล้วจึง **PUSH** Operator Input ลงไป
  3. ถ้าเจอ **วงเล็บเปิด `(`** $\rightarrow$ **PUSH** ลง `opst` ทันที
  4. ถ้าเจอ **วงเล็บปิด `)`** $\rightarrow$ **POP** ตัวดำเนินการใน `opst` ไปไว้ Output เรื่อยๆ จนกว่าจะเจอ `(` (ทิ้งวงเล็บทั้งคู่)
  5. เมื่ออ่าน Input หมด $\rightarrow$ **POP** ตัวดำเนินการที่เหลือทั้งหมดใน `opst` ออกไปไว้ที่ Output

### 3.4 การหาผลลัพธ์จากนิพจน์ Postfix (Postfix Evaluation)
* **ขั้นตอน**:
  1. สแกนนิพจน์ Postfix จากซ้ายไปขวา
  2. ถ้าเจอ **Operand** $\rightarrow$ **PUSH** เข้า Stack
  3. ถ้าเจอ **Operator** $\rightarrow$ **POP** ข้อมูล 2 ตัวออกจาก Stack
     * ให้ $A$ = ข้อมูลที่ Pop ตัวที่สอง (Operand 1)
     * ให้ $B$ = ข้อมูลที่ Pop ตัวแรก (Operand 2)
     * คำนวณ $\text{Result} = A \text{ Operator } B$
     * **PUSH** Result กลับเข้า Stack
  4. ค่าสุดท้ายที่เหลือใน Stack คือคำตอบ

### 3.5 การเขียนโปรแกรมแบบเรียกตัวเอง (Recursion)
* **แนวคิด**: การแก้ปัญหาโดยเรียกใช้ฟังก์ชันตัวเองซ้ำ เช่น แฟกทอเรียล $n! = n \times (n-1)!$ โดยมี Base Case คือ $0! = 1$
* คอมพิวเตอร์จะใช้ **Stack** ภายในระบบเพื่อเก็บค่า Local Variables และ Return Address ของฟังก์ชันแต่ละรอบ

---

## บทที่ 4: โครงสร้างข้อมูลแบบคิว (Queue Data Structure)

### 4.1 คุณลักษณะและหลักการของคิว
* **หลักการ**: **FIFO (First-In, First-Out)** คือ "เข้าก่อน ออกก่อน"
* **ปลายทางใช้งาน (2 Ends)**:
  * **REAR (หางคิว)**: ใช้สำหรับเพิ่มข้อมูลเข้าคิว (Enqueue / Add)
  * **FRONT (หัวคิว)**: ใช้สำหรับนำข้อมูลออกจากคิว (Dequeue / Delete)
* **สถานะเริ่มต้น (คิวว่าง)**: `Front = 0, Rear = -1` (หรือ `Front = -1, Rear = -1`)

### 4.2 การดำเนินการบนคิวแบบเชิงเส้น (Linear Queue)
1. **การนำข้อมูลเข้าคิว (Enqueue / Add)**:
   * ตรวจสอบ **OVERFLOW** (เมื่อ `Rear == ArraySize - 1`)
   * `Rear = Rear + 1`
   * `QUEUE[Rear] = ITEM`
2. **การนำข้อมูลออกจากคิว (Dequeue / Remove)**:
   * ตรวจสอบ **UNDERFLOW** (เมื่อ `Rear < Front` หรือคิวว่าง)
   * `ITEM = QUEUE[Front]`
   * `Front = Front + 1`
* **สถานการณ์พิเศษของคิว**:
  * คิวว่าง: `Rear < Front`
  * คิวมีสมาชิก 1 ตัว: `Front == Rear`
  * คิวเต็มแบบปกติ: `Rear == ArraySize - 1`

### 4.3 ปัญหาของคิวเชิงเส้นและคิวแบบวงกลม (Circular Queue)
* **ปัญหาของคิวเชิงเส้น**: เมื่อมีการ Dequeue พื้นที่ด้านหน้าจะว่าง แต่ไม่สามารถนำกลับมาใช้ใหม่ได้เนื่องจาก `Rear` ชี้ติดขอบขวาแล้วเรียกว่า **False Overflow**
* **คิวแบบวงกลม (Circular Queue)**:
  * นำส่วนท้ายอาร์เรย์มาเชื่อมต่อกับส่วนหัว
  * **การเพิ่มข้อมูล**: เลื่อน `Rear` ไปตำแหน่งถัดไป ถ้า `Rear == Size - 1` จะวนกลับไป `Rear = 0`
  * **การลบข้อมูล**: เลื่อน `Front` ไปตำแหน่งถัดไป ถ้า `Front == Size - 1` จะวนกลับไป `Front = 0`
  * **เงื่อนไขคิววงกลมเต็ม**: `(Rear + 1) % Size == Front` หรือ `Front == Rear + 1`

---

## บทที่ 5: โครงสร้างข้อมูลแบบลิงค์ลิสต์ (Linked List Data Structure)

### 5.1 ความหมายและโครงสร้างของโหนด (Node)
* **นิยาม**: โครงสร้างข้อมูลเชิงเส้นที่มีขนาดไม่ตายตัว (Dynamic Structure) จัดเก็บไม่จำเป็นต้องเรียงติดต่อกันในหน่วยความจำ
* **องค์ประกอบของ 1 โหนด (Node)**:
  1. **INFO / DATA**: ส่วนที่ใช้เก็บข้อมูลจริง
  2. **LINK / NEXT / POINTER**: ส่วนที่เก็บแอดเดรสชี้ไปยังโหนดถัดไป (โหนดสุดท้ายจะชี้ไปที่ `NULL` หรือ `^`)

### 5.2 การจัดสรรหน่วยความจำ (Memory Allocation)
* **Free Storage Pool / Storage Pool**: กลุ่มของโหนดว่างในหน่วยความจำที่พร้อมให้ดึงไปใช้ โดยมี Pointer ชื่อ **`AVAIL`** ชี้ไปยังโหนดว่างแรก
* เมื่อต้องการสร้างโหนดใหม่ จะดึงโหนดจาก `AVAIL` เมื่อลบโหนดจะนำโหนดนั้นคืนกลับไปที่ `AVAIL`

### 5.3 ลิงค์ลิสต์เดี่ยว (Singly Linked List)
แต่ละโหนดมีตัวชี้ทิศทางเดียว (`LINK`) ชี้ไปข้างหน้า
* **ตัวชี้หลัก**: `Head` (ชี้โหนดแรก) และ `Tail` (ชี้โหนดสุดท้าย)

#### อัลกอริทึมปฏิบัติการบน Singly Linked List:
1. **การสร้างโหนดแรก**:
   `New(P)`, `Data(P) = X`, `Next(P) = NULL`, `Head = P`, `Tail = P`
2. **การเพิ่มโหนดต่อจากโหนดสุดท้าย (Append)**:
   `New(P)`, `Data(P) = X`, `Next(P) = NULL`, `Next(Tail) = P`, `Tail = P`
3. **การเพิ่มโหนดไว้ก่อนหน้าโหนดแรก (Prepend)**:
   `New(P)`, `Data(P) = X`, `Next(P) = Head`, `Head = P`
4. **การแทรกโหนดใหม่ไว้หลังโหนด P**:
   `Next(Newnode) = Next(P)`, `Next(P) = Newnode`
5. **การลบโหนดแรก**:
   `Head = Next(Head)`
6. **การลบโหนดตรงกลาง (ลบโหนดถัดจาก BeforeP)**:
   `Next(BeforeP) = Next(P)` *(เมื่อ P คือโหนดที่ต้องการลบ)*
7. **การลบโหนดสุดท้าย**:
   `Tail = BeforeP`, `Next(Tail) = NULL`

### 5.4 ลิงค์ลิสต์คู่ (Doubly Linked List)
แต่ละโหนดมีพอยน์เตอร์ 2 ทิศทาง:
$$\text{[ LLINK / PREV } | \text{ DATA } | \text{ RLINK / NEXT ]}$$
* **LLINK / PREV**: ชี้ไปยังโหนดก่อนหน้า
* **RLINK / NEXT**: ชี้ไปยังโหนดถัดไป

#### อัลกอริทึมปฏิบัติการบน Doubly Linked List:
1. **เพิ่มโหนดใหม่ก่อนโหนดแรก**:
   `Next(P) = Head`, `Prev(P) = NULL`, `Prev(Head) = P`, `Head = P`
2. **เพิ่มโหนดใหม่ต่อจากโหนดสุดท้าย**:
   `Next(P) = NULL`, `Prev(P) = Tail`, `Next(Tail) = P`, `Tail = P`
3. **แทรกโหนดใหม่ก่อนหน้าโหนด P**:
   `Prev(P) = Newnode`, `Next(Newnode) = P`, `Prev(Newnode) = Prev(P)`, `Next(Prev(P)) = Newnode`
4. **แทรกโหนดใหม่หลังโหนด P**:
   `Prev(Next(P)) = Newnode`, `Next(Newnode) = Next(P)`, `Prev(Newnode) = P`, `Next(P) = Newnode`
5. **ลบโหนด P ตรงกลาง**:
   `Next(Prev(P)) = Next(P)`, `Prev(Next(P)) = Prev(P)`

### 5.5 ลิงค์ลิสต์แบบวงกลม (Circular Linked List)
* **Circular Singly Linked List**: `Next` ของโหนดสุดท้ายชี้กลับมาที่ `Head`
* **Circular Doubly Linked List**: `RLINK` ของโหนดสุดท้ายชี้มาที่ `Head` และ `LLINK` ของโหนดแรกชี้ไปที่ `Tail`

---

## 🎯 สรุปจุดเน้นยอดฮิตที่มักออกสอบประจำ (Exam Highlights & Key Formulas)

### 📌 1. ตารางเปรียบเทียบโครงสร้างข้อมูลเชิงเส้น (Linear Comparison)
| โครงสร้างข้อมูล | หลักการทำงาน | จุดเด่น | ปัญหา/ข้อจำกัด |
| :--- | :--- | :--- | :--- |
| **Array** | Random Access ($O(1)$) | เข้าถึงข้อมูลได้เร็วมากผ่าน Index | ขนาดคงที่ (Static), เสียเวลาเลื่อนข้อมูลเมื่อ Insert/Delete |
| **Stack** | **LIFO** (Last-In First-Out) | จัดการลำดับการทำงานย้อนกลับ, Recursion, Infix/Postfix | เกิด Overflow ถ้าจอง Array ไว้เต็ม |
| **Queue** | **FIFO** (First-In First-Out) | จัดการแถวคอยตามลำดับก่อนหลัง | คิวเชิงเส้นเกิด False Overflow ต้องแก้ด้วย Circular Queue |
| **Linked List** | Dynamic Allocation | ขนาดปรับเปลี่ยนได้ยืดหยุ่น แทรก/ลบง่าย $O(1)$ | สุ่มเข้าถึงไม่ได้ ต้องใช้ Sequential Search ($O(n)$) |

---

### 📌 2. รวบรวมสูตรคำนวณตำแหน่งในหน่วยความจำของ Array
* **1 มิติ**: $\text{Loc}(A[i]) = B + C(i - L)$
* **2 มิติ Row Major**: $\text{Loc}(A[i, j]) = B + C[(i - L_1)N + (j - L_2)]$
* **2 มิติ Column Major**: $\text{Loc}(A[i, j]) = B + C[(j - L_2)M + (i - L_1)]$
* **3 มิติ Row Major**: $\text{Loc}(A[i, j, k]) = B + C[(i - L_1)MN + (j - L_2)N + (k - L_3)]$
* **3 มิติ Column Major**: $\text{Loc}(A[i, j, k]) = B + C[(i - L_1)MN + (k - L_3)M + (j - L_2)]$

---

### 📌 3. ลำดับพอยน์เตอร์การแทรก/ลบโหนดใน Linked List (ระวังโดนหลอก!)
* **แทรกโหนดใหม่หลังโหนด P ใน Singly Linked List**:
  * ✅ *ทำถูกต้อง*: `Next(Newnode) = Next(P)` ก่อน แล้วค่อย `Next(P) = Newnode`
  * ❌ *ทำผิด*: ถ้าสั่ง `Next(P) = Newnode` ก่อน สายชี้โหนดถัดไปจะหลุดหายทันที!
* **ลบโหนด P ใน Doubly Linked List**:
  * `Next(Prev(P)) = Next(P)`
  * `Prev(Next(P)) = Prev(P)`
