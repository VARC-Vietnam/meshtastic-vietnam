# Bắt đầu với Meshtastic tại Việt Nam

[English](Getting-Started.en.md) · [README](README.md) · [Bảng tần số](BANDS-FrequencySlots.md)

Hướng dẫn ngắn để flash firmware và cấu hình node tham gia mesh cộng đồng tại Việt Nam.

> Gắn **ăng-ten trước** khi cấp nguồn / phát sóng. Phát không ăng-ten có thể hỏng chip LoRa.

## Gợi ý cấu hình VARC (Việt Nam)

| Mục | Giá trị gợi ý |
| --- | --- |
| **Region** | `SG_923` (chưa có region `VN_*` chính thức) |
| **Modem Preset** | **LongFast** (`LONG_FAST`) |
| **Primary channel** | Kênh công cộng mặc định **LongFast** (tên `LongFast`, PSK mặc định) |
| **Frequency Slot** | **4 – 23** (tần số trung tâm trong **918 – 923 MHz** — cột VN923); **mặc định gợi ý: 6** |
| **TX Power** | **≤ 14 dBm** (~**25 mW**) — **không** để mặc định thiết bị |

Bảng slot đầy đủ: [BANDS-FrequencySlots.md](BANDS-FrequencySlots.md) · [Frequency Slot Calculator](https://meshtastic.org/docs/overview/radio-settings/)

> Trong một số app / calculator, Frequency Slot bắt đầu từ **1** (= slot **0** trong bảng). Hãy đối chiếu tần số (MHz) với cột VN923, không chỉ số slot thô.

> **TX Power:** Region `SG_923` cho phép firmware tới ~**20 dBm** (~100 mW). Giá trị **0** / mặc định trên thiết bị thường dùng trần region đó — **cao hơn** ngưỡng miễn phép VN (**≤ 25 mW ERP**). Nên chỉnh thủ công xuống **≤ 14 dBm**. Gain ăng-ten làm tăng ERP thực tế; ăng-ten có gain dương cần TX thấp hơn nữa.

---

## 1. Chuẩn bị phần cứng

1. Node LoRa hỗ trợ Meshtastic (ESP32 / nRF52 / …) + ăng-ten phù hợp ~915–925 MHz.
2. Cáp USB **truyền dữ liệu** (không chỉ sạc).
3. Máy tính hoặc điện thoại để flash / cấu hình.

## 2. Flash firmware

1. Mở [Meshtastic Web Flasher](https://flash.meshtastic.org/).
2. Chọn đúng mẫu thiết bị.
3. Flash firmware ổn định mới nhất theo [Getting Started](https://meshtastic.org/docs/getting-started/).
4. Nếu máy tính cần driver (ESP32): xem hướng dẫn trên trang Getting Started.

## 3. Kết nối app / client

Chọn một trong các cách:

- **Android** — [Meshtastic Android](https://meshtastic.org/docs/software/android/)
- **iOS / iPadOS** — [Meshtastic Apple](https://meshtastic.org/docs/software/apple/)
- **Web** — [client.meshtastic.org](https://client.meshtastic.org/)
- **CLI** — `pip3 install --upgrade meshtastic` ([Python CLI](https://meshtastic.org/docs/software/python/cli/))

Ghép nối Bluetooth hoặc USB Serial với thiết bị.

## 4. Cấu hình LoRa cho Việt Nam

Theo [Initial Configuration](https://meshtastic.org/docs/getting-started/initial-config/):

1. Mở **Settings → LoRa** (hoặc *Radio Configuration → LoRa*).
2. Đặt **Region** = **`SG_923`**.
3. Đặt **Modem Preset** = **`LONG_FAST`** (LongFast).
4. Đặt **Frequency Slot** trong khoảng **4 – 23** — **gợi ý mặc định: 6** (mọi node trong cùng mesh phải **cùng slot**).
5. Đặt **Transmit Power / TX Power** = **≤ 14 dBm** (không để `0` / mặc định thiết bị).
6. Giữ **Use Preset** bật (trừ khi bạn cố ý cấu hình modem tùy chỉnh).
7. Gửi / lưu cấu hình lên thiết bị.

### Ví dụ CLI

```bash
meshtastic --set lora.region SG_923
meshtastic --set lora.modem_preset LONG_FAST
meshtastic --set lora.channel_num 6
meshtastic --set lora.tx_power 14
```

`channel_num` trong CLI/app thường là **Frequency Slot** (1-based ở một số UI). Kiểm tra tần số thực tế trên màn hình thiết bị hoặc calculator; chọn giá trị tương ứng cột **VN923** trong [BANDS-FrequencySlots.md](BANDS-FrequencySlots.md).

`lora.tx_power` tính bằng **dBm**. Dùng **14** (hoặc thấp hơn) thay vì mặc định / `0`.

## 5. Kênh LongFast (public)

1. Mở cấu hình **Channels**.
2. Channel 0 (primary): tên **`LongFast`**, dùng khóa công cộng mặc định (PSK mặc định Meshtastic — thường `AQ==`).
3. Không đổi tên kênh primary nếu bạn muốn khớp mesh công cộng (đổi tên sẽ đổi hash slot khi Frequency Slot = 0 / tự động).
4. Khi đã **cố định Frequency Slot** (ví dụ **6**, trong khoảng 4–23), mọi node mesh phải dùng **cùng** region, LongFast, và **cùng slot**.

Xem thêm: [Joining your local mesh](https://meshtastic.org/docs/getting-started/joining-your-local-mesh/).

## 6. Kiểm tra

1. Đặt **Node name** / short name dễ nhận.
2. Gửi tin nhắn thử trên kênh LongFast.
3. Xác nhận tần số / slot trên thiết bị khớp VN923 (918–923 MHz).
4. Nếu không thấy node khác: hỏi cộng đồng VARC slot đang dùng ở khu vực bạn, rồi chỉnh cùng slot.

## Lưu ý pháp lý (tóm tắt)

- Region `SG_923` chỉ là preset firmware gần nhất — xem [BANDS-FrequencySlots.md](BANDS-FrequencySlots.md) và [README](README.md).
- Miễn phép tại VN có trần công suất / duty cycle chặt; mesh Meshtastic thông thường khó khớp đủ điều kiện miễn phép. Người vận hành tự chịu trách nhiệm tuân thủ pháp luật.

## Tham chiếu

- [Getting Started](https://meshtastic.org/docs/getting-started/)
- [Initial Configuration](https://meshtastic.org/docs/getting-started/initial-config/)
- [Joining your local mesh](https://meshtastic.org/docs/getting-started/joining-your-local-mesh/)
- [Web Flasher](https://flash.meshtastic.org/)
- [BANDS-FrequencySlots.md](BANDS-FrequencySlots.md)
- [README — pháp lý](README.md)
