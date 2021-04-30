# SSH

1. Dari Local ke Server Gateway

```
1. Membuat SSH-Key dari Local terlebih dahulu dengan Command: ssh-keygen
2. Lakukan Copy SSH Key Public ke Server Gateway agar dapat di-generate secara automatis langsung ke authorized_keys di Server Gateway
3. Melakukan verifikasi dan identifikasi SSH Key dengan SSH Agent untuk pertama kalinya dengan Command: eval `ssh-agent -s`
4. Menambahkan SSH Private Key yang sudah dibuat ke SSH Agent dengan command: ssh-add aureezzhenx@dumbways
5. Masuk ke server Gateway
6. Sudah tidak perlu menggunakan Password
7. Keluar dari server Gateway untuk melakukan Copy file SSH Key Public dan Private nya ke Server Gateway
8. Copy dengan command: scp aureezzhenx@dumbways.pub jouzienginx@54.85.186.198:/home/jouzienginx/aureezzhenx@dumbways.pub | scp aureezzhenx@dumbways.pub jouzienginx@54.85.186.198:/home/jouzienginx/aureezzhenx@dumbways
9. Copy file sudah berhasil.
```

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-06-09-384.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-06-14-119.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-11-05-149.jpg)

2. Dari Server Gateway ke Server Frontend

```
1. Lakukan Copy SSH Key Public ke Server Frontend agar dapat di-generate secara automatis langsung ke authorized_keys di Server Frontend
2. Melakukan verifikasi dan identifikasi SSH Key dengan SSH Agent untuk pertama kalinya dengan Command: eval `ssh-agent -s`
3. Menambahkan SSH Private Key yang sudah dibuat ke SSH Agent dengan command: ssh-add aureezzhenx@dumbways
4. Masuk ke server Frontend
5. Sudah tidak perlu menggunakan Password
6. Keluar dari server Frontend untuk melakukan Copy file SSH Key Public dan Private nya ke Server Frontend
7. Copy dengan command: scp aureezzhenx@dumbways.pub jouziefrontend@172.31.76.70:/home/jouziefrontend/aureezzhenx@dumbways.pub | scp aureezzhenx@dumbways.pub jouziefrontend@172.31.76.70:/home/jouziefrontend/aureezzhenx@dumbways
8. Copy file sudah berhasil.
```

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-15-33-703.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-16-59-611.jpg)

3. Dari Server Frontend ke Server Backend

```
1. Lakukan Copy SSH Key Public ke Server Backend agar dapat di-generate secara automatis langsung ke authorized_keys di Server Backend
2. Melakukan verifikasi dan identifikasi SSH Key dengan SSH Agent untuk pertama kalinya dengan Command: eval `ssh-agent -s`
3. Menambahkan SSH Private Key yang sudah dibuat ke SSH Agent dengan command: ssh-add aureezzhenx@dumbways
4. Copy dengan command: scp aureezzhenx@dumbways.pub jouziebackend@172.31.79.55:/home/jouziebackend/aureezzhenx@dumbways.pub | scp aureezzhenx@dumbways.pub jouziebackend@172.31.79.55:/home/jouziebackend/aureezzhenx@dumbways
5. Masuk ke Server Backend, sudah tidak menggunakan Password lagi.
```

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-20-24-330.jpg)

4. Dari Server Backend ke Server Database

```
1. Lakukan Copy SSH Key Public ke Server Backend agar dapat di-generate secara automatis langsung ke authorized_keys di Server Database
2. Melakukan verifikasi dan identifikasi SSH Key dengan SSH Agent untuk pertama kalinya dengan Command: eval `ssh-agent -s`
3. Menambahkan SSH Private Key yang sudah dibuat ke SSH Agent dengan command: ssh-add aureezzhenx@dumbways
4. Copy dengan command: scp aureezzhenx@dumbways.pub jouziedatabase@172.31.75.134:/home/jouziedatabase/aureezzhenx@dumbways.pub | scp aureezzhenx@dumbways.pub jouziedatabase@172.31.75.134:/home/jouziedatabase/aureezzhenx@dumbways
5. Masuk ke Server Database, sudah tidak menggunakan Password lagi.
```

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-22-37-626.jpg)

5. Dari Server Database ke Server CI/CD

```
1. Lakukan Copy SSH Key Public ke Server Backend agar dapat di-generate secara automatis langsung ke authorized_keys di Server CI/CD
2. Melakukan verifikasi dan identifikasi SSH Key dengan SSH Agent untuk pertama kalinya dengan Command: eval `ssh-agent -s`
3. Menambahkan SSH Private Key yang sudah dibuat ke SSH Agent dengan command: ssh-add aureezzhenx@dumbways
4. Copy dengan command: scp aureezzhenx@dumbways.pub jouziecicd@172.31.65.126:/home/jouziecicd/aureezzhenx@dumbways.pub | scp aureezzhenx@dumbways.pub jouziecicd@172.31.65.126:/home/jouziecicd/aureezzhenx@dumbways
5. Masuk ke Server CI/CD, sudah tidak menggunakan Password lagi.
```

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-26-28-514.jpg)

6. Dari Server CI/CD ke Server Monitoring

```
1. Lakukan Copy SSH Key Public ke Server Backend agar dapat di-generate secara automatis langsung ke authorized_keys di Server Monitoring
2. Melakukan verifikasi dan identifikasi SSH Key dengan SSH Agent untuk pertama kalinya dengan Command: eval `ssh-agent -s`
3. Menambahkan SSH Private Key yang sudah dibuat ke SSH Agent dengan command: ssh-add aureezzhenx@dumbways
4. Copy dengan command: scp aureezzhenx@dumbways.pub jouziemonitoring@172.31.73.143:/home/jouziemonitoring/aureezzhenx@dumbways.pub | scp aureezzhenx@dumbways.pub jouziemonitoring@172.31.73.143:/home/jouziemonitoring/aureezzhenx@dumbways
5. Masuk ke Server CI/CD, sudah tidak menggunakan Password lagi.
```

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-28-47-360.jpg)

7. Menambahkan SSH Key Public ke GitHub

Buka pengaturan akun GitHub, lalu masuk ke SSH and GPG Keys. Klik New SSH Key

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-37-48-691.jpg)

Menambahkan isi dari SSH Public Key aureezzhenx@dumbways

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-38-23-914.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-38-58-581.jpg)

8. Tes koneksi GitHub dengan cara: `ssh -T git@github.com` di Server Frontend dan Backend

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-40-40-143.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/SSH/bandicam%202021-04-27%2014-42-55-786.jpg)
