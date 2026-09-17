# فهرست roadmap.html (Index)

این فایل یک نمایهٔ فشرده از `roadmap.html` است — فقط شناسه/عنوان/سطح/برچسب نردبان — تا بدون بارگذاری کل فایل ۴۵۰KB بتوان ساختار نقشه راه را مرور کرد.

- ستون **سطح** = دشواری موضوع (Beginner/Intermediate/Advanced/Expert).
- ستون **L** = حداقل سطح نردبان مهندسی نرم‌افزار (۱ تا ۸) که باید این موضوع را بداند؛ سطوح بالاتر هم باید بدانند (تعریف کامل هر سطح در فاز p54 و در `نردبان مهندس نرم_افزار بیت_پین.md`).

## p0 (فاز 0) 🧭 یادگرفتنِ یادگیری
مهارت‌های فراشناختی که به همه فازهای بعدی سرعت می‌دهند.

| id | عنوان | سطح | L |
|---|---|---|---|
| learn-docs | خواندن مستندات فنی و RFC | Beginner | L1+ |
| learn-debug-method | روش علمی در دیباگ کردن | Beginner | L1+ |
| learn-ai-usage | استفاده مؤثر و ایمن از AI در یادگیری | Beginner | L1+ |

## p1 (فاز 1) 🖥️ مبانی معماری کامپیوتر
فهم سخت‌افزار زیربنایی: CPU، حافظه، کش و I/O — چرا این‌ها برای بک‌اند مهم‌اند.

| id | عنوان | سطح | L |
|---|---|---|---|
| cpu-basics | CPU، رجیسترها و چرخهٔ اجرای دستورات | Beginner | L1+ |
| memory-hierarchy | سلسله‌مراتب حافظه: کش، RAM، دیسک | Intermediate | L2+ |

## p2 (فاز 2) 🐧 سیستم‌عامل
پردازش، نخ، حافظهٔ مجازی، همروندی و مکانیزم‌های هم‌گام‌سازی.

| id | عنوان | سطح | L |
|---|---|---|---|
| process-vs-thread | Process، Thread و Context Switching | Intermediate | L2+ |
| concurrency-primitives | Mutex، Semaphore، Race Condition و Deadlock | Advanced | L4+ |
| virtual-memory | حافظهٔ مجازی، Paging و Page Fault | Advanced | L4+ |

## p3 (فاز 3) 🐧 لینوکس
لینوکس در سطح مهندس بک‌اند/SRE حرفه‌ای: shell، پردازش‌ها، شبکه، عیب‌یابی.

| id | عنوان | سطح | L |
|---|---|---|---|
| linux-filesystem | فایل‌سیستم لینوکس، inode و مجوزها | Beginner | L1+ |
| linux-process-tools | ابزارهای مانیتورینگ و عیب‌یابی پردازش (ps, top, strace, lsof) | Intermediate | L2+ |
| linux-networking-tools | ابزارهای شبکه: ss, tcpdump, dig, curl | Intermediate | L2+ |

## p4 (فاز 4) 🐍 برنامه‌نویسی پایتون
از مبانی زبان تا مفاهیم پیشرفته: async، GIL، مدیریت حافظه و CPython.

| id | عنوان | سطح | L |
|---|---|---|---|
| py-oop-typing | OOP، Typing و Dataclasses در پایتون | Beginner | L1+ |
| py-generators-async | Generator، Coroutine و Event Loop | Advanced | L4+ |
| py-memory-gc | مدیریت حافظه، Reference Counting و Garbage Collector | Expert | L5+ |

## p5 (فاز 5) 🌳 ساختمان داده
از آرایه تا B+Tree و LSM Tree — پیاده‌سازی، پیچیدگی و کاربرد واقعی در بک‌اند.

| id | عنوان | سطح | L |
|---|---|---|---|
| ds-hash-table | Hash Table | Intermediate | L2+ |
| ds-btree | B-Tree و B+Tree | Advanced | L4+ |
| ds-lsm-tree | LSM Tree | Expert | L5+ |

## p6 (فاز 6) 🧮 الگوریتم‌ها
پیچیدگی، جستجو، مرتب‌سازی، گراف و برنامه‌نویسی پویا با کاربرد بک‌اند.

| id | عنوان | سطح | L |
|---|---|---|---|
| algo-complexity | تحلیل پیچیدگی (Big O) | Beginner | L1+ |
| algo-graph-bfs-dfs | BFS، DFS و کوتاه‌ترین مسیر (Dijkstra) | Intermediate | L2+ |

## p7 (فاز 7) ➗ ریاضیات مهندسی نرم‌افزار
فقط ریاضیاتی که ارزش عملی مستقیم برای مهندسی دارد: احتمال، ترکیبیات، صف و اطلاعات.

| id | عنوان | سطح | L |
|---|---|---|---|
| math-prob-queueing | احتمال و تئوری صف (Queueing Theory) برای ظرفیت‌سنجی | Intermediate | L2+ |

## p8 (فاز 8) 🌿 Git و کنترل نسخه
مدل داده‌ای Git، استراتژی‌های شاخه‌بندی و بازبینی کد حرفه‌ای.

| id | عنوان | سطح | L |
|---|---|---|---|
| git-internals | معماری داخلی Git: Objects، Blobs، Trees، Refs | Intermediate | L2+ |
| git-branching-strategy | استراتژی شاخه‌بندی: Trunk-Based vs GitFlow | Intermediate | L2+ |

## p9 (فاز 9) 🌐 شبکه
از مدل OSI تا TCP، DNS، HTTP/2 و HTTP/3 — عمیق و کاربردی.

| id | عنوان | سطح | L |
|---|---|---|---|
| net-tcp-handshake | TCP: هندشیک، کنترل ازدحام و چرخهٔ اتصال | Advanced | L4+ |
| net-dns | DNS: Resolver، Authoritative Server و TTL | Intermediate | L2+ |

## p10 (فاز 10) 🕸️ مبانی وب
از تایپ کردن URL تا رندر صفحه — چرخهٔ کامل درخواست وب.

| id | عنوان | سطح | L |
|---|---|---|---|
| web-url-to-render | از URL تا رندر: چرخهٔ کامل یک درخواست وب | Intermediate | L2+ |
| web-cookies-sessions | Cookie، Session و مدیریت وضعیت (State) در HTTP | Intermediate | L2+ |

## p11 (فاز 11) 🔀 وب‌سرورها و پراکسی معکوس
Nginx، Gunicorn/Uvicorn، WSGI/ASGI و معماری قرارگیری آن‌ها.

| id | عنوان | سطح | L |
|---|---|---|---|
| wsgi-asgi | WSGI و ASGI: چگونه Django با وب‌سرور صحبت می‌کند | Intermediate | L2+ |
| nginx-reverse-proxy | Nginx به‌عنوان Reverse Proxy و Load Balancer | Intermediate | L2+ |

## p12 (فاز 12) 🔌 مهندسی API
طراحی عمیق REST، نسخه‌بندی، Idempotency، Rate Limiting و مقایسه با gRPC/GraphQL.

| id | عنوان | سطح | L |
|---|---|---|---|
| api-idempotency | Idempotency و طراحی API قابل‌اعتماد در برابر تکرار | Advanced | L4+ |
| api-pagination-versioning | صفحه‌بندی، فیلترینگ و نسخه‌بندی API | Intermediate | L2+ |

## p13 (فاز 13) 🎸 Django
از ساختار پروژه تا داخلی‌های ORM، میان‌افزار و چرخهٔ درخواست.

| id | عنوان | سطح | L |
|---|---|---|---|
| django-request-lifecycle | چرخهٔ کامل یک درخواست در Django (Middleware، URL Resolver، View) | Intermediate | L2+ |
| django-orm-internals | داخلی‌های ORM جنگو: QuerySet تنبل، select_related و N+1 | Advanced | L4+ |

## p14 (فاز 14) 🧩 Django REST Framework
Serializers، ViewSets، Permissions، Throttling و طراحی API حرفه‌ای با DRF.

| id | عنوان | سطح | L |
|---|---|---|---|
| drf-serializers-viewsets | Serializers، ViewSets و Routers در DRF | Intermediate | L2+ |
| drf-auth-throttling | احراز هویت، Permission و Throttling در DRF | Advanced | L4+ |

## p15 (فاز 15) 🗄️ مبانی دیتابیس
نظریهٔ رابطه‌ای، نرمال‌سازی و SQL پیشرفته.

| id | عنوان | سطح | L |
|---|---|---|---|
| db-normalization | نرمال‌سازی (1NF تا BCNF) و دنرمال‌سازی آگاهانه | Intermediate | L2+ |

## p16 (فاز 16) ⚙️ داخلی دیتابیس
Query Planner، انواع ایندکس، اسکن‌ها و اتصال (Join) داخلی.

| id | عنوان | سطح | L |
|---|---|---|---|
| db-query-planner | Query Planner، EXPLAIN و انتخاب استراتژی اجرا | Advanced | L4+ |

## p17 (فاز 17) 🔒 تراکنش و همروندی دیتابیس
ACID، سطوح Isolation، قفل‌ها و MVCC.

| id | عنوان | سطح | L |
|---|---|---|---|
| db-acid-isolation | ACID و سطوح Isolation (Dirty Read، Phantom Read) | Advanced | L4+ |

## p18 (فاز 18) 🐘 PostgreSQL
از نصب تا VACUUM، Replication، Partitioning و تنظیم عملکرد.

| id | عنوان | سطح | L |
|---|---|---|---|
| pg-vacuum-wal | WAL، MVCC و VACUUM در PostgreSQL | Advanced | L4+ |
| pg-replication-partitioning | Replication (Streaming/Logical) و Partitioning | Expert | L5+ |

## p19 (فاز 19) 📦 NoSQL
مدل‌های داده‌ای متفاوت: Document (MongoDB)، Key-Value (Redis)، Wide-Column (Cassandra)، Search (Elasticsearch).

| id | عنوان | سطح | L |
|---|---|---|---|
| nosql-categories | دسته‌بندی NoSQL و مدل CAP در انتخاب دیتابیس | Intermediate | L2+ |
| redis-data-structures | Redis: ساختارهای داده، Persistence و کاربردهای توزیع‌شده | Advanced | L4+ |

## p20 (فاز 20) 📈 مقیاس‌پذیری دیتابیس
Replication، Sharding، Consistent Hashing و الگوهای تراکنش توزیع‌شده.

| id | عنوان | سطح | L |
|---|---|---|---|
| sharding-consistent-hashing | Sharding و Consistent Hashing | Expert | L5+ |

## p21 (فاز 21) ⚡ کشینگ
استراتژی‌های کش، مشکلات کلاسیک (Stampede، Penetration، Avalanche) و راه‌حل‌ها.

| id | عنوان | سطح | L |
|---|---|---|---|
| cache-strategies | استراتژی‌های کش و مشکلات کلاسیک آن | Advanced | L4+ |

## p22 (فاز 22) ⏱️ پردازش ناهمگام
صف تسک، Celery، Retry با Backoff و الگوهای تحویل پیام.

| id | عنوان | سطح | L |
|---|---|---|---|
| celery-retries-idempotency | Celery: صف تسک، Retry با Exponential Backoff و Idempotency | Advanced | L4+ |

## p23 (فاز 23) 📬 صف پیام و بروکرها
RabbitMQ (Exchange/Queue) و Kafka (Partition/Offset/Consumer Group) — مقایسه و کاربرد.

| id | عنوان | سطح | L |
|---|---|---|---|
| rabbitmq-exchanges | RabbitMQ: Exchange، Queue، Routing و Acknowledgement | Advanced | L4+ |
| kafka-partitions-consumer-groups | Kafka: Partition، Offset و Consumer Group | Expert | L5+ |

## p24 (فاز 24) 🕰️ همروندی توزیع‌شده
ساعت منطقی، اجماع (Consensus) و قفل توزیع‌شده.

| id | عنوان | سطح | L |
|---|---|---|---|
| logical-clocks-consensus | ساعت منطقی (Lamport/Vector Clock) و مقدمهٔ Consensus (Raft) | Expert | L5+ |

## p25 (فاز 25) 🌍 سیستم‌های توزیع‌شده
CAP/PACELC، سازگاری، الگوهای تحمل خطا (Circuit Breaker، Saga، Outbox).

| id | عنوان | سطح | L |
|---|---|---|---|
| cap-theorem | قضیهٔ CAP و PACELC | Advanced | L4+ |
| resilience-patterns | الگوهای تحمل خطا: Circuit Breaker، Retry، Bulkhead، Saga | Expert | L5+ |

## p26 (فاز 26) 📐 اصول مهندسی نرم‌افزار
SOLID، DRY، KISS، YAGNI و اصول طراحی ماژولار.

| id | عنوان | سطح | L |
|---|---|---|---|
| solid-principles | اصول SOLID با مثال پایتون/Django | Intermediate | L2+ |

## p27 (فاز 27) 🧱 الگوهای طراحی
Creational، Structural و Behavioral Patterns با کاربرد واقعی پایتونی.

| id | عنوان | سطح | L |
|---|---|---|---|
| design-patterns-practical | الگوهای طراحی رایج در بک‌اند: Factory، Strategy، Observer، Decorator | Intermediate | L2+ |

## p28 (فاز 28) 🏛️ معماری نرم‌افزار
لایه‌بندی، Clean/Hexagonal Architecture و Domain-Driven Design.

| id | عنوان | سطح | L |
|---|---|---|---|
| clean-architecture-ddd | Clean/Hexagonal Architecture و مفاهیم پایهٔ DDD | Advanced | L4+ |

## p29 (فاز 29) 🧬 میکروسرویس‌ها
مرزبندی سرویس، ارتباطات، مالکیت داده و چرا میکروسرویس همیشه انتخاب درستی نیست.

| id | عنوان | سطح | L |
|---|---|---|---|
| microservices-boundaries | مرزبندی سرویس، مالکیت داده و چرا مونولیت گاهی بهتر است | Advanced | L4+ |

## p30 (فاز 30) 🏗️ طراحی سیستم
از تخمین ظرفیت تا طراحی کامل سیستم‌های بزرگ‌مقیاس (URL Shortener تا صرافی).

| id | عنوان | سطح | L |
|---|---|---|---|
| sysdesign-capacity-estimation | تخمین ظرفیت (Back-of-the-envelope Estimation) | Advanced | L4+ |
| sysdesign-url-shortener | طراحی کامل: سرویس کوتاه‌کنندهٔ URL | Advanced | L4+ |

## p31 (فاز 31) 🚀 عملکرد نرم‌افزار
پروفایلینگ، بنچمارک، N+1، فلیم‌گراف و ابزارهای بار.

| id | عنوان | سطح | L |
|---|---|---|---|
| perf-profiling | پروفایلینگ پایتون با cProfile و py-spy | Advanced | L4+ |

## p32 (فاز 32) ✅ تست
Unit/Integration/E2E، pytest، Mock و تست عمیق Django.

| id | عنوان | سطح | L |
|---|---|---|---|
| testing-django-pytest | تست Django با pytest: Unit، Integration و Mock | Intermediate | L2+ |

## p33 (فاز 33) 🛡️ امنیت
OWASP Top 10، احراز هویت/اختیار، رمزنگاری و مدل‌سازی تهدید.

| id | عنوان | سطح | L |
|---|---|---|---|
| security-owasp-top | OWASP Top 10: SQL Injection، XSS، CSRF، SSRF، IDOR | Advanced | L4+ |

## p34 (فاز 34) 🐳 Docker
Container، Image، Dockerfile چندمرحله‌ای، شبکه و امنیت.

| id | عنوان | سطح | L |
|---|---|---|---|
| docker-images-layers | Image، Layer و Dockerfile چندمرحله‌ای (Multi-stage) | Intermediate | L2+ |

## p35 (فاز 35) ☸️ Kubernetes
Pod، Deployment، Service، HPA، StatefulSet و مدیریت خوشه در مقیاس.

| id | عنوان | سطح | L |
|---|---|---|---|
| k8s-core-objects | Pod، Deployment، Service و چرخهٔ حیات در Kubernetes | Advanced | L4+ |

## p36 (فاز 36) ☁️ کلاود
مفاهیم AWS (IAM، VPC، EC2، S3، RDS) قابل انتقال به سایر کلودها.

| id | عنوان | سطح | L |
|---|---|---|---|
| cloud-vpc-iam | VPC، Subnet، Security Group و IAM | Intermediate | L2+ |

## p37 (فاز 37) 🧾 زیرساخت به‌عنوان کد
Terraform: State، Provider، Module و مدیریت drift.

| id | عنوان | سطح | L |
|---|---|---|---|
| terraform-state-modules | Terraform: State، Plan/Apply و ماژول‌سازی | Advanced | L4+ |

## p38 (فاز 38) 🔁 CI/CD
پایپ‌لاین ساخت/تست/استقرار و استراتژی‌های Deploy (Blue-Green، Canary).

| id | عنوان | سطح | L |
|---|---|---|---|
| cicd-deployment-strategies | استراتژی‌های استقرار: Rolling، Blue-Green و Canary | Advanced | L4+ |

## p39 (فاز 39) 🚨 SRE
SLI/SLO/Error Budget، مدیریت اینسیدنت و پست‌مورتم بدون سرزنش.

| id | عنوان | سطح | L |
|---|---|---|---|
| sre-sli-slo-error-budget | SLI، SLO، SLA و Error Budget | Advanced | L4+ |
| sre-incident-postmortem | مدیریت اینسیدنت و پست‌مورتم بدون سرزنش (Blameless Postmortem) | Advanced | L4+ |

## p40 (فاز 40) 📊 مشاهده‌پذیری
سه ستون Observability: متریک (Prometheus/Grafana)، لاگ و ردیابی توزیع‌شده (OpenTelemetry).

| id | عنوان | سطح | L |
|---|---|---|---|
| observability-three-pillars | سه ستون Observability: Metrics، Logs، Traces | Advanced | L4+ |

## p41 (فاز 41) 🏭 مهندسی تولید
استقرار بدون Downtime، Migration ایمن، Feature Flag و بازیابی فاجعه.

| id | عنوان | سطح | L |
|---|---|---|---|
| prod-zero-downtime-migration | Migration دیتابیس سازگار با گذشته (Backward-Compatible) و استقرار بدون Downtime | Expert | L5+ |

## p42 (فاز 42) 🔄 دسترس‌پذیری بالا
افزونگی، Failover، Multi-AZ/Multi-Region و Graceful Degradation.

| id | عنوان | سطح | L |
|---|---|---|---|
| ha-failover-multiregion | Failover، Multi-AZ و طراحی برای Graceful Degradation | Expert | L5+ |

## p43 (فاز 43) 💥 مهندسی هرج‌ومرج
تزریق خطای کنترل‌شده برای اثبات مقاومت واقعی سیستم.

| id | عنوان | سطح | L |
|---|---|---|---|
| chaos-engineering-basics | اصول Chaos Engineering: فرضیه، Blast Radius و آزمایش کنترل‌شده | Expert | L5+ |

## p44 (فاز 44) ⚡ معماری رویدادمحور
Event Sourcing، CQRS، Transactional Outbox و CDC.

| id | عنوان | سطح | L |
|---|---|---|---|
| eda-outbox-cqrs | الگوی Transactional Outbox و CQRS | Expert | L5+ |

## p45 (فاز 45) 📊 مهندسی داده
ETL/ELT، پردازش دسته‌ای/جریانی و انبار داده، تا حد نیاز یک بک‌اند ارشد.

| id | عنوان | سطح | L |
|---|---|---|---|
| data-eng-etl-cdc | ETL/ELT و Change Data Capture (CDC) | Intermediate | L2+ |

## p46 (فاز 46) 🔍 جستجو
ایندکس معکوس، تحلیلگرها، Relevance (BM25) و معماری Elasticsearch.

| id | عنوان | سطح | L |
|---|---|---|---|
| search-inverted-index-bm25 | ایندکس معکوس، تحلیلگرها و رتبه‌بندی BM25 | Advanced | L4+ |

## p47 (فاز 47) 💬 سیستم‌های بلادرنگ
WebSocket، SSE، Pub/Sub و معماری چت/اعلان.

| id | عنوان | سطح | L |
|---|---|---|---|
| realtime-websocket-presence | WebSocket، Django Channels و مدیریت Presence | Advanced | L4+ |

## p48 (فاز 48) 📝 شیوه‌های مهندسی
کد تمیز، Code Review، ADR/RFC و مدیریت بدهی فنی.

| id | عنوان | سطح | L |
|---|---|---|---|
| eng-practices-adr-review | Architecture Decision Record (ADR) و Code Review مؤثر | Intermediate | L2+ |

## p49 (فاز 49) 🐞 مهارت دیباگ
سناریوهای واقعی اینسیدنت: CPU 100%، نشت حافظه، Connection Pool Exhaustion و بیشتر.

| id | عنوان | سطح | L |
|---|---|---|---|
| debug-cpu-100-connection-exhaustion | سناریوی دیباگ: CPU ناگهان به ۱۰۰٪ می‌رسد و Connection Pool تمام می‌شود | Expert | L5+ |

## p50 (فاز 50) 💎 کیفیت کد
خوانایی، Coupling/Cohesion، طراحی خطا و سازگاری با گذشته.

| id | عنوان | سطح | L |
|---|---|---|---|
| code-quality-error-handling | طراحی مدیریت خطا (Exception Design) و خوانایی کد | Intermediate | L2+ |

## p51 (فاز 51) 🎓 بلوغ مهندسی
تفاوت Junior تا Staff: مالکیت، تصمیم‌گیری فنی و رهبری فنی.

| id | عنوان | سطح | L |
|---|---|---|---|
| eng-maturity-levels | تفاوت Junior، Mid، Senior، Staff و Principal Engineer | Advanced | L4+ |

## p52 (فاز 52) 🏆 طراحی سیستم سطح Senior/Staff
طراحی سیستم‌های واقعاً پیچیده: صرافی، سیستم پرداخت، فید خبر مقیاس‌بزرگ.

| id | عنوان | سطح | L |
|---|---|---|---|
| sysdesign-payment-ledger | طراحی سیستم پرداخت و Ledger با تضمین سازگاری قوی | Expert | L5+ |

## p53 (فاز 53) 🎯 آزمون جامع نهایی (Capstone)
ارزیابی نهایی ترکیبی از تمام حوزه‌ها: نظری، کدنویسی، SQL، دیباگ، طراحی سیستم و زیرساخت.

| id | عنوان | سطح | L |
|---|---|---|---|
| capstone-final-project | پروژهٔ نهایی: پلتفرم سرمایه‌گذاری/مالی کامل با تمام لایه‌های تولیدی | Expert | L5+ |

## p54 (فاز 54) 🪜 نردبان مهندسی نرم‌افزار (Career Ladder)
تطبیق مهارت‌های فنی این نقشه راه با سطوح رسمی نردبان مهندسی نرم‌افزار (سطح ۱ تا ۸) — قلمرو، اثرگذاری، مهارت و رفتار مورد انتظار در هر سطح.

| id | عنوان | سطح | L |
|---|---|---|---|
| ladder-se1 | نردبان: مهندس نرم‌افزار یک — قلمرو تسک | Beginner | L1+ |
| ladder-se2 | نردبان: مهندس نرم‌افزار دو — قلمرو تسک | Beginner | L2+ |
| ladder-se3 | نردبان: مهندس نرم‌افزار سه (Senior) — قلمرو پروژه/فیچر | Intermediate | L3+ |
| ladder-se4 | نردبان: مهندس نرم‌افزار چهار (Tech Lead) — پروژه/فیچر بزرگ | Advanced | L4+ |
| ladder-se5 | نردبان: مهندس نرم‌افزار پنج (Senior Tech Lead) — دامین | Advanced | L5+ |
| ladder-se6 | نردبان: مهندس نرم‌افزار شش (Staff) — دامین یا تخصص | Expert | L6+ |
| ladder-se7 | نردبان: مهندس نرم‌افزار هفت (Senior Staff) — دامین یا چند دامین | Expert | L7+ |
| ladder-se8 | نردبان: مهندس نرم‌افزار هشت (Principal) — شرکت | Expert | L8+ |
