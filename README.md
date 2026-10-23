# Mạng lưới Meshtastic VARC Việt Nam

[English](README.en.md)

Kho lưu trữ này thuộc **VARC (Vietnam Amateur Radio Club / Câu lạc bộ Vô tuyến điện nghiệp dư Việt Nam)** — cộng đồng hỗ trợ kết nối node Meshtastic vào mạng lưới mesh tại Việt Nam.

## Meshtastic là gì?

[Meshtastic](https://meshtastic.org/) là dự án mã nguồn mở xây dựng mạng lưới liên lạc **phi tập trung, hoạt động ngoài lưới (off-grid)** bằng LoRa. Các thiết bị (node) tạo thành mạng mesh: tin nhắn, vị trí và dữ liệu cảm biến có thể được chuyển tiếp qua nhiều hop mà không phụ thuộc mạng di động hay Internet.

## Mạng Meshtastic VARC

VARC là tổ chức xã hội phi lợi nhuận của cộng đồng vô tuyến điện nghiệp dư Việt Nam, thành viên IARU (International Amateur Radio Union), với hô hiệu quốc gia thường dùng tiền tố **XV** / **3W**.

**Mạng lưới Meshtastic VARC** nhằm:

- Kết nối người dùng Meshtastic trong nước thành mạng mesh cộng đồng
- Chia sẻ hướng dẫn cấu hình, tần số và thực hành an toàn / hợp pháp
- Phối hợp với hoạt động vô tuyến điện nghiệp dư (đào tạo, nghiên cứu kỹ thuật, hỗ trợ cộng đồng khi cần)
- Tài liệu hóa cấu hình và tài nguyên cho mạng Việt Nam

> **Lưu ý:** Nội dung dưới đây mang tính tham khảo cộng đồng. Đây **không phải** tư vấn pháp lý. Người vận hành thiết bị phát sóng phải tự đối chiếu văn bản hiện hành và hướng dẫn của cơ quan quản lý (Cục Tần số vô tuyến điện / UBND cấp tỉnh theo phân cấp).

## Bắt đầu

Flash firmware và cấu hình node cho mesh tại Việt Nam: **[Getting-Started.md](Getting-Started.md)** — Region `SG_923`, LongFast, Frequency Slot **4–23** (mặc định **6**, 918–923 MHz), TX Power **≤ 14 dBm**.

Bảng tần số / so sánh region: [BANDS-FrequencySlots.md](BANDS-FrequencySlots.md).

---

## Pháp lý sử dụng Meshtastic tại Việt Nam

Việc phát sóng vô tuyến tại Việt Nam được điều chỉnh bởi **Luật Tần số vô tuyến điện** (Luật số 42/2009/QH12, sửa đổi bởi Luật số 09/2022/QH15 và các điều chỉnh liên quan; văn bản hợp nhất hiện hành: [**36/VBHN-VPQH**](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-36-vbhn-vpqh-41379.htm), ký xác thực **27/12/2023**).

Nguyên tắc chung: **phải có giấy phép sử dụng tần số vô tuyến điện**, trừ thiết bị thuộc danh mục **miễn giấy phép** và đáp ứng đủ điều kiện kỹ thuật / khai thác.

### Danh mục văn bản hợp nhất / khung pháp lý (mới → cũ theo ngày ký xác thực)

| Văn bản | Ký xác thực | Hiệu lực (theo công bố) | Vai trò với Meshtastic / tần số |
| --- | --- | --- | --- |
| [**09/2026/VBHN-TT-BKHCN**](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-09-2026-vbhn-tt-bkhcn-470351.htm) — Kiểm định thiết bị viễn thông, đài vô tuyến điện | 25/08/2026 | *(theo công bố Công báo)* | Kiểm định đài/thiết bị thuộc danh mục bắt buộc (nếu áp dụng) |
| [**23/VBHN-BTC**](https://chinhphu.vn/?docid=214898&pageid=27160) (2025) — Hợp nhất TT 265/2016/TT-BTC (cập nhật phí / lệ phí) | 05/08/2025 | *(theo sửa đổi trong văn bản; gồm TT 65/2025)* | Bản hợp nhất phí **mới hơn** 19/VBHN-BTC — ưu tiên tra cứu khi nộp phí |
| [**01/VBHN-BKHCN**](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Van-ban-hop-nhat-01-VBHN-BKHCN-2025-Thong-tu-Danh-muc-thiet-bi-vo-tuyen-dien-duoc-mien-giay-phep-660171.aspx) — Thiết bị miễn giấy phép sử dụng tần số | 04/06/2025 | 04/06/2025 | **Cốt lõi miễn phép LoRa/LPWAN/SRD** (hợp nhất TT 08/2021 + sửa đổi) |
| [**36/VBHN-VPQH**](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-36-vbhn-vpqh-41379.htm) — Luật Tần số vô tuyến điện | 27/12/2023 | 27/12/2023 | Khung luật: cấp phép, miễn phép, quyền–nghĩa vụ người dùng |
| [**19/VBHN-BTC**](https://luatvietnam.vn/thue/van-ban-hop-nhat-19-vbhn-btc-230686-d5.html) — Phí / lệ phí cấp phép & sử dụng tần số (hợp nhất TT 265/2016) | 05/09/2022 | 05/09/2022 | Biểu phí khi xin giấy phép (bản hợp nhất 2022) |
| [**08/VBHN-BTTTT**](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-08-vbhn-btttt-37604.htm) — Xử phạt VPHC (bưu chính, viễn thông, **tần số**, CNTT…) | 20/07/2022 | 20/07/2022 | Chế tài khi dùng tần số / thiết bị sai (gồm thiết bị miễn phép — Điều 64 NĐ gốc) |
| [**05/VBHN-BTTTT**](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-05-vbhn-btttt-37109.htm) — Quy hoạch phổ tần số quốc gia (hợp nhất) | 05/05/2022 | 05/05/2022 | Quy hoạch cũ (QD 71/2013 + sửa đổi). **Hiện hành:** [37/2025/QĐ-TTg](https://congbao.chinhphu.vn/van-ban/quyet-dinh-so-37-2025-qd-ttg-46329/59232.htm) (HL 20/11/2025) |

Với Meshtastic (LoRa mesh), thực tế có **hai hướng** thường được thảo luận:

### 1. Thiết bị miễn giấy phép (SRD / LPWAN)

Căn cứ chính:

| Văn bản | Nội dung liên quan |
| --- | --- |
| [Thông tư 08/2021/TT-BTTTT](https://datafiles.chinhphu.vn/cpp/files/vbpq/2021/10/08-btttt.signed.pdf) | Danh mục thiết bị vô tuyến được miễn giấy phép sử dụng tần số; điều kiện kỹ thuật và khai thác |
| [**01/VBHN-BKHCN**](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Van-ban-hop-nhat-01-VBHN-BKHCN-2025-Thong-tu-Danh-muc-thiet-bi-vo-tuyen-dien-duoc-mien-giay-phep-660171.aspx) (04/06/2025) | Văn bản hợp nhất hiện hành của TT 08/2021 và các sửa đổi |
| [Thông tư 01/2025/TT-BKHCN](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Van-ban-hop-nhat-01-VBHN-BKHCN-2025-Thong-tu-Danh-muc-thiet-bi-vo-tuyen-dien-duoc-mien-giay-phep-660171.aspx) | Sửa đổi, bổ sung phụ lục của Thông tư 08/2021 |

**Băng tần ~433 / ~920 MHz được miễn giấy phép** theo Phụ lục 1 (danh mục) và điều kiện kỹ thuật tương ứng:

| Mục (Phụ lục 1) | Băng tần | Loại thiết bị | Công suất tối đa (miễn GP) | Điều kiện khai thác | Phụ lục điều kiện |
| --- | --- | --- | --- | --- | --- |
| 39 | **433,05 – 434,79 MHz** | LPWAN | ≤ **25 mW ERP** | Gateway ≤ **10%** DC; đầu cuối ≤ **1%** DC | [Phụ lục 19](https://datafiles.chinhphu.vn/cpp/files/vbpq/2021/10/08-btttt.signed.pdf) |
| 44 | **918,4 – 923 MHz** | SRD mục đích chung | ≤ **25 mW ERP** | **LBT** hoặc duty cycle ≤ **1%** | [Phụ lục 3](https://datafiles.chinhphu.vn/cpp/files/vbpq/2021/10/08-btttt.signed.pdf) |
| 45 | **920 – 923 MHz** | LPWAN | ≤ **25 mW ERP** | Gateway ≤ **10%** DC; đầu cuối ≤ **1%** DC | [Phụ lục 19](https://datafiles.chinhphu.vn/cpp/files/vbpq/2021/10/08-btttt.signed.pdf) |

Bổ sung (cùng Thông tư 08/2021):

- Mục 43: **918,4 – 923 MHz** RFID ≤ 500 mW ERP (không phải lớp thiết bị Meshtastic thông thường)
- Vượt ngưỡng miễn phép (ví dụ LPWAN 433 MHz tới 100 mW ERP, hoặc 920–923 MHz tới 306 mW ERP) → cần **giấy phép sử dụng tần số và thiết bị** (Điều 4 Thông tư 08/2021)
- Thiết bị đa công suất / đa băng phải được **cố định** tham số tần số và công suất theo quy định khi sử dụng tại Việt Nam

So sánh region Meshtastic / `SG_923` / Singapore: xem [BANDS-FrequencySlots.md](BANDS-FrequencySlots.md).

### 2. Nghiệp vụ vô tuyến điện nghiệp dư (có chứng chỉ + giấy phép đài)

Nếu khai thác trên băng tần **nghiệp dư**, người dùng cần:

1. **Chứng chỉ vô tuyến điện nghiệp dư**, và  
2. **Giấy phép sử dụng tần số và thiết bị** cho đài vô tuyến điện nghiệp dư.

| Văn bản / quy hoạch | Vai trò |
| --- | --- |
| [Quyết định 37/2025/QĐ-TTg](https://congbao.chinhphu.vn/van-ban/quyet-dinh-so-37-2025-qd-ttg-46329/59232.htm) | **Quy hoạch phổ tần số vô tuyến điện quốc gia** (hiệu lực từ 20/11/2025). Trong dải ~70 cm, Việt Nam phân chia **Nghiệp dư** (thường là nghiệp vụ phụ) tại các đoạn **430–432**, **432–435**, **435–438**, **438–440 MHz** |
| [Nghị định 133/2025/NĐ-CP](https://rfd.gov.vn/tin-tuc/pages/van-ban-moi.aspx?ItemID=3329) | Từ **01/7/2025**, UBND cấp tỉnh thực hiện nhiều thủ tục cấp / gia hạn giấy phép đài nghiệp dư và công nhận tổ chức cấp chứng chỉ |
| [Thông tư 37/2026/TT-BKHCN](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Thong-tu-37-2026-TT-BKHCN-trinh-tu-thu-tuc-thi-cap-chung-chi-vo-tuyen-dien-nghiep-du-714522.aspx) | Chứng chỉ Hạng I / II / III; trình tự thi, cấp, thu hồi (hiệu lực từ **01/7/2026**) |
| [Thông tư 23/2024/TT-BTTTT](https://congbao.chinhphu.vn/van-ban/thong-tu-so-23-2024-tt-btttt-44060.htm) | Bãi bỏ [Quyết định 18/2008/QĐ-BTTTT](https://chinhphu.vn/default.aspx?docid=64638&pageid=27160) (quy định cũ về hoạt động nghiệp dư) kể từ **31/12/2024** |

Định hướng nghiệp dư (theo khung pháp lý truyền thống và quy hoạch hiện hành):

- Mục đích **tự đào tạo, nghiên cứu kỹ thuật, sở thích cá nhân**, **không vì lợi nhuận**
- Không phát thông tin thương mại, an ninh–quốc phòng, thời sự, phát thanh quảng bá; hạn chế chuyển thông tin hộ bên thứ ba (trừ tình huống khẩn cấp thiên tai, thảm họa theo quy định)
- Phải tuân thủ băng tần / công suất theo chứng chỉ, giấy phép và quy hoạch quốc gia; sẵn sàng xuất trình giấy tờ khi kiểm tra

VARC hỗ trợ cộng đồng về đào tạo và định hướng thủ tục; **cơ quan nhà nước** (UBND cấp tỉnh / Cục Tần số vô tuyến điện theo phân cấp) mới là nơi cấp phép chính thức.

### Tóm tắt nhanh

| Hướng | Cần giấy phép tần số? | Điều kiện chính | Phù hợp Meshtastic? |
| --- | --- | --- | --- |
| LPWAN / SRD miễn phép | Không *nếu* đủ điều kiện | ≤25 mW ERP + duty cycle rất thấp (1%/10%) | Khó với mesh Meshtastic tiêu chuẩn |
| LPWAN vượt ngưỡng miễn phép | Có | Giấy phép tần số & thiết bị | Có thể, nếu được cấp phép |
| Nghiệp dư (ham) | Có (chứng chỉ + giấy phép đài) | Đúng băng nghiệp dư, đúng mục đích, đúng công suất | Có thể với operator đã cấp phép; cấu hình region phải khớp giấy phép / quy hoạch |

---

## Tham chiếu hữu ích

**Meshtastic / cộng đồng**

- [Bắt đầu với Meshtastic (Việt Nam)](Getting-Started.md) — LongFast, Frequency Slot 4–23 (mặc định 6), TX ≤ 14 dBm
- [Bảng tần số `SG_923` / VN923, so sánh region & VN↔SG](BANDS-FrequencySlots.md)
- [Frequency Slot Calculator](https://meshtastic.org/docs/overview/radio-settings/)
- [Meshtastic – LoRa Configuration](https://meshtastic.org/docs/configuration/radio/lora/)
- [Meshtastic – Region by country](https://meshtastic.org/docs/configuration/region-by-country/)
- [Cục Tần số vô tuyến điện (RFD)](https://rfd.gov.vn/)
- [VARC — website / blog](https://hamvn.com)
- [GitHub VARC-Vietnam](https://github.com/VARC-Vietnam)

**Văn bản Việt Nam (mới → cũ; xem thêm bảng danh mục phía trên)**

- [09/2026/VBHN-TT-BKHCN](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-09-2026-vbhn-tt-bkhcn-470351.htm) — Kiểm định thiết bị / đài vô tuyến (25/08/2026)
- [23/VBHN-BTC](https://chinhphu.vn/?docid=214898&pageid=27160) (05/08/2025) · [19/VBHN-BTC](https://luatvietnam.vn/thue/van-ban-hop-nhat-19-vbhn-btc-230686-d5.html) (05/09/2022) — Phí / lệ phí tần số
- [01/VBHN-BKHCN](https://thuvienphapluat.vn/van-ban/Cong-nghe-thong-tin/Van-ban-hop-nhat-01-VBHN-BKHCN-2025-Thong-tu-Danh-muc-thiet-bi-vo-tuyen-dien-duoc-mien-giay-phep-660171.aspx) — Thiết bị miễn giấy phép (04/06/2025)
- [Thông tư 08/2021/TT-BTTTT (PDF)](https://datafiles.chinhphu.vn/cpp/files/vbpq/2021/10/08-btttt.signed.pdf) — Phụ lục 1 mục 39/44/45; Phụ lục 3 & 19
- [37/2025/QĐ-TTg](https://congbao.chinhphu.vn/van-ban/quyet-dinh-so-37-2025-qd-ttg-46329/59232.htm) — Quy hoạch phổ tần hiện hành · [05/VBHN-BTTTT](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-05-vbhn-btttt-37109.htm) — Hợp nhất 2022
- [36/VBHN-VPQH](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-36-vbhn-vpqh-41379.htm) — Luật Tần số vô tuyến điện (27/12/2023)
- [08/VBHN-BTTTT](https://congbao.chinhphu.vn/van-ban/van-ban-hop-nhat-so-08-vbhn-btttt-37604.htm) — Xử phạt VPHC lĩnh vực tần số (20/07/2022)

---

## Đóng góp

Issues và pull request liên quan tài liệu mạng Việt Nam, hướng dẫn cấu hình hợp pháp, hoặc cải thiện README đều được chào đón. Trước khi phát sóng, hãy xác nhận cấu hình của bạn phù hợp văn bản pháp luật hiện hành.
