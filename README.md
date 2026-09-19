# Security Audit Pro

**Professional adversarial security audit skill for coding agents**  
**اسکیل حرفه‌ای و ارتقاء‌یافته ممیزی امنیتی تخاصمی برای ایجنت‌های کدنویسی**

---

## English

### What is this?

**Security Audit Pro** turns your coding agent into a structured, rigorous security auditor.  
It finds real trust-boundary violations, validates them adversarially (the finder never confirms its own bug), and produces clear, actionable reports that owners can actually use.

This is a professional upgrade of Cloudflare’s excellent [security-audit-skill](https://github.com/cloudflare/security-audit-skill).  
We kept the strongest ideas — independent verification, coverage thinking, and strict `confirmed` / `needs_validation` / `rejected` verdicts — and made the whole experience clearer, more usable, better documented, and easier to run to completion.

### Key Improvements over the original

- Clear **Quick / Standard / Deep** profiles with explicit guidance
- Full **bilingual documentation** (English + Persian)
- Much simpler step-by-step path from zero to finished report
- Better executive summaries and actionable findings
- Graceful degradation when a full sandbox is not available
- Cleaner structure and faster onboarding
- Explicit anti-patterns so agents stay disciplined

### Quick Start

1. Install the skill:
   ```bash
   npx skills add https://github.com/Beig-Rules/security-audit-pro --skill security-audit-pro
   ```

2. Open your coding agent inside (or pointed at) the repository you want to audit.

3. Give a clear instruction, for example:
   - `security audit this codebase`
   - `run a quick security audit`
   - `do a standard security audit and produce the full report`
   - `perform a deep security review`

4. The agent will confirm the profile if needed, run the structured workflow, and write the report files.

### Profiles Explained

| Profile      | Best for                            | What you get                              | Cost   |
|--------------|-------------------------------------|-------------------------------------------|--------|
| **Quick**    | Small projects, first look, triage  | Fast focused pass, main risks             | Low    |
| **Standard** | Most real-world projects            | Balanced coverage + solid verification    | Medium |
| **Deep**     | High-stakes or large codebases      | Maximum thoroughness and re-verification  | High   |

### What you receive after a full audit

- `REPORT.md` — Start here. Executive summary + prioritized confirmed findings with concrete recommendations.
- `FINDINGS-DETAIL.md` — Full technical evidence and source traces.
- `NEEDS-VALIDATION.md` — Precise list of items that need the owner to check one specific fact.
- `findings.json` — Machine-readable results.
- `coverage-ledger.json` — Record of what was examined.

### Core Principles (kept and clarified)

- Only real trust-boundary failures are reported as confirmed.
- The agent that finds a candidate never confirms it.
- Severity exists only on confirmed findings (likelihood × impact).
- Defense-in-depth gaps without a reachable violation are hardening notes.
- Source-first analysis + bounded local evidence. No guessing of external behavior.
- Multiple runs improve coverage over time.

### Detailed Usage Guide (English)

**From zero to finished report:**

1. Ensure your coding agent supports tools and sub-agents.
2. Install the skill with the command above.
3. Open or point the agent at the target repository.
4. State clearly what you want (include the profile if you already know it).
5. Answer any short clarifying questions (scope, output folder, profile).
6. Let the agent complete the phases.
7. Open `REPORT.md` first. Use the other files only when you need deeper evidence.

**Recommended first commands:**

```
run a quick security audit on this repo
```

```
do a standard security audit and write the full report
```

```
perform a deep security audit, focus on authentication and authorization
```

---

## فارسی

### این پروژه چیست؟

**Security Audit Pro** ایجنت کدنویسی شما را به یک ممیز امنیتی ساختاریافته و سخت‌گیر تبدیل می‌کند.  
آسیب‌پذیری‌هایی که واقعاً مرز اعتماد را نقض می‌کنند پیدا می‌کند، آن‌ها را به صورت تخاصمی اعتبارسنجی می‌کند (کسی که باگ را پیدا کرده حق تأیید نهایی آن را ندارد) و گزارش‌های واضح و قابل‌اجرا تولید می‌کند که صاحب پروژه واقعاً بتواند از آن‌ها استفاده کند.

این نسخه، ارتقاء حرفه‌ای اسکیل عالی [security-audit-skill](https://github.com/cloudflare/security-audit-skill) از Cloudflare است.  
قوی‌ترین ایده‌ها (اعتبارسنجی مستقل، تفکر coverage، و تفکیک دقیق سه وضعیت `confirmed` / `needs_validation` / `rejected`) حفظ شده و کل تجربه استفاده ساده‌تر، شفاف‌تر، مستندتر و قابل‌اتکاتر شده است.

### مهم‌ترین بهبودها نسبت به نسخه اصلی

- پروفایل‌های واضح **سریع / استاندارد / عمیق** همراه با راهنمای صریح
- مستندات کامل دو زبانه (فارسی + انگلیسی)
- مسیر خیلی ساده‌تر از صفر تا گزارش نهایی
- خلاصه مدیریتی بهتر و یافته‌های واقعاً actionable
- رفتار منطقی و شفاف وقتی sandbox کامل در دسترس نیست
- ساختار تمیزتر و شروع بسیار آسان‌تر
- لیست ضدالگوها برای نگه داشتن انضباط ایجنت

### شروع سریع

1. اسکیل را نصب کنید:
   ```bash
   npx skills add https://github.com/Beig-Rules/security-audit-pro --skill security-audit-pro
   ```

2. ایجنت کدنویسی را داخل (یا اشاره به) ریپازیتوری هدف باز کنید.

3. دستور واضح بدهید، مثلاً:
   - `security audit this codebase`
   - `یک ممیزی امنیتی سریع انجام بده`
   - `ممیزی استاندارد امنیتی انجام بده و گزارش کامل بده`
   - `ممیزی عمیق امنیتی انجام بده`

4. ایجنت در صورت نیاز پروفایل را تأیید می‌کند، فرآیند را اجرا می‌کند و فایل‌های گزارش را می‌نویسد.

### توضیح پروفایل‌ها

| پروفایل     | مناسب برای                          | چه چیزی دریافت می‌کنید                    | هزینه  |
|-------------|-------------------------------------|-------------------------------------------|--------|
| **سریع**    | پروژه‌های کوچک، نگاه اول، تریاژ     | پوشش سریع و ریسک‌های اصلی                 | کم     |
| **استاندارد** | اکثر پروژه‌های واقعی               | پوشش متعادل + اعتبارسنجی خوب              | متوسط  |
| **عمیق**    | پروژه‌های حساس یا بزرگ              | حداکثر دقت و بازبینی مستقل                | بالا   |

### خروجی‌های یک ممیزی کامل

- `REPORT.md` — از اینجا شروع کنید. خلاصه مدیریتی + یافته‌های اولویت‌بندی‌شده همراه با توصیه مشخص.
- `FINDINGS-DETAIL.md` — جزئیات فنی کامل و شواهد.
- `NEEDS-VALIDATION.md` — لیست دقیق مواردی که صاحب پروژه باید یک واقعیت مشخص را بررسی کند.
- `findings.json` — نتایج قابل‌خواندن توسط ماشین.
- `coverage-ledger.json` — سابقه آنچه بررسی شده است.

### اصول اصلی (حفظ‌شده و شفاف‌شده)

- فقط نقض واقعی مرز اعتماد به عنوان confirmed گزارش می‌شود.
- ایجنتی که کاندیدا را پیدا کرده هرگز خودش آن را تأیید نمی‌کند.
- شدت فقط برای یافته‌های confirmed محاسبه می‌شود.
- کمبود لایه‌های دفاعی بدون نقض قابل‌دسترس، فقط یادداشت hardening است.
- تحلیل منبع‌محور + شواهد محدود محلی. حدس زدن رفتار خارجی ممنوع است.
- اجرای چندباره پوشش را بهتر می‌کند.

### راهنمای دقیق استفاده (فارسی)

**از صفر تا گزارش نهایی:**

1. مطمئن شوید ایجنت شما از ابزار و sub-agent پشتیبانی می‌کند.
2. اسکیل را با دستور بالا نصب کنید.
3. وارد ریپازیتوری هدف شوید یا آن را به ایجنت نشان دهید.
4. واضح بگویید چه می‌خواهید (اگر پروفایل را می‌دانید ذکر کنید).
5. به سؤالات کوتاه احتمالی (محدوده، پوشه خروجی، پروفایل) پاسخ دهید.
6. اجازه دهید فازها کامل شوند.
7. اول فایل `REPORT.md` را باز کنید. بقیه فایل‌ها فقط وقتی به شواهد بیشتر نیاز دارید.

**دستورات پیشنهادی اول:**

```
یک ممیزی امنیتی سریع روی این ریپو انجام بده
```

```
ممیزی استاندارد امنیتی انجام بده و گزارش کامل بنویس
```

```
ممیزی عمیق امنیتی انجام بده، تمرکز روی احراز هویت و دسترسی‌ها
```

---

## Installation / نصب

```bash
npx skills add https://github.com/Beig-Rules/security-audit-pro --skill security-audit-pro
```

Alternatively, clone this repository and point your agent to the `skills/security-audit-pro` directory.

---

## Project Structure / ساختار پروژه

```
security-audit-pro/
├── README.md                          # This bilingual documentation
├── LICENSE                            # MIT + attribution
└── skills/
    └── security-audit-pro/
        ├── SKILL.md                   # Main skill definition (profiles, workflow, principles)
        └── README.md                  # Short note for the skill package
```

---

## Attribution & Copyright / اعتبار و کپی‌رایت

This project is a professional upgrade inspired by the excellent work of Cloudflare:

**Original project:** [cloudflare/security-audit-skill](https://github.com/cloudflare/security-audit-skill)  
The original authors and contributors retain full credit for the core adversarial methodology, independent verification approach, coverage-ledger concept, and rigorous evidence standards.

**This upgraded version (Security Audit Pro)**  
Copyright © 2026 Beig (Beig-Rules)  
Published under the MIT License.

You are free to use, modify, and distribute this version.  
When you use or fork it, please keep the attribution to both the original Cloudflare work and this upgraded edition.

---

**ساخته‌شده برای استفاده حرفه‌ای‌تر، شفاف‌تر و کاربردی‌تر از ممیزی امنیتی با ایجنت‌ها**  
**Built for clearer, more usable, and professional agent-driven security auditing**
