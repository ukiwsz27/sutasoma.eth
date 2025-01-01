---
author: Andi Nugroho
title: "Ethereum : Bitcoin 2.0"
description: dan mengapa ini penting
date: 2025-01-29T14:32:05+07:00
draft: false
copyright: "Unless otherwise noted, all blog posts, photos, graphics, presentations and other media and assets are copyrighted work with all rights reserved. Unless otherwise noted, all code snippets are available under the Unlicense."
comments: true
---

*sebelumnya telah di-post di [sini](https://sutasomablog.wordpress.com/2017/10/29/ethereum-bitcoin-2-0/).*

Bagi para pengamat cryptocurrency, nama Ethereum mungkin sudah tidak asing lagi, terlebih sejak setahun lalu di akhir kuartal 2016 terdapat salah satu website exchange indonesia yang mengadopsi Ether (disingkat Eth, token untuk Ethereum) dan mulai bersaing di pasar nasional menyaingi Bitcoin. Kini Ethereum sudah cukup populer dikalangan para pengamat cryptocurrency. Kepopuleran ini dipicu dari beberapa hal umum yang membedakan Ethereum dengan Bitcoin ataupun cryptocurrency lainnya.

Sampai saat ini sudah banyak blog atau web indonesia yang membahas tentang Bitcoin, namun bisa dibilang hanya beberapa blog yang menjelaskan tentang Ethereum, sangat sedikit. Awal mula blog ini sebenarnya memang ditujukan untuk para peminat Ethereum yang ingin mendapatkan info tentang teknologi ini. Namun untuk awalan, ada baiknya pada tulisan kali ini dijelaskan secara mudah apa sebenarnya Ethereum, apa bedanya Ethereum dengan Bitcoin, dan kenapa Ethereum sering disebut Bitcoin 2.0 oleh para pengamatnya.

# Sejarah Singkat

Bitcoin pada awal mulanya hadir sebagai token untuk transaksi saja. Namun perkembangan dan pemanfaatan teknologi blockchain sebenarnya sangat luas, muncul beberapa coin yang membawa terobosan teknologi lain, mulai dari LiteCoin, Ripple, Dash, Monero, ZCash, ZCoin dan Ethereum yang baru-baru ini muncul ke permukaan.
Padahal blockchain sendiri sebenarnya tidak hanya dapat digunakan sebagai media pertukaran/transaksi uang saja. Potensi lain yang dimiliki blockchain tidak tereksploitasi secara utuh, seperti asuransi aset, crowdfunding, proses voting, registrasi domain dan banyak lagi potensi yang bisa didapat karena sifat blockchain yang terdesentralisasi dan immutable.

{{< figure src="/images/kalkulator.jpg" alt="kalkulator" width="100px" class="about-center" >}}

Problemnya adalah seperti gambar diatas, sebagian besar blockchain didesain seperti kalkulator, ia sangat baik dalam melakukan satu hal yaitu menghitung. Padahal potensi blockchain begitu luas, keterbatasannya dibuat karena desain yang sempit, ya seperti kalkulator.
Bisa saja kita membuat blockchain berbeda untuk fungsi yang berbeda, misalnya blockchain A yang fokus dalam transaksi keuangan, blockchain B yang fokus dalam crowdfunding, tapi itu tidak praktis.
Bagaimana jika membuat blockchain yang dapat melakukan segala hal diatas? Caranya bagaimana?

Bicara tentang ethereum tidak terlepas dari bicara tentang Vitalik Buterin, seorang researcher dan programmer dalam bidang cryptocurrency. Pada tahun 2013 akhir, Vitalik mempropose sebuah scripting language yang disematkan dalam Bitcoin untuk kepentingan application development yang terdesentralisasi. Namun, pengajuannya ditolak dan pada awal januari 2014 ia dan timnya mendesign sebuah platform dengan general scripting language, yaitu Ethereum.

**Hah? Maksudnya?**

Oke bagi sebagian kita yang awam mungkin akan bingung saat membaca sejarah singkat diatas, apalagi yang awam tentang programming language dan cryptocurrency.

Jadi begini, yang ingin diajukan oleh Vitalik adalah sebuah tempat (platform) dimana kita bisa membuat sebuah program simpel yang disemat dalam blockchain dan dapat diakses oleh publik. Dengan sifat blockchain yang terdesentralisasi dan immutable (tidak bisa disensor) maka kita dapat membuat sebuah program dimana apa yang terprogram didalamnya akan selalu berjalan sesuai dengan apa yang ditulis. Menarik bukan?

Bayangkan sebuah program dimana seluruh sifat blockchain ada pada dirinya, keamanan yang tinggi serta akan selalu berjalan sesuai yang di program kan, apa itu tidak menarik?

Platform itulah yang dinamakan Ethereum, dan program tersebut disebut Smart Contract.

# Smart Contract

{{< figure src="/images/aci-kakek.jpg" alt="aci kakek" width="100px" class="about-center" >}}

Kakek Aci suatu hari ingin pergi ke jakarta untuk menemui anaknya yang akan menikah 15 hari lagi. Namun ia memiliki keterbatasan finasial. Untungnya si Aci mengenal smart contract dan ia pun membuat sebuah smart contract pada blockchain Ethereum. Kira-kira begini bunyinya:

* Saya ingin mengadakan crowdfunding untuk perjalanan Kakek saya ke Jakarta.
* Estimasi biaya: Rp 500.000
* Estimasi waktu perjalanan: 2 hari
* Sehingga saya perlu mendapatkan uang sebesar Rp 500.000 paling telat dalam waktu 13 hari kedepan.
* Siapapun boleh melakukan donasi ke alamat 0xsmartcontractaci, ketika uang terkumpul sebesar Rp 500.000 maka uang tersebut akan langsung tertransfer ke alamat 0xkakekaci. Namun jika uang tidak terkumpul sebesar Rp. 500.000 dalam waktu 13 hari maka uang yang telah terdonasi akan otomatis kembali ke masing-masing donatur.
* Reward untuk yang sudah melakukan donasi adalah diskon belanja di warung aci (dengan melampirkan bukti transfer ke 0xsmartcontractaci)
***

Anggaplah tulisan diatas merupakan sebuah code dalam Smart Contract yang dibuat oleh Aci (yang seharusnya ditulis dalam bahasa solidity).

{{< figure src="/images/aci-kakek-coding.jpg" alt="aci coding" width="100px" class="about-center" >}}

Aci lalu mengirimkan code Smart Contract tersebut kedalam blockchain Ethereum, dan setelah beberapa block time, Smart Contract tersebut dapat digunakan untuk 13 hari kedepan.

{{< figure src="/images/aci-kakek-skema.jpg" alt="skema" width="100px" class="about-center" >}}

dari gambar diatas, para donatur mendapatkan kepastian jika donasi tidak mencapai 500.000 dalam 13 hari maka uang mereka kembali. Namun ketika sudah mencapai 500.000 maka uang tersebut akan masuk kedalam mangkuk kakek Aci (wallet) dan dapat digunakan oleh kakek Aci. Para donatur yang sebelumnya menerima bukti transaksi (Tx) dapat membuktikannya secara digital untuk mendapatkan diskon belanja di warung Aci. Semua senang!

Jika boleh berpendapat, Smart Contract untuk donasi/crowd funding ini sebenarnya sangat bermanfaat bagi banyak start-up yang akan merintis bisnis, bisa saja dalam code Smart Contract untuk para start-up menggunakan code Aci diatas dan dimodif serta ditambahkan misalnya milestone yang ingin dicapai adalah dalam 10 bulan setelah proses crowd funding selesai. Maka bisa di state dalam Smart Contract bahwa fund yang telah di invest para investor akan cair ke pihak start-up sebanyak 10% setiap bulannya.

Ingat! Hal yang telah disebutkan diatas akan berjalan secara automatic dan tanpa perlu ada yang mengontrol, tanpa perlu ada middleman dalam mengatur fund yang telah diproses kedalam Smart Contract. Tidak perlu khawatir fund anda di tilep, misalnya pada Contract Kakek Aci, ketika sudah 500.000 maka uangnya malah masuk ke alamat mbok Ijah, itu tidak mungkin karena sudah di state diawal pembuatan contract bahwa alamat pengiriman fund donasi adalah alamat kakek Aci. Dan itu tidak dapat diubah! Trustless!

Betapa luas penggunaan Smart Contract pada Ethereum ini. Yang saya sebutkan diatas hanya sebuah contoh kecil dari apa yang bisa dibuat dalam platform ini. Bahkan kita dapat membuat Token sendiri, Decentralized Organization sendiri, dan lain-lain!

Jika Bitcoin hanya membawa dirinya sebagai nilai tukar, maka inilah Ethereum dengan seluruh apa yang bisa Bitcoin lakukan ditambah potensi tak terbatas dari Smart Contract! Welcome to Bitcoin 2.0!
