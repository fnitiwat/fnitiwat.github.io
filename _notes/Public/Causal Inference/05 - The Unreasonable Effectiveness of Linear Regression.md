### Note
#### All You Need is Regression
- เวลาเราทำ  causal inference เราจะพบว่ามันมี potential outcome สำหรับแต่ละตัวได้ 2 แบบ ได้แก่ Y0, Y1
- ส่วน T ก็คือ setting ในการเลือกว่าจะ treatment หรือไม่ treatment
- เราไม่สามารถรู้ค่า Y0 และ Y1 พร้อมกันได้
- ดังนั้น treatment effect  Ti = Y1i - Y0i เราจึงไม่สามารถรู้ได้
- EQ1 (Q: ต้องการจะบอกอะไร ?) ![[Screenshot 2566-09-21 at 08.20.34.png]]
	- potential outcome ของ unit i =
		- potential outcome กรณีไม่ได้ treat +  treatment effect... [TODO]
	- เท่าที่ผมเข้าใจเนี่ยสมการนี้คือ
		- Outcome ของ unit i = Outcome  กรณีไม่ treat 
		- ถ้าไม่  treat ก็จบใน term Y0i
		- ถ้า treat ก็บวก treatment effect ซึ่งที่นี้ก้คือ 1(Ti) * (Y1i - Y0i)
		- ส่วนฝั่งขวาก็แค่จัดรูปเฉยๆ
			- Y0i - Y0iTi + TiY1i
- estimating the average causal effect
	- บางคนให้ผลลัพธ์ที่ดีกว่าคนอื่นเมื่อได้รับ treatment
	- แต่เราไม่สามารถรู้ว่าใคร
	- ดังนั้นเราจึงพยายามมองว่า treatment work **on average**
- EQ2
![[Screenshot 2566-09-24 at 09.21.21.png]]
	- ATE (average treatment effect) =  Expectation(Outcome treatment - Outcome non treatment)
	- 
- สมมติถ้าทำให้มันง่ายว่า treatment effect เป็นค่าคงที่ จะได้  Y1i = Y0i + k
- ซึ่งผมเข้าใจว่า k เป็นเหมือน  treatment effect
- ถ้า k เป็น positive เราก็จะบอกได้ว่า โดยเฉลี่ยแล้ว treatment มี positive effect ถึงแม้ว่าจะมีผลแย่กับบางคน แต่โดยรวมแล้วถือว่า positive
- สมมติว่าถ้าเราไม่สามารถ simplify E[Y1-Y0] = E[Y|T=1] - E[Y|T=0] เนื่องจาก bias
- bias ส่วนใหญ่แล้วเกิดเมื่อ treated และ untreated แตกต่างกันจากสาเหตุอื่นนอกเหนือจากการ treatment
- วิธีเช็คก็คือ How they differ in potential outcome Y0 (ดูว่า Y0 ต่างกันในแต่ละกรุ้ปไหม ซึ่งก็คือ AA test ปะ)
- EQ3: ![[Screenshot 2566-09-24 at 10.08.00.png]]
	- ATE = ATET + BIAS
- เราสามารถลบ bias ด้วย RandomExperiment or Random Controlled Trial (RCT) (ตอนนี่สมตติว่าทั้งสองอันคือสิ่งเดียวกัน)
- RCT forces ให้ treated กับ untreated เหมือนกัน ดังนั้น bias จึงหายไป
- เปรียบเทียบ
	- เปรียบ treat และ untreated เหมือนกับ แอปเปิ้ลสำหรับของหวาน, linear regression ก็คงเป็น cold and creamy tiramisu (แปลว่าไร ?)
	- หรือถ้าเราเปรียบเทียบ treated และ untreated. เป็น loaf เก่าๆ ของ white wonder bread (? loaf กับ bread ต่างกันยังไง -> loaf เป็นก้อนวงรี, bread คือขนมปัง)
- สมมติว่าเราต้องการจะ run analysis เปรียบเทียบระหว่าง online VS face-to-face classes แทนที่เราจะต้องทำ math เกี่ยวกับพวก confidence intervals เราแค่รัน regression สมการตามนี้![[Screenshot 2566-09-24 at 12.58.14.png]]
	- exami  = ผลสอบ
	- B0 = baseline
	- k * Onlinei = เทิร์มที่เอาไว้บวก ถ้า class เป็น online
	- ui = เดาว่าเป็นค่าเฉลี่ย
	- Notice: Online เป็น treatment indication ของเรา
- เหมือนเขาบอกว่าหลังจาก linear regression แล้วจะได้
	- E[Y|T=0] = B0
	- E[Y|T=1] = B0 + k
	- ซึ่ง K คือ ATE

?>>>> you are here before regression theory ขอติดไว้ก่อนตรงนี้ยังไม่เข้าใจว่าโค้ดต้องการให้เราดูอะไร
#### Regression Theory
- regression ในทางทฤษฎีแก้ปัญหา linear prediction ได้ดีที่สุด
- มันน่าจะเป็นสมการในการส multi variable regression อะ แต่เราไม่ค่อยคุ้น
- Let B* be a vector of parameters
	- ![[Screenshot 2566-09-24 at 16.28.22.png]]
- Linear Regression จะหา parameter ที่ทำให้  minimise mean squared erro (MSE)
- ถ้าเรา diff มัน แล้ว set เป็น 0 จะได้ linear solution สำหรับปัญหานี้ คือ
	- ![[Screenshot 2566-09-24 at 16.45.34.png]]
- เราสามารถประมาณค่า beta ด้วย sample equivalent
	- ![[Screenshot 2566-09-24 at 19.28.59.png]]
- code![[Screenshot 2566-09-24 at 19.48.00.png]]
	- [ ] Q: ค่าที่เขา return มา 2 อันคืออะไร
- ใน causal inference ส่วนใหญ่แล้วเรา ประมาณ causal impact ของ variable T on an outcome y. 
- เราใช้ regression ด้วย ตัวแปรเดียว เพื่อประมาณ effect
- ถึงแม้ว่าเราจะเพิ่มตัวแปรอื่นเข้าไปด้วย แต่ส่วนใหญ่ก็เป็นแค่ส่วนเสริม
- การเพิ่มตัวแปรอื่นเข้าไปช่วยให้เราประมาณค่า causal effect ของ treatment แต่เราไม่ได้สนใจที่จะประมาณค่า parameters
![[Screenshot 2566-09-24 at 19.56.05.png]]
- ถ้าเรามีมากกว่า 1 regressor (????) เราสามาต่อยอด formula ข้างล่าง 
- เช่น variable อื่นๆเป็นแค่ส่วนเสริม เราสนใจที่จะ estimate แค่ parameter K ที่สัมพันธ์กับ T
![[Screenshot 2566-09-25 at 07.19.46.png]]
- สัมการบน ก็ Regression ปกติ
- สัมการล่างน่าจะเป็นสูตรอะไรสักอย่าง
- หมายความว่า coefficient ของ multivariate regression is bivariate coefficient ของ regressor เดียวกัน
- ใน causal inference k เป็น bivariate coefficient ของ T หลังจากใช้ variable อื่นๆทั้งหมด predict it
- ถ้าเราสามารถ predict T ด้วย variable อื่น แปลว่ามันไม่ได้ random
- แต่เราสามารถทำให้ T เหมือนเป็น random ได้ โดยการ control variable อื่น
- and then we take the residuals of that regression T~ (???)


#### Regression For Non-Random Data
- Experiments are very expensive to conduct
- การที่จะโนมน้าวให้ McKinsey สุ่มให้บริการ service แบบฟรีๆ เพื่อที่จะทำ random experiment เป็นไปได้อยาก ซึ่งบริษัทที่สามารถใช้บริการ McKinsey ส่วนใหญก็ มีตังอยู่แล้ว (มี resource)
- สมมติว่าเราต้องการประมาณ impact ของ จำนวนปีการศึกษษ ต่อ ค่าแรงรายชั่วโมง
- ซึ่งมันทำยากถ้าเราจะ experiment เกี่ยวกับการศึกษา เราไม่สามารถ randomizze คนที่มีการศึกษษ 4, 8, 12 ปีได้ 
- ในเคสนี้ observation data คือ ทั้งหมดที่เรามี
- First, let’s estimate a very simple model

#### Omitted Variable or Confounding Bias
- จะรู้ได้ยังไงว่า parameter ที่ถูก estimate นั้นจะเป็น causal (สาเหตุ)
- สมการต่อไปนี้อธิบายว่า การศึกษาส่งผลกระทบต่อรายได้อย่างไร ![[Screenshot 2566-09-27 at 20.32.33.png]]
- โดย รายได้ ได้รับผลกระทบจาก การศึกษา โดยวัดจากตัวแปร K และ ปัจจัยอื่นๆ
- ![[Screenshot 2566-09-27 at 21.00.45.png]]
- Q: short equals long คืออะไร ?
	- short: ทำการ omits variable
	- long: include them
- Q: OVB คืออะไร
- ไม่มี OVB ถ้า confounding variable (แชร์ common cause ระหว่าง treatment, outcome) ทั้งหมดอยู่ในโมเดล
- เราไม่สามารถชัวร์ได้ว่า confounder ทุกตัวถูก รวมมาไว้แล้ว

#### Key Idea
- How we can use regression for ABTesting
- How it give us confidence intervals
- How regression solves a prediction problem
- And it's the best liniear approximation to the conditional expectation function (CEF)
- How "Short equals long plus the effect of omitted times the regression of omitted on included"
- We used causal grah to see how RCT and regression fixes confounding

- ใช้ linear regression เนี่ย หา K (treatment effect) กับสัมประสัทธิ์ของ factor ต่างๆ
### Questions
- [ ] What is equation 1 ?
	- [ ] How second term come ?
- [x] What is EQ2 ? and What it tell about ?
	- ATE (average treatment effect) =  Expectation(Outcome treatment - Outcome non treatment)
- [ ] Linear Regression Y = MX + C ปะ แล้วมันเกี่ยวไรกับ สมการ 1
- [x] ATE คืออะไร ?
	- [x] average treatment effect
- [x] What is Randomised Controlled Trial (RCT)
	- ตอนนี้ assume ว่าคืออันเดียวกับ random experiment (ABTest)
- [x] T คือไรนะ ?
	- ถ้าในอันเก่ามันคือตัวบอกว่า unit  นี้โดน treat หรือไม่โดน treat
	- T คือบอกว่า Unit นี้โดน treat ไหม
- [x] What is ATET
	- เดาว่าคือ average treatment effect on  treatmented
	- ค่าคาดหวังของความแตกต่างระหว่าง outcome ของกลุ่มที่ถูก treat - กลุ่มที่ไม่ถูก treat เมื่อ ถูก treat
	- **ภาษาคน:** ความแตกต่าง outcome ระหว่าง กลุ่มที่ถูก treat และไม่ถูก treat ในสถานการณ์ที่ ถูก treat
	- แต่ในบท 1 เขาใช้คำว่า ATT
- [x] What is bias in EQ3 mean ?
	- ค่าคาดหวังของ outcome กลุ่มที่ไม่ถูก treat เมื่อ ถูก treat - ค่าคาดหวังของกลุ่มที่ไม่ถูก treat เมื่อไม่ถูก treat
	- **ภาษาคน**: ความแตกต่าง outcome ของกลุ่มที่ไม่ถูก treat ในสถานการณ์ที่โดน treat และไม่ได้โดน treat
- [x] What is RCT is it same as randomized experiment
	-  ในบทที่ 2 พูดเหมือนว่าคือสิ่งเดียวกัน
	- แต่พอถาม chatgpt บอกไม่เหมือนกัน
	- เรา assume ว่าเหมือนกันไปก่อน
- [x] Linear Regression มาเกี่ยวอะไรกับ causal inference
	- ใช้ linear regression หาค่า E[Y|T=0], E[Y|T=1]
- [ ] สงสัยว่ามันมาเชื่อมกันได้ไงระหว่าง B0, B0+k กับ E[Y|T=0,1]
- [x] สงสัยว่า linear regression ไม่ใช่ Y = WX + B หรอ
	- Y = MX + C สำหรับ 1 ตัวแปร
	- np.linalg.inv(X.T.dot(X)).dot(X.T.dot(y)) สำหรับหลายตัวแปร
		- เดาว่าคือท่าในการหา multi-variable linear regression![[Screenshot 2566-09-24 at 17.12.54.png]]
- [x] B* กับ B^ ต่างกันยังไง
	- B* = beta vector (เดา)
	- B^ = estimated beta vector 
- [x] cov คืออะไร
	- covariance บอก ทิศทาง
- [x] var คืออะไร
	- [x] .var()
- [ ] T ในที่นี้คืออะไร ใช้ setting treatment ไหม ?
- [ ] T~ คือไร
- [ ] What is K is it same as B1
- [ ] Confounding bias คือ ?
	      
### Vocab
- Y0 = outcome if don't take treatment
- Y1 = outcome if take treatment
- T = setting treatment
- ATE (average treatment effect) =  Expectation(Outcome treatment - Outcome non treatment) 
- ATET, ATT =  **ภาษาคน:** ความแตกต่าง outcome ระหว่าง กลุ่มที่ถูก treat และไม่ถูก treat ในสถานการณ์ที่ ถูก treat
- BIAS = ความแตกต่าง outcome ของกลุ่มที่ไม่ถูก treat ในสถานการณ์ที่โดน treat และไม่ได้โดน treat
- Confounding Bias
- 
### Summary
- อย่างงง
- เดี๋ยวลองอ่านใหม่อีกรอบ

### Leading script

### Plan 
- summary in each section




