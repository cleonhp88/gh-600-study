---
title: "1.8 — Recap quiz Foundations"
---

# 🎓 Recap quiz — 10 câu kiểm tra Foundations

!!! abstract "🎯 Mục tiêu (15 phút)"
    🇺🇸 _10 questions covering everything from 1.1 to 1.7. Self-grade and identify weak spots._

    🇻🇳 _10 câu phủ hết từ 1.1 → 1.7. Tự chấm và nhận diện điểm yếu._

!!! tip "Cách làm"
    🇺🇸 _Read each question, think for ~30 seconds, then open the answer. Track your score below._

    🇻🇳 _Đọc câu hỏi, nghĩ ~30 giây, rồi mở đáp án. Ghi điểm vào bảng cuối bài._

---

## Q1 — Agent vs Script

🇺🇸 _Your team needs to format code on every commit. Use an agent or a script? Why?_

🇻🇳 _Team cần format code mỗi commit. Dùng agent hay script? Vì sao?_

??? success "Đáp án"
    🇺🇸 _**Script** — formatting is deterministic and the rules are fixed. An agent would be slower, more expensive, and could hallucinate weird formatting._

    🇻🇳 _**Script** — format là deterministic, rule cố định. Agent ở đây chậm hơn, đắt hơn, lại có thể hallucinate ra format kỳ cục._

---

## Q2 — SDLC stages

🇺🇸 _Name 2 SDLC stages where reasoning makes agents more valuable than scripts._

🇻🇳 _Kể 2 giai đoạn SDLC mà suy luận làm agent hữu ích hơn script._

??? success "Đáp án"
    🇺🇸 _Code Review (reasoning about quality), Monitor (parsing logs and inferring root cause). Also: Plan (from issue → tasks), Test (smart test generation)._

    🇻🇳 _Review code (suy luận chất lượng), Monitor (đọc log + đoán nguyên nhân gốc). Hoặc: Plan (từ issue → task), Test (sinh test thông minh)._

---

## Q3 — 3 phases

🇺🇸 _Why must planning and action be separated by a validation gate?_

🇻🇳 _Vì sao planning và action phải tách ra bởi 1 validation gate?_

??? success "Đáp án"
    🇺🇸 _Reviewability (cheap to fix plans), safety (insert human approval before irreversible steps), auditability (trace decisions later)._

    🇻🇳 _Reviewability (plan sửa rẻ), safety (chèn human approve trước hành động không hoàn tác), auditability (lưu vết để debug)._

---

## Q4 — Inspectable artifacts

🇺🇸 _Name 3 inspectable artifacts an agent should produce in a pull request._

🇻🇳 _Kể 3 inspectable artifacts agent nên tạo trong 1 pull request._

??? success "Đáp án"
    🇺🇸 _Any 3 of: PR description, PLAN.md, reasoning trace JSON, test report, SARIF scan, PR review comments, workflow run log._

    🇻🇳 _3 bất kỳ: PR description, PLAN.md, reasoning trace JSON, test report, SARIF scan, comment review, log workflow run._

---

## Q5 — Standard tooling

🇺🇸 _Why must artifacts live in standard tooling (GitHub) not private storage (Slack DM)?_

🇻🇳 _Vì sao artifact phải ở tooling chuẩn (GitHub), không phải kho riêng (Slack DM)?_

??? success "Đáp án"
    🇺🇸 _Team-wide access without special permissions; artifacts survive personnel changes; audit trails remain searchable._

    🇻🇳 _Cả team truy cập được không cần quyền đặc biệt; artifact còn lại khi người rời đi; audit trail luôn tìm được._

---

## Q6 — Autonomy levels

🇺🇸 _An agent auto-deploys to production. Which autonomy level fits, and why?_

🇻🇳 _Agent tự deploy lên prod. Autonomy level nào phù hợp, vì sao?_

??? success "Đáp án"
    🇺🇸 _**L4** — agent runs freely but pauses for irreversible/risky actions (the prod deploy itself, schema migrations). Below L4, you lose velocity; above, you lose safety._

    🇻🇳 _**L4** — agent tự chạy, chỉ dừng ở hành động không hoàn tác/rủi ro (chính lúc deploy prod, migration schema). Dưới L4 mất tốc độ; trên L4 mất an toàn._

---

## Q7 — Mandatory HITL

🇺🇸 _List 3 categories of actions that always need human approval, regardless of autonomy._

🇻🇳 _Kể 3 nhóm hành động luôn cần human approval, bất kể autonomy._

??? success "Đáp án"
    🇺🇸 _Any 3 of: irreversible, security-sensitive, compliance-sensitive, cost-significant, cross-team blast radius._

    🇻🇳 _3 bất kỳ trong: irreversible, security-sensitive, compliance-sensitive, cost-significant, cross-team blast radius._

---

## Q8 — Anti-pattern recognition

🇺🇸 _A prompt says "make this code better." Which anti-pattern is this and how to fix?_

🇻🇳 _Prompt ghi "làm code này tốt hơn." Đây là anti-pattern gì và sửa như nào?_

??? success "Đáp án"
    🇺🇸 _**#1 No success criteria.** Fix: define checklist (tests pass + complexity < N + perf budget + no new deps)._

    🇻🇳 _**#1 No success criteria.** Sửa: định nghĩa checklist (test pass + complexity < N + budget perf + không dep mới)._

---

## Q9 — Velocity vs safety

🇺🇸 _Why is approving every single agent action also a bad pattern?_

🇻🇳 _Tại sao approve mọi action của agent cũng là pattern tệ?_

??? success "Đáp án"
    🇺🇸 _Approvals cost team velocity. Each approval must materially reduce risk. Reviewing safe actions (format, lint, doc) wastes time and trains the team to rubber-stamp._

    🇻🇳 _Approval tốn tốc độ team. Mỗi approval phải giảm rủi ro thật. Review hành động an toàn (format, lint, doc) phí thời gian và làm team đóng dấu cho qua._

---

## Q10 — Tổng hợp

🇺🇸 _An agent runs, never logs, never produces a plan, edits any file in the repo. Which anti-patterns are violated?_

🇻🇳 _Agent chạy, không log, không tạo plan, sửa file bất kỳ trong repo. Vi phạm anti-pattern nào?_

??? success "Đáp án"
    🇺🇸 _**#2 unbounded scope**, **#4 no observability**, **#5 action without plan** — at least 3 of the 5. Likely also #1 (no success criteria) and #3 (no structured output) depending on the prompt._

    🇻🇳 _**#2 unbounded scope**, **#4 no observability**, **#5 action without plan** — ít nhất 3 trong 5. Có thể cả #1 (no criteria) và #3 (no structured output) tuỳ prompt._

---

## 📊 Tự chấm điểm

| Q | Score (1 nếu đúng, 0 nếu sai/không chắc) |
|---|---|
| Q1 — Agent vs Script | _ |
| Q2 — SDLC stages | _ |
| Q3 — 3 phases | _ |
| Q4 — Inspectable artifacts | _ |
| Q5 — Standard tooling | _ |
| Q6 — Autonomy levels | _ |
| Q7 — Mandatory HITL | _ |
| Q8 — Anti-pattern recognition | _ |
| Q9 — Velocity vs safety | _ |
| Q10 — Tổng hợp | _ |
| **TOTAL** | **__ / 10** |

!!! tip "Diễn giải"
    🇺🇸 _**9–10**: Foundations solid → move to Domain 2. **6–8**: revisit weak lessons. **<6**: re-read Foundations 1.1–1.7._

    🇻🇳 _**9–10**: Foundations vững → sang Domain 2. **6–8**: ôn lại bài yếu. **<6**: đọc lại 1.1–1.7._

---

## 🔑 Take-away Foundations

!!! success "Tóm tắt 8 bài"
    🇺🇸 _**Agents reason; scripts obey.** SDLC has 8 stages; pick agents where reasoning helps. Plan → validate → act, never blend. Artifacts must be inspectable in GitHub. Autonomy L0–L5; pick the lowest that delivers value. HITL for the risky 5%, not the safe 95%. Avoid the 5 anti-patterns._

    🇻🇳 _**Agent suy luận; script tuân lệnh.** SDLC có 8 giai đoạn; chọn agent ở chỗ cần suy luận. Plan → validate → act, không gộp. Artifact phải inspectable trong GitHub. Autonomy L0–L5; chọn thấp nhất mà vẫn giao giá trị. HITL cho 5% rủi ro, không phải 95% an toàn. Tránh 5 anti-patterns._

---

[← 1.7 Anti-patterns](07-anti-patterns.md){ .md-button } [🏠 Trang chủ](../../index.md){ .md-button .md-button--primary }
