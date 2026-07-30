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
$$	ext{[ LLINK / PREV } | 	ext{ DATA } | 	ext{ RLINK / NEXT ]}$$
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