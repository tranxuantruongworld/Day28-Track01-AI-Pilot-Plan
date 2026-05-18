---
artifact: 7 — AI Pilot Plan core
bai-tap: Pilot Plan — cam kết hai chiều: xin – hứa – đo – dừng
phase: Double Diamond vòng 2 · ◇ giãn → ◆ siết (liệt kê hết rồi chốt gọn)
time: ~10 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 02-solution/2-FINAL-solution.md · 00-context.md · prompts/06-pilot-plan-challenge.md
nop-cuoi: Không — file trung gian (bản nộp ở 2-FINAL-pitch.md)
---

# 1 — AI Pilot Plan core

Mục tiêu: viết phần kế hoạch xin pilot — scope, người, data, budget, timeline, metric, exit criteria, adoption, lời hứa, lời xin. Bước này giãn ra (liệt kê hết những thứ cần) rồi siết lại (chốt bản gọn đủ để stakeholder quyết).

Lý do làm bước này: đây là thứ stakeholder dùng để **quyết approve hay dừng**. AI Pilot Plan **không phải proposal xin tiền** — là _cam kết hai chiều_: nhóm xin nguồn lực, đổi lại hứa giao evidence + chấp nhận dừng nếu metric fail. Demo đẹp mà không nói được "xin gì, hứa gì, đo gì, dừng khi nào" → trượt Gate 5.

Quy tắc: **budget tách từng hạng mục, không gộp 1 cục; không có mục "miscellaneous".** Exit criteria phải có người có quyền thực thi, không chỉ trên giấy.

## Quy trình 10 phút

```text
6 phút  — Điền 10 mục core (kéo nguyên liệu từ 00 + 01-frame + 02-solution)
3 phút  — Phần exit criteria + adoption (chỗ nhóm hay bỏ quên)
1 phút  — Tự phản biện
```

---

## 10 mục core

Câu hỏi phụ (tự trả lời):

- Nếu tóm vấn đề không gọn trong 1 câu → nhóm chưa hiểu vấn đề.
- Exit criteria của nhóm có ai DÁM thực thi khi sếp vẫn thích pilot không?
- Adoption: ai dùng đầu tiên — không phải "cả khóa ~500 người"?

### Trả lời

1. **Tóm vấn đề** (1 câu, từ Problem Framing): Instructor live cần một công cụ gom câu hỏi Discord theo topic để biết chỗ nào nhiều học viên vướng mà không phải đọc toàn bộ chat thủ công.
2. **Cách làm + lý do** (từ 02-solution, 1 câu): Boost bằng cách dùng API/embedding hiện có để cluster câu hỏi Discord và hiển thị cho instructor review, vì đây là productivity layer cần pilot nhanh, không cần build NLP từ số 0.
3. **Scope pilot**: phục vụ Instructor live và Admin track; thử nghiệm trên 1-2 buổi live / 1 nhóm nhỏ; thời lượng pilot 2 tuần; 2 phase (Phase 1: prototype + sample test, Phase 2: live pilot + refine).
4. **Người**: Nhóm làm: Trần Xuân Trường; Ai review output rủi ro cao: Instructor live; Ai có quyền quyết approve/dừng: Lead instructor / admin track.
5. **Data**: Dùng sample Discord chat từ 1-2 buổi live hiện có hoặc giả định log nếu chưa có; privacy: chỉ dùng nội dung public channel, tránh PII, ẩn danh nếu cần; citation: output kèm nguồn tin nhắn gốc và tag message IDs.
6. **Budget** (tách hạng mục): API/tool: OpenAI/Azure embeddings + chat completion ~ $50-100 cho pilot nhỏ; thời gian người: dev/implementation ~ 10-15 giờ của 1 người, instructor review ~ 2-4 giờ; hạng mục ẩn: 2 giờ onboarding instructor, 3 giờ bảo trì/giải quyết cluster sai.
7. **Timeline + cổng giữa phase**: Phase 1 (1 tuần): xây prototype clustering + test sample log → cổng: instructor xác nhận 4-5 cluster đầu tiên đúng >80%. Phase 2 (1 tuần): chạy pilot 1-2 buổi live + refine UI và review process → cổng: instructor thấy công cụ hữu ích và dùng được trong 1-2 buổi.
8. **Metrics** (SMART + baseline + ngưỡng + ai đo):

| Metric                       | Đo bằng gì · ai đo                                                            | Baseline                   | Ngưỡng đạt             |
| ---------------------------- | ----------------------------------------------------------------------------- | -------------------------- | ---------------------- |
| Tỷ lệ cluster chính xác      | So sánh cluster với đánh giá instructor trên 10 cluster mẫu · instructor đo   | Baseline 0% (chưa có tool) | ≥80%                   |
| Tiết kiệm thời gian đọc chat | Thời gian instructor dùng công cụ vs đọc thủ công trên 1 buổi · instructor đo | Baseline ~20 phút lọc chat | Giảm ≥10 phút mỗi buổi |
| Tỷ lệ instructor chấp nhận   | Số buổi instructor dùng công cụ / số buổi thử nghiệm · admin đo               | Baseline 0 buổi            | ≥70%                   |

Leading indicator (biết kết quả sớm trong 1–2 tuần): Tỷ lệ cluster được instructor xác nhận đúng sau review đầu tiên, mục tiêu ≥80%.

9. **Exit criteria** (định trước, ≥2 mức):

| Mức          | Điều kiện                                                                              | Hành động                                                    | Ai có quyền dừng        |
| ------------ | -------------------------------------------------------------------------------------- | ------------------------------------------------------------ | ----------------------- |
| Cảnh báo     | Tỷ lệ cluster chính xác <70% hoặc instructor không dùng tool trong 50% buổi thử nghiệm | Điều chỉnh thuật toán, tăng review, kiểm tra lại sau 1 buổi  | Lead instructor / admin |
| Nghiêm trọng | Tỷ lệ cluster chính xác <60% hoặc instructor từ chối dùng tool vì không tin tưởng      | Dừng pilot, thu thập thêm data / cải tiến trước khi tiếp tục | Lead instructor / admin |

_Liên hệ 2 Red Flag ở `00-context.md`: exit criteria chặn được spam/topic nhạy cảm bằng review output và dừng pilot nếu instructor không tin cluster; cũng chặn privacy bằng yêu cầu chỉ dùng public chat và citation._

10. **Adoption** (tool không ai dùng = $0): Instructor live dùng đầu tiên, workflow đổi từ đọc toàn bộ chat sang xem danh sách topic câu hỏi và nguồn message gốc. Instructor duyệt cluster và quyết định ưu tiên giải thích. Lead instructor/admin hỗ trợ onboarding 1-2 buổi. Nếu không ai dùng thì pilot dừng và nhóm tập trung lấy thêm feedback để cải tiến trước khi thử lại.

---

## Tự phản biện

- Budget thiếu hạng mục ẩn nào không?
- Exit criteria đủ mạnh để THẬT SỰ dừng, hay chỉ trên giấy?
- Giả định quan trọng nhất sai → plan gì?

---

## Tổng kiểm tra trước khi sang `2-FINAL-pitch.md`

| Hạng mục                                            | Xong? |
| --------------------------------------------------- | ----- |
| Tóm vấn đề trong 1 câu                              | /     |
| Budget tách hạng mục, không "miscellaneous"         | /     |
| Metric có baseline + ngưỡng + ai đo                 | /     |
| Exit criteria có người có quyền thực thi (≥2 mức)   | /     |
| Adoption: chỉ rõ ai dùng đầu tiên (không "cả khóa") | /     |

⚑ Coach kiểm tra ở Mốc 4: _"Xin gì? Hứa gì? Đo gì? Dừng khi nào?"_

Sau bước này, mở `2-FINAL-pitch.md` — dồn tất cả thành 5-slide pitch + AI Support Log.

_Liên quan: handbook §A7+§A8 · `templates/ai-pilot-plan-core.md` · `prompts/06-pilot-plan-challenge.md`_
