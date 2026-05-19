---
title: "1.4 — Inspectable artifacts"
---

# 📦 Inspectable artifacts — sản phẩm review được

!!! abstract "🎯 Mục tiêu (5 phút)"
    🇺🇸 _Understand what an **inspectable artifact** is, why agents must produce them, and where to store them._

    🇻🇳 _Hiểu **inspectable artifact** (sản phẩm có thể xem lại) là gì, vì sao agent phải tạo ra, và lưu ở đâu._

---

## 1. Định nghĩa

!!! quote ""
    🇺🇸 _An **inspectable artifact** is a persistent output of an agent that a human or another agent can **review later** to understand what happened._

    🇻🇳 _**Inspectable artifact** = output **lưu lại được** của agent, để **người khác xem lại sau** mà không cần chạy agent lần nữa._

---

## 2. Các loại artifact phổ biến

<div class="grid cards" markdown>

-   :material-message-text:{ .lg } **📝 PR description**

    ---

    🇺🇸 _Why the agent proposes this change, what it tested._

    🇻🇳 _Vì sao agent đề xuất change này, đã test gì._

-   :material-checkbox-marked-outline:{ .lg } **📋 PLAN.md**

    ---

    🇺🇸 _Checklist of steps the agent planned to take._

    🇻🇳 _Checklist các bước agent dự định làm._

-   :material-code-json:{ .lg } **🧠 Reasoning trace**

    ---

    🇺🇸 _JSON log of tool calls, params, and intermediate results._

    🇻🇳 _Log JSON các lần gọi tool, tham số, kết quả trung gian._

-   :material-test-tube:{ .lg } **🧪 Test report**

    ---

    🇺🇸 _Pass/fail per case, in JUnit XML or markdown._

    🇻🇳 _Pass/fail từng test, định dạng JUnit XML hoặc markdown._

-   :material-shield-bug:{ .lg } **🔒 SARIF scan**

    ---

    🇺🇸 _Security findings from CodeQL or similar._

    🇻🇳 _Lỗi bảo mật phát hiện qua CodeQL hoặc tương đương._

-   :material-comment-text:{ .lg } **💬 PR comments**

    ---

    🇺🇸 _Inline code review notes from the agent._

    🇻🇳 _Bình luận review code inline trong PR._

-   :material-file-document:{ .lg } **📜 Workflow run log**

    ---

    🇺🇸 _Step-by-step execution log from GitHub Actions._

    🇻🇳 _Log từng bước thực thi của GitHub Actions._

-   :material-archive:{ .lg } **🗄️ Audit log**

    ---

    🇺🇸 _Append-only log: who/what/when._

    🇻🇳 _Log chỉ thêm: ai/làm gì/khi nào._

</div>

---

## 3. "Standard development tooling" = gì?

```mermaid
flowchart LR
    subgraph OK["✅ Đúng (standard tooling)"]
        A1[GitHub PR]
        A2[GitHub Issues]
        A3[GitHub Actions logs]
        A4[GitHub Checks API]
        A5[Files in repo]
    end

    subgraph BAD["❌ Sai (private/ephemeral)"]
        B1[/tmp/ files]
        B2[Slack DMs]
        B3[Agent-private DB]
        B4[Email only]
    end

    style OK fill:#e8f5e9
    style BAD fill:#ffebee
```

🇺🇸 _Artifacts must live in **standard development tooling** — GitHub PR, Issues, Actions, Checks, repo files — so the whole team can review without special access._

🇻🇳 _Artifact phải nằm trong **standard development tooling** (công cụ phát triển chuẩn) — GitHub PR, Issues, Actions, Checks, file trong repo — để cả team xem được không cần quyền đặc biệt._

---

## 4. ⚡ Mini-quiz (30 giây)

**Q1.**
🇺🇸 _List 3 inspectable artifacts an agent should produce in a PR._

🇻🇳 _Kể 3 inspectable artifacts agent nên tạo trong 1 PR._

??? success "Đáp án"
    🇺🇸 _Any 3 from: PR description, PLAN.md (or checklist), reasoning trace JSON, test report, SARIF scan, PR review comments, structured commit messages, workflow run log._

    🇻🇳 _3 bất kỳ trong: PR description, PLAN.md (checklist), reasoning trace JSON, test report, SARIF scan, comment review trong PR, commit message có cấu trúc, log workflow run._

**Q2.**
🇺🇸 _Why must artifacts live in standard development tooling, not private storage?_

🇻🇳 _Vì sao artifact phải ở standard development tooling, không phải kho riêng?_

??? success "Đáp án"
    🇺🇸 _So the whole team can review without special access, and audit trails survive personnel changes. Private storage (Slack DM, /tmp) disappears or excludes most reviewers._

    🇻🇳 _Để cả team review được không cần quyền đặc biệt, và audit trail vẫn còn khi người rời đi. Kho riêng (Slack DM, /tmp) sẽ mất hoặc loại trừ phần lớn reviewer._

---

## 5. 🔑 Take-away

!!! success "Câu chốt"
    🇺🇸 _**If a human can't review it later in GitHub, it isn't an inspectable artifact.**_

    🇻🇳 _**Nếu sau này con người không xem lại được trong GitHub, đó không phải inspectable artifact.**_

---

[← 1.3](03-planning-reasoning-action.md){ .md-button } [Tiếp: 1.5 Autonomy levels →](05-autonomy-levels.md){ .md-button .md-button--primary }
