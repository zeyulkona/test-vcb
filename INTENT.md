# INTENT.md

## Bağlam
E-ticaret satıcıları ve küçük markalar, ürünlerini öne çıkaran kampanya/vitrin görselleri hazırlamak için genellikle bir tasarımcıya ya da zaman alan manuel düzenlemeye ihtiyaç duyuyor. Ellerinde arka planı beyaz/düz olan bir ürün fotoğrafı var, ancak bunu satışa hazır, bir sahne içine yerleştirilmiş ve kampanya mesajı içeren bir görsele dönüştürmek ayrı bir tasarım uzmanlığı gerektiriyor.

## Hedef
Kullanıcının yüklediği, arka planı beyaz/düz olan bir ürün fotoğrafını alıp; ürünü orijinaline birebir sadık kalacak şekilde dekupe eden, hazır bir sahne şablonuna yerleştiren ve üzerine düzenlenebilir kampanya metni ekleyen bir web uygulaması ile, tek akışta e-ticaret vitrin/kampanya görseli üretmek.

## Kullanıcı
E-ticaret satıcısı / küçük marka sahibi ve pazarlama-içerik ekipleri; tasarım bilgisi olmadan hızlıca kampanya görseli üretmek isteyen kullanıcılar.

## Başarı kriteri
- Dekupe edilen üründeki tüm detaylar (renk, logo, doku, yazı, şekil) orijinal fotoğrafla karşılaştırıldığında değişmeden korunur.
- Kullanıcı, en az 3 hazır sahne şablonu arasından seçim yapabilir.
- Platform, ürün/kampanya bilgisinden yola çıkarak kampanya metnini (başlık + vurgu/indirim ifadesi) otomatik önerir ve kullanıcı bu metni serbestçe düzenleyebilir.
- Kampanya metni, görsel üzerine ürünün üzerini kapatmayacak şekilde otomatik konumlandırılır.
- Kullanıcı, üretilen görseli en az 3 hazır boyut/format seçeneğinde (ör. Instagram kare post, Instagram story, site banner) indirebilir.
- Ürün fotoğrafı yüklendikten, sahne ve metin onaylandıktan sonraki üretim (render) süresi 30 saniyeyi geçmez.

## Kapsam dışı
- Ürünün kendisinin AI ile değiştirilmesi (renk/şekil/logo değişikliği, üründe retuş).
- Kullanıcının sahneyi serbest metinle tarif etmesi veya kendi arka plan görselini yüklemesi (ilk sürümde yalnızca hazır şablonlar kullanılır).
- Video veya animasyon çıktısı üretimi.
- Aynı görselde birden fazla ürünün bir arada gösterilmesi (collage).
- Üretilen görselin e-ticaret/sosyal medya platformlarına doğrudan otomatik yayınlanması/entegrasyonu.
- Kullanıcı hesap yönetimi, takım ve yetkilendirme özellikleri.
- Sahne şablonlarının kullanıcı tarafından düzenlenmesi veya yeni şablon eklenmesi (yönetici paneli).

## Riskler
- Dekupe (arka plan kaldırma) kalitesi; saç, şeffaf/parlak yüzey veya ince detaylarda hatalı kesime yol açabilir.
- Ürünün sahneye yerleştirilmesinde ışık, gölge ve perspektif uyumsuzluğu, görselin yapay durmasına neden olabilir.
- AI'ın önerdiği kampanya metni marka tonuna uymayabilir veya kampanya gerçeğini (fiyat/indirim doğruluğu) yansıtmayabilir; kullanıcı onayı olmadan yayınlanmamalı.
- Otomatik metin yerleşimi, bazı sahne/ürün kombinasyonlarında okunabilirliği düşürebilir veya ürünün önemli bir kısmını kapatabilir.
- Kullanılan AI görsel üretim/dekupe servisinin telif ve veri kullanım koşulları netleştirilmelidir.
