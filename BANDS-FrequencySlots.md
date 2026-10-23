# Bảng tần số Meshtastic — `SG_923`

[English](BANDS-FrequencySlots.en.md) · [README](README.md) · [Bắt đầu](Getting-Started.md)

Region Meshtastic **`SG_923`**: **917.0 – 925.0 MHz** (Singapore firmware preset).

> Tần số tính theo preset mặc định **`LONG_FAST`** (bandwidth **250 kHz**), công thức firmware Meshtastic:  
> `freq = 917.0 + (bw/2000) + (slot × bw/1000)` MHz  
> Tra cứu / kiểm tra nhanh: [Frequency Slot Calculator](https://meshtastic.org/docs/overview/radio-settings/)

**Lưu ý:** Trong app / calculator, Frequency Slot thường bắt đầu từ **1** (= slot **0** trong bảng này). Slot **0** trong cấu hình đôi khi nghĩa là *tự động (hash theo tên kênh)*.

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

- **32** slot (`LONG_FAST` / 250 kHz trên `SG_923`)

Preset khác (125 / 500 kHz) sẽ đổi số slot và tần số — dùng [Frequency Slot Calculator](https://meshtastic.org/docs/overview/radio-settings/).

## So sánh giới hạn region Meshtastic với Việt Nam

Cột **duty cycle / công suất** của các region Meshtastic lấy từ [cấu hình LoRa chính thức](https://meshtastic.org/docs/configuration/radio/lora/). Đây là giới hạn firmware áp dụng; luật quốc gia có thể còn quy định khác (ví dụ FCC ở Mỹ không chỉ là duty cycle %).

**Quy đổi công suất nhanh:** 10 dBm ≈ 10 mW · **14 dBm ≈ 25 mW** (trần LPWAN VN) · 20 dBm = 100 mW · 27 dBm ≈ 500 mW · 30 dBm = 1 W

| Region / quy định | Băng (MHz) | Duty cycle (firmware / luật) | Trần công suất | Phù hợp mesh Meshtastic? |
| --- | --- | --- | --- | --- |
| **Việt Nam LPWAN (luật miễn GP)** | 433,05–434,79 / 920–923 | **1% đầu cuối / 10% gateway** | **≤ 25 mW ERP (~14 dBm)** | Khó — chưa có region `VN_*` chính thức |
| `EU_433` | 433–434 | **10%** | 10 dBm | Có thể, nhưng bị hạn chế |
| `EU_868` | 869,4–869,65 | **10%** | 27 dBm | Có thể; firmware tạm dừng TX khi chạm trần |
| `EU_866` | 865,6–867,6 | **2,5%** (10% với router) | 27 dBm | Chặt |
| `TH` (Thái Lan) | 920–925 | **10%** (firmware) | 27 dBm | Tương tự EU |
| `UA_433` | 433–434,7 | **10%** | 10 dBm | Tương tự `EU_433` |
| `US` | 902–928 | **100%*** | 30 dBm | Thuận lợi |
| `ANZ` | 915–928 | **100%*** | 30 dBm | Thuận lợi |
| `ANZ_433` | 433,05–434,79 | **100%*** | 14 dBm | Thuận lợi (công suất gần VN) |
| `KR` | 920–923 | **100%*** | 23 dBm | Thuận lợi |
| `JP` | 920,5–923,5 | **100%*** | 13 dBm | Thuận lợi (công suất thấp) |
| `SG_923` (firmware) | **917–925** | **100%*** | 20 dBm (~100 mW) | Firmware lỏng hơn luật SG |
| `MY_433` / `MY_919` | 433–435 / 919–924 | **100%*** | 20 / 27 dBm | Thuận lợi |
| `CN` | 470–510 | **100%*** | 19 dBm | Thuận lợi |
| `LORA_24` | 2400–2483,5 | **100%*** | 10 dBm | Thuận lợi (tầm ngắn) |

\*Trong bảng Meshtastic, **100%** nghĩa là firmware **không ép** giới hạn duty cycle. Luật địa phương vẫn có thể áp dụng quy tắc khác (nhảy tần, chiếm dụng kênh, v.v.).

### Điểm chính khi so sánh

1. **Công suất:** Trần ~14 dBm của Việt Nam gần `ANZ_433` / `JP`, thấp hơn US / `EU_868` / KR, cao hơn một chút so với `EU_433` (10 dBm). Công suất **không phải** điểm khác biệt lớn nhất so với EU.
2. **Duty cycle mới là khác biệt của VN:** nhiều region châu Á / Mỹ / ANZ = firmware 100%; EU / Thái = **10%** (Meshtastic vẫn chạy được); đầu cuối VN miễn phép = **1%** — chặt hơn EU và là lý do chính khiến region `VN_*` bị từ chối.
3. **EU là trường hợp giữa:** Meshtastic sống được với **10%** (tạm ngừng phát khi hết hạn mức). **1% trên client** của Việt Nam khó tương thích beacon + chuyển tiếp đa hop.
4. **Băng nghiệp dư (khác đường miễn phép):** các region `ITU3_70CM`… trong firmware cho phép tới 30 dBm / 100%, nhưng chỉ ở **licensed mode** (hô hiệu, không mã hóa). Tại Việt Nam vẫn cần chứng chỉ + giấy phép đài.

**Tóm lại:** Meshtastic miễn phép dễ nhất ở nơi luật/firmware cho phép airtime cao (US, ANZ, KR, MY…). EU/TH chặt hơn nhưng vẫn dùng được với 10%. LPWAN miễn phép Việt Nam có **airtime client 1%** — quá thấp so với mesh Meshtastic thông thường.

## So sánh khu vực: Việt Nam ↔ Singapore

| | Việt Nam (miễn GP) | Singapore (IMDA) | Meshtastic `SG_923` (firmware) |
| --- | --- | --- | --- |
| Băng tần | **918,4–923** (SRD) / **920–923** (LPWAN) MHz | **917–925** MHz | **917–925** MHz |
| Công suất LPWAN đầu cuối | ≤ **25 mW ERP** (~14 dBm) | ≤ **100 mW ERP** | Trần firmware **20 dBm** (~100 mW) |
| Duty cycle LPWAN | Đầu cuối ≤ **1%**; gateway ≤ **10%** | Đầu cuối ≤ **1%**; NAP ≤ **10%** | Firmware ghi **100%** (không ép 1%/10%) |
| Region Meshtastic chính thức | Chưa có `VN_*` | — | `SG_923` |

| Nguồn | Nội dung |
| --- | --- |
| [01/VBHN-BKHCN](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Van-ban-hop-nhat-01-VBHN-BKHCN-2025-Thong-tu-Danh-muc-thiet-bi-vo-tuyen-dien-duoc-mien-giay-phep-660171.aspx) / [TT 08/2021 PDF](https://datafiles.chinhphu.vn/cpp/files/vbpq/2021/10/08-btttt.signed.pdf) | VN: mục 44–45, Phụ lục 3 & 19 |
| [IMDA TS SRD](https://www.imda.gov.sg/-/media/imda/files/regulation-licensing-and-consultations/ict-standards/telecommunication-standards/radio-comms/imdatssrd.pdf) (Table 1, 30a–30d) | SG: 917–925 MHz; 30c LPWAN end ≤100 mW / ≤1%; 30b NAP ≤500 mW / ≤10% |
| [Meshtastic LoRa — `SG_923`](https://meshtastic.org/docs/configuration/radio/lora/) | Firmware: 917–925 MHz, 20 dBm, không ép duty cycle luật SG |

`SG_923` là region firmware cho Singapore — **không** phải băng miễn phép của Việt Nam. Dùng tại VN có thể phát ngoài **918,4–923 / 920–923 MHz** và không khớp trần công suất / duty cycle VN.

## Tham chiếu

- [Frequency Slot Calculator / Radio Settings](https://meshtastic.org/docs/overview/radio-settings/)
- [LoRa Configuration — Region `SG_923`](https://meshtastic.org/docs/configuration/radio/lora/)
- [IMDA TS SRD (Singapore)](https://www.imda.gov.sg/-/media/imda/files/regulation-licensing-and-consultations/ict-standards/telecommunication-standards/radio-comms/imdatssrd.pdf)
- [README — pháp lý VN](README.md)
