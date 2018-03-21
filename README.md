
# Aplikasi Streaming Musik : mStream


<h5 align="center"><img src="http://www.mstream.io/img/logos/mstream-logo.png"</h5>

![enter image description here](https://github.com/IrosTheBeggar/mStream/raw/master/public/img/devices2.png?raw=true)

[Deskripsi](#deskripsi-mstream) | [Instalasi](#instalasi) | [Referensi](#referensi) 
:---:|:---:|:---:

## Deskripsi mStream
mStream adalah layanan server streaming personal. mStream memungkinkan seseorang untuk men-streaming lagu dari server miliknya, seperti komputer rumah ke semua device, dimana saja.
mStream menggunakan nodejs sebagai platformnya. Nodejs bekerja sebagai server / backend layaknya Apache/Nginx/.Net, dll.

# Instalasi

#### Prasyarat Sebelum Memasang mStream

- Menginstall Ubuntu Server di virtual box dengan konfigurasi seperti berikut pada tab network:
![](https://i.imgur.com/RJHf9Vg.png)
- Menginstall ssh pada client remote
- Menginstall nodeJS, npm, dan juga git pada client server

##### Langkah Instalasi pada CLI

######  Install NodeJS & git
- Pertama, praktikan meng-install nodejs dengan mendownload file-nya melalui metode curl :
`$ curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -`
- Setelah selesai praktikan menginstall nodejs :
`$ sudo apt-get install -y nodejs`
- Kemudian, praktikan menginstall git :
`$ sudo-apt-get install git`

##### Install mStream
- Praktikan kemudian men-clone data dari github :
`$ git clone https://github.com/IrosTheBeggar/mStream.git`
- Setelah berhasil di clone, praktikan masuk ke dalam folder mStream :
`$ cd mStream`
- Lalu meng-install mStream :
`$ npm install --only=production`
`$ sudo npm link`

##### Meng-update mStream
- Jika terdapat perubahan pada mStream dan perlu di update, maka praktikan harus menarik perubahan dari git dan reboot server :
`$ git pull`

##### Menggunakan mStream
- Untuk menggunakan server mStream, ketikan `$ mstream` di terminal. Standarnya, mstream akank menggunakan port 3000, jadi mstream dapat diakses melalui http://localhost:3000/ pada browser.


##### Konfigurasi Opsional
- Praktikan juga dapat membuat folder musik dengan flag `$ -m` (contoh: `$ mstream -m /path/to/your/music`). Praktikan harus menuliskan seluruh jalur filenya. Jika tidak, mStream akan menggunakan direktori yang sekarang.

- Praktikan bisa memasang user dan password pada server dengan menggunakan flag `$ -u` dan `$ -x` (contoh: `$ mstream -u admin -x password`). Jika praktikan tidak menggunakan flag ini, maka servernya akan bisa diakses oleh semua orang.
##### Otomatisasi
- Praktikan dapat membuat file bash launch script dan menjalankannya pada saat server dijalankan
`$ editor launchscript.sh`
dengan menambahkan perintah-perintah yang dapat dilakukan oleh mstream seperti meload database, login, path music, dan lain lain
contoh:
`mstream -u admin -x password -m ./mStream/music -d mstream.db`
dengan menulis perintah diatas di file launchscript,maka ketika dijalankan file tersebut akan melakukan command yang sudah dituliskan di file tersebut
Perintah command lainnya dapat diakses di [sini](https://github.com/IrosTheBeggar/mStream/blob/master/docs/cli_arguments.md)
##### Keuntungan dan Kekurangan dari Aplikasi Sejenis
- Instalasi lebih mudah dan cepat dibandingkan aplikasi sejenis, seperti sonorezh
-  Supports file FLAC streaming
-   Built in SQLite DB. Tidak perlu konfigurasi database eksternal
-   Akun guest
-   Automatic port forwarding
- File Explorer
- UI kurang baik namun cukup responsive
# Referensi
1. [mStream About](http://www.mstream.io/about)
2.	[Reddit](https://www.reddit.com/r/selfhosted/comments/4zj5ad/mstream_a_selfhosted_music_streaming_server/)
3.	[Running Command with Bash](http://matt.might.net/articles/bash-by-example/)


