# Reflection 1

**Clean Code Principles dan Secure Coding Practices yang Telah Diterapkan:**
- Separation of concerns: Kode dipisahkan ke dalam package yang berbeda (model, repository, service, controller) sesuai tanggung jawabnya masing-masing, sehingga lebih mudah dipahami dan di-maintain.
- Meaningful names: Nama yang digunakan deskriptif untuk class, method, dan variable. Contoh: ProductController, createProduct(), dan productList yang langsung menjelaskan fungsinya tanpa perlu comment tambahan.
- Focused functions: Setiap method yang dibuat fokus untuk melakukan satu tugas saja. Misalnya createProductPage() hanya menampilkan halaman form, sedangkan createProductPost() khusus untuk memproses data produk baru.
- Separation of logic: Business logic dipisahkan di service layer, tidak langsung di controller, sehingga lebih aman dan mudah untuk ditambahkan security check di masa depan.
- UUID generation: Menggunakan java.util.UUID untuk membuat ID produk secara acak dan unik, sehingga user tidak bisa menebak ID produk lain hanya dengan mencoba angka yang berurutan di URL.

**Improvement yang Bisa Dilakukan:**
- Error Handling: Saat ini error handling masih minimal. Perlu ditambahkan try-catch dan validasi untuk handle edge cases seperti product dengan ID yang tidak ada saat edit/delete.
- Input Sanitization: Melakukan pembersihan pada input teks untuk memastikan tidak ada tag HTML atau script berbahaya yang dimasukkan oleh user melalui form.


# Reflection 2

### (1)
- Menulis unit test membuat saya merasa lebih yakin dengan kode yang saya buat dan lebih tenang saat development. Unit test membantu saya memastikan setiap method sudah bekerja sesuai ekspektasi.
- Menurut saya, jumlah unit test yang perlu dibuat untuk suatu class tidak menentu, yang penting minimal setiap method public harus memiliki satu test untuk positive dan negative scenario. Untuk method yang kompleks, mungkin perlu lebih banyak test untuk cover berbagai case.
- Untuk memastikan unit test yang dibuat sudah cukup atau belum, bisa gunakan code coverage sebagai pengukur.
- Akan tetapi, 100% code coverage tidak menjamin kode bebas dari bug atau error, karena code coverage hanya mengukur baris kode yang dijalankan, bukan apakah logika tersebut sudah benar dalam menangani semua kemungkinan skenario.

### (2)
- Membuat functional test suite baru dengan setup procedures dan instance variables yang sama akan menurunkan code quality karena terjadi code duplication.
- Potensi masalah clean code:
    - Violation of DRY Principle: Setup WebDriver dan konfigurasi yang sama akan ditulis berulang di setiap test class
    - Redundant Code: Instance variables dan setup method akan ter-duplicate di semua functional test suite
    - Poor Maintainability: Jika ada perubahan konfigurasi, harus mengubah di banyak file
- Saran improvement adalah menerapkan prinsip DRY (Don't Repeat Yourself) dengan membuat sebuah base class yang menampung prosedur setup umum, sehingga test class lainnya cukup inherit dari base class tersebut.