// Ambil angka dari notifikasi BRI Merchant
var teks = [notification_main_text]; 
var angka = teks.replace(/[^0-9]/g, '');

// Bersihkan angka nol di belakang (format bank)
if (angka.endsWith("00") && angka.length > 4) {
    angka = angka.slice(0, -2);
}

var nominal = parseInt(angka);

// Daftar harga jualanmu: 4rb, 5rb, 7rb, 10rb, 12rb, 16rb
if (nominal == 4000 || nominal == 5000 || nominal == 7000 || nominal == 10000 || nominal == 12000 || nominal == 16000) {
    var suara = "Pesanan diterima, nominal " + nominal + " rupiah";
    
    // Perintah suara
    document.location = "macrodroid://speak?text=" + encodeURIComponent(suara);
} else {
    // Kalau ada nominal lain (iseng), tetap bunyi tapi beda suara
    var suaraLain = "Ada uang masuk " + nominal + " rupiah";
    document.location = "macrodroid://speak?text=" + encodeURIComponent(suaraLain);
}
