---
artifact: 3 — Quick Win Selection
bai-tap: Frame — chọn lát cắt làm trước
phase: Double Diamond vòng 1 · ◆ siết (hội tụ về 1 lựa chọn)
time: ~10 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 1-intake-breakdown.md · prompts/02-quick-win-challenge.md
nop-cuoi: Không — file trung gian (bản chốt phase này ở 3-FINAL-problem-framing.md)
---

# 2 — Quick Win: chọn lát cắt làm trước

Mục tiêu: từ 5–8 use case ở file `1`, chấm điểm nhanh và chốt **1 Quick Win** để pilot đầu tiên — kèm lý do chọn và lý do _không_ chọn các phần khác. Đây là nửa "siết lại" của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 1.

Lý do làm bước này: đây là quyết định quan trọng nhất của phase Frame. Quick Win **không phải** phần dễ nhất hay nghe hay nhất — là phần _chứng minh được giá trị nhanh và có người ủng hộ_. Chọn sai → pilot fail → mất uy tín → khó xin pilot tiếp. Nhóm phải chọn được _và bảo vệ được bằng lý do_, không bằng cảm tính.

Quy tắc: **điểm số chỉ là gợi ý, không phải đáp án.** Đừng để con số quyết thay nhóm — nó chỉ giúp so sánh.

## Bước 0 — Lấy 4–6 use case mạnh nhất từ file `1` (1 phút)

## Quy trình 10 phút

```text
1 phút  — Bước 0: chọn 4–6 ứng viên
5 phút  — Phần A: chấm điểm 4 trục
3 phút  — Phần B: 1 lý do nên / 1 lý do không cho top 2
1 phút  — Phần C: chốt + ai ủng hộ + cái KHÔNG chọn
```

---

## Phần A — Chấm điểm 4 trục (1–5 mỗi trục)

Câu hỏi phụ (tự trả lời):

- "Risk" ở đây là _sai thì mất gì_ — chọn đúng việc chính của user (task centrality) thì sai cũng đỡ đau; chọn việc lớn nhất thì sai rất đắt. Use case nào risk thấp thật?
- Use case nào có sẵn data + có người trong AI20k thật sự muốn dùng?

| Use case                                                | Impact | Feasibility | Evidence nhanh | Risk (cao = an toàn) | Tổng |
| ------------------------------------------------------- | :----: | :---------: | :------------: | :------------------: | :--: |
| Gom câu hỏi từ Discord và group theo topic              |   4    |      4      |       5        |          4           |  17  |
| Phát hiện confusion cluster                             |   4    |      3      |       4        |          3           |  14  |
| Ghi lại câu hỏi + đáp án instructor để trả lời sau live |   3    |      3      |       3        |          4           |  13  |
| Tạo recap sau live                                      |   3    |      3      |       4        |          3           |  13  |

(Thang điểm chi tiết: `templates/quick-win-scoring.md`.)

## Phần B — 1 lý do nên / 1 lý do không, cho top 2

**Ứng viên A — Gom câu hỏi từ Discord và group theo topic**

```text
Nên chọn vì:
- Trực tiếp giải quyết pain của instructor: họ cần biết chỗ nào nhiều học viên vướng mà không thể đọc toàn bộ chat.
- Feasibility cao với dữ liệu Discord hiện có; có thể demo nhanh bằng sample log và clustering rule/LLM.
- Evidence nhanh: có thể dựng pilot nhỏ với một kênh Discord ngay.
Không nên vì:
- Chỉ là lát cắt ban đầu, chưa trả lời hết nhu cầu “chatbot 24/7” hay “tự động trả lời học viên”.
```

**Ứng viên B — Phát hiện confusion cluster**

```text
Nên chọn vì:
- Cung cấp insight quan trọng cho instructor: biết concept nào đang bị hiểu nhầm nhiều.
- Giá trị ra quyết định cao nếu alert rõ ràng và đúng trọng tâm.
Không nên vì:
- Cần threshold và grouping chính xác; nếu sai dễ gây alert fatigue hoặc bỏ sót.
- Pilot đầu cần ít biến số hơn, nên tránh vào analytics phức tạp ngay.
```

## Phần C — Chốt Quick Win

- **Quick Win nhóm chọn**: Gom câu hỏi từ Discord và group theo topic.
- **Vì sao chọn cái này trước** (2–4 câu, bám điểm + impact + evidence nhanh): Đây là lát cắt có giá trị instructor rõ ràng, dễ demo và ít rủi ro hơn so với các chức năng phân tích sâu. Nó giúp instructor nắm nhanh điểm đau của lớp live mà không cần đọc tất cả chat, nên phù hợp với pilot nhỏ và có thể triển khai nhanh với dữ liệu Discord mẫu.
- **Ai trong AI20k sẽ ủng hộ pilot này** (và vì sao họ care — "có người ủng hộ" thường quan trọng hơn "impact cao"): Instructor và admin live sẽ ủng hộ vì nó giảm thời gian scan chat và cung cấp insight tức thì. Support coach live cũng sẽ care vì họ có thể biết nhóm nào gặp vấn đề mà không cần can thiệp thủ công.
- **Nhóm KHÔNG chọn gì + vì sao** (≥2 use case bị loại): 1. Phát hiện confusion cluster — vì cần cấu hình threshold và dễ alert fatigue, không phù hợp pilot đầu nếu chưa có dữ liệu lớn. 2. Tạo recap sau live — vì recap chỉ có thể làm tốt khi đã thu thập dữ liệu đủ và chưa phải lát cắt nhanh nhất cho pilot.

---

## Phát hiện ban đầu

- Use case tập trung vào giá trị trực tiếp cho instructor sẽ có xác suất thành công cao hơn các chức năng gián tiếp.
- Pilot này giúp xác định nhanh nhất xem Discord có thể cung cấp insight actionable cho instructor hay không.

## Câu hỏi mở (mang sang Problem Framing)

- Dữ liệu Discord mẫu của chúng ta gồm kênh, thread và reaction, hay chỉ text chat?
- Làm sao định nghĩa “same topic” đủ tốt để không group quá rộng hoặc quá chặt?
- Pilot sẽ demo với live session thật hay chỉ replay log mẫu?

---

## Tổng kiểm tra trước khi sang `3-FINAL-problem-framing.md`

| Hạng mục                                                 | Xong? |
| -------------------------------------------------------- | ----- |
| Có bảng chấm 4 trục cho ≥4 use case                      | /     |
| Chốt 1 Quick Win, lý do bám số/impact (không "nghe hay") | /     |
| Nêu rõ ai ủng hộ pilot này                               | /     |
| Ghi rõ ≥2 phần KHÔNG chọn + lý do                        | /     |

⚑ Đây là phần coach kiểm tra ở Mốc 1: _"Vì sao không làm full tool? Vì sao chọn lát cắt này trước?"_

Sau bước này, mở `3-FINAL-problem-framing.md` — đóng khung vấn đề thật (bản nộp của phase Frame).

_Liên quan: handbook §A3 · `templates/quick-win-scoring.md` · `prompts/02-quick-win-challenge.md`_
