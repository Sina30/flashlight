# FiveM Blinker Script / FiveM Fahrtrichtungsanzeiger

*[English](#english) | [Deutsch](#deutsch)*

---

## English

A complete blinker system for FiveM with realistic sounds and player synchronization.

### Features

- **Arrow Key Controls**: Simple operation using arrow keys
- **Flexible Permission System**: Configurable - only driver or all passengers can operate blinkers
- **Ground Vehicles Only**: Works only with cars, motorcycles, trucks, etc.
- **Realistic Sounds**: 4 different WAV audio files for authentic feedback
  - `TURN_LEVER_INTRO.wav` - Turn blinker on
  - `TURN_LEVER_OUTRO.wav` - Turn blinker off
  - `INDICATOR_SOUND.wav` - Continuous tick sound
  - `HAZARD_BUTTON.wav` - Hazard lights sound
- **Sound Sharing**: All passengers in the same vehicle hear the blinker sounds
- **Synchronized**: All players see other vehicles' blinkers in real-time
- **Smart Turn-Off**: Two modes - instant or delayed automatic turn-off after curves
- **Configurable**: Volume, sound activation, auto-turn-off and permissions adjustable
- **Hazard Lights**: Includes hazard lights function
- **Debug System**: Detailed console output for troubleshooting
- **Multilingual**: German and English language support

### Controls

| Key | Function |
|-----|----------|
| ← (Left) | Left blinker on/off |
| → (Right) | Right blinker on/off |
| ↓ (Down) | Hazard lights on/off |

### Configuration

All settings can be adjusted in `config.lua`:

#### Sound Settings
```lua
Config.Sound = {
    enabled = true,              -- Sound enabled (true/false)
    volume = 0.5,               -- Global volume (0.0 - 1.0)
    shareWithPassengers = true, -- Share sounds with other passengers (true/false)
    
    -- Individual sound files
    sounds = {
        indicator = "INDICATOR_SOUND.wav",      -- Blinker tick sound
        turnOn = "TURN_LEVER_INTRO.wav",       -- Blinker on sound
        turnOff = "TURN_LEVER_OUTRO.wav",      -- Blinker off sound
        hazard = "HAZARD_BUTTON.wav"           -- Hazard lights sound
    }
}
```

#### Blinker Settings
```lua
Config.Blinker = {
    customTiming = true,        -- Use custom blink timing (true) or GTA standard (false)
    interval = 500,             -- Blink interval in milliseconds (only if customTiming = true)
    autoTurnOff = {
        enabled = true,         -- Automatic turn-off after curves
        steeringThreshold = 15, -- Steering angle threshold
        instantTurnOff = true   -- Turn off immediately when angle reached (true) or wait until straight (false)
    }
}
```

#### Vehicle Settings
```lua
Config.Vehicle = {
    -- Allowed vehicle classes (ground vehicles)
    allowedClasses = {
        0,  -- Compacts
        1,  -- Sedans
        2,  -- SUVs
        3,  -- Coupes
        4,  -- Muscle
        5,  -- Sports Classics
        6,  -- Sports
        7,  -- Super
        8,  -- Motorcycles
        9,  -- Off-road
        10, -- Industrial
        11, -- Utility
        12, -- Vans
        17, -- Service
        18, -- Emergency
        19, -- Military
        20  -- Commercial
    },
    
    -- Blacklisted vehicle models (hash names)
    blacklistedModels = {
        -- Example: GetHashKey("hydra")
    },
    
    -- Who can operate the blinkers?
    driverOnly = true           -- true = only driver, false = all passengers
}
```

#### Language Settings
```lua
Config.Language = {
    current = "en",             -- Current language: "de" = German, "en" = English
    -- Language texts are automatically loaded
}
```

### Installation

1. Download the resource
2. Place in your FiveM server's `resources` folder
3. Add `ensure flashlight` to your `server.cfg`
4. Place the 4 WAV sound files in the `html/` folder
5. Restart your server

### Sound Files

The script requires 4 WAV audio files in the `html/` folder:
- `INDICATOR_SOUND.wav` - Tick sound during blinking
- `TURN_LEVER_INTRO.wav` - Sound when turning blinker on
- `TURN_LEVER_OUTRO.wav` - Sound when turning blinker off
- `HAZARD_BUTTON.wav` - Sound for hazard lights

### Commands

- `/testsound <soundname>` - Test individual sounds (for development)

### Troubleshooting

- **No sound**: Check if WAV files are in the `html/` folder
- **Blinkers don't work**: Check if you're in a ground vehicle and have permission
- **No synchronization**: Check if StateBags are enabled in `Config.Advanced.enableStateBags`

---

## Deutsch

Ein vollständiges Blinker-System für FiveM mit realistischen Sounds und Synchronisation zwischen Spielern.

### Features

- **Pfeiltasten-Steuerung**: Einfache Bedienung mit den Pfeiltasten
- **Flexibles Berechtigungssystem**: Konfigurierbar - nur Fahrer oder alle Insassen können Blinker bedienen
- **Nur Bodenfahrzeuge**: Funktioniert nur bei Autos, Motorrädern, LKWs etc.
- **Realistische Sounds**: 4 verschiedene WAV-Audio-Dateien für authentisches Feedback
  - `TURN_LEVER_INTRO.wav` - Blinker einschalten
  - `TURN_LEVER_OUTRO.wav` - Blinker ausschalten
  - `INDICATOR_SOUND.wav` - Kontinuierlicher Tick-Sound
  - `HAZARD_BUTTON.wav` - Warnblinker Sound
- **Sound-Sharing**: Alle Insassen im gleichen Fahrzeug hören die Blinker-Sounds
- **Synchronisiert**: Alle Spieler sehen die Blinker anderer Fahrzeuge in Echtzeit
- **Intelligentes Ausschalten**: Zwei Modi - sofortiges oder verzögertes automatisches Ausschalten nach Kurven
- **Konfigurierbar**: Lautstärke, Sound-Aktivierung, Auto-Turn-Off und Berechtigungen anpassbar
- **Warnblinker**: Inklusive Hazard-Lights Funktion
- **Debug-System**: Detaillierte Konsolen-Ausgaben für Fehlersuche
- **Mehrsprachig**: Deutsche und englische Sprachunterstützung

### Steuerung

| Taste | Funktion |
|-------|----------|
| ← (Links) | Linker Blinker ein/aus |
| → (Rechts) | Rechter Blinker ein/aus |
| ↓ (Runter) | Warnblinker ein/aus |

### Konfiguration

Alle Einstellungen können in der `config.lua` angepasst werden:

### Sound Einstellungen
```lua
Config.Sound = {
    enabled = true,              -- Sound aktiviert (true/false)
    volume = 0.5,               -- Globale Lautstärke (0.0 - 1.0)
    shareWithPassengers = true, -- Sounds mit anderen Insassen teilen (true/false)
    
    -- Individuelle Sound-Dateien
    sounds = {
        indicator = "INDICATOR_SOUND.wav",      -- Blinker-Tick Sound
        turnOn = "TURN_LEVER_INTRO.wav",       -- Blinker an Sound
        turnOff = "TURN_LEVER_OUTRO.wav",      -- Blinker aus Sound
        hazard = "HAZARD_BUTTON.wav"           -- Warnblinker Sound
    }
}
```

### Blinker Einstellungen
```lua
Config.Blinker = {
    customTiming = true,        -- Eigenes Blink-Timing verwenden (true) oder GTA Standard (false)
    interval = 500,             -- Blink-Intervall in Millisekunden (nur wenn customTiming = true)
    autoTurnOff = {
        enabled = true,         -- Automatisches Ausschalten nach Kurven
        steeringThreshold = 15, -- Lenkwinkel-Schwellenwert in Grad
        instantTurnOff = true   -- Sofort ausschalten bei Winkel-Erreichen (true) oder warten bis geradeaus (false)
    }
}
```

### Fahrzeug Einstellungen
```lua
Config.Vehicle = {
    driverOnly = true           -- true = nur Fahrer, false = alle Insassen
}
```

### Tastenbelegung
```lua
Config.Controls = {
    leftBlinker = "LEFT",       -- Pfeiltaste Links
    rightBlinker = "RIGHT",     -- Pfeiltaste Rechts
    hazardLights = "DOWN"       -- Pfeiltaste Runter
}
```

### Debug Einstellungen
```lua
Config.Debug = {
    enabled = true,             -- Debug-Modus aktiviert
    showStateChanges = true,    -- State-Änderungen in Console anzeigen
    showVehicleInfo = false     -- Fahrzeug-Informationen anzeigen
}
```

## Automatisches Ausschalten

Das Script bietet zwei Modi für das automatische Ausschalten:

### 🚀 Sofortiges Ausschalten (`instantTurnOff = true`)
- Blinker wird **sofort** ausgeschaltet, sobald der Lenkwinkel-Schwellenwert erreicht wird
- Sehr reaktiv und direkt
- Ideal für schnelle Fahrweise

### ⏳ Verzögertes Ausschalten (`instantTurnOff = false`)
- Blinker wird erst ausgeschaltet, wenn du nach einer starken Lenkbewegung wieder geradeaus fährst
- Realistischer wie im echten Auto
- Ideal für langsamere, realistische Fahrweise

**Kurven-Erkennung**: Wenn der Lenkwinkel über den Schwellenwert (15°) geht  
**Wichtig**: Funktioniert bei jeder Geschwindigkeit, auch im Stand oder bei Rückwärtsfahrt.

## Blinker-Timing System

Das Script bietet flexible Timing-Optionen:

### ⚙️ Eigenes Timing (`customTiming = true`)
- **Vollständige Kontrolle** über das Blink-Intervall
- Konfigurierbar von 100ms bis 2000ms
- **Synchron**: Visuelle Blinker und Sounds perfekt abgestimmt
- Ideal für: Angepasste Server-Einstellungen

### 🎮 GTA Standard (`customTiming = false`)
- Verwendet **GTA's eingebautes** Blinker-Timing
- Etwa 500ms Intervall (wie normale GTA Fahrzeuge)
- Weniger Konfiguration nötig
- Ideal für: Standard GTA-Feeling beibehalten

**Beispiele**:
- `interval = 300` → Schnelle, sportliche Blinker
- `interval = 750` → Langsame, realistische Blinker
- `interval = 1000` → Sehr langsame LKW-ähnliche Blinker

## Berechtigung System

Das Script bietet zwei Modi für die Blinker-Bedienung:

### 👨‍✈️ Nur Fahrer (`driverOnly = true`)
- Nur der Fahrer kann die Blinker bedienen
- Beifahrer und andere Insassen haben keinen Zugriff
- Realistisch wie im echten Auto

### 👥 Alle Insassen (`driverOnly = false`)
- Jeder Insasse kann die Blinker bedienen
- Fahrer, Beifahrer, Rücksitzpassagiere - alle haben Zugriff
- Praktisch für Roleplay-Szenarien oder Fahrstunden

## Sound System

Das Script bietet ein intelligentes Sound-System:

### 🔊 Sound-Sharing (`shareWithPassengers = true`)
- **Alle Insassen** im gleichen Fahrzeug hören die Blinker-Sounds
- Realistisch - wie im echten Auto
- Tick-Sound, Ein/Aus-Geräusche und Warnblinker für alle hörbar

### 🔇 Nur eigene Sounds (`shareWithPassengers = false`)
- **Nur der Spieler** der die Blinker bedient hört die Sounds
- Andere Insassen hören nichts
- Weniger Netzwerk-Traffic

**Wichtig**: Andere Fahrzeuge hören nie deine Sounds - nur die Insassen im gleichen Auto!

## Test Commands

- `/testsound` - Spielt den Indikator-Sound zum Testen ab

## Installation

1. Script in den `resources` Ordner kopieren
2. In der `server.cfg` hinzufügen: `ensure flashlight`
3. Server neustarten

## Dateien

- `client.lua` - Client-seitige Logik mit Auto-Turn-Off System
- `server.lua` - Server-seitige StateBag-Synchronisation  
- `config.lua` - Zentrale Konfigurationsdatei
- `fxmanifest.lua` - Resource-Definition
- `html/index.html` - NUI Audio-Interface für WAV-Wiedergabe
- `html/*.wav` - Audio-Dateien für realistische Sounds

## Technische Details

- **StateBags**: Optimierte Echtzeit-Synchronisation zwischen Clients
- **NUI Audio**: Browser-basierte WAV-Wiedergabe für beste Sound-Qualität
- **Fahrzeugklassen-Filter**: Unterstützt nur Bodenfahrzeuge (keine Flugzeuge/Boote)
- **Fahrersitz-Erkennung**: Verhindert Missbrauch durch Beifahrer
- **Auto-Turn-Off**: Intelligente Kurven-Erkennung ohne Geschwindigkeitsbegrenzung

## Kompatibilität

- Funktioniert mit allen Standard FiveM Servern
- Verwendet StateBags für optimale Performance
- Kompatibel mit anderen Vehicle-Scripts
- Keine Konflikte mit Standard GTA V Blinker-System

## Support

Bei Problemen oder Fragen, bitte ein Issue erstellen oder den Entwickler kontaktieren.

---
**Version:** 2.0.0  
**Author:** xtomatex2
**Resource Name:** flashlight
