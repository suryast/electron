# Distribusi Aplikasi

Untuk mendistribusikan aplikasi Anda dengan Electron, Anda perlu mendownload Electron's [prebuilt binaries](https://github.com/electron/electron/releases). Selanjutnya, folder yang berisi aplikasi Anda harus diberi nama `app` dan ditempatkan di direktori *resources* seperti yang ditunjukkan pada contoh berikut. Perhatikan bahwa lokasi *prebuilt binaries* Electron diindikasikan dengan `elektron /` seperti contoh berikut.

Di macOS:

```text
electron/Electron.app/Contents/Resources/app/
├── package.json
├── main.js
└── index.html
```

Di Windows dan Linux:

```text
electron/resources/app
├── package.json
├── main.js
└── index.html
```

Kemudian jalankan `Electron.app` (atau` electron` di Linux, `electron.exe` pada Windows), dan Elektron akan mulai sebagai aplikasi Anda. Direktori `electron` akan menjadi direktori distribusi Anda untuk dikirim ke pengguna aplikasi.

## Kemasan Aplikasi Anda ke File

Terlepas dari pengiriman aplikasi Anda dengan menyalin semua file sumbernya, Anda juga bisa kemas aplikasi Anda ke arsip [asar](https://github.com/electron/asar) guna menghindari memperlihatkan kode sumber aplikasi Anda kepada pengguna.

Untuk menggunakan arsip 'asar` untuk mengganti folder `app`, Anda perlu mengganti nama arsip ke nama `app.asar`, dan letakkan di bawah direktori sumber Elektron seperti di bawah, dan Elektron kemudian akan mencoba membaca arsip dan memulai dari situ.

Di macOS:

```text
electron/Electron.app/Contents/Resources/
└── app.asar
```

Pada Windows dan Linux:

```text
electron/resources/
└── app.asar
```

Keterangan lebih lanjut dapat ditemukan di [Application packaging](application-packaging.md).

## Rebranding dengan Binari Download

Setelah menggabungkan aplikasi Anda ke Elektron, Anda akan ingin mengubah *branding* Elektron Sebelum mendistribusikannya ke pengguna.

### Windows

Anda dapat mengganti nama `electron.exe` menjadi nama yang Anda sukai, dan edit ikonnya dan informasi yang lainnya  dengan tool seperti [rcedit](https://github.com/atom/rcedit).

### macOS

Anda dapat mengganti nama `Electron.app` menjadi nama yang Anda inginkan, dan Anda juga harus mengganti nama
Field `CFBundleDisplayName`,` CFBundleIdentifier` dan `CFBundleName` di
File berikut:

* `Electron.app / Isi / Info.plist`
* `Electron.app/Contents/Frameworks/Electron Helper.app / Isi / Info.plist`

Anda juga dapat mengganti nama aplikasi penolong agar tidak menampilkan `Elektron Helper` di
Activity Monitor, tapi pastikan Anda telah mengganti nama aplikasi penolong yang dapat dijalankan
Nama file

Struktur aplikasi berganti nama menjadi seperti:

`` `
MyApp.app/Contents
├── Info.plist
├── MacOS /
│ └── MyApp
└── Kerangka /
    ├── Helper MyApp EH.app
    | ├── Info.plist
    | └── MacOS /
    | └── Helper MyApp EH
    ├── Helper MyApp NP.app
    | ├── Info.plist
    | └── MacOS /
    | └── MyApp Helper NP
    └── Helper.app MyApp
        ├── Info.plist
        └── MacOS /
         └── Pembantu MyApp
`` `

### Linux

Anda dapat mengganti nama `electron` yang dapat dieksekusi dengan nama yang Anda sukai.

## Alat Bungkus Kemasan

Selain mengepak aplikasi Anda secara manual, Anda juga dapat memilih untuk menggunakan pihak ketiga
Alat pengemasan untuk melakukan pekerjaan untuk Anda:

* [Pembangun elektron] (https://github.com/electron-userland/electron-builder)
* [Electron-packager] (https://github.com/electron-userland/electron-packager)

Rebranding dengan Membangun Kembali Elektron dari Sumber

Hal ini juga memungkinkan untuk mengubah citra Elektron dengan mengubah nama produk dan
Membangun dari sumber. Untuk melakukan ini, Anda perlu memodifikasi file `atom.gyp` dan
Memiliki bersih membangun kembali.

### grunt-build-atom-shell

Secara manual memeriksa kode Elektron dan pembangunan kembali bisa jadi rumit
Tugas Grunt telah dibuat yang akan menangani ini secara otomatis:
[Grunt-build-atom-shell] (https://github.com/paulcbetts/grunt-build-atom-shell).

Tugas ini secara otomatis akan menangani pengeditan file `.gyp`, yang dibuat dari
Sumber, kemudian membangun kembali modul asli Node aplikasi Anda agar sesuai dengan yang baru
Nama yang dapat dieksekusi

### Membuat Fork Elektron Kustom

Membuat garpu khusus Elektron hampir pasti bukan sesuatu yang akan Anda lakukan
Perlu dilakukan untuk membangun aplikasi Anda, bahkan untuk aplikasi "Tingkat Produksi".
Menggunakan alat seperti `electron-packager` atau` electron-builder` akan memungkinkan Anda melakukannya
"Rebrand" Electron tanpa harus melakukan langkah-langkah ini.

Anda perlu garpu Elektron bila Anda memiliki kode C + + kustom yang telah Anda tambakan
Langsung ke Elektron, yang entah tidak bisa di hulu, atau sudah ditolak
Dari versi resmi Sebagai pengelola Elektron, kami sangat menginginkannya
Untuk membuat skenario Anda bekerja, jadi tolong usahakan sekeras yang Anda bisa untuk mendapatkan perubahan Anda
Ke versi resmi Elektron, akan jauh lebih mudah bagi Anda, dan
Kami menghargai bantuanmu

#### Membuat Custom Release dengan surf-build

1. Instal [Surf] (https://github.com/surf-build/surf), via npm:
  `Npm install -g surfing-build @ latest`

2. Buat ember S3 baru dan buat struktur direktori kosong berikut ini:

    `` `
    - atom-shell /
      - simbol /
      - dist /
    `` `

3. Tetapkan variabel lingkungan berikut ini:

  * `ELECTRON_GITHUB_TOKEN` - sebuah token yang dapat membuat rilis di GitHub
  * `ELECTRON_S3_ACCESS_KEY`,` ELECTRON_S3_BUCKET`, `ELECTRON_S3_SECRET_KEY`
