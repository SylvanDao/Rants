# Phân tích và Đầu tư vào Flying Tulip (FT)

## I. Tổng quan về Sản phẩm và Tầm nhìn Kinh doanh (The Business)

Flying Tulip (FT), một sáng kiến mới từ Andre Cronje và đội ngũ của ông, đang đặt mục tiêu xây dựng một **sàn giao dịch DeFi full-stack**.

1. **Tầm nhìn Sản phẩm (Product Vision):** FT mong muốn trở thành một "siêu ứng dụng DeFi" (DeFi super app) hoàn chỉnh, bao gồm:
    
    - Các chức năng giao dịch cơ bản như giao dịch giao ngay (spot), hợp đồng tương lai vĩnh viễn (perps), và quyền chọn (options).
    - Các dịch vụ tài chính khác như cho vay (lending) và tạo ra lợi suất có cấu trúc (structured yield).
    - Các sản phẩm chuyên biệt như stablecoin riêng (ftUSD), thị trường cho vay delta-neutral, phái sinh delta-neutral, bảo hiểm, CLOB (Central Limit Order Book) on-chain, và AMM (Automated Market Maker) không cần cấp phép.
2. **Mục tiêu Kinh doanh:** FT đang cố gắng đối đầu trực tiếp với các gã khổng lồ DeFi hiện tại, những đơn vị có khả năng huy động vốn tốt hơn, doanh thu định kỳ mạnh mẽ và lợi thế mạng lưới đã ăn sâu. Mô hình gây quỹ của họ được thiết kế để duy trì hoạt động đủ lâu cho đến khi bộ sản phẩm tự tạo ra doanh thu.
    

## II. Phân tích Mô hình Gây quỹ và Căn chỉnh Lợi ích (The Radical Fundraising Model)

Mô hình gây quỹ của Flying Tulip được mô tả là một trong những mô hình độc đáo nhất từng thấy trong lĩnh vực crypto.

### A. Cơ chế Huy động Vốn

1. **Vốn Góp và Kho Bạc (Treasury):** Các nhà đầu tư đóng góp stablecoin, ETH, hoặc các tài sản sinh lời khác (ví dụ: stablecoin, BTC, ETH, SOL, AVAX). Số vốn này đi thẳng vào kho bạc (treasury) của giao thức.
2. **Sử dụng Vốn (Cash Cow Concept):** Thay vì chi tiêu trực tiếp số tiền huy động được như các dự án thông thường, FT sẽ triển khai vốn này vào các chiến lược DeFi rủi ro thấp để **kiếm lợi suất**. **Chính lợi suất này** mới là nguồn tài trợ cho các hoạt động ban đầu của giao thức và các khoản trợ cấp ban đầu.
3. **Chi phí Thực sự cho Nhà đầu tư VC:** Khoản "đầu tư" thực chất là **chi phí cơ hội** (opportunity cost)—lợi suất (~4% hàng năm) mà nhà đầu tư từ bỏ nếu họ tự gửi vốn vào DeFi.
![Flying tulip investment flow](https://substackcdn.com/image/fetch/$s_!KGlx!,w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc7ce3fc4-354c-4f2d-b59a-ef7d4a5210b7_6663x3019.png)
### B. Căn chỉnh Lợi ích và Trách nhiệm (Accountability and Alignment)

1. **Đội ngũ Phát triển:** Đội ngũ không nhận được token ngay từ đầu. **Mặt lợi nhuận của họ CHỈ đến từ một phần doanh thu của giao thức** (phí thực tế) được tạo ra bởi một sản phẩm hoạt động hiệu quả. Nếu giao thức không hoạt động và không thu hút người dùng, đội ngũ sẽ không nhận được gì. ![if the team has no tokens at TGE, how are they getting them?](https://substackcdn.com/image/fetch/$s_!w3Lp!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa55bfc63-b57c-489e-811e-a480be6b78b3_6118x2197.png)
2. **Lòng tin và Danh tiếng:** Mô hình này được xây dựng xung quanh sự cần thiết phải huy động một lượng lớn vốn, thường được neo giữ bởi một người hoặc đội ngũ chủ chốt có danh tiếng, ảnh hưởng và lòng tin, như Andre Cronje.

## III. Cơ chế và Tiện ích Token FT (Token Utility and Mechanism)

Token FT được thiết kế với cơ chế giảm phát (deflationary mechanics) ngay từ ngày đầu tiên.

### A. Sự Bảo đảm và Quyền chọn Vĩnh viễn (Perpetual Put Option)

1. **Được Hỗ trợ Toàn bộ:** Mọi token FT được phát hành cho nhà đầu tư đều được **hỗ trợ đầy đủ bởi tài sản thế chấp** (collateral) mà nhà đầu tư đóng góp.
2. **Perpetual Put Option (Quyền chọn Bán Vĩnh viễn):** Mỗi token FT đi kèm với một quyền chọn bán vĩnh viễn (perpetual put option). Điều này mang lại cho nhà đầu tư **quyền (nhưng không phải nghĩa vụ)** để bán lại token của họ bất cứ lúc nào để lấy lại vốn ban đầu. Quyền chọn này không có ngày hết hạn.
3. **Bảo vệ Giảm thiểu Rủi ro:** Về mặt lý trí, nhà đầu tư sẽ chỉ thực hiện quyền chọn bán nếu token được giao dịch dưới giá mua của họ. Cơ chế này bảo vệ nhà đầu tư khỏi rủi ro thua lỗ vốn ban đầu.

### B. Cơ chế Giảm phát và Quay lại Thị trường

Cơ chế giảm phát được củng cố bằng cả hành động đổi (redeem) và bán (sell) token.

1. **Thực hiện Quyền chọn (Exercising the Put/Redemption):**
    
    - Khi nhà đầu tư thực hiện quyền chọn bán, họ trả lại token và nhận lại vốn ban đầu.
    - **Token bị đốt cháy** (burned), làm giảm nguồn cung. ![Scenerio 2: Exercising the Put/Redemption](https://substackcdn.com/image/fetch/$s_!-nWa!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F34254439-bdbc-490e-8d3d-70bb82538cbe_5626x2605.png)
2. **Bán trên Thị trường Mở (Selling on Open Market):**
    
    - Nếu nhà đầu tư bán token trên thị trường mở (vì họ có lợi nhuận), **sự bảo vệ của quyền chọn bán sẽ biến mất** (vô hiệu). ![Scenerio 1: investors sell or transfer NFT](https://substackcdn.com/image/fetch/$s_!7Spl!,w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F04c9bae1-2615-4995-ad6d-7125d319af51_5462x2605.png)
    - Vốn ban đầu tương ứng với số token đó được giải phóng và được chuyển thẳng sang việc **mua lại và đốt** (buy and burn) thêm token từ thị trường.
    - Hành động mua lại và đốt này được sử dụng để bù đắp cho việc giảm giá do hành động bán và giảm sự biến động.
3. **Phân bổ Cung ứng (Supply Allocation):** 100% token được lưu hành (float) nằm trong tay nhà đầu tư ngay từ khi ra mắt, không có sự khan hiếm giả tạo hay phân bổ lớn cho đội ngũ.
    
4. **Tích hợp Doanh thu:** Doanh thu được tạo ra từ lợi suất kho bạc (yield) và sau này là phí từ bộ sản phẩm cốt lõi, sẽ được sử dụng để mua lại và đốt token FT. Đây là một động lực bổ sung cho nhu cầu mua vào và giảm nguồn cung.
    

## IV. Đánh giá Rủi ro và Bài học Đầu tư (Risks and Investment Lessons)

Flying Tulip là một thử nghiệm và không phải là một canh bạc không rủi ro.

### A. Rủi ro Cụ thể của Mô hình

1. **Rủi ro Thanh khoản (Liquidity Risk):**
    
    - Quyền chọn bán (PUT) là **tài sản cụ thể** (asset-specific): nếu nhà đầu tư đóng góp USDC, họ phải được trả bằng USDC.
    - Kho bạc phải duy trì tính thanh khoản cao cho từng loại tài sản và triển khai chúng vào các chiến lược thanh khoản cao (ví dụ: stablecoin trong Aave).
    - **Áp lực Chuộc lại:** Các vị thế stake có thể liên quan đến thời gian mở khóa (unbonding periods) hoặc hàng đợi rút tiền (withdrawal queues). Nếu có số lượng lớn các yêu cầu thực hiện quyền chọn bán (PUT) đồng thời, sự chậm trễ trong việc thanh toán có thể gây ra hoảng loạn và thêm bất ổn cho hệ thống, làm suy yếu sự bảo vệ giảm thiểu rủi ro đã hứa.
2. **Rủi ro Lợi suất:**
    
    - Lợi suất từ các chiến lược DeFi có thể trở nên **âm hoặc không đủ** để trang trải các yêu cầu chuộc lại quyền chọn bán. Trong trường hợp này, giao thức sẽ gánh chịu tổn thất.
3. **Chi phí Cơ hội (Stagnation Risk):**
    
    - Nếu giá FT duy trì gần mức ban đầu trong thời gian dài, các nhà đầu tư sẽ không thu được lợi nhuận tăng trưởng vốn (capital gains). Lợi nhuận của họ sẽ chỉ phản ánh những gì họ có thể kiếm được từ việc nắm giữ và sinh lời trực tiếp từ stablecoin. Điều này làm giảm động lực tham gia lâu dài.

### B. Bài học cho investor

1. **Ưu tiên Khả năng Thực thi Sản phẩm:** Sự thành công của mô hình FT hoàn toàn phụ thuộc vào khả năng của đội ngũ trong việc **quản lý kho bạc hiệu quả, duy trì lợi suất và quan trọng nhất là cung cấp một bộ sản phẩm cạnh tranh**.
2. **Căn chỉnh Lợi ích Mạnh mẽ:** Mô hình này là một sự thay đổi căn bản so với phương pháp "gọi vốn trước, tìm tiện ích sau". Cấu trúc này buộc đội ngũ phải cung cấp sản phẩm và căn chỉnh lợi ích sâu sắc giữa nhà đầu tư (được bảo vệ rủi ro giảm giá) và đội ngũ (chỉ thắng khi giao thức thắng).
3. **Tính thử nghiệm:** Mô hình này là một **thí nghiệm** mà ngành công nghiệp crypto rất cần. Nếu thành công, nó sẽ trở thành một khuôn mẫu (blueprint) mới cho các dự án đầy tham vọng. Các VC như Nascent đang hỗ trợ FT vì đây là loại hình đổi mới giúp hệ sinh thái trở nên trung thực và cạnh tranh hơn.

## Nguồn

- https://research.hazeflow.xyz/p/flying-tulip-using-yield-instead
- https://x.com/Lemniscap/status/1972711856646082599
- https://x.com/delitzer/status/1972783089865933149