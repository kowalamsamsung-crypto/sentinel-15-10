# SENTINEL - APK (Android)

Aplikacja to ta sama strona co na komputerze, opakowana w aplikację Android (Capacitor).
Telefon łączy się z serwerem SENTINEL uruchomionym na komputerze w tej samej sieci Wi-Fi.

## Zawartość repozytorium
- `www/` - strona aplikacji i biblioteki offline (`lib/`)
- `native/java/pl/sentinel/app/` - natywny skaner kodów (CameraX + ML Kit) i most do strony
- `scripts/patch-android.js` - przygotowanie projektu Android (uprawnienia, zależności, podpis, wersja)
- `.github/workflows/build-apk.yml` - automatyczne budowanie APK na GitHub
- `capacitor.config.json`, `package.json` - konfiguracja

Folder `android/` nie jest w repozytorium. Powstaje sam podczas budowania.

## Instalacja i aktualizacja
Build jest debugowy i podpisany automatycznym kluczem debug (nie wymaga sekretów ani klucza `keystore`).
Taki APK instaluje się normalnie na telefonie, ale każdy build na GitHub Actions może mieć inny klucz debug,
dlatego przed instalacją nowej wersji **odinstaluj poprzednią aplikację SENTINEL**.

## Budowanie APK
1. Wgraj zawartość repozytorium (zastąp pliki).
2. Wejdź w **Actions -> Build APK -> Run workflow** (lub zrób zwykły commit).
3. Po zakończeniu pobierz artefakt **SENTINEL-apk** i zainstaluj `app-debug.apk` na telefonie (wcześniej odinstaluj starą wersję).

## Ważne
- Komputer z serwerem musi być włączony, a telefon w tej samej sieci Wi-Fi.
- Zapora Windows musi zezwalać na połączenia do portu 3000.
- Zmiana adresu serwera: przycisk statusu w aplikacji (lewy dolny róg) -> Zapisz adres.
- Aktualizacja strony: podmień `www/index.html`, wgraj na GitHub i zbuduj ponownie.
