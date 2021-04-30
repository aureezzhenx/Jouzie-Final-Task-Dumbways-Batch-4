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

5. Menginstall certbot dengan 3 command berikut:

```
sudo snap install --classic certbot
sudo ln -s /snap/bin/certbot /usr/bin/certbot
sudo apt-get install certbot python3-certbot-nginx python3-certbot-dns-cloudflare
```

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-17-07-378.jpg)

6. Menjalankan `certbot` dengan Cloudflare Authenticator untuk meregister subdomain `jouzie.onlinecamp.id` dan `api.jouzie.onlinecamp.id` dengan command:

```
sudo certbot certonly --dns-cloudflare --dns-cloudflare-credentials ~/.secrets/cloudflare.ini -d jouzie.onlinecamp.id -d api.jouzie.onlinecamp.id
```

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-20-09-840.jpg)

7. Menjalankan `certbot` dengan Cloudflare Authenticator untuk meregister subdomain `cicd.jouzie.onlinecamp.id`, `monitoring.jouzie.onlinecamp.id` dan `prometheus.jouzie.onlinecamp.id` dengan command:

```
sudo certbot certonly --dns-cloudflare --dns-cloudflare-credentials ~/.secrets/cloudflare.ini -d cicd.jouzie.onlinecamp.id -d monitoring.jouzie.onlinecamp.id -d prometheus.jouzie.onlinecamp.id`
```

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-21-45-385.jpg)

8. Menjalankan `sudo certbot` untuk mendaftarkan SSL Lets Encyrpt dan me-Redirect HTTPS kesemua list Subdomain

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-22-08-269.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-23-10-564.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-23-14-034.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-23-17-091.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-23-21-688.jpg)

9. Subdomain dan Domain sudah berhasil registrasi SSL Lets Encrypt dan sudah diredirect ke HTTPS

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-23-43-210.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-23-49-941.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-23-53-422.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-24-02-395.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Web%20Server/bandicam%202021-04-27%2019-25-31-055.jpg)


