# VARC Meshtastic Networking (Vietnam)

[Tiếng Việt](README.md)

This repository is maintained under **VARC (Vietnam Amateur Radio Club)** — the community effort to connect Meshtastic nodes into Vietnam’s mesh networks.

## What is Meshtastic?

[Meshtastic](https://meshtastic.org/) is an open-source project for **decentralized, off-grid** messaging over LoRa. Devices (nodes) form a mesh: text, location, and sensor data can hop across the network without cellular or Internet infrastructure.

## VARC Meshtastic network

VARC is Vietnam’s non-profit amateur radio society and an IARU member society. Vietnamese amateur call signs commonly use the **XV** / **3W** prefixes.

The **VARC Meshtastic network** aims to:

- Connect Meshtastic users in Vietnam into a community mesh
- Share configuration guidance, frequency practice, and safe / lawful operating notes
- Align with amateur-radio culture (training, technical study, community support when appropriate)
- Document Vietnam-oriented network resources and configs

> **Disclaimer:** The legal section below is community documentation for orientation only. It is **not** legal advice. Anyone who transmits must verify current law and guidance from the competent authorities (the Radio Frequency Directorate and/or provincial People’s Committees under the current decentralization rules).

## Getting Started

Flash firmware and configure a node for mesh use in Vietnam: **[Getting-Started.en.md](Getting-Started.en.md)** — Region `SG_923`, LongFast, Frequency Slot **4–23** (default **6**, 918–923 MHz), TX Power **≤ 14 dBm**.

Frequency table / region comparison: [BANDS-FrequencySlots.en.md](BANDS-FrequencySlots.en.md).

---

## Legal framework for Meshtastic in Vietnam

Radio transmission in Vietnam is governed by the **Law on Radio Frequencies** (Law No. 42/2009/QH12, amended by Law No. 09/2022/QH15 and related adjustments; current consolidated text: [**36/VBHN-VPQH**](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-36-vbhn-vpqh-41379.htm), authenticated **27 Dec 2023**).

General rule: a **radio-frequency use license** is required, except for devices on the **license-exempt** list that also meet the technical and operational conditions.

### Consolidated legal instruments (newest → oldest by authentication date)

| Instrument | Authenticated | Effective (as published) | Role for Meshtastic / spectrum |
| --- | --- | --- | --- |
| [**09/2026/VBHN-TT-BKHCN**](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-09-2026-vbhn-tt-bkhcn-470351.htm) — Inspection of telecom equipment & radio stations | 25 Aug 2026 | *(as published in Công báo)* | Mandatory inspection where the station/device is on the compulsory list |
| [**23/VBHN-BTC**](https://chinhphu.vn/?docid=214898&pageid=27160) (2025) — Updated consolidation of Circular 265/2016/TT-BTC | 5 Aug 2025 | *(per amendments in the text; includes Circular 65/2025)* | **Newer** fee consolidation than 19/VBHN-BTC — prefer when paying fees |
| [**01/VBHN-BKHCN**](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Van-ban-hop-nhat-01-VBHN-BKHCN-2025-Thong-tu-Danh-muc-thiet-bi-vo-tuyen-dien-duoc-mien-giay-phep-660171.aspx) — License-exempt radio devices | 4 Jun 2025 | 4 Jun 2025 | **Core LoRa/LPWAN/SRD exemption** rules (consol. of Circular 08/2021 + amendments) |
| [**36/VBHN-VPQH**](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-36-vbhn-vpqh-41379.htm) — Law on Radio Frequencies | 27 Dec 2023 | 27 Dec 2023 | Primary statute: licensing, exemptions, operator duties |
| [**19/VBHN-BTC**](https://luatvietnam.vn/thue/van-ban-hop-nhat-19-vbhn-btc-230686-d5.html) — License & spectrum use fees (consol. of Circular 265/2016) | 5 Sep 2022 | 5 Sep 2022 | Fee schedule when applying for a license (2022 consolidation) |
| [**08/VBHN-BTTTT**](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-08-vbhn-btttt-37604.htm) — Administrative sanctions (postal, telecom, **radio frequency**, IT…) | 20 Jul 2022 | 20 Jul 2022 | Penalties for unlawful frequency/equipment use (incl. exempt-device misuse — Art. 64 of the underlying decree) |
| [**05/VBHN-BTTTT**](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-05-vbhn-btttt-37109.htm) — National spectrum plan (consolidated) | 5 May 2022 | 5 May 2022 | Older plan (Decision 71/2013 + amendments). **Current:** [37/2025/QĐ-TTg](https://congbao.chinhphu.vn/van-ban/quyet-dinh-so-37-2025-qd-ttg-46329/59232.htm) (effective 20 Nov 2025) |

For Meshtastic (LoRa mesh), two paths are commonly discussed:

### 1. License-exempt devices (SRD / LPWAN)

Primary instruments:

| Document | Relevance |
| --- | --- |
| [Circular 08/2021/TT-BTTTT](https://datafiles.chinhphu.vn/cpp/files/vbpq/2021/10/08-btttt.signed.pdf) | List of radio devices exempt from a frequency-use license; technical & operational conditions |
| [**01/VBHN-BKHCN**](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Van-ban-hop-nhat-01-VBHN-BKHCN-2025-Thong-tu-Danh-muc-thiet-bi-vo-tuyen-dien-duoc-mien-giay-phep-660171.aspx) (4 Jun 2025) | Current consolidation of Circular 08/2021 and amendments |
| [Circular 01/2025/TT-BKHCN](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Van-ban-hop-nhat-01-VBHN-BKHCN-2025-Thong-tu-Danh-muc-thiet-bi-vo-tuyen-dien-duoc-mien-giay-phep-660171.aspx) | Amendments to the annexes of Circular 08/2021 |

**License-exempt ~433 / ~920 MHz bands** under Appendix 1 (list) plus matching technical annexes:

| Item (Appendix 1) | Band | Device class | Max power (exempt) | Operating conditions | Conditions annex |
| --- | --- | --- | --- | --- | --- |
| 39 | **433.05 – 434.79 MHz** | LPWAN | ≤ **25 mW ERP** | Gateway ≤ **10%** DC; end device ≤ **1%** DC | [Appendix 19](https://datafiles.chinhphu.vn/cpp/files/vbpq/2021/10/08-btttt.signed.pdf) |
| 44 | **918.4 – 923 MHz** | Non-specific SRD | ≤ **25 mW ERP** | **LBT** or duty cycle ≤ **1%** | [Appendix 3](https://datafiles.chinhphu.vn/cpp/files/vbpq/2021/10/08-btttt.signed.pdf) |
| 45 | **920 – 923 MHz** | LPWAN | ≤ **25 mW ERP** | Gateway ≤ **10%** DC; end device ≤ **1%** DC | [Appendix 19](https://datafiles.chinhphu.vn/cpp/files/vbpq/2021/10/08-btttt.signed.pdf) |

Also from Circular 08/2021:

- Item 43: **918.4 – 923 MHz** RFID ≤ 500 mW ERP (not a typical Meshtastic device class)
- Above the exemption ceilings (e.g. LPWAN up to 100 mW ERP on 433 MHz, or up to 306 mW ERP on 920–923 MHz) → a **frequency and equipment license** is required (Article 4 of Circular 08/2021)
- Multi-band / multi-power devices used in Vietnam must have frequency and power parameters **fixed** to the allowed values

For Meshtastic region limits and `SG_923` / Singapore comparison, see [BANDS-FrequencySlots.en.md](BANDS-FrequencySlots.en.md).

### 2. Amateur radio service (certificate + station license)

Operating on **amateur** allocations requires:

1. An **amateur radio operator certificate**, and  
2. A **frequency and equipment license** for the amateur station.

| Instrument / plan | Role |
| --- | --- |
| [Decision 37/2025/QĐ-TTg](https://congbao.chinhphu.vn/van-ban/quyet-dinh-so-37-2025-qd-ttg-46329/59232.htm) | **National radio spectrum plan** (effective 20 Nov 2025). Around 70 cm, Vietnam allocates **Amateur** (often as a secondary service) in **430–432**, **432–435**, **435–438**, and **438–440 MHz** |
| [Decree 133/2025/NĐ-CP](https://rfd.gov.vn/tin-tuc/pages/van-ban-moi.aspx?ItemID=3329) | From **1 Jul 2025**, provincial People’s Committees handle many amateur station licensing steps and recognition of certificate-issuing organizations |
| [Circular 37/2026/TT-BKHCN](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Thong-tu-37-2026-TT-BKHCN-trinh-tu-thu-tuc-thi-cap-chung-chi-vo-tuyen-dien-nghiep-du-714522.aspx) | Amateur certificates Classes I / II / III; exam, issuance, and revocation procedures (effective **1 Jul 2026**) |
| [Circular 23/2024/TT-BTTTT](https://congbao.chinhphu.vn/van-ban/thong-tu-so-23-2024-tt-btttt-44060.htm) | Repealed the former [Decision 18/2008/QĐ-BTTTT](https://chinhphu.vn/default.aspx?docid=64638&pageid=27160) (old amateur operating rules) as of **31 Dec 2024** |

Amateur operating principles (under the traditional framework and current allocation plan):

- Purpose is **self-training, technical study, and personal interest**, **not for profit**
- No commercial traffic, national-security content, news broadcasts, or entertainment broadcasting; third-party traffic is restricted (emergency / disaster exceptions apply as provided by law)
- Stay within the bands, power, and identification rules of your certificate, station license, and the national plan; keep papers ready for inspection

VARC can help the community with training and procedural orientation; **state authorities** (provincial People’s Committees / the Radio Frequency Directorate under the current split of powers) issue official permissions.

### Quick comparison

| Path | Frequency license? | Main conditions | Fit for Meshtastic? |
| --- | --- | --- | --- |
| Exempt LPWAN / SRD | No *if* fully compliant | ≤25 mW ERP + very low duty cycle (1%/10%) | Hard for stock Meshtastic mesh |
| LPWAN above exemption | Yes | Frequency & equipment license | Possible if licensed |
| Amateur (ham) | Yes (certificate + station license) | Amateur bands, non-commercial purpose, licensed power | Possible for licensed operators; region/settings must match the license & plan |

---

## Useful references

**Meshtastic / community**

- [Getting Started with Meshtastic (Vietnam)](Getting-Started.en.md) — LongFast, Frequency Slot 4–23 (default 6), TX ≤ 14 dBm
- [`SG_923` / VN923 table, region limits & VN↔SG comparison](BANDS-FrequencySlots.en.md)
- [Frequency Slot Calculator](https://meshtastic.org/docs/overview/radio-settings/)
- [Meshtastic – LoRa Configuration](https://meshtastic.org/docs/configuration/radio/lora/)
- [Meshtastic – Region by country](https://meshtastic.org/docs/configuration/region-by-country/)
- [Radio Frequency Directorate (RFD)](https://rfd.gov.vn/)
- [VARC — website / blog](https://hamvn.com)
- [GitHub VARC-Vietnam](https://github.com/VARC-Vietnam)

**Vietnamese instruments (newest → oldest; see catalog table above)**

- [09/2026/VBHN-TT-BKHCN](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-09-2026-vbhn-tt-bkhcn-470351.htm) — Equipment / station inspection (25 Aug 2026)
- [23/VBHN-BTC](https://chinhphu.vn/?docid=214898&pageid=27160) (5 Aug 2025) · [19/VBHN-BTC](https://luatvietnam.vn/thue/van-ban-hop-nhat-19-vbhn-btc-230686-d5.html) (5 Sep 2022) — Spectrum fees
- [01/VBHN-BKHCN](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Van-ban-hop-nhat-01-VBHN-BKHCN-2025-Thong-tu-Danh-muc-thiet-bi-vo-tuyen-dien-duoc-mien-giay-phep-660171.aspx) — License-exempt devices (4 Jun 2025)
- [Circular 08/2021/TT-BTTTT (PDF)](https://datafiles.chinhphu.vn/cpp/files/vbpq/2021/10/08-btttt.signed.pdf) — Appendix 1 items 39/44/45; Appendices 3 & 19
- [37/2025/QĐ-TTg](https://congbao.chinhphu.vn/van-ban/quyet-dinh-so-37-2025-qd-ttg-46329/59232.htm) — Current spectrum plan · [05/VBHN-BTTTT](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-05-vbhn-btttt-37109.htm) — 2022 consolidation
- [36/VBHN-VPQH](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-36-vbhn-vpqh-41379.htm) — Law on Radio Frequencies (27 Dec 2023)
- [08/VBHN-BTTTT](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-08-vbhn-btttt-37604.htm) — Administrative sanctions (radio frequency) (20 Jul 2022)

---

## Contributing

Issues and pull requests that improve Vietnam network docs, lawful configuration guidance, or these READMEs are welcome. Before transmitting, confirm that your setup matches current Vietnamese law.
