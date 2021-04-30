# CI/CD

1. Melakukan Docker-rize Image Docker `jenkins` versi Latest, membuka port 8080 dan 50000 untuk tcp Jenkins. Store data jenkins akan tersimpan di `/home/jouzieaureezz/jenkinsdata`, dan saya lakukan Store Data SSH-Key saya.

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-34-43-171.jpg)

2. Menjalankan `docker-compose` yang diisi Image Jenkins

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-35-14-306.jpg)

3. Masuk ke Docker Bash Jenkins, lalu lakukan authentikasi SSH-Key Private untuk pertama kalinya

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-36-58-123.jpg)

4. Membuat Job

```
1. Menerima Trigger dari GitHub Repository housy-frontend/housy-backend (Branch: Production)
2. Jenkins akses Instance SSH Frontend/Backend, dan lakukan Git Clone Repository Frontend/Backend
3. Menghapus Container
4. Menghapus Images
5. Dockerrize
6. Deployment (docker-compose)

Job dibuat untuk melakukan Docker Build dan Run dalam satu Tagname/Versi yang sama. (latest)
```

Konfigurasi Job Backend. 

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-37-15-452.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-37-17-839.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-37-20-395.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-37-22-480.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-37-25-497.jpg)

Konfigurasi Job Frontend.

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-38-37-703.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-38-40-356.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-38-42-773.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-38-46-195.jpg)

5. Mengatur WebHook GitHub dari setiap masing-masing Repository Aplikasi agar dapat ter-Trigger ke Jenkins

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-39-05-483.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-39-12-744.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-39-41-051.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-39-45-081.jpg)

6. Jenkins mendapatkan Trigger Push dari Github Repository Frontend

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-42-22-891.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-44-40-684.jpg)

7. Job untuk Build Image dan Run aplikasi Frontend sudah berjalan dengan baik sesuai alurnya

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-45-36-773.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-46-22-562.jpg)

8. Jenkins mendapatkan Trigger Push dari Github Repository Backend

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-46-50-960.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-48-00-835.jpg)

9. Job untuk Build Image dan Run aplikasi Backend sudah berjalan dengan baik sesuai alurnya.

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/CICD/bandicam%202021-04-29%2016-48-24-010.jpg)















