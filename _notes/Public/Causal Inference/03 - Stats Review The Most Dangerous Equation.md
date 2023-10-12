### Note
- ![[Screenshot 2566-09-19 at 05.13.51.png]]
- Why not knowing this equation is very dangerous ?
- top school have on average fewer student.
- but bottom 1% of schools have fewer students too !![[Screenshot 2566-09-19 at 05.26.06.png]]
- "Probability is not a mere computation of odds on the dice or more complicated variants; it is the acceptance of the lack of certainty in our knowledge and the development of methods for dealing with our ignorance."
- One way to quantify our uncertainty is the **variance of our estimates**
#### The Standard Error of Our Estimates
- equation![[Screenshot 2566-09-19 at 05.53.17.png]]

#### Confidence Intervals
- data generating process
- **with the standard error, we can create an interval that will contain the true mean 95% of the time**.
- To calculate the confidence interval, we use the **central limit theorem**.
	- This theorem states that **means of experiments are normally distributed**.
- การคำนวณ CI ใช้ central limit theore![[Screenshot 2566-09-20 at 05.14.21.png]]m โดยมันกล่าวไว้ว่า mean of experiments are normally distributed 
- ปกติแล้วเราคำนวณหาช่วงใช่ไหม ?
- กราฟที่บอกความน่าจะเป็นที่จะอยู่ในช่วง ของ normal distribution
- โอกาสที่ popmean 
- เราจะเชื่อได้ขนาดไหนว่าค่าที่เรารีพอร์ตจะไม่ห่างจากค่าจริงมาก

#### Hypothesis Testing
- เป็นอีกหนึ่งวิธีในการรวมความไม่แน่นอน
- งอง

#### P-values
- “the p-value is the probability of obtaining test results at least as extreme as the results actually observed during the test, assuming that the null hypothesis is correct”
- pvalue คือ ความน่าจะเป็นในการเก็บผลการเทสโดยอย่างน้อยต้องมีมากกว่า ผลลัพธ์จากการ observe ระหว่างเทส ถึงจะสามารถสมมติฐานได้ว่า  null hypothesis เป็นจริง

#### Key Ideas
- งอง
### Questions
- [x] What is confidence interval 
	-  ช่วงความเชื่อมัน
	-  หากเราคำนวณการวัดอายุการใช้งานของหลอดไฟที่เก็บตัวอย่างมาอย่างสุ่ม และคำนวณได้ 95% confidence interval ได้ 1,230 - 1,265 ชั่วโมง นั่นหมายความว่า เรามั่นใจได้ 95% ว่าค่าเฉลี่ยประชากรของอายุการใช้งานหลอดไฟจะอยู่ระหว่าง 1,230 - 1,265 ชั่วโมง
	- มั่นใจได้ 95% ว่าค่าเฉลี่ยๆจริงๆจะอยู่ในช่วงนั้น
- [ ] Hypothesis Testing คืออะไร
- [ ] Hypothesis Testing step เป็นยังไง
- [x] Null Hypothesis คือ ?
	- [x] ตรงข้ามกับสิ่งที่เราจะ proof
- [ ] p value คำนวณ หรือ วิธีเอาไปใช้สเตปเป็นยังไง
- [ ] standard deviation VS standard error ต่างกันยังไง
	- se variance mean
		- raw -> mean
	- sd vairance 
		- sample mean -> population mean
- [ ] เราสามารถอธิบายเป็นภาษาปกติได้ไหมว่าทำไม n กับ n-1 
- [x] ช่วง CI 2 ตัว แล้วถ้ามัน overlap จะสรุปว่าไง
	- ถ้า overlap กัน ต้องไปทำ hypothesis testing ต่อ
	- อ่อยังสรุปไม่ได้ถึงจะไม่ overlap
	- 
### Vocab
- SE = standard error
- _์_ = standard deviation
- n = sample size
- confidence interval = ช่วงความเชื่อมัน
	- หากเราคำนวณการวัดอายุการใช้งานของหลอดไฟที่เก็บตัวอย่างมาอย่างสุ่ม และคำนวณได้ 95% confidence interval ได้ 1,230 - 1,265 ชั่วโมง นั่นหมายความว่า เรามั่นใจได้ 95% ว่าค่าเฉลี่ยประชากรของอายุการใช้งานหลอดไฟจะอยู่ระหว่าง 1,230 - 1,265 ชั่วโมง
	- มั่นใจได้ 95% ว่าค่าเฉลี่ยๆจริงๆจะอยู่ในช่วงนั้น
- pvalue
- zscore
### Summary
