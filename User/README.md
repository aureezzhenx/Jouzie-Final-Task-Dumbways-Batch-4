# User

User Instance
- Gateway : jouzienginx
- Frontend : jouziefrontend
- Backend : jouziebackend
- Database : jouziedatabase
- CICD : jouziecicd
- Monitoring : jouziemonitoring 

```
1. Masuk ke setiap Instance Private
2. Menambahkan user baru dengan Command: sudo adduser jouzie.....
3. Mengisi Password user baru
4. Mengisi identitas user baru
5. Menambahkan user baru ke grup Root (Sudo) dengan command: sudo usermod -aG sudo jouzie....
6. Melakukan edit konfigurasi sshd_config dengan nano: sudo nano /etc/ssh/sshd_config
7. Merubah PasswordAuthentication menjadi Yes
8. Save Overwrite
9. Restart sshd untuk me-refresh konfigurasi yang sudah saya edit dengan command: sudo systemctl restart sshd
10. Keluar server, lalu masuk lagi untuk meng-test login dengan menggunakan Password. Berhasil
```

Saya lakukan secara berulang untuk di semua Instance

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/User/bandicam%202021-04-27%2011-58-43-338.jpg)

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/User/bandicam%202021-04-27%2011-59-07-618.jpg)

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/User/bandicam%202021-04-27%2011-59-38-471.jpg)

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/User/bandicam%202021-04-27%2012-00-07-360.jpg)

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/User/bandicam%202021-04-27%2012-11-38-460.jpg)

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/User/bandicam%202021-04-27%2012-13-36-255.jpg)

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/User/bandicam%202021-04-27%2012-15-54-858.jpg)

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/User/bandicam%202021-04-27%2012-17-50-991.jpg)

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/User/bandicam%202021-04-27%2012-19-43-627.jpg)





