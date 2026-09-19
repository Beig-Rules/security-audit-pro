# Security Audit Pro

**Professional adversarial security audit skill for coding agents**  
**اسکیل حرفه‌ای و ارتقاء‌یافته ممیزی امنیتی تخاصمی برای ایجنت‌های کدنویسی**

---

## English

### What is this?

**Security Audit Pro** turns your coding agent into a structured, rigorous security auditor.  
It finds real trust-boundary violations, validates them adversarially (the finder never confirms its own bug), and produces clear, actionable reports that owners can actually use.

This is a professional upgrade of Cloudflare’s excellent [security-audit-skill](https://github.com/cloudflare/security-audit-skill).  
We kept the strongest ideas and made the experience clearer, more complete, and far more usable.

### Key Improvements over the original

- Clear **Quick / Standard / Deep** profiles
- Full **bilingual documentation** (English + Persian)
- Practical **domain guides** + ready **hunting templates**
- Clear **severity scoring** rules
- Simple **findings.json schema**
- **Resume / continue** support for interrupted audits
- Common **false-positive** patterns to reject weak candidates
- **Scoped** and **Minimal** modes
- Integration notes for major coding agents
- Example reports for every profile
- Operational checklists (English + Persian)
- Quick reference card for agents

### Quick Start

```bash
npx skills add https://github.com/Beig-Rules/security-audit-pro --skill security-audit-pro
```

Then tell your agent:

- `run a quick security audit`
- `do a standard security audit and produce the full report`
- `perform a deep security audit`
- `continue the previous security audit from the last output folder`

### Profiles

| Profile      | Best for                         | Cost   |
|--------------|----------------------------------|--------|
| **Quick**    | Small projects, first look       | Low    |
| **Standard** | Most real-world projects         | Medium |
| **Deep**     | High-stakes or large codebases   | High   |

### Output Files

- `REPORT.md` — Executive summary + prioritized actionable findings
- `FINDINGS-DETAIL.md` — Full technical evidence
- `NEEDS-VALIDATION.md` — Exact facts the owner must check
- `findings.json` — Machine-readable results
- `coverage-ledger.json` — What was examined

---

## فارسی

### این پروژه چیست؟

**Security Audit Pro** ایجنت کدنویسی شما را به یک ممیز امنیتی ساختاریافته و سخت‌گیر تبدیل می‌کند.  
آسیب‌پذیری‌های واقعی که مرز اعتماد را نقض می‌کنند پیدا می‌کند، آن‌ها را به صورت تخاصمی اعتبارسنجی می‌کند و گزارش‌های واضح و قابل‌اجرا تولید می‌کند.

این نسخه ارتقاء حرفه‌ای و کامل‌شده اسکیل [security-audit-skill](https://github.com/cloudflare/security-audit-skill) از Cloudflare است.

### مهم‌ترین قابلیت‌ها

- پروفایل‌های **سریع / استاندارد / عمیق**
- مستندات کامل دو زبانه
- راهنماهای دامنه + قالب‌های شکار آماده
- قوانین شفاف امتیازدهی شدت
- Schema ساده برای findings.json
- پشتیبانی از **ادامه دادن** ممیزی قطع‌شده
- لیست false-positiveهای رایج
- حالت‌های Scoped و Minimal
- راهنمای یکپارچه‌سازی با ایجنت‌های مختلف
- نمونه گزارش برای هر پروفایل
- چک‌لیست عملیاتی فارسی و انگلیسی

### شروع سریع

```bash
npx skills add https://github.com/Beig-Rules/security-audit-pro --skill security-audit-pro
```

سپس به ایجنت بگویید:

- `یک ممیزی امنیتی سریع انجام بده`
- `ممیزی استاندارد انجام بده و گزارش کامل بده`
- `ممیزی عمیق امنیتی انجام بده`
- `ممیزی قبلی را از همان پوشه خروجی ادامه بده`

---

## Project Structure / ساختار کامل پروژه

```
security-audit-pro/
├── README.md
├── LICENSE
├── examples/
│   ├── REPORT.example.md
│   ├── REPORT-quick.example.md
│   ├── REPORT-standard.example.md
│   └── REPORT-deep.example.md
└── skills/
    └── security-audit-pro/
        ├── SKILL.md                 # Main skill definition
        ├── DOMAINS.md               # Domain guides
        ├── HUNTING-TEMPLATES.md     # Ready hunting prompts
        ├── VALIDATION.md            # Validation rules
        ├── SEVERITY.md              # Severity scoring
        ├── SCHEMA.md                # findings.json schema
        ├── CHECKLIST.md             # English checklist
        ├── CHECKLIST.fa.md          # Persian checklist
        ├── GUIDANCE.md              # English guidance
        ├── GUIDANCE.fa.md           # Persian guidance
        ├── RESUME.md                # Resume / continue support
        ├── FALSE-POSITIVES.md       # Common weak candidates
        ├── QUICK-REFERENCE.md       # One-page agent card
        ├── INTEGRATIONS.md          # How to use with agents
        ├── SCOPED-AND-MINIMAL.md    # Scoped & minimal modes
        └── README.md
```

---

## Attribution & Copyright / اعتبار و کپی‌رایت

**Original inspiration:** [cloudflare/security-audit-skill](https://github.com/cloudflare/security-audit-skill)  
Full credit to Cloudflare and the original authors for the core adversarial methodology, independent verification approach, and rigorous evidence standards.

**This upgraded version (Security Audit Pro)**  
Copyright © 2026 Beig (Beig-Rules)  
Published under the MIT License.

Please keep attribution to both the original work and this Pro edition when you use or fork it.

---

**ساخته‌شده برای استفاده حرفه‌ای، شفاف و کاملاً کاربردی**  
**Built to be complete, clear, and ready for real professional use**
