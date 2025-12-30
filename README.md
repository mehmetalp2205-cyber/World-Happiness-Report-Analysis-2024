2024 Dünya Mutluluk Raporu Analizi (World Happiness Report Analysis)

Proje Sahibi: Mehmet Alp Yıldırım

Projenin Amacı
Bu projenin temel amacı, 2024 Dünya Mutluluk Raporu veri setini kullanarak ülkelerin mutluluk skorlarını etkileyen faktörleri incelemek, veriyi temizleyip analiz edilebilir hale getirmek ve ekonomik göstergelerin mutluluk üzerindeki gerçek etkisini veri görselleştirme teknikleriyle kanıtlamaktır.
Proje kapsamında sadece "en mutlu ülke hangisi" sorusuna değil, "Bir ülkeyi mutlu yapan formül nedir?" sorusuna istatistiksel yanıtlar aranmıştır.

1. Veri Hazırlığı ve Temizlik 
Kaggle'dan temin edilen ham veri seti üzerinde analiz öncesi şu işlemler uygulandı:

Sütun İsimlendirme: Kod okunabilirliğini artırmak için karmaşık sütun isimleri standart Snake_case formatına  çevrildi.
Eksik Veri Yönetimi: Veri setinde tespit edilen eksik (NaN) değerlere sahip satırlar, analizin tutarlılığını korumak amacıyla veri setinden çıkarılmıştır.
Veri Tipi Kontrolü: Sayısal analizlerin hatasız yapılabilmesi için tüm metriklerin 'float' sayısal tipinde olduğu doğrulanmıştır.
Veri Setinde Hata Kontrolü: Veri setinde olabilecek hatalar ve eksikler analiz edilmiş lakin veri setinde bir hata bulunamamıştır. Bu durum kullanılan veri setinin düzenli yapısından kaynaklıdır.


2. Görselleştirme ve Analiz Süreci

2.1-Dünya Genelinde Mutluluk Dağılımı
Çizilen histogram grafiği ile dünya genelindeki mutluluk puanlarının dağılımı incelenmiştir. Skorların büyük çoğunluğunun 4.5 ile 6.5 arasında toplandığı, yani dünyanın "ortalama bir mutlulukta" olduğu saptanmıştır.

2.2-Zirve ve Dip: En İyi ve En Kötü 10 Ülke
'sort_values' fonksiyonu kullanılarak yapılan sıralamada:
En Mutlu: Finlandiya ve diğer İskandinav ülkeleri, yüksek gelir ve sosyal haklarla listenin başında yer aldı.
En Mutsuz: Afganistan ve Lübnan gibi siyasi/ekonomik istikrarsızlık yaşayan ülkeler son sırada kaldı.
Bulgu: En mutlu ve en mutsuz ülke arasında yaklaşık 3 katlık devasa bir puan farkı bulunması bize birçok şeyi anlatmaktadır.

2.3-Bölgesel Farklılıklar
Kıtalara göre yapılan gruplandırmada (groupby), Kuzey Amerika ve Avrupa bölgesinin ortalamasının, Sahra Altı Afrika bölgesinden belirgin şekilde yüksek olduğu tespit edildi. Bu durumda zaten ilk ve son 10 ülke grafiklerinde yukarıda görünmekteydi.


2.4-İlişki Analizi (Korelasyon & Isı Haritası)
Faktörlerin birbirini nasıl etkilediğini görmek için Isı Haritası (Heatmap) oluşturuldu:
Mutluluk ile en güçlü pozitif ilişki GDP (Ekonomi) ve Sosyal Destek arasında çıktı. Bu durum zaten tahmin edilen bir sonuçtu.
Şaşırtıcı bir şekilde Cömertlik (Generosity) kavramının mutlulukla çok düşük bir ilişkisi olduğu görüldü. Bu durum beni bu görevde en çok şaşırtan şey oldu.Çünkü mutlulukla bağdaştırdığım insanlık kavramının en temel davranışlarından biri bence cömertlikti.


3. Derinlemesine Analiz: Mutluluk Sadece Para'dan mı ibaret?

Projenin en kritik aşamasında, "Ekonomi/Para her şey midir?" sorusuna yanıt aramak için Çok Değişkenli Analizler yapıldı. Grafikler tek tek incelendi ve yorumlandı.

3.1- 3D Scatter Plot: Gelir, Sağlık ve Mutluluk üçlüsü aynı anda incelendi. Geliri yüksek olup sağlığı kötü olan ülkelerin mutlulukta geride kaldığı görüldü. Bu durumun tam tersinde de aynı şekilde mutluluğu etkilediği saptandı.


3.2- Yolsuzluk Algısı (Scatter Plot): Zengin olmasına rağmen yolsuzluk algısı yüksek olan ülkelerin mutluluk sıralamasında potansiyellerinin altında kaldığı tespit edildi. Günümüz dünyası düşünüldüğünde özellikle az gelişmiş orta doğu ve afrika ülkelerinde bu durumu canlı canlı izlemek ve saptamak mümkün bir durum.

Kişisel Değerlendirme:

Analiz süreci göstermiştir ki; ekonomik güç (GDP) mutluluk için gerekli bir şarttır ancak yeterli değildir. Toplumun devlete duyduğu güven (Düşük Yolsuzluk) ve bireysel özgürlükler, en az bankadaki para kadar mutluluğu etkilemektedir.

Kullanılan Teknolojiler
Python (Pandas, NumPy)
Görselleştirme: Plotly (İnteraktif), Seaborn, Matplotlib
Ortam: Notebook
