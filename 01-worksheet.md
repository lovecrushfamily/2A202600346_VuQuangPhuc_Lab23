# Day 23 — Worksheet Product ROI Dashboard

File này dùng để nhóm điền trong lớp, sau đó copy nội dung cuối vào `03-product-roi-dashboard.md` trong repo cá nhân của từng thành viên.

---

## 0. Thông tin nhóm

| Trường | Trả lời |
|---|---|
| Nhóm | |
| Thành viên + phần phụ trách | |
| Product chọn phân tích | |
| Người dùng chính | |
| Link repo / file nộp cuối | |

---

## 1. Case Comparison

Tóm tắt bài học từ case study để dùng cho dashboard.

| Trường | Case thành công / tín hiệu tốt | Case cảnh báo / thất bại |
|---|---|---|
| Case | | |
| AI được dùng trong workflow nào? | | |
| Người dùng chính là ai? | | |
| Họ đo metric gì? | | |
| Metric đó chứng minh được gì? | | |
| Metric đó chưa chứng minh được gì? | | |
| Thiếu metric nào? | | |
| Bài học cho dashboard nhóm | | |

**Bài học nhóm sẽ áp dụng vào dashboard:**

```markdown
...
```

---

## 2. Part A — Adoption Context

| Trường | Trả lời |
|---|---|
| Product | |
| Người dùng chính | |
| Bối cảnh sử dụng | |
| Mục tiêu kinh doanh / học tập / vận hành | |
| Rào cản ADKAR chính | Awareness / Desire / Knowledge / Ability / Reinforcement |

### 2-4 workflow chính

| # | Workflow | AI làm gì? | Con người kiểm tra ở đâu? | Khi AI sai thì xử lý thế nào? |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |

### 3 tactic tăng adoption

| Tactic | Nhắm vào rào cản nào? | Áp dụng cho workflow nào? | Người phụ trách |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

## 3. Part B — ROI Dashboard

### B.1 Metric toàn product

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | | | | | | | |
| Engagement / Retention | | | | | | | |
| Trust / Quality / Value | | | | | | | |

### B.2 Metric theo workflow

Sao chép block dưới cho mỗi workflow đã chọn. Mỗi workflow cần ít nhất 4 layer, ưu tiên Productivity + Quality + Trust hoặc Value.

#### Workflow 1 — [tên]

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | | | | | | | |
| Engagement | | | | | | | |
| Productivity | | | | | | | |
| Quality | | | | | | | |
| Trust | | | | | | | |
| Value | | | | | | | |

#### Workflow 2 — [tên]

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | | | | | | | |
| Engagement | | | | | | | |
| Productivity | | | | | | | |
| Quality | | | | | | | |
| Trust | | | | | | | |
| Value | | | | | | | |

#### Workflow 3 — [nếu có]

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | | | | | | | |
| Engagement | | | | | | | |
| Productivity | | | | | | | |
| Quality | | | | | | | |
| Trust | | | | | | | |
| Value | | | | | | | |

#### Workflow 4 — [nếu có]

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | | | | | | | |
| Engagement | | | | | | | |
| Productivity | | | | | | | |
| Quality | | | | | | | |
| Trust | | | | | | | |
| Value | | | | | | | |

---

## 4. Part C — Dashboard Mock

Vẽ 4-6 ô. Ô đầu tiên là tình trạng toàn product, các ô sau là tín hiệu theo workflow hoặc quyết định.

```text
┌──────────────────────────────┐ ┌──────────────────────────────┐
│ PRODUCT HEALTH               │ │ WORKFLOW 1                   │
│ Metric: ____________________ │ │ Metric: ____________________ │
│ Current: ____ Target: _____  │ │ Current: ____ Target: _____  │
│ Status: Green / Amber / Red  │ │ Status: Green / Amber / Red  │
│ Action if red: _____________ │ │ Action if red: _____________ │
└──────────────────────────────┘ └──────────────────────────────┘

┌──────────────────────────────┐ ┌──────────────────────────────┐
│ WORKFLOW 2                   │ │ QUALITY / TRUST              │
│ Metric: ____________________ │ │ Metric: ____________________ │
│ Current: ____ Target: _____  │ │ Current: ____ Target: _____  │
│ Status: Green / Amber / Red  │ │ Status: Green / Amber / Red  │
│ Action if red: _____________ │ │ Action if red: _____________ │
└──────────────────────────────┘ └──────────────────────────────┘

┌──────────────────────────────┐ ┌──────────────────────────────┐
│ VALUE                         │ │ DECISION                     │
│ Metric: ____________________ │ │ Continue / Pivot / Kill: ___ │
│ Current: ____ Target: _____  │ │ Metric mạnh nhất: __________ │
│ Status: Green / Amber / Red  │ │ Before scale: ______________ │
└──────────────────────────────┘ └──────────────────────────────┘
```

---

## 5. Part D — Decision Memo

```markdown
# Decision Memo — [tên product]

1. Nhóm khuyến nghị: continue / pivot / kill.

2. Metric mạnh nhất để bảo vệ quyết định là:

3. Metric hoặc giả định nhóm đã sửa sau red-team là:
   V1: ...
   V2: ...
   Vì sao sửa này tốt hơn:

4. Trước khi scale, nhóm phải:
   1.
   2.
   3.
```

---

## 6. Red-team và sửa v2

### Nhóm mình đi red-team nhóm khác

| Vai nhóm được giao | Nhóm bị phản biện | 3 câu hỏi / rủi ro nhóm mình nêu |
|---|---|---|
| CFO / User / Risk / Workflow Owner | | 1.  2.  3. |

### Nhóm mình bị red-team

| Red-team risk | Metric / giả định bị chất vấn | Nhóm sửa gì ở v2? |
|---|---|---|
| 1 | | |
| 2 | | |
| 3 | | |

### Ít nhất 2 thay đổi cụ thể từ v1 sang v2

| # | V1 có vấn đề gì? | V2 sửa thành gì? | Vì sao sửa này tốt hơn? |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

## 7. Checklist trước khi nộp

- [ ] Có 1 product cụ thể, không chọn "AI cho cả công ty".
- [ ] Có 2-4 workflow chính.
- [ ] Mỗi workflow có vai trò AI, human review và failure path.
- [ ] Có rào cản ADKAR chính.
- [ ] Dashboard có metric toàn product và metric theo workflow.
- [ ] Không chỉ đo usage: login, prompt count, DAU/MAU.
- [ ] Có baseline, target, data source và owner cho các metric chính.
- [ ] Có ít nhất 1 metric Quality, Trust hoặc Value.
- [ ] Có Red-team risk và Fix.
- [ ] Có ít nhất 2 thay đổi rõ từ v1 sang v2.
- [ ] Decision Memo có continue / pivot / kill.
