---
author: Andi Nugroho
title: Mengenal Blockchain
description: dan membedakan bitcoin dengan blockchain
date: 2025-01-01
copyright: "Unless otherwise noted, all blog posts, photos, graphics, presentations and other media and assets are copyrighted work with all rights reserved. Unless otherwise noted, all code snippets are available under the Unlicense."
comments: true
---


*sebelumnya telah di-post di [sini](https://sutasomablog.wordpress.com/2017/05/28/mengenal-blockchain/).*

Tak bisa dipungkiri perkembangan teknologi semenjak 5 dekade terakhir berkembang begitu pesat. Munculnya beberapa teknologi *disruptive* (teknologi dengan pola atau metode tidak biasa yang menggantikan teknologi yang di-*disrupt*) mau tidak mau menjadi pemantik pada perkembangan yang pesat ini. Misalnya saja, penemuan mikroprosesor semikonduktor pada tahun 1960 yang men-*disrupt* penyimpanan data konvensional (fisik, pada tahun itu) menjadi data digital merupakan sebuah terobosan yang bisa dibilang pintu gerbang menuju era digital yang sedang kita nikmati saat ini. Berpindahnya penyimpanan data dari fisik ke digital memicu efek yang besar terutama dalam bidang perbankan, teknologi tersebut diadopsi dan dikembangkan sehingga pencatatan data perbankan bisa dilakukan secara digital. Bayangkan sebelumnya bank-bank tersebut menyimpan beratus-ratus buku besar untuk mencatat setiap transaksi nasabahnya, dan ketika suatu saat terjadi musibah yang membuat buku-buku tersebut tidak dapat dibaca merupakan petaka bagi bank dan nasabahnya.

Kita melompat dari 1960 ke 2017, mungkin terlalu jauh, kita kembali ke November 2008, saat seorang atau sekelompok orang dibawah nama Satoshi Nakamoto mengirimkan sebuah paper dalam milis *cryptography* dengan judul "*Bitcoin: a Peer-to-Peer Cash System*" yang dalam isinya terdapat cara untuk membuat sebuah jaringan atau network yang mencanangkan transaksi elektronik *trustless*, tanpa bergantung pada siapapun, maksudnya transaksi bisa dilakukan oleh siapapun dan kapanpun tanpa harus ada yang menjadi perantara (pihak ketiga).

Lalu? Kenapa bisa *trustless*? Mekanismenya seperti apa sih?

# SISTEM BLOCKCHAIN
Untuk memulai mengerti Bitcoin/*Cryptocurrency* lain, ada baiknya kita mengupas terlebih dahulu yang menjadi punggung dari perhelatan *cryptocurrency* di dunia ini. Tidak lain tidak bukan yaitu sistem *Blockchain*.

Masih ingat dengan buku-buku pencatat transaksi di bank yang sebelumnya pernah disinggung?

Ya, itulah *blockchain*.

**Lho? Kok bisa?**

Blockchain memiliki mekanisme yang sama dengan pencatatan transaksi, perbedaannya adalah dalam hal kepemilikan pencatatan transaksi dimana blockchain ini tidak dimiliki oleh siapapun. Jika kita berbicara bank, pencatatan transaksi pada bank dikelola oleh bank itu sendiri, dan ketika ada orang yang tidak bertanggung jawab ingin mengubah isi dari transaksi. Ekstrimnya jika ada serangan *DDoS* / meteor jatuh dan menghantam arsip digital dari bank tersebut, bisa jadi aktivitas bank akan down untuk sementara sampai bisa teratasi oleh pihak bank tersebut.

**Bagaimana dengan blockchain?**

Blockchain sendiri merupakan sebuah distribusi dari database, bayangkan sebuah file *spreadsheet* yang berisi transaksi, dimana setiap orang dapat me-*request* transaksi yang tercatat dalam spreadsheet tersebut. Uniknya spreadsheet tersebut tersebar atau memiliki salinan beratus-ratus ribu spreadsheet, dengan isi yang sama tentunya, yang tersimpan dalam setiap *node* (komputer/perangkat yang terhubung langsung dengan jaringan blockchain) yang terupdate setiap jeda waktu tertentu. Jika terjadi DDoS dalam sebuah/beberapa node, network dari blockchain dapat memitigasi serangan ini dan sistem transaksi masih tetap berjalan sebagaimana mestinya.

Secara singkat dapat kita simpulkan bahwa database tersebut tidak tersimpan di satu lokasi/komputer saja, dan dapat dengan mudah diakses oleh siapa saja (public) namun tingkat keamanan sangat tinggi karena tidak ter-centralized pada suatu lokasi alias ter-decentralized, meaning kalau misalnya ada node iseng mengganti isi spreadsheet tersebut sesuai kemauan si dia misalnya mentransfer 10 Bitcoin ke address wallet seseorang, ini tidak mungkin terjadi, karena setiap perubahan di spreadsheet akan diverifikasi oleh sang validator.

**Validator? Apa itu?**

Tentunya dalam mengolah spreadsheet (penulis meningatkan bahwa spreadsheet ini hanya sebuah umpama ya, untuk memudahkan analogi dari blockchain tersebut) pada blockchain diperlukan seorang validator, yaitu node terpilih (biasanya disebut *miner*) yang melakukan validasi block transaksi request dari para pengguna blockchain dengan menggunakan algoritma yang ditentukan agar transaksi tersebut dapat diproses sebagaimana mestinya.

{{< figure src="/images/infographics0517-01.png" alt="skema blockchain" width="100px" class="about-center" >}}

Gambar diatas merupakan skema blockchain, diambil dari [sini](https://blockgeeks.com/guides/what-is-blockchain-technology/).

Bayangkan seseorang user melakukan request untuk mengirim 1 Bitcoin dari address miliknya bernama address A ke address B.

Anggaplah address A memiliki 1 Bitcoin, dan address B memiliki 0 Bitcoin.

Request dan status user tersebut akan dilanjutkan ke node-node terhubung untuk diverifikasi, lalu dengan menggunakan metode Proof-of-Work (bukti sudah bekerja), akan dipilih satu node untuk memvalidasi block yang berisi transaksi tersebut beserta transaksi dari user-user lain (yang dihimpun dalam satuan block time, yaitu waktu yang diperlukan untuk membuat sebuah block) dan dibuatlah sebuah block berisi data transaksi dan disematkan dalam ledger blockchain tersebut. Block ini ketika sudah tercipta, tidak dapat diutak-atik artinya block ini permanen. Block tersebut diidentifikasi dengan block height, atau ketinggian block yang berupa angka. Untuk contoh diatas misalnya block height nya 1089, ketika kita mengecek block tersebut kita dapat melihat bahwa address A mengirimkan 1 Bitcoin ke address B.

{{< figure src="/images/contoh-block-height.png" alt="block height 468549" width="100px" class="about-center" >}}

contoh gambar [diatas](https://blockchain.info/block/00000000000000000046afac9ff60e22d3d80e6e932e43aebc9bd0dd298e1a9b) adalah contoh block height 468549 milik Bitcoin, beberapa data seperti banyak transaksi yang ada di block tersebut, isi transaksi yang ada, dan beberapa data lain dapat dilihat. Its openly public, anyone can see it.

Namun, metode *Proof-of-Work* mengharuskan node-node (*miner*) untuk melakukan pemecahan serangkaian problem matematis agar ia dianggap telah bekerja, sehingga miner tersebut dapat menjadi kandidat bahwa ia telah melakukan suatu kerja yang cukup untuk menjadi validator terpilih.

Problem matematis tersebut memiliki difficulty (disebut *block difficulty*) yang berhubungan dengan jumlah miner yang terhubung dan *block time*. Semakin banyak node terhubung maka semakin sulit problem tersebut.

Metode *proof-of-work* ini mengharuskan miner untuk terus menerus melakukan kalkulasi/*hashing* sampai mendapat jawaban yang benar dan dapat dipilih menjadi validator. Tentunya komputer yang melakukan kalkulasi/*hashing* tersebut membutuhkan waktu dan biaya listrik yang sangat amat besar, karena dari ribuan miner tersebut hanya ada satu node terpilih yang bisa memvalidasi block. Bisa saja node selama 24 jam tidak menjadi validator terpilih, bayangkan biaya listrik yang dimakan oleh CPU/GPU komputer tersebut yang berjalan hampir 100% terus menerus.

**Lalu apa gunanya menjadi *miner*?**

Keuntungan menjadi miner sangatlah besar saat menjadi validator, selain mendapatkan *transaction fees* dari transaksi-transaksi yang *miner* cantumkan di block yang ia temukan, ia mendapat bayaran dari blockchain tersebut. Jika kita membicarakan Bitcoin, maka bayaran miner tersebut sebesar 12.5 Bitcoin (untuk saat artikel ini ditulis, karena reward dari Bitcoin sendiri berkurang setengah setiap 210.000 block height). Berapa harga 1 Bitcoin? Silahkan googling sendiri.

Reward dari menemukan block ini merupakan apresiasi kepada miner validator terpilih karena telah ikut andil dalam menjaga keamanan dan stabilitas dari blockchain itu sendiri, reward ini adalah satu-satunya cara untuk mendapatkan token dari blockchain yang node jalankan (well, dalam kasus ini token itu adalah Bitcoin).

Untuk mengubah isi dari transaksi, setidaknya butuh 51% ***computational power*** dari seluruh node yang terhubung, dan untuk melakukan hal tersebut butuh biaya yang sangat besar, hal ini menyebabkan keamanan dan legitimasi dari transaksi yang dilakukan pada blockchain sangatlah tinggi.

# KESIMPULAN

*Decentralization* memang merupakan sebuah jargon yang dicanangkan oleh sistem blockchain, dimana dalam hal tersebut tidak ada pihak central yang mengatur bagaimana dan tidak ada yang memiliki blockchain tersebut. Blockchain itu milik publik dan dapat diakses oleh publik.

Manfaatnya untuk khalayak umum?

Sangat banyak tentunya.

Selain untuk melakukan transaksi yang bersifat trustless, yakin sampai, tidak mungkin dana transaksi dicolong orang, ada banyak lagi manfaat dari sistem blockchain ini. Kita bisa saja mencatat seluruh sejarah manusia di blockchain, atau mencatat identitas diri kita pada blockchain. Yang paling seru adalah menulis program dalam blockchain, yang biasa disebut *smart contract*, yang akan selalu berjalan sesuai apa yang diprogramkan.

Penasaran? Nantikan di artikel selanjutnya!
