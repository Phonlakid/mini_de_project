# r2de_project
mini project  Road to Data Engineer
เนื่องจากพึ่งเรียน Road to Data Engineer (R2DE 2.0) จาก DATAth.com จบเลยมาลองทบทวนความรู้ด้วยทำ mini project ของตนเอง โดย mini project นี้จะแสดง Data Engineer end-to-end flow ที่ได้จากการเข้าเรียน Road to Data Engineer (R2DE 2.0) จาก DATAth.com โดย flow การทำงานนั้น สามารถดูได้จากภาพประกอบที่ 1
 ![alt text](https://drive.google.com/file/d/1-UhgqBEPmRltA88KKeHw0af-zXFw8ddd/view)
 
ภาพประกอบที่ 1 Data Engineer end-to-end flow โดยใช้ google cloud platform
จากภาพประกอบที่ 1 จะพบว่ามีขั้นตอนทั้งหมด 6 ขั้นตอนดังนี้
1.	Data Collection with Python (Google Colab)
2.	Data Cleansing
3.	Data Lake
4.	Data Pipeline
5.	Data Warehouse
6.	Data Visualization
จากขั้นตอนทั้ง 6 ขั้นตอน สามารถแสดงรายละเอียดของแต่ล่ะขั้นตอนได้ดังนี้

1.Data Collection with Python (Google Colab)
	สำหรับขั้นตอนนี้ คือการ รวบรวมข้อมูลมาจากหลายๆแหล่ง เช่น Database หรือ ไม่ก็ API
โดยอ้างอิงจาก Data Engineer end-to-end flow ดังภาพประกอบที่ 2
 
จากภาพที่ 2 จะพบว่า แหล่งข้อมูล ในขั้นตอน Data Collection นั้นมีการได้มา 2 วิธี ได้แก่ 1.Database และ 2.API โดยใน mini project นี้จะใช้แหล่งข้อมูลในรูปแบบ API คือ ข้อมูลผู้ป่วย covid19 แบบแยกตามจังหวัดจาก covid19.ddc.moph.go.th และ ข้อมูลจาก Database ที่อาศัยข้อมูลจำนวนประชากรในประเทศไทยแยกตามจังหวัดในรูปแบบสำนักงานสถิติแห่งชาติ มาบันทึกไว้ใน Database ที่เตรียมเอาไว้

2. Data Cleansing



