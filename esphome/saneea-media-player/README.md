# ESP32-S3 Media Player

ESP32-S3 Supermini + MAX98357A audio player for Home Assistant. Plays TTS notifications, MP3/WAV files, and internet radio streams via ESPHome.

## Wiring

| ESP32-S3 Supermini | MAX98357A |
|--------------------|-----------|
| 5V                 | VIN       |
| GND                | GND       |
| GPIO13             | DIN       |
| GPIO12             | BCLK      |
| GPIO11             | LRC       |