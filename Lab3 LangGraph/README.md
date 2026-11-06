# Lab 3: LangGraph Agent Orchestrator

## ภาษาไทย

### โจทย์

ใช้ AI ช่วยสร้างเว็บแอปที่รับคำถามจากผู้ใช้ และใช้ LangGraph ประสาน specialist เพื่อประมวลผล แสดงคำตอบ และแสดงลำดับการทำงานเป็นภาพ

ให้รองรับ specialist 3 ประเภท: **research** ใช้ LLM ที่กำหนดใน `.env` ตอบคำถาม, **calculator** คำนวณเลข และ **summarizer** สรุปข้อความ เมื่อคำขอตรงหลายประเภทให้ทำงานตามลำดับนี้ โดยแต่ละประเภททำงานไม่เกินหนึ่งครั้ง หากไม่มีประเภทที่ตรงให้แจ้งผู้ใช้

ใช้เวลา **10–20 นาที** คุณสามารถเลือกเครื่องมือ วิธีนำเสนอ และออกแบบ feature เพิ่มเติมได้เอง

### เงื่อนไข

- เลือก specialist ด้วยกฎที่ทำงานซ้ำได้: research สำหรับ `research`, `explain` หรือ `what is`; calculator สำหรับ `calculate` หรือนิพจน์คณิตศาสตร์; summarizer สำหรับ `summarize` หรือ `brief`
- Calculator ใช้ restricted `ast` รองรับตัวเลข เครื่องหมายบวก/ลบหน้าตัวเลข วงเล็บ และ `+`, `-`, `*`, `/`, `**` โดยจำกัดขนาดเลขชี้กำลังไม่เกิน 100 ห้ามใช้ `eval`, `exec` หรือ shell execution
- Research ต้องเรียก LLM จริงและแสดงข้อผิดพลาดเมื่อเรียกไม่สำเร็จ โดยไม่อ้างว่าค้นเว็บหรือข้อมูลสดหากไม่ได้ทำจริง
- อ่าน `LITELLM_BASE_URL`, `LITELLM_API_KEY` และ `LLM_MODEL` จาก `.env` เก็บ API key ไว้ฝั่ง server และห้ามส่งไฟล์ `.env` หรือเปิดเผย key ในผลงาน
- มีการทดสอบแบบ mock ทั้งกรณี LLM สำเร็จและล้มเหลวที่รันได้โดยไม่ใช้ key หรือเครือข่าย พร้อมขั้นตอนตรวจการเชื่อมต่อ LLM จริงแยกต่างหาก

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

Use AI to help create a web application that accepts user requests and uses LangGraph to coordinate specialists, return an answer, and visually show the workflow.

Support three specialists: **research** answers questions using the LLM configured in `.env`, **calculator** evaluates arithmetic, and **summarizer** summarizes text. When multiple specialists match, run them in that order, at most once each. Inform the user when none match.

You have **10–20 minutes**. Choose your own tools, presentation, and additional features.

### Requirements

- Use deterministic routing rules: research for `research`, `explain`, or `what is`; calculator for `calculate` or a mathematical expression; summarizer for `summarize` or `brief`.
- Use restricted `ast` for the calculator. Support numeric literals, unary plus/minus, parentheses, and `+`, `-`, `*`, `/`, `**`, with an absolute exponent limit of 100. Do not use `eval`, `exec`, or shell execution.
- Research must call the real LLM and report errors when the call fails. Do not claim to have searched the web or accessed live information unless the application actually did so.
- Read `LITELLM_BASE_URL`, `LITELLM_API_KEY`, and `LLM_MODEL` from `.env`. Keep the API key on the server and do not submit `.env` or expose the key in the deliverables.
- Provide tests with mocked LLM success and failure that run without a key or network access, plus a separate procedure to verify the real LLM connection.

### Example requests

1. `Research LangGraph, calculate (12 + 3) * 4, then summarize.`
2. `What is LangGraph?`
3. `Calculate 25 * 4 - 10`
4. `Summarize: Solar panels generate electricity. Inverters convert the electricity. Batteries store energy.`
5. `Explain solar energy and calculate 2 ** 3.`
6. `Hello there`

### Submission

1. A working application, installation commands, and run instructions.
2. Test commands or verification steps and their results.
3. Key prompts or relevant AI conversation history.
4. A short explanation of how you checked or corrected the AI output and what remains incomplete.
