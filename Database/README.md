# Database

1. Melakukan Docker-rize Image `postgres` dengan tag name latest dengan `docker-compose`. Membuka port 5432 untuk `postgres` serta store data untuk menyimpan semua data-data dari database ke server dengan metode volume, dan meng-set Environment `POSTGRES_PASSWORD` sebagai Password SuperUser PostgreSQL.

Saya lakukan store data di direktori `/home/jouziedatabase/postgresql/data`

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Database/bandicam%202021-04-28%2023-17-53-995.jpg)

2. Jika sudah, saya menjalankan konfigurasi `docker-compose.yml` dengan mode Daemon, lalu masuk ke Bash Docker di image `postgres` dengan command: `docker exec -it postgres bash`

Lalu masuk ke PostgreSQL Prompt dengan command: `psql -U postgres -h localhost -p 5432` 

Paramater Flag

- (-U) User
- (-h) Host
- (-p) Port

Jika sudah masuk ke Prompt PostgreSQL, membuat Database baru untuk `dumbflix` dengan command `CREATE DATABASE dumblix;`

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Database/bandicam%202021-04-28%2023-22-24-221.jpg)

3. Masuk ke Instance Backend, masuk ke direktori Aplikasi Backend, lalu mengatur Environment `DATABASE_URL` untuk PostgreSQL bertujuan untuk melakukan migrasi Table Database ke Instance Database dengan command: `export DATABASE_URL=postgres://postgres:postgres@172.31.75.134:5432/dumbflix`

Format: `POSTGRES://USER:PASSWORD@HOST:PORT/DATABASE`

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Database/bandicam%202021-04-28%2023-25-04-029.jpg)

4. Lakukan migrasi Table Database dengan `sequelize` Environment mode Production dengan Command: `sequelize db:migrate --env production`

Table Database sudah berhasil di-imigrasi-kan.

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Database/bandicam%202021-04-28%2023-25-31-577.jpg)

5. Kembali cek di Instance Database untuk memastikan apakah sudah berhasil di imigrasi-kan atau belum, masuk ke PostgreSQL Prompt dari Bash Docker image PostgreSQL.

Memakai Database Dumbflix: `\c dumbflix`; Melihat Table dari Database Dumbflix: `\dt`

![alt text](https://github.com/aureezzhenx/Jouzie-Final-Task-Dumbways-Batch-4/blob/main/Database/bandicam%202021-04-28%2023-30-55-859.jpg)





