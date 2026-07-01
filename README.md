# trip_plans

Zaszyfrowane plany podróży dla aplikacji **Plan Podróży** (Android/Windows).

- Każdy plik `*.enc` to plan podróży zaszyfrowany **AES-256-GCM** (klucz z hasła, PBKDF2-HMAC-SHA256).
- `manifest.enc` to zaszyfrowana lista dostępnych planów (id → plik → tytuł).
- Nazwy plików są nieprzezroczyste (`plan-0001.enc`), a treść i tytuły są zaszyfrowane — bez hasła nie da się odczytać, co jest w repo, mimo że jest publiczne.

Aplikacja pobiera `manifest.enc`, odszyfrowuje go hasłem wpisanym przez użytkownika, pokazuje listę planów i pobiera wybrany plik. Odszyfrowanie odbywa się wyłącznie na urządzeniu.

Plany dodaje się narzędziem `tool/encrypt_plan.dart` z repozytorium aplikacji (te samo hasło co w apce). **Nigdy nie commituj tu plików jawnych (`*.json`).**
