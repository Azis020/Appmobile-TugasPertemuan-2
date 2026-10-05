NIM         : 1124160173 /n
Nama        : Nur Azis Gimnastiar /n
Kelas       : TI 24 SE SH /n
Studi Kasus : Bank Sampah /n

```dart
// Nama nasabah yang sudah terdaftar
String getNamaNasabah(String kode) {
  Map<String, String> daftarNasabah = {
    'NSB01': 'Emon',
    'NSB02': 'Radit',
    'NSB03': 'Ahmad',
  };

  return daftarNasabah[kode] ?? 'Nasabah Tidak Ditemukan';
}

// Jika berat >= 1 
int hitungKategoriHarga(double berat) {
  return berat >= 1.0 ? (berat * 1000).toInt() : 0;
}

// Untuk memfilter jenis sampah
String keteranganJenisSampah(String jenis) {
  return switch (jenis) {
    'Plastik'   => 'Daur ulang jadi kerajinan',
    'Kertas'    => 'Dibuat bubur kertas',
    'Kardus'    => 'Dibuat boks baru',
    'Kaca'      => 'Dilebur ulang',
    'Organik'   => 'Diolah menjadi pupuk kompos',
    _           => 'Perlu pemilahan lanjut',
  };
}

void main() {
  print("Sistem Transaksi Bank Sampah");

  String kodeNasabah = "NSB01";
  String nasabahName = getNamaNasabah(kodeNasabah);

  String jenisSampah = "Kertas";
  double beratSampah = 4.5; // dalam kilogram
  bool isVerified = true;

  int totalHarga = hitungKategoriHarga(beratSampah);
  String keteranganDaurUlang = keteranganJenisSampah(jenisSampah);

  print('Kode: $kodeNasabah, Nasabah: $nasabahName, Jenis: $jenisSampah');
  print('Berat: $beratSampah kg, Harga: Rp $totalHarga, Terverifikasi: $isVerified',);
  print('Keterangan Olahan: $keteranganDaurUlang');

  String? catatanPetugas;
  catatanPetugas = null;
  String ketentuan = catatanPetugas ?? 'Tidak ada catatan tambahan dari petugas';
  print(ketentuan.toUpperCase());
}

