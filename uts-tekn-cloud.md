# Docker - MongoDB

Ujian Tengah Semester - Teknologi Cloud

1. Buat Account DockerHub
- Untuk membuat akun dockerhub dapat dengan mengakses [hub.docker.com](https://hub.docker.com/) seperti gambar dibawah ini, lalu isikan username, email, dan password yang akan didaftarkan
![1](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/1.png)

- Kemudian lakukan verifikasi email sesuai email yang telah didaftarkan
![2](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/2.png)

- Setelah proses verifikasi selesai maka kita dapat melakukan login dengan akun dockerhub yang telah dibuat
![3](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/3.png)


2. Pilih Image Docker untuk di pull
- Image Docker yang akan saya pull yaitu MongoDB, untuk langkah - langkah pull untuk Image MongoDB yaitu seperti pada gambar berikut :
![4](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/4.png)
![5](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/5.png)

3. Langkah menjalankan Docker, pull image, menjalankan image menjadi container, dan menghentikan container
Disini saya menjalankan Docker tersebut pada Sistem Operasi Ubuntu 18.04.3 pada VMware Workstation
![6](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/6.png)

### Untuk langkah - langkah awal dalam menggunakan Docker pada Ubuntu yaitu sebagai berikut :
- Untuk melakukan install Docker pada Ubuntu, pertama - tama kita harus menghapus versi lama docker terlebih dahulu dengan mengetikan perintah berikut pada Terminal
![7](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/7.png)

- Kemudian kita melakukan set up Docker Repository menggunakan perintah berikut
![8](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/8.png)
![9](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/9.png)
![10](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/10.png)

- Setelah proses set up selesai, disini kita melakukan update apt package index dan melakukan proses instalasi Docker
![11](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/11.png)
![12](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/12.png)

- Setelah proses instalasi berhasil, kita dapat mengecek Docker yang telah terinstal tersebut dengan menggunakan perintah berikut

![13](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/13.png)



### Selanjutnya yang dilakukan yaitu kita melakukan pull image (MongoDB), menjalankan image menjadi container, dan menghentikan container
- Untuk proses melakukan Pull Image MongoDB yaitu seperti pada gambar no 2 sebelumnya, yaitu dengan menggunakan perintah docker pull mongo
![14](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/14.png)

- Setelah proses selesai, kita dapat menjalankan container mongodb tersebut. Pada perintah 'docker image', kita dapat melihat image apa yang kita miliki dan dapat digunakan Lalu dengan perintah 'docker run -d -p 27017-27019:27017-27019 --name mongodb mongo' maka program akan menjalankan docker pada image mongo dengan nama containernya mongodb
![15](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/15.png)

- Kemudian dengan perintah 'docker exec -it mongodb bash' maka kita telah masuk pada container dari image mongo tersebut. Dan dengan perintah 'mongo' maka kita telah masuk ke CLI dari MongoDB
![16](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/16.png)

- Untuk keluar dari container image Mongo tersebut, cukup dengan mengetikan perintah 'exit' pada CLI Mongo, dan 'exit' pada container image mongo
![17](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/17.png)

- Kemudian dengan perintah 'docker ps' kita dapat melihat daftar container yang aktif lalu menghentikan container tersebut sesuai dengan IDnya menggunakan perintah docker stop
![18](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/18.png)


4. Buat Dockerfile dan Push Image di DockerHub
- Membuat Dockerfile
Langkah - langkah yang harus dilakukan dalam membuat dockerfile yaitu sebagai berikut :
Pertama kita membuat folder dengan nama bebas (misal DockerFiles -> mkdir DockerFiles), lalu pindah ke lokasi folder tersebut (cd DockerFiles/), kemudian buat file Dockerfile (touch Dockerfile), dan edit isi dari file Dockerfile tersebut menggunakan vim (vim Dockerfile)
![19](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/19.png)

Kemudian untuk isi dari Dockerfilenya sebagai berikut dimana nantinya isi dari image ini akan menampilkan kata - kata yang ada pada perintah CMD
![20](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/20.png)

- Build Image menggunakan Dockerfile
Untuk membuat Image menggunakan file Dockerfile yang telah dibuat sebelumnya yaitu dengan menggunakan perintah "docker build -t tekncloud:uts" dimana image yang terbuat akan memiliki nama "tekncloud" dengan tag namenya "uts"
![21](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/21.png)

- Cek hasil Image
Untuk melihat hasil dari Image yang telah dibuat sebelumnya, dapat dengan menggunakan perintah "docker image ls" dan untuk mencoba menjalankan image tersebut dapat dengan menggunakan perintah "docker run (ID image)"
![22](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/22.png)
![23](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/23.png)

- Push Image ke DockerHub
Untuk melakukan proses Push ke DockerHub, kita perlu membuat repository terlebih dahulu pada [hub.docker.com](https://hub.docker.com/), dan pastinya kita harus login docker terlebih dahulu pada terminal tersebut
![24](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/24.png)
![25](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/25.png)

login docker di terminal 
![26](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/26.png)

- Commit n Push
setelah proses login dan pembuatan repo pada dockerhub telah selesai, selanjutnya kita melakukan commit n push image docker sesuai dengan nama container/image yang ingin di masukan ke repo

Disini saya membuat container bernama uts-tc terlebih dahulu dari image tekncloud yang dibuat sebelumnya
![27](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/27.png)
![28](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/28.png)
![29](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/29.png)

- Hasil Repo
![30](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/30.png)
![31](https://github.com/amharnh13/uts-tekn-cloud/blob/master/image/31.png)