---
artifact: 02 — JTBD Project Analysis
bai-tap: Lab 2 — Dùng JTBD để soi lại dự án nhóm
format: Theo nhóm dự án → share trong bàn → chốt hypothesis cuối
time: 25 phút trên lớp
nop-cuoi: Có — đây là file nộp cuối của Lab 2
companion-reference: Strategyn_JTBD_Playbook.pdf (giảng viên gửi kèm)
---

# Lab 2 — JTBD Project Analysis / Dùng JTBD để soi lại dự án nhóm

**Tên dự án / sản phẩm:** AI Hotel Deal Advisor — Trợ lý AI tư vấn du lịch và hỗ trợ đặt phòng

---

## Bước 0 — Khoanh đúng 1 lát cắt của dự án
- **Dự án của nhóm tôi là:** AI Hotel Deal Advisor — Hệ thống AI hỗ trợ người dùng tìm phòng khách sạn phù hợp theo địa điểm, khoảng cách, ngân sách và nhu cầu cá nhân; đồng thời hiển thị ảnh phòng, địa chỉ cụ thể, thông tin phòng, giá gốc, phí dịch vụ, tổng giá dự kiến và hỗ trợ đặt.
- **Lát cắt tôi chọn để phân tích hôm nay là:** Người đi du lịch hoặc đi công tác tự túc, cần tìm và chốt phòng gấp trong vòng 24-48 giờ trước chuyến đi, đòi hỏi phòng phải tối ưu sát theo nhu cầu cá nhân (gần trung tâm/địa điểm họp, có bồn tắm, có bữa sáng, giá trọn gói không phát sinh phí ẩn).
- **Vì sao tôi chọn lát cắt này:**  
  > Đây là nhóm người dùng có áp lực thời gian cao, workflow tìm kiếm cực kỳ phức tạp vì phải cân đo đong đếm quá nhiều bộ lọc (vị trí, tổng chi phí thực tế sau thuế phí, chất lượng thực tế qua hình ảnh). Đây chính là nơi nỗi đau "so sánh và tính toán" lặp đi lặp lại nhiều nhất gây tốn thời gian.

---

## Bước 1 — Viết `Project Snapshot`

### Tóm tắt dự án trong 3 dòng

1. **Nhóm tôi đang nghĩ mình đang giải quyết vấn đề gì?**  
   > Người dùng tốn quá nhiều thời gian lướt qua lại giữa nhiều ứng dụng đặt phòng để so sánh giá, dễ bị đánh lừa bởi giá ảo chưa cộng thuế phí, và mệt mỏi khi phải tự lọc thủ công hàng trăm khách sạn để tìm ra nơi đúng ý.

2. **Người dùng chính hiện nhóm đang nhắm tới là ai?**  
   > Khách du lịch tự túc, người đi công tác, có hành vi lên kế hoạch kỹ càng nhưng muốn tối ưu hóa thời gian lựa chọn và ngân sách.

3. **Hiện tại người dùng đó đang giải quyết vấn đề này bằng cách nào?**  
   > Mở cùng lúc 3-4 tab (Agoda, Booking, Google Maps); gõ tìm kiếm; bấm vào từng phòng xem ảnh; tự cộng nhẩm thuế phí ẩn ở bước thanh toán cuối; rồi chép ra Excel để so sánh.

---

## Bước 2 — Viết `Market Context`

### Trả lời 4 câu ngắn

1. **Ai đang gặp vấn đề này?**  
   > Những người tự lên lịch trình du lịch/công tác và chịu trách nhiệm chi trả tài chính cho chuyến đi của mình.

2. **Vấn đề xuất hiện trong hoàn cảnh nào?**  
   > Trước chuyến đi từ vài ngày đến vài tuần; thông tin phòng ốc rải rác, giá cả biến động theo giờ, các app lữ hành cố tình ẩn bớt phụ phí dịch vụ để kích cầu khiến việc so sánh giá gốc trở nên khó khăn.

3. **Hiện tại họ đang dùng giải pháp thay thế nào?**  
   > Tự dò tay trên OTA (Agoda/Booking), đọc review trên nhóm Facebook/TikTok, hỏi đại lý du lịch, hoặc nhờ ChatGPT tư vấn lịch trình chung chung nhưng ChatGPT lại không hiển thị được phòng thật, ảnh thật và giá thời gian thực.

4. **Vì sao đây là thời điểm đáng giải?**  
   > Xu hướng du lịch cá nhân hóa (Hyper-personalization) bùng nổ; người tiêu dùng ngày càng nhạy cảm với các loại "phí ẩn" trên app đặt phòng. Đồng thời, công nghệ AI kết hợp RAG và Function Calling đã cho phép đọc dữ liệu thời gian thực (Real-time giá phòng, API đặt phòng) và xuất ra cả hình ảnh trực quan một cách chính xác

### Tóm tắt market context trong 3-4 dòng

> Người đi du lịch tự túc đang bị quá tải thông tin trước hàng loạt phòng ốc phân mảnh và các chiêu trò "ẩn phụ phí" của các nền tảng OTA hiện tại. Họ phải tự chắp vá bằng cách dò tay, so sánh thủ công rất mất thời gian. Bây giờ là thời điểm đáng giải vì AI thế hệ mới đã đủ mạnh để tổng hợp toàn bộ thông tin (từ vị trí, ảnh phòng đến tổng giá cuối gồm cả phí dịch vụ) thành một câu trả lời may đo duy nhất theo nhu cầu.
---

## Bước 3 — Xác định `Job Executor`

- **Job executor của dự án này là:** Người trực tiếp lên kế hoạch và tự đặt phòng cho chuyến đi (không phải công ty lữ hành, không phải chủ khách sạn).
- **Vì sao tôi tin đây là người trực tiếp "thuê" giải pháp để làm job:**  
  > Họ là người trực tiếp bỏ tiền túi (hoặc ngân sách công tác được duyệt), trực tiếp điền thông tin nhu cầu, đọc thông tin phòng, xem hình ảnh và thực hiện hành vi bấm nút thanh toán để hoàn thành việc tìm chỗ ở.

---

## Bước 4 — Viết `Core JTBD`

### Bản nháp 1

**Core JTBD bản nháp:**  
> Đặt phòng khách sạn giá rẻ bằng trợ lý AI thông minh. (Còn nhét solution: "trợ lý AI")

### Gạch bỏ từ solution nếu có

- Các từ solution tôi đang lỡ nhét vào câu: Các từ solution tôi đang lỡ nhét vào câu: "trợ lý AI", "thông minh".

### Bản chốt

**Core JTBD cuối cùng:**  
> Chọn và chốt được nơi lưu trú phù hợp nhất với ngân sách thực tế và sở thích cá nhân tại một điểm đến, trong thời gian ngắn nhất.

---

## Bước 5 — Viết 3 `Job Stories`

### Bảng 3 job stories

| # | Trigger / When | Motivation / I want to | Outcome / so I can | Điều story này cho thấy |
|---|---|---|---|---|
| JS1 | Khi tôi cần tìm phòng gần địa điểm tổ chức hội nghị trong bán kính 1km với ngân sách dưới 1 triệu/đêm | Biết ngay danh sách phòng đáp ứng đúng tiêu chí kèm địa chỉ cụ thể và ảnh thực tế | Chốt nhanh mà không phải bật bản đồ đối chiếu thủ công từng khách sạn | Pain ở bước lọc vị trí kết hợp ngân sách dưới áp lực thông tin. |
| JS2 | Khi tôi nhìn thấy một phòng có giá hiển thị rất rẻ trên danh sách | Nhìn thấy ngay mức tổng giá dự kiến cuối cùng bao gồm cả phí dịch vụ và thuế | Quyết định chính xác có nên chọn hay không, tránh bị hụt hẫng ở bước thanh toán | Pain ở bước minh bạch tài chính (so sánh chi phí thực tế). |
| JS3 | Khi tôi đi du lịch gia đình có con nhỏ và cần phòng không hút thuốc, có rào chắn ban công | Đưa ra yêu cầu bằng ngôn ngữ tự nhiên và AI lọc ra đúng các phòng có đặc điểm đó | Yên tâm đặt phòng mà không cần đọc hết hàng trăm bình luận review để tự kiểm tra | Pain ở bước cá nhân hóa sâu theo nhu cầu đặc thù. |

---

## Bước 6 — Liệt kê `Current Alternatives`

### Bảng alternatives

| Alternative hiện tại | User đang thuê nó để làm gì? | Nó làm tốt gì? | Nó fail ở đâu? | Switching cost hiện tại cao hay thấp? |
|---|---|---|---|---|
| Alt 1 | Các ứng dụng OTA (Agoda, Booking.com) | Tìm kiếm, xem phòng và đặt phòng trực tuyến. | Kho dữ liệu khổng lồ, thanh toán an toàn, giao diện quen thuộc. | Hay giấu phí dịch vụ/thuế ở trang ngoài; bộ lọc cứng nhắc, phải bấm vào từng phòng mới thấy đầy đủ ảnh và chi tiết. | Thấp (Chỉ cần tải app hoặc vào web miễn phí). |
| Alt 2 | ChatGPT / Claude (bản Web thường) | Hỏi gợi ý khách sạn hoặc khu vực nên ở khi đi du lịch. | Hiểu ngôn ngữ tự nhiên rất tốt, tư vấn thân thiện. | Không có dữ liệu phòng trống thời gian thực; không hiển thị được ảnh phòng thật; không biết giá thực tế hôm nay và không hỗ trợ đặt. | Thấp |

### Kết luận nhanh

**Nếu project của tôi biến mất hôm nay, user nhiều khả năng sẽ quay về:**  
> Nếu project của tôi biến mất hôm nay, user nhiều khả năng sẽ quay về: Tiếp tục lướt mệt mỏi trên Agoda/Booking, tự bật Google Maps đo khoảng cách và tự bấm vào bước cuối cùng của từng phòng để xem tổng giá thật.

---

## Bước 7 — Điền `JTBD Lite Map`

### Bảng JTBD Lite Map

| Step | Trong workflow này user đang cố làm gì? | Hôm nay họ đang dùng gì? | Friction / pain hiện tại | Mức đau |
|---|---|---|---|---|
| Define | Xác định khu vực muốn ở, khoảng giá chấp nhận được và các tiện ích bắt buộc. | Tự nghĩ, thảo luận với bạn đi cùng. | Mơ hồ về địa phương mới, không rõ khu nào tiện đi lại. | Med |
| Locate | Tìm kiếm danh sách các khách sạn nằm trong khu vực mục tiêu. | Gõ tìm kiếm trên Agoda, Booking, Google Maps. | Quá nhiều kết quả rác hoặc quảng cáo tài trợ che mất phòng tốt. | Med |
| Prepare | So sánh chi tiết thông tin phòng, địa chỉ, ảnh, giá gốc và tổng giá sau thuế phí. | Bấm vào từng phòng, lướt kho ảnh, bấm thử vào bước thanh toán để xem phí dịch vụ. | Cực kỳ tốn giờ. Phải mở hàng chục tab để so sánh tổng giá thực tế và xem ảnh phòng. | High |
| Confirm | Xác nhận lại phòng này có đúng các tiêu chuẩn cá nhân không (ví dụ: giờ check-in muộn, có ăn sáng). | Đọc phần mô tả nhỏ (Fine print) và phần review của khách cũ. | Thông tin chữ nhỏ dễ bị bỏ sót, dễ gặp rủi ro khi đến nơi. | Med |
| Execute | Nhập thông tin cá nhân và tiến hành đặt phòng. | Điền form trên OTA, nhập thẻ tín dụng. | Phải nhập đi nhập lại thông tin nếu đặt nhiều phòng ở nhiều nơi. |Low |
| Monitor | Kiểm tra trạng thái xác nhận đặt phòng thành công từ khách sạn. | Chờ email xác nhận, kiểm tra app. | Thỉnh thoảng lo lắng không biết khách sạn đã thực sự nhận đơn chưa. | Low |
| Modify | Thay đổi ngày đặt hoặc hủy phòng nếu lịch trình du lịch thay đổi. | Vào mục quản lý đơn hàng của OTA để bấm hủy/đổi. | Một số phòng không cho hủy free, chính sách lằng nhằng khó đọc. | Med |
| Conclude | Check-in, trải nghiệm phòng và thanh toán nốt các chi phí tại chỗ (nếu có). | Xuất trình voucher điện tử tại quầy lễ tân. | Đôi khi bị phụ thu những khoản không rõ ràng từ trước. | Med |

### Chốt 2 bước đau nhất

**Bước đau nhất #1:** Prepare — Tổng hợp, đối chiếu ảnh phòng, địa chỉ cụ thể và tính toán "Tổng giá dự kiến cuối cùng" (Giá gốc + thuế phí).  
**Bước đau nhất #2:** Confirm — Kiểm tra các yêu cầu cá nhân tinh tế (khoảng cách thực tế, nhu cầu đặc thù) xem có khớp với khách sạn không.

**Vì sao đây là nơi đáng chú ý nhất:**  
> Bước Prepare là bước tốn nhiều năng lượng tinh thần nhất của user. Người dùng ghét cảm giác bị "lừa" khi thấy giá hiển thị bên ngoài rất rẻ nhưng bấm vào thanh toán lại đội lên rất cao do phí dịch vụ. Việc AI tính toán minh bạch tổng giá ngay từ giao diện tư vấn đầu tiên sẽ giải quyết triệt để friction này.

---

## Bước 8 — Chỉ ra `AI Leverage Point`

### Bảng leverage point

| Step | AI nên giúp bằng cách nào? | Vì sao AI hợp ở đây? | Rủi ro chính nếu dùng AI |
|---|---|---|---|
| Prepare | Đọc yêu cầu tự nhiên của user -> Trích xuất dữ liệu API thực tế -> Hiển thị ngay một thẻ thông tin đầy đủ: [Ảnh phòng trực quan] + [Địa chỉ cụ thể] + [Thông tin phòng rõ ràng] + [Bảng giá minh bạch: Giá gốc + Phí dịch vụ = Tổng giá dự kiến]. | Đây là bài toán tổng hợp dữ liệu đa nguồn (Multi-source aggregation) và biểu diễn trực quan — AI làm việc này nhanh gấp hàng trăm lần con người tự click xem từng tab. | Dữ liệu giá hoặc ảnh phòng từ API bị chậm/lệch so với thực tế của khách sạn tại giây đó. |
| Confirm | Đóng vai trò chuyên gia phân tích review, đối chiếu nhanh các chính sách ngầm hoặc bộ lọc ngách (ví dụ: "Phòng này ban công có an toàn cho trẻ em không?"). | AI có khả năng đọc hiểu ngữ cảnh từ hàng ngàn dòng text review và mô tả của khách sạn để rút ra kết luận chuẩn xác cho user. | AI hiểu sai ngữ cảnh review (ví dụ review khen mang tính mỉa mai). |

### Kết luận nhanh

**AI leverage point quan trọng nhất của dự án tôi là:**  
> Bước Prepare — Trích xuất và hiển thị minh bạch toàn bộ thông tin phòng, ảnh phòng và cấu trúc tổng chi phí thực tế theo nhu cầu thực thời gian thực.

**Vì sao không phải ở bước khác:**  
> Các bước như Execute (thanh toán) hay Modify (hủy phòng) chỉ cần cổng thanh toán và logic hệ thống CRUD thông thường (automation thường), dùng AI tạo sinh ở đó không mang lại giá trị gia tăng lớn và dễ gây lỗi bảo mật giao dịch.

---

## Bước 9 — Viết `Product Hypothesis`

### Bản hypothesis của tôi

> Nếu chúng ta giúp người đi du lịch tự túc làm việc so sánh và chuẩn bị thông tin đặt phòng tốt hơn ở bước Prepare, bằng cách để AI Hotel Deal Advisor tự động tổng hợp thông tin, hiển thị ảnh phòng trực quan và bóc tách minh bạch Tổng giá cuối (Giá gốc + Phí dịch vụ) theo thời gian thực, thì họ sẽ chuyển từ việc mở nhiều tab OTA dò tay thủ công sang AI Hotel Deal Advisor, vì nó giúp loại bỏ hoàn toàn các loại phí ẩn, hiển thị toàn bộ bối cảnh phòng kèm ảnh chỉ trong một câu lệnh chat duy nhất, nhanh hơn và minh bạch hơn.

### Tín hiệu sớm nếu hypothesis này đúng

1. Người dùng thực hiện hành vi bấm vào nút "Hỗ trợ đặt" (Click-through rate đến luồng book phòng) cao ngay từ những gợi ý đầu tiên của AI mà không cần yêu cầu AI đổi phương án khác quá nhiều lần.
2. Tỷ lệ người dùng hỏi các câu hỏi kiểm tra về "chi phí phát sinh" giảm xuống, chứng tỏ bảng tổng giá dự kiến hiển thị ban đầu đã đủ độ tin cậy.

---

## Bước 10 — Liệt kê `Assumptions to Validate`

### Bảng assumptions

| Assumption | Vì sao assumption này rủi ro? | Tôi đang có bằng chứng gì? | Cần validate bằng cách nào tiếp theo? |
|---|---|---|---|
| A1: Người dùng coi "Phí ẩn/Thuế phí hiện muộn" là nỗi đau lớn nhất khiến họ mất thời gian ở bước Prepare. | Nếu họ không quan tâm đến việc lệch giá vài chục nghìn, họ sẽ không có động lực đổi công cụ. | Các bài báo cáo thị trường du lịch lữ hành cho thấy 70% người dùng bỏ giỏ hàng ở bước cuối vì phí ẩn xuất hiện đột ngột. | Khảo sát nhanh (Survey) hoặc phỏng vấn 10 người hay đi du lịch tự túc để xem họ có ức chế với phí ẩn không. |
| A2: Hệ thống gọi được API hiển thị ảnh phòng và bảng giá gốc + phí dịch vụ chính xác theo thời gian thực. | Nếu thông tin giá AI đưa ra lệch so với giá lúc thanh toán thật, user sẽ mất hoàn toàn lòng tin và rời bỏ app ngay. | Chưa có dữ liệu thực tế, phụ thuộc vào chất lượng kết nối API với đối tác cung cấp dữ liệu khách sạn. | Thử nghiệm kết nối kỹ thuật (Technical Spike/Prototype) với một bên cung cấp API dữ liệu khách sạn lớn để đo độ trễ và độ chính xác của dữ liệu. |
| A3: Người dùng dám bấm "Đặt phòng" thông qua một giao diện Trợ lý AI. | Nếu họ sợ hệ thống AI không an toàn bằng các ông lớn OTA, họ chỉ dùng để tham khảo rồi lại về Agoda đặt. | Khách hàng thế hệ mới (Gen Z/Millennials) rất chuộng sự tiện lợi, sẵn sàng mua sắm qua chatbot nếu luồng thanh toán được chuyển hướng đến bên thứ ba uy tín. | Thiết kế bước "Hỗ trợ đặt" dưới dạng chuyển hướng (deep-link) sang trang đặt phòng chính thức của đối tác hoặc hiển thị rõ đối tác bảo mật cổng thanh toán, sau đó đo tỷ lệ chuyển đổi đơn hàng. |

### Assumption nguy hiểm nhất nếu tôi đang sai

> A2 — Nếu hệ thống AI hiển thị sai lệch thông tin phòng, ảnh phòng không khớp hoặc tổng giá dự kiến bị sai so với thực tế khi đặt, lý do tồn tại của sản phẩm sụp đổ hoàn toàn vì nó không còn đạt được tiêu chí "minh bạch và nhanh chóng".

---

## Bước 11 — Share trong bàn (3')

### Ghi nhanh sau khi nghe bàn phản biện

| Ý phản biện tôi nghe được | Nó chạm vào phần nào? | Tôi sẽ giữ / sửa gì? |
|---|---|---|
| "Các app lớn như Agoda giờ cũng có AI tư vấn hoặc hiển thị giá gồm thuế rồi, app mình cạnh tranh thế nào?" | Current Alternatives + Hypothesis | Sửa/Làm rõ: Agoda chỉ hiển thị sản phẩm của chính họ và thuật toán luôn ưu tiên các phòng chạy quảng cáo (sponsored). AI của nhóm sẽ định vị là "Advisor độc lập", có thể so sánh chéo giá giữa các nguồn cung cấp khác nhau để tìm ra deal thực sự tốt nhất cho user. |
| "Nhu cầu xem ảnh phòng rất cao, nếu chat chỉ ra text thì không ai thèm đọc." | AI Leverage Point | Giữ nguyên & Nhấn mạnh: Thẻ thông tin trả về của AI bắt buộc phải có cấu trúc UI Rich Component (hiển thị slide ảnh phòng trực quan, bản đồ mini), tuyệt đối không trả về một khối văn bản text thuần túy. |

---

## Bước 12 — Chốt version cuối sau thảo luận

### Sau khi nghe phản biện, tôi thay đổi gì?

- [x] Giữ nguyên `job executor`
- [x] Giữ nguyên `core JTBD`
- [x] Giữ nguyên `AI leverage point`
- [x] Sửa `product hypothesis`

### Vì sao tôi giữ / sửa?

> Phản biện trong bàn giúp nhóm nhận ra nếu chỉ làm một chatbot trả về text thông thường thì sẽ thua hoàn toàn các app OTA truyền thống ở trải nghiệm thị giác (hình ảnh phòng là yếu tố quyết định hành vi đặt). Vì vậy, nhóm quyết định giữ nguyên cấu trúc leverage point nhưng sửa đổi cách thức hiện thực hóa hypothesis: Phải bán giải pháp dưới dạng giao diện thẻ thông tin trực quan (Rich UI) kết hợp sức mạnh phân tích của AI.

### Version cuối cùng tôi nộp

**Job executor:**  
> Người đi du lịch hoặc đi công tác tự túc, tự lên kế hoạch và chi trả chi phí.

**Core JTBD:**  
> Chọn và chốt được nơi lưu trú phù hợp nhất với ngân sách thực tế và sở thích cá nhân tại một điểm đến, trong thời gian ngắn nhất.

**2 bước đau nhất trong workflow:**  
> Prepare (Đối chiếu ảnh phòng, vị trí, giá gốc và tổng chi phí cuối) và Confirm (Xác thực nhu cầu ngách/tiện ích cá nhân đặc thù).

**AI leverage point chính:**  
> Prepare — Tự động tổng hợp dữ liệu thời gian thực để xuất ra thẻ thông tin trực quan đầy đủ gồm ảnh phòng, địa chỉ cụ thể và bảng bóc tách chi phí minh bạch (Giá gốc + Phí dịch vụ = Tổng giá dự kiến).

**Product hypothesis:**  
> Nếu chúng ta giúp người đi du lịch tự túc làm việc so sánh, chuẩn bị thông tin đặt phòng tốt hơn ở bước Prepare, bằng cách sử dụng AI Hotel Deal Advisor để tự động trích xuất dữ liệu, hiển thị hình ảnh trực quan và bóc tách minh bạch tổng chi phí (không phí ẩn), thì họ sẽ chuyển từ việc mở nhiều tab OTA dò tay sang AI Hotel Deal Advisor, vì nó cung cấp câu trả lời trọn gói, trực quan và trung thực chỉ trong một giao diện duy nhất.

**Assumption cần validate đầu tiên:**  
> A2 — Khả năng lấy và hiển thị dữ liệu phòng (ảnh, thông tin, bảng giá trọn gói) chính xác, đồng bộ theo thời gian thực từ các nguồn API du lịch.

---

## Checklist trước khi nộp

- [x] Tôi đã khoanh đúng 1 lát cắt cụ thể của dự án.
- [x] Tôi đã phân biệt được `job executor` với buyer / influencer.
- [x] `Core JTBD` của tôi không nhét solution vào câu.
- [x] Tôi đã viết đủ 3 `job stories`.
- [x] Tôi đã điền `JTBD lite map` và khoanh ra 2 bước đau nhất.
- [x] Tôi đã chỉ ra `AI leverage point` thay vì nhảy thẳng vào feature list.
- [x] Tôi đã ghi rõ `assumptions to validate`.
- [x] Tôi đã sửa version cuối sau khi share trong bàn.

---

## Nếu còn thời gian / làm về nhà

- Phỏng vấn nhanh 1 người dùng thật để kiểm xem `job story` nào là sát nhất.
- So sánh `current alternatives` với project của nhóm theo 3 tiêu chí: nhanh hơn, rẻ hơn, tin hơn.
- Tự hỏi lại một câu khó: **nếu không dùng AI, project này còn tạo giá trị không?**
- Nếu câu trả lời là "không", hãy xem lại liệu nhóm đang giải **job thật** hay chỉ đang tìm chỗ để nhét AI.
