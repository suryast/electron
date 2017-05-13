# Tentang Electron

[Elektron] (https://electron.atom.io) adalah sebuah *open source library* yang dikembangkan oleh GitHub untuk membangun aplikasi desktop cross-platform dengan HTML, CSS, dan JavaScript. Elektron mencapai hal ini dengan menggabungkan [Chromium] (https://www.chromium.org/Home) dan [Node.js] (https://nodejs.org) ke dalam satu runtime dan aplikasi dapat dikemas untuk Mac, Windows, Dan Linux.

Elektron dimulai pada tahun 2013 sebagai kerangka di mana [Atom] (https://atom.io), editor teks GitHub yang dapat diretas, akan dibangun. Keduanya dibuat menjadi *open source* pada musim semi tahun 2014.

Sejak itu Electron menjadi alat populer yang digunakan oleh pengembang open source, startups, dan perusahaan mapan. [Lihat siapa yang membangun Elektron] (https://electron.atom.io/apps/).

Baca terus untuk mengetahui lebih lanjut tentang kontributor dan pelepasan Elektron atau mulai membangun dengan Elektron di [Panduan Mulai Cepat](quick-start.md).

## Tim Inti dan Kontributor

Elektron dikelola oleh tim di GitHub dan juga sekelompok [kontributor aktif](https://github.com/electron/electron/graphs/contributors) dari komunitas. Beberapa kontributornya adalah individu dan beberapa bekerja di perusahaan besar yang sedang mengembangkan aplikasi menggunakan Electron. Kami senang menambahkan kontributor yang sering ke proyek sebagai pengelola. Baca lebih lanjut tentang [berkontribusi pada Elektron](https://github.com/electron/electron/blob/master/CONTRIBUTING.md).

## Rilis

[Electron release](https://github.com/electron/electron/releases) sering diupdate. Kami merilis versi baru saat ada  perbaikan bug, API baru, atau saat memperbarui versi Chromium atau Node.js.

### Memperbarui Ketergantungan

Versi Electron dari Chromium biasanya diperbarui dalam satu atau dua minggu setelah versi kromium stabil baru diluncurkan, bergantung pada upaya yang dilakukan dalam peningkatan versi.

Saat versi baru Node.js dilepaskan, Electron biasanya menunggu sekitar satu bulan sebelum melakukan upgrade agar bisa menghasilkan versi yang lebih stabil.

Di Elektron, Node.js dan Chromium mengunnakan versi V8 tunggal-biasanya versi yang digunakan Chromium. Biasanya hal ini tidak bermasalah tp terkadang butuh menambal Node.js.

### Versi

Karena ketergantungan keras pada Node.js dan Chromium, Electron berada dalam posisi versi yang rumit dan [tidak mengikuti `semver`](http://semver.org). Oleh karena itu Anda harus selalu mereferensi versi tertentu dari Elektron. [Baca lebih lanjut tentang versi Elektron](https://electron.atom.io/docs/tutorial/electron-versioning/) atau lihat [versi yang sedang digunakan](https://electron.atom.io/#electron- Versi).

### LTS

Dukungan jangka panjang dari Elektronika versi lama saat ini tidak ada. Jika versi Elektron Anda saat ini bekerja untuk Anda, Anda dapat tetap menggunakannya selama yang Anda inginkan. Jika Anda ingin memanfaatkan fitur baru saat mereka masuk, Anda harus *gupgrade* ke versi yang lebih baru.

Pembaruan utama datang dengan versi `v1.0.0`. Jika Anda belum menggunakan versi ini, Anda harus [baca lebih lanjut tentang perubahan `v1.0.0`](https://electron.atom.io/blog/2016/05/11/electron-1-0).

## Filosofi Inti

Untuk menjaga supaya ukuran Elektron tetap kecil (ukuran file) dan berkelanjutan (penyebaran dependensi dan API) proyek ini membatasi lingkup proyek inti.

Misalnya, Elektron hanya menggunakan perpustakaan rendering dari Chromium dan tidak semua Chromium. Hal ini mempermudah untuk meng-upgrade Chromium namun juga berarti beberapa fitur browser yang ditemukan di Google Chrome tidak ada di Electron.

Fitur baru yang ditambahkan ke Elektron terutama harus berupa API asli. Jika sebuah fitur bisa menjadi modul Node.js sendiri, mungkin seharusnya begitu. Lihat [alat elektron yang dibangun oleh masyarakat](https://electron.atom.io/community).

## Sejarah

Berikut adalah tonggak sejarah dalam sejarah Elektron.

| : Kalender: | : Tada:
| --- | --- |
| ** April 2013 ** | [Atom Shell dimulai](https://github.com/electron/electron/commit/6ef8875b1e93787fa9759f602e7880f28e8e6b45). |
| ** Mei 2014 ** | [Atom Shell terbuka sumber](http://blog.atom.io/2014/05/06/atom-is-now-open-source.html). |
| ** April 2015 ** | [Atom Shell dinamai ulang Electron] (https://github.com/electron/electron/pull/1389). |
| ** Mei 2016 ** | [Elektron melepaskan `v1.0.0`] (https://electron.atom.io/blog/2016/05/11/electron-1-0). |
| ** Mei 2016 ** | [Aplikasi elektron yang kompatibel dengan Mac App Store] (https://electron.atom.io/docs/tutorial/mac-app-store-submission-guide). |
| ** Agustus 2016 ** | [Dukungan Windows Store untuk aplikasi Elektron] (https://electron.atom.io/docs/tutorial/windows-store-guide). |
