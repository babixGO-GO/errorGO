# errorGO - Android Project

## Projektübersicht
errorGO ist eine moderne Android-Anwendung entwickelt mit Kotlin und Android Gradle Build System.

## Projektstruktur
```
errorGO/
├── app/                          # Hauptanwendungsmodul
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/             # Kotlin/Java Quellcode
│   │   │   ├── res/              # Ressourcen (Layouts, Strings, etc.)
│   │   │   └── AndroidManifest.xml
│   │   ├── test/                 # Unit Tests
│   │   └── androidTest/          # Instrumentierte Tests
│   └── build.gradle(.kts)        # App-Modul Build-Konfiguration
├── build.gradle(.kts)            # Root Build-Konfiguration
├── settings.gradle(.kts)         # Projekt-Einstellungen
├── gradle/                       # Gradle Wrapper Dateien
└── gradlew                       # Gradle Wrapper Script (Unix)
```

## Main Activity Pfad
```
app/src/main/java/com/babixgo/errorgo/MainActivity.kt
```

## Build-Befehle

### Projekt Bauen
```bash
# Debug Build
./gradlew assembleDebug

# Release Build
./gradlew assembleRelease

# Alle Builds
./gradlew build
```

### Tests Ausführen
```bash
# Unit Tests
./gradlew test

# Instrumentierte Tests
./gradlew connectedAndroidTest

# Alle Tests
./gradlew test connectedAndroidTest

# Test mit Coverage Report
./gradlew testDebugUnitTest jacocoTestReport
```

### Code-Qualität
```bash
# Lint Prüfung
./gradlew lint

# Detekt (Kotlin Static Analysis)
./gradlew detekt

# Projekt bereinigen
./gradlew clean
```

### APK Installation
```bash
# Debug APK installieren
./gradlew installDebug

# Release APK installieren
./gradlew installRelease
```

## Code-Style Guidelines

### Kotlin Coding Conventions
- Folge den [offiziellen Kotlin Coding Conventions](https://kotlinlang.org/docs/coding-conventions.html)
- Verwende 4 Leerzeichen für Einrückungen
- Maximale Zeilenlänge: 120 Zeichen
- Verwende aussagekräftige Variablen- und Funktionsnamen

### Namenskonventionen
- **Klassen**: PascalCase (z.B. `MainActivity`, `UserViewModel`)
- **Funktionen**: camelCase (z.B. `onCreate()`, `fetchUserData()`)
- **Variablen**: camelCase (z.B. `userName`, `isLoggedIn`)
- **Konstanten**: UPPER_SNAKE_CASE (z.B. `MAX_RETRY_COUNT`)
- **Packages**: lowercase (z.B. `com.babixgo.errorgo`)

### Android Best Practices
- Verwende ViewModel für UI-Logik und Datenverwaltung
- Implementiere Dependency Injection (Hilt/Koin)
- Befolge MVVM oder MVI Architektur-Muster
- Nutze Kotlin Coroutines für asynchrone Operationen
- Verwende ViewBinding oder Compose für UI
- Implementiere proper Lifecycle-Handling

### Code-Dokumentation
```kotlin
/**
 * Beschreibt die Funktion oder Klasse.
 *
 * @param param1 Beschreibung des Parameters
 * @return Beschreibung des Rückgabewerts
 */
fun exampleFunction(param1: String): Boolean {
    // Implementation
}
```

## Testing-Anweisungen

### Unit Tests (src/test)
- Verwende JUnit 4 für Test-Framework
- Verwende MockK oder Mockito für Mocking
- Teste Geschäftslogik, ViewModels und Use Cases
- Ziel: Mindestens 80% Code Coverage

#### Test-Struktur
```kotlin
@Test
fun `test description in backticks`() {
    // Given (Arrange)
    val input = "test"
    
    // When (Act)
    val result = functionUnderTest(input)
    
    // Then (Assert)
    assertEquals(expected, result)
}
```

### Instrumentierte Tests (src/androidTest)
- Verwende Espresso für UI-Tests
- Teste User Flows und UI-Interaktionen
- Verwende Test-Datenbanken und Mock-APIs

### Test-Befehle
```bash
# Spezifischen Test ausführen
./gradlew test --tests "com.babixgo.errorgo.ExampleTest"

# Tests mit Logging
./gradlew test --info

# Tests mit Stack Traces bei Fehlern
./gradlew test --stacktrace
```

## Continuous Integration

Die CI/CD Pipeline läuft automatisch bei:
- Push zu `main` oder `develop` Branch
- Pull Requests zu diesen Branches

### CI Pipeline Schritte
1. Checkout Code
2. Setup JDK 17
3. Cache Gradle Dependencies
4. Run Lint Checks
5. Run Unit Tests
6. Build Debug APK
7. Upload Test Reports

## Entwicklungsumgebung

### Voraussetzungen
- Android Studio Hedgehog (2023.1.1) oder neuer
- JDK 17
- Android SDK 34 (API Level 34)
- Kotlin 1.9.0+

### Setup
1. Repository klonen
2. Android Studio öffnen und Projekt importieren
3. Gradle Sync ausführen
4. Emulator oder physisches Gerät verbinden
5. App ausführen

### Empfohlene Plugins
- Kotlin Plugin
- Android Studio Compose Plugin
- SonarLint
- GitToolBox

## Troubleshooting

### Häufige Probleme
**Gradle Build fehlgeschlagen:**
```bash
./gradlew clean build --refresh-dependencies
```

**Android SDK nicht gefunden:**
- Setze `ANDROID_HOME` Umgebungsvariable
- Überprüfe `local.properties` Datei

**Dependency Resolution Fehler:**
```bash
./gradlew clean
./gradlew build --refresh-dependencies
```

## Ressourcen
- [Android Developer Documentation](https://developer.android.com/)
- [Kotlin Documentation](https://kotlinlang.org/docs/home.html)
- [Material Design Guidelines](https://m3.material.io/)
- [Android Architecture Components](https://developer.android.com/topic/libraries/architecture)

## Kontakt & Support
Für Fragen oder Issues, bitte erstelle ein Issue im GitHub Repository.
