---
artifact: 5 — Solution Approach + 6 — Demo/Mockup/Flow (bản nộp phase Solution)
bai-tap: Solution — chốt cách làm + cho stakeholder nhìn thấy
phase: Double Diamond vòng 2 · ◆ siết (chốt 1 cách làm + 1 artifact trực quan)
time: ~12 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 1-find-existing-solutions.md · 00-context.md · templates/demo-examples.md · prompts/05-demo-challenge.md
nop-cuoi: Có — bản nộp của phase Solution (Part B + C · A3 mục Solution Approach + Demo/Mockup/Flow)
---

# 2 — FINAL: Solution Approach + Demo/Mockup/Flow

Mục tiêu: chốt cách làm cho Quick Win (Build / Buy / Boost / Partner), nói rõ data & ai review cần có, và tạo 1 bản vẽ trực quan để stakeholder _nhìn_ được. Đây là nửa "siết lại" của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 2 và là bản nộp của phase Solution.

Lý do làm bước này: hai cái bẫy. Một, "tự build" cho oai — trong khi 80–90% nhu cầu nội bộ chỉ cần Boost/Buy; tự build là quyết định khó rút lại nhất. Hai, chỉ nói bằng chữ — stakeholder không duyệt một đoạn văn, họ duyệt khi _nhìn thấy_ flow. Không có bản vẽ → trượt Gate 4 dù lập luận tốt.

Quy tắc: **bản vẽ trực quan là BẮT BUỘC; demo chạy được chỉ là điểm cộng.** _Demo đơn giản + lập luận chặt > demo đẹp + lập luận yếu._

## Quy trình 12 phút

```text
4 phút  — Phần A: chốt Build/Buy/Boost/Partner (decision tree + ego check)
3 phút  — Phần B: data & ai review cần có
5 phút  — Phần C: vẽ 1 artifact trực quan + đánh dấu chỗ người review
```

---

## Phần A — Chốt cách làm

Đi decision tree, đừng chọn theo cảm giác:

```text
Bài này có phải LỢI THẾ CẠNH TRANH CỐT LÕI không?
 ├─ CÓ  → đội có AI engineer mạnh? CÓ → Build · KHÔNG → Boost
 └─ KHÔNG (chỉ là productivity layer) → có tool sẵn?
          CÓ → Buy · KHÔNG → Boost (model sẵn + data riêng)
```

Câu hỏi phụ:

- Nhóm chọn cách này vì _cần_ hay vì _thích tự build_? Một câu thành thật.
- Hướng nào ở file `1` (đã tìm được người làm rồi) khớp với cách này — "đi từ 5 lên"?

### Trả lời

- **Cách làm chốt**: Boost
- **Lý do CẦN (không phải thích), 2–3 câu**: Quick Win là một productivity layer cho instructor, không phải core product AI20k. Nhóm không cần tự build NLP từ đầu mà nên tận dụng LLM/embedding API đã có để xem Discord chat dưới dạng topic clusters. Đây là cách nhanh nhất để có pilot với budget nhỏ, vẫn giải được bài toán chính và giữ được human review.
- **Vì sao KHÔNG "Build từ số 0"**: Vì bài toán không yêu cầu lợi thế cạnh tranh độc quyền mà cần giải một bài common pattern (chat/question clustering). Build từ số 0 sẽ tốn thời gian và rủi ro cao hơn so với dùng API/embedding service sẵn có để prototype.
- **Tool / API / vendor cần + ước lượng chi phí thô** (budget nhỏ, ưu tiên sẵn có): Discord API để lấy chat; OpenAI/Azure OpenAI embeddings + chat completion để cluster và generate topic labels; một UI nhẹ (Google Sheets / Notion / Figma mockup / simple web app) cho instructor review. Chi phí API ước lượng ~ $50-100/pilot dựa trên 500-1000 tin nhắn demo.

## Phần B — Data & ai review (cách làm này cần gì để chạy được)

| Cần gì                                  | Có sẵn trong AI20k?                     | Trong lab dùng (mẫu/giả định)                                | Privacy?                                                                 |
| --------------------------------------- | --------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------------------ |
| Discord chat live từ 1-2 buổi           | Có nếu beeline thử nghiệm trên kênh lớp | Dùng sample log Discord / giả định 1 buổi 100+ tin nhắn      | Chỉ dùng nội dung public channel, không dùng PII / data nhạy cảm cá nhân |
| Câu trả lời instructor / context chủ đề | Có thể thu từ instructor demo           | Dùng ví dụ câu trả lời instructor, title bài học, tag chủ đề | Output kèm trích nguồn tin nhắn gốc để minh bạch                         |

- **Output nào rủi ro cao** (sai gây hậu quả): Topic clustering sai khiến instructor ưu tiên nhầm phần, hoặc bỏ qua confusion point quan trọng. Nếu bot group nhầm query, instructor có thể mất trust vào tool.
- **Ai review + bao nhiêu mẫu + pass/fail theo gì**: Instructor live review trực tiếp các nhóm câu hỏi trong pilot, đánh giá 5-10 cluster đầu tiên; pass nếu ≥80% cluster phản ánh đúng chủ đề và không có nhóm sao chép/bê nguyên một câu hỏi không cùng topic. Admin/lead instructor kiểm tra với 1-2 buổi thật để xác nhận usability.
- **Có cần citation / nói "không biết" khi thiếu nguồn không**: Có — output cần kèm nguồn tin nhắn gốc và nếu không rõ topic thì bot phải đánh dấu "topic chưa rõ" thay vì bịa nhãn.

## Phần C — Bản vẽ trực quan (BẮT BUỘC)

```text
[Discord Live Chat] -> [Capture message stream từ channel] -> [Extract câu hỏi + metadata]
                                      |
                                      v
                            [Embedding + semantic similarity]
                                      |
                                      v
                   [Cluster câu hỏi theo topic / số lượng câu hỏi]
                                      |
                                      v
                [UI Instructor xem topic + xem tin nhắn gốc]
                                      |
                                      v
                        [Instructor xác nhận / điều chỉnh]

Example output:
- Topic 1: "difference between Quick Win and Pilot Plan" (5 câu)
   + Source: msg #23, #45, #78
- Topic 2: "data privacy for learner info" (3 câu)
   + Source: msg #52, #60
- Topic 3: "how to write Problem Framing" (4 câu)
   + Source: msg #12, #29

Chỗ con người review (output rủi ro cao) nằm ở:
- Instructor review các nhóm topic và tin nhắn gốc trước khi dùng thông tin để điều chỉnh live.
- Nếu bot không chắc, instructor nên giữ quyền điều chỉnh nhãn / gộp / tách cluster.
```

Câu hỏi phụ — một người đóng vai stakeholder nhìn 20 giây: _hiểu user làm gì, nhận lại gì, không cần giải thích thêm không? Có chỗ nào "đẹp nhưng rỗng" không?_

---

## Tổng kiểm tra trước khi sang `../03-pilot-plan/`

| Hạng mục                                                | Xong? |
| ------------------------------------------------------- | ----- |
| Cách làm có lý do CẦN, không phải "mặc định tự build"   | /     |
| Nói rõ data cần + ai review output rủi ro cao           | /     |
| Có ≥1 bản vẽ trực quan, người ngoài hiểu trong ~20 giây | /     |
| Có đánh dấu chỗ con người review                        | /     |

⚑ Coach kiểm tra ở Mốc 3: _"Stakeholder nhìn vào đâu để hiểu flow? Mockup/sketch/demo đâu?"_ Chỉ nói bằng chữ = chưa qua.

Sau bước này, mở `../03-pilot-plan/1-pilot-plan.md`.

_Liên quan: handbook §A5+§A6 · `templates/demo-examples.md` · `prompts/05-demo-challenge.md`_
