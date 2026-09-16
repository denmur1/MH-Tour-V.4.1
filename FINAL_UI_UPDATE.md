# MH Tour — Final UI Refresh

Updated the actual Android application UI (not the reference images).

## Home screen
- MH TOUR logo from supplied app branding asset.
- `ID · Indonesia` header.
- `Dikelola Oleh: Ponpes Miftahul Huda Cigondewah`.
- Role prompt matching supplied reference layout.
- Jamaah and Guide buttons matching the supplied visual direction.
- Privacy entry.

## Guide screen
- Large microphone indicator.
- Microphone status changes when Guide starts/stops talking.
- Pulsing microphone indicator while live.
- Mute/unmute updates the microphone indicator.

## App icon
- MH Tour logo installed as the Android application icon.

## Online behavior
- Existing LiveKit/online connection code was preserved; this UI update does not remove the working online flow.

## Build note
- The source package is prepared for the existing GitHub Actions Gradle build. This environment does not include Gradle, so a local APK build was not executed here.


## Home screen refresh — 2026-09-16
- Tampilan awal diperbarui mengikuti referensi yang diberikan: logo besar, kartu judul MH Tour, pilihan Jamaah/Guide yang lebih jelas, dan tombol Donasi Seikhlasnya.
- Tombol Jamaah, Guide, Donasi, dan Kebijakan Privasi diberi state/click handling yang eksplisit setelah setiap rebuild layar.
- Link donasi tetap `https://saweria.co/denimurdhan`.
- Struktur navigasi, LiveKit, QR scanner, token flow, dan server tidak diubah.
- Tidak ada perubahan pada `server/server.js`, `server/docker-compose.yml`, atau konfigurasi LiveKit.

## Verification
- `server/server.js` passed Node syntax validation.
- APK belum dikompilasi di lingkungan ini karena project tidak menyertakan Gradle wrapper dan Gradle tidak tersedia di runtime.


## Donation page update — 2026-09-16
- Tombol **Donasi Seikhlasnya** di beranda sekarang membuka halaman **Donasi Seikhlasnya** di dalam aplikasi, bukan langsung membuka link eksternal.
- Halaman tersebut menampilkan QR donasi yang diberikan, link DANA berikut, serta tombol **Unduh QR Code**, **Buka Link Donasi**, dan **Kembali**:
  `https://link.dana.id/minta?full_url=https://qr.dana.id/v1/281012012023022707162488`
- QR dapat disimpan sebagai PNG. Android 10+ menyimpannya ke `Unduhan/MH Tour`; Android versi lama meminta lokasi penyimpanan melalui pemilih file.
- Tidak ada perubahan pada `server/server.js`, `server/docker-compose.yml`, `server/livekit.yaml`, token flow, atau konfigurasi LiveKit.
