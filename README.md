# Tendo

**Tendo** is an AI-driven, tendon-actuated flexible continuum manipulator ("spine" architecture). 

The mechanical structure uses antagonist cable pairs (Bowden cables) routed to shared pulleys, allowing smooth, bio-inspired bending and actuation controlled via a real-time microcontroller interface and high-level AI logic.

---

## Architecture

* **High-Level Control (AI & Host):** Raspberry Pi / Host PC running Python scripts and AI models, communicating over USB Serial (ASCII protocol).
* **Real-Time Motion Control:** STM32F411 microcontroller handling step/dir pulse generation, acceleration profiles, safety limits, and auxiliary I/O.
* **Logic Level Shifting:** 3.3V to 5V buffering via `SN74HCT245N` octals.
* **Power & Actuation:** 4× NEMA 23 stepper motors driven at 36V DC by `TB67S109AFTG` stepper drivers.

---

## Hardware Bill of Materials (BOM)

| Component | Qty | Model / Link |
| :--- | :---: | :--- |
| **Stepper Motors** | 4 | [SY57STH41-2804B (NEMA 23, 2.8A)](https://kosmodrom.ua/ru/shagovyy-dvigatel/sy57sth41-2804b.html) |
| **Stepper Drivers** | 4 | [TB67S109AFTG-MODUL-BOX](https://kosmodrom.ua/ru/kontroller-shagovogo-dvigatelya/tb67s109aftg-modul-box.html) |
| **Power Supply** | 1 | [Mean Well LRS-350-36 (36V, 350W)](https://kosmodrom.ua/ru/modulnyy-istochnik-pitaniya-v-metallicheskom-korpuse/lrs-350-36.html) |
| **MCU Board** | 1 | [STM32F411CEU6 Black Pill (25MHz HSE)](https://kosmodrom.ua/ru/otladochnaya-plata/stm32f411ceu6-25m-hse.html) |
| **Level Shifters** | 4 | [SN74HCT245N (Octal Bus Transceiver)](https://kosmodrom.ua/ru/mikroshema-serii-74hct/sn74hct245n.html) |
| **Host Controller** | 1 | Raspberry Pi 1 Model B+ (or compatible Linux host) |

---

## Project Roadmap

- [ ] Mechanical design of spine segments, pulleys, and Bowden cable guides (PETG + Nylon tendons)
- [ ] Electronics wiring and 3.3V → 5V level-shifting board assembly
- [ ] STM32 firmware with `AccelStepper` and Serial ASCII command parser
- [ ] Python Serial interface and safety limits validation
- [ ] AI control integration

---

## License

MIT
