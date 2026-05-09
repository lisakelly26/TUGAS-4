# TUGAS-4

NAMA : LISA KELLY
NIM  : IK2411010

Deskripsi

Program ini dibuat menggunakan MySQL Stored Procedure untuk mempelajari penggunaan struktur perulangan pada MySQL, yaitu:

LOOP
WHILE LOOP
FOR-style menggunakan WHILE

Praktikum ini terdiri dari 4 program:

Menampilkan angka 1 sampai 10 menggunakan LOOP
Menghitung total angka 1 sampai 20 menggunakan WHILE
Menampilkan bilangan genap 2 sampai 20 menggunakan WHILE
Menghitung total belanja pelanggan sampai Rp500.000
Software yang Digunakan
MySQL
phpMyAdmin / MySQL Workbench / Visual Studio Code
Extension SQL (jika menggunakan VS Code)
Cara Menjalankan Program
1. Masuk ke Database MySQL
USE nama_database;

Contoh:

USE praktikum_mysql;
Program 1 - LOOP Menampilkan Angka 1 sampai 10
Kode Program
DELIMITER //

CREATE PROCEDURE loop_1_sampai_10()
BEGIN
    DECLARE angka INT DEFAULT 1;

    myloop: LOOP

        SELECT angka AS hasil;

        SET angka = angka + 1;

        IF angka > 10 THEN
            LEAVE myloop;
        END IF;

    END LOOP myloop;

END //

DELIMITER ;
Cara Menjalankan
CALL loop_1_sampai_10();
Output
1
2
3
4
5
6
7
8
9
10
Program 2 - WHILE LOOP Menghitung Total 1 sampai 20
Kode Program
DELIMITER //

CREATE PROCEDURE total_1_sampai_20()
BEGIN
    DECLARE i INT DEFAULT 1;
    DECLARE total INT DEFAULT 0;

    WHILE i <= 20 DO

        SET total = total + i;

        SET i = i + 1;

    END WHILE;

    SELECT total AS jumlah_total;

END //

DELIMITER ;
Cara Menjalankan
CALL total_1_sampai_20();
Output
210
Program 3 - Menampilkan Bilangan Genap 2 sampai 20
Kode Program
DELIMITER //

CREATE PROCEDURE genap_2_sampai_20()
BEGIN
    DECLARE angka INT DEFAULT 2;

    WHILE angka <= 20 DO

        SELECT angka AS bilangan_genap;

        SET angka = angka + 2;

    END WHILE;

END //

DELIMITER ;
Cara Menjalankan
CALL genap_2_sampai_20();
Output
2
4
6
8
10
12
14
16
18
20
Program 4 - Menghitung Total Belanja Pelanggan
Kode Program
DELIMITER //

CREATE PROCEDURE total_belanja()
BEGIN
    DECLARE total INT DEFAULT 0;

    WHILE total < 500000 DO

        SET total = total + 50000;

        SELECT total AS total_belanja;

    END WHILE;

END //

DELIMITER ;
Cara Menjalankan
CALL total_belanja();
Output
50000
100000
150000
200000
250000
300000
350000
400000
450000
500000
Kesimpulan

Pada praktikum ini dipelajari penggunaan:

LOOP untuk perulangan umum
WHILE LOOP untuk perulangan berdasarkan kondisi
Stored Procedure pada MySQL
Penggunaan variabel dan kondisi IF
