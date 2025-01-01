---
title: "Web Ini Hidup di IPFS"
description: "Lebih Jauh Tentang Protokol Distribusi File Terbesar di Planet Bumi"
author: Andi Nugroho
date: 2025-01-31T01:09:00+07:00
draft: false
copyright: "Unless otherwise noted, all blog posts, photos, graphics, presentations and other media and assets are copyrighted work with all rights reserved. Unless otherwise noted, all code snippets are available under the Unlicense."
comments: true
---

Istri penulis berpendapat bahwa penulis memang suka melakukan hal yang tidak perlu, seperti meng-*hosting* blognya sendiri.

Ya memang benar! Hahahaha. Mungkin istri penulis belum mengerti ya apa sih fungsinya meng-*hosting* blog/*website* sendiri. Tulisan ini saya buat bukan sebagai jawaban atas pendapat istri karena memang pendapatnya benar (lagipula wanita selalu benar) namun lebih menuju ke penjelasan, kenapa sih? *why* gitu loh?
Sebagai seorang penulis di *distributed/decentralized website* seperti *website* ini, sangat sulit rasanya jika tidak berbagi tentang hal tersebut.
Selain istri mungkin banyak juga yang bertanya-tanya (asumsi penulis) *sebenarnya apa sih distributed website itu? Apa bedanya sama website biasa? Apa pentingnya desentralisasi dan kenapa saya perlu tahu?*
Sebenarnya pertanyaan terakhir jawabannya **ga perlu tahu juga, tapi ya simak aja yak**.

Kalau kita menilik ke masa lalu, kita akan sadar seberapa jauh manusia berkembang terutama dalam hal teknologi.
Mungkin beberapa dari kita sempat mendengar suara koneksi *dial-up* tiap kali akan terhubung ke internet, dan lihatlah kondisi sekarang dimana internet dan kecepatan tinggi merupakan suatu hal yang menjadi kewajiban dalam berkehidupan sehari-hari. Sangat mencengangkan!

Benar saja, dalam kehidupan manusia saat ini sangat erat hubungannya dengan internet. Tapi ada berapa banyak sih yang mengerti serangkaian teknologi didalam internet tersebut?
*ah yang penting bisa make aja.*
Iya tidak salah memang, namun tidak salah juga kalau kita sedikit tahu kan?

## HyperText Transfer Protocol (HTTP)

HTTP. Internet tidak jauh dari HTTP.

HTTP ini semacam rambu lalu lintas yang ada dijalanan, yang kita sering lihat namun tidak tahu arti dan tujuannya. *Betul?*

{{< figure src="/images/HTTP.jpg" alt="skema HTTP" width="100px" class="about-center" >}}

HTTP sebenarnya sebuah aturan atau protokol dimana tatacara komunikasi antara *client* dan *host* (server) diatur (komunikasi ini disebut *peer-to-peer*). Ada komunikasi antara *client* yang me-*request* *file/dynamic document* (seperti HTML) via *web browser* dimana agar file tersebut dapat diakses oleh si *client*. Misalnya kita ingin mengakses laman berisi video di youtube, maka dengan *web browser* akan di-*translate* untuk menampilkan konten tersebut dari server youtube. Walaupun terlihat ada komunikasi antara client dan server, protokol ini sangat tergantung terhadap apa yang ada di server. Misalnya saja laman video yang kita request dihapus oleh youtube di servernya, maka saat kita ingin mengaksesnya kembali pasti akan mendapatkan warning bahwa laman video tersebut sudah tidak tersedia. Dari sini terlihat peran server sebagai tempat me-maintain segala jenis file yang dapat diakses di internet.

{{< figure src="/images/jkt-hawaii.jpg" alt="jauhnyaaa" width="100px" class="about-center" >}}

Model HTTP ini sangat tersentralisasi di setiap server yang ada. Belum lagi dengan adanya jarak antara server dengan client, misalnya server ada di Jakarta dan client berada di Hawaii, maka request client ke server dan mengirim hasil request tersebut ke client membutuhkan waktu dan biaya yang lumayan banyak. HTTP memang menunjuk file secara lokasi, baik dari segi *geo-location* dan juga lokasi file tersebut di server. Metode ini disebut sebagai *Location-Based Addressing*.

### Location-Based Addressing

Studi kasus. Misalnya kita ingin mencari info tentang Istanbul di situs wikipedia berikut:
```
https://id.wikipedia.org/wiki/Istanbul
```
Ketika kita memasukkan URL tersebut di address bar pada browser, perangkat kita akan meminta/*request* salah satu server dari wikipedia yang mungkin ada dibelahan dunia sana untuk menampilkan laman Istanbul.

Atau ketika kita akan mengakses file **budi.xls** di komputer kita, kita bisa mengetik di address bar file explorer dengan merujuk lokasinya. Contoh:
```
F:\data\penting\budi.xls
```
Sebenarnya kita memerintahkan untuk file explorer untuk pergi ke alamat hard disk **drive F**, didalam folder **data**, lalu ke folder **penting** dimana file **budi.xls** berada.
Inilah yang disebut *Location-Based Addressing*.

Sudah dapat gambarannya? dan kenapa ini problem jika dipakai sebagai protokol internet? Mari kita dalami lagi.

Pertama adalah Sentralisasi. Link pada webiste merupakan identifier yang menunjuk sebuah lokasi di internet, yang mana terdapat di server tertentu yang ditunjuk. [Siapapun yang mengontrol lokasi (server) tersebut, juga mengontrol kontennya](https://flyingzumwalt.gitbooks.io/decentralized-web-primer/content/avenues-for-access/lessons/power-of-content-addressing.html). Walaupun ada sekian ratus orang yang sudah men-*download* konten tersebut, dimana artinya konten tersebut berada diratusan lokasi berbeda, Link pada HTTP tetap akan menunjuk dan hanya akan menunjuk satu tempat, yaitu server. Hal ini juga membuat pemilik yang mengontrol lokasi tersebut dapat menentukan siapa saja yang boleh mengakses konten tersebut. Belum lagi jika ternyata konten tersebut merupakan konten yang bertentangan dengan pemerintah yang opresif misalnya, mudah untuk pemerintah turun tangan untuk melakukan sensor ataupun modifikasi konten tersebut, pemerintah hanya perlu mencari pemilik dari server tersebut dan memintanya untuk menghapus/memodifikasi kontennya. Belum lagi jika ada serangan *DDoS* ke server yang menyebabkan *server down*, tentunya konten yang ada didalam server tidak bisa disajikan ke khalayak umum lagi kan?

Kedua, Histori dan Biaya (ini kedua dan ketiga harusnya). Kita asumsikan bahwa pemilik konten tersebut akan terus menyimpan dan memberikan akses terhadap kontennya kesiapapun. Namun trend dan juga topik hangat di dunia ini sangat dinamis yang menyebabkan ada bahkan banyak penyedia konten menghapus konten yang sudah basi demi terus meningkatkan *traffic* kunjungan atau bahkan dikarenakan biaya untuk me-*maintain* server dan memperbaharui infrastruktur yang semakin mahal. Sebuah studi juga menunjukkan rata-rata sebuah laman web hidup selama [100 hari](https://blogs.loc.gov/thesignal/2011/11/the-average-lifespan-of-a-webpage/) saja. Sebuah sarana bernama internet idealnya dapat menyimpan segala jenis sejarah dan histori yang pernah ditulis, sangatlah tidak elok jika tumpuan hidup masa kini rentan terhadap hal ini.

Problem diatas mengisyaratkan kembali, bahwa tidak seharusnya internet tersentralisasi. Internet seharusnya kembali menjadi terdesentralisasi dengan sensor terhadap internet sangat sulit dan informasi yang ada di internet tidak akan mudah hilang dikarenakan server yang tidak berfungsi sebagaimana mestinya.

*Memangnya ada alternatif lain?*

Oh jelas ada! Untuk mengatasi problem tersebut ada sebuah protokol *peer-to-peer* sama seperti HTTP namun bedanya jika HTTP menganut sistem sentralisasi di server tertentu, protokol ini mendistribusi konten tersebut di banyak node-node (ratusan bahkan ribuan). Bisa dianggap *node* ini seperti server, namun client tidak harus merequest data dari satu server saja. Itulah **IPFS**!

## InterPlanetary File System (IPFS)

Seperti namanya yang diambil sebagai penghormatan terhadap [J.C.R. Licklider](https://en.wikipedia.org/wiki/J._C._R._Licklider#Global_computer_network) dan "*intergalactic computer network*"-nya, IPFS bertujuan untuk merombak kembali internet dengan membuat sebuah protokol *file system* yang menampung semua konten yang ada di muka bumi ini. Berbeda dengan HTTP yang merupakan *Transfer Protocol*, IPFS merupakan *Distribution Protocol* yaitu sebuah aturan untuk mendistribusi file/konten. Masih agak abstrak ya?

Untuk mengerti IPFS, mungkin saya jabarkan dulu apa sih *Distribution Protocol*.

Gampangnya begini, web yang tersentralisasi yang sudah disebutkan diatas berbicara tentang lokasi, lokasi dan lokasi. Sedangkan web yang terdistribusi berbicara tentang konten, bukan lokasi. Hal ini disebut sebagai *Content Addressing*.

*Bedanya?*

Bedanya adalah, Location-Based Addressing memberitahu komputer *dimana* ia akan menemukan file/konten yang ditunjuk, sedangkan IPFS memberitahu *isi konten* apa yang akan dicari.

{{< figure src="/images/mencari-novel.jpg" alt="mencari novel" width="100px" class="about-center" >}}

Agar semakin mudah dipahami, kita coba untuk membuat analogi. Misalnya ada 2 orang sahabat bernama Aci dan Budi. Mereka adalah penggemar Harry Potter. Walaupun mereka penggemar, namun mereka belum pernah membaca bukunya, hanya mengetahui dari film. Sehingga mereka bertanya kepada saya yang kebetulan sedang menulis tentang *distributed website*. Walaupun saya bukan penggemar Harry Potter, namun saya secara ajaib tahu karena saya yang membuat cerita ini. Saya memberikan respon yang berbeda kepada mereka demi memudahkan pembaca mengerti dan memahami apa yang sedang saya tulis.

Kepada Aci saya berkata:
>Novel Harry Potter and the Sorcerer's Stone ya? kamu bisa menemukannya di Perpustakaan Daerah Jalan Gatot Subroto Nomor 1337, Bandung. Posisinya ada di lantai 2 di rak buku bagian fiksi non terjemahan. Tepatnya dirak bagian tengah yang menghadap timur dan berada di pojok kanan atas, urutannya 5 buku dari kanan.

{{< figure src="/images/aci-map.jpg" alt="mumet" width="100px" class="about-center" >}}

Aci lalu pergi ke alamat yang saya berikan serta instruksinya dengan wajah gondok. Setelah ia sampai, tentu dia menemukan novelnya. Ya karena saya bukan orang usil yang suka mengerjai orang.

Kepada Budi saya berkata:
>Novel Harry Potter and the Sorcerer's Stone ya? Ini nomor ISBN-10 nya: 0439708184. Silahkan dicari.

{{< figure src="/images/budi-isbn.jpg" alt="ezpz" width="100px" class="about-center" >}}

Budi lalu mencatat nomor ISBN tersebut dan langsung pergi mencari novel tersebut. Budi memiliki lebih banyak pilihan lokasi untuk mencari novel tersebut, entah di rumah teman, perpustakaan kampus, perpustakaan daerah, toko buku, dan lain sebagainya. Jaminan isi novel akan selalu sama dimanapun ia menemukannya, asalkan kode ISBN nya sama seperti yang sebelumnya sudah dicatat.

Dari sini sebenarnya kita sudah dapat melihat superioritas dari metode yang digunakan kepada Budi. Itulah Content addressing.

Sekali lagi, *Location-Based Addressing* menunjukkan kepada kita dimana harus mencari, sedangkan *Content Addressing* menunjukkan apa yang harus kita cari. Bisa saja jika ternyata di Perpustakaan Daerah ternyata sudah tidak menyimpan novel Harry Potter, Aci akan kebingungan dan tidak akan pernah bisa mendapatkan novel tersebut. Berbeda dengan Budi, walaupun dirumah tetangganya tidak ada novel yang sesuai dengan ISBN-10 tersebut, ia masih punya pilihan untuk mencarinya ditempat lain. Sedangkan Aci? tidak sama sekali, termenung dan merenung akan harapan untuk membaca novel tersebut. Nah, metode yang dipakai oleh Budi yaitu Content Addressing adalah metode yang digunakan pada decentralized web.

### Lebih Jauh tentang Content Addressing

Keren banget ternyata! Eh tapi... Bagaimana *Content Addressing* bekerja? Kini hadir kembali metode kriptografi yang sudah pasti para pembaca tahu yaitu [hashing](https://en.wikipedia.org/wiki/Cryptographic_hash_function).

Secara garis besar, *hashing* mengambil data dari konten dengan ukuran file dan jenis file **apapun** dan mengubahnya menjadi kumpulan huruf dan angka atau *hash* yang jumlah total karakternya sudah ditentukan. Misalnya kita mempunyai sebuah mesin hashing yang merubah berbagai macam konten menjadi *hash* dengan total karakter 8 digit.

Berikut hasil jika melakukan *hashing* file b.doc dengan file size 28mb:
{{< figure src="/images/hashing-machine1.jpg" alt="hash example" width="100px" class="about-center" >}}

*Hashing* file x.doc dengan file size 200mb:
{{< figure src="/images/hashing-machine2.jpg" alt="hash example 2" width="100px" class="about-center" >}}

Bahkan, jika kita memasukkan seluruh isi novel Harry Potter, hasil hashnya masih tetap 8 digit.

Hasil *hashing* ini lah yang digunakan dalam *Content Addressing*, dengan mengetahui hash sebuah konten, maka kita bisa mencari konten dengan isi yang tepat sama dengan membandingkan hasil hash konten tersebut dengan hash yang kita pegang.

Kita praktek ya? 2 Gambar tentang mesin *hashing* yang ada diatas, jika kita *hash* dengan [SHA-256](https://en.wikipedia.org/wiki/SHA-2) maka akan memunculkan *hash* sebagai berikut secara berurutan:
```
QmV9ztZ2TT9G69WEWXmaJZ6jUTRiBae3fqyRpB88ML8fou
QmbZF7HYJHbPayTsDpy4bPLVpyhERxNhqtUpvPHABYFqtz
```
Dengan memegang 2 *hash* ini, kita dapat mencari konten dengan bentuk dan rupa yang sama, tidak akan ketemu gambar yang beda. Karena bahkan jika saya menambah 1 titik hitam di salah satu gambar, hasil hasnya juga akan berbeda. Sekali lagi, hash mengacu kepada isi konten.

Nah, 2 gambar tadi sudah saya masukkan kedalam IPFS, untuk mengecek gambar tersebut kita bisa menggunakan browser dan masuk ke gateway IPFS dengan menyertakan hasil hash tersebut:

```
https://ipfs.io/ipfs/QmV9ztZ2TT9G69WEWXmaJZ6jUTRiBae3fqyRpB88ML8fou
https://ipfs.io/ipfs/QmbZF7HYJHbPayTsDpy4bPLVpyhERxNhqtUpvPHABYFqtz
```

Hanya dengan mengetahui hash gambar diatas, kita bisa mendapatkan gambarnya. Tidak mungkin tertukar. Dan tidak masalah siapa saja yang meng*hosting* gambar tersebut, hasilnya akan sama saja. Bahkan jika ada 100 *node* yang memiliki gambar tersebut diatas, saat kita mengakses maka yang menyediakan gambar tersebut adalah *node* *paling dekat* dari geo-lokasi kita. Kecepatan sudah tidak diragukan lagi, tentunya biaya menjadi lebih murah karena konten tidak perlu ditransfer dari server yang jauh dan memakan bandwidth. Walaupun ada 1 *node* yang sudah tidak meng*hosting* gambar tersebut, jika kita menggunakan IPFS, maka gambar tersebut tetap akan ada selama ada *node* lain yang meng*hosting* gambar tersebut. Bahkan jika kita sudah menginstall IPFS, saat kita mengakses gambar tersebut otomatis komputer akan diperintahkan untuk meng-cache gambar tersebut dan meng*hosting*nya! Resistan sekali bukan!

Dengan begini, masalah sentralisasi, biaya, dan penjagaan histori yang terjadi pada *centralized web* akan hilang.

### Jadi Apa itu IPFS ?

{{< figure src="/images/IPFS.jpg" alt="IPFS" width="100px" class="about-center" >}}

Sekarang gambar diatas akan *makes sense*. IPFS adalah sebuah protokol distribusi sistem file secara cakupan intra-planet dimana setiap *node* melakukan hashing terhadap konten yang akan di-*hosting* dan menginformasikan kepada *node* yang lain. Ketika ada *node* yang mengakses hash dari konten di *node* lain, otomatis *node* yang mengakses itu akan diberi copy dari konten dan hashnya, sehingga *node* tersebut juga menjadi *host* terhadap konten yang baru saja ia akses. Tidak ada sama sekali server sentral disini, semua di-*host* oleh node-node yang aktif menjalankan protokol IPFS.

### Kekurangan IPFS
Setelah sekian paragraf membahas tentang Kelebihan dari IPFS, adalah fair jika saya juga membahas tentang kekurangan protokol ini. Ya memang karena IPFS sendiri sampai saat ini masih tahap alpha sehingga sedang gencar-gencarnya didevelop agar lebih baik.

Beberapa hal yang dapat diperbaiki kedepannya untuk IPFS:

* Ketersediaan Konten yang di-*hosting*

  Karena konten diambil dari node-node yang online, ketika semua *node* yang memiliki copy dari konten tersebut offline maka konten tersebut tidak dapat ditemukan. Hal ini sama seperti jika torrent tidak memiliki seeders. Workaround yang dilakukan untuk saat ini adalah memberikan insentif kepada *node* yang menyimpan dan melakukan hosting konten di distributed web. Protokol ini disebut [FileCoin](https://docs.filecoin.io/about-filecoin/ipfs-and-filecoin/).

* Tidak *Human Readable*

  Seperti contoh gambar yang sebelumnya saya jabarkan, link dari IPFS sangat... Eh bukan sangat lagi, namun tidak bisa dibaca manusia. Bayangkan saja jika ingin mengakses gambar tadi kita harus menggunakan link:
  > https://ipfs.io/ipfs/QmV9ztZ2TT9G69WEWXmaJZ6jUTRiBae3fqyRpB88ML8fou

  Bahkan mata pun sakit melihatnya.

  Bagaimana jika kita menggunakan IPFS sebagai tempat meng*hosting* website? Seperti Website ini? Tentu saya akan pusing untuk me-*manage link* dari IPFS, dimana setiap ada postingan baru ataupun ketika saya melakukan perubahan konfigurasi web, tentu hasil *hash* nya akan berbeda. Ibaratnya setiap saya mengupdate *website*, tentu *hash*-nya berbeda, dan membuat link ke website ini berubah-ubah.

  Solusi saat ini yang bisa dipakai adalah dengan menggunakan IPNS (InterPlanetary Naming System), yaitu sebuah *hash* dari *public key* dimana hash ini tidak akan berubah karena hash ini hanya sebagai penghubung terhadap konten asli yang hashnya sudah di sign oleh *private key*.

  Selain itu, ada juga [DNSLink](https://docs.ipfs.io/concepts/dnslink/) dan [ENS](https://docs.ens.domains/) yang dapat digunakan untuk mengubah link *hash* dari IPFS menjadi *human readable* yang manusiawi.


Memang IPFS masih jauh dari kata sempurna dan mungkin memang belum saatnya untuk IPFS mengubah cara kerja internet. Tetapi bukan berarti kita tidak perlu menjadi orang-orang yang melakukan perubahan diawal revolusi decentralized web. Tidak ada salahnya untuk menjadi *early adopter*.

Sekian dari saya. Untuk section selanjutnya merupakan sumur teknikal yang mungkin tidak semua orang perlu baca. Jadi *see you on the next post!*


## Practical Guide

### Instalasi

1. Download Linux binary IPFS
```
wget https://dist.ipfs.io/go-ipfs/v0.8.0/go-ipfs_v0.8.0_linux-amd64.tar.gz
```
2. Unzip file tersebut
```
tar -xvzf go-ipfs_v0.8.0_linux-amd64.tar.gz

> x go-ipfs/install.sh
> x go-ipfs/ipfs
> x go-ipfs/LICENSE
> x go-ipfs/LICENSE-APACHE
> x go-ipfs/LICENSE-MIT
> x go-ipfs/README.md
```
3. Masuk ke direktori go-ipfs dan install via script
```
cd go-ipfs
sudo bash install.sh

> Moved ./ipfs to /usr/local/bin
```
4. Cek apakah IPFS sudah terinstall
```
ipfs --version

> ipfs version 0.8.0
```

### Inisialisasi repository

IFPS menyimpan seluruh *setting*-nya beserta data internal di folder repository yang perlu kita init.

```
ipfs init

> initializing ipfs node at /Users/sutasoma/.ipfs
> generating 2048-bit RSA keypair...done
> peer identity: Qmcpo2iLBikrdf1d6QU6vXuNb6P7hwrbNPW9kLAH8eG67z
> to get started, enter:
>
>   ipfs cat /ipfs/QmYwAPJzv5CZsnA625s3Xf2nemtYgPpHdWEz79ojWnPbdG/readme
```
Jika kita melakukan command ```ipfs cat /ipfs/QmYwAPJzv5CZsnA625s3Xf2nemtYgPpHdWEz79ojWnPbdG/readme``` maka akan muncul:

```
Hello and Welcome to IPFS!
██╗██████╗ ███████╗███████╗
██║██╔══██╗██╔════╝██╔════╝
██║██████╔╝█████╗  ███████╗
██║██╔═══╝ ██╔══╝  ╚════██║
██║██║     ██║     ███████║
╚═╝╚═╝     ╚═╝     ╚══════╝
If you're seeing this, you have successfully installed
IPFS and are now interfacing with the ipfs merkledag!
-------------------------------------------------------
| Warning:                                              |
|   This is alpha software. Use at your own discretion! |
|   Much is missing or lacking polish. There are bugs.  |
|   Not yet secure. Read the security notes for more.   |
 -------------------------------------------------------
Check out some of the other files in this directory:
./about
  ./help
  ./quick-start     <-- usage examples
  ./readme          <-- this file
  ./security-notes
```
Command ```ipfs cat``` berfungsi untuk melihat isi file dari *object* ipfs, dalam hal ini kita melihat file dari ```/ipfs/QmYwAPJzv5CZsnA625s3Xf2nemtYgPpHdWEz79ojWnPbdG/readme```.

### Menambahkan File ke IPFS

Untuk menambahkan file ke IPFS sangat mudah:

```
echo "Hello World" > hello.txt
```
Lalu gunakan command add untuk menambahkan file tadi:
```
ipfs add hello.txt
```
Return dari command tadi adalah hash yang berawalan Qm yang dapat digunakan untuk mengakses konten dari hello.txt.

Untuk mengecek file apa saja yang sudah kita masukkan ke IPFS bisa dengan command:
```
ipfs pin ls
```

### Berinteraksi dengan Node Lain

Semua yang tadi kita lakukan masih dalam lingkup lokal, artinya file hello.txt tadi sudah kita ubah menjadi object IPFS namun belum bisa diakses oleh orang lain. Agar file tersebut dapat diakses orang lain maka kita perlu melakukan init pada ipfs daemon:
```
ipfs daemon
```
Setelah itu kita dapat mengecek siapa saja node yang menjadi peers kita:
```
ipfs swarm peers
```
Dengan menggunakan command ```ipfs daemon``` kita juga telah melakukan set up pada localhost dimana kita dapat berinteraksi dengan IPFS network via browser. Port yang digunakan secara default adalah 8080.

Mari kita lihat file kita menggunakan browser dengan menuju alamat:
```
localhost:8080/ipfs/<hash>
```
Tersedia juga web UI yang cukup cantik. Kita dapat mengaksesnya di:
```
127.0.0.1:5001/webui
```

Silahkan bereksplorasi, dan jika ingin lebih detil, kita dapat mengakses dokumentasinya [disini](https://docs.ipfs.io/).
