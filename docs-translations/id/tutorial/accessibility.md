# Aksesibilitas

Membuat aplikasi yang mudah diakses sangat penting, dan kami dengan senang hati memperkenalkan fungsi baru ke [Devtron](https://electron.atom.io/devtron) dan [Spectron](https://electron.atom.io/spectron) yang memberi para *developer* kesempatan untuk membuat aplikasi mereka lebih baik untuk semua orang.

---

Kekhawatiran aksesibilitas dalam aplikasi Elektron serupa dengan situs web karena keduanya HTML. Dengan aplikasi Elektron, Anda tidak dapat menggunakan sumber online untuk audit aksesibilitas karena aplikasi Anda tidak memiliki URL untuk menunjuk auditor.

Fitur baru ini membawa alat audit tersebut ke aplikasi Elektron Anda. Anda dapat memilih untuk menambahkan audit ke tes Anda dengan Spectron atau menggunakannya di dalam DevTools dengan Devtron. Baca terus untuk ringkasan alat atau checkout [dokumentasi aksesibilitas kami](https://electron.atom.io/docs/tutorial/accessibility) untuk informasi lebih lanjut.

### Spektron

Dalam kerangka pengujian Spectron, Anda sekarang dapat mengaudit setiap jendela dan tag `<webview>` di aplikasi Anda. Sebagai contoh:

```javascript
app.client.auditAccessibility().then(function (audit) {
  if (audit.failed) {
    console.error(audit.message)
  }
})
```

Anda dapat membaca lebih lanjut tentang fitur ini di dokumentasi [Spectron](https://github.com/electron/spectron#accessibility-testing).

### Devtron

Di Devtron, ada tab aksesibilitas baru yang memungkinkan Anda mengaudit halaman di aplikasi Anda, menyortir dan memfilter hasilnya.

! [Tampilan screenshot Dectron](https://cloud.githubusercontent.com/assets/1305617/17156618/9f9bcd72-533f-11e6-880d-389115f40a2a.png)

Kedua alat ini menggunakan *library* [Accessibility Developer Tools](https://github.com/GoogleChrome/accessibility-developer-tools) yang dibuat oleh Google untuk Chrome. Anda dapat mempelajari lebih lanjut tentang aturan audit aksesibilitas yang digunakan perpustakaan ini pada [wiki repositori](https://github.com/GoogleChrome/accessibility-developer-tools/wiki/Audit-Rules).

Jika Anda mengetahui alat aksesibilitas terbaik lainnya untuk Elektron, tambahkan ke [dokumentasi aksesibilitas](https://electron.atom.io/docs/tutorial/accessibility) dengan *pull request*
