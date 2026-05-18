---
artifact: 5 — Solution Approach (phần khám phá)
bai-tap: Solution — tìm lời giải đã có sẵn trước khi tự xây
phase: Double Diamond vòng 2 · ◇ giãn (mở hết lựa chọn, chưa chốt)
time: ~8 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 01-frame/3-FINAL-problem-framing.md · 00-context.md · prompts/04-find-solutions.md
nop-cuoi: Không — file trung gian (bản chốt ở 2-FINAL-solution.md)
---

# 1 — Find existing solutions (đừng xây lại từ số 0)

Mục tiêu: trước khi quyết Build / Buy / Boost / Partner, nhóm phải biết bài này đã có ai giải ở chỗ khác chưa, và họ giải bằng cách nào. Đây là nửa "giãn ra" của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 2 — mở hết các lời giải đang tồn tại, chưa chốt cái nào.

Lý do làm bước này: đây là chỗ nhiều nhóm hỏng mà không biết. Hỏng vì nhảy thẳng vào "tự build" cho oai, trong khi 80–90% nhu cầu nội bộ chỉ cần Boost hoặc Buy. Hỏng vì không hỏi "ai làm rồi" nên đi lại từ số 0. Gần như bài nào cũng đã có người giải ở một ngành khác — không thấy thì phí cả pilot.

Quy tắc: **không có nguồn = giả định.** Mỗi cái AI/web nói ra, hỏi lại "lấy ở đâu?". Không chỉ được nguồn thì đánh dấu 🧮 (giả định để giảng), đừng xài như fact.

## Bước 0 — Bài này thực ra là dạng bài gì? (2 phút)

Bỏ context AI20k sang một bên. Mô tả Quick Win của nhóm như một bài toán chung — không có chữ "học viên / coach / Discord". Vài ví dụ cho dễ hình dung:

- "câu hỏi của user → câu trả lời kèm nguồn" → đây là bài Q&A có citation
- "một đống văn bản lộn xộn → data có cấu trúc" → bài extraction
- "bài nộp → nhận xét theo rubric" → bài rubric grading

Dạng bài (the pattern) đó gần như chắc chắn đã có người làm ở ngành khác. Tìm ra dạng bài → tìm ra người đã giải nó.

- **Quick Win của nhóm, viết lại thành 1 dạng bài chung (không có chữ domain)**: Chuyển một luồng chat trực tiếp lộn xộn thành các nhóm câu hỏi theo chủ đề để người hỗ trợ biết chỗ nào cần giải thích lại.
- **Input → output thực chất là gì**: Tin nhắn chat thời gian thực → cụm câu hỏi/topic clusters.
- **Ràng buộc không bỏ được (lấy từ `00-context.md`)**: Privacy, human review, citation, budget nhỏ, formative, adoption.

## Quy trình 8 phút

```text
2 phút  — Bước 0: gọi tên dạng bài
4 phút  — Phần A: deep research 4 tầng "ai giải dạng bài này rồi"
2 phút  — Phần B: rút về 2–3 hướng khả thi, đánh dấu nguồn
```

---

## Phần A — Deep research: ai giải dạng bài này rồi, giải sao?

Không phải gõ 1 câu vào AI rồi chép. Chạy 4 tầng, **tầng sau lấy kết quả tầng trước làm input**. Khung câu lệnh ở `prompts/04-find-solutions.md`.

Câu hỏi phụ (tự trả lời — viết ra cái nhóm _tìm thấy_, không phải cái nhóm _đoán_):

- Dạng bài này giống bài nào ở một ngành hoàn toàn khác?
- Hướng nào AI gợi ý mà nhóm **không kiểm được nguồn** — vậy có nên tin không?
- Một ca thất bại của người đi trước dạy nhóm tránh đúng điều gì?
- Nhóm "đi từ mức mấy" — kế thừa được gì để khỏi bắt đầu từ 0?

### Trả lời — điền theo 4 tầng

| Tầng           | Hỏi AI/web câu gì                                                                                  | Tìm được gì                                                                                                                                                                                                                                                                 | Nguồn / 🧮 nếu là giả định                                                       |
| -------------- | -------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| 1 · Map        | "Dạng bài này thường giải bằng những hướng nào? 4–6 hướng, mỗi hướng khi nào nên dùng."            | Chat analytics / conversational summarization / question clustering / meeting intelligence / support ticket triage. Thường dùng embeddings + semantic similarity cho grouping, hoặc rules + keyword extraction khi data nhỏ.                                                | 🧮 tổng hợp từ các bài toán NLP phổ biến và các sản phẩm chat analytics hiện có. |
| 2 · Tiền lệ    | "Đội nào (ngành bất kỳ) đã làm dạng bài này ở quy mô tương tự? Họ làm cách nào?"                   | Customer support platforms (Zendesk, Freshdesk) dùng ticket classification / topic clustering; meeting assistants (Otter.ai, Fireflies) dùng transcript summarization; education forums (Piazza, Stack Overflow for Teams) dùng thread/topic grouping cho câu hỏi tương tự. | 🧮 dựa trên kiến thức sản phẩm công nghiệp và các case study công khai.          |
| 3 · Phản chứng | "Ca nào làm dạng bài này thất bại? Nguyên nhân gốc là cách làm hay chuyện khác?"                   | Nhiều giải pháp thất bại do alert/summarization quá generic, tạo ra quá nhiều noise và không phân biệt được câu hỏi thực sự. Nếu không có human review, bot dễ đưa ra nhóm/topic sai, gây mất niềm tin.                                                                     | 🧮 từ phân tích thất bại chung của các hệ thống chat/meeting AI.                 |
| 4 · Thu hẹp    | "Với ràng buộc [budget nhỏ · có người review · cần citation], hướng nào khả thi cho pilot 6 tuần?" | Khả thi nhất là dùng existing LLM/embedding API để semantically cluster chat, rồi hiển thị kết quả cho instructor review. Không nên build model riêng, cũng không nên phụ thuộc tool chưa hiểu rõ.                                                                          | 🧮 kinh nghiệm pilot AI nhỏ: dùng API sẵn, minimal custom logic.                 |

---

## Phần B — Rút về 2–3 hướng khả thi

Câu hỏi phụ:

- Hướng nào _kế thừa được nhiều nhất_ từ người đã làm?
- Hướng nào nghe hay nhưng nhóm **không có nguồn** để tin?

### Trả lời

| Hướng giải khả thi                                                                           | Ai làm rồi (gần bài mình nhất)                                           | Nguồn / 🧮                                                 | Hợp ràng buộc `00-context`?                                                        |
| -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ | ---------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Boost dùng LLM/embedding API để cluster chat Discord và hiển thị topic cho instructor review | Otter.ai/Fireflies (meeting summarization) + Zendesk (ticket clustering) | 🧮 case phổ biến của meeting assistants và support triage  | Có — budget nhỏ, human review, citation dễ thực hiện vì output kèm nguồn tin nhắn. |
| Buy/adapt existing chat summarization bot cho Discord (nếu có)                               | Các bot Discord/editor như Sesh, Guilded summaries                       | 🧮 chưa xác định tool cụ thể cho Discord live Q&A          | Có/Không — nếu tồn tại, có thể tiết kiệm build nhưng cần kiểm tra fit.             |
| Build lightweight Discord bot custom pipeline dùng embeddings + rule-based clustering        | Một số startup edtech tự xây Q&A aggregator                              | 🧮 dựa trên cách nhiều team R&D hiện thực proof-of-concept | Không ưu tiên — budget/time hạn chế và pilot nên tận dụng API sẵn.                 |

**"Đi từ 5 lên" — nhóm kế thừa cụ thể cái gì** (1–2 câu):

```text
Nhóm đi từ 5 lên bằng cách tận dụng pattern chat/question clustering đã có ở support triage và transcript summarization, thay vì xây full bot trả lời. Cụ thể là dùng embeddings + semantic grouping rồi thêm layer review cho instructor.
```

---

## Phát hiện ban đầu

Ghi nhanh 2–3 cái đáng chú ý nhất (chưa phải quyết định — quyết định ở file FINAL):

- Giải pháp có vẻ gần nhất với customer support ticket triage và meeting intelligence hơn là chatbot Q&A toàn diện.
- Pilot nên tập trung vào “cluster câu hỏi” thay vì cố gắng trả lời tự động, để giảm risk và tăng adoption.
- Nếu có tool Discord summarization sẵn, cần kiểm tra fit với live chat và việc trích nguồn rõ ràng.

## Câu hỏi mở (mang sang bước chốt)

- Có tool Discord hiện tại trong AI20k mà nhóm có thể tận dụng không?
- Dữ liệu sample Discord live có thể dùng để test clustering chưa?
- Instructor muốn output hiển thị cách nào: danh sách topic, số lượng câu hỏi, hay đề xuất câu nói lại?

---

## Tổng kiểm tra trước khi sang `2-FINAL-solution.md`

| Hạng mục                                               | Xong? |
| ------------------------------------------------------ | ----- |
| Gọi được dạng bài trong 1 câu, không còn chữ domain    | /     |
| Đủ 4 tầng deep research, tầng nào cũng có kết quả      | /     |
| Mỗi kết quả có nguồn, hoặc đánh dấu 🧮 nếu là giả định | /     |
| Rút về 2–3 hướng + nói được "đi từ 5 lên" cái gì       | /     |

Hàng nào chưa xong → quay lại Phần A, đừng sang bước chốt vội.

Sau bước này, mở `2-FINAL-solution.md` — chốt Build/Buy/Boost/Partner + data & ai review + bản vẽ trực quan (đây là bản nộp của phase này).

_Liên quan: handbook §A5 · `prompts/04-find-solutions.md` · `00-context.md`_
