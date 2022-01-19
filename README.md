# r2de_project
mini project  Road to Data Engineer
เนื่องจากพึ่งเรียน Road to Data Engineer (R2DE 2.0) จาก DATAth.com จบเลยมาลองทบทวนความรู้ด้วยทำ mini project ของตนเอง โดย mini project นี้จะแสดง Data Engineer end-to-end flow ที่ได้จากการเข้าเรียน Road to Data Engineer (R2DE 2.0) จาก DATAth.com โดย flow การทำงานนั้น สามารถดูได้จากภาพประกอบที่ 1
<p align="center">
	<img src="https://lh3.googleusercontent.com/EfP9JlTJWV4qwLO3-Ub7U9SkOvOz-KK-aDgEZZOiZH0LgFLuDbfRaLL6Yvkn9xgKbNjlqc6y7UUDTIOE8bZR6dcHjUgr3DAkC-v2sQRzuN0GUOzQxGMnHgHJKlbvKbmBiOuydVc7H6TfN1RIbEp_RDtEo75KN2KLZTceMdgbenuddcq75RRB5ZX0OKi3Zf_PSbD8G05LmTxsuoXIouimfhU900kiRNvNvK1vs85n23cl6S9AIHoS98yE179KOkHFFEURbX2dZ0rsQ4AWJ9Jg_qPxnGJPjmviXpCu9r3m8eO6KtRAc5iwrG-MWj3_LFiG2JFDaCm7OkdUhgCH0FBD4z9yDzFoCT1jGDv6cgjfiRa1bAJ267Ug8LQGlnqA8ZB2yqa6CgQDS-rDFEa0SDaFa_NvJdyUugqBBRVK8rPZ60emGoxg1Sf03K8HCBFXynvaY3ntQnMkPuB_L2tW8Q7CjREGZOXW-Fb1tznC7PboiWwRlcxv3L96WMxGprkeEFFqaFYZ-tD04NjMYeSV65B7ug2qTeAbfRAKk4OOyVhJSLUtdN3y1QcS2qD2N_poGvUWIVcsbto2wExsp8lGND0CmwzQXvpRR6PQSdEhaDrZg52FQvL1Kreuv02kRc0cDot8jcAaSP7H0fYafJSlBzy-J9BDYjF85c0wZxvnlYmnfcqSUjTJXSQz7-8du1STZCHApYm56fGIA4nAZ1H0eA3Xu6o=w624-h284-no?authuser=0"  title="pic1">
 </p>
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
 <p align="center">
	<img src="https://lh3.googleusercontent.com/17Q4pTqXY4qkOYSv6cGjmh10YQGFPUnVgiVXFiJ4C4Y4U6MTs59fR6ieM-vzDPYwkLo3_qDRHnpI6U3Wf99RmSwZNEMdwkMEowPko-rBy43-DHFsCzgvk7TovAavoHiVYpzDiZpG06OlLmoh3otzOD-Yo-dLXwSe7F_KYDM8fOdKndDM1B9UB8uH1svdTuKNCL08hF4CDGg8mhExf0TLSbsHnbqnlfuk4BtSxbU5YASe7UIHbfJVuSGwA7iPqFqLf81eEljyLgTc_xqS6UvBGezJ_V87Ia4XOurB65bSm-E1bncWlEwLCeiBvDGxdOrXE5Fgz2UIPa8hiVW683zE9bDGf67xYTfGe3ouwO11AmdOnha0VeBLrg-G4Aq5KYRTe4PXIDVjnAi51cca8eZY1Wb0NMSI1wa4rBcjQlaXo0uPW76GILZDz6sEBpVoDDU_Y01osv4n3hMP-QEzEnU0OCUvutY-SvfDsS7A9dBPsyxq2TeI4wXPVuBaY4UIr2abPaNecri8jv6VUp6PuYdCqIUlDT-YN5peCQRCt9mdlRrH5n4EfaEbhDldzima3KpQVuxF8y_MBPm4h-Au0rLXcmHG3Wx0y61QWZSEvrkgXiUkREM7c2jVAYJIpxmLP-m_hL7M3ny9XnKYvxw4fMZT3JnJw8MdiQaTFUJ5b_do3-O3mH3ZmR4bEF-B7_t61dPmmTmlpEQ_7zaPUVzMj2FSuYI=w624-h281-no?authuser=0"  title="pic1">
 </p>
จากภาพที่ 2 จะพบว่า แหล่งข้อมูล ในขั้นตอน Data Collection นั้นมีการได้มา 2 วิธี ได้แก่ 1.Database และ 2.API โดยใน mini project นี้จะใช้แหล่งข้อมูลในรูปแบบ API คือ ข้อมูลผู้ป่วย covid19 แบบแยกตามจังหวัดจาก covid19.ddc.moph.go.th และ ข้อมูลจาก Database ที่อาศัยข้อมูลจำนวนประชากรในประเทศไทยแยกตามจังหวัดในรูปแบบสำนักงานสถิติแห่งชาติ มาบันทึกไว้ใน Database ที่เตรียมเอาไว้

2. Data Cleansing



