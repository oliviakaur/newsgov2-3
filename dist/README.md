# Newsgo CSR

Frontend client-side rendered vanilla JavaScript. `index.html` menunjuk ke backend melalui `data-newsgo-api-origin`; ganti nilainya ke origin API VPS saat deploy, lalu daftarkan origin frontend tersebut di `allow-domain` backend.

Route artikel memakai `/{database}/{slug}`. Hosting static wajib melakukan fallback route tersebut ke `index.html`.

Untuk SEO, proxy hanya `sitemap.xml` dan `rss.xml` ke endpoint backend yang sama. Atom khusus frontend Blogspot dan tidak perlu dipasang di frontend CSR. Backend membentuk URL artikel sesuai origin frontend dari query `domain`, misalnya `https://powerhouse.my.id/api/sitemap.xml?db=automotive&domain=https%3A%2F%2Fpowerhouse.my.id`.

Feed publik aktif secara default. Set `PUBLIC_XML_FEEDS=false` di backend jika feed harus tetap memakai autentikasi legacy.
