### Note
- 
#### Think about causality
- Independence and conditional dependence are central to causal inference.
#### Crash Course in Graphical Models
- ![[Screenshot 2566-09-21 at 06.30.41.png]]
- grate causal expertise -> gra![[]]te chance of promotion
![[Screenshot 2566-09-21 at 06.44.35.png]]
- arrow with line = independence
- arrow without line = dependence

#### Confounding Bias
- ![[Screenshot 2566-09-21 at 07.05.27.png]]

#### Selection Bias
- ![[Screenshot 2566-09-21 at 07.11.59.png]]

#### Key Idea
- We've studied graphical models as a language to better understand 
- We do summary of  thre rules of conditional independence on a graph
	- confounding
		- happend when treatment and outcome have common cause (ที่เราไม่สามารถควบคุมหรือจัดการได้)
	- selection bias
		- conditioning on a common effect
	- excessive controlling lead to bias ??
### Question
- [ ] What is graphical causal models ?
- [ ] What is collid
- [ ] confounding bias คือ ?
- [x] selection bias คือ ?
- [ ]  excessive controlling lead to bias ?? เกิดยังไง แล้วเพระาออะไร
### Vocab
- collider = arrow 2 ตัวชี้ไปตัวเดียวกัน
- Confounding Bias -> treatment and outcome share common cause
- Selection Bias 
	- เวลาเราคอรโทรลมากเกินไปทำให้ treatment และ potential outcome มี independent ไม่เห็นผล
	- ส่วนใหญ่จะเป็นแชร์เอฟเฟค
	- เช่น เราจะทดลอง educ -> wage
	- แต่เรา control invest
	- ทำให้เราไม่เห็น effect ของ educ -> wage เพราะว่า ปกติแล้ว คน eudc สูง จะ wage สูง และก็ invest สูง
### Summary
- 