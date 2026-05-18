---
artifact: 1 — Track & Big Ask + 2 — Tool Breakdown
bai-tap: Frame — nghe đúng đề rồi tách nhỏ
phase: Double Diamond vòng 1 · ◇ giãn (nghe rộng, chưa chốt)
time: ~12 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 00-context.md · track card · prompts/01-breakdown.md
nop-cuoi: Không — file trung gian (bản chốt phase này ở 3-FINAL-problem-framing.md)
---

# 1 — Intake & Breakdown: nghe đúng đề, tách nhỏ

Mục tiêu: cả nhóm hiểu giống nhau "công cụ lớn stakeholder muốn", rồi tách nó thành 5–8 use case nhỏ làm được riêng. Đây là nửa "giãn ra" của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 1 — nghe rộng, tách rộng, chưa chọn.

Lý do làm bước này: hai cái bẫy chết người ở đây. Một, nhận đề literal ("làm con chatbot") rồi nhảy vào build — trong khi yêu cầu mơ hồ thường chỉ là triệu chứng. Hai, ôm cả công cụ lớn đi pitch "build cả platform" → trượt Gate 1 ngay. Tách nhỏ là động tác bắt buộc để từ "một ý tưởng to" sang "danh sách phần làm được".

Quy tắc: **nghe trước, tách trước, chưa chọn.** Bước này không được chốt Quick Win (việc đó ở file `2`).

## Bước 0 — Đọc track card + 00-context (2 phút)

Đọc track card được giao và `00-context.md` (mục 2 đã điền). Đừng lướt.

## Quy trình 12 phút

```text
2 phút  — Bước 0: đọc track card + context
4 phút  — Phần A: phát biểu lại Big Ask bằng lời nhóm
6 phút  — Phần B: tách 5–8 use case + check độc lập
```

---

## Phần A — Phát biểu lại Big Ask bằng lời nhóm

Đừng chép lại đề. Cả nhóm nói lại "công cụ lớn stakeholder muốn" bằng lời mình. Nếu 3 người nói 3 kiểu khác nhau → chưa hiểu giống nhau, bàn thêm.

Câu hỏi phụ (tự trả lời):

- Stakeholder nói họ muốn gì, và họ thực sự _cần_ gì — có khác nhau không?
- "Tại sao bây giờ?" — ở quy mô ~500 người, cái gì đang đau khiến phải làm công cụ này lúc này?
- Ai là người dùng đầu tiên thật sự, không phải "cả khóa"?

### Trả lời

- **Big Ask, viết lại bằng lời nhóm (2–3 câu)**: Stakeholder cần một trợ lý lớp live trên Discord để tự động gom câu hỏi, nhận diện chỗ nhiều người vướng, lưu lại câu trả lời instructor và tạo recap/feedback, giúp instructor/admin nắm được điểm đau mà không phải đọc hết chat tay.
- **Tại sao bây giờ**: Với quy mô ~500 học viên và nhiều lớp live, Discord chứa quá nhiều câu hỏi rải rác; instructor không kịp bắt được pattern và chưa có công cụ tự động cảnh báo confusion point.
- **Người dùng đầu tiên cụ thể**: Instructor / Admin trong lớp live, người cần nắm nhanh vấn đề của nhóm học viên.

## Phần B — Tách công cụ lớn thành 5–8 use case

Nhìn mục **Big Vision Modules** trong track card. Mỗi dòng = 1 use case làm được riêng, viết dạng _"AI làm X cho ai để họ Y"_ — không phải tính năng mơ hồ. Cần 5–8 dòng (ít hơn 5 = chưa tách đủ; nhiều hơn 8 = đang liệt kê vụn).

| #   | Use case (AI làm gì · cho ai · để họ làm được gì)                                           | Người dùng         | Làm được độc lập? |
| --- | ------------------------------------------------------------------------------------------- | ------------------ | ----------------- |
| 1   | Gom câu hỏi từ Discord và group theo topic để instructor thấy chỗ nhiều người vướng         | Instructor         | Có                |
| 2   | Phát hiện confusion cluster khi nhiều học viên hỏi cùng một concept và cảnh báo instructor  | Instructor         | Có                |
| 3   | Ghi lại câu hỏi + đáp án instructor trong live để trả lời lại học viên sau buổi khi cần     | Instructor         | Có                |
| 4   | Tạo recap sau live: top câu hỏi, confusion point, và đề xuất follow-up cho instructor/admin | Instructor / Admin | Có                |
| 5   | Phát poll nhanh / thu feedback sau live để xác định điểm khó và mức độ cần giải thích lại   | Instructor         | Có                |
| 6   | Lọc spam / nội dung nhạy cảm trên Discord và gửi cảnh báo review cho admin/instructor       | Admin / Instructor | Có                |
| 7   |                                                                                             |                    |                   |
| 8   |                                                                                             |                    |                   |

Cần ít nhất **4 use case thật sự độc lập** (làm được mà không cần cái khác xong trước). Nếu nhiều cái phụ thuộc nhau → gộp hoặc viết lại cho tách bạch.

---

## Phát hiện ban đầu

- Công cụ cần tập trung vào giá trị cho instructor/admin, không phải chatbot trả lời học viên 24/7 toàn bộ.
- Dữ liệu Discord rất lộn xộn; cần ưu tiên lọc spam & bảo vệ thông tin nhạy cảm ngay từ đầu.

## Câu hỏi mở (mang sang bước chọn Quick Win)

- Use case nào cho instructor/admin có thể demo nhanh nhất với dữ liệu mẫu Discord? (group câu hỏi hay confusion alert?)
- Chúng ta có sẵn log Discord hoặc cách test poll/feedback ngay trong buổi live không?
- Confusion point định nghĩa thế nào để không báo quá nhiều và không bỏ sót?

---

## Tổng kiểm tra trước khi sang `2-quick-win.md`

| Hạng mục                                                      | Xong? |
| ------------------------------------------------------------- | ----- |
| Cả nhóm phát biểu lại Big Ask giống nhau, không cần nhìn card | /     |
| Có 5–8 use case dạng "AI làm X cho ai để Y"                   | /     |
| Có ≥4 use case thật sự độc lập                                | /     |
| Nhóm KHÔNG còn ý định pitch "build cả platform"               | /     |

Sau bước này, mở `2-quick-win.md` — chấm điểm chọn 1 lát cắt làm trước.

_Liên quan: handbook §A1+§A2 · `prompts/01-breakdown.md` · `00-context.md`_
