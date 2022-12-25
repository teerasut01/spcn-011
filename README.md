# SPCN-011
# ทำการสร้าง master vm แล้วทำการ set ค่าต่างๆ (ubuntu-22.04)
1.เลือก Creat Virtual Machine
![image](https://user-images.githubusercontent.com/117635686/209475752-7e03ab54-4c1e-4b59-8281-c2e15d6b5920.png)

set update time ด้วยคำสั่ง

sudo timedatectl set-timezone Asia/Bangkok

date

set qemu-guest-agent เพื่อเปิดใช้งาน ip qemu ด้วยคำสั่ง

sudo -i
apt update
apt install qemu-guest-agent
systemctl enable qemu-guest-agent
และทำการตั้งค่าที่ option ให้เปิดใช้งานตัว Qemu guest agent  
![image](https://user-images.githubusercontent.com/117635686/209475912-622dbea0-a7ac-4d9a-8972-1d5a6659efa1.png)
