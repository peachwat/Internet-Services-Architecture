# Internet Services Architecture

Projekt realizowany w ramach przedmiotu **Architektura Usług Internetowych**. Przedstawia proces budowy nowoczesnej aplikacji webowej w architekturze mikroserwisowej, przechodząc przez etapy od podstawowych mechanizmów Javy do pełnej konteneryzacji (Docker) i integracji z frontendem (Angular).

## Przegląd Projektu

System służy do zarządzania strukturą organizacyjną firmy (Firmy i Pracownicy). Projekt został podzielony na kilka etapów (Labów), z których każdy wprowadza nowe wzorce architektoniczne i technologie.

### Struktura i etapy rozwoju

* **Lab 1**: Podstawy Javy i serializacja. Implementacja klas domenowych `Company` i `Employee`.
* **Lab 2**: Wprowadzenie frameworka **Spring Boot**. Zastosowanie Spring Data JPA, implementacja warstw Repository i Service oraz automatyczna inicjalizacja danych.
* **Lab 3**: Budowa pełnego **REST API**. Wykorzystanie wzorca **DTO** (Data Transfer Object) oraz funkcji mapujących do separacji modelu bazy danych od modelu API.
* **Lab 4**: Transformacja do architektury **Mikroserwisów**. Rozdzielenie logiki na dwa niezależne serwisy (`company` i `employee`) oraz wprowadzenie **API Gateway**.
* **Lab 5**: Implementacja frontendu w **Angularze**. Tworzenie interaktywnych komponentów do wyświetlania, dodawania i edycji danych oraz integracja z bramą API (obsługa CORS).
* **Lab 6**: **Konteneryzacja**. Przygotowanie plików `Dockerfile` dla każdego modułu oraz konfiguracja `docker-compose.yml` w celu uruchomienia całego systemu jednym poleceniem.

## Stack Technologiczny

### Backend:
* **Java 17+**
* **Spring Boot**: Spring Web, Spring Data JPA
* **H2 Database**: Baza danych in-memory do celów deweloperskich
* **Maven**: Zarządzanie zależnościami
* **Spring Cloud Gateway**: Centralny punkt wejścia do mikroserwisów

### Frontend:
* **Angular**: Framework TypeScript do budowy interfejsu
* **Nginx**: Serwer WWW do serwowania aplikacji frontendowej w kontenerze

### Infrastruktura:
* **Docker & Docker Compose**: Konteneryzacja i orkiestracja usług

## Uruchomienie projektu (Docker)

Najszybszym sposobem na uruchomienie pełnego systemu (Backend + Frontend + Gateway) jest użycie Dockera. Przejdź do katalogu `Lab6` i wykonaj:

```bash
docker-compose up --build
