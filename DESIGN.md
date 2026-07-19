---
name: Vitrin
description: Booking.com'dan ilham alan, güven veren ve kart tabanlı bir arayüz dili — koyu lacivert + parlak mavi marka rengi, sarı vurgu rengiyle öne çıkan rozet/fırsat unsurları, bol beyaz alan.
version: alpha
colors:
  primary: "#003580"
  secondary: "#0071c2"
  accent: "#febb02"
  success: "#008009"
  danger: "#cc0000"
  neutral-900: "#262626"
  neutral-600: "#6b6b6b"
  neutral-100: "#f5f5f5"
  white: "#ffffff"
typography:
  h1:
    fontFamily: Inter
    fontSize: 2.5rem
    fontWeight: 700
    lineHeight: 1.2
  h2:
    fontFamily: Inter
    fontSize: 1.75rem
    fontWeight: 700
    lineHeight: 1.25
  body-md:
    fontFamily: Inter
    fontSize: 1rem
    fontWeight: 400
    lineHeight: 1.5
  label-sm:
    fontFamily: Inter
    fontSize: 0.75rem
    fontWeight: 600
    letterSpacing: 0.02em
rounded:
  sm: 4px
  md: 8px
  lg: 16px
spacing:
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 32px
components:
  button-primary:
    backgroundColor: "{colors.secondary}"
    textColor: "{colors.white}"
    typography: "{typography.body-md}"
    rounded: "{rounded.sm}"
    padding: 12px 20px
  button-secondary:
    backgroundColor: "{colors.white}"
    textColor: "{colors.secondary}"
    typography: "{typography.body-md}"
    rounded: "{rounded.sm}"
    padding: 12px 20px
  badge-discount:
    backgroundColor: "{colors.success}"
    textColor: "{colors.white}"
    typography: "{typography.label-sm}"
    rounded: "{rounded.sm}"
  badge-highlight:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.neutral-900}"
    typography: "{typography.label-sm}"
    rounded: "{rounded.sm}"
  card:
    backgroundColor: "{colors.white}"
    rounded: "{rounded.lg}"
    padding: "{spacing.md}"
---

## Overview

**Vitrin**, Booking.com'un görsel dilinden ilham alır: koyu lacivert ana marka rengi, parlak mavi aksiyon rengi, sarı vurgu rengiyle dikkat çeken rozet/fırsat unsurları ve bol beyaz alan kullanan kart tabanlı bir düzen. Amaç, kullanıcının ürün fotoğrafından vitrin/kampanya görseli ürettiği akışın (sahne seçimi, metin düzenleme, boyut/dışa aktarma ekranları) güvenilir, hızlı ve işlevsel — bir rezervasyon platformu kadar net — hissetmesidir. Görsel dil, üretilecek kampanya görselinin kendisine değil, bu görseli üreten uygulama arayüzüne uygulanır.

## Colors

- `primary` (#003580): Üst bar, logo, başlıklarda ve koyu vurgu gereken alanlarda kullanılır.
- `secondary` (#0071c2): Ana aksiyon rengi — birincil butonlar, linkler, seçili/aktif durumlar.
- `accent` (#febb02): Sarı vurgu — yalnızca rozet, "önerilen sahne" veya kısa dikkat çekici etiketlerde, geniş alanlarda kullanılmaz.
- `success` (#008009): İndirim/kampanya rozetlerinde ve olumlu durum mesajlarında.
- `danger` (#cc0000): Hata mesajları ve geri alınamaz aksiyon uyarılarında.
- `neutral-900` / `neutral-600`: Sırasıyla birincil ve ikincil metin rengi.
- `neutral-100`: Bölüm arka planları, kartların oturduğu zemin.
- `white`: Kart ve panel arka planı.

## Typography

Yazı ailesi olarak Inter kullanılır — Booking.com'un sistem fontu gibi yüksek okunabilirlikte, nötr bir sans-serif. `h1`/`h2` başlıklarda kalın ağırlık (700) ile netlik sağlar; `body-md` arayüz metinleri için, `label-sm` ise rozet ve etiketler için büyük harf/geniş harf aralığıyla kullanılır.

## Layout

12 kolonlu grid üzerine kurulu, kart tabanlı bir düzen. `spacing` ölçeği (4/8/16/24/32px) tüm boşluklarda tutarlı kullanılır. Sayfalar arasında bol beyaz alan bırakılır; içerik yoğunluğu Booking.com'daki gibi orta-yüksek olsa da her kart kendi içinde nefes alan bir boşluğa sahiptir. Akış adımları (yükle → sahne seç → metni düzenle → dışa aktar) yatay bir adım göstergesiyle üstte sabit kalır.

## Elevation & Depth

Kartlar hafif bir gölgeyle (`0 1px 2px rgba(0,0,0,0.08)`) zeminden ayrılır. Rozetler ve etiketler düz (gölgesiz) kalır. Modal ve dışa aktarma paneli gibi geçici katmanlar daha belirgin bir gölgeyle (`0 4px 16px rgba(0,0,0,0.16)`) öne çıkar.

## Shapes

Köşe yuvarlaklığı üç kademeli: `rounded.sm` (4px) buton ve giriş alanlarında, `rounded.md` (8px) küçük panellerde, `rounded.lg` (16px) kartlarda. Tam daire yalnızca ikon butonları ve avatar benzeri küçük öğelerde kullanılır; büyük yüzeylerde köşeli/keskin şekillerden kaçınılır.

## Components

- `button-primary`: Ana aksiyonlar için (örn. "Görseli Oluştur", "Dışa Aktar") — `secondary` mavi zemin, beyaz metin.
- `button-secondary`: İkincil aksiyonlar için (örn. "Vazgeç", "Şablonu Değiştir") — beyaz zemin, mavi kenarlık/metin.
- `badge-discount`: Kampanya/indirim etiketleri — yeşil zemin.
- `badge-highlight`: "Önerilen sahne", "Yeni" gibi öne çıkarma etiketleri — sarı zemin.
- `card`: Sahne şablonu, boyut seçeneği gibi seçilebilir öğelerin kapsayıcısı.

## Do's and Don'ts

**Yap:**
- Birincil aksiyonlarda tek bir renk (`secondary` mavi) kullan, tutarlılığı koru.
- `accent` sarısını yalnızca küçük rozet/etiketlerde, dikkat çekmesi gereken tek bir noktada kullan.
- Kartlar ve paneller arasında `spacing` ölçeğine sadık kal.

**Yapma:**
- `accent` sarısını büyük arka plan alanlarında veya birden fazla bileşende aynı anda kullanma — vurgu gücünü kaybeder.
- Aynı ekranda ikiden fazla vurgu rengini (accent, danger, success) birlikte kullanma.
- Uygulama arayüzünün görsel diliyle, kullanıcının yüklediği ürün fotoğrafını veya üretilen kampanya görselini karıştırma — bu tasarım sistemi yalnızca uygulama kabuğuna (shell) uygulanır, üretilen çıktıya değil.
