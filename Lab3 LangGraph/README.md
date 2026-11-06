# Lab 3: LangGraph Agent Orchestrator

## ภาษาไทย

### โจทย์

ใช้ AI ช่วยสร้างเว็บแอปที่รับคำถามจากผู้ใช้ และใช้ LangGraph ประสาน specialist เพื่อประมวลผล แสดงคำตอบ และแสดงลำดับการทำงานเป็นภาพ
specialist 3 ประเภท: **research** ใช้ LLM ตอบคำถาม, **calculator** คำนวณเลข และ **summarizer** สรุปข้อความ 

### เงื่อนไข

- เลือก specialist ด้วยกฎที่ทำงานซ้ำได้: research สำหรับ `research`, `explain` หรือ `what is`; calculator สำหรับ `calculate` หรือนิพจน์คณิตศาสตร์; summarizer สำหรับ `summarize` หรือ `brief`
- Calculator ใช้รองรับตัวเลข เครื่องหมายบวก/ลบหน้าตัวเลข วงเล็บ และ `+`, `-`, `*`, `/`, `**` 
- Research ต้องเรียก LLM จริง

### ตัวอย่างคำถาม

1. `Research LangGraph, calculate (12 + 3) * 4, then summarize.`
2. `What is LangGraph?`
3. `Calculate 25 * 4 - 10`
4. `Summarize: Solar panels generate electricity. Inverters convert the electricity. Batteries store energy.`
5. `Explain solar energy and calculate 2 ** 3.`
6. `Hello there`

### สิ่งที่ต้องส่ง

1. แอปที่รันได้ พร้อมคำสั่งติดตั้งและวิธีรัน
2. คำสั่งทดสอบหรือขั้นตอนตรวจสอบ พร้อมผลที่ได้
3. Prompt หรือประวัติการใช้ AI ที่สำคัญ
4. คำอธิบายสั้น ๆ ว่าตรวจหรือแก้ผลลัพธ์จาก AI อย่างไร และส่วนใดที่ยังไม่สมบูรณ์

---

## English

### Task

Use AI to help create a web application that accepts questions and uses LangGraph to coordinate specialists, process requests, display answers, and visualize the workflow.

There are three specialists: **research** answers questions using an LLM, **calculator** performs arithmetic, and **summarizer** summarizes text.

### Requirements

- Use deterministic routing rules: research for `research`, `explain`, or `what is`; calculator for `calculate` or a mathematical expression; summarizer for `summarize` or `brief`.
- The calculator supports numeric literals, unary plus/minus, parentheses, and `+`, `-`, `*`, `/`, `**`.
- Research must call a real LLM.

### Example questions

1. `Research LangGraph, calculate (12 + 3) * 4, then summarize.`
2. `What is LangGraph?`
3. `Calculate 25 * 4 - 10`
4. `Summarize: Solar panels generate electricity. Inverters convert the electricity. Batteries store energy.`
5. `Explain solar energy and calculate 2 ** 3.`
6. `Hello there`

### Submission

1. A working application with installation commands and run instructions.
2. Test commands or verification steps, along with their results.
3. Key prompts or relevant AI conversation history.
4. A short explanation of how you checked or corrected the AI output and what remains incomplete.
