# 02 — Case Comparison

## So sánh 2 case

| Trường | Case thành công / tín hiệu tốt | Case cảnh báo / thất bại |
|---|---|---|
| Case | Morgan Stanley | Klarna |
| AI được dùng trong workflow nào? | Wealth management advisor hỏi đáp tri thức nội bộ để chuẩn bị tư vấn khách hàng | Customer support AI xử lý chat hỗ trợ và chuyển case phức tạp |
| Người dùng chính là ai? | Financial advisors trong môi trường có yêu cầu trust rất cao | Khách hàng cuối và đội support |
| Họ đo metric gì? | Adoption cao trong môi trường rủi ro cao; expert feedback loop; compliance controls; trust architecture | Khoảng 2,3 triệu chat; khoảng 2/3 tổng chat; thời gian xử lý từ 11 phút xuống dưới 2 phút; hiệu quả tương đương khoảng 700 FTE |
| Metric đó chứng minh được gì? | Nếu AI có guardrail, eval và expert review tốt thì adoption vẫn xảy ra ở workflow nhạy cảm | AI có thể tạo productivity gain và cost efficiency rất lớn ở workflow lặp lại |
| Metric đó chưa chứng minh được gì? | Chưa chứng minh đầy đủ business outcome cuối cùng như retention hoặc NPS của client | Chưa chứng minh được chất lượng bền vững, complaint rate, trust dài hạn hoặc khả năng xử lý case phức tạp |
| Thiếu metric nào? | Client outcome, post-advice quality, override rate theo scenario | CSAT theo độ phức tạp, repeat inquiry, escalation success, complaint rate, human handoff quality |
| Bài học cho dashboard nhóm | Thiết kế trust trước khi scale | Không bao giờ để productivity metric đứng một mình |

## Bài học nhóm sẽ áp dụng vào dashboard

```markdown
1. Product của nhóm không được đo bằng login, prompt count hoặc số phiên chat.

2. Với một AI assistant liên quan đến tư vấn nghề nghiệp, chỉ số mạnh nhất phải là:
   output có được dùng vào buổi tư vấn / báo cáo thật hay không, và có phải sửa fact lớn không.

3. Mỗi workflow phải có ít nhất:
   - một metric productivity,
   - một metric quality hoặc trust,
   - một owner rõ,
   - một failure path khi AI sai.

4. Dashboard phải tránh hai bẫy:
   - bẫy Morgan Stanley ngược: scale trước khi có trust architecture,
   - bẫy Klarna: thấy volume và speed đẹp rồi tưởng là ROI đã được chứng minh.
```

## Kết luận ngắn

Morgan Stanley cho thấy adoption bền vững cần trust architecture. Klarna cho thấy productivity rất mạnh nhưng chưa đủ để kết luận value bền vững. Vì vậy dashboard của `A20-App-116` phải ưu tiên đo cited-answer usefulness, correction rate, source freshness, report readiness và weekly reuse trong workflow tư vấn thật.
