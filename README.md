# 🤖 Workflow AI Customer Service

Workflow n8n ini adalah *engine* AI yang memproses pesan masuk dan membalasnya menggunakan kepribadian (*persona*) yang bisa diatur secara dinamis.

## ⚙️ Cara Kerja Singkat

1. **📥 Menerima Pesan (Webhook)**
   Node ini aktif ketika menerima *request* API (Metode `POST` di *endpoint* `/simulasi-cs`). Data yang ditangkap meliputi isi pesan pelanggan, nama CS, dan sifat CS (*System Message*).
2. **🧠 Proses AI (AI Agent + Gemini)**
   Data pesan dan kepribadian tersebut dikirim ke model **Google Gemini Flash**. AI kemudian memproses dan menciptakan balasan teks sesuai dengan karakter yang diinstruksikan.
3. **📤 Mengirim Balasan (Respond to Webhook)**
   Teks balasan dari AI diubah menjadi format JSON yang valid (menggunakan `JSON.stringify`) agar aman dari *error* karakter khusus/emoji, lalu dikirimkan kembali ke aplikasi pemanggil (seperti WhatsApp Bot).

   
