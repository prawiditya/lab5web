# lab5web
nama: prawiditya sahrul akbar
nim: 312410146




    <!-- Bagian Identitas -->
    <div class="box">
        <h2>Identitas Mahasiswa</h2>
        <form id="identitas">
            Nama: <input type="text" id="nama" placeholder="Masukkan nama">
            | NIM: <input type="text" id="nim" placeholder="Masukkan NIM">
            | Kelas: <input type="text" id="kelas" placeholder="Masukkan kelas">
            <br><br>
            <button type="button" onclick="tampilkanIdentitas()">Tampilkan</button>
        </form>
        <p id="hasilIdentitas"></p>

        <script>
            function tampilkanIdentitas() {
                let nama = document.getElementById("nama").value;
                let nim = document.getElementById("nim").value;
                let kelas = document.getElementById("kelas").value;

                if (nama === "" || nim === "" || kelas === "") {
                    alert("Harap isi semua data identitas!");
                    return;
                }

                document.getElementById("hasilIdentitas").innerHTML =
                    "Halo, " + nama + " (" + nim + ") dari kelas " + kelas + ".";
            }
        </script>
    </div>

    <!-- Bagian 1 -->
    <div class="box">
        <h2>1. Pengenalan JavaScript</h2>
        <script>
            document.write("Hello World dari JavaScript!<br>");
            console.log("Hello World dari Console!");
        </script>
    </div>

    <!-- Bagian 2 -->
    <div class="box">
        <h2>2. Alert, Prompt, dan Confirm</h2>
        <script>
            alert("Selamat datang di Praktikum JavaScript!");
            let namaPrompt = prompt("Masukkan nama Anda:");
            let konfirmasi = confirm("Apakah Anda ingin melanjutkan?");
            if(konfirmasi) {
                document.write("<b>Halo, " + namaPrompt + "!</b> Selamat belajar JavaScript!<br>");
            } else {
                document.write("Terima kasih sudah berkunjung.<br>");
            }
        </script>
    </div>

    <!-- Bagian 3 -->
    <div class="box">
        <h2>3. Operasi Dasar Aritmatika</h2>
        <script>
            let a = 10, b = 5;
            document.write("a = " + a + ", b = " + b + "<br>");
            document.write("Penjumlahan: " + (a + b) + "<br>");
            document.write("Pengurangan: " + (a - b) + "<br>");
            document.write("Perkalian: " + (a * b) + "<br>");
            document.write("Pembagian: " + (a / b) + "<br>");
        </script>
    </div>

    <!-- Bagian 4 -->
    <div class="box">
        <h2>4. Seleksi Kondisi (if..else)</h2>
        <script>
            let nilai = prompt("Masukkan nilai Anda:");
            if (nilai >= 80) {
                document.write("Nilai A - Sangat Baik<br>");
            } else if (nilai >= 60) {
                document.write("Nilai B - Baik<br>");
            } else {
                document.write("Nilai C - Cukup<br>");
            }
        </script>
    </div>

    <!-- Bagian 5 -->
    <div class="box">
        <h2>5. Seleksi Kondisi (Switch)</h2>
        <script>
            let hari = new Date().getDay();
            let namaHari;
            switch (hari) {
                case 0: namaHari = "Minggu"; break;
                case 1: namaHari = "Senin"; break;
                case 2: namaHari = "Selasa"; break;
                case 3: namaHari = "Rabu"; break;
                case 4: namaHari = "Kamis"; break;
                case 5: namaHari = "Jumat"; break;
                case 6: namaHari = "Sabtu"; break;
                default: namaHari = "Tidak diketahui";
            }
            document.write("Hari ini adalah: " + namaHari + "<br>");
        </script>
    </div>

    <!-- Bagian 6 -->
    <div class="box">
        <h2>6. Form Input dan Button</h2>
        <form name="formNilai" onsubmit="return validasiForm()">
            Nama: <input type="text" name="nama">
            Nilai: <input type="number" name="nilai"><br><br>
            <input type="button" value="Proses Nilai" onclick="prosesNilai()">
        </form>

        <script>
            function prosesNilai() {
                let nama = document.formNilai.nama.value;
                let nilai = document.formNilai.nilai.value;
                let hasil = "";

                if (nilai >= 80) hasil = "A";
                else if (nilai >= 60) hasil = "B";
                else hasil = "C";

                alert("Halo " + nama + ", nilai kamu: " + hasil);
            }

            function validasiForm() {
                let nama = document.formNilai.nama.value;
                let nilai = document.formNilai.nilai.value;
                if (nama == "" || nilai == "") {
                    alert("Semua field harus diisi!");
                    return false;
                }
            }
        </script>
    </div>

    <!-- Bagian 7 -->
    <div class="box">
        <h2>7. HTML DOM - Perhitungan Otomatis</h2>
        <form name="menuForm">
            <input type="checkbox" name="makanan" value="10000" onclick="hitungTotal()"> Nasi Goreng (10.000)<br>
            <input type="checkbox" name="makanan" value="8000" onclick="hitungTotal()"> Mie Ayam (8.000)<br>
            <input type="checkbox" name="makanan" value="5000" onclick="hitungTotal()"> Es Teh (5.000)<br><br>
            Total Bayar: <input type="text" id="total" readonly>
        </form>

        <script>
            function hitungTotal() {
                let total = 0;
                let items = document.getElementsByName("makanan");
                for (let i = 0; i < items.length; i++) {
                    if (items[i].checked) {
                        total += parseInt(items[i].value);
                    }
                }
                document.getElementById("total").value = total;
            }
        </script>
    </div>

    <hr>
    <footer>
        <p><b>Laporan Praktikum 5 - Pemrograman Web</b><br>
        Universitas Pelita Bangsa | © 2025</p>
    </footer>
</body>
</html>
