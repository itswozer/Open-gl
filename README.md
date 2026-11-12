# Open GL Path Tracer

Tarayıcıda çalışan, harici grafik kütüphanesi kullanmayan progresif path tracing demosu. WebGL 2 destekleniyorsa ışın izleme GPU'da çalışır; GPU bağlamı kaybolduğunda veya WebGL 2 kullanılamadığında çok çekirdekli CPU Worker motoru devreye girer.

## Çalıştırma

`genetik-algoritma.html` dosyasını güncel bir tarayıcıda açın. Önerilen tarayıcı WebGL 2 desteklemelidir. GPU hızlandırma kullanılamazsa CPU yedek motoru daha yavaş çalışabilir.

## Kontroller

- `W`, `A`, `S`, `D`: kamerayı hareket ettir
- Canvas üzerinde boş alanda sürükleme: kamerayla etrafa bak
- Küre üzerinde sürükleme: küreyi sahnede taşı
- Çözünürlük menüsü: önizleme, Full HD, DCI 2K veya QHD seç
- GPU örnekleme kaydırıcısı: her karede GPU'nun hesapladığı örnek sayısını ayarla

Kamera, nesne veya çözünürlük değiştiğinde progresif örnek birikimi sıfırlanır. Yüksek çözünürlükler daha fazla GPU belleği ve işlem gücü gerektirir.

## Teknik

- WebGL 2 fragment shader ile GPU path tracing
- GPU bağlamı geri kazanımı ve CPU Worker yedeği
- CPU yedek motorunda küre kesişimleri için BVH
- Diffüz ve ayna yüzeyler, emissive alan ışığı, Monte Carlo örnekleme
- Tek HTML uygulaması; harici runtime kütüphanesi yok
