### Note
- AI hard to implement
- If you are smart, you will learn to ignore the foam as a starter.
- Learn what makes your work valueable and valueable not th latest shining tool that no one figure out how to use.
- There are no shortcut.
- ML is notoriously bad at this inverse causality type of problem.
- individual treatment effect = y1i - y0i
- ถึง bias
#### Bias
- bias คือตัวที่ทำให้ association ต่างจาก causation
- เช่น ตัวอย่าง table โรงเรียนที่มีตังซื้อแทบเล็ตอาจจะรวยจนทำให้มีตังจ้างครูดีๆก็ได้
- Y0 of the treated 
	- ผลลัพธ์จากการที่ไม่ได้รับ tablet จากโรงเรียนที่ควรจะได้แทบเล็ต
	- ซึ่งไม่ได้เกิดขึ้นจริง เป็น counterfactual
- สมการ
	- ![[Screenshot 2566-09-16 at 12.46.43.png]]
	- association = treatment effect on the treated + bias term
	- bias = กลุ่ม treated กับกลุ่ม control ต่างกันเท่าไร ก่อน treatment ในกรณีที่ทั้งคู่ไม่ใช่กลุ่มที่ได้รับการ treatment
#### Summary
- บทนี่ก็คือการเกริ่นแหละให้เห็นว่า assoc != causal
	- โดยตัวอย่าง tablet
	- กับสมการ
---

### Vocab
- counterfactual -> ทางที่ไม่ได้เกิด
- Y0i = ผลลัพธ์ของกลุ่มที่ไม่ได้ treatment (for a unit)
- Y1i = ผลลัพธ์ของกลุ่มที่ได้ treatment (same unit)
- T = 1 unit ได้ treatment
- T = 0  unit ไม่ได้ treatment
- ATT คือ ?
- 
### Summary
- หนังสือเล่มนี้ต้องการที่ "how to make association be causation**"




