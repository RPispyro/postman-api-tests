# Postman API Tests

Zbiór testów API przygotowanych w [Postmanie](https://www.postman.com/). Repozytorium służy do przechowywania kolekcji, środowisk oraz testów automatycznych wspierających weryfikację endpointów API.

## Zawartość repozytorium

> Uzupełnij poniższą listę wraz z rozwojem projektu.

- kolekcje Postmana (`.json`),
- konfiguracje środowisk (`.json`),
- skrypty przed żądaniami i testy odpowiedzi,
- dokumentacja uruchamiania testów.

## Wymagania

- [Node.js](https://nodejs.org/) — wymagany do uruchamiania testów z użyciem Newman,
- [Postman](https://www.postman.com/downloads/) — do ręcznego przeglądania i uruchamiania kolekcji,
- dostęp do testowanego API,
- dane uwierzytelniające wymagane przez API.

## Uruchamianie w Postmanie

1. Sklonuj repozytorium:

   ```bash
   git clone https://github.com/RPispyro/postman-api-tests.git
   cd postman-api-tests
   ```

2. Otwórz Postmana.
3. Zaimportuj kolekcję oraz odpowiednie środowisko z repozytorium.
4. Uzupełnij zmienne środowiskowe, takie jak adres API i dane uwierzytelniające.
5. Uruchom kolekcję za pomocą **Collection Runner**.

## Uruchamianie z Newmanem

Zainstaluj Newman globalnie:

```bash
npm install -g newman
```

Następnie uruchom kolekcję:

```bash
newman run path/to/collection.json -e path/to/environment.json
```

Zastąp ścieżki nazwami plików znajdujących się w repozytorium.

## Konfiguracja

Nie zapisuj w repozytorium haseł, tokenów ani kluczy API. Wartości wrażliwe przechowuj lokalnie w środowisku Postmana lub przekazuj podczas uruchamiania Newmana, np. jako zmienne środowiskowe.

Przykład:

```bash
newman run path/to/collection.json \
  --env-var "baseUrl=$API_BASE_URL" \
  --env-var "token=$API_TOKEN"
```

## Dobre praktyki

- używaj osobnych środowisk dla różnych etapów, np. `local`, `test` i `staging`,
- stosuj jednoznaczne nazwy kolekcji, folderów i testów,
- asercje zapisuj w testach Postmana, a nie tylko w dokumentacji,
- nie commituj sekretów ani danych produkcyjnych,
- utrzymuj kolekcje kompatybilne z uruchamianiem bez interfejsu graficznego.

## Status

Projekt jest rozwijany. Szczegółowe informacje o dostępnych kolekcjach i sposobie uruchamiania zostaną uzupełnione wraz z dodawaniem testów.

## Licencja

Licencja nie została jeszcze określona.
