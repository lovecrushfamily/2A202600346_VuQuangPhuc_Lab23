# Ngày 23 — Change Management & AI Adoption

**Chủ đề:** Khi công nghệ tốt nhưng nhân viên không dùng  
**Thời lượng:** 09:00-13:00  
**Sản phẩm cuối buổi:** Product ROI Dashboard cho 1 sản phẩm AI thật của nhóm

Trong buổi này, **AI adoption** được hiểu là **đưa AI vào vận hành thực tế**. Không chỉ là mua công cụ, mở tài khoản, hoặc dùng thử vài lần. AI chỉ tạo giá trị khi nó đi vào workflow thật, có người chịu trách nhiệm, có cách kiểm tra khi AI sai, và có metric đo được kết quả.

---

## Mục tiêu buổi học

Sau buổi này, nhóm của bạn cần làm được 3 việc:

1. Phân tích vì sao một sản phẩm AI chưa được dùng thật sự.
2. Thiết kế dashboard đo được adoption, chất lượng và giá trị, không chỉ đo usage.
3. Dùng dashboard để đưa ra quyết định: **continue / pivot / kill**.

---

## Lịch học

| Thời gian | Hoạt động | Kết quả |
|---|---|---|
| 09:00-10:00 | Lecture: AI adoption, ADKAR, Metrics Ladder, Measurement Trap, Gartner Lite, 25 tactics | Nắm khung tư duy chính |
| 10:00-11:00 | Case study theo nhóm | Rút bài học từ case để dùng cho dashboard |
| 11:00-12:00 | Build dashboard v1 | Có bản nháp Product ROI Dashboard |
| 12:00-12:30 | Red-team | Nhóm khác phản biện metric, rủi ro và logic quyết định |
| 12:30-13:00 | Revise + submit | Sửa dashboard v2 và nộp link repo |

---

## Bài cần nộp

Mỗi học viên tạo **một repo GitHub cá nhân** và để các file nộp bài trong repo đó.

| File | Làm cá nhân hay nhóm? | Deadline | Ghi chú |
|---|---|---|---|
| `01-case-evidence-matrix.md` | Cá nhân | Trong Block 2 | Phân tích case được giao |
| `02-case-comparison.md` | Nhóm, mỗi thành viên copy về repo cá nhân | Cuối Block 2 | So sánh case thành công / cảnh báo |
| `03-product-roi-dashboard.md` | Nhóm, mỗi thành viên copy về repo cá nhân | 13:00 | Dashboard cuối sau red-team |
| `04-reflection.md` | Cá nhân | 24h sau lớp | 150-200 từ: 1 metric hoặc 1 giả định bạn sẽ sửa |

Cuối Block 5, share link repo cá nhân lên Discord `#day23-submissions`.

---

## Product ROI Dashboard cần có gì?

Dashboard phải áp dụng cho **1 sản phẩm cụ thể** và **2-4 workflow chính**.

Không chọn quá rộng:

- Không chọn: "AI trong công ty".
- Không chọn: "dùng ChatGPT nói chung".
- Nên chọn: "AI chatbot cho chăm sóc khách hàng SME" hoặc "AI learning assistant cho sinh viên đọc tài liệu".

Trong [`Day23-Lab-Assignment.md`](Day23-Lab-Assignment.md) có một ví dụ mẫu dựa trên case Klarna để minh họa workflow, metric, dashboard mock và decision memo.

### Part A — Adoption Context

Cần trả lời:

- Product là gì?
- Ai dùng product này?
- 2-4 workflow chính là gì?
- AI làm phần nào trong từng workflow?
- Con người kiểm tra ở đâu?
- Nếu AI sai thì xử lý thế nào?
- Rào cản ADKAR chính là gì?
- Nhóm chọn 3 tactic nào để tăng adoption?

### Part B — ROI Dashboard

Dashboard dùng 8 cột:

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|

Metric không được chỉ là login, prompt count, DAU/MAU hoặc số người mở tool. Những chỉ số đó có thể dùng, nhưng phải đi kèm metric về:

- productivity: công việc nhanh hơn hoặc nhiều hơn không;
- quality: output có ít lỗi hơn không;
- trust: người dùng có tin và tiếp tục dùng không;
- value: có tiết kiệm chi phí, tăng doanh thu, tăng NPS, tăng retention hoặc cải thiện learning outcome không.

### Part C — Dashboard Mock

Vẽ nhanh 4-6 ô dashboard. Không cần đẹp, nhưng phải thể hiện logic đo lường.

```text
[Activation]      [Productivity]
[Quality]         [Trust]
[Value]           [Decision: Continue / Pivot / Kill]
```

### Part D — Decision Memo

Trả lời ngắn:

1. Nhóm đề xuất continue / pivot / kill?
2. Metric mạnh nhất là gì, vì sao?
3. Metric nào đã thay sau red-team?
4. Trước khi scale, nhóm phải làm gì?

---

## Chấm điểm

Day 23 = **100 điểm**.

| Hạng mục | Điểm |
|---|---:|
| Case Evidence Matrix | 15 |
| Case comparison | 15 |
| Product ROI Dashboard v2 | 60 |
| Reflection cá nhân sau lớp | 10 |

Dashboard tốt cần có:

- 1 product cụ thể + 2-4 workflow chính.
- Metric có baseline, target, data source và owner rõ.
- Có ít nhất một metric về quality, trust hoặc value.
- Có red-team risk và phần Fix sau khi bị phản biện.
- Có ít nhất 2 thay đổi rõ từ v1 sang v2.
- Có decision logic: continue / pivot / kill.

Chi tiết rubric: [`../../assessment/day23-rubric-requirements.md`](../../assessment/day23-rubric-requirements.md)

---

## Cách nộp bài

Tạo repo GitHub cá nhân:

| Trường | Yêu cầu |
|---|---|
| Tên repo | `Day23-Track01-<MãHọcViên>` |
| Ví dụ | `Day23-Track01-V202301001` |
| Visibility | Public |
| Branch | `main` |

Cấu trúc repo:

```text
Day23-Track01-<MãHọcViên>/
├── README.md
├── 01-case-evidence-matrix.md
├── 02-case-comparison.md
├── 03-product-roi-dashboard.md
├── 04-reflection.md
└── assets/
```

Lưu ý:

- File nộp dùng Markdown (`.md`).
- Mỗi thành viên copy file nhóm vào repo cá nhân.
- Discord chỉ dùng để gửi link repo, không nộp file trực tiếp.
- Repo phải public để đội chấm có thể truy cập.

---

## Tài liệu cần dùng

| File | Dùng để làm gì? |
|---|---|
| [`Day23-Lab-Assignment.md`](Day23-Lab-Assignment.md) | Đề bài chính |
| [`01-worksheet.md`](01-worksheet.md) | Worksheet tổng hợp Parts A-D |
| [`02-templates/00-case-evidence-matrix.md`](02-templates/00-case-evidence-matrix.md) | Template Case Evidence Matrix |
| [`02-templates/01-part-a-adoption-context.md`](02-templates/01-part-a-adoption-context.md) | Template Part A |
| [`02-templates/02-part-b-roi-dashboard.md`](02-templates/02-part-b-roi-dashboard.md) | Template Part B |
| [`02-templates/03-part-c-dashboard-mock.md`](02-templates/03-part-c-dashboard-mock.md) | Template Part C |
| [`02-templates/04-part-d-decision-memo.md`](02-templates/04-part-d-decision-memo.md) | Template Part D |
| [`02-templates/05-red-team-template.md`](02-templates/05-red-team-template.md) | Template red-team |
| [`05-reference-document.md`](05-reference-document.md) | Tài liệu tham khảo |
| [`05-reference-document.pdf`](05-reference-document.pdf) | Bản PDF tài liệu tham khảo |

---

## Checklist trước 13:00

- `03-product-roi-dashboard.md` đã có Parts A-D.
- Dashboard có red-team risk và Fix.
- Nhóm đã sửa ít nhất 2 điểm từ v1 sang v2.
- Mỗi thành viên đã copy file nhóm vào repo cá nhân.
- Repo cá nhân đã push lên GitHub và để public.
- Link repo đã được gửi lên Discord `#day23-submissions`.

---

*Ngày 23 — VinUni A20 — AI Thực Chiến*
