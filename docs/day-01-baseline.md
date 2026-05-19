# Day 1 — Baseline Self-Assessment

> Mục tiêu: đo bạn đang ở đâu trên 6 domain của GH-600 → cá nhân hóa lộ trình.
> Thời gian: 20–30 phút. Trả lời ngắn (1–3 câu mỗi câu) — không tra Google.
> Khi xong, gửi câu trả lời cho Claude để chấm + map sang study plan.

---

## Domain 1 — Agent architecture & SDLC (15–20%)

**Q1.** Một AI agent được tích hợp vào SDLC có 3 giai đoạn riêng biệt: **planning → reasoning → action**. Vì sao quan trọng phải tách rời chúng (thay vì để agent vừa nghĩ vừa hành động)?

**Q2.** "Inspectable artifacts" trong agent workflow là gì? Cho 2 ví dụ cụ thể agent có thể produce trong 1 PR.

---

## Domain 2 — Tool use & environment interaction (20–25%)

**Q3.** MCP (Model Context Protocol) server khác gì so với 1 REST API thông thường? Tại sao cần MCP **allowlist** trong production?

**Q4.** Một coding agent cần access vào repo. Bạn sẽ scope quyền của nó như thế nào (3 tầng kiểm soát)?

**Q5.** Agent gọi 1 tool nhưng tool throw error. Liệt kê 4 chiến lược xử lý theo thứ tự ưu tiên.

---

## Domain 3 — Memory, state, execution (10–15%)

**Q6.** Phân biệt **short-term memory**, **long-term memory**, và **external memory** của agent. Khi nào dùng cái nào?

---

## Domain 4 — Evaluation, error analysis, tuning (15–20%)

**Q7.** Agent tạo 1 PR fix bug nhưng test fail. Bạn dùng những signal/artifact nào để **root-cause** lỗi (kể tên ≥4 nguồn)?

**Q8.** "Reasoning error" vs "tool misuse" vs "context error" — cho mỗi loại 1 ví dụ cụ thể.

---

## Domain 5 — Multi-agent coordination (15–20%)

**Q9.** Hai agent cùng edit cùng 1 file dẫn đến conflict. Mô tả 1 orchestration pattern để **prevent** conflict này TRƯỚC khi xảy ra (không phải fix sau).

**Q10.** "Human-in-the-loop recovery" trong multi-agent workflow nghĩa là gì? Khi nào nên dùng?

---

## Domain 6 — Guardrails & accountability (10–15%)

**Q11.** "Least-privilege" áp dụng cho agent permissions thế nào? Cho 1 ví dụ vi phạm và cách fix.

**Q12.** Action nào của agent **PHẢI** require human approval, bất kể autonomy level? (≥3 loại)

---

## Self-score (sau khi trả lời xong)

Với mỗi domain, tự đánh giá:
- 0 = chưa nghe bao giờ
- 1 = nghe nói nhưng không hiểu rõ
- 2 = hiểu khái niệm, chưa làm
- 3 = đã làm 1–2 lần
- 4 = làm thường xuyên, vững
- 5 = có thể dạy người khác

| Domain | Score |
|---|---|
| 1. Architecture & SDLC | _ |
| 2. Tools & MCP | _ |
| 3. Memory & State | _ |
| 4. Evaluation | _ |
| 5. Multi-agent | _ |
| 6. Guardrails | _ |

---

**Next step**: Gửi câu trả lời cho Claude (paste vào chat hoặc reference file này). Claude sẽ:
1. Chấm điểm từng câu (✅ vững / ⚠️ thiếu / ❌ sai)
2. Update self-score trong INDEX.md
3. Đề xuất Day 2 task — bắt đầu từ domain yếu nhất.
