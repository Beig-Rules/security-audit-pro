# Security Audit Pro

**Professional adversarial security audit skill for coding agents**  
**اسکیل حرفه‌ای و ارتقاء‌یافته ممیزی امنیتی تخاصمی برای ایجنت‌های کدنویسی**

---

## English

### What is this?

Security Audit Pro turns your coding agent into a structured, rigorous security auditor.  
It finds real trust-boundary violations, validates them adversarially (the finder never confirms its own bug), and produces clear, actionable reports.

This is a professional upgrade of Cloudflare’s excellent [security-audit-skill](https://github.com/cloudflare/security-audit-skill).  
We kept the strongest ideas (independent verification, coverage ledger, strict `confirmed` / `needs_validation` / `rejected` verdicts) and made the whole experience clearer, more usable, and better documented.

### Key Improvements over the original

- Clear **Quick / Standard / Deep** profiles
- Much better **bilingual documentation** (English + Persian)
- Simpler step-by-step guide from zero to finished report
- Better executive summaries and actionable findings
- Graceful degradation when full sandbox is not available
- Resume-friendly design
- Cleaner structure and easier onboarding

### Quick Start (English)

1. Install the skill (example with Skills CLI):
   ```bash
   npx skills add https://github.com/Beig-Rules/security-audit-pro --skill security-audit-pro
   ```

2. Open your coding agent inside (or pointed at) the repository you want to audit.

3. Say one of these:
   - `security audit this codebase`
   - `run a quick security audit`
   - `do a full security review with report`

4. The agent will ask for the profile (Quick / Standard / Deep) if not specified, then run the structured workflow and produce the reports.

### Profiles

| Profile   | Best for                    | Depth          | Cost   |
|-----------|-----------------------------|----------------|--------|
| **Quick** | Small projects, first look  | Fast coverage  | Low    |
| **Standard** | Most real projects       | Balanced       | Medium |
| **Deep**  | High-stakes / large codebases | Maximum rigor | High   |

### Output Files

After a full audit you typically get:

- `REPORT.md` — Executive summary + prioritized findings
- `FINDINGS-DETAIL.md` — Full technical details
- `NEEDS-VALIDATION.md` — Items that need owner confirmation
- `findings.json` — Machine-readable results
- `coverage-ledger.json` — What was examined

### Core Principles (kept from original)

- Only report real trust-boundary failures
- The agent that finds a candidate never confirms it
- Severity only on confirmed findings (likelihood × impact)
- Defense-in-depth gaps are hardening notes, not vulnerabilities
- Multiple runs improve coverage

---

## فارسی

### این پروژه چیست؟

**Security Audit Pro** ایجنت کدنویسی شما را به یک ممیز امنیتی ساختاریافته و سخت‌گیر تبدیل می‌کند.  
آسیب‌پذیری‌هایی که واقعاً مرز اعتماد (trust boundary) را نقض می‌کنند پیدا می‌کند، آن‌ها را به صورت تخاصمی اعتبارسنجی می‌کند (کسی که باگ را پیدا کرده حق تأیید آن را ندارد) و گزارش‌های واضح و قابل اجرا تولید می‌کند.

این نسخه، ارتقاء حرفه‌ای اسکیل عالی [security-audit-skill](https://github.com/cloudflare/security-audit-skill) از Cloudflare است.  
قوی‌ترین ایده‌ها (اعتبارسنجی مستقل، coverage ledger، تفکیک دقیق `confirmed` / `needs_validation` / `rejected`) حفظ شده و کل تجربه استفاده ساده‌تر، شفاف‌تر و مستندتر شده است.

### مهم‌ترین بهبودها نسبت به نسخه اصلی

- پروفایل‌های واضح **سریع / استاندارد / عمیق**
- مستندات کامل دو زبانه (فارسی + انگلیسی)
- راهنمای قدم‌به‌قدم خیلی ساده از صفر تا گزارش نهایی
- خلاصه مدیریتی بهتر و یافته‌های actionable
- رفتار منطقی وقتی sandbox کامل در دسترس نیست
- طراحی مناسب برای ادامه دادن (resume)
- ساختار تمیزتر و شروع آسان‌تر

### شروع سریع (فارسی)

1. اسکیل را نصب کنید (مثال با Skills CLI):
   ```bash
   npx skills add https://github.com/Beig-Rules/security-audit-pro --skill security-audit-pro
   ```

2. ایجنت کدنویسی خود را داخل (یا اشاره به) ریپازیتوری مورد نظر باز کنید.

3. یکی از این دستورات را بگویید:
   - `security audit this codebase`
   - `یک ممیزی امنیتی سریع انجام بده`
   - `ممیزی کامل امنیتی با گزارش انجام بده`

4. ایجنت در صورت نیاز پروفایل را می‌پرسد (سریع / استاندارد / عمیق)، سپس فرآیند ساختاریافته را اجرا می‌کند و گزارش‌ها را تولید می‌کند.

### پروفایل‌ها

| پروفایل     | مناسب برای                    | عمق          | هزینه  |
|-------------|-------------------------------|--------------|--------|
| **سریع**    | پروژه‌های کوچک، نگاه اول     | پوشش سریع    | کم     |
| **استاندارد** | اکثر پروژه‌های واقعی         | متعادل       | متوسط  |
| **عمیق**    | پروژه‌های حساس یا بزرگ       | حداکثر دقت   | بالا   |

### فایل‌های خروجی

بعد از یک ممیزی کامل معمولاً این فایل‌ها تولید می‌شوند:

- `REPORT.md` — خلاصه مدیریتی + یافته‌های اولویت‌بندی شده
- `FINDINGS-DETAIL.md` — جزئیات فنی کامل
- `NEEDS-VALIDATION.md` — مواردی که نیاز به تأیید صاحب پروژه دارند
- `findings.json` — نتایج قابل خواندن توسط ماشین
- `coverage-ledger.json` — آنچه بررسی شده است

### اصول اصلی (حفظ‌شده از نسخه اصلی)

- فقط نقض واقعی مرز اعتماد گزارش می‌شود
- ایجنتی که کاندیدا را پیدا کرده هرگز خودش آن را تأیید نمی‌کند
- شدت (severity) فقط برای یافته‌های confirmed محاسبه می‌شود
- کمبود لایه‌های دفاعی فقط یادداشت hardening است، نه آسیب‌پذیری
- اجرای چندباره پوشش را بهتر می‌کند

---

## Installation / نصب

```bash
npx skills add https://github.com/Beig-Rules/security-audit-pro --skill security-audit-pro
```

Or clone this repository and point your agent to the `skills/security-audit-pro` directory.

---

## Detailed Usage Guide / راهنمای دقیق استفاده

### English – From Zero to Report

1. Make sure your coding agent supports tools and sub-agents.
2. Install the skill (command above).
3. Navigate to (or open) the target repository.
4. Tell the agent clearly what you want:
   - For a fast first look → “run a quick security audit”
   - For normal projects → “do a standard security audit and produce the report”
   - For high-stakes code → “perform a deep security audit”
5. Answer any clarifying questions (scope, profile, output directory).
6. Wait for the structured phases to finish.
7. Read `REPORT.md` first, then dive into the detailed files if needed.

### فارسی – از صفر تا گزارش نهایی

1. مطمئن شوید ایجنت شما از ابزار و sub-agent پشتیبانی می‌کند.
2. اسکیل را با دستور بالا نصب کنید.
3. وارد ریپازیتوری هدف شوید (یا آن را به ایجنت نشان دهید).
4. واضح بگویید چه می‌خواهید:
   - برای نگاه اول سریع → «یک ممیزی امنیتی سریع انجام بده»
   - برای پروژه‌های معمولی → «ممیزی استاندارد امنیتی انجام بده و گزارش بده»
   - برای کدهای حساس → «ممیزی عمیق امنیتی انجام بده»
5. به سؤالات احتمالی ایجنت (محدوده، پروفایل، پوشه خروجی) پاسخ دهید.
6. صبر کنید تا فازهای ساختاریافته تمام شود.
7. اول فایل `REPORT.md` را بخوانید، بعد در صورت نیاز به جزئیات مراجعه کنید.

---

## Attribution & Copyright / اعتبار و کپی‌رایت

This project is a professional upgrade and re-packaging inspired by the excellent work of Cloudflare:

**Original project:** [cloudflare/security-audit-skill](https://github.com/cloudflare/security-audit-skill)  
Original authors and contributors retain full credit for the core methodology, adversarial validation approach, coverage ledger design, and rigorous principles.

**This upgraded version (Security Audit Pro)**  
Copyright © 2026 Beig (Beig-Rules)  
Published under the MIT License (same as the original spirit).

You are free to use, modify, and distribute this version.  
When you use or fork it, please keep the attribution to both Cloudflare’s original work and this upgraded edition.

---

**ساخته‌شده برای استفاده حرفه‌ای‌تر، شفاف‌تر و کاربردی‌تر از ممیزی امنیتی با ایجنت‌ها**  
**Built for clearer, more usable, and professional agent-driven security auditing**
