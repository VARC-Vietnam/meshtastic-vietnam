# Getting Started with Meshtastic in Vietnam

[Tiếng Việt](Getting-Started.md) · [README](README.en.md) · [Frequency slots](BANDS-FrequencySlots.en.md)

Short guide to flash firmware and configure a node for community mesh use in Vietnam.

> Attach an **antenna before** powering on / transmitting. Transmitting without an antenna can damage the LoRa radio.

## Recommended VARC (Vietnam) settings

| Setting | Suggested value |
| --- | --- |
| **Region** | `SG_923` (no official `VN_*` region yet) |
| **Modem Preset** | **LongFast** (`LONG_FAST`) |
| **Primary channel** | Default public **LongFast** channel (name `LongFast`, default PSK) |
| **Frequency Slot** | **4 – 23** (center frequency in **918 – 923 MHz** — VN923 column); **suggested default: 6** |
| **TX Power** | **≤ 14 dBm** (~**25 mW**) — **do not** leave the device default |

Full slot table: [BANDS-FrequencySlots.en.md](BANDS-FrequencySlots.en.md) · [Frequency Slot Calculator](https://meshtastic.org/docs/overview/radio-settings/)

> In some apps / the calculator, Frequency Slot starts at **1** (= slot **0** in our table). Match the **MHz** value to the VN923 column, not only the raw slot number.

> **TX Power:** Region `SG_923` allows firmware up to ~**20 dBm** (~100 mW). A setting of **0** / device default usually means that region ceiling — **above** Vietnam’s license-exempt limit (**≤ 25 mW ERP**). Set it manually to **≤ 14 dBm**. Antenna gain raises real ERP; with positive-gain antennas, use a lower TX power.

---

## 1. Hardware checklist

1. Meshtastic-compatible LoRa node (ESP32 / nRF52 / …) + antenna suitable for ~915–925 MHz.
2. USB **data** cable (not charge-only).
3. Computer or phone for flashing / configuration.

## 2. Flash firmware

1. Open the [Meshtastic Web Flasher](https://flash.meshtastic.org/).
2. Select your exact device model.
3. Flash the latest stable firmware following [Getting Started](https://meshtastic.org/docs/getting-started/).
4. Install serial drivers if required (typical for ESP32) — see Getting Started.

## 3. Connect a client

Use one of:

- **Android** — [Meshtastic Android](https://meshtastic.org/docs/software/android/)
- **iOS / iPadOS** — [Meshtastic Apple](https://meshtastic.org/docs/software/apple/)
- **Web** — [client.meshtastic.org](https://client.meshtastic.org/)
- **CLI** — `pip3 install --upgrade meshtastic` ([Python CLI](https://meshtastic.org/docs/software/python/cli/))

Pair over Bluetooth or USB Serial.

## 4. LoRa settings for Vietnam

Follow [Initial Configuration](https://meshtastic.org/docs/getting-started/initial-config/):

1. Open **Settings → LoRa** (or *Radio Configuration → LoRa*).
2. Set **Region** = **`SG_923`**.
3. Set **Modem Preset** = **`LONG_FAST`** (LongFast).
4. Set **Frequency Slot** to a value in **4 – 23** — **suggested default: 6** (every node on the same mesh must use the **same** slot).
5. Set **Transmit Power / TX Power** to **≤ 14 dBm** (do not leave `0` / device default).
6. Keep **Use Preset** enabled unless you intentionally customize modem parameters.
7. Send / save the config to the device.

### CLI example

```bash
meshtastic --set lora.region SG_923
meshtastic --set lora.modem_preset LONG_FAST
meshtastic --set lora.channel_num 6
meshtastic --set lora.tx_power 14
```

`channel_num` in the CLI/app is often the **Frequency Slot** (1-based in some UIs). Check the actual frequency on the device or calculator and pick a value that lands in the **VN923** column of [BANDS-FrequencySlots.en.md](BANDS-FrequencySlots.en.md).

`lora.tx_power` is in **dBm**. Use **14** (or lower) instead of the default / `0`.

## 5. LongFast public channel

1. Open **Channels**.
2. Channel 0 (primary): name **`LongFast`**, default public PSK (Meshtastic default — commonly `AQ==`).
3. Do not rename the primary channel if you want to match the public mesh when Frequency Slot is left at 0 / automatic (renaming changes the hash).
4. When you **pin Frequency Slot** (e.g. **6**, within 4–23), every mesh peer must share the same region, LongFast, and **same slot**.

See also: [Joining your local mesh](https://meshtastic.org/docs/getting-started/joining-your-local-mesh/).

## 6. Verify

1. Set a clear **Node name** / short name.
2. Send a test message on LongFast.
3. Confirm the device frequency / slot is in VN923 (918–923 MHz).
4. If you hear no peers: ask the VARC community which slot is used locally, then match it.

## Legal note (short)

- `SG_923` is only the closest firmware preset — see [BANDS-FrequencySlots.en.md](BANDS-FrequencySlots.en.md) and [README.en.md](README.en.md).
- Vietnam’s license-exempt rules have strict power / duty-cycle limits; a typical Meshtastic mesh may not fully meet them. Operators are responsible for lawful use.

## References

- [Getting Started](https://meshtastic.org/docs/getting-started/)
- [Initial Configuration](https://meshtastic.org/docs/getting-started/initial-config/)
- [Joining your local mesh](https://meshtastic.org/docs/getting-started/joining-your-local-mesh/)
- [Web Flasher](https://flash.meshtastic.org/)
- [BANDS-FrequencySlots.en.md](BANDS-FrequencySlots.en.md)
- [README — legal](README.en.md)
