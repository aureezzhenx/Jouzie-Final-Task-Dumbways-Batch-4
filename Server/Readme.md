# Server

1. Masuk ke VPC, lalu me-rename untuk Mengetahui/Memisahkan Subnet Private/Public

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-02-31-458.jpg)

2. Membuat Instance Private baru untuk Frontend, Backend, Database, Monitoring.

Memakai Ubuntu 

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-04-29-637.jpg)

Memilih tipe spesifikasi `t2.micro`

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-04-38-145.jpg)

Masukan Number of Instance sebanyak 4, lalu arahkan ke Subnet Private yang sebelumnya sudah di Rename, Auto-assigned Public IP menjadi Disable, mengingat ini adalah untuk Server Private

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-05-18-975.jpg)

Size Hardisk 10 GB

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-05-26-106.jpg)

Membuat Security Group baru, saya menggunakan All Traffic.

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-05-56-307.jpg)

Membuat SSH Key baru aureezzhenx@dumbways

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-06-45-257.jpg)

Server sudah berhasil dibuat

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-08-07-681.jpg)

3. Membuat Server untuk CI/CD

Karena spesifikasi mininal untuk Jenkins itu lumayan besar, saya memilih `t2.large`

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-09-09-868.jpg)

Size Hardisk 30 GB

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-09-36-248.jpg)

Untuk konfigurasi Instance Detail, Security Group, SSH Key Pair sama seperti sebelumnya.

4. Membuat Server Gateway

```
1. t2.micro
2. Instance Detail. Auto-Assigned Public IP Enable, Subnet Public.
3. Security Group: All Traffic
4. SSH Keypair sama seperti sebelumnya
```

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-12-45-789.jpg)

5. Melakukan Asosiasi Elastic IP

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-15-02-121.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-15-20-975.jpg)

Memilih Instance Gateway/NGINX

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-15-31-753.jpg)

6. Konfigurasi NAT Instance

Karena sifat Server/Instance Private itu tidak ada IP Public/Tidak diasosiasikan dengan Elastic IP, maka dari itu koneksi internet di semua Instance Private tidak ada. Maka dari itu perlu NAT Instance agar mendapatkan koneksi internet dari Gateway

Launch Instance, masuk ke Community AMI lalu ketik 'nat', pilih versi teratas.

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-17-37-013.jpg)

Hanya merubah menjadi Subnet Public, agar untuk menjembatani koneksi dari Gateway

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-18-10-600.jpg)

Memasukan type Security Group menjadi All Task, dengan custom Source diisi dengan IPv4 CDR dari Subnet Private. Tujuan nya agar untuk menjembatani koneksi Dari Subnet Public yang diterima dari NAT, diteruskan ke Subnet Private

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-27-41-787.jpg)

Memilih Key Pair yang sama

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-28-04-108.jpg)

Memilih NAT Instance, lalu arahkan ke Action dan pilih Networking > Change Source and Destination Check

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-28-58-105.jpg)

Menceklist Stop

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-29-07-277.jpg)

Masuk ke VPC, lalu buat Route Table baru. Mengisi VPC Target

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-30-01-300.jpg)

Jika sudah, Lakukan Edit Routes untuk Route Table yang sebelumnya sudah dibuat dengan cara Actions > Edit Routes

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-30-09-929.jpg)

Mengisi Target untuk NAT Instance, lalu Destination nya menjadi 0.0.0.0/0 agar dapat di use ke semua Instance

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-30-52-193.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-31-08-316.jpg)

Masuk ke Subnet's, pilih Subnet Private untuk dilakukan Asosiasi Route Table yang sebelumnya dibuat

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-31-35-228.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-31-42-778.jpg)

Route Table FinalTask sudah berhasil di asosiasikan

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Server/img/bandicam%202021-04-27%2011-32-02-902.jpg)

Konfigurasi NAT Instance sudah berhasil dilakukan.

