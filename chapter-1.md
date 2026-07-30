# บทที่ 1: ความรู้เบื้องต้นเกี่ยวกับโครงสร้างข้อมูลและอัลกอริทึม[cite: 1]

## 1.1 ความหมายและเป้าหมาย[cite: 1]
* **โครงสร้างข้อมูล (Data Structure)**: รูปแบบความสัมพันธ์ของข้อมูลที่จัดเก็บอยู่ในหน่วยความจำคอมพิวเตอร์อย่างเป็นระเบียบ เพื่อให้เรียกใช้งานได้รวดเร็ว[cite: 1]
* **สมการสร้างโปรแกรม**: 
  $$\text{Data} + \text{Algorithms} = \text{Program}$$
[cite: 1]
* **เป้าหมายหลัก**:
  1. ใช้พื้นที่หน่วยความจำน้อยที่สุด (Space Efficiency)[cite: 1]
  2. ใช้เวลาประมวลผลสั้นที่สุด (Time Efficiency)[cite: 1]

---

## 1.2 ลำดับขั้นของข้อมูล (Data Hierarchy)[cite: 1]
เรียงลำดับจากเล็กไปใหญ่:
$$\text{Bit} \rightarrow \text{Byte} \rightarrow \text{Field} \rightarrow \text{Record} \rightarrow \text{File} \rightarrow \text{Database}$$
[cite: 1]

* **Bit**: หน่วยเล็กสุด (`0` หรือ `1`)[cite: 1]
* **Byte**: 8 Bits = 1 ตัวอักษร (เช่น `'I'` ใน ASCII คือ `01001001`)[cite: 1]
* **Field**: กลุ่มตัวอักษรที่รวมกันแล้วมีความหมาย เช่น `Student_ID`, `Course`[cite: 1]
* **Record**: การรวมฟิลด์ที่มีความสัมพันธ์กัน เช่น ข้อมูลนักศึกษา 1 คน[cite: 1]
* **File**: การรวมเรคอร์ดประเภทเดียวกัน[cite: 1]
* **Database**: การรวมไฟล์ที่มีความสัมพันธ์กันเข้าด้วยกัน[cite: 1]

---

## 1.3 ประเภทของโครงสร้างข้อมูล[cite: 1]
1. **ทางกายภาพ (Physical Data Structure)**:
   * **ข้อมูลเบื้องต้น (Primitive Data Type)**: ข้อมูลพื้นฐาน เช่น Integer, Real/Float, Character[cite: 1]
   * **ข้อมูลโครงสร้าง (Structure Data Type)**: เกิดจากการนำข้อมูลเบื้องต้นมาประกอบกัน เช่น Array, Record, File[cite: 1]
2. **ทางตรรกะ (Logical Data Structure)**:
   * **แบบเชิงเส้น (Linear Data Structure)**: เก็บต่อเนื่อง เข้าถึงตามลำดับ ได้แก่ **Array, Stack, Queue, Linked List**[cite: 1]
   * **แบบไม่เชิงเส้น (Non-Linear Data Structure)**: เก็บไม่ต่อเนื่อง ระบุตำแหน่งด้วยความสัมพันธ์ ได้แก่ **Tree, Graph**[cite: 1]

---

## 1.4 การแทนที่ข้อมูลในหน่วยความจำ[cite: 1]
* **Static Memory Representation**: จองพื้นที่แน่ชัดไว้ล่วงหน้า (เช่น Array) เขียนโปรแกรมง่าย แต่ปรับขนาดไม่ได้ เกิดปัญหาสูญเสียพื้นที่หรือ Overflow[cite: 1]
* **Dynamic Memory Representation**: จองพื้นที่ยืดหยุ่นตามต้องการ ณ เวลา Runtime ผ่าน Pointer ใช้หน่วยความจำมีประสิทธิภาพสูง[cite: 1]

---

## 1.5 ขั้นตอนพัฒนาโปรแกรมและวิเคราะห์งาน[cite: 1]
* **SDLC 5 ขั้นตอน**: Plan $\rightarrow$ Design $\rightarrow$ Develop $\rightarrow$ Deploy $\rightarrow$ Maintenance[cite: 1]
* **การวิเคราะห์โจทย์ (Job Analysis)**:
  1. สิ่งที่โจทย์ต้องการ (Goal)[cite: 1]
  2. ข้อมูลนำเข้า (Input) & ตัวแปร (Variables)[cite: 1]
  3. ผลลัพธ์ที่ต้องการ (Output)[cite: 1]
  4. วิธีการประมวลผล (Processing)[cite: 1]

---

## 1.6 เครื่องมือออกแบบอัลกอริทึม[cite: 1]
1. **ผังงาน (Flowchart)**:
   * `Terminator` (วงกลมมน): จุดเริ่มต้น/สิ้นสุด[cite: 1]
   * `Process` (สี่เหลี่ยมผืนผ้า): คำนวณ/กำหนดค่า[cite: 1]
   * `Input/Output` (สี่เหลี่ยมด้านขนาน): รับ/แสดงข้อมูลทั่วไป[cite: 1]
   * `Decision` (สี่เหลี่ยมขนมดียกปูน): การตัดสินใจเปรียบเทียบ (IF/Case)[cite: 1]
   * `Preparation` (หกเหลี่ยม): กำหนดค่าล่วงหน้า (For loop)[cite: 1]
   * **โครงสร้าง**: แบบลำดับ (Sequential), แบบทางเลือก (Selection), แบบวนซ้ำ (Repetition: **Do-While** [ตรวจก่อนทำ], **Repeat-Until** [ทำก่อนตรวจอย่างน้อย 1 ครั้ง], **For** [รู้จำนวนรอบแน่นอน])[cite: 1]
2. **รหัสเทียม (Pseudocode)**: ภาษาอังกฤษจำลองคำสั่ง เช่น `BEGIN`, `END`, `SET`, `READ`, `WRITE`, `IF-THEN-ELSE-ENDIF`, `DO WHILE-ENDDO`[cite: 1]

---

## 1.7 ประสิทธิภาพอัลกอริทึมและ Big-O Notation[cite: 1]
* **การวัดประสิทธิภาพ**: วัดจาก **Space Utilization** (หน่วยความจำ) และ **Time Efficiency** (เวลาในการประมวลผล $T(n)$)[cite: 1]
* **ลำดับอัตราการเติบโต Big-O (เรียงจากเร็วไปช้า)**:
  $$O(1) < O(\log_2 n) < O(n) < O(n \log_2 n) < O(n^2) < O(n^3) < O(n^k) < O(2^n) < O(n!)$$
[cite: 1]
* **ตัวอย่างการวิเคราะห์ลูป**:
  * **Linear Loop** (`for i=0; i<n; i++`) $\rightarrow O(n)$[cite: 1]
  * **Logarithmic Loop** (`for i=1; i<n; i*=2`) $\rightarrow O(\log_2 n)$[cite: 1]
  * **Nested Loop** (ลูปซ้อน $n \times n$) $\rightarrow O(n^2)$[cite: 1]
  * **Dependent Loop** ($1+2+...+n = \frac{n(n+1)}{2}$) $\rightarrow O(n^2)$[cite: 1]