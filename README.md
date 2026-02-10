# Reflection 1

Clean Code Principles dan Secure Coding Practices yang Telah Diterapkan:
- Separation of concerns: Kode dipisahkan ke dalam package yang berbeda (model, repository, service, controller) sesuai tanggung jawabnya masing-masing, sehingga lebih mudah dipahami dan di-maintain.
- Meaningful names: Nama yang digunakan deskriptif untuk class, method, dan variable. Contoh: ProductController, createProduct(), dan productList yang langsung menjelaskan fungsinya tanpa perlu comment tambahan.
- Focused functions: Setiap method yang dibuat fokus untuk melakukan satu tugas saja. Misalnya createProductPage() hanya menampilkan halaman form, sedangkan createProductPost() khusus untuk memproses data produk baru.
- Separation of logic: Business logic dipisahkan di service layer, tidak langsung di controller, sehingga lebih aman dan mudah untuk ditambahkan security check di masa depan.

Improvement yang bisa dilakukan:
- Input Validation: Perlu ditambahkan validasi yang lebih ketat untuk mencegah injection atau input berbahaya, terutama untuk field name dan quantity.
- Error Handling: Saat ini error handling masih minimal. Perlu ditambahkan try-catch dan validasi untuk handle edge cases seperti product dengan ID yang tidak ada saat edit/delete.
