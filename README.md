# flowchartt

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Diagram Mermaid - Flowchart Gerak Peluru</title>
    <!-- Menghubungkan Mermaid.js dari file lokal -->
    <script src="scripts/mermaid.min.js"></script>
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            mermaid.initialize({ startOnLoad: true });
        });
    </script>
</head>
<body>
    <h1>Flowchart Perhitungan Jarak Mendatar Peluru</h1>
    <!-- Menyisipkan Diagram Mermaid -->
    <div class="mermaid">
        %%{init: {"themeVariables": { "flowchart.backgroundColor": "#ffffff" }}}%%
        graph TD;
            A[Mulai] --> B[Input jarak sasaran dalam meter]
            B --> C[Input sudut lontar dalam derajat]
            C --> D[Input kecepatan awal peluru]
            D --> E[Hitung jarak mendatar maksimal menggunakan fungsi jarak_mendatar]
            E --> F{Apakah jarak mendatar >= jarak sasaran?}
            F -- Yes --> G[Tambahkan ke tabel hasil dengan status 'Tercapai']
            F -- No --> H[Tambahkan ke tabel hasil dengan status 'Tidak Tercapai']
            G --> I{Masih ada jarak sasaran yang harus dicek?}
            H --> I
            I -- Yes --> E
            I -- No --> J[Tampilkan tabel hasil sasaran]
            J --> K{Apakah semua jarak tercapai?}
            K -- No --> L[Tampilkan pesan 'Sasaran tidak tercapai']
            K -- Yes --> M[Buat tabel pergerakan peluru menggunakan fungsi buat_tabel_pergerakan_peluru]
            L --> M
            M --> N[Tampilkan tabel pergerakan peluru]
            N --> O[Visualisasikan lintasan peluru dalam grafik]
            O --> P[Selesai]
    </div>
</body>
</html>
