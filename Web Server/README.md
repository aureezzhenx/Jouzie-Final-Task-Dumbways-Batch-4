# Web Server

1. Meng-install `nginx` seperti biasa, masuk ke direktory `/etc/nginx/` lalu buat direktory untuk per-setiap aplikasi

```
sudo mkdir housy-frontend
sudo mkdir housy-backend
sudo mkdir database
sudo mkdir cicd-jenkins
sudo mkdir prometheus
sudo mkdir monitoring
```

Lalu masuk ke `dash.cloudfrare.com` Membuat record baru untuk setiap Domain dan Subdomain baru

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-07-22-047.jpg)

Lalu buat file konfigurasi seperti ini, domain, subdomain, dan port nya menyesuaikan yang dibutuhkan aplikasi masing-masing

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-04-40-702.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-05-55-095.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-09-21-821.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-10-06-978.jpg)

2. Memasukan Include konfigurasi yang sebelumnya sudah dibuat dengan edit file `nginx.conf`

```
include /etc/nginx/housy-frontend/*;
include /etc/nginx/housy-backend/*;
include /etc/nginx/cicd-jenkins/*;
include /etc/nginx/monitoring/*;
include /etc/nginx/prometheus/*;
```

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-14-53-313.jpg)

Jika sudah, save overwrite. Lalu restart nginx dengan cara `sudo nginx -t` dan `sudo systemctl restart nginx`

3. Buat direktori `.secrets` di Home, lalu buat file `cloudflare.ini` 

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-15-59-601.jpg)

4. Mengisi Email yang terdaftar di Cloudflare, lalu mengisi GLOBAL API KEY yang didapat di Dashboard akun Cloudflare pribadi

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-16-12-479.jpg)
