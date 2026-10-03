# Advance_LFR_OS

### Advanced Embedded Control Platform for an Autonomous Line Following Robot

**Advance_LFR_OS** is a modular embedded control system developed for a high-performance autonomous Line Following Robot (LFR) built around the **ESP32 DevKit V1**.

The system combines multi-channel IR sensing, external ADC acquisition, sensor calibration, real-time line-position calculation, P+D control, track-pattern recognition, autonomous path handling, BLE communication, onboard diagnostics, OLED visualization, motor control, and race timing into a single robotics control platform.

The current hardware implementation is based on the **RED SHIFT Alpha V4** platform.

---

## Project Overview

Advance_LFR_OS was designed with one primary objective:

> Build a flexible and extensible control platform for a competition-oriented Line Following Robot rather than a simple sensor-to-motor Arduino program.

The system separates the robot into several functional layers:

```text
                    ADVANCE_LFR_OS
                          │
        ┌─────────────────┼─────────────────┐
        │                 │                 │
     SENSING           CONTROL          INTERFACE
        │                 │                 │
        ▼                 ▼                 ▼
  TCRT5000 Array       P + D Control      OLED
        │                 │               Buttons
        ▼                 ▼               BLE
   MCP3208 ADCs       Motor Control       Buzzer
        │                 │
        └────────┬────────┘
                 ▼
             Navigation
                 │
       ┌─────────┼─────────┐
       ▼         ▼         ▼
    Turns    Intersections  Path
       │         │           │
       └─────────┼───────────┘
                 ▼
            TB6612FNG
                 │
          ┌──────┴──────┐
          ▼             ▼
       N20 Motor      N20 Motor
