---
artifact: 8 — 5-slide Pitch + AI Support Log (bản nộp cuối lab)
bai-tap: Pilot Plan — dồn thành pitch, sẵn sàng phản biện
phase: Double Diamond vòng 2 · ◆ output (bản nộp cuối + present)
time: ~5 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 1-pilot-plan.md + toàn bộ 01-frame + 02-solution · templates/5-slide-pitch.md
nop-cuoi: Có — bản nộp cuối lab (Part E · 5-slide Pitch + AI Support Log)
---

# 2 — FINAL: 5-slide Pitch + AI Support Log

Mục tiêu: dồn cả A3 Working Canvas thành 5 slide pitch (5 phút), chuẩn bị trả lời 3 câu phản biện, và ghi AI Support Log. Đây là bản nộp cuối cùng của lab.

Lý do làm bước này: nguyên tắc _demo đơn giản + lập luận chặt > demo đẹp + lập luận yếu_. Slide đẹp mà không trả lời được "số này lấy ở đâu" thì hỏng. Pitch không phải kể chuyện — là đưa evidence để stakeholder ra được một quyết định.

Quy tắc: **slide cuối phải là một lời xin rõ ràng** (xin gì · đổi lại hứa gì). Không có lời xin = stakeholder không biết approve cái gì.

## Quy trình 5 phút

```text
3 phút  — Dồn 5 slide (mỗi slide 1 thông điệp)
1 phút  — Chuẩn bị 3 câu phản biện
1 phút  — AI Support Log
```

---

## Phần A — 5 slide (mỗi slide 1 thông điệp)

| #                                                                                                                                | Slide                                | Lấy từ              | Nội dung 1–2 gạch đầu dòng                                                        | Ai nói |
| -------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ | ------------------- | --------------------------------------------------------------------------------- | ------ |
| 1                                                                                                                                | Problem & user                       | 01-frame/3-FINAL    | - Instructor live phải đọc >100 tin nhắn Discord mỗi buổi.                        |
| - 10-15 câu hỏi cần xử lý, mất ~20 phút lọc thông tin.                                                                           | Trần Xuân Trường                     |
| 2                                                                                                                                | Breakdown & Quick Win                | 01-frame/1,2        | - Tách 6 use case, chọn Quick Win: gom câu hỏi Discord và group theo topic.       |
| - Đây là lát cắt có giá trị nhanh, thấp rủi ro và dễ demo.                                                                       | Trần Xuân Trường                     |
| 3                                                                                                                                | Solution + bản vẽ trực quan          | 02-solution/2-FINAL | - Boost: dùng embeddings/API để cluster câu hỏi, hiển thị topic + nguồn tin nhắn. |
| - Instructor review trước khi dùng, giảm noise và giữ human-in-the-loop.                                                         | Trần Xuân Trường                     |
| 4                                                                                                                                | AI Pilot Plan                        | 03-pilot-plan/1     | - Pilot 2 tuần, thử 1-2 buổi live, dùng sample Discord chat.                      |
| - Budget nhỏ, review output bởi instructor, dừng nếu accuracy <60%.                                                              | Trần Xuân Trường                     |
| 5                                                                                                                                | Metric · exit criteria · **lời xin** | 03-pilot-plan/1     | - Metric: ≥80% cluster chính xác, giảm ≥10 phút đọc chat, adoption ≥70%.          |
| - Lời xin: Xin 2 tuần pilot + access sample Discord + support instructor review; đổi lại hứa evidence + dừng nếu không hiệu quả. | Trần Xuân Trường                     |

## Phần B — Chuẩn bị 3 câu phản biện

1. _"Số liệu / giả định này lấy ở đâu?"_ → Số liệu lấy từ quan sát Discord live: một buổi có 100+ tin nhắn, 10-15 câu hỏi cần phục vụ, instructor mất khoảng 20 phút để lọc. Những con số này là giả định dựa trên bối cảnh AI20k và có thể xác nhận với lead instructor bằng sample log.
2. _"Nếu giả định quan trọng nhất của bạn sai thì sao?"_ → Nếu chat không có đủ pattern để cluster, chúng tôi sẽ dùng pilot để thu thêm dữ liệu và chuyển dần sang hướng tóm tắt câu hỏi/making recap. Pilot vẫn có giá trị vì nó giúp xác định ngay liệu Discord có đủ signal để ưu tiên các phần cần giảng lại.
3. _"Tình huống nào sẽ khiến bạn dừng pilot?"_ → Nếu cluster accuracy thấp dưới 60% hoặc instructor từ chối dùng tool vì không tin tưởng, chúng tôi dừng pilot. Cụ thể, nếu trong 1-2 buổi live tool không được dùng trong ít nhất 50% thời gian review, pilot sẽ tạm dừng để điều chỉnh.

## Phần C — AI Support Log

| Câu hỏi                                            | Trả lời                                                                                                                                                            |
| -------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| AI giúp được gì trong lab này?                     | AI gợi ý cấu trúc pitch, đề xuất metrics và mockup flow, giúp nhóm đi nhanh từ overview sang pilot plan cụ thể.                                                    |
| AI đưa output nào nghe hợp lý nhưng nhóm phải sửa? | AI đề xuất nhiều hướng giải pháp và metrics chung chung; nhóm chỉnh lại thành cluster câu hỏi Discord, chọn Boost, và cụ thể hóa số liệu dựa trên context thực tế. |
| Phần nào nhóm tự lập luận, KHÔNG copy AI?          | Nhóm tự đánh giá Quick Win, quyết định pilot scope, chọn exit criteria, và viết lời xin/chống phản biện dựa trên bối cảnh track thực tế.                           |

---

## Tổng kiểm tra trước khi nộp

| Hạng mục                                                      | Xong? |
| ------------------------------------------------------------- | ----- |
| 5 slide, mỗi slide 1 thông điệp, đã phân ai nói slide nào     | /     |
| Slide 5 có lời xin rõ ràng (xin gì · hứa gì)                  | /     |
| Có câu trả lời sẵn cho cả 3 câu phản biện                     | /     |
| AI Support Log điền đủ 3 dòng                                 | /     |
| Tất cả file worksheet/ đã commit + push, link dán vào Discord | /     |

Đây là file cuối. Pitch 5 phút + nhận phản biện theo bảng 5 Gate (`templates/rubric-gate-sheet.md`).

_Liên quan: handbook §A9 · `templates/5-slide-pitch.md` · `templates/ai-support-log.md`_
