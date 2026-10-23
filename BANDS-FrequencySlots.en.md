# Meshtastic Frequency Table — `SG_923`

[Tiếng Việt](BANDS-FrequencySlots.md) · [README](README.en.md) · [Getting Started](Getting-Started.en.md)

Meshtastic region **`SG_923`**: **917.0 – 925.0 MHz** (Singapore firmware preset).

> Frequencies use the default **`LONG_FAST`** preset (**250 kHz** bandwidth) and the Meshtastic firmware formula:  
> `freq = 917.0 + (bw/2000) + (slot × bw/1000)` MHz  
> Verify interactively: [Frequency Slot Calculator](https://meshtastic.org/docs/overview/radio-settings/)

**Note:** In the app / calculator, Frequency Slot often starts at **1** (= slot **0** in this table). Config value **0** may mean *automatic (hash from channel name)*.

## Meshtastic Frequency Table

| Frequency Slot | SG923 (MHz) | VN923 (MHz) |
| ---: | ---: | ---: |
| 0 | 917.125 |  |
| 1 | 917.375 |  |
| 2 | 917.625 |  |
| 3 | 917.875 |  |
| 4 | 918.125 | 918.125 |
| 5 | 918.375 | 918.375 |
| 6 | 918.625 | 918.625 |
| 7 | 918.875 | 918.875 |
| 8 | 919.125 | 919.125 |
| 9 | 919.375 | 919.375 |
| 10 | 919.625 | 919.625 |
| 11 | 919.875 | 919.875 |
| 12 | 920.125 | 920.125 |
| 13 | 920.375 | 920.375 |
| 14 | 920.625 | 920.625 |
| 15 | 920.875 | 920.875 |
| 16 | 921.125 | 921.125 |
| 17 | 921.375 | 921.375 |
| 18 | 921.625 | 921.625 |
| 19 | 921.875 | 921.875 |
| 20 | 922.125 | 922.125 |
| 21 | 922.375 | 922.375 |
| 22 | 922.625 | 922.625 |
| 23 | 922.875 | 922.875 |
| 24 | 923.125 |  |
| 25 | 923.375 |  |
| 26 | 923.625 |  |
| 27 | 923.875 |  |
| 28 | 924.125 |  |
| 29 | 924.375 |  |
| 30 | 924.625 |  |
| 31 | 924.875 |  |

- **32** slots (`LONG_FAST` / 250 kHz on `SG_923`)

Other presets (125 / 500 kHz) change slot count and frequencies — use the [Frequency Slot Calculator](https://meshtastic.org/docs/overview/radio-settings/).

## Meshtastic region limits vs Vietnam

Duty-cycle and power columns for Meshtastic regions come from the official [LoRa Configuration](https://meshtastic.org/docs/configuration/radio/lora/) docs. Those are **firmware** ceilings; national law may add other rules (for example, US FCC constraints are not only a simple duty-cycle %).

**Power cheat sheet:** 10 dBm ≈ 10 mW · **14 dBm ≈ 25 mW** (Vietnam LPWAN cap) · 20 dBm = 100 mW · 27 dBm ≈ 500 mW · 30 dBm = 1 W

| Region / rule | Band (MHz) | Duty cycle (firmware / law) | Power ceiling | Fit for Meshtastic mesh? |
| --- | --- | --- | --- | --- |
| **Vietnam LPWAN (license-exempt law)** | 433.05–434.79 / 920–923 | **1% end device / 10% gateway** | **≤ 25 mW ERP (~14 dBm)** | Poor — no official `VN_*` region |
| `EU_433` | 433–434 | **10%** | 10 dBm | Possible but constrained |
| `EU_868` | 869.4–869.65 | **10%** | 27 dBm | Possible; firmware pauses TX at the limit |
| `EU_866` | 865.6–867.6 | **2.5%** (10% for routers) | 27 dBm | Tight |
| `TH` (Thailand) | 920–925 | **10%** (firmware) | 27 dBm | Like EU |
| `UA_433` | 433–434.7 | **10%** | 10 dBm | Like `EU_433` |
| `US` | 902–928 | **100%*** | 30 dBm | Favorable |
| `ANZ` | 915–928 | **100%*** | 30 dBm | Favorable |
| `ANZ_433` | 433.05–434.79 | **100%*** | 14 dBm | Favorable (power similar to VN) |
| `KR` | 920–923 | **100%*** | 23 dBm | Favorable |
| `JP` | 920.5–923.5 | **100%*** | 13 dBm | Favorable (low power) |
| `SG_923` (firmware) | **917–925** | **100%*** | 20 dBm (~100 mW) | Firmware looser than SG law |
| `MY_433` / `MY_919` | 433–435 / 919–924 | **100%*** | 20 / 27 dBm | Favorable |
| `CN` | 470–510 | **100%*** | 19 dBm | Favorable |
| `LORA_24` | 2400–2483.5 | **100%*** | 10 dBm | Favorable (short range) |

\*In the Meshtastic table, **100%** means the firmware **does not enforce** a duty-cycle limit. Local law may still impose other constraints (frequency hopping, channel occupancy, etc.).

### Takeaways

1. **Power:** Vietnam’s ~14 dBm ceiling is similar to `ANZ_433` / `JP`, lower than US / `EU_868` / KR, and a bit higher than `EU_433` (10 dBm). Versus EU, power alone is **not** the main gap.
2. **Duty cycle is Vietnam’s difference:** many Asia / US / ANZ regions use firmware **100%**; EU / Thailand use **10%** (Meshtastic can still run); Vietnam license-exempt end devices require **1%** — stricter than EU and the main reason `VN_*` regions were rejected.
3. **EU is the middle case:** Meshtastic can live with **10%** (it pauses TX when the budget is used). Vietnam’s **1% on clients** is hard to reconcile with beacons and multi-hop relays.
4. **Amateur bands (separate from license-free):** Meshtastic `ITU3_70CM` and similar regions allow up to 30 dBm / 100% in firmware, but only in **licensed mode** (callsign, no encryption). In Vietnam you still need an amateur certificate and station license.

**Bottom line:** License-free Meshtastic is easiest where law/firmware allow high airtime (US, ANZ, KR, MY…). EU/TH are tighter but workable at 10%. Vietnam’s license-exempt LPWAN has **1% client airtime** — too low for typical Meshtastic mesh.

## Regional comparison: Vietnam ↔ Singapore

| | Vietnam (license-exempt) | Singapore (IMDA) | Meshtastic `SG_923` (firmware) |
| --- | --- | --- | --- |
| Band | **918.4–923** (SRD) / **920–923** (LPWAN) MHz | **917–925** MHz | **917–925** MHz |
| LPWAN end-device power | ≤ **25 mW ERP** (~14 dBm) | ≤ **100 mW ERP** | Firmware ceiling **20 dBm** (~100 mW) |
| LPWAN duty cycle | End ≤ **1%**; gateway ≤ **10%** | End ≤ **1%**; NAP ≤ **10%** | Firmware lists **100%** (does not enforce 1%/10%) |
| Official Meshtastic region | No `VN_*` yet | — | `SG_923` |

| Source | Content |
| --- | --- |
| [01/VBHN-BKHCN](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Van-ban-hop-nhat-01-VBHN-BKHCN-2025-Thong-tu-Danh-muc-thiet-bi-vo-tuyen-dien-duoc-mien-giay-phep-660171.aspx) / [Circular 08/2021 PDF](https://datafiles.chinhphu.vn/cpp/files/vbpq/2021/10/08-btttt.signed.pdf) | VN: items 44–45, Appendices 3 & 19 |
| [IMDA TS SRD](https://www.imda.gov.sg/-/media/imda/files/regulation-licensing-and-consultations/ict-standards/telecommunication-standards/radio-comms/imdatssrd.pdf) (Table 1, 30a–30d) | SG: 917–925 MHz; 30c LPWAN end ≤100 mW / ≤1%; 30b NAP ≤500 mW / ≤10% |
| [Meshtastic LoRa — `SG_923`](https://meshtastic.org/docs/configuration/radio/lora/) | Firmware: 917–925 MHz, 20 dBm, no SG legal duty-cycle enforcement |

`SG_923` is a Singapore firmware region — **not** a Vietnamese license-exempt allocation. Using it in Vietnam can transmit outside **918.4–923 / 920–923 MHz** and miss Vietnam’s power / duty-cycle ceilings.

## References

- [Frequency Slot Calculator / Radio Settings](https://meshtastic.org/docs/overview/radio-settings/)
- [LoRa Configuration — Region `SG_923`](https://meshtastic.org/docs/configuration/radio/lora/)
- [IMDA TS SRD (Singapore)](https://www.imda.gov.sg/-/media/imda/files/regulation-licensing-and-consultations/ict-standards/telecommunication-standards/radio-comms/imdatssrd.pdf)
- [README — Vietnam legal notes](README.en.md)
