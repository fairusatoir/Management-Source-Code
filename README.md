# Management Source Code

## Requirement

Kebutuhan dokumentasi untuk pengembangan, perbaikan dan perilisan suatu perangkat lunak menggunakan [semantic versioning 2.0.0](https://semver.org/lang/id/spec/v2.0.0.html) untuk dokumentasi perilisan dan [git](https://git-scm.com/doc) untuk kolaborasi dan monitoring source code.

## Aturan Dokumentasi

1. Dokumentasi Perangkat lunak yang dibuat bisa dijelaskan dengan kode, atau ditulis di dokumentasi, ditulis dengan jelas dan akurat disetiap perilisan dari versi terbaru.
2. Versi HARUS ditulis dalam bentuk X.Y.Z, dengan X, Y, Z bilangan bulat positif, dan TIDAK BOLEH didahului angka 0 (contoh 01.02.03). X adalah versi MAJOR, Y adalah minor, dan Z adalah patch.
3. Setiap perubahan HARUS merilis versi dengan penomoran baru. Isi dari versi tersebut TIDAK BOLEH diubah.
4. Versi 1.0.0 adalah titik awal dari perangkat lunak yang dirilis publik
5. Versi patch Z (x.y.Z | x > 0) HARUS dinaikkan jika ada perbaikan bug tanpa menambah fitur.
6. Versi minor Y (x.Y.z | x > 0) HARUS dinaikkan jika ada fitur baru, atau ada fitur lama yang yang sudah usang. Versi ini BISA dinaikkan jika ada tambahan fungsionalitas substansial atau optimalisasi. Versi ini BISA diubah bersama dengan versi patch. Versi patch HARUS dikembalikan ke angka 0 jika versi minor dinaikkan.
7. Versi major X (X.y.z | X > 0) HARUS dinaikkan jika ada perubahan yang membuat versi baru tidak kompatibel dengan versi lama, seperti menghapus fitur lama, menambah fitur baru yang tidak bisa digunakan di versi lama, BISA diubah bersama dengan versi patch dan minor, jika versi major dinaikkan, maka versi minor dan patch harus dikembalikan ke angka 0.
8. Versi sebelum rilis ke publik BISA ditulis dengan menambahkan garis pemisah dangan dan diikuti angka yang selalu increment jika ada build perangkat lunak baru (contoh 2.0.2-4)

## Flow Git

