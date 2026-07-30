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