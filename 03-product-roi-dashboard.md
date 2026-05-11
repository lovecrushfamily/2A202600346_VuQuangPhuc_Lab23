# 03 — Product ROI Dashboard

## Product chọn phân tích

- Product: `A20-App-116` — AI Career Advisor Assistant / AI Career Counselor
- Người dùng chính: career advisor, HR/recruiter, researcher cần insight aggregate có nguồn
- Phạm vi dashboard này: 3 workflow đang phù hợp nhất với repo tham chiếu
  1. Hỏi đáp thị trường lao động bằng AI chat có cited sources
  2. Xem market dashboard theo tuần/tháng/quý/năm
  3. Xuất PDF báo cáo để dùng cho tư vấn hoặc briefing

Lưu ý: repo tham chiếu đang ở giai đoạn MVP, có phần dashboard demo data và một số observability endpoint chưa hoàn thiện. Vì vậy các baseline dưới đây được dùng như **mốc pilot nội bộ đầu tiên**, không phải số liệu production đã xác nhận.

## Part A — Adoption Context

| Trường | Trả lời |
|---|---|
| Product | AI Career Advisor Assistant tổng hợp dữ liệu JD công khai, trả lời câu hỏi thị trường lao động bằng chat AI có nguồn và dashboard aggregate |
| Người dùng chính | Career advisor và HR/recruiter; secondary user là researcher |
| Bối cảnh sử dụng | Chuẩn bị buổi tư vấn nghề nghiệp, so sánh nhu cầu kỹ năng, làm weekly market brief, trả lời câu hỏi ad-hoc nhanh hơn tìm tay |
| Mục tiêu kinh doanh / học tập / vận hành | Rút ngắn thời gian tổng hợp insight, tăng độ tin cậy của dữ liệu khi tư vấn, giảm việc tìm nguồn thủ công, tạo report share-ready nhanh hơn |
| Rào cản ADKAR chính | `Ability` — người dùng chưa biết khi nào có thể tin output AI, khi nào phải mở cited sources hoặc kiểm tra lại dashboard trước khi dùng vào tư vấn thật |

### 3 workflow chính

| # | Workflow | AI làm gì? | Con người kiểm tra ở đâu? | Khi AI sai thì xử lý thế nào? |
|---|---|---|---|---|
| 1 | Hỏi đáp thị trường lao động bằng chat | Classify intent, tìm insight phù hợp, sinh câu trả lời tự nhiên, hiển thị cited sources | Advisor/HR phải mở ít nhất 1 nguồn khi câu trả lời được dùng cho buổi tư vấn hoặc briefing thật | Flag câu trả lời, ghi reason, fallback sang dashboard hoặc tìm nguồn tay, đưa case vào QA sample tuần |
| 2 | Phân tích dashboard market trend | Tổng hợp KPI, top skill, top field, line chart, platform/company/industry trend theo range | Người dùng kiểm tra freshness stamp, đối chiếu widget quan trọng trước khi trích vào tư vấn | Nếu source coverage mỏng hoặc số không khớp, không dùng để tư vấn; chuyển sang manual verification |
| 3 | Xuất PDF báo cáo để chia sẻ | Tạo bản report từ snapshot hiện tại, chuẩn hóa cấu trúc thành file share-ready | Advisor/HR rà lại headline, citation, range thời gian và diễn giải trước khi gửi cho người khác | Nếu report cần sửa lớn, đánh dấu correction type, không gửi ngay, chuyển lại team product để sửa template/data |

### 3 tactic tăng adoption

| Tactic | Nhắm vào rào cản nào? | Áp dụng cho workflow nào? | Người phụ trách |
|---|---|---|---|
| Source freshness badge + “ready to cite / verify first” label trên từng output | Ability | 1, 2, 3 | Product Designer + Frontend Lead |
| Prompt playbook cho advisor/HR: 10 câu hỏi mẫu + checklist “khi nào phải mở nguồn” | Ability | 1, 2 | Product Manager |
| QA review hằng tuần cho câu trả lời bị dislike hoặc report bị sửa lớn | Reinforcement phụ trợ cho Ability | 1, 3 | AI Ops Lead |

## Part B — ROI Dashboard

### B.1 Metric toàn product

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % người dùng mục tiêu hoàn thành phiên đầu tiên có `1 câu trả lời + mở ít nhất 1 citation` trong 7 ngày | 34% | 60% | Auth log + chat session log + citation click log | Product Manager | Chỉ đo sign-up đẹp nhưng chưa chứng minh dùng thật | Chỉ tính activated khi có cited answer và source open |
| Retention / Value | % user đã activate quay lại ít nhất 1 lần/tuần trong 3 tuần liên tiếp để làm task thật | 18% | 40% | Session log + event “task completed” | Growth Lead | Có thể quay lại chỉ để xem thử chứ không tạo value | Chỉ tính phiên có workflow completion event |
| Trust / Quality | % output AI được dùng trong tư vấn/report mà không cần sửa fact lớn | 55% | 80% | QA sample + advisor review form + report correction log | AI Ops Lead | Self-report dễ thiên vị | Audit ngẫu nhiên 10 mẫu/tuần bởi 1 reviewer độc lập |

### B.2 Metric theo workflow

#### Workflow 1 — Chat market analysis with cited sources

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % active user gửi ít nhất 1 câu hỏi thị trường hợp lệ mỗi tuần | 42% | 70% | Chat request log + intent classifier | Product Analyst | Câu hỏi thử nghiệm vẫn được tính | Chỉ tính intent thuộc career/market và có phản hồi thành công |
| Engagement | % session đi tới lượt 2+ sau câu trả lời đầu tiên | 28% | 50% | Chat session log | Product Analyst | Nhiều lượt có thể do câu trả lời đầu gây rối | Ghép với thumbs-up hoặc citation open để tránh hiểu sai |
| Productivity | Median time từ lúc nhập câu hỏi đến lúc có câu trả lời “advisor-ready draft” | 4.5 phút | 1.5 phút | FE timestamps + advisor quick rating | Frontend Lead | Nhanh hơn nhưng chưa chắc dùng được | Chỉ coi completed khi advisor chọn “usable draft” |
| Quality | % câu trả lời có ít nhất 2 citation hợp lệ và crawl date <= 14 ngày | 62% | 90% | Citation renderer log + source metadata | Data Lead | Citation có thể mới nhưng không liên quan | Thêm QA rubric relevance score cho sample hằng tuần |
| Trust | % câu trả lời được dùng mà không rewrite quá 30% nội dung | 48% | 75% | Advisor post-task form + transcript diff sample | AI Ops Lead | Người dùng lười báo sửa | Random transcript review 10 case/tuần |
| Value | Thời gian tiết kiệm trung vị cho mỗi lần chuẩn bị insight ad-hoc | 12 phút | 25 phút | Time diary pilot + session timestamps | Product Manager | Self-report có thể phóng đại | So sánh với baseline manual task trong cùng nhóm pilot |

#### Workflow 2 — Dashboard market trend review

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % weekly active user mở tab dashboard sau login | 31% | 60% | Frontend route + tab event log | Frontend Lead | Mở tab do tò mò, không tạo value | Chỉ tính nếu ở lại >= 30 giây hoặc đổi range |
| Engagement | % session có đổi range và xem ít nhất 2 widget sâu | 24% | 50% | UI interaction log | Product Analyst | Click nhiều không đồng nghĩa hiểu insight | Thêm micro-action “mark useful insight” |
| Productivity | Median time để tạo tóm tắt “top 3 biến động tuần này” | 18 phút | 7 phút | Task study + export draft timestamps | Product Manager | Người dùng có thể chốt nhanh nhưng sai | Pair với quality metric ở dưới |
| Quality | % widget có freshness stamp <= 7 ngày và số liệu khớp source metadata | 70% | 98% | Pipeline metadata + widget QA check | Data Lead | Widget xanh nhưng coverage vẫn mỏng | Hiển thị source coverage badge theo platform |
| Trust | % user đánh dấu dashboard là “ready to cite” sau khi xem | 52% | 80% | In-app pulse survey | UX Researcher | Chỉ power user mới chịu survey | Trigger survey ngẫu nhiên ở nhiều phân khúc |
| Value | Median time để làm weekly market brief từ dashboard | 75 phút | 25 phút | Export log + advisor time sample | Career Ops Lead | Time saving không chứng minh brief tốt hơn | Đo thêm brief acceptance bởi team lead |

#### Workflow 3 — Export PDF report for counseling/briefing

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % dashboard session dẫn tới hành động export | 9% | 25% | Export button event | Frontend Lead | Test nội bộ cũng bị tính | Dedupe theo user + range + 1 giờ |
| Engagement | % file export được mở hoặc chia sẻ trong 7 ngày | 35% | 70% | Download log + optional shared-link/open tracking | Growth Lead | Mở file không chứng minh hữu ích | Ghép với correction rate và reuse tag |
| Productivity | Median time từ chọn range đến có PDF share-ready | 9 phút | 3 phút | FE timestamps + export completion log | Frontend Lead | Xuất nhanh nhưng report khó dùng | Pair với quality metric dưới |
| Quality | % PDF cần sửa thủ công lớn trước khi gửi | 40% | <10% | Pre-send checklist + advisor review log | Product Manager | Người dùng không ghi lại lần sửa | Bắt buộc 1-click “sent as-is / edited / not used” sau export |
| Trust | Điểm hài lòng về độ sẵn sàng để chia sẻ của report (1-5) | 3.2 | 4.4 | In-app survey sau export | UX Researcher | Chỉ đo cảm nhận, không đo đúng sai | Audit 5 report/tuần với checklist fact + clarity |
| Value | % buổi tư vấn/briefing dùng report AI thay cho bản tổng hợp tay | 12% | 40% | Meeting prep form + export log | Career Ops Lead | Logging thêm bước có thể làm user ngại | Gắn tag 1-click trong workflow chuẩn bị buổi tư vấn |

## Thay đổi từ v1 sang v2 sau red-team

| # | V1 có vấn đề gì? | V2 sửa thành gì? | Vì sao sửa này tốt hơn? |
|---|---|---|---|
| 1 | V1 dùng `prompt count/user/week` để đo adoption chat | V2 đổi thành `% output AI được dùng trong tư vấn/report mà không cần sửa fact lớn` | V2 đo kết quả task thật và trust, không thưởng cho spam prompt |
| 2 | V1 dùng `number of exports` để chứng minh value | V2 thêm `% PDF cần sửa lớn` và `% file được mở/chia sẻ trong 7 ngày` | Export count một mình là vanity metric; V2 đo cả usage sau export và chất lượng report |
| 3 | V1 dùng một chỉ số CSAT trung bình cho cả sản phẩm | V2 tách trust theo chat, dashboard và export workflow | Tách theo workflow giúp biết chỗ nào đang làm người dùng mất niềm tin |

## Part C — Dashboard Mock

```text
┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 1: PRODUCT HEALTH             │ │ TILE 2: CHAT WORKFLOW              │
│ Metric: Activated + cited session  │ │ Metric: Usable answer no big edit  │
│ Current: 34%   Target: 60%         │ │ Current: 48%   Target: 75%         │
│ Status: AMBER                      │ │ Status: AMBER                      │
│ Action if red: fix first-run tour  │ │ Action if red: QA citations + flag │
└────────────────────────────────────┘ └────────────────────────────────────┘

┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 3: DASHBOARD WORKFLOW         │ │ TILE 4: TRUST / QUALITY            │
│ Metric: Weekly brief prep time     │ │ Metric: Fresh widget <= 7 days     │
│ Current: 75m    Target: 25m        │ │ Current: 70%   Target: 98%         │
│ Status: RED                        │ │ Status: AMBER                      │
│ Action if red: simplify top-3 flow │ │ Action if red: block stale widgets │
└────────────────────────────────────┘ └────────────────────────────────────┘

┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 5: REPORT VALUE               │ │ TILE 6: DECISION                   │
│ Metric: PDF sửa lớn trước khi gửi  │ │ Continue / Pivot / Kill: PIVOT     │
│ Current: 40%   Target: <10%        │ │ Metric mạnh nhất: no-big-edit rate │
│ Status: RED                        │ │ Before scale: real citations + QA  │
│ Action if red: fix template/report │ │ Owner: PM + AI Ops + Data Lead     │
└────────────────────────────────────┘ └────────────────────────────────────┘
```

## Part D — Decision Memo

# Decision Memo — A20 AI Career Advisor Assistant

1. Nhóm khuyến nghị: **pivot before scale**.

Pivot ở đây không phải bỏ product, mà là thu hẹp trọng tâm từ một “AI career app cho mọi thứ” sang một “trusted market-insight copilot cho advisor và HR”, chỉ scale khi cited answer, dashboard freshness và report quality đủ mạnh.

2. Metric mạnh nhất để bảo vệ quyết định là:

`% output AI được dùng trong tư vấn/report mà không cần sửa fact lớn` — baseline 55%.

Đây là chỉ số mạnh nhất vì nó nối được ba lớp cùng lúc:
- AI có tạo ra output usable không
- Người dùng có đủ trust để dùng vào việc thật không
- Product có tạo value vận hành hay chỉ tạo thêm một bước kiểm tra

3. Metric hoặc giả định nhóm đã sửa sau red-team là:

V1: dùng `prompt count/user/week` để đo adoption chat.  
V2: đổi sang `% output AI được dùng trong tư vấn/report mà không cần sửa fact lớn`.

Vì sao sửa này tốt hơn:
V1 rất dễ bị chạy số, đúng kiểu bài học từ KPMG/JPMorgan. V2 khó hơn nhưng phản ánh adoption thật trong workflow tư vấn.

4. Trước khi scale, nhóm phải:

1. Hoàn thiện logging cho citation click, source freshness và export correction flow — `Frontend Lead + Data Lead` — trong 2 tuần.
2. Thiết lập QA sample hằng tuần cho 20 câu trả lời chat và 5 report export — `AI Ops Lead` — bắt đầu ngay từ tuần pilot đầu.
3. Chạy pilot 4 tuần với 10 advisor/HR thực sự, có manual baseline task time để so sánh — `Product Manager` — hoàn thành trước quyết định scale.
