mini project นี้เป็นการทบทวนความรู้ จากการไปเรียน คอร์ส Road to Data Engineer ด้วยการทำ mini project ของตัวเอง ด้วยโจทย์คือ ต้องการทราบข้อมูลผู้ป่วยโควิดในแต่ล่ะวันของแต่ล่ะจังหวัดและประชากรชายและหญิงของจังหวัดนั้นๆโดยคิดเป็นเปอร์เซ็นในแต่ล่ะจังหวัด โดย mini project นี้จะมี end-to-end flow และบริหารของ Google Cloud Platform  ดังภาพประกอบที่ 1
<p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture1.png?raw=true"  title="pic1">
</p>
<p align="center">
ภาพประกอบที่ 1 Data Engineer end-to-end flow โดยใช้ google cloud platform
</p>
	จากภาพประกอบที่ 1 จะพบว่ามีขั้นตอนทั้งหมด 6 ขั้นตอนดังนี้
	1.	Data Collection <br>
	2.	Data Cleansing  <br>
	3.	Data Lake  <br>
	4.	Data Pipeline  <br>
	5.	Data Warehouse  <br>
	6.	Data Visualization  <br>
	จากขั้นตอนทั้ง 6 ขั้นตอน แต่ในโปรเจคนี้จะทำถึงแค่ขั้นตอนที่ 5 โดยแต่ล่ะขั้นตอนสามารถแสดงรายละเอียดแต่ล่ะขั้นตอนได้ดังนี้

1.Data Collection
	สำหรับขั้นตอนนี้ คือการ รวบรวมข้อมูลมาจากหลายๆแหล่ง เช่น Database หรือ ไม่ก็ API
โดยอ้างอิงจาก Data Engineer end-to-end flow ดังภาพประกอบที่ 2
 <p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture2.png?raw=true"  title="pic1">
 </p>
 <p align="center">
ภาพประกอบที่ 2 Data Engineer end-to-end flow
 </p>
จากภาพที่ 2 จะพบว่า แหล่งข้อมูล ในขั้นตอน Data Collection นั้นมีการได้มา 2 วิธี ได้แก่  
1.Database และ 2.API โดยใน mini project นี้จะใช้แหล่งข้อมูลในรูปแบบ API คือ ข้อมูลผู้ป่วย covid19 แบบแยกตามจังหวัดจาก covid19.ddc.moph.go.th ซึ่งเมื่อดึงข้อมูลมาแล้วจะได้ข้อมูลดังภาพประกอบที่ 3
  <p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture2.png?raw=true"  title="pic1">
 </p>
 <p align="center">
ภาพประกอบที่ 3 ภาพข้อมูลผู้ป่วยโควิดรายวัน
 </p>
และข้อมูลจำนวนประชากรในประเทศไทยแยกตามจังหวัดในรูปแบบสำนักงานสถิติแห่งชาติ ซึ่งข้อมูลที่ดึงมาจะได้ข้อมูลดังรูปที่ 4
  <p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture4.png?raw=true"  title="pic1">
 </p>
 <p align="center">
ภาพประกอบที่ 4 ข้อมูลจำนวนประชากรในประเทศไทย
 </p>
	จากภาพประกอบที่ 3 และ 4 นั้นพบว่าข้อมูลที่ดึงมาเป็นรูปแบบ JSON ซึ่งทำให้สามารถดูรายละเอียดของข้อมูลได้ยากเพราะฉนั้นต้องทำการแปลงข้อมูลเป็นรูปแบบตาราง โดยใช้ pandas เข้ามาช่วย ซึ่งจะได้ข้อมูลเป็นตารางดังภาพประกอบที่ 5 และ 6 ดังนี้
  <p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture5.png?raw=true"  title="pic1">
 </p>
<p align="center">
ภาพประกอบที่ 5 ภาพข้อมูลผู้ป่วยโควิดรายวันในรูปแบบตาราง
</p>

  <p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture6.png?raw=true"  title="pic1">
 </p>

<p align="center">
ภาพประกอบที่ 6 ภาพข้อมูลจำนวนประชากรในประเทศไทยในรูปแบบตาราง
</p>
2. Data Cleansing
	Data Cleansing สำหรับขั้นตอนนี้คือขั้นตอนทำความสะอาดข้อมูล รวมทั้งรบข้อมูลที่ไม่ได้ใช้งานอกไป โดยขั้นตอนนี้มีรายละเอียดดังนี้
1.ข้อมูลผู้ป่วยโควิทรายวัน สำหรับข้อมูลผู้ป่วยรายวันนั้นได้ทำการลบข้อมูลใน column ที่ไม่ต้องการออกไปซึ่งจะได้ข้อมูลที่ผ่านการทำ Data Cleansing ดังภาพประกอบที่ 7
<p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture6.png?raw=true"  title="pic1">
</p>
<p align="center">
ภาพประกอบที่ 7 ภาพข้อมูลผู้ป่วยโควิทรายวันที่ผ่านการทำ Data Cleansing
</p>
	2.ข้อมูลประชากรแต่ล่ะจังหวัด สำหรับข้อมูลประชากรแต่ล่ะจังหวัดนั้น เมื่อทำการตรวจสอบชนิดข้อมูลแล้วพบว่าข้อมูลประชากรที่เป็นตัวเลข ที่ type ของข้อมูลเป็น object ดังภาพประกอบที่ 8
   <p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture7.png?raw=true"  title="pic1">
 </p>

<p align="center">
ภาพประกอบที่ 8 ภาพประเภท type ของข้อมูลประชากรแต่ล่ะจังหวัด
</p>
จากนั้นทำการแปลง type ของข้อมูลที่ต้องการจะใช้ใน project นี้ได้แก่ column MALE,FREMALE,
TOTAL ซึ่งเมื่อทำการแปลงข้อมูลแล้วจะได้ข้อมูลดังภาพประกอบที่ 9
   <p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture9.png?raw=true"  title="pic1">
 </p>
<p align="center">
ภาพประกอบที่ 9 ภาพข้อมูลประชากรแต่ล่ะจังหวัดที่ทำการแปลง type ของข้อมูลแล้ว
</p>
จากนั้นเมื่อดูข้อมูลในส่วนของรายชื่อจังหวัดจากภาพประกอบที่ 6 จะพบว่าในข้อมูลรายชื่อจังหวัดนั้นมีการเติมคำว่า จังหวัดลงไปนำหน้าชื่อจังหวัดแทบจะทุก record ดังนั้นจึงต้องทำการลบคำว่าจังหวัดออกไปจากข้อมูล ซึ่งเมื่อลบไปแล้วจะได้ดังภาพประกอบที่ 10
   <p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture10.png?raw=true"  title="pic1">
 </p>

<p align="center">
ภาพประกอบที่ 10 ภาพข้อมูลประชากรแต่ล่ะจังหวัดที่ทำการแก้ไขข้อมูลจังหวัดแล้ว
</p>
	จากนั้นลบข้อมูลใน column ที่ไม่ต้องการออกไปซึ่งจะเหลือข้อมูลดังภาพประกอบที่ 11 ซึ่งมีรายละเอียดดังนี้
<p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture11.png?raw=true"  title="pic1">
</p>

<p align="center">
ภาพประกอบที่ 11 ภาพข้อมูลประชากรแต่ล่ะจังหวัดที่ทำการลบข้อมูลที่ไม่ต้องการออกไป
</p>
	จากนั้นทำการ merge data ข้อมูลประชากรแต่ล่ะจังหวัดกับข้อมูลผู้ป่วยโควิทรายวันของแต่ล่ะจังหวัด จะได้ข้อมูลดังภาพประกอบที่ 12 ซึ่งมีรายละเอียดดังนี้
<p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture12.png?raw=true"  title="pic1">
</p>
<p align="center">
ภาพประกอบที่ 12 ภาพข้อมูลที่ผ่านการ merge data
</p>	
จากนั้นทำการคำนวณยอดของแต่ล่ะจังหวัดโดยคิดเป็นเปอร์เซ็นต์ด้วยการเพิ่ม column เข้าไปในตาราง
ซึ่งจะได้ข้อมูลดังภาพประกอบที่ 13
<p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture13.png?raw=true"  title="pic1">
</p>
<p align="center">
ภาพประกอบที่ 13 ภาพข้อมูลการเพิ่มข้อมูลที่คำนวณเป็นเปอร์เซ็นต์แล้ว
</p>	
3. Data Lake 
Data Lake คือที่เก็บส่วนกลางซึ่งช่วยให้คุณจัดเก็บข้อมูลที่มีและไม่มีโครงสร้างในทุกขนาดได้ คุณสามารถจัดเก็บข้อมูลตามที่เป็นโดยไม่ต้องวางโครงสร้าง และยังสามารถใช้การวิเคราะห์ประเภทต่างๆ ได้ 
ซึ่งใน mini project นี้ จะใช้ Google Cloud Storage เป็น Data Lake ที่ไว้เก็บ Data จากขั้นตอน Data Collection และ Data Cleansing ในรูปแบบ File CSV
<br>
4.Data Pipeline
Data Pipeline Orchestration Orchestration เป็นการจัดการ Pipeline ต่างๆให้เป็นระเบียบโดยจัดการคิวของ Pipeline รวมถึง Monitor การทำงานตั้งแต่ต้นจนจบ โดยใน mini project นี้จะใช้ Airflow ซึ่งอยู่ในบริการของ Google Cloud Composer  ดังภาพประกอบที่
<p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture14.png?raw=true"  title="pic1">
</p>
<p align="center">
ภาพประกอบที่ 14 ภาพ DAGS ใน Airflow
</p>	
โดยใน mini project นี้มี DAG ในรูปแบบ Graph View ทั้งหมด 6 ทั้ง ดังภาพประกอบที่  15
<p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture15.png?raw=true"  title="pic1">
</p>
<p align="center">
ภาพประกอบที่ 15 ภาพ DAGS ในรูปแบบ Graph View
</p>	
โดย DAG ทั้ง 6 มีรายละเอียดดังนี้
1.get_covid_data ขั้นตอนนี้เป็นขั้นตอนการทำ Data Collection โดยเป็นการดึงข้อมูลผู้ป่วยโควิทรายวัน <br>
และเมื่อทำการ Collection เสร็จแล้วจะส่งข้อมูลเข้าสู่ Data Lake ในรูปแบบ csv <br>
2.get_population_data ขั้นตอนนี้เป็นขั้นตอนการทำ Data Collection โดยเป็นการดึงข้อมูลประชากรแต่ล่ะจังหวัด และเมื่อทำการ Collection เสร็จแล้วจะส่งข้อมูลเข้าสู่ Data Lake ในรูปแบบ csv <br>
3.clear_covid_data ขั้นตอนนี้เป็นขั้นตอนการทำ Data Cleansing ของข้อมูลผู้ป่วยโควิดแต่ล่ะจังหวัดและเมื่อทำการ Cleansing เสร็จแล้วจะส่งข้อมูลเข้าสู่ Data Lake ในรูปแบบ csv <br>
4.clear_population_data ขั้นตอนนี้เป็นขั้นตอนการทำ Data Cleansing ของข้อมูลประชากรแต่ล่ะจังหวัดและเมื่อทำการ Cleansing เสร็จแล้วจะส่งข้อมูลเข้าสู่ Data Lake ในรูปแบบ csv <br>
5.merge_data ขั้นตอนนี้เป็นขั้นตอนการ Merge Data โดยการนำข้อมูลผู้ป่วยโควิดแต่ล่ะจังหวัดและข้อมูลประชากรแต่ล่ะจังหวัดมา Merge กัน และเมื่อทำการ Merge เสร็จแล้วจะส่งข้อมูลเข้าสู่ Data Lake ในรูปแบบ csv <br>
6.load_to_bq ในขั้นตอนนี้เป็นการนำ data จากขั้นตอนที่ 5 เข้าสู่ Google Big Query โดยเมื่อข้อมูลเข้าสู่ <br>
Google Big Query แล้วจะพบข้อมูลดังภาพประกอบที่ 16
<p align="center">
<img src="https://github.com/Phonlakid/de_mini_project/blob/main/pic/Picture16.png?raw=true"  title="pic1">
</p>
<p align="center">
ภาพประกอบที่ 16 ภาพตัวอย่างข้อมูลใน Google Big Query
</p>	
5.Data Warehouse
Data Warehouse เหมาะกับการเก็บข้อมูลประเภท Structured data ที่มีขนาดใหญ่ใช้พื้นที่จัดเก็บที่ปริมาณมากข้อมูลที่เก็บมักจะเป็นข้อมูลในอดีต(historical data) ที่ไม่มีการเปลี่ยนแปลง โดยใน mini project นี้จะ Google Big Query เป็น Data Warehouse โดยจะนำเข้าข้อมูลในขั้นตอนที่ 4 Data Pipeline




