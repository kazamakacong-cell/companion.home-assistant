// Kode otomatis untuk MacroDroid/Tasker
var teks = [notification_text]; // Ini mengambil teks dari BRI Merchant
var nominal = teks.replace(/[^0-9]/g, ''); // Ambil angkanya saja

if (nominal >= 1000 && nominal <= 1000000) {
    var s = new SpeechSynthesisUtterance("Pesanan diterima, nominal " + nominal + " rupiah");
    s.lang = 'id-ID';
    window.speechSynthesis.speak(s);
}
