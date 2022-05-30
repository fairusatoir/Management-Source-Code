# Management Source Code

## Requirement

Kebutuhan dokumentasi untuk pengembangan, perbaikan dan perilisan suatu perangkat lunak menggunakan [semantic versioning 2.0.0](https://semver.org/lang/id/spec/v2.0.0.html) untuk dokumentasi perilisan dan [git](https://git-scm.com/doc) untuk kolaborasi dan monitoring source code.

## Aturan Versioning perilisan

![SemVer 2](https://miro.medium.com/max/700/1*X0AvlnrTy5Vt2-cGiJCSvg.png)

1. Dokumentasi Perangkat lunak yang dibuat **BISA** dijelaskan dengan kode, atau ditulis di dokumentasi, ditulis dengan jelas dan akurat disetiap perilisan dari versi terbaru.
2. Versi **HARUS** ditulis dalam bentuk **X.Y.Z**, dengan X, Y, Z bilangan bulat positif, dan **TIDAK BOLEH** didahului angka 0 (contoh 01.02.03). X adalah versi MAJOR, Y adalah minor, dan Z adalah patch.
3. Setiap perubahan **HARUS** merilis versi dengan penomoran baru. Isi dari versi tersebut **TIDAK BOLEH** diubah.
4. Versi `1.0.0` adalah titik awal dari perangkat lunak yang dirilis publik
5. Versi patch **Z** (x.y.Z | x > 0) **HARUS** dinaikkan jika ada perbaikan bug tanpa menambah fitur.
6. Versi minor **Y** (x.Y.z | x > 0) **HARUS** dinaikkan jika ada fitur baru, atau ada fitur lama yang yang sudah usang. Versi ini **BISA** dinaikkan jika ada tambahan fungsionalitas substansial atau optimalisasi. Versi ini **BISA** diubah bersama dengan versi patch. Versi patch **HARUS** dikembalikan ke angka 0 jika versi minor dinaikkan.
7. Versi major **X** (X.y.z | X > 0) **HARUS** dinaikkan jika ada perubahan yang membuat versi baru tidak kompatibel dengan versi lama, seperti menghapus fitur lama, menambah fitur baru yang tidak **BISA** digunakan di versi lama, **BISA** diubah bersama dengan versi patch dan minor, jika versi major dinaikkan, maka versi minor dan patch **HARUS** dikembalikan ke angka 0.
8. Versi sebelum rilis ke publik **BISA** ditulis dengan menambahkan garis pemisah dangan dan diikuti angka yang selalu increment jika ada build perangkat lunak baru (contoh 2.0.2-4)

## Git-Flow

Suatu konsep alur bercabangan dan penggabungan *source code* dalam meggunakan *versioning control Git* untuk mengembangkan, memperbaiki dan merilis suatu aplikasi.

### Kenapa HARUS meggunakan git-Flow

* Setiap anggota tim dapat mengerjakan pengembangan atau perbaikan di *branch* masing-masing tanpa khawatir terjadi *conflict*
* Mudah Tracking perubahan yang dilakukan setiap anggota tim

![branching git](https://wac-cdn.atlassian.com/dam/jcr:34c86360-8dea-4be4-92f7-6597d4d5bfae/02%20Feature%20branches.svg?cdnVersion=365)

### Branching
Dalam  pengembangan, perbaikan dan perilisan perangkat lunak membutuhkan beberapa *branch* :

1. `master` : *branch* berisikan *source code* yang menjadi acuan **pengembangan** (**cabang utama**) dan menyimpan **riwayat rilis** resmi. 
2. `dev` : *branch* yang berisi riwayat lengkap dalam pengembangan dan perbaikan, cabang ini hasil *cloning* cabang `master` dan jika ada perubahan untuk perilisan baru, harus di **merge** dengan cabang `master`.
3. `feature/` : nama *branch* diawalai `feature/` dan diikuti nama *branch* yang mendiskripsikan nama fitur baru tersebut, contoh `feature/fitur-lupa-password`. Berisi *source code* hasil clone `dev` untuk  ditambahkan suatu fitur baru. jika suatu fitur selesai dikembangkan, harus di **merge** ke cabang `dev`.
4. `bug-fix/` : nama *branch* dengan penamaan yang dawalai `bug-fix/` diikuti nama *branch* yang mendiskripsikan *bug* yang diperbaiki, contoh `bug-fix/data-nomor-ktp-tidak-terkirim`. Berisi *source code* hasil clone dari `master`, berisi perbaikan bug yang ditemukan di versi rilis. Jika suatu bug selesai diperbaiki, harus di **merge** ke cabang `master` dan `dev`.

### Commit
- `feat` : untuk menambah algoritma atau tambahan lainnya
- `fix` : untuk mengubah algoritma yang sudah ada atau memperbaiki
- `docs` : untuk mengubah atau membuat dokumentasi
- `add` : untuk mengubah algoritma atau tambahan lainnya (opsional)
