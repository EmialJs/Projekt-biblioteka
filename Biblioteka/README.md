# System Zarządzania Biblioteką

System Zarządzania Biblioteką oparty na technologii webowej, stworzony z wykorzystaniem Angular 18 jako front-endu oraz .NET Core 8 jako zaplecza API. System umożliwia zarządzanie książkami, użytkownikami biblioteki i personelem, oferując funkcje dostępne w zależności od przypisanych ról.

## Funkcjonalności

- **Autoryzacja użytkowników**: Dostęp oparty na rolach dla administratorów, bibliotekarzy i członków.
- **Zarządzanie książkami**: Dodawanie, edytowanie i usuwanie książek z inwentarza.
- **Wypożyczanie i zwroty**: Obsługa wypożyczeń książek, zwrotów oraz monitorowanie terminów zwrotów.
- **Kontrola inwentarza**: Śledzenie dostępności książek i zarządzanie kategoriami książek.
- **Zarządzanie użytkownikami**: Zarządzanie członkami biblioteki i personelem.

## Stos technologiczny

- **Front-end**: Angular 18
- **Back-end**: .NET Core 8
- **Baza danych**: SQL Server (lub inna relacyjna baza danych)

## Pierwsze kroki

### Wymagania wstępne

Upewnij się, że masz zainstalowane następujące narzędzia:

- [Node.js](https://nodejs.org/)
- [Angular CLI](https://angular.io/cli)
- [.NET SDK](https://dotnet.microsoft.com/download)
- [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) (lub inną kompatybilną bazę danych)

### Instalacja

2. Przejdź do katalogu projektu:

   ```bash
   cd library-management-system
   ```

3. Zainstaluj zależności Angulara:

   ```bash
   cd UI
   npm install
   ```

4. Skonfiguruj zaplecze:

   ```bash
   cd ../API
   dotnet restore
   ```

5. Zaktualizuj ciąg połączenia do bazy danych w pliku `appsettings.json`.

6. Uruchom API zaplecza:

   ```bash
   dotnet run
   ```

7. Uruchom aplikację Angular:

   ```bash
   cd ../UI
   ng serve
   ```

### Użytkowanie

1. Otwórz aplikację w przeglądarce pod adresem `http://localhost:4200/`.
2. Zaloguj się jako administrator, bibliotekarz lub członek, aby przetestować dostępne funkcje.

### Punkty końcowe API

**Biblioteka**

- **Rejestracja użytkownika**  
  - `POST /api/Library/Register`

- **Logowanie użytkownika**  
  - `GET /api/Library/Login`

- **Pobierz książki**  
  - `GET /api/Library/GetBooks`

- **Zamów książkę**  
  - `POST /api/Library/OrderBook`

- **Zobacz zamówienia użytkownika**  
  - `GET /api/Library/GetOrdersOFUser`

- **Dodaj kategorię książek**  
  - `POST /api/Library/AddCategory`

- **Pobierz kategorie**  
  - `GET /api/Library/GetCategories`

- **Dodaj książkę do biblioteki**  
  - `POST /api/Library/AddBook`

- **Usuń książkę z biblioteki**  
  - `DELETE /api/Library/DeleteBook`

- **Zwrot książki**  
  - `GET /api/Library/ReturnBook`

- **Pobierz użytkowników**  
  - `GET /api/Library/GetUsers`

- **Zatwierdź prośbę o wypożyczenie**  
  - `GET /api/Library/ApproveRequest`

- **Pobierz wszystkie zamówienia**  
  - `GET /api/Library/GetOrders`

- **Wyślij powiadomienia e-mail o zaległych zwrotach**  
  - `GET /api/Library/SendEmailForPendingReturns`

- **Zablokuj użytkowników z zaległymi karami**  
  - `GET /api/Library/BlockFineOverdueUsers`

- **Odblokuj użytkownika**  
  - `GET /api/Library/Unblock`