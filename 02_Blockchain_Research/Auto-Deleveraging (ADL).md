https://x.com/0xdoug/status/1976850615621107743
Đây là các ghi chú bài học toàn diện về cơ chế Auto-Deleveraging (ADL) trong bối cảnh xây dựng sàn giao dịch Hợp đồng Vĩnh cửu (Perp DEX), tập trung vào các bài học về thiết kế kinh doanh và kỹ thuật được rút ra từ các nguồn đã cung cấp.

---

## Ghi chú Bài học về Cơ chế Thanh toán Solvency (Solvency Mechanism) cho Perp DEX: Auto-Deleveraging (ADL)

ADL là một cơ chế an toàn **(solvency safeguard)** được kích hoạt khi các đợt thanh lý dây chuyền (cascading liquidations) làm cạn kiệt quỹ bảo hiểm (insurance funds), buộc các vị thế đang có lợi nhuận phải đóng.

### I. Bài học về Thiết kế Kinh doanh (Learned Biz Design)

Các bài học quan trọng nhất đối với một nhà xây dựng Perp DEX liên quan đến bản chất cơ bản của thị trường phái sinh vĩnh cửu và sự cần thiết của các cơ chế an toàn hệ thống.

#### 1. Bản chất Zero-Sum và Mô phỏng (Zero-Sum Nature and Simulation)

- **Tính Zero-Sum Tuyệt đối:** Thị trường hợp đồng vĩnh cửu là **hoàn toàn zero sum**. Trong hệ thống này, giá trị không bao giờ được tạo ra hay bị phá hủy, giống như nguyên lý nhiệt động lực học.
- **Tiền mặt là cốt lõi:** Perps hoạt động trên một "đống tiền mặt nhàm chán khổng lồ" ("big boring pile of cash"). Thậm chí không có BTC thực để mất giá trị. ![Perp futures mechanics](https://pbs.twimg.com/media/G28vKubWQAAk6IJ?format=jpg&name=large)
- **Thế giới Mô phỏng:** Perps xây dựng một mô phỏng rất đẹp về thị trường giao ngay (underlying spot). Tuy nhiên, **tất cả chỉ là tưởng tượng** ("all imaginary") và ADL là khoảnh khắc người dùng chạm tới "rìa của mô phỏng" ("edge of the simulation"). ![edge of the simulation](https://pbs.twimg.com/media/G28vO5wWkAAWE9-?format=jpg&name=small)
#### 2. Vai trò của ADL như Cơ chế Bảo vệ Solvency

- **Bảo vệ Hệ thống:** ADL tồn tại để **bảo vệ hệ thống** ("protects system") chứ không phải bảo vệ các vị thế cá nhân của người dùng ("your bags").
- **Sự cần thiết:** ADL cần phải tồn tại ở một mức độ nào đó vì không sàn giao dịch nào có thể đảm bảo cung cấp một luồng người thua lỗ vô tận ở phía bên kia giao dịch.
- **Giống như Vượt Quá Công Suất:** Cơ chế này được ví như một chuyến bay bị đặt quá số lượng (overbooked airline flight). Nếu người mua (longs) hết tiền và không ai sẵn sàng tham gia để thế chỗ, hệ thống không còn lựa chọn nào khác ngoài việc buộc ít nhất một số người bán khống (shorts) phải đóng vị thế. ![there just isn’t enough liquidity in the book](https://pbs.twimg.com/media/G28vLzZXYAANBSU?format=jpg&name=small)
- **Lợi nhuận của Vault/Quỹ Bảo hiểm:** Dữ liệu cho thấy các vault (kho tiền) **thường xuyên kiếm được lợi nhuận về lâu dài** bằng cách hấp thụ các đợt thanh lý được chiết khấu. Trong sự kiện Hyperliquid ngày 11 tháng 10 năm 2025, vault đã kiếm được **40 triệu đô la** trong vòng chưa đầy một giờ. ![HLP Liquidator](https://pbs.twimg.com/media/G28vMG0W0AAWYUF?format=jpg&name=large)![HLP Liquidator](https://pbs.twimg.com/media/G28vMcHWoAAYtaa?format=jpg&name=large)
#### 3. Phản ứng và Phê phán về Tính Công bằng

- **Sự Phẫn nộ Tự nhiên:** Người dùng thường cảm thấy khó chịu vì ADL bị coi là không công bằng ("feels unfair") khi họ bị buộc phải thoát khỏi vị thế **ngay lúc đang thắng lớn nhất** ("winning the hardest").
- **Phân tích sự mất cân bằng:** Một số người tóm tắt rằng hệ thống được xây dựng để người dùng thua lỗ (the game is built for you to lose), vì người dùng có thể chịu mức lỗ tối đa (mất tất cả), trong khi sàn giao dịch có thể chọn dừng mức lợi nhuận tối đa (profit ceiling) của họ bất cứ lúc nào.
- **Phê bình về Thiết kế Rủi ro:** Các yếu tố gây ra vấn đề lớn bao gồm việc **cho phép quá nhiều đòn bẩy** (too much leverage) – đây là lỗi của sàn giao dịch. Ngoài ra, việc các sàn giao dịch không sẵn lòng đặt vốn của chính họ vào trước khi thực hiện lựa chọn cuối cùng (ADL) tạo ra sự mất cân bằng về động lực (incentive misalignment).

---

### II. Bài học về Thiết kế Kỹ thuật (Learned Tech Design)

Thiết kế kỹ thuật của ADL tập trung vào việc xác định và đóng các vị thế chiến thắng (winning positions) một cách có trật tự để tái lập khả năng thanh toán.

#### 1. Cơ chế Hoạt động

- **Đối tượng Mục tiêu:** Hệ thống ADL sẽ chọn các vị thế ở **phe chiến thắng** ("winning side") để đóng.
- **Nguyên tắc "Cá Voi Lớn Nhất Bị Đuổi về nhà":** ADL hoạt động bằng cách ưu tiên các "cá voi" (whales) có lợi nhuận cao và đòn bẩy lớn để buộc phải thoát lệnh. ![most profitable whales get sent home first](https://pbs.twimg.com/media/G28vNjYX0AAaQ68?format=jpg&name=large)

#### 2. Hệ thống Xếp hạng Ưu tiên ADL (ADL Priority Ranking System)

Hệ thống ADL thường chọn vị thế để đóng dựa trên **hệ thống xếp hạng** ("ranking system") có ba tiêu chí chính, được sử dụng để xác định vị thế nào nên được thanh lý trước:

1. **Lợi nhuận lớn nhất (most profit)**.
2. **Đòn bẩy (leverage)**.
3. **Quy mô (size)**.

Kết quả là, **những cá voi lớn nhất và có lợi nhuận cao nhất sẽ bị buộc phải đóng trước** ("the biggest, most profitable whales get sent home first").

#### 3. Biến thể Thực hiện (Implementation Variation)

Quá trình được sử dụng để chọn ai và đóng ở mức giá nào (close out price) **thay đổi rất nhiều giữa các sàn giao dịch** ("varies a lot between exchanges").