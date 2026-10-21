# Engineering Roadmaps

[English](#en) · [فارسی](#fa)

<a id="en"></a>

## English

Self-paced learning roadmaps for backend engineers. Each roadmap is a single, self-contained HTML file (the UI is in Persian): no server, no build step, no account. Your progress is saved in your browser, and you move it between browsers or machines with **Export** and **Import**.

### Repository layout

```text
.
├── index.html                                # start page: links to every roadmap
├── README.md
├── .gitignore
└── roadmaps/
    ├── bitpin-engineering-ladder.md          # Bitpin engineering ladder (L1–L8), shared by all roadmaps
    ├── backend/                              # main roadmap
    │   ├── roadmap.html
    │   └── roadmap-index.md
    ├── database/
    │   ├── roadmap.html
    │   └── roadmap-index.md
    └── networking/
        ├── roadmap.html
        └── roadmap-index.md
```

Every roadmap folder has the same two files:

- `roadmap.html` is the roadmap itself. Open it in a browser.
- `roadmap-index.md` is a compact index (id, title, level, ladder L) of that roadmap. It's handy for skimming or for giving an AI the structure without the full HTML.

| Folder | Roadmap |
|---|---|
| `roadmaps/backend/` | Main roadmap: senior backend engineer (Python, Django, SRE, distributed systems) |
| `roadmaps/database/` | Database roadmap (SQL, NoSQL, indexing, sharding, plus a catalog of databases) |
| `roadmaps/networking/` | Network roadmap (DNS, TLS, routing, proxy, VPN, Linux networking) |

To add a new roadmap, create `roadmaps/<topic>/` with its own `roadmap.html` and `roadmap-index.md`. Give it its own `localStorage` key and an export file name that contains `progress` and ends in `.json`, so `.gitignore` already covers it. Then add an entry for it to the `ROADMAPS` list in `index.html`, and put the same `homelink` (pointing to `../../index.html`) at the top of its sidebar.

### Getting started

1. Open `index.html` in the repo root in a browser (double-click it, or `xdg-open index.html`). It links to every roadmap and shows how many topics you've done, are learning, and have due for review in each. You can also open any `roadmaps/*/roadmap.html` directly. Each roadmap has a **→ همهٔ نقشه‌های راه** (*all roadmaps*) link at the top of its sidebar that brings you back to this page. Everything works offline except the external resource links.
2. Start at **Dashboard**. It shows your overall stats, the suggested next topic (the first unfinished topic whose prerequisites are all done), your bookmarks, topics due for review, and a gap analysis for key domains.
3. Use **Phases** to browse topics. Click a card to open the topic.

### Views

| View | What you do there |
|---|---|
| Dashboard | Overall progress, next topic, bookmarks, reviews due, gap analysis |
| Phases | All topics, or one phase picked from the sidebar, with filters |
| Comparisons | Side-by-side comparisons of related technologies |
| Scenarios | Real-world, production-style problems |
| Periodic review | Spaced-repetition queue: due today and upcoming |
| Capstone | Final checklist. Click an item to tick it |
| Database catalog *(database roadmap only)* | Database families and individual database profiles |
| Path by L *(database roadmap only)* | Topics grouped by ladder level, with cumulative % per level |

**Search** (sidebar) looks in the title and the short and deep descriptions, and switches to Phases automatically.
**Filters** in Phases: difficulty level, ladder level (L1+ … L8+, or *optional*), status, and *bookmarked only*.
**🌓** toggles light/dark theme. The theme is remembered and shared by all three roadmaps.

### Working with a topic

Each topic window has:

- **Status**: `not started` → `learning` → `practicing` → `completed` → `mastered`. *Completed* and *mastered* count as done for stats, prerequisites, and next-topic suggestions.
- **★ Bookmark**, to mark topics you want to come back to.
- **Prerequisites**, shown green ✓ when done and red ✗ when not.
- The content: short and deep explanations, objectives, examples, exercise, project, completion criteria, interview questions, common mistakes, production notes, and free resources.
- **🤖 AI mentor prompt**. Click *Copy prompt* and paste it into your AI assistant to be quizzed and coached on that topic.
- **📝 Personal note**, saved as you type.
- **🔁 Spaced review buttons** (see below).

### Spaced repetition

After studying a topic, rate how well you remembered it. The next review date is picked from the sequence **1 → 3 → 7 → 14 → 30 → 90 days**:

| Button | Effect on the interval |
|---|---|
| Forgot | Back to the start (1 day) |
| Hard | Stays at the current step |
| Good | Moves one step forward |
| Easy | Moves two steps forward |

Topics whose date has arrived show up in **Periodic review** and on the Dashboard.

### Where progress is stored

Progress is kept in your browser's `localStorage`. Each roadmap has its own key, so the three roadmaps never overwrite each other:

| Roadmap | localStorage key | Export file name |
|---|---|---|
| Main | `roadmap_progress_v1` | `roadmap-progress-YYYY-MM-DD.json` |
| Network | `network_roadmap_progress_v1` | `network-roadmap-progress-YYYY-MM-DD.json` |
| Database | `db_roadmap_progress_v1` | `db-roadmap-progress-YYYY-MM-DD.json` |

> **Your progress lives only in this browser and profile.** A different browser, another machine, a private window, or clearing site data shows an empty roadmap. Some browsers also tie `file://` storage to the file's location, so moving or renaming the HTML file can hide it. **Export regularly.** The export file is your backup.

### Export

Click **⬇️ Export progress file** (`اکسپورت فایل پیشرفت`) in the sidebar. The browser downloads a JSON file named after today's date (see the table above). It contains everything: statuses, bookmarks, notes, review schedules, and capstone checkmarks.

```json
{
  "exportedAt": "2026-09-27T13:03:07.986Z",
  "version": 1,
  "progress": {
    "process-vs-thread": {
      "status": "completed",
      "note": "",
      "bookmark": false,
      "review": { "lastDate": "2026-09-27T13:03:02.403Z", "nextDate": "2026-09-28T13:03:02.403Z", "stage": 0 }
    },
    "learn-docs": { "status": "learning", "note": "", "bookmark": false, "review": null }
  }
}
```

- Keys in `progress` are topic ids (the `id` column in the index files). Capstone items are stored as `capstone_<section>_<n>`, or `netcapstone_…` in the network roadmap.
- The network export also includes `"kind": "network-roadmap"`. The database export includes `"app": "database-roadmap"` and a `summary` (`done`, `total`, `pct`).
- `.gitignore` ignores every `*progress*.json` file in any folder. That covers both the files you export and the ones you import back. You can keep them anywhere in the repo and they won't be committed.

### Import

1. Click **⬆️ Import progress file** (`ایمپورت فایل پیشرفت`) and pick a JSON file. Both the export format above and a bare `{ topicId: {...} }` object are accepted.
2. Network and database roadmaps only: if the file looks like it belongs to another roadmap, you are asked to confirm first.
3. Choose how to apply it:
   - **OK = Replace**: your current progress for this roadmap is thrown away and replaced by the file.
   - **Cancel = Merge**: the file is combined with your current progress.

How **Merge** behaves per roadmap:

| Roadmap | Merge rule |
|---|---|
| Main, Network | Per topic, the **file wins**. A topic in the file overwrites the whole local entry for that topic (status, note, bookmark, review). Topics only present locally are kept. |
| Database | Smart, field-by-field merge. The **more advanced status** wins, **notes are combined** (joined with `---` if they differ), the **bookmark** is kept if either side has it, and the **most recent review** wins. |

> ⚠️ The main roadmap does **not** check which roadmap a file came from. Importing a network or database export into it with **Replace** wipes your main progress. Check the file name before you click OK.

### Common workflows

- **Backup**: export now and then, for example after each study session.
- **Moving to a new machine or browser**: export on the old one, open the same HTML on the new one, import, choose **Replace**.
- **Studying on two machines**: export from the one you used last, import on the other, choose **Merge**. On the main and network roadmaps the file overwrites topics it contains, so always import the *newer* file into the *older* browser.
- **Starting over**: import a file containing `{}` with **Replace**, or clear the site data for the page.

---

<a id="fa"></a>

<div dir="rtl">

## فارسی

نقشه‌های راه یادگیری خودخوان برای مهندسان بک‌اند. هر نقشه راه یک فایل HTML مستقل است: بدون سرور، بدون build و بدون حساب کاربری. پیشرفت شما در مرورگر ذخیره می‌شود و با **اکسپورت** و **ایمپورت** آن را بین مرورگرها یا سیستم‌ها جابه‌جا می‌کنید.

### ساختار مخزن

صفحهٔ شروع `index.html` در ریشهٔ مخزن است. همهٔ نقشه‌های راه داخل پوشهٔ `roadmaps/` هستند و هر نقشه راه زیرپوشهٔ خودش را دارد (درخت کامل پوشه‌ها در بخش انگلیسی آمده است). هر زیرپوشه دو فایل یکسان دارد:

- `roadmap.html` خود نقشه راه است. آن را در مرورگر باز کنید.
- `roadmap-index.md` نمایهٔ فشردهٔ همان نقشه راه است (شناسه، عنوان، سطح، نردبان L). برای مرور سریع یا دادن ساختار به AI بدون کل HTML مناسب است.

| پوشه | نقشه راه |
|---|---|
| `roadmaps/backend/` | نقشه راه اصلی: مهندس بک‌اند ارشد (Python، Django، SRE، سیستم‌های توزیع‌شده) |
| `roadmaps/database/` | نقشه راه دیتابیس (SQL، NoSQL، Indexing، Sharding و کاتالوگ دیتابیس‌ها) |
| `roadmaps/networking/` | نقشه راه شبکه (DNS، TLS، Routing، Proxy، VPN، شبکه در لینوکس) |
| `roadmaps/bitpin-engineering-ladder.md` | نردبان مهندسی بیت‌پین (L1 تا L8)، مشترک بین همهٔ نقشه‌های راه |

برای افزودن نقشه راه جدید، پوشهٔ `roadmaps/<موضوع>/` را با `roadmap.html` و `roadmap-index.md` خودش بسازید. یک کلید `localStorage` جداگانه و نام فایل اکسپورتی که `progress` داشته باشد و به `.json` ختم شود به آن بدهید تا `.gitignore` خودبه‌خود پوشش دهد. سپس یک مورد برای آن به فهرست `ROADMAPS` در `index.html` اضافه کنید و همان لینک `homelink` (به `../../index.html`) را بالای نوار کناری آن بگذارید.

### شروع کار

۱. فایل `index.html` در ریشهٔ مخزن را در مرورگر باز کنید (دابل‌کلیک یا `xdg-open index.html`). این صفحه به همهٔ نقشه‌های راه لینک دارد و برای هر کدام تعداد موضوعات تکمیل‌شده، در حال یادگیری و نیازمند مرور را نشان می‌دهد. می‌توانید هر `roadmaps/*/roadmap.html` را هم مستقیم باز کنید. بالای نوار کناری هر نقشه راه لینک **→ همهٔ نقشه‌های راه** هست که شما را به همین صفحه برمی‌گرداند. همه‌چیز آفلاین کار می‌کند به‌جز لینک منابع خارجی.
۲. از **داشبورد** شروع کنید. آمار کلی، موضوع پیشنهادی بعدی (اولین موضوع ناتمامی که همهٔ پیش‌نیازهایش تمام شده)، بوکمارک‌ها، مرورهای سررسیدشده و تحلیل شکاف حوزه‌های کلیدی را نشان می‌دهد.
۳. با **فازها** موضوعات را مرور کنید و روی هر کارت کلیک کنید تا باز شود.

### نماها

| نما | کاربرد |
|---|---|
| داشبورد | پیشرفت کلی، موضوع بعدی، بوکمارک‌ها، مرورهای امروز، تحلیل شکاف |
| فازها | همهٔ موضوعات یا یک فاز (از نوار کناری)، همراه با فیلترها |
| مقایسه‌ها | مقایسهٔ کنار‌به‌کنار فناوری‌های مرتبط |
| سناریوها | مسائل واقعی و تولیدی |
| مرور دوره‌ای | صف Spaced Repetition: امروز و آینده |
| آزمون نهایی | چک‌لیست Capstone. با کلیک روی هر مورد تیک بخورد |
| کاتالوگ دیتابیس‌ها *(فقط نقشه راه دیتابیس)* | خانواده‌ها و پروفایل تک‌تک دیتابیس‌ها |
| مسیر بر اساس L *(فقط نقشه راه دیتابیس)* | موضوعات به تفکیک سطح نردبان، با درصد تجمعی هر سطح |

**جستجو** (نوار کناری) در عنوان، توضیح کوتاه و توضیح عمیق جستجو می‌کند و خودکار به نمای فازها می‌رود.
**فیلترها** در نمای فازها: سطح دشواری، سطح نردبان (L1+ تا L8+ یا *اختیاری*)، وضعیت و *فقط بوکمارک‌شده*.
**🌓** تم روشن/تیره را عوض می‌کند. تم ذخیره می‌شود و بین هر سه نقشه راه مشترک است.

### کار با یک موضوع

پنجرهٔ هر موضوع شامل این‌هاست:

- **وضعیت**: `شروع نشده` ← `در حال یادگیری` ← `در حال تمرین` ← `تکمیل‌شده` ← `مسلط`. *تکمیل‌شده* و *مسلط* در آمار، پیش‌نیازها و پیشنهاد موضوع بعدی «انجام‌شده» حساب می‌شوند.
- **★ بوکمارک** برای موضوعاتی که می‌خواهید به آن‌ها برگردید.
- **پیش‌نیازها**: سبز ✓ اگر تمام شده و قرمز ✗ اگر نه.
- محتوا: توضیح کوتاه و عمیق، اهداف، مثال، تمرین، پروژه، معیار تکمیل، سؤالات مصاحبه، اشتباهات رایج، ارتباط با تولید و منابع رایگان.
- **🤖 پرامپت مربی AI**: روی *کپی پرامپت* بزنید و در دستیار AI خود بچسبانید تا روی آن موضوع از شما سؤال بپرسد و راهنمایی‌تان کند.
- **📝 یادداشت شخصی** که همزمان با تایپ ذخیره می‌شود.
- **🔁 دکمه‌های مرور دوره‌ای** (پایین‌تر توضیح داده شده).

### مرور دوره‌ای (Spaced Repetition)

بعد از مطالعهٔ هر موضوع، میزان به‌یادآوردن را مشخص کنید. تاریخ مرور بعدی از دنبالهٔ **۱ ← ۳ ← ۷ ← ۱۴ ← ۳۰ ← ۹۰ روز** انتخاب می‌شود:

| دکمه | اثر روی فاصله |
|---|---|
| فراموش کردم | برگشت به ابتدا (۱ روز) |
| سخت بود | در همان مرحله می‌ماند |
| خوب بود | یک مرحله جلو |
| آسان بود | دو مرحله جلو |

موضوعاتی که تاریخ مرورشان رسیده در **مرور دوره‌ای** و داشبورد نمایش داده می‌شوند.

### پیشرفت کجا ذخیره می‌شود؟

پیشرفت در `localStorage` مرورگر نگه داشته می‌شود. هر نقشه راه کلید جداگانهٔ خودش را دارد، پس این سه نقشه راه هیچ‌وقت روی هم نمی‌نویسند:

| نقشه راه | کلید localStorage | نام فایل اکسپورت |
|---|---|---|
| اصلی | `roadmap_progress_v1` | `roadmap-progress-YYYY-MM-DD.json` |
| شبکه | `network_roadmap_progress_v1` | `network-roadmap-progress-YYYY-MM-DD.json` |
| دیتابیس | `db_roadmap_progress_v1` | `db-roadmap-progress-YYYY-MM-DD.json` |

> **پیشرفت شما فقط در همین مرورگر و پروفایل وجود دارد.** در مرورگر دیگر، سیستم دیگر، پنجرهٔ خصوصی یا بعد از پاک کردن دادهٔ سایت، نقشه راه خالی دیده می‌شود. بعضی مرورگرها حافظهٔ `file://` را به مسیر فایل وابسته می‌کنند، پس جابه‌جا کردن یا تغییر نام فایل HTML ممکن است پیشرفت را پنهان کند. **مرتب اکسپورت بگیرید.** فایل اکسپورت نسخهٔ پشتیبان شماست.

### اکسپورت

روی **⬇️ اکسپورت فایل پیشرفت** در نوار کناری بزنید. مرورگر یک فایل JSON با تاریخ امروز دانلود می‌کند (جدول بالا). این فایل همه‌چیز را دارد: وضعیت‌ها، بوکمارک‌ها، یادداشت‌ها، برنامهٔ مرور و تیک‌های آزمون نهایی.

</div>

```json
{
  "exportedAt": "2026-09-27T13:03:07.986Z",
  "version": 1,
  "progress": {
    "process-vs-thread": {
      "status": "completed",
      "note": "",
      "bookmark": false,
      "review": { "lastDate": "2026-09-27T13:03:02.403Z", "nextDate": "2026-09-28T13:03:02.403Z", "stage": 0 }
    },
    "learn-docs": { "status": "learning", "note": "", "bookmark": false, "review": null }
  }
}
```

<div dir="rtl">

- کلیدهای داخل `progress` شناسهٔ موضوعات هستند (ستون `id` در فایل‌های نمایه). موارد آزمون نهایی با کلید `capstone_<بخش>_<شماره>` ذخیره می‌شوند (در نقشه راه شبکه `netcapstone_…`).
- اکسپورت شبکه فیلد `"kind": "network-roadmap"` هم دارد. اکسپورت دیتابیس فیلد `"app": "database-roadmap"` و یک `summary` (`done`، `total`، `pct`) دارد.
- `.gitignore` همهٔ فایل‌های `*progress*.json` را در هر پوشه‌ای نادیده می‌گیرد. هم فایل‌هایی که اکسپورت می‌کنید و هم فایل‌هایی که ایمپورت می‌کنید پوشش داده می‌شوند. می‌توانید آن‌ها را هر جای مخزن نگه دارید و commit نمی‌شوند.

### ایمپورت

۱. روی **⬆️ ایمپورت فایل پیشرفت** بزنید و فایل JSON را انتخاب کنید. هم قالب اکسپورت بالا و هم یک شیء سادهٔ `{ topicId: {...} }` پذیرفته می‌شود.
۲. فقط در نقشه راه شبکه و دیتابیس: اگر فایل به نظر مال نقشه راه دیگری باشد، اول از شما تأیید گرفته می‌شود.
۳. نحوهٔ اعمال را انتخاب کنید:
   - **OK = جایگزینی**: پیشرفت فعلی این نقشه راه دور ریخته می‌شود و محتوای فایل جای آن را می‌گیرد.
   - **Cancel = ادغام (Merge)**: فایل با پیشرفت فعلی ترکیب می‌شود.

رفتار **ادغام** در هر نقشه راه:

| نقشه راه | قاعدهٔ ادغام |
|---|---|
| اصلی، شبکه | برای هر موضوع، **فایل برنده است**. موضوعی که در فایل هست کل ورودی محلی همان موضوع (وضعیت، یادداشت، بوکمارک، مرور) را بازنویسی می‌کند. موضوعاتی که فقط در مرورگر هستند حفظ می‌شوند. |
| دیتابیس | ادغام هوشمند فیلدبه‌فیلد: **وضعیت پیشرفته‌تر** حفظ می‌شود، **یادداشت‌ها ترکیب می‌شوند** (اگر متفاوت باشند با `---` به هم وصل می‌شوند)، **بوکمارک** اگر در هر طرف باشد می‌ماند و **جدیدترین مرور** انتخاب می‌شود. |

> ⚠️ نقشه راه اصلی بررسی **نمی‌کند** که فایل مال کدام نقشه راه است. اگر فایل اکسپورت شبکه یا دیتابیس را با **جایگزینی** در آن ایمپورت کنید، پیشرفت نقشه راه اصلی پاک می‌شود. قبل از زدن OK نام فایل را چک کنید.

### سناریوهای رایج

- **پشتیبان‌گیری**: هر از گاهی اکسپورت بگیرید، مثلاً بعد از هر جلسهٔ مطالعه.
- **انتقال به سیستم یا مرورگر جدید**: در قبلی اکسپورت بگیرید، همان HTML را در جدید باز کنید، ایمپورت کنید و **جایگزینی** را بزنید.
- **مطالعه روی دو سیستم**: از سیستمی که آخرین بار استفاده کرده‌اید اکسپورت بگیرید، در دیگری ایمپورت کنید و **ادغام** را بزنید. در نقشه راه اصلی و شبکه فایل روی موضوعات خودش می‌نویسد، پس همیشه فایل *جدیدتر* را در مرورگر *قدیمی‌تر* ایمپورت کنید.
- **شروع از صفر**: فایلی با محتوای `{}` را با **جایگزینی** ایمپورت کنید یا دادهٔ سایت را پاک کنید.

</div>
