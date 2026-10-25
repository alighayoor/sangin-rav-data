# دادهٔ سنگین‌رو (SanginRav data)

بستهٔ گراف شهرهای ایران برای اپ «مسیریاب سنگین‌رو» — قالب `sanginrav.city.v1`.

| مورد | مقدار |
|---|---|
| شهر | ۱٬۳۱۰ بسته · ۸٬۴۱۴٬۸۸۶ قطعهٔ معبر · ۳۹۶٬۹۹۵ کیلومتر · ۱۰۳٫۸ مگابایت |
| release‌ها | `data-v1` (۱٬۰۰۰ بسته) + `data-v2` (۳۱۰ بسته) — گیت‌هاب در هر release حداکثر ۱٬۰۰۰ دارایی می‌پذیرد (D-119) |
| فهرست | [`index.json`](index.json) — همان فایلی که داخل APK است (`assets/index.json`) |
| هر بسته | zip شامل `manifest.json` + `restrictions.json` + `graph/{nodes,edges,*.bin.gz}` + لایهٔ POI |
| صحت | sha256 و حجم هر بسته در `index.json` آمده و اپ قبل از نصب هر دو را می‌سنجد |
| منبع و پروانه | دادهٔ معابر: © OpenStreetMap contributors — **ODbL 1.0** |

## دانلود مستقیم

```
https://github.com/alighayoor/sangin-rav-data/releases/download/data-v1/<slug>.sgz
https://github.com/alighayoor/sangin-rav-data/releases/download/data-v2/<slug>.sgz
```

شاخهٔ هر شهر در `index.json` با کلید `release` مشخص است (نبودن کلید = `data-v1`).

## آنچه اینجا نیست

دیتاست کامل اندازه‌گیری (`data/edges/*.parquet`)، گراف‌های خام (`data/graphs/`) و
PBF ایران در مخزن کد هم نگه داشته نمی‌شوند (D-117)؛ همه از
`https://download.geofabrik.de/asia/iran-latest.osm.pbf` با اسکریپت‌های
`pipeline/` در مخزن [sangin-rav](https://github.com/alighayoor/sangin-rav) بازتولید می‌شوند.

## صداقت داده

عرض معبر برای ۷٫۹٪ طول شبکه «اندازه‌گیری‌شده» (از ردپای بناهای OSM) و برای بقیه
«تخمین کلاس معبر» با برچسب اطمینان است. جزئیات: `docs/nation_report.html` در مخزن کد.
