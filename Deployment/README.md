# Deployment

BACKEND:

1. Melakukan konfigurasi Docker Build Image dengan file `Dockerfile` untuk Aplikasi Backend.

- Mengambil sumber depedensi `node 14`
- Set Environment Variable `NODE_ENV` dari React menjadi `production`
- Set Environment Variable `DATABASE_URL` dari PostgreSQL: `postgres://postgres:postgres@172.31.75.134:5432/dumbflix`
- Menentukan Image akan berjalan di direktori mana dengan metode `WORKDIR`
- Menentukan posisi File yang ingin di Docker Build
- Menjalankankan instalasi depedensi `npm`
- Menjalankankan instalasi `sequelize` dengan metode instalasi secara Global `RUN npm install sequelize -g`
- Melakukan migrasi Table Database dengan `RUN sequelize db:migrate --env production`
- Membuka Port 5000 untuk aplikasi Backend
- Meng-set Command Shell untuk menjalankan aplikasi Backend `CMD ["node","index.js"]`

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-34-34-398.jpg)

2. Membuat file `docker-compose.yml` untuk aplikasi Backend

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-34-49-355.jpg)

3. Melakukan Docker Build dari File `dockerfile` dengan Command: `docker build -t aureezzhenx/housy-backend` dengan Tagname/versi `latest`

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-39-19-686.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-39-23-024.jpg)

4. Menjalankan Docker Image Backend dengan `docker-compose` secara mode Daemon

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-40-36-911.jpg)

Backend sudah berhasil di Deploy.

FRONTEND:

1. Masuk ke direktori Aplikasi Frontend, lalu edit File `setAuthToken.jsx`. Mengisi URL dari `baseURL` dengan Domain `https://api.jouzie.onlinecamp.id` untuk meng-koneksikan Database dari Instance server Database

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-41-09-741.jpg)

2. Melakukan konfigurasi Docker Build Image dengan file `Dockerfile` untuk Aplikasi Backend.

- Mengambil sumber depedensi `node 14`
- Set Environment Variable `NODE_ENV` dari React menjadi `production`
- Menentukan Image akan berjalan di direktori mana dengan metode `WORKDIR`
- Menentukan posisi File yang ingin di Docker Build
- Menjalankankan instalasi depedensi Node 14 `RUN npm install`
- Menjalankan Optimalisasi Build di mode Production `RUN npm run build`
- Meng-install Server untuk menjalankan Frontend secara mode Production `RUN npm install serve -g`
- Membuka Port 3000 untuk aplikasi Backend
- Meng-set Command Shell untuk menjalankan aplikasi Backend `CMD ["serve","-p","3000","build"]`

Membuat file `docker-compose.yml` untuk aplikasi Frontend

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-41-35-997.jpg)

3. Build Image aplikasi Frontend dengan Docker

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-43-22-366.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-46-09-825.jpg)

4. Menjalankan aplikasi Frontend dengan `docker-compose up -d` secara mode Daemon

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-46-29-899.jpg)

5. Aplikasi Frontend sudah berhasil dijalankan dengan mode Production

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-46-49-438.jpg)

5. Update Aplikasi Frontend dan Backend ke Repository GitHub Branch Production

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-48-26-634.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-49-04-569.jpg)

5. Aplikasi Frontend dan Backend sudah di Update ke Repository GitHub

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-49-34-052.jpg)

![alt image](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Deployment/bandicam%202021-04-28%2023-49-44-067.jpg)

















