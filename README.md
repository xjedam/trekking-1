# Trekking

Projekt stworzony na laboratoria z Architektury serwisów internetowych,

## Funkcjonalność

Serwis pozwala użytkownikom na proste tworzenie i edycję własnych ścieżek, a także wyszukiwanie ścieżek terenowych utworzonych przez innych użytkowników.

Do każdej ścieżki wyświetlane są dodatkowe informacje: jej całkowita długość, ilość punktów kontrolnych oraz wykres zmian wysokości terenu na trasie.

## Wykorzystane technologie

### JavaScript:

* Google Maps API w JavaScript (http://code.google.com/apis/maps/documentation/javascript/)
  * Markers do zaznaczania pozycji punktów kontrolnych:
    http://code.google.com/apis/maps/documentation/javascript/overlays.html#Markers
  * Polylines do rysowania ścieżek łączących punkty:  
    http://code.google.com/apis/maps/documentation/javascript/overlays.html#Polylines
  * Elevation Service odpowiedzialne za pobieranie wysokości terenu na podanej ścieżce
    http://code.google.com/apis/maps/documentation/javascript/services.html#Elevation
* Google Charts API - używane do wyświetlania danych zwróconych przez `getElevationAlongPath()` z Elevation Service. Dzięki kompatybilności różnych API nie wymagają żadnej obróbki przed wyświetleniem ich na wykresie.
  * przykład wykresu i jego użycie: http://code.google.com/apis/chart/interactive/docs/gallery/areachart.html
  * mnóstwo innych typów wykresów, które można wyświetlać => http://code.google.com/apis/chart/interactive/docs/examples.html#gauge_example

### Baza danych

[MongoDB](http://www.mongodb.org/), ponieważ wspiera przechowywanie współrzędnych i wyszukiwanie rekordów na podstawie ich pozycji.

### Kluczowe gemy

* [devise](https://github.com/plataformatec/devise) - dodaje możliwość logowania, rejestracji itp.
* [cancan](https://github.com/ryanb/cancan) - ustalanie uprawnień użytkowników
* [simple_form](https://github.com/plataformatec/simple_form) - łatwe tworzenie formularzy
* [geocoder](http://www.rubygeocoder.com/) - dodaje funkcje zamiany adresu na współrzedne (konkretnie metoda `coordinates` z http://rubydoc.info/github/alexreisner/geocoder/master/Geocoder:coordinates). Używam do szukania ścieżek w pobliżu podanego miejsca.
* [mongoid](http://mongoid.org) - adapter MongoDB dla Ruby. Wzorowany na ActiveRecord, przez co użycie jest bardzo podobne.                                        
* [haml](http://haml-lang.com/tutorial.html) - bardzo atrakcyjna warstwa zapisu HTMLa. Skraca czas potrzebny na napisanie kodu i zdecydowanie poprawia czytelność.                          
                                          
                                    
                                           