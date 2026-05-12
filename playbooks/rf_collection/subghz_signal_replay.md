# 🏴‍☠️ CK-RF-001: Sub-GHz Signal Replay Attack

| Metadato | Valor |
|:---|:---|
| **ID (CK)** | CK-RF-001 |
| **Táctica MITRE** | Collection (T1119) |
| **Herramienta** | HackRF One + PortaPack-Havoc-Mod |
| **Dificultad** | ⭐⭐☆☆☆ |

## 📋 Resumen para la Abuela
> “Abuela, con esto grabo la llave de tu garaje cuando pulsas el mando, y luego la repito para abrirlo yo. Tranquila, ¡solo lo pruebo en mi casa!”

## ⚙️ Kit Necesario
- [HackRF One](https://greatscottgadgets.com/hackrf/)
- PortaPack H2+ con [PortaPack-Havoc-Mod](https://github.com/KevinDevSecOps/PortaPack-Havoc-Mod-KevDevSecOps-)
- Mando original del dispositivo a emular

## ⚡ Pasos de Emulación
1. **Reconocimiento:** Abre la app `Capture` en el PortaPack. Sintoniza la frecuencia (comúnmente 433.92 MHz). Pulsa el mando original para ver la señal.
2. **Captura:** Graba la señal completa a una tasa de 500k muestras/seg.
3. **Arma:** Ve a la app `Replay`, selecciona tu captura y ajusta la ganancia TX a 47dB.
4. **¡Fuego!** Transmite la señal. El dispositivo objetivo debería actuar como si usaras el mando original.

## 🛡️ Cómo Detectarlo (Blue Teaming)
Si ves en tu monitor de espectro (como `gqrx`) una señal idéntica repetida cada pocos segundos en la banda ISM de 433 MHz fuera del horario normal, tienes un posible replay attack. Adjunto una regla Sigma en `/detection`.