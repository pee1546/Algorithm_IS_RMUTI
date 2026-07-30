# บทที่ 4: โครงสร้างข้อมูลแบบคิว (Queue Data Structure)[cite: 4]

## 4.1 คุณลักษณะและหลักการ[cite: 4]
* **หลักการ**: **FIFO (First-In, First-Out)** "เข้าก่อน ออกก่อน"[cite: 4]
* **พอยน์เตอร์ 2 ด้าน**:
  * **REAR (หางคิว)**: ใช้เพิ่มข้อมูลเข้าคิว (Enqueue)[cite: 4]
  * **FRONT (หัวคิว)**: ใช้นำข้อมูลออกจากคิว (Dequeue)[cite: 4]
* **สถานะคิวว่าง**: `Rear < Front` หรือ `Front = 0, Rear = -1`[cite: 4]

---

## 4.2 การดำเนินการบนคิวเชิงเส้น (Linear Queue)[cite: 4]
1. **Enqueue (Add)**:
   * ตรวจสอบ Overflow (`Rear == Size - 1`)[cite: 4]
   * `Rear = Rear + 1; QUEUE[Rear] = ITEM;`[cite: 4]
2. **Dequeue (Delete)**:
   * ตรวจสอบ Underflow (`Rear < Front`)[cite: 4]
   * `ITEM = QUEUE[Front]; Front = Front + 1;`[cite: 4]

---

## 4.3 คิวแบบวงกลม (Circular Queue)[cite: 4]
* **การแก้ปัญหา False Overflow**: ในคิวเชิงเส้น เมื่อลบข้อมูลแล้วพื้นที่ด้านหน้าว่าง แต่ `Rear` ติดขอบขวา จะใส่ข้อมูลอีกไม่ได้[cite: 4]
* **การทำงาน**: เชื่อมส่วนท้ายอาร์เรย์กลับมาที่ส่วนหัว[cite: 4]
  * เมื่อ `Rear == Size - 1` ให้เลื่อนกลับไป `Rear = 0`[cite: 4]
  * เมื่อ `Front == Size - 1` ให้เลื่อนกลับไป `Front = 0`[cite: 4]
* **เงื่อนไขคิววงกลมเต็ม**: 
  $$\text{Front} == \text{Rear} + 1 \quad \text{หรือ} \quad (\text{Rear} + 1) \pmod{\text{Size}} == \text{Front}$$[cite: 4]