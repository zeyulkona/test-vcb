# MEMORY.md

Bu dosya, [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory) yaklaşımından ilham alarak bu depodaki bilgiyi nasıl katmanladığımızı ve güncel tuttuğumuzu tanımlar. **agentmemory'nin kendisi (sunucusu, hook'ları, vektör/BM25/grafik arama altyapısı) bu projeye kurulmaz** — burada benimsenen şey yalnızca onun 4 katmanlı hafıza konsolidasyon modeli ve "aynı şeyi tekrar tekrar anlatma" felsefesidir; bu proje şu an sadece markdown dosyalarından oluştuğu için katmanlar dosya bazlı ve insan/AI ajanı tarafından elle konsolide edilir.

## Neden bu dosya var

Her yeni Claude Code oturumu, önceki konuşmadaki bağlamı hatırlamaz. `INTENT.md` ve `DESIGN.md` gibi dosyalar zaten "kalıcı gerçekleri" tutuyor; bu dosya ise **bu gerçeklerin nasıl üretildiğini, nereye yazıldığını ve ne zaman güncellendiğini** tanımlayan üst-süreç kuralıdır — agentmemory'deki "Working → Episodic → Semantic → Procedural" konsolidasyon zincirinin bu depodaki karşılığı.

## Katmanlar ve bu depodaki karşılıkları

| agentmemory katmanı | Bu depodaki karşılığı | İçerik |
|---|---|---|
| **Working** (ham gözlem) | O anki konuşma / oturum | Henüz tartışılmamış, teyit edilmemiş fikirler, sorular, taslaklar. Kalıcı dosyalara yazılmaz. |
| **Episodic** ("ne oldu") | Git commit geçmişi | Her commit mesajı, o oturumda hangi kararın alındığını ve neden alındığını özetler — `git log` bu projenin oturum kaydıdır, ayrı bir CHANGELOG tutulmaz. |
| **Semantic** ("ne biliyorum") | `INTENT.md`, `DESIGN.md`, `CLAUDE.md` | Üzerinde el sıkışılmış, tartışmaya kapanmış kalıcı gerçekler: ne inşa ediyoruz (INTENT), nasıl görünüyor (DESIGN), oturuma başlarken ne okunmalı (CLAUDE). |
| **Procedural** ("nasıl yapılır") | Bu dosyanın "Süreç kuralları" bölümü + CLAUDE.md'deki iş akışı notları | Kararların nasıl alındığı, nereye yazıldığı, çakışma olduğunda ne yapılacağı. |

## Süreç kuralları

1. **Oluştur → Tartış → Arşivle.** Yeni bir karar önce taslak olarak ilgili dosyaya yazılır, kullanıcıyla tartışılır (`AskUserQuestion` veya açık soru ile), onaylanınca commit edilir. Onaylanmamış taslaklar semantic dosyalara (INTENT/DESIGN) kalıcı gerçek gibi yazılmaz.
2. **Tek kaynak, çakışma yok.** Aynı konuda iki dosyada birbirini çelişen ifade bulunmaz (agentmemory'nin "çelişki algılama"sının elle uygulanan hali). Bir karar değiştiğinde eski ifade silinir/güncellenir, yanına not olarak bırakılmaz.
3. **Doğru dosyaya yaz.** Ne/neden → `INTENT.md`. Nasıl görünüyor → `DESIGN.md`. Oturum başlangıcında ajanın okuması gereken özet ve proje durumu → `CLAUDE.md`. Süreç/karar kaydı → commit mesajları.
4. **`CLAUDE.md` asla drift etmemeli.** `INTENT.md` veya `DESIGN.md` değiştiğinde `CLAUDE.md`'deki özet aynı commit içinde güncellenir.
5. **Küçük, sık commit.** Her commit tek bir konsolide edilmiş kararı temsil eder (agentmemory'deki "working → episodic" sıkıştırmasının karşılığı); tartışılmakta olan birden fazla konu tek commit'te karıştırılmaz.
6. **Eskiyeni geçersiz kılar, silinmez ama üstü çizilir.** Kapsam dışı bırakılan veya vazgeçilen kararlar `INTENT.md`'nin "Kapsam dışı" bölümünde tutulur (agentmemory'deki decay/TTL yerine: unutmak yerine bilinçli olarak "kapsam dışı" diye işaretleme).

## Kapsam dışı

- agentmemory'nin sunucusunun, MCP araçlarının, hook'larının veya vektör/BM25 arama altyapısının bu projeye kurulması.
- Otomatik oturum/gözlem yakalama (SessionStart/PostToolUse gibi hook'lar) — bu depoda yok, çünkü henüz çalışan bir uygulama/kod tabanı yok.
- Ayrı bir CHANGELOG.md tutulması — bu rol git commit geçmişi tarafından karşılanıyor.

Kod tabanı büyüdüğünde (gerçek hook'ların çalışacağı bir uygulama ortaya çıktığında) bu dosya yeniden değerlendirilip agentmemory'nin otomatik katmanlarının hangi ölçüde gerçekten kurulacağına o zaman karar verilir.
