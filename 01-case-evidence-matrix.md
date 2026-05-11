# 01 — Case Evidence Matrix

## A. Case Evidence Matrix — cá nhân

| Trường | Trả lời |
|---|---|
| Case | Klarna AI customer support assistant |
| AI được dùng trong workflow nào? | Phân loại chat hỗ trợ khách hàng, trả lời case đơn giản, rút ngắn thời gian xử lý và chỉ chuyển case phức tạp sang người thật |
| Người dùng chính là ai? | Khách hàng cần hỗ trợ và đội customer support của Klarna |
| Họ đo metric gì? | Khoảng 2,3 triệu cuộc trò chuyện được AI xử lý; khoảng 2/3 tổng số chat; thời gian xử lý giảm từ 11 phút xuống dưới 2 phút; hiệu quả được mô tả tương đương khoảng 700 FTE |
| Metric đó thuộc layer nào? | Productivity + Value + một phần Activation/Coverage |
| Metric đó chứng minh được gì? | AI có thể xử lý volume lớn ở workflow lặp lại, giảm mạnh thời gian xử lý và tạo tín hiệu tốt về chi phí vận hành |
| Metric đó chưa chứng minh được gì? | Chưa chứng minh được khách hàng có hài lòng hơn không, case phức tạp có được xử lý tốt không, complaint có tăng không, và trust có bền vững không |
| Thiếu metric nào? | CSAT theo độ phức tạp của case, repeat inquiry trong 7 ngày, escalation success rate, complaint rate, human handoff quality |
| Rủi ro lớn nhất | Tối ưu speed và cost quá mạnh làm chất lượng dịch vụ giảm ở các tình huống nhạy cảm hoặc phức tạp |
| Bài học cho dashboard nhóm | Không dùng volume hoặc tốc độ như bằng chứng duy nhất. Mọi metric productivity phải đi kèm quality, trust và human fallback |

## B. Case Comparison — nhóm

| Trường | Case thành công / tín hiệu tốt | Case cảnh báo / thất bại |
|---|---|---|
| Case | Morgan Stanley AI assistant | Klarna AI customer support assistant |
| Workflow có AI | Advisor tìm nhanh tri thức nội bộ để phục vụ khách hàng | AI xử lý chat hỗ trợ khách hàng quy mô lớn |
| Metric chính | Adoption cao trong môi trường rủi ro cao nhờ eval, expert feedback loop và compliance controls | 2,3 triệu cuộc trò chuyện; khoảng 2/3 chat; thời gian xử lý từ 11 phút xuống dưới 2 phút; khoảng 700 FTE-equivalent |
| Metric đó chứng minh được gì? | Trust architecture tốt có thể mở adoption ngay cả khi workflow nhạy cảm | AI tạo năng suất rất lớn trên workflow lặp lại |
| Metric đó chưa chứng minh được gì? | Chưa chứng minh đầy đủ tác động cuối cùng lên client retention, NPS hoặc business outcome | Chưa chứng minh chất lượng dài hạn, trust của khách hàng, complaint hay hiệu quả ở case phức tạp |
| Thiếu metric nào? | Client outcome, quality by scenario, downstream business impact | CSAT theo độ phức tạp, repeat inquiry, escalation success, complaint rate |
| Bài học cho dashboard nhóm | Xây trust, kiểm chứng và compliance trước khi scale | Productivity luôn phải đi với quality và trust |

## Câu chốt

```markdown
Case thành công dạy nhóm tôi rằng:
AI adoption bền vững không đến từ việc ép dùng nhiều hơn, mà đến từ việc thiết kế trust architecture trước khi scale.

Case cảnh báo / thất bại dạy nhóm tôi rằng:
Một dashboard chỉ đo volume, speed hoặc FTE-equivalent rất dễ bỏ sót điều quan trọng nhất là chất lượng và niềm tin của người dùng cuối.

Vì vậy dashboard nhóm tôi phải:
đo task completion thật, chất lượng output, trust khi dùng vào quyết định, và giá trị vận hành; không dùng prompt count hay login count làm chỉ số trung tâm.
```
