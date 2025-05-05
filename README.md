# System automatycznego podlewania ogrodu
## Opis projektu

System automatycznego podlewania ogrodu to system czasu rzeczywistego zaprojektowany w języku AADL. Celem modelu jest monitorowanie warunków glebowych i atmosferycznych oraz automatyczne zarządzanie nawadnianiem ogrodu. System inteligentnie dostosowuje harmonogram podlewania w oparciu o wilgotność gleby, prognozy pogody oraz predefiniowane ustawienia użytkownika.

## Komponenty systemu

### Pakiet
- `GardenIrrigationSystem` – główny pakiet zawierający wszystkie komponenty systemu automatycznego podlewania ogrodu.

### Data
- `SoilMoistureData` – dane z czujników wilgotności gleby.
- `TemperatureData` – dane z czujnika temperatury otoczenia.
- `RainPredictionData` – dane dotyczące prognozy opadów.
- `WaterLevelData` – dane o poziomie wody w zbiorniku.
- `CommandData` – komendy przesyłane z aplikacji użytkownika.
- `IrrigationScheduleData` – dane harmonogramu podlewania.
- `ZoneConfigData` – konfiguracja stref podlewania.

### Threads (Wątki)
- `MoistureSensorMonitor` – wątek monitorujący odczyty czujników wilgotności gleby.
- `WeatherDataCollector` – wątek zbierający dane pogodowe.
- `IrrigationController` – wątek sterujący zaworami podlewającymi.
- `TankMonitor` – wątek monitorujący poziom wody w zbiorniku.
- `CameraController` – wątek zarządzający kamerą i wykonujący zdjęcia stanu ogrodu.
- `NotificationManager` – wątek wysyłający powiadomienia do użytkownika.

### Process (Procesy)
- `SensorProcess` – proces zawierający wątki zbierające dane z czujników.
- `ControlProcess` – proces zawierający logikę sterowania systemem.
- `NotificationProcess` – proces obsługujący powiadomienia i alerty.

### Devices (Urządzenia)
- `MoistureSensor` – czujniki wilgotności gleby.
- `TemperatureSensor` – czujnik temperatury otoczenia.
- `SolenoidValve` – elektrozawory sterujące dopływem wody do poszczególnych stref.
- `WaterPump` – pompa wodna.
- `WaterLevelSensor` – czujnik poziomu wody w zbiorniku.
- `Camera` – kamera monitorująca stan ogrodu.
- `WiFiModule` – moduł komunikacji bezprzewodowej.

### Bus (Magistrale)
- `I2CBus` – magistrala komunikacyjna dla czujników.
- `WiFiBus` – magistrala do komunikacji bezprzewodowej.

### Processor (Procesory)
- `MainController` – główny procesor sterujący pracą całego systemu.

### Memory (Pamięć)
- `SystemMemory` – pamięć operacyjna dla systemu.

### System
- `GardenIrrigationSystem` – kompletny system integrujący wszystkie komponenty.

## Funkcjonalności systemu

1. **Monitorowanie warunków** – system regularnie zbiera dane z czujników wilgotności gleby i temperatury.
2. **Inteligentne podlewanie** – automatyczne dostosowanie częstotliwości i długości podlewania w oparciu o odczyty wilgotności.
3. **Oszczędzanie wody** – integracja z prognozami pogody pozwala na wstrzymanie podlewania przed spodziewanymi opadami.
4. **Podział na strefy** – możliwość konfiguracji różnych harmonogramów podlewania dla różnych stref ogrodu.
5. **Monitoring zbiornika** – ciągłe monitorowanie poziomu wody w zbiorniku z alertami przy niskim stanie.
6. **Dokumentacja wizualna** – system wykonuje zdjęcia ogrodu, umożliwiając śledzenie jego stanu.
7. **Powiadomienia** – system wysyła alerty o niskim poziomie wody, problemach z czujnikami lub zaworami.
8. **Kontrola zdalna** – możliwość zdalnego sterowania systemem poprzez aplikację.

## Przepływy danych

System implementuje następujące przepływy danych:
- Monitoring wilgotności -> Analiza -> Decyzja o podlewaniu -> Sterowanie zaworami
- Prognoza pogody -> Adjustacja harmonogramu podlewania
- Stan zbiornika -> Powiadomienia dla użytkownika
- Harmonogram -> Wykonanie podlewania -> Dokumentacja fotograficzna
