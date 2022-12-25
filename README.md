# SPCN-011
- ทำการสร้าง master vm แล้วทำการ set ค่าต่างๆ (ubuntu-22.04) -
1.เลือก Creat Virtual Machine
![image](https://user-images.githubusercontent.com/117635686/209475752-7e03ab54-4c1e-4b59-8281-c2e15d6b5920.png)

-set update time ด้วยคำสั่ง

sudo timedatectl set-timezone Asia/Bangkok

date

-set qemu-guest-agent เพื่อเปิดใช้งาน ip qemu ด้วยคำสั่ง

sudo -i

apt update

apt install qemu-guest-agent

systemctl enable qemu-guest-agent

และทำการตั้งค่าที่ option ให้เปิดใช้งานตัว Qemu guest agent  
![image](https://user-images.githubusercontent.com/117635686/209475912-622dbea0-a7ac-4d9a-8972-1d5a6659efa1.png)

reboot เพื่อรีระบบ clone from template 2 vm

Click ที่ vm(master) แล้วไป Convert to template

หลังจาก vm(master)กลายเป็นtemplate ให้คลิกที่ vm แล้วเลือก Clone
![image](https://user-images.githubusercontent.com/117635686/209476157-66bd84db-1209-438b-9198-1caa97bec915.png)

ทำการsetระบบ
![image](https://user-images.githubusercontent.com/117635686/209476197-5f3f6598-5e28-4155-8d2e-c0ae452bcecb.png)

- พิมพ์ date เพื่อเช็คtimezone

เปลี่ยนค่าไอดีตัว vm เพื่อทำการเปลี่ยน ip ใหม่ เพื่อไม่ให้ ip ตัว MASTER ซ้ำกับตัว CLONE โดยทำขั้นตอนดังนี้
sudo -i

rm /var/lib/dbus/machine-id

nano /etc/machine-id ทำการลบตัวไอดีในไฟล์ทั้งหมด

ln -s /etc/machine-id /var/lib/dbus/machine-id  

/var/lin/dbus/machine-id กับตัวไฟล์ /etc/machine-id

reboot เมื่อ reboot สำเร็จ ตัวไอดีขึ้นใหม่ และได้รับ ip ใหม่ ทำขั้นตอนนี้ที่ vm clone 2 เช่นกัน

#summary
Master
![image](https://user-images.githubusercontent.com/117635686/209476298-78fd3250-9606-40f7-bd6c-264e0a7371f6.png)

clone 1 :
![image](https://user-images.githubusercontent.com/117635686/209476322-be1ea135-0cec-48cc-9c52-75a63a3a614b.png)

clone 2 :
![image](https://user-images.githubusercontent.com/117635686/209476345-e08669a6-befd-4750-80ea-68f2ccb30a27.png)

watch
clone 1 :
![image](https://user-images.githubusercontent.com/117635686/209476405-6f1772ec-4d27-41d7-aa4e-41a691ae9d7b.png)

clone 2 :
![image](https://user-images.githubusercontent.com/117635686/209476451-bbbb1a0e-0321-4165-b766-b732dce36dd4.png)

หลังจากเสร็จ Clone 2 ตัวมาสร้าง create vm from other os ต่อ
![image](https://user-images.githubusercontent.com/117635686/209476498-33c2cb2c-c446-4915-b7a4-2699707b0235.png)

![image](https://user-images.githubusercontent.com/117635686/209476515-9acb75cc-9a0a-4586-931d-03758363eac1.png)

หลังจากเสร็จการสร้าง other os แล้วเรามาทำการสร้าง container ต่อ
-summary
![image](https://user-images.githubusercontent.com/117635686/209476553-d3e39a40-9c50-47b0-b7ff-06e42a59dde2.png)

-console
![image](https://user-images.githubusercontent.com/117635686/209476589-67341df9-b233-45fc-abc7-5d1ad5dea6af.png)

เสร็จสิ้น
