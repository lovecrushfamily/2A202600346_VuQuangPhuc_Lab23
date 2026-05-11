# Ngày 23 — Tài liệu tham khảo

**Chương trình:** VinUni A20 — AI Thực Chiến — Track 1 Product & Business  
**Chủ đề:** Change Management & AI Adoption — Khi công nghệ tốt nhưng nhân viên không dùng

Tài liệu này dùng để tra cứu trong và sau buổi học. Bạn không cần đọc hết trước lớp. Khi làm bài thực hành (lab), hãy dùng tài liệu này để nhớ lại khung tư duy (framework), chọn tình huống nghiên cứu (case study) phù hợp, kiểm tra chỉ số đo lường (metric) trong bảng đo lường (dashboard), và giải thích vì sao nhóm chọn một chiến thuật cụ thể.

**Cách dùng nhanh**

- Khi nghe buổi giảng: đọc Section 1-6 để nắm khung tư duy chính.
- Khi làm case study: dùng Section 7 để so sánh tình huống, metric, rủi ro và bài học.
- Khi làm Product ROI Dashboard: dùng Section 6, Section 8 và Section 9.
- Khi viết reflection: dùng lại các ví dụ về bẫy đo lường (measurement trap), dashboard sai và cách sửa metric.
- Khi trích dẫn: xem Section 10. Mọi tình huống, số liệu và framework chính đều có link nguồn.

---

## 1. Vì sao AI adoption không chỉ là chuyện công nghệ

Một công cụ AI có thể gây ấn tượng rất nhanh, nhưng điều đó chưa đủ để tạo giá trị. Giá trị chỉ xuất hiện khi AI được đưa vào quy trình thật: ai dùng, dùng lúc nào, ai kiểm tra, đo bằng chỉ số nào, và khi có lỗi thì xử lý ra sao.

Trong tài liệu này, **AI adoption** được hiểu là quá trình đưa AI từ một khả năng mới thành cách làm việc ổn định trong tổ chức. Một công ty không thể nói "chúng tôi đã áp dụng AI thật sự" chỉ vì đã mua quyền sử dụng, mở tài khoản, hoặc có vài nhóm thử dùng trong tuần đầu.

Nói ngắn gọn:

> AI lan nhanh khi nó gây wow. AI chỉ tạo giá trị khi nó trở thành quy trình làm việc (workflow).

Day 23 dùng hai khái niệm để tách bạch chuyện này:

- **Diffusion**: công nghệ lan ra, nhiều người biết đến hoặc dùng thử.
- **Normalization**: công nghệ trở thành cách làm mặc định trong tổ chức.

Cách nói "Diffusion khác Normalization" là phần tổng hợp cho bài học Day 23, dựa trên Rogers về *Diffusion of Innovations* và May et al. về *Normalization Process Theory*. Đây không phải trích dẫn nguyên văn từ hai nguồn đó. Khi cần trích dẫn học thuật, hãy ghi là teaching synthesis dựa trên [Rogers / NCBI summary](https://www.ncbi.nlm.nih.gov/books/NBK618128/) và [May et al. 2009](https://link.springer.com/article/10.1186/1748-5908-4-29).

### Wow khác adoption như thế nào?

"Wow" là phản ứng ban đầu khi AI làm được điều gì đó gây ấn tượng. Adoption là khi tổ chức thay đổi cách làm việc vì AI tạo ra giá trị ổn định.

| Câu hỏi | Wow | Adoption |
|---|---|---|
| Quan sát trong bao lâu? | Một lần demo hoặc vài ngày đầu | Nhiều tuần, nhiều tháng, trong quy trình thật |
| Ai tham gia? | Nhóm thích thử công nghệ mới | Cả người dùng chính, quản lý, người vận hành và người còn nghi ngại |
| Bối cảnh sử dụng | Demo có kịch bản đẹp | Công việc thật, có lỗi, có ngoại lệ, có trách nhiệm |
| Tín hiệu thành công | "Trông hay quá" | Cách làm việc đổi, KPI đổi, chất lượng không giảm |

Vì vậy, một sản phẩm AI có thể có 80% người dùng kích hoạt tài khoản trong tuần đầu nhưng sau sáu tháng chỉ còn rất ít người dùng thường xuyên. Khi đó, dự án đã lan ra, nhưng chưa được áp dụng thật sự.

### Ví dụ Klarna: chỉ số vận hành cao chưa chắc là giá trị bền vững

Klarna là tình huống tốt để thấy một dự án AI có thể có số liệu ban đầu rất ấn tượng nhưng vẫn cần điều chỉnh khi đi vào vận hành thật.

Năm 2024, [OpenAI công bố case study Klarna](https://openai.com/index/klarna/) nói rằng AI assistant của Klarna đã xử lý khoảng 2,3 triệu cuộc trò chuyện, tương đương khoảng hai phần ba số lượt chat, giúp thời gian xử lý giảm mạnh và được mô tả là tương đương khoảng 700 nhân sự toàn thời gian. Đây là những con số rất tốt về năng suất và chi phí.

Nhưng các chỉ số đó chủ yếu trả lời câu hỏi: AI xử lý được bao nhiêu việc? Chúng chưa đủ để trả lời câu hỏi: khách hàng có hài lòng hơn không, các tình huống phức tạp có được xử lý tốt không, và chất lượng dịch vụ có giữ được không?

Đến năm 2025, [Reuters đưa tin Klarna điều chỉnh trọng tâm](https://www.reuters.com/business/swedens-klarna-shifts-ai-focus-cost-cuts-growth-2025-09-10/), bổ sung lại yếu tố con người trong dịch vụ khách hàng và nhấn mạnh tăng trưởng, chất lượng dịch vụ thay vì chỉ cắt chi phí.

Bài học cho Day 23:

> Tỷ lệ AI tự xử lý yêu cầu (deflection rate) có thể cao, nhưng nếu mức hài lòng của khách hàng, tỷ lệ khiếu nại, hoặc khả năng xử lý tình huống phức tạp đi xuống, bảng đo lường (dashboard) đang đo sai điều quan trọng.

Klarna không phải ví dụ "AI thất bại". Đây là ví dụ về việc hệ chỉ số phải trưởng thành theo dự án. Lúc đầu, đo số lượng việc AI xử lý là hợp lý. Khi dự án mở rộng, phải bổ sung chỉ số về chất lượng, niềm tin và giá trị kinh doanh.

### Vì sao Day 23 dạy adoption thay vì chỉ dạy build

Nhiều khóa học AI tập trung vào cách xây sản phẩm: chọn mô hình (model), viết câu lệnh (prompt), đánh giá kết quả đầu ra, triển khai hệ thống. Những phần đó rất cần thiết, nhưng chưa đủ.

Trong doanh nghiệp, thất bại thường xảy ra ở đoạn sau:

- Người dùng không hiểu AI giúp gì cho công việc thật.
- Quản lý không đổi cách giao việc hoặc đánh giá hiệu quả.
- Quy trình cũ vẫn giữ nguyên, AI chỉ bị gắn thêm ở ngoài.
- Dashboard chỉ đo số lần dùng, không đo chất lượng hoặc kết quả.
- Không có quy tắc rõ ràng để tiếp tục, đổi hướng hoặc dừng dự án.

[BCG 2024](https://www.bcg.com/press/24october2024-ai-adoption-in-2024-74-of-companies-struggle-to-achieve-and-scale-value) nêu rằng 74% công ty gặp khó khi mở rộng giá trị AI từ giai đoạn thử nghiệm. Vấn đề không chỉ nằm ở model, mà nằm ở khả năng tổ chức hấp thụ công nghệ: quy trình, con người, ngân sách, quản trị và đo lường.

Vì vậy, câu hỏi trung tâm của Day 23 là:

> Nếu công ty xây AI tốt, nhưng quy trình không đổi, hành vi không đổi, và chỉ số đo lường không đổi, AI đó có tạo giá trị thật không?

Câu trả lời thường là không.

### Checklist trước khi nói "AI đã được adopt"

Trước khi chuyển một dự án AI sang giai đoạn mở rộng, nhà sáng lập hoặc quản lý sản phẩm (PM) nên tự hỏi:

1. **Người dùng có quay lại không?** Tuần đầu nhiều người thử là chưa đủ. Hãy so sánh tỷ lệ dùng ở tuần 1 và tuần 8.
2. **Workflow có đổi không?** Nếu tài liệu vận hành, checklist, mô tả công việc hoặc handoff vẫn như cũ, AI có thể chỉ là công cụ phụ.
3. **Có người chịu trách nhiệm thật không?** Nếu không ai chịu trách nhiệm về dữ liệu, chất lượng, đào tạo và quyết định tiếp tục hay dừng, dự án chưa đi vào vận hành.
4. **Dashboard có đo đủ lớp không?** Chỉ đo kích hoạt ban đầu (activation) hoặc số lần dùng là chưa đủ. Cần có chỉ số về năng suất, chất lượng, niềm tin và giá trị.
5. **Có quy tắc quyết định không?** Nếu không có ngưỡng rõ ràng để tiếp tục, đổi hướng hoặc dừng, dự án sẽ rất khó học từ dữ liệu.

### Công thức Day 23

```text
Giá trị AI = Chất lượng công nghệ × Chất lượng adoption × Chất lượng đo lường
```

Đây là phép nhân, không phải phép cộng. Nếu công nghệ tốt nhưng không ai dùng đúng cách, giá trị gần như bằng không. Nếu nhiều người dùng nhưng đo sai, tổ chức có thể tưởng là thành công trong khi chất lượng hoặc niềm tin đang giảm.

---

## 2. Năm framework cần biết

Day 23 không yêu cầu bạn thuộc lòng lý thuyết MBA. Nhưng nếu làm sản phẩm AI trong doanh nghiệp, bạn cần biết vài framework đủ để chẩn đoán vấn đề đúng chỗ.

### 2.1 Rogers — Diffusion of Innovations

Rogers mô tả cách một đổi mới lan ra trong xã hội theo các nhóm người dùng: Innovators, Early Adopters, Early Majority, Late Majority và Laggards. Tóm tắt công khai có thể xem tại [NCBI / National Academies](https://www.ncbi.nlm.nih.gov/books/NBK618128/).

Điểm quan trọng cho AI: không phải ai cũng áp dụng cùng lúc. Nhóm thích thử công nghệ mới có thể dùng rất sớm, nhưng họ không đại diện cho số đông. Dự án thường kẹt ở đoạn chuyển từ Early Adopters sang Early Majority, vì lúc này người dùng không còn dùng vì tò mò mà cần thấy lợi ích rõ trong công việc.

Năm yếu tố cần soi:

| Yếu tố | Câu hỏi cần hỏi |
|---|---|
| Relative advantage | AI làm tốt hơn cách cũ bao nhiêu? |
| Compatibility | AI có hợp với cách làm, văn hóa và quy định hiện tại không? |
| Complexity | Người dùng có thấy AI dễ học, dễ dùng không? |
| Trialability | Họ có thể thử an toàn trước khi bị yêu cầu dùng chính thức không? |
| Observability | Kết quả tốt có nhìn thấy và chia sẻ được không? |

Trong bối cảnh Việt Nam, người dùng thử đầu tiên thường là nhân viên trẻ hoặc người thích công nghệ, nhưng họ không luôn có đủ uy tín để kéo cả nhóm đi theo. Vì vậy, champion network nên có cả người trẻ giỏi công cụ và một senior được tin tưởng.

### 2.2 TAM và UTAUT — vì sao cá nhân có muốn dùng hay không

Technology Acceptance Model (TAM) giải thích việc chấp nhận công nghệ qua hai niềm tin: người dùng có thấy công cụ hữu ích không, và có thấy nó dễ dùng không. UTAUT mở rộng thêm yếu tố ảnh hưởng xã hội và điều kiện hỗ trợ.

| Yếu tố | Câu hỏi cần hỏi |
|---|---|
| Performance expectancy | Công cụ có giúp tôi làm việc tốt hơn không? |
| Effort expectancy | Công cụ có dễ học và dễ dùng không? |
| Social influence | Sếp, đồng nghiệp, người có uy tín có dùng và khuyến khích không? |
| Facilitating conditions | Tổ chức có hỗ trợ quyền truy cập, đào tạo, bộ phận hỗ trợ và thời gian thử không? |

Với AI trong doanh nghiệp Việt Nam, **social influence** thường rất mạnh. Một công cụ được sếp dùng công khai thường có sức nặng hơn nhiều so với một tài liệu hướng dẫn được gửi trong group chat.

Giới hạn của TAM/UTAUT: các framework này thường đo ý định dùng, không đảm bảo hành vi thật. Một người có thể nói "em sẽ dùng" trong khảo sát nhưng vẫn không đưa AI vào workflow. Vì vậy Day 23 luôn yêu cầu đo hành vi và kết quả, không chỉ đo cảm nhận.

### 2.3 TOE — công nghệ, tổ chức và môi trường

TOE nhìn adoption ở cấp tổ chức, không chỉ cấp cá nhân. Một công ty có thể có nhân viên rất muốn dùng AI nhưng vẫn không triển khai được nếu hệ thống cũ không tích hợp, dữ liệu không sẵn sàng, hoặc môi trường pháp lý chưa rõ.

| Nhóm yếu tố | Cần soi điều gì? |
|---|---|
| Technology | Model, dữ liệu, API, tích hợp hệ thống, độ ổn định |
| Organization | Sponsor, ngân sách, năng lực vận hành, văn hóa rủi ro |
| Environment | Áp lực cạnh tranh, quy định ngành, vendor ecosystem, kỳ vọng nhà đầu tư |

Với ngân hàng, y tế hoặc bảo hiểm, yếu tố Environment đặc biệt quan trọng. Nếu quy định chưa rõ hoặc bộ phận compliance chưa có cơ chế duyệt, dự án AI có thể phải dừng dù đội sản phẩm và người dùng đều sẵn sàng.

### 2.4 NPT — khi nào công nghệ trở thành routine

Normalization Process Theory (NPT) của [May et al. 2009](https://link.springer.com/article/10.1186/1748-5908-4-29) hỏi một câu khác: công nghệ đã trở thành việc bình thường hằng ngày chưa?

NPT có bốn cơ chế chính:

| Cơ chế | Câu hỏi cần hỏi | Tín hiệu thực tế |
|---|---|---|
| Coherence | Người dùng có hiểu vì sao công nghệ tồn tại không? | Họ giải thích được mục đích trong một câu |
| Cognitive participation | Họ có thật sự tham gia và kéo người khác vào không? | Dùng đều sau nhiều tuần, không chỉ thử một lần |
| Collective action | Workflow, vai trò và handoff đã đổi chưa? | Tài liệu vận hành có cập nhật |
| Reflexive monitoring | Có vòng phản hồi để cải thiện không? | Cả nhóm xem lại dữ liệu định kỳ và sửa cách làm |

Một dấu hiệu rất thực tế: khi nhân viên không còn nói "đang thử AI" mà nói "workflow này làm như sau", AI đã bắt đầu trở thành một phần bình thường của công việc.

### 2.5 ADKAR — chẩn đoán rào cản thay đổi

ADKAR là framework change management của [Prosci](https://www.prosci.com/adkar/adkar-model), thường dùng trong tư vấn thay đổi tổ chức. Với AI, Prosci cũng có hướng dẫn riêng về [AI change management](https://www.prosci.com/ai-change-management).

| Stage | Câu hỏi | Nếu chẩn đoán sai sẽ sửa sai cách |
|---|---|---|
| Awareness | Họ có biết vì sao cần thay đổi không? | Training khi người dùng còn chưa hiểu lý do |
| Desire | Họ có muốn tham gia không? | Gửi thêm hướng dẫn trong khi họ đang sợ bị thay thế |
| Knowledge | Họ có biết cách làm không? | Nói truyền cảm hứng nhưng không dạy cách dùng |
| Ability | Họ có làm được trong workflow thật không? | Workshop một lần nhưng không có coaching |
| Reinforcement | Hành vi mới có được duy trì không? | Launch rầm rộ rồi không ai follow-up |

Quy tắc quan trọng:

> Sửa sai stage thì adoption vẫn chết. Nếu rào cản là Desire, tài liệu hướng dẫn không giải quyết được. Nếu rào cản là Ability, video của CEO không đủ.

### Tóm tắt: dùng framework nào khi nào?

| Câu hỏi | Framework phù hợp |
|---|---|
| Công nghệ lan ra theo nhóm người dùng như thế nào? | Rogers |
| Vì sao cá nhân muốn hoặc không muốn dùng? | TAM / UTAUT |
| Vì sao tổ chức chưa sẵn sàng dù cá nhân muốn dùng? | TOE |
| Vì sao nhiều người thử nhưng workflow chưa đổi? | NPT |
| Người dùng đang kẹt ở bước thay đổi nào? | ADKAR |

---

## 3. Gartner AI Maturity và Gartner Lite

[Gartner AI Maturity Model Toolkit](https://www.gartner.com/en/chief-information-officer/research/ai-maturity-model-toolkit) nhìn năng lực AI của doanh nghiệp qua nhiều trụ cột như strategy, data, engineering, governance, operating model và people/culture. Bản đầy đủ hữu ích cho audit cấp doanh nghiệp, nhưng quá nặng cho một buổi lab.

Day 23 dùng bản rút gọn gọi là **Gartner Lite**. Đây là teaching synthesis dựa trên Gartner, không phải mô hình chính thức do Gartner xuất bản.

| Trục | Gộp từ các trụ cột nào? | Câu hỏi cho lab |
|---|---|---|
| Direction | Strategy + AI product/value | AI phục vụ ưu tiên kinh doanh nào? Có người bảo trợ và OKR rõ không? |
| Readiness | Data + Engineering + Governance | Dữ liệu, tích hợp, bảo mật, legal và eval đã đủ chưa? |
| Absorption | Operating model + People/culture | Ai sở hữu workflow, ngân sách, đào tạo, metric và reinforcement? |

Ví dụ: một AI assistant cho call center SME của ngân hàng có thể có Direction tốt vì được lãnh đạo khối SME bảo trợ và gắn với mục tiêu NPS. Nhưng nếu dữ liệu email chỉ lưu 90 ngày, có PII chưa được xử lý, và tích hợp Salesforce chậm sáu tuần, Readiness vẫn là rủi ro chính. Nếu không có trưởng nhóm vận hành chịu trách nhiệm, Absorption cũng chưa đủ.

Cách dùng trong lab:

- Part A dùng Direction để làm rõ sản phẩm, người dùng, workflow và ưu tiên kinh doanh.
- Part B dùng Readiness để kiểm tra nguồn dữ liệu, baseline, target và tính đo được.
- Part B-D dùng Absorption để gắn người chịu trách nhiệm, tactic và quyết định continue / pivot / kill.

Lỗi thường gặp là chấm một "maturity score" trung bình cho cả tổ chức. Với AI, trụ cột yếu nhất mới là thứ làm dự án kẹt. Dữ liệu tốt nhưng governance yếu vẫn có thể không scale. Người bảo trợ mạnh nhưng workflow không đổi vẫn có thể không tạo giá trị.

---

## 4. Task split, Centaur/Cyborg và workflow redesign

Trước khi đưa AI vào workflow, cần tách công việc thành từng bước. Một workflow hiếm khi là "AI làm hết" hoặc "người làm hết". Nó thường là chuỗi nhiều bước, mỗi bước có mức độ phù hợp với AI khác nhau.

### Just Me / Delegated / Automated

Ethan Mollick, trong *[Co-Intelligence](https://www.penguinrandomhouse.com/books/740825/co-intelligence-by-ethan-mollick/)*, gợi ý phân loại công việc theo mức độ giao cho AI:

| Loại việc | Nghĩa là gì? | Ví dụ |
|---|---|---|
| Just Me | Con người giữ quyết định chính vì cần judgment, trách nhiệm hoặc đạo đức | Ký duyệt pháp lý, quyết định nhạy cảm, xử lý khiếu nại nghiêm trọng |
| Delegated | AI làm bản nháp hoặc hỗ trợ, con người kiểm tra trước khi dùng | Tóm tắt nghiên cứu, draft email, gợi ý code, meeting summary |
| Automated | AI có thể làm gần như toàn bộ vì việc lặp lại, rủi ro thấp và có quy tắc rõ | Phân loại ticket đơn giản, routing, ghi chú thô |

### Centaur và Cyborg

Mollick cũng phân biệt hai kiểu cộng tác giữa người và AI:

| Mode | Cách làm | Phù hợp khi nào? | Rủi ro |
|---|---|---|---|
| Centaur | Người và AI chia việc rõ, có điểm handoff rõ | Workflow có cấu trúc, cần audit, finance/legal/healthcare | Chậm nếu handoff thiết kế kém |
| Cyborg | Người và AI đan xen liên tục trong quá trình làm | Viết, brainstorm, coding, phân tích mở | Khó đo, khó audit, khó quy trách nhiệm |

Với triển khai doanh nghiệp lần đầu, Centaur thường an toàn hơn vì dễ đo: AI làm bước nào, người kiểm tra ở đâu, lỗi được phát hiện thế nào.

### Workflow Redesign Canvas

Một workflow có AI cần trả lời ít nhất bảy câu hỏi:

| Field | Câu hỏi |
|---|---|
| AS-IS workflow | Hiện tại làm qua những bước nào, đau ở đâu? |
| TO-BE workflow with AI | AI sẽ hỗ trợ, thay thế hoặc handoff ở bước nào? |
| Human review | Ai kiểm tra, kiểm tra lúc nào, theo trigger nào? |
| Owner | Ai chịu trách nhiệm kết quả cuối cùng? |
| Failure path | Khi AI sai, không chắc, hoặc thiếu dữ liệu thì làm gì? |
| Outcome metric | Kết quả nào phải cải thiện? |
| Trust signal | Người dùng biết output đủ an toàn bằng tín hiệu nào? |

Nếu mô tả công việc, người chịu trách nhiệm, điểm handoff hoặc failure path không đổi, đó chỉ là rollout công cụ, chưa phải redesign workflow.

### Vì sao people/process quan trọng hơn model

[BCG 2024](https://www.bcg.com/press/24october2024-ai-adoption-in-2024-74-of-companies-struggle-to-achieve-and-scale-value) nhấn mạnh nguyên tắc 10-20-70: trong các chương trình AI tạo giá trị, phần thuật toán chỉ là một phần nhỏ; phần lớn nỗ lực nằm ở công nghệ tích hợp, con người và quy trình. Day 23 tập trung vào phần con người và quy trình vì đó là nơi nhiều dự án doanh nghiệp thất bại.

[McKinsey State of AI 2024](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai-2024) cũng nhấn mạnh rằng giá trị từ AI phụ thuộc mạnh vào việc thiết kế lại workflow, không chỉ đưa thêm công cụ vào tổ chức.

### Ví dụ ngắn: sales proposal

Workflow viết proposal trước AI có thể mất khoảng 5 giờ: ghi chú meeting, nghiên cứu khách hàng, viết bản nháp phần mở đầu, viết solution/pricing, tìm case study, quản lý review, gửi khách hàng.

Sau khi tách việc:

- Ghi chú meeting: Automated.
- Research khách hàng: Delegated, người bán kiểm tra lại các fact quan trọng.
- Draft mở đầu: Delegated, người bán chỉnh tone.
- Pricing: Just Me, vì sai giá là rủi ro cao.
- Chọn case study: Delegated, người bán chọn case cuối.
- Quản lý review: Just Me.

Khi đó AI không "viết proposal thay người". AI rút ngắn một số bước có tính lặp lại, còn con người giữ các điểm cần judgment và trách nhiệm.

---

## 5. ADKAR cho AI change management

AI khác nhiều thay đổi công nghệ thông thường vì nó chạm trực tiếp vào nỗi lo về năng lực, vai trò và việc làm. Người dùng không chỉ hỏi "công cụ này có khó không?" mà còn hỏi "nó có thay tôi không?", "nếu AI sai thì lỗi của ai?", "dùng AI có làm tôi mất kỹ năng không?".

Dùng ADKAR để chẩn đoán đúng rào cản:

| Stage | Với AI cần hỏi cụ thể |
|---|---|
| Awareness | Vì sao phải dùng AI này, cho workflow này, vào thời điểm này? |
| Desire | Người dùng có muốn tham gia không, hay đang sợ bị thay thế / bị ép dùng? |
| Knowledge | Họ có biết viết prompt thế nào, kiểm chứng output ra sao, khi nào không nên dùng AI không? |
| Ability | Họ có dùng được AI trong workflow thật, với dữ liệu thật, dưới áp lực thời gian thật không? |
| Reinforcement | Quản lý, KPI, nhịp review và recognition có giữ hành vi mới lại không? |

### Điều chỉnh cho bối cảnh Việt Nam

Trong nhiều team Việt Nam, khảo sát công khai dễ tạo tín hiệu giả. Người dùng có thể trả lời "ổn" để giữ thể diện hoặc tránh đi ngược ý sếp. Vì vậy, khi chẩn đoán Desire và Ability, nên kết hợp:

- Kênh góp ý ẩn danh cho nỗi lo bị thay thế hoặc bị ép dùng.
- 1:1 với line manager để nghe vấn đề thật.
- Buổi practice không phán xét để người chưa biết dùng không bị mất mặt.
- Champion network có cả junior giỏi công cụ và senior được tôn trọng.

### Ví dụ chẩn đoán ADKAR

Một công cụ AI tóm tắt nội dung cho call center có thể có profile như sau:

| Stage | Tín hiệu | Chẩn đoán |
|---|---|---|
| Awareness | Town hall đã giới thiệu, nhiều người biết công cụ tồn tại | Trung bình |
| Desire | 45% lo AI thay thế công việc, 30% không thấy lợi ích trực tiếp | Rào cản chính |
| Knowledge | Chỉ một phần nhỏ nhân viên được đào tạo | Yếu |
| Ability | Sandbox đã có, tích hợp cơ bản đã sẵn sàng | Khá |
| Reinforcement | Chưa có KPI mới, manager chưa follow-up | Rào cản thứ hai |

Nếu rào cản chính là Desire, mở thêm lớp đào tạo chưa đủ. Cần giải thích rõ AI hỗ trợ chứ không thay thế toàn bộ vai trò, gắn với kế hoạch reskilling, và cho người dùng thấy senior thật sự dùng công cụ trong workflow thật.

---

## 6. Metrics ladder và measurement trap

Một dashboard AI tốt không thể chỉ có một con số. Nó cần đi từ việc có dùng hay không đến việc công việc có nhanh hơn, tốt hơn, đáng tin hơn và tạo giá trị thật hay không.

Section này tổng hợp từ nhiều nguồn thực hành về đo lường AI adoption, gồm [Microsoft Inside Track về Copilot rollout](https://www.microsoft.com/insidetrack/blog/measuring-the-success-of-our-microsoft-365-copilot-rollout-at-microsoft/), [Larridin về đo ROI vượt khỏi khảo sát](https://larridin.com/ai-workflow-mapping/how-to-measure-ai-roi-beyond-surveys), [Worklytics về productivity uplift](https://www.worklytics.co/resources/proving-productivity-uplift-ai-tool-adoption-pwc-2025-worklytics-data), và [KPMG về enterprise AI pilots](https://kpmg.com/us/en/articles/2026/enterprise-ai-pilots.html). Đây là góc nhìn thực hành, không phải benchmark học thuật trung lập.

### Metrics ladder

| Layer | Câu hỏi | Ví dụ metric | Độ mạnh của tín hiệu |
|---|---|---|---|
| Activation | Người dùng đã thử đúng use case chưa? | % người hoàn thành task đầu tiên bằng AI | Yếu nếu đứng một mình |
| Engagement | Có dùng đều và đủ sâu không? | Dùng lặp lại, độ sâu tính năng, số bước workflow có AI | Trung bình |
| Productivity | Công việc nhanh hơn hoặc nhiều hơn không? | Cycle time, tickets/agent/day, throughput | Tốt nếu có baseline |
| Quality | Kết quả có tốt hơn hoặc không tệ đi không? | Error rate, rework rate, escalation rate | Mạnh khi đi cùng productivity |
| Trust | Người dùng và khách hàng có tin tiếp không? | Override rate, CSAT, complaint rate | Mạnh |
| Value | Kết quả kinh doanh có cải thiện không? | Cost per task, revenue, retention, NPS, ROI | Mạnh nhất nhưng khó quy attribution |

Quy tắc quan trọng:

> Productivity phải đi cùng Quality. Nếu năng suất tăng nhưng lỗi cũng tăng, đó không phải thành công. Trust phải đi cùng Quality hoặc Productivity. Value nên có ít nhất hai nguồn dữ liệu để tránh tự kể chuyện.

### Measurement trap: Active users không phải ROI

Các metric như số license đã kích hoạt, MAU/WAU, số prompt, số giờ dùng AI rất dễ đo và dễ trình bày. Nhưng chúng chỉ cho thấy hoạt động, không chứng minh giá trị.

| Team show | Vì sao chưa đủ | CFO/Board cần hỏi thêm |
|---|---|---|
| 90% license đã kích hoạt | Có quyền dùng, chưa chắc dùng đúng việc | Bao nhiêu người hoàn thành workflow thật? |
| MAU/WAU cao | Có mở công cụ, chưa chắc tạo output | Task nào nhanh hơn? |
| Prompt count tăng | Có thể là mò mẫm hoặc spam | Output trên mỗi prompt có tốt hơn không? |
| Khảo sát hài lòng | Có self-report bias | Telemetry và business KPI có khớp không? |
| Pilot demo tốt | Demo có kịch bản đẹp | Khi production có edge case thì sao? |

### KPMG và JPMorgan: dashboard đo usage có thể phản tác dụng

[Business Insider đưa tin về dashboard AI của KPMG](https://www.businessinsider.com/kpmg-dashboard-consultants-ai-adoption-use-tracker-employees-2026-5), trong đó hành vi dùng AI được theo dõi theo target nội bộ. Case này hữu ích vì nó cho thấy khi một con số usage trở thành mục tiêu, nhân viên có thể tối ưu để vượt ngưỡng thay vì tạo giá trị thật. [Business Insider cũng đưa tin về KPMG Spark Awards](https://www.businessinsider.com/kpmg-ai-spark-awards-cash-prizes-for-employee-ai-innovation-2026-3), cho thấy mặt "khuyến khích bằng phần thưởng" của việc thúc đẩy AI adoption.

[Business Insider đưa tin về JPMorgan](https://www.businessinsider.com/jpmorgan-track-software-engineers-ai-use-dashboards-2026-4), nơi usage của kỹ sư với các công cụ như GitHub Copilot và Claude Code được theo dõi và phân loại. Dù công ty nói dữ liệu không dùng cho performance management, việc dashboard có cảm giác xếp hạng vẫn có thể tạo nỗi sợ và làm giảm Desire trong ADKAR.

Bài học:

> Khi doanh nghiệp chưa biết đo ROI thật, họ dễ chuyển sang đo usage. Một người dùng AI 100 lần mỗi ngày có thể vẫn không tạo tác động kinh doanh. Một người dùng AI 3 lần mỗi ngày nhưng rút ngắn proposal từ 3 ngày xuống 4 giờ có thể tạo giá trị lớn hơn.

### Goodhart's Law

Goodhart's Law nói rằng khi một chỉ số trở thành mục tiêu, nó thường mất khả năng đo đúng thực tế. Với AI dashboard:

- Mục tiêu số ngày dùng AI có thể dẫn đến việc mở công cụ cho đủ ngày.
- Mục tiêu số prompt có thể dẫn đến spam prompt.
- Target số ticket AI xử lý có thể làm giảm chất lượng xử lý case khó.

Thiết kế tốt hơn:

- Không dùng một ngưỡng usage đơn lẻ làm mục tiêu chính.
- Đo theo kết quả của workflow, không chỉ đo hoạt động trong công cụ.
- Ghép productivity với quality và trust.
- Có QA ngẫu nhiên để phát hiện hành vi "chạy metric".
- Có quy tắc rõ: nếu metric X vượt ngưỡng rủi ro thì pivot hoặc kill.

### Decision rules: Continue / Pivot / Kill

Dashboard chỉ hữu ích khi nó dẫn đến quyết định. Mỗi metric quan trọng nên có quy tắc:

| Rule | Khi nào dùng | Ví dụ |
|---|---|---|
| Continue | Metric đạt target và chất lượng không giảm | Escalation ≤10% và CSAT ≥4.2 sau 8 tuần thì mở rộng sang team tiếp theo |
| Pivot | Có tín hiệu dùng nhưng workflow hoặc đào tạo chưa đúng | Activation ≥70% nhưng engagement <50% thì chuyển sang intervention về Knowledge |
| Kill | Rủi ro chất lượng hoặc trust vượt ngưỡng | CSAT case phức tạp dưới 4.0 hoặc escalation tăng >20% thì dừng AI assist |
| Pause | Dữ liệu nhiễu, chưa đủ quyết định | Dừng mở rộng 2 tuần để lấy baseline rõ hơn |

Một quy tắc đủ tốt cần có: ngưỡng định lượng, ngày đánh giá, người quyết định, nhịp review và đường escalation.

### Ví dụ dashboard cho call center

| Layer | Metric | Baseline | Target 90 ngày | Data source | Owner | Decision rule |
|---|---|---:|---:|---|---|---|
| Activation | % agent hoàn thành setup AI trong workflow | 0% | 90% vào ngày 14 | App telemetry | Training Lead | Nếu <70% ở ngày 14 thì dừng mở rộng, kiểm tra Knowledge |
| Engagement | Prompt-to-completion ratio mỗi ticket | Chưa có | Median 1.2-1.5 | App logs | Ops Lead | Nếu >3.0 thì kiểm tra spam hoặc workflow khó dùng |
| Productivity | Tickets/agent/day | 35 | 50 | Salesforce report | Ops Manager | Nếu <40 ở week 6 thì pivot tactic |
| Quality | Escalation rate | 8% | ≤10% | QA random sample | QA Lead | Nếu tăng >20% so với baseline thì kill AI assist |
| Trust | CSAT theo độ phức tạp của case | 4.2 | ≥4.4 mỗi tier | Post-ticket survey | CX Lead | Nếu case phức tạp <4.0 thì điều tra Klarna pattern |
| Value | Cost per ticket | 45,000 VND | 30,000 VND | Finance report | Finance Manager | Nếu >40,000 ở week 12 thì reassess economics |

---

## 7. Case library

Mỗi case dưới đây dùng để học cách đọc metric. Không case nào nên được dùng như "công thức copy-paste". Khi trích dẫn, dùng đúng link và đúng nhãn nguồn ở Section 10.

### 7.1 Nansen — behavior instrumentation

Nguồn: [SuperAI talk / YouTube](https://www.youtube.com/watch?v=LdIC44npJOM). Nhãn: pending verification.

Nansen là công ty crypto analytics. Theo ghi chú nguồn hiện có, case này nói về cách instrument hành vi dùng AI trong team, ví dụ weekly AI hours hoặc khảo sát nội bộ.

Metric layer chính: Activation và Engagement.

Điều case này có thể chứng minh: người dùng đang thử và hình thành thói quen.  
Điều case này chưa chứng minh: công việc nhanh hơn, output tốt hơn, hoặc kết quả kinh doanh cải thiện.

Bài học: "AI hours per week" dễ thành vanity metric nếu không ghép với chất lượng output, cycle time hoặc kết quả kinh doanh.

### 7.2 Stripe — internal AI platform

Nguồn: [SuperAI talk / YouTube](https://www.youtube.com/watch?v=kWK8_dBUmCA). Nhãn: pending verification.

Theo ghi chú nguồn hiện có, Stripe xây internal LLM platform để các team tự build nhiều ứng dụng AI nội bộ. Đây là tình huống tốt để học về cách platform giúp các team tự triển khai.

Điều case này có thể chứng minh: tổ chức có năng lực xây công cụ có AI.  
Điều case này chưa chứng minh: từng app có người dùng thật, có governance đủ, có ROI rõ, hoặc không bị trùng lặp.

Bài học: nhiều ứng dụng AI không đồng nghĩa với adoption. Nếu không có registry, người chịu trách nhiệm, lifecycle và metric, platform có thể tạo app sprawl.

### 7.3 Morgan Stanley — trust trước scale

Nguồn: [OpenAI Morgan Stanley case study](https://openai.com/index/morgan-stanley/). Nhãn: practitioner / số liệu do công ty công bố.

Morgan Stanley triển khai AI assistant cho wealth management advisors để truy cập tri thức nội bộ nhanh hơn. Case này nổi bật vì adoption cao trong môi trường rủi ro cao, nhờ trust architecture: eval, expert feedback loop và compliance controls.

Điều case này có thể chứng minh: adoption trong môi trường rủi ro cao khả thi khi trust được thiết kế trước khi scale.  
Điều case này chưa chứng minh đầy đủ: tác động cuối cùng lên client outcomes như retention, return hoặc NPS.

Bài học: với finance, healthcare, legal, đừng scale trước rồi mới xây trust. Trust architecture là điều kiện để adoption xảy ra.

### 7.4 DWP / GDS — phương pháp đo quyết định độ tin cậy

Nguồn: [UK government cross-government Copilot findings](https://www.gov.uk/government/publications/microsoft-365-copilot-experiment-cross-government-findings-report/microsoft-365-copilot-experiment-cross-government-findings-report-html) và [DWP Copilot trial evaluation](https://www.gov.uk/government/publications/an-evaluation-of-dwps-microsoft-copilot-365-trial/an-evaluation-of-dwps-microsoft-365-copilot-trial). Nhãn: canonical / government.

Hai báo cáo này hữu ích vì chúng cho thấy cách đo ảnh hưởng đến kết luận. Self-report về thời gian tiết kiệm thường cho số cao hơn so với thiết kế có comparison group hoặc phân tích chặt hơn.

Điều case này có thể chứng minh: methodology quan trọng không kém metric.  
Điều case này chưa chứng minh tự động: thời gian tiết kiệm chuyển thành cost saving hoặc citizen outcome tốt hơn.

Bài học: nếu muốn nói về ROI một cách có thể bảo vệ trước chất vấn, cần baseline, comparison, hoặc ít nhất nhiều nguồn dữ liệu khớp nhau.

### 7.5 Klarna — volume không đủ nếu quality tụt

Nguồn: [OpenAI Klarna case study](https://openai.com/index/klarna/) và [Reuters 2025](https://www.reuters.com/business/swedens-klarna-shifts-ai-focus-cost-cuts-growth-2025-09-10/). Nhãn: practitioner + major news.

Klarna cho thấy AI có thể xử lý volume lớn và giảm thời gian xử lý, nhưng dashboard không được dừng ở containment, FTE-equivalent hoặc speed. Khi case phức tạp làm khách hàng không hài lòng, phải đo thêm quality, escalation, complaint và human handoff.

Bài học: productivity metric luôn cần quality và trust metric đi cùng.

### 7.6 IBM Watson / MD Anderson — model nổi tiếng không đủ

Nguồn: [JNCI / Oxford Academic article](https://academic.oup.com/jnci/article/109/5/djx113/3847623). Nhãn: canonical / academic.

MD Anderson hợp tác với IBM Watson cho oncology AI assistant, nhưng dự án bị hủy trước khi đi vào dùng với bệnh nhân thật. Case này thường được dùng để nhắc rằng thương hiệu model, ngân sách lớn và người bảo trợ cấp cao vẫn không đủ nếu dữ liệu, tích hợp, workflow và trust chưa sẵn sàng.

Bài học: demo tốt không đảm bảo adoption trong vận hành thật. Với healthcare AI, data readiness và workflow integration phải đi trước scale.

### 7.7 KPMG — usage dashboard dễ bị tối ưu sai

Nguồn: [Business Insider về KPMG AI usage dashboard](https://www.businessinsider.com/kpmg-dashboard-consultants-ai-adoption-use-tracker-employees-2026-5) và [Business Insider về KPMG Spark Awards](https://www.businessinsider.com/kpmg-ai-spark-awards-cash-prizes-for-employee-ai-innovation-2026-3). Nhãn: practitioner / major news.

KPMG là cautionary case về dashboard đo hành vi dùng AI. Khi mục tiêu là tần suất dùng, người dùng có thể tối ưu cho chỉ số thay vì tối ưu cho output.

Bài học: không thưởng theo số prompt hoặc số lần đăng nhập. Hãy thưởng theo outcome, quality, workflow completion và đóng góp học tập cho cả nhóm.

### 7.8 JPMorgan — ranking tạo áp lực và làm giảm Desire

Nguồn: [Business Insider về JPMorgan AI usage dashboards](https://www.businessinsider.com/jpmorgan-track-software-engineers-ai-use-dashboards-2026-4). Nhãn: practitioner / major news.

JPMorgan là cautionary case về việc dashboard có thể tạo cảm giác bị giám sát. Ngay cả khi công ty nói dữ liệu không dùng cho performance management, việc phân loại hoặc so sánh cá nhân vẫn có thể làm người dùng sợ bị đánh giá.

Bài học: nếu muốn tăng adoption, dashboard nên ưu tiên học tập ở cấp nhóm và cải thiện workflow, không tạo danh sách bêu tên.

### Pattern chung từ 8 case

| Pattern | Case | Cách xử lý |
|---|---|---|
| Vanity adoption | Nansen, KPMG | Thêm task-level outcome metric |
| Dashboard bị "chạy số" | KPMG, JPMorgan | Đo output, không chỉ input; có QA ngẫu nhiên |
| Volume cao nhưng quality rủi ro | Klarna | Ghép productivity với quality và trust |
| Data/integration fail | IBM Watson | Kiểm tra readiness trước scale |
| App sprawl | Stripe | Có registry, owner, lifecycle |
| Trust architecture tốt | Morgan Stanley | Eval + expert feedback + compliance trước scale |
| Methodology quyết định độ tin | DWP/GDS | Dùng baseline, comparison group, nhiều nguồn dữ liệu |

---

## 8. Tactics playbook

Nguồn chính cho phần này là bài của Peter Yang: [25 proven tactics to accelerate AI adoption at your company](https://creatoreconomy.so/p/25-proven-tactics-to-accelerate-ai-adoption-at-your-company). Đây là playbook thực hành trong ngành, không phải academic framework.

Quy tắc dùng:

> 25 tactics không phải checklist. Chúng là menu can thiệp. Chỉ chọn tactic sau khi biết readiness gap, workflow gap, ADKAR barrier và metric gap.

### Move 1 — Explain the how

Dùng khi người dùng biết AI tồn tại nhưng không hiểu AI thay đổi công việc cụ thể thế nào.

| # | Tactic | Khi dùng |
|---:|---|---|
| 1 | Specific AI memo | Awareness mơ hồ |
| 2 | Focused adoption week | Cần tạo nhịp thử nghiệm ngắn |
| 3 | Define "embracing AI" | Mọi người hiểu "AI-first" mỗi kiểu |
| 4 | Embed with teams | Leader cần hiểu workflow thật |
| 5 | Lead by example live | Cần social proof từ senior |

Ví dụ: Phó GĐ khối SME viết memo 2 trang nói rõ AI assistant thay đổi ba workflow nào, metric nào sẽ đo, và ngưỡng chất lượng cần giữ là gì. Đây tốt hơn nhiều so với thông điệp chung chung "công ty sẽ áp dụng AI".

### Move 2 — Track and reward adoption

Dùng khi người dùng thử một lần rồi bỏ, hoặc hành vi mới không được củng cố.

| # | Tactic | Khi dùng |
|---:|---|---|
| 6 | Adoption in performance review | Reinforcement yếu |
| 7 | Publish usage by team | Cần accountability ở cấp nhóm |
| 8 | Track team-specific impact | Board hỏi ROI |
| 9 | Proxy productivity metric | Outcome thật còn khó đo |
| 10 | Daily habit challenge | Activation thấp |

Cảnh báo: track and reward rất dễ phản tác dụng nếu thưởng theo số prompt hoặc số lần đăng nhập. KPMG và JPMorgan là hai case cần nhớ ở đây.

### Move 3 — Cut the red tape

Dùng khi người dùng muốn thử nhưng bị chặn bởi procurement, legal, security, hoặc thiếu thời gian.

| # | Tactic | Khi dùng |
|---:|---|---|
| 11 | AI learning budget | Không có không gian thử an toàn |
| 12 | Approval owner | Procurement/legal chậm |
| 13 | Time to tinker | Người dùng nói "không có thời gian" |
| 14 | Multiple approved tools | Một công cụ không phù hợp mọi workflow |
| 15 | Employee tool nominations | Thiếu discovery từ dưới lên |

Ví dụ: thay vì để quy trình duyệt công cụ đi qua năm phòng ban trong 6-8 tuần, đặt một approval owner có SLA 5 ngày và phân loại rủi ro theo use case.

### Move 4 — Turn enthusiasts into teachers

Dùng khi power users có kỹ năng nhưng kỹ năng không lan ra cả nhóm.

| # | Tactic | Khi dùng |
|---:|---|---|
| 16 | Learning villages / FriAIdays | Kỹ năng bị phân mảnh |
| 17 | Show-and-tell ritual | Kiến thức không được chia sẻ đều |
| 18 | AI SWAT team | Team không biết workflow nào nên dùng AI |
| 19 | Hackathons / demos | Cần không gian thử nghiệm |
| 20 | Promotion signal for upleveling others | Power user giữ kỹ năng cho riêng mình |

Trong bối cảnh Việt Nam, FriAIdays nên có cả junior giỏi công cụ và senior được tin tưởng. Nếu chỉ có junior demo, người khác có thể xem đó là "trò của mấy bạn thích công nghệ".

### Move 5 — Prioritize high-impact tasks

Dùng khi tổ chức có quá nhiều thử nghiệm rời rạc và không biết tập trung ở đâu.

| # | Tactic | Khi dùng |
|---:|---|---|
| 21 | Support triage | Customer service workflow |
| 22 | Performance review prep | HR / manager workflow |
| 23 | Content creation | Content, course, marketing |
| 24 | AI personas for PM feedback | Product discovery |
| 25 | Internal evaluation tools | Cross-team eval workflow |

Một task đáng ưu tiên thường có volume cao, lặp lại nhiều, có baseline, rủi ro kiểm soát được, tích hợp được vào workflow hiện tại và có người chịu trách nhiệm rõ.

### Chọn tactic cho lab

Trong Product ROI Dashboard, mỗi nhóm chọn 3 tactics:

- Một tactic xử lý Awareness hoặc Desire.
- Một tactic xử lý measurement hoặc reinforcement.
- Một tactic xử lý readiness, workflow hoặc ưu tiên task.

Ví dụ cho call center:

| Tactic | Lý do chọn |
|---|---|
| Embed with teams | Xử lý Desire bằng cách giải thích trực tiếp theo workflow thật |
| Track team-specific impact | Gắn dashboard với productivity, quality, trust và value |
| FriAIdays | Xử lý Knowledge và Ability bằng peer learning |

---

## 9. Lab flow và deliverable

Day 23 dùng mô hình build → bị phản biện → sửa → nộp. Lý do là sinh viên thường không thiết kế được metric tốt ngay lần đầu. Red-team giúp nhìn ra vanity metric, rủi ro bị "chạy số", thiếu nguồn dữ liệu hoặc thiếu quy tắc quyết định.

### Flow trong lớp

| Block | Thời lượng | Việc cần làm | Output |
|---|---:|---|---|
| Block 1 | 60 phút | Lecture: adoption, metric ladder, measurement trap, Gartner Lite, ADKAR, tactics | Bộ từ vựng chung |
| Block 2 | 60 phút | Case study research + present | Case Evidence Matrix |
| Block 3 | 60 phút | Chọn 1 product, extract 2-4 workflows, build dashboard v1 | Bản nháp Parts A-B-C |
| Block 4 | 30 phút | Red-team attack theo vai CFO/User/Risk/Workflow owner | Cột Red-team risk |
| Block 5 | 30 phút | Sửa dashboard, thêm fix, viết decision memo, nộp | Final Product ROI Dashboard |

### Product ROI Dashboard gồm gì?

**Part A — Adoption Context**

- Product cụ thể, không phải "AI assistant" chung chung.
- Người dùng / team cụ thể.
- 2-4 core workflows.
- Vai trò của AI trong từng workflow.
- Human review point.
- Failure path.
- Main ADKAR barrier.
- 3 adoption tactics.

**Part B — ROI Dashboard**

Dashboard có 8 cột:

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|

Nên có metric ở cả cấp sản phẩm (product-level) và cấp workflow. Activation và engagement thường ở product-level. Productivity và quality thường cần tách theo workflow. Trust và value có thể ở product-level hoặc workflow-level tùy case.

**Part C — Dashboard Mock**

Mock nên có 4-6 tiles, ví dụ:

```text
[Activation]      [Productivity]
[Quality]         [Trust]
[Value]           [Decision: Continue / Pivot / Kill]
```

**Part D — Decision Memo**

Trả lời ngắn bốn câu:

1. Nhóm đề xuất continue / pivot / kill?
2. Metric mạnh nhất là gì và vì sao?
3. Metric nào đã thay sau red-team?
4. Trước khi scale cần làm gì?

### Red-team roles

| Role | Hỏi theo góc nào? | Câu hỏi mẫu |
|---|---|---|
| CFO | Bằng chứng tài chính | Active users không phải ROI. $ saved hoặc revenue lift nằm ở đâu? |
| User | Coercion / friction | Metric này có ép tôi dùng AI không? Nếu tôi không dùng thì sao? |
| Risk / Legal | Quality + compliance | Metric này có che lỗi, bias hoặc compliance risk không? Audit trail ở đâu? |
| Workflow owner | Khả năng vận hành | Data lấy từ đâu, ai pull report, ai chịu trách nhiệm? |

### Rubric gates

| Gate | Pass | Fail |
|---|---|---|
| Product + workflows | Product rõ + 2-4 workflows cụ thể | Product mơ hồ hoặc không có workflow |
| Metric quality | Có 4+ layers và paired metrics | Chỉ active users / prompt count |
| Red-team response | Col 7-8 có risk và fix rõ, ít nhất 2 thay đổi | Dashboard không đổi sau red-team |
| Data realism | Baseline, target, source, owner khả thi | Data source mơ hồ hoặc không đo được |
| Decision logic | Có continue / pivot / kill rule | Dashboard chỉ để trang trí |

### File liên quan

| Tài liệu | Link |
|---|---|
| README lab package | [README.md](README.md) |
| Lab assignment | [Day23-Lab-Assignment.md](Day23-Lab-Assignment.md) |
| Master worksheet | [01-worksheet.md](01-worksheet.md) |
| Case Evidence Matrix | [02-templates/00-case-evidence-matrix.md](02-templates/00-case-evidence-matrix.md) |
| Part A template | [02-templates/01-part-a-adoption-context.md](02-templates/01-part-a-adoption-context.md) |
| Part B template | [02-templates/02-part-b-roi-dashboard.md](02-templates/02-part-b-roi-dashboard.md) |
| Part C template | [02-templates/03-part-c-dashboard-mock.md](02-templates/03-part-c-dashboard-mock.md) |
| Part D template | [02-templates/04-part-d-decision-memo.md](02-templates/04-part-d-decision-memo.md) |
| Red-team template | [02-templates/05-red-team-template.md](02-templates/05-red-team-template.md) |
| Rubric chi tiết | [../../assessment/day23-rubric-requirements.md](../../assessment/day23-rubric-requirements.md) |

---

## 10. Source caveats và source bank

Không phải nguồn nào cũng có cùng độ tin cậy. Khi dùng case hoặc số liệu trong dashboard, memo, CV hoặc bài viết, cần nói rõ loại nguồn.

| Label | Nghĩa | Khi dùng |
|---|---|---|
| canonical | Academic, official government, hoặc nguồn chính thức có phương pháp rõ | Rogers, NPT, UK gov reports, JNCI/Oxford |
| practitioner | Vendor, consulting, company case study, industry playbook | OpenAI case, Prosci, BCG, McKinsey, Microsoft blog |
| synthesis | Tổng hợp để dạy trong lớp, không phải quote nguyên văn | Gartner Lite, Diffusion ≠ Normalization |
| pending verification | Có nguồn gợi ý nhưng chưa verify transcript/số liệu | Nansen / Stripe SuperAI notes |
| sample observation | Quan sát lớp học hoặc pattern nội bộ, không generalize | VN hierarchy, survey công khai dễ nhiễu |

### Cách đọc nguồn

- Không dùng headline kiểu "85% AI projects fail" nếu không có nguồn và ngữ cảnh rõ. Hãy dùng cách nói cụ thể hơn như "AI adoption value gap", "ROI reckoning" hoặc "pilot purgatory" với link nguồn.
- Vendor/company case study dùng được cho teaching case, nhưng phải ghi rõ đây là số liệu do công ty hoặc vendor công bố.
- Nansen và Stripe hữu ích nhưng đang để pending verification. Không trích số liệu exact nếu chưa xem transcript/video.
- Larridin và Worklytics là góc nhìn từ vendor. Dùng để hiểu measurement trap, không dùng như benchmark trung lập.

### Source bank

**Academic / canonical**

- R02 — [Rogers Diffusion summary, NCBI / National Academies](https://www.ncbi.nlm.nih.gov/books/NBK618128/)
- R03 — [May et al. 2009, Normalization Process Theory](https://link.springer.com/article/10.1186/1748-5908-4-29)
- R04 — [Gartner AI Maturity Model Toolkit](https://www.gartner.com/en/chief-information-officer/research/ai-maturity-model-toolkit)
- R17 — UK government Copilot reports: [Cross-government Copilot findings](https://www.gov.uk/government/publications/microsoft-365-copilot-experiment-cross-government-findings-report/microsoft-365-copilot-experiment-cross-government-findings-report-html) · [DWP Copilot trial evaluation](https://www.gov.uk/government/publications/an-evaluation-of-dwps-microsoft-copilot-365-trial/an-evaluation-of-dwps-microsoft-365-copilot-trial)
- R18 — [JNCI / Oxford Academic, MD Anderson Watson](https://academic.oup.com/jnci/article/109/5/djx113/3847623)

**Vendor / practitioner**

- R10 — [Prosci ADKAR](https://www.prosci.com/adkar/adkar-model)
- R11 — [Prosci AI change management](https://www.prosci.com/ai-change-management)
- R12 — [Microsoft Inside Track: Measuring Copilot rollout](https://www.microsoft.com/insidetrack/blog/measuring-the-success-of-our-microsoft-365-copilot-rollout-at-microsoft/)
- R13 — [Larridin: Measure AI ROI Beyond Surveys](https://larridin.com/ai-workflow-mapping/how-to-measure-ai-roi-beyond-surveys)
- R14 — [Worklytics: Proving Productivity Uplift](https://www.worklytics.co/resources/proving-productivity-uplift-ai-tool-adoption-pwc-2025-worklytics-data)
- R15 — [OpenAI Klarna case](https://openai.com/index/klarna/)
- R16 — [OpenAI Morgan Stanley case](https://openai.com/index/morgan-stanley/)
- R22 — Nansen / Stripe SuperAI talks, pending verification: [Nansen talk](https://www.youtube.com/watch?v=LdIC44npJOM) · [Stripe talk](https://www.youtube.com/watch?v=kWK8_dBUmCA)
- Tactics source — [Peter Yang: 25 proven tactics to accelerate AI adoption at your company](https://creatoreconomy.so/p/25-proven-tactics-to-accelerate-ai-adoption-at-your-company)

**Consulting / industry research**

- R05 — [McKinsey State of AI 2024](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai-2024)
- R06 — [BCG 2024 AI adoption value gap](https://www.bcg.com/press/24october2024-ai-adoption-in-2024-74-of-companies-struggle-to-achieve-and-scale-value)
- R19 — [KPMG enterprise AI pilots](https://kpmg.com/us/en/articles/2026/enterprise-ai-pilots.html) · [Salesforce: Why AI pilots fail](https://www.salesforce.com/news/stories/why-ai-pilots-fail/)
- R20 — [Gartner GenAI proof-of-concept abandonment prediction](https://www.gartner.com/en/newsroom/press-releases/2024-07-29-gartner-predicts-30-percent-of-generative-ai-projects-will-be-abandoned-after-proof-of-concept-by-end-of-2025)
- R21 — [IBM Think: Why enterprise AI projects stall before scale](https://www.ibm.com/think/insights/why-most-enterprise-ai-projects-stall-before-scale)

**Major news / cautionary cases**

- R23 — [Reuters: Klarna shifts AI focus, 2025](https://www.reuters.com/business/swedens-klarna-shifts-ai-focus-cost-cuts-growth-2025-09-10/)
- R24 — [Business Insider: KPMG AI usage dashboard, 2026-05](https://www.businessinsider.com/kpmg-dashboard-consultants-ai-adoption-use-tracker-employees-2026-5)
- R25 — [Business Insider: JPMorgan AI usage dashboards, 2026-04](https://www.businessinsider.com/jpmorgan-track-software-engineers-ai-use-dashboards-2026-4)
- R26 — [Business Insider: KPMG Spark Awards, 2026-03](https://www.businessinsider.com/kpmg-ai-spark-awards-cash-prizes-for-employee-ai-innovation-2026-3)

---

*Tài liệu tham khảo — Ngày 23: Change Management & AI Adoption*  
*VinUni A20 — AI Thực Chiến — Track 1 Product & Business*
