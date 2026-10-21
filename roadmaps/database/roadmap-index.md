# فهرست roadmaps/database/roadmap.html (Index)

این فایل نمایهٔ فشردهٔ `roadmaps/database/roadmap.html` است — فقط شناسه/عنوان/نوع/سطح/برچسب نردبان — تا بدون بارگذاری کل فایل بتوان ساختار نقشه راه دیتابیس را مرور کرد. این فایل به‌صورت خودکار از داده‌های HTML تولید شده است.

- ستون **سطح** = دشواری موضوع (Beginner/Intermediate/Advanced/Expert).
- ستون **L** = حداقل سطح نردبان مهندسی نرم‌افزار (۱ تا ۸) که باید این موضوع را بداند؛ سطوح بالاتر هم باید بدانند (تعریف سطوح در `../bitpin-engineering-ladder.md`). **اختیاری** یعنی موضوع برای هیچ سطحی الزامی نیست.
- ستون **نوع**: «مفهوم»، «خانواده» (نمای کلی یک نوع دیتابیس + نمونهٔ کاربرد) یا «پروفایل» (معرفی یک دیتابیس: نمای کلی، کاربردها، مثال، ابزارها).
- پیشرفت در `localStorage` با کلید `db_roadmap_progress_v1` (جدا از نقشه راه اصلی) ذخیره می‌شود و با دکمه‌های اکسپورت/ایمپورت به فایل `db-roadmap-progress-YYYY-MM-DD.json` منتقل می‌شود.

## d0 (فاز 0) 🧭 مبانی و تصویر کلان دیتابیس‌ها
نقشهٔ ذهنی کلان: DBMS چیست، از درون چطور کار می‌کند، OLTP و OLAP چه فرقی دارند و خانواده‌های مختلف دیتابیس هر کدام برای چه ساخته شده‌اند.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| dbms-what-why | DBMS چیست و چرا فایل کافی نیست | مفهوم | Beginner | L1+ |
| dbms-architecture | معماری داخلی DBMS: از Parser تا دیسک | مفهوم | Intermediate | L2+ |
| oltp-vs-olap | OLTP در برابر OLAP (و HTAP) | مفهوم | Beginner | L2+ |
| data-models-overview | نقشهٔ خانواده‌های دیتابیس و مدل‌های داده | مفهوم | Intermediate | L3+ |
| sql-vs-nosql | SQL در برابر NoSQL: فراتر از کلیشه‌ها | مفهوم | Intermediate | L3+ |

## d1 (فاز 1) 🧮 SQL از پایه تا پیشرفته
تسلط عملی بر SQL با گویش PostgreSQL (و تفاوت‌های MySQL): از SELECT و JOIN تا Window Function، CTE بازگشتی، JSONB، Upsert و تله‌های NULL.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| sql-select-filter | SELECT، WHERE، ORDER BY و LIMIT (و ترتیب منطقی اجرا) | مفهوم | Beginner | L1+ |
| sql-joins | JOINها: INNER، LEFT، FULL، CROSS، SELF، LATERAL و Semi/Anti Join | مفهوم | Beginner | L1+ |
| sql-aggregation-groupby | تجمیع: GROUP BY، HAVING، FILTER و GROUPING SETS | مفهوم | Beginner | L1+ |
| sql-subqueries-cte | زیرکوئری‌ها و CTE (WITH) | مفهوم | Intermediate | L2+ |
| sql-window-functions | Window Functions: رتبه‌بندی، مجموع تجمعی و مقایسه با ردیف قبل | مفهوم | Intermediate | L2+ |
| sql-ddl-constraints | DDL، انواع داده و Constraintها | مفهوم | Beginner | L1+ |
| sql-recursive-cte | CTE بازگشتی: درخت، گراف و سلسله‌مراتب | مفهوم | Intermediate | L3+ |
| sql-json-arrays | JSONB، آرایه‌ها و داده‌های نیمه‌ساخت‌یافته در SQL | مفهوم | Intermediate | L3+ |
| sql-upsert-merge | Upsert و MERGE: INSERT ... ON CONFLICT، ON DUPLICATE KEY و RETURNING | مفهوم | Intermediate | L2+ |
| sql-nulls-pitfalls | NULL و منطق سه‌مقداری: تله‌های پنهان SQL | مفهوم | Beginner | L2+ |

## d2 (فاز 2) 🧩 مدل‌سازی داده (رابطه‌ای و NoSQL)
از ER و انتخاب کلید تا نرمال‌سازی، Denormalization آگاهانه، مدل‌سازی Access-pattern محور در NoSQL، Migration بدون Downtime، Multitenancy و دادهٔ زمانی/Audit.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| model-er-keys | مدل ER، روابط و انتخاب کلید (Surrogate، Natural، UUIDv7 و bigserial) | مفهوم | Intermediate | L2+ |
| model-normalization | نرمال‌سازی: 1NF تا BCNF و آنومالی‌ها | مفهوم | Intermediate | L2+ |
| model-denormalization | Denormalization آگاهانه: Counter Cache، Materialized View و Read Model | مفهوم | Advanced | L3+ |
| model-nosql-access-patterns | مدل‌سازی Access-pattern محور در NoSQL: Embedding، Referencing و Single-table Design | مفهوم | Advanced | L4+ |
| model-schema-migrations | Schema Migration و الگوی Expand/Contract (Alembic، Django، Flyway، Liquibase) | مفهوم | Intermediate | L1+ |
| model-multitenancy | Multitenancy: Shared Schema، Schema-per-tenant، DB-per-tenant و Row-Level Security | مفهوم | Advanced | L4+ |
| model-temporal-audit-softdelete | دادهٔ زمانی، Audit Trail و Soft Delete | مفهوم | Advanced | L3+ |

## d3 (فاز 3) 🗂️ ایندکس‌گذاری در عمل
چطور ایندکس درست طراحی کنیم، چطور با EXPLAIN استفاده‌شدنش را ثابت کنیم و هزینهٔ نوشتن آن را چطور مدیریت کنیم؛ از B-Tree ساده تا Full-Text، Geo و ایندکس‌های ثانویه در NoSQL.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| idx-basics | ایندکس چیست و چرا کوئری را سریع می‌کند | مفهوم | Beginner | L1+ |
| idx-composite-leftmost | ایندکس ترکیبی و قانون Leftmost Prefix | مفهوم | Intermediate | L2+ |
| idx-covering-include | Covering Index، ستون‌های INCLUDE و Index-Only Scan | مفهوم | Intermediate | L2+ |
| idx-selectivity-cardinality | Selectivity، Cardinality و توزیع داده | مفهوم | Intermediate | L2+ |
| idx-partial-expression | Partial Index و Expression (Functional) Index | مفهوم | Intermediate | L2+ |
| idx-clustered-vs-secondary | Clustered در برابر Secondary Index: InnoDB در برابر Heap پستگرس | مفهوم | Advanced | L3+ |
| idx-write-cost-antipatterns | هزینهٔ نوشتن ایندکس‌ها و ضدالگوهای ایندکس‌گذاری | مفهوم | Intermediate | L2+ |
| idx-fulltext | جست‌وجوی متن کامل: tsvector و GIN، pg_trgm، و مرز رفتن به Elasticsearch | مفهوم | Intermediate | L3+ |
| idx-geospatial | ایندکس‌های مکانی: PostGIS، Geohash/S2/H3، Redis GEO و Mongo 2dsphere | مفهوم | Advanced | اختیاری |
| idx-nosql-secondary | ایندکس ثانویه در NoSQL: MongoDB، Cassandra، DynamoDB و Elasticsearch | مفهوم | Advanced | L4+ |

## d4 (فاز 4) 🌳 ساختارهای دادهٔ ایندکس و درخت‌ها (Internals)
درون ایندکس‌ها چه می‌گذرد: B-Tree و B+Tree، LSM و Compaction، Hash، Bitmap، Inverted Index، R-Tree/GiST، Skip List، Bloom Filter، ART، BRIN و ایندکس‌های برداری؛ با چیدمان صفحه، ریاضی ارتفاع و بده‌بستان Read/Write/Space Amplification.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| tree-rum-amplification | Read/Write/Space Amplification و حدس RUM | مفهوم | Advanced | L4+ |
| tree-btree | B-Tree: درخت جست‌وجوی چندشاخه و چرا دیسک آن را دوست دارد | مفهوم | Intermediate | L3+ |
| tree-bplus-tree | B+Tree در عمل: چیدمان صفحه، Fanout، Split/Merge و ریاضی ارتفاع (InnoDB و PostgreSQL) | مفهوم | Advanced | L3+ |
| tree-lsm-sstable | LSM-Tree و SSTable: مسیر نوشتن و خواندن در RocksDB، Cassandra و ScyllaDB | مفهوم | Advanced | L4+ |
| tree-compaction-strategies | استراتژی‌های Compaction: Size-Tiered، Leveled، Time-Window و Unified | مفهوم | Expert | L4+ |
| tree-hash-index | Hash Index: از Bitcask تا Hash Index پستگرس و Adaptive Hash Index در InnoDB | مفهوم | Intermediate | L3+ |
| tree-bitmap-index | Bitmap Index، Bitmap Scan پستگرس و Roaring Bitmap | مفهوم | Advanced | L4+ |
| tree-inverted-index | Inverted Index: Posting List، Segment در Lucene و FST | مفهوم | Advanced | اختیاری |
| tree-rtree-gist | R-Tree، GiST و SP-GiST برای داده‌های مکانی | مفهوم | Advanced | اختیاری |
| tree-skiplist-memtable | Skip List و نقش آن به‌عنوان MemTable | مفهوم | Advanced | اختیاری |
| tree-bloom-filter | Bloom Filter و فیلترهای احتمالاتی در SSTable | مفهوم | Advanced | L4+ |
| tree-art-trie | Trie و Adaptive Radix Tree (ART) در موتورهای In-Memory | مفهوم | Expert | اختیاری |
| tree-brin-zonemap | BRIN، Zone Map و Data Skipping در Postgres و ClickHouse | مفهوم | Advanced | اختیاری |
| tree-vector-hnsw-ivf | ایندکس برداری: HNSW، IVF و Product Quantization | مفهوم | Expert | اختیاری |

## d5 (فاز 5) 🚀 اجرای کوئری و بهینه‌سازی (Query Execution & Optimization)
از Planner و آمار تا خواندن EXPLAIN ANALYZE، الگوریتم‌های Join، N+1، صفحه‌بندی Keyset، روند عیب‌یابی کوئری کند و Bulk Loading.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| qry-planner-statistics | Query Planner، Cost Model و آمار (Statistics) | مفهوم | Advanced | L3+ |
| qry-explain-analyze | خواندن EXPLAIN ANALYZE مثل یک حرفه‌ای | مفهوم | Intermediate | L2+ |
| qry-join-algorithms | الگوریتم‌های Join: Nested Loop، Hash و Merge | مفهوم | Advanced | L3+ |
| qry-n-plus-one-orm | N+1 و ORM: select_related، prefetch_related و Batching | مفهوم | Intermediate | L2+ |
| qry-pagination-keyset | صفحه‌بندی: OFFSET در برابر Keyset (Seek) | مفهوم | Intermediate | L2+ |
| qry-slow-query-workflow | روند عیب‌یابی کوئری کند: pg_stat_statements، auto_explain و Slow Log | مفهوم | Intermediate | L3+ |
| qry-bulk-batching | Bulk Load و Batching: COPY، executemany و عملیات دسته‌ای | مفهوم | Intermediate | L2+ |

## d6 (فاز 6) 🔒 تراکنش‌ها و هم‌روندی (Concurrency)
ACID واقعاً چه تضمینی می‌دهد، سطوح Isolation و Anomalyها با تایم‌لاین دو Session، MVCC، قفل‌ها، Deadlock و انتخاب بین قفل خوش‌بینانه و بدبینانه.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| tx-acid | ACID و چرخهٔ عمر تراکنش | مفهوم | Intermediate | L2+ |
| tx-isolation-anomalies | سطوح Isolation و Anomalyها (با تایم‌لاین دو Session) | مفهوم | Advanced | L3+ |
| tx-mvcc | MVCC: پیاده‌سازی در PostgreSQL، InnoDB و Oracle | مفهوم | Advanced | L3+ |
| tx-locking | قفل‌ها: Row، Table، Gap/Next-Key و Advisory | مفهوم | Advanced | L3+ |
| tx-deadlocks | Deadlock: تشخیص، تحلیل و پیشگیری | مفهوم | Advanced | L3+ |
| tx-optimistic-pessimistic | کنترل هم‌روندی خوش‌بینانه در برابر بدبینانه | مفهوم | Intermediate | L3+ |

## d7 (فاز 7) 💾 موتور ذخیره‌سازی و ماندگاری (Durability)
صفحه‌ها و Buffer Pool، WAL و Checkpoint، ذخیره‌سازی سطری در برابر ستونی، فشرده‌سازی و Encoding، و Vacuum/Bloat؛ یعنی آنچه زیر هر کوئری روی دیسک و حافظه اتفاق می‌افتد.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| st-pages-buffer-pool | صفحه‌ها (Pages)، Heap و Buffer Pool | مفهوم | Advanced | L3+ |
| st-wal-checkpoint | WAL، Redo Log و Checkpoint | مفهوم | Advanced | L3+ |
| st-row-vs-column | ذخیره‌سازی سطری در برابر ستونی | مفهوم | Intermediate | L3+ |
| st-compression-encoding | فشرده‌سازی و Encoding در موتورهای ذخیره‌سازی | مفهوم | Advanced | اختیاری |
| st-vacuum-bloat | Vacuum، Bloat و XID Wraparound | مفهوم | Advanced | L3+ |

## d8 (فاز 8) 🔁 Replication، دسترس‌پذیری بالا (HA) و Backup
Leader-Follower، همگام و ناهمگام و Replication Lag، Multi-Leader و حل Conflict، Leaderless و Quorum، Failover بدون Split Brain، و Backup/PITR با RPO و RTO مشخص.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| rep-leader-follower | Replication تک‌رهبره (Leader-Follower): فیزیکی و منطقی | مفهوم | Intermediate | L3+ |
| rep-sync-async-lag | Replication همگام و ناهمگام، Lag و Read-Your-Writes | مفهوم | Advanced | L4+ |
| rep-multi-leader | Replication چندرهبره (Multi-Leader) و حل Conflict | مفهوم | Expert | L5+ |
| rep-leaderless-quorum | Replication بدون رهبر (Leaderless) و Quorum | مفهوم | Expert | L5+ |
| rep-failover-ha | Failover و دسترس‌پذیری بالا: Patroni، Orchestrator، انتخابات MongoDB و Split Brain | مفهوم | Advanced | L5+ |
| rep-backup-pitr | Backup، PITR و RPO/RTO: pgBackRest، WAL-G و XtraBackup | مفهوم | Intermediate | L3+ |

## d9 (فاز 9) 🧱 Partitioning و Sharding
از Partitioning داخل یک سرور تا Sharding بین ده‌ها سرور: استراتژی‌های Range، Hash، Directory و Geo، انتخاب Shard Key با مثال‌های کامل، Consistent Hashing با Virtual Node، Resharding بدون Downtime، کلیدهای داغ، کوئری‌ها و تراکنش‌های بین‌شاردی و ابزارهای Citus، Vitess، MongoDB، Cassandra و DynamoDB.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| shd-partitioning | Partitioning جدول در یک سرور (Range، List، Hash) | مفهوم | Advanced | L4+ |
| shd-strategies | استراتژی‌های Sharding و انتخاب Shard Key (با مثال‌های کامل) | مفهوم | Expert | L5+ |
| shd-consistent-hashing | Consistent Hashing و Virtual Nodes (با پیاده‌سازی Python) | مفهوم | Expert | L5+ |
| shd-rebalancing-resharding | Rebalancing و Resharding بدون Downtime | مفهوم | Expert | L5+ |
| shd-hot-keys | کلیدهای داغ، Hot Partition و مسئلهٔ سلبریتی | مفهوم | Expert | L5+ |
| shd-cross-shard | کوئری‌ها، JOINها و تراکنش‌های بین‌شاردی | مفهوم | Expert | L5+ |
| shd-tools-citus-vitess | ابزارهای Sharding: Citus، Vitess، MongoDB، Cassandra، DynamoDB و ProxySQL | مفهوم | Expert | L5+ |

## d10 (فاز 10) 🌐 تئوری دیتابیس‌های توزیع‌شده
CAP و PACELC، طیف مدل‌های Consistency، Raft با Walkthrough، 2PC در برابر Saga و Outbox، Spanner و TrueTime، و CRDTها؛ مبانی‌ای که پشت هر تصمیم Replication و Sharding قرار دارد.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| dist-cap-pacelc | CAP و PACELC: Trade-off واقعی سیستم‌های توزیع‌شده | مفهوم | Advanced | L5+ |
| dist-consistency-models | مدل‌های Consistency (Linearizable تا Eventual) | مفهوم | Expert | L6+ |
| dist-consensus-raft | Consensus و Raft: Leader Election و Log Replication | مفهوم | Expert | L6+ |
| dist-2pc-saga | تراکنش توزیع‌شده: 2PC در برابر Saga (و Outbox) | مفهوم | Expert | L5+ |
| dist-spanner-truetime | Spanner و TrueTime: External Consistency در مقیاس جهانی | مفهوم | Expert | L6+ |
| dist-crdt | CRDTها: همگرایی بدون هماهنگی (G-Counter، OR-Set، LWW) | مفهوم | Expert | اختیاری |

## d11 (فاز 11) 🐘 دیتابیس‌های رابطه‌ای (Relational)
خانوادهٔ RDBMS و پروفایل عمیق PostgreSQL، MySQL، SQLite و RDBMSهای تجاری (SQL Server/Oracle): معماری، ابزارها، کاربردها و دام‌های عملیاتی.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| type-relational | خانوادهٔ دیتابیس‌های رابطه‌ای (RDBMS) | خانواده (Relational) | Beginner | L1+ |
| db-postgresql | PostgreSQL | پروفایل (Relational) | Beginner | L1+ |
| db-mysql | MySQL (و MariaDB) | پروفایل (Relational) | Intermediate | L2+ |
| db-sqlite | SQLite (و libSQL/Turso) | پروفایل (Relational) | Beginner | L2+ |
| db-sqlserver-oracle | SQL Server و Oracle Database (RDBMSهای تجاری) | پروفایل (Relational) | Intermediate | اختیاری |

## d12 (فاز 12) 📄 دیتابیس‌های سندگرا (Document)
خانوادهٔ Document Store با تمرکز بر MongoDB (WiredTiger، Replica Set، Sharding، Aggregation، Change Streams) و Couchbase/CouchDB؛ مدل‌سازی بر اساس الگوی دسترسی.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| type-document | خانوادهٔ دیتابیس‌های سندگرا (Document Stores) | خانواده (Document) | Intermediate | L3+ |
| db-mongodb | MongoDB | پروفایل (Document) | Intermediate | L3+ |
| db-couchbase-couchdb | Couchbase و CouchDB | پروفایل (Document) | Intermediate | اختیاری |

## d13 (فاز 13) 🔑 Key-Value، دیتابیس‌های درون‌حافظه‌ای و Coordination
خانوادهٔ Key-Value از کش درون‌حافظه‌ای (Redis، Memcached) تا Key-Value مدیریت‌شدهٔ مقیاس‌پذیر (DynamoDB) و Coordination Storeهای مبتنی بر اجماع (etcd، ZooKeeper).

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| type-keyvalue | خانوادهٔ Key-Value و دیتابیس‌های درون‌حافظه‌ای | خانواده (Key-Value) | Beginner | L2+ |
| db-redis | Redis (و Valkey) | پروفایل (Key-Value) | Beginner | L2+ |
| db-memcached | Memcached | پروفایل (Key-Value) | Intermediate | L3+ |
| db-dynamodb | Amazon DynamoDB | پروفایل (Key-Value) | Advanced | L4+ |
| db-etcd-zookeeper | etcd و ZooKeeper (Coordination Stores) | پروفایل (Coordination) | Advanced | L5+ |

## d14 (فاز 14) 🧱 دیتابیس‌های Wide-Column
خانوادهٔ Wide-Column برای نوشتن عظیم و مقیاس افقی خطی: Cassandra (Ring، Tunable Consistency، مدل‌سازی Query-first)، ScyllaDB (Shard-per-core) و HBase/Bigtable.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| type-widecolumn | خانوادهٔ دیتابیس‌های Wide-Column | خانواده (Wide-Column) | Advanced | L5+ |
| db-cassandra | Apache Cassandra | پروفایل (Wide-Column) | Advanced | L5+ |
| db-scylladb | ScyllaDB | پروفایل (Wide-Column) | Advanced | اختیاری |
| db-hbase-bigtable | HBase و Google Cloud Bigtable | پروفایل (Wide-Column) | Advanced | اختیاری |

## d15 (فاز 15) 🔎 موتورهای جستجو (Search Engines)
Inverted Index، Analyzer، رتبه‌بندی BM25 و معماری توزیع‌شدهٔ Elasticsearch/OpenSearch و موتورهای سبک‌تری مثل Meilisearch و Typesense؛ این‌که جستجو را کِی و چطور کنار دیتابیس اصلی بگذاریم.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| type-search | خانوادهٔ Search Engine: جستجوی متنی، رتبه‌بندی و Faceting | خانواده (Search) | Intermediate | L3+ |
| db-elasticsearch | Elasticsearch: موتور جستجو و تحلیل توزیع‌شده روی Lucene | پروفایل (Search) | Intermediate | L3+ |
| db-opensearch | OpenSearch: Fork متن‌باز Elasticsearch | پروفایل (Search) | Intermediate | اختیاری |
| db-meilisearch-typesense | Meilisearch و Typesense: موتورهای جستجوی سبک و Developer-Friendly | پروفایل (Search) | Beginner | اختیاری |

## d16 (فاز 16) 📊 تحلیلی (Columnar/OLAP) و سری‌زمانی
ذخیره‌سازی ستونی، Vectorized Execution و انبارهای داده (ClickHouse، DuckDB، BigQuery/Snowflake/Redshift) به‌همراه دیتابیس‌های سری‌زمانی (TimescaleDB، InfluxDB، Prometheus) برای بارهای تحلیلی و متریک.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| type-olap-columnar | خانوادهٔ Columnar/OLAP: ذخیرهٔ ستونی برای تحلیل | خانواده (Columnar/OLAP) | Advanced | L4+ |
| db-clickhouse | ClickHouse: انبار تحلیلی ستونی فوق‌سریع | پروفایل (Columnar/OLAP) | Advanced | اختیاری |
| db-duckdb | DuckDB: «SQLite برای تحلیل» (OLAP درون‌فرایندی) | پروفایل (Columnar/OLAP) | Intermediate | اختیاری |
| db-cloud-warehouses | انبارهای داده ابری: BigQuery، Snowflake و Redshift | پروفایل (Columnar/OLAP) | Intermediate | اختیاری |
| type-timeseries | خانوادهٔ Time-Series: داده‌های وابسته به زمان | خانواده (Time-Series) | Intermediate | اختیاری |
| db-timescaledb | TimescaleDB: سری‌زمانی روی PostgreSQL | پروفایل (Time-Series) | Intermediate | اختیاری |
| db-influxdb-prometheus | InfluxDB و Prometheus (به‌همراه VictoriaMetrics، Thanos، Mimir) | پروفایل (Time-Series) | Intermediate | L3+ |

## d17 (فاز 17) 🕸️ دیتابیس‌های گراف و برداری
مدل Property Graph و Cypher برای روابط پیچیده، و جستجوی برداری (Embedding، ANN، HNSW) برای Semantic Search و RAG با pgvector، Qdrant و Milvus.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| type-graph | خانوادهٔ Graph: روابط به‌عنوان شهروند درجه یک | خانواده (Graph) | Intermediate | اختیاری |
| db-neo4j | Neo4j: دیتابیس Property Graph و زبان Cypher | پروفایل (Graph) | Intermediate | اختیاری |
| type-vector | خانوادهٔ Vector: جستجوی شباهت روی Embedding | خانواده (Vector) | Intermediate | اختیاری |
| db-pgvector | pgvector: جستجوی برداری داخل PostgreSQL | پروفایل (Vector) | Intermediate | اختیاری |
| db-qdrant-milvus | Qdrant و Milvus (به‌همراه Weaviate و Pinecone) | پروفایل (Vector) | Advanced | اختیاری |

## d18 (فاز 18) 🌍 NewSQL / SQL توزیع‌شده
دیتابیس‌های SQL توزیع‌شده با تراکنش ACID سراسری، Raft و Range/Region Sharding خودکار: CockroachDB، TiDB، Google Spanner و YugabyteDB.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| type-newsql | خانوادهٔ NewSQL: SQL و ACID با مقیاس افقی | خانواده (NewSQL) | Expert | L6+ |
| db-cockroachdb | CockroachDB: SQL توزیع‌شدهٔ Serializable و مقاوم | پروفایل (NewSQL) | Expert | اختیاری |
| db-tidb | TiDB: SQL توزیع‌شده سازگار با MySQL و HTAP | پروفایل (NewSQL) | Expert | اختیاری |
| db-google-spanner | Google Cloud Spanner: دیتابیس رابطه‌ای جهانی با TrueTime | پروفایل (NewSQL) | Expert | L6+ |
| db-yugabytedb | YugabyteDB: SQL توزیع‌شده با لایه PostgreSQL واقعی | پروفایل (NewSQL) | Expert | اختیاری |

## d19 (فاز 19) 🛠️ عملیات و ابزارها (Operations & Tooling)
آنچه دیتابیس را در پروداکشن زنده نگه می‌دارد: Connection Pooling، مانیتورینگ، تغییر اسکیما بدون Downtime، CDC، امنیت، بکاپ، اجرا روی Kubernetes و تست.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| ops-connection-pooling | Connection Pooling: PgBouncer، pgcat، ProxySQL و CONN_MAX_AGE | مفهوم | Intermediate | L3+ |
| ops-monitoring | مانیتورینگ دیتابیس: pg_stat_*، Exporterها، Grafana و متریک‌های کلیدی | مفهوم | Intermediate | L3+ |
| ops-online-schema-change | تغییر اسکیما بدون Downtime: lock_timeout، CONCURRENTLY، gh-ost، pt-osc و pg-osc | مفهوم | Advanced | L3+ |
| ops-cdc-debezium | Change Data Capture: Logical Decoding، Binlog و Debezium + Kafka Connect | مفهوم | Advanced | L4+ |
| ops-security | امنیت دیتابیس: Least Privilege، RLS، TLS، رمزنگاری، Secrets، SQL Injection و Audit | مفهوم | Intermediate | L3+ |
| ops-backup-tooling | ابزارهای بکاپ برای هر دیتابیس: pgBackRest، WAL-G، XtraBackup، PBM، Medusa و Snapshot API | مفهوم | Intermediate | L3+ |
| ops-db-on-kubernetes | دیتابیس روی Kubernetes: StatefulSet، PV و Operatorها (CloudNativePG، Percona، K8ssandra، ECK) | مفهوم | Advanced | L4+ |
| ops-testing-local-dev | تست و توسعهٔ محلی با دیتابیس: Testcontainers، Fixture/Factory و Migration در CI | مفهوم | Intermediate | L2+ |

## d20 (فاز 20) 🧠 الگوهای معماری داده
الگوهایی که داده را بین سرویس‌ها و Storeها جابه‌جا و سازگار نگه می‌دارند: Caching، CQRS، Event Sourcing، Outbox، Polyglot Persistence و ETL/ELT/Lakehouse.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| pat-caching-strategies | استراتژی‌های Caching: Cache-aside، Read/Write-through، Write-behind، Invalidation و Stampede | مفهوم | Intermediate | L2+ |
| pat-cqrs-read-models | CQRS و Read Modelها: جداسازی مدل نوشتن از مدل‌های خواندن | مفهوم | Advanced | L4+ |
| pat-event-sourcing | Event Sourcing: رویداد به‌عنوان منبع حقیقت | مفهوم | Expert | L6+ |
| pat-transactional-outbox | Transactional Outbox و Inbox: انتشار مطمئن رویداد بدون Dual Write | مفهوم | Advanced | L4+ |
| pat-polyglot-persistence | Polyglot Persistence: دیتابیس مناسب برای هر Bounded Context | مفهوم | Expert | L6+ |
| pat-etl-elt-lakehouse | ETL، ELT و Lakehouse: Airflow، dbt، Spark، Parquet و Iceberg/Delta | مفهوم | Advanced | L4+ |

## d21 (فاز 21) 🎯 انتخاب دیتابیس و مطالعات موردی System Design
چارچوب تصمیم برای انتخاب دیتابیس، تخمین ظرفیت با اعداد واقعی، چهار طراحی کامل (چت، فروشگاه، دفتر کل مالی، تحلیل و جستجو) و استراتژی و حاکمیت داده در سطح سازمان.

| id | عنوان | نوع | سطح | L |
|---|---|---|---|---|
| sel-decision-framework | چارچوب تصمیم برای انتخاب دیتابیس | مفهوم | Advanced | L5+ |
| sel-capacity-estimation | تخمین ظرفیت: QPS، رشد Storage، IOPS، Working Set و کانکشن‌ها | مفهوم | Advanced | L4+ |
| sel-case-chat | مطالعهٔ موردی: پیام‌رسان و چت در مقیاس بزرگ (Cassandra/ScyllaDB به سبک Discord) | مفهوم | Expert | L5+ |
| sel-case-ecommerce | مطالعهٔ موردی: فروشگاه اینترنتی (PostgreSQL + Redis + Elasticsearch) | مفهوم | Advanced | L4+ |
| sel-case-ledger | مطالعهٔ موردی: دفتر کل مالی (Ledger) با PostgreSQL، Double-entry و Idempotency | مفهوم | Expert | L5+ |
| sel-case-analytics-search | مطالعهٔ موردی: تحلیل رویداد و جستجو (ClickHouse + Elasticsearch) | مفهوم | Expert | L5+ |
| sel-org-data-strategy | استراتژی داده در سطح سازمان: Paved Road، استانداردها، هزینه و مهاجرت | مفهوم | Expert | L7+ |
| sel-data-platform-governance | پلتفرم داده و حاکمیت: Data Contract، مالکیت، Lineage، انطباق (GDPR) و هزینه | مفهوم | Expert | L8+ |

## جدول‌های مقایسه (13)

- SQL در برابر NoSQL
- B-Tree در برابر LSM-Tree
- PostgreSQL در برابر MySQL
- PostgreSQL JSONB در برابر MongoDB
- Cassandra در برابر ScyllaDB در برابر DynamoDB
- Elasticsearch در برابر PostgreSQL Full-Text
- ClickHouse در برابر PostgreSQL در برابر DuckDB برای تحلیل
- Redis در برابر Memcached در برابر Valkey/DynamoDB DAX
- ماتریس سطح ایزوله در برابر ناهنجاری‌ها
- حالت‌های Replication
- استراتژی‌های Sharding
- انواع Index و بهترین کاربرد
- پایگاه‌های داده برداری

## سناریوهای اینسیدنت (15)

- خواندن کهنه (stale read) به‌خاطر replication lag — L3+
- Bloat و نزدیک شدن به Transaction ID Wraparound در PostgreSQL — L3+
- طوفان Deadlock در سرویس سفارش — L3+
- Migration که ACCESS EXCLUSIVE lock گرفت و سایت را قفل کرد — L3+
- اتمام اتصال‌ها (connection exhaustion) — L2+
- Timeout در Cassandra به‌خاطر Tombstone — L5+
- Hot Partition در DynamoDB / Cassandra — L5+
- انفجار mapping و خوشه red در Elasticsearch — L3+
- آرایه بی‌پایان و عبور از سقف 16MB در MongoDB — L3+
- Redis: Eviction، کلید بزرگ و KEYS * که سرور را قفل کرد — L2+
- تغییر ناگهانی query plan بعد از drift آمار — L3+
- Resharding که اشتباه پیش رفت — L5+
- Split Brain بعد از قطع شبکه و failover — L5+
- بکاپی که هرگز restore نشده بود — L3+
- Long-running transaction و رشد بی‌پایان WAL / replication slot — L4+

## خلاصه

- 22 فاز، 143 موضوع
- توزیع L: L1+: 9، L2+: 24، L3+: 36، L4+: 19، اختیاری: 28، L5+: 18، L6+: 7، L7+: 1، L8+: 1
