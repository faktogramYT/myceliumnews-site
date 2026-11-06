# Publikacja strony MyceliumNEWS na GitHub Pages (darmowo)

Nic nie zostało opublikowane. Strona jest gotowa lokalnie w `STRONA_WWW\podglad` (dane przykładowe, NIE publikować). Publikacja wymaga Twoich decyzji i Twojego konta GitHub.

## 1. Zatwierdź treść
Otwórz w przeglądarce pliki z `STRONA_WWW\podglad\`: `index.html`, `app.html`, `privacy.html`, `terms.html`, `contact.html`. Teksty prawne opisują faktyczne działanie aplikacji, ale **to nie jest porada prawna**: przeczytaj je i popraw, co się nie zgadza (pliki źródłowe: `STRONA_WWW\szablony\`).

## 2. Uzupełnij dane publiczne
W `STRONA_WWW\site.config.json` wpisz: `operator` (nazwa, pod którą występujesz: osoba lub nazwa marki), `contact_email` (adres PUBLICZNY, np. dedykowany), `governing_law_country` (kraj, np. Poland). Ustaw `"approved_by_owner": true`. Zbuduj stronę:
`NARZEDZIA\venv\Scripts\python.exe KOD\build_site.py publish` → powstaje `STRONA_WWW\public\` (skrypt odmówi, jeśli czegoś brakuje).

## 3. GitHub (darmowe konto, bez karty)
Wariant A (bez żadnych tokenów, najprostszy): na github.com utwórz **publiczne** repozytorium (np. `myceliumnews-site`) → **Add file → Upload files** → przeciągnij **zawartość** folderu `public` (razem z `.nojekyll`) → Commit. Potem **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: main, folder: / (root) → Save**.
Wariant B (git z mojej strony): utwórz puste repozytorium, podaj mi jego adres; `git push` otworzy okno logowania GitHub na Twoim komputerze (logujesz się Ty, ja nie widzę hasła ani tokenu). Nie wklejaj tokenów do czatu.

## 4. Adresy (po ~1-2 minutach)
Dla repozytorium `UŻYTKOWNIK/REPO` strona działa pod `https://UŻYTKOWNIK.github.io/REPO/`. Trzy adresy do pól TikTok Developers:
- Web/Desktop URL: `https://UŻYTKOWNIK.github.io/REPO/`
- Privacy Policy URL: `https://UŻYTKOWNIK.github.io/REPO/privacy.html`
- Terms of Service URL: `https://UŻYTKOWNIK.github.io/REPO/terms.html`
Po publikacji sprawdzę, że każdy zwraca HTTP 200 i właściwą treść, i dopiero wtedy wpiszę Ci konkretne adresy.

## 5. Weryfikacja URL w TikTok (instrukcja)
W portalu: aplikacja → **URL properties** (tryb Production) → **Verify properties** → wybierz **URL prefix** i wpisz `https://UŻYTKOWNIK.github.io/REPO/` (jeden prefiks pokrywa wszystkie trzy adresy; musi być https, nie może przekierowywać) → pobierz plik sygnatury (nazwa w stylu `tiktok….txt`) → wgraj go do **głównego folderu repozytorium** (Add file → Upload files) → odczekaj do publikacji → kliknij Verify. Plik sygnatury musi być dostępny pod `https://UŻYTKOWNIK.github.io/REPO/<nazwa pliku>`.
Uwaga: w Sandboxie weryfikacja URL jest wymagana tylko dla Content Posting API, którego nie używamy.

## 6. Ikona aplikacji
`STRONA_WWW\zasoby\app-icon-1024.png` (1024x1024, PNG, 38 KB): do pola App icon.
