# ASL Glove Translator

> **Status: In Development** — Hardware planning and component selection in progress.

A wearable smart glove that recognizes American Sign Language (ASL) hand gestures in real time and translates them into text and speech output.

## Concept

The glove captures hand orientation and finger flex data using embedded sensors, processes the gesture on-device using a trained model, and outputs the recognized letter/word via a companion app or speaker.

```
[Glove Sensors] --> [ESP32] --> [BLE/WiFi] --> [Mobile App / Speaker]
  Flex x5            MCU         Wireless        Text + TTS output
  IMU (MPU6050)      Inference
```

## Planned Hardware

| Component | Purpose |
|-----------|---------|
| ESP32 | Main MCU — sensor reading, inference, wireless |
| MPU6050 | IMU — wrist pitch, roll, twist |
| Flex sensors x5 | Finger bend detection (one per finger) |
| Bluetooth / WiFi | Data transmission to companion app |
| Speaker (optional) | On-device TTS audio output |

## Planned Software

- **Firmware (Arduino/ESP-IDF):** Sensor fusion, gesture classification, BLE communication
- **ML Model:** Train a classifier on ASL alphabet gesture data (flex + IMU features)
- **Companion App:** Display recognized text, sentence builder, TTS playback

## Roadmap

- [ ] Finalize BOM and hardware design
- [ ] Build and wire prototype glove
- [ ] Collect gesture dataset (flex + IMU readings per ASL letter)
- [ ] Train and optimize classification model (target: edge-deployable)
- [ ] Implement real-time inference on ESP32
- [ ] Build companion mobile app
- [ ] Test full pipeline end-to-end

## Related Work

This project builds on experience from the [ESP32 Gesture-Controlled Robotic Arm](https://github.com/breksos/esp32-gesture-robotic-arm), which uses the same MPU6050 + flex sensor approach for hand tracking.

## Team

- Berk Hakan Öge
- Utku Gökçek
