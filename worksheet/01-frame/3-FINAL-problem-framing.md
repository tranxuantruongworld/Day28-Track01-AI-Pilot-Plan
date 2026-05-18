---
artifact: 4 — Problem Framing (bản nộp phase Frame)
bai-tap: Frame — đóng khung vấn đề thật
phase: Double Diamond vòng 1 · ◆ output (chốt — owner xác nhận)
time: ~13 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 2-quick-win.md · prompts/03-problem-framing-challenge.md
nop-cuoi: Có — đây là bản nộp của phase Frame (Part A · A3 Working Canvas mục Problem Framing)
---

# 3 — FINAL: Problem Framing

Mục tiêu: đóng khung Quick Win đã chọn cho thật cụ thể. Đây **không phải** bản đề xuất giải pháp — là tài liệu trả lời đúng 1 câu: _"nhóm đã hiểu đúng vấn đề chưa?"_. Đây là output chốt của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 1, và là một mục trong A3 Working Canvas nộp cuối buổi.

Lý do làm bước này: một AI Pilot Plan cho vấn đề SAI — dù viết hay — vẫn sai. Đa số nhóm trượt Gate 3 vì khung chung chung ("học viên cần học tốt hơn", "coach quá tải") — câu đó không đo được, không ai chịu trách nhiệm, không biết khi nào thành công.

Quy tắc: **pain phải có số.** "Nhiều người phàn nàn" không phải evidence. "200 câu hỏi/tuần × 20 phút = 67 giờ/tuần" mới là evidence. Trong lab dùng số giả định cũng được, nhưng phải nói rõ số đến từ đâu.

## Quy trình 13 phút

```text
9 phút  — Điền 9 mục Problem Framing
3 phút  — Tự phản biện
1 phút  — Chốt: owner (giả định) có xác nhận đúng vấn đề không
```

---

## 9 mục Problem Framing

Câu hỏi phụ (tự trả lời trước khi điền):

- Một người ngoài đọc khung này có biết CHÍNH XÁC ai đau, đau cái gì không?
- Nếu KHÔNG có baseline thì nhóm đo "tốt hơn" bằng cách nào?
- Mục Open Questions trống = nguy hiểm (chưa nghĩ đủ). Nhóm còn chưa biết gì?

### Trả lời

1. **Original Ask** (stakeholder nói gì, nguyên văn): Agent hỗ trợ lớp live: gom câu hỏi, cluster confusion, recap, poll.
2. **Reframed problem** (vấn đề thật sau khi tách): Instructor live cần một cách tự động gom và nhóm câu hỏi Discord theo topic để biết chỗ nào nhiều học viên vướng, vì hiện tại họ phải đọc chat thủ công và có thể bỏ sót vấn đề quan trọng.
3. **Current workflow** (hiện tại đang xử lý thế nào, kể cả "không ai làm gì"): Instructor đọc chat thủ công, dùng thread tay, không có công cụ gom câu hỏi. Họ phải tự lọc các tin nhắn Discord bằng mắt, rất tốn thời gian và dễ bỏ sót các câu hỏi tương tự.
4. **Pain evidence — bằng SỐ** (ai đau · đau ở khoảnh khắc nào trong việc · tần suất · quy mô; số giả định ghi rõ nguồn giả định):

```text
- Trong một buổi live, Discord tạo ra 100+ tin nhắn, trong đó 10-15 là câu hỏi thật sự cần xử lý.
- Instructor mất khoảng 20 phút mỗi buổi để đọc toàn bộ chat và lọc lại các câu hỏi có cùng chủ đề.
- Do không có công cụ gom câu hỏi, instructor dễ bỏ sót các vấn đề lặp lại và không biết phần nào của bài học cần nhấn mạnh lại.
- Các lớp live AI20k thường có 1-2 instructor/admin theo dõi mỗi buổi, nên thời gian đọc chat này nhân lên với số buổi và nhóm.
- Các số liệu trên là giả định dựa trên kinh nghiệm đọc Discord live của track và bối cảnh AI20k.
```

5. **Affected people** (ai dùng · ai quyết · ai là người review/expert): Instructor live dùng; admin track track kết quả; lead instructor review.
6. **Constraints** (từ `00-context.md`: privacy / human review / citation / budget / formative / adoption): Privacy: không dùng data học viên nhạy cảm ngoài nội dung public Discord; Human review: instructor phải review output bot trước khi dựa vào; Citation: nếu bot trích nguồn câu hỏi/đáp, phải rõ nguồn; Budget: pilot cần dùng tool/API sẵn có, không xây nền tảng lớn; Formative: pilot chỉ hỗ trợ feedback/chỉ báo nội dung, không thay thế quyết định giảng dạy; Adoption: giá trị chỉ khi instructor thực sự dùng và thấy tiết kiệm thời gian.
7. **Quick Win đã chọn** (1 dòng, lấy từ file `2`): Gom câu hỏi từ Discord và group theo topic.
8. **Open questions** (còn chưa biết gì — không được để trống): Có sample log Discord để demo không? Dữ liệu Discord gồm thread/reaction hay chỉ text text? Cách xác định “same topic” đủ chính xác để không group quá rộng hoặc quá chặt? Pilot sẽ chạy realtime trong live hay chỉ trên bản ghi chat?
9. **Validation** (đóng vai owner: _"đúng, đây là vấn đề đáng giải"_ — Có / Chưa, vì sao):

```text
Có — vì vấn đề này nhắm trực tiếp vào pain của instructor live: họ cần biết phần nào của buổi học có nhiều học viên vướng mà không thể đọc hết chat tay. Nếu pilot giúp giảm 20 phút đọc chat mỗi buổi và tạo insight topic nhanh, thì đây là vấn đề đáng giải.
```

---

## Tự phản biện

- Khung này còn câu chung chung kiểu "cần học tốt hơn" không?
- 3 câu sẽ bị hỏi: _số/giả định lấy ở đâu · giả định chính sai thì sao · tình huống nào khiến dừng._ Trả lời thử 1 câu.

---

## Tổng kiểm tra trước khi sang `02-solution/`

| Hạng mục                                                            | Xong? |
| ------------------------------------------------------------------- | ----- |
| Chỉ rõ 1 nhóm người + 1 khoảnh khắc cụ thể (không "user nói chung") | /     |
| Pain có số (hoặc kế hoạch lấy số), nói rõ số từ đâu                 | /     |
| Có baseline (hoặc cách đo baseline) + ≥1 chỉ số có ngưỡng           | /     |
| Mục 9: owner (giả định) xác nhận đúng vấn đề = qua cổng phase Frame | /     |

⚑ Coach kiểm tra ở Mốc 2: _"Ai đau? Baseline là gì? Không có baseline thì đo thế nào?"_

Owner chưa xác nhận → quay lại file `1`/`2`, đừng sang Solution. Owner xác nhận → mở `../02-solution/1-find-existing-solutions.md`.

_Liên quan: handbook §A4 · `prompts/03-problem-framing-challenge.md`_
