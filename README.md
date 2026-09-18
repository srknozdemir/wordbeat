# wordbeat

Metronom temposunda tek tek kelime gösteren okuma hızı ve göz hareketi alıştırması — okumaya yeni başlayan çocuklar ve yetişkinler için.

**[Uygulamayı aç](https://srknozdemir.github.io/wordbeat/)** · [English](README.md)

---

## Ne yapıyor

Bir kelime beliriyor, bir tık duyuluyor, kelime yerini bir sonrakine bırakıyor. Okuyan kişi her kelimeyi göründüğü anda sesli söylüyor; tempoyu okuyan değil, metronom belirliyor. Seans ilerledikçe harf harf sökmek yerine kelimeyi bütün olarak tanımak zorunda kalıyor, çünkü tempo başka bir şeye vakit bırakmıyor.

Alıştırmanın niteliğini iki ayar belirliyor:

- **Kelimenin nerede çıkacağı.** Ekranın ortasında sabit durursa gözler yerinde kalır, yalnızca tanıma çalışılır. Ekranda gezinirse gözlerin önce kelimeyi bulması, sonra okuması gerekir; alıştırmanın göz hareketi tarafı burada devreye giriyor.
- **Ne hızda ilerleyeceği.** Kelime başına 3 saniyeden 0,2 saniyeye kadar, yani dakikada 20 ile 300 kelime arasında. Ayrıca her on kelimede aralığı %5 kısaltan bir seçenek var; böylece kimse ayarlara dokunmadan seans kendiliğinden zorlaşıyor.

## Özellikler

- Her dil için iki liste: **Çocuk** (kısa, kolay kelimeler) ve **Yetişkin** (uzun kelimeler)
- **Türkçe ve İngilizce** — hem kelime listeleri hem arayüzün tamamı
- Hazır tempo kademeleri ve ince ayar sürgüsü, yanında dakikadaki kelime karşılığı
- Her kelimede metronom tıkı, her dördüncü vuruşta hafifçe tiz
- Sabit ya da gezinen kelime, gezinme için üç genişlik kademesi
- 20, 50, 100 kelimelik ya da sınırsız seans, ilerleme çubuğuyla
- Gündüz ve gece modu: fildişi üzerine siyah ya da siyaha yakın zemin üzerine fildişi
- Seans sonunda özet: okunan kelime, süre, dakikadaki kelime
- Okuma sırasında klavye denetimi — boşluk duraklatır, Esc bitirir, yön tuşları tempoyu değiştirir
- Ayarlar bir sonraki açılışta hatırlanıyor

## Kullanımı

Bağlantıyı herhangi bir cihazda açmanız yeterli. Telefonda tarayıcıdan açıp *Ana Ekrana Ekle* derseniz adres çubuğu olmadan, uygulama gibi açılır.

Uygulamadan beklentiyi yerinde tutmak için birkaç not:

- Doğru gelenden yavaş başlayın. Kelime başına 1,5 saniyede rahat okuyan bir çocuk 1,0 saniyede zorlanır ve bırakır.
- Sesli okumak önemli. Tık, okuyana yetişilecek bir hedef verir; kendi sesini duyması da atladığı kelimeleri fark etmesini sağlar.
- Seansları kısa tutun. Yirmi ile elli kelime yeterlidir; bu alıştırma sıradan okumadan farklı bir yorgunluk veriyor.
- Gezinme modu göründüğünden zordur. Sabit modda rahatlık yerleşmeden ona geçmeyin.

Bu bir alıştırma aracıdır; tanı koyan ya da tedavi eden bir araç değildir. Okuma güçlüğü sürüyorsa bu, uygulamanın değil öğretmenin ya da bir uzmanın konusudur.

## Kendi kopyanızı çalıştırmak

Uygulamanın tamamı tek bir HTML dosyası; derleme adımı, bağımlılık ya da sunucu gerektirmiyor. `index.html` dosyasını indirip herhangi bir tarayıcıda açabilir ya da herhangi bir statik sunucuya koyabilirsiniz.

GitHub Pages'te yayımlamak için: bir depo açın, `index.html` dosyasını yükleyin, **Settings → Pages** bölümünde kaynak olarak *Deploy from a branch*, dal olarak `main`, klasör olarak `/ (root)` seçin. Adres bir iki dakika içinde beliriyor.

## Kelime listelerini değiştirmek

Listeler `index.html` içindeki betiğin başında tek bir nesnede duruyor:

```js
const WORDS = {
  en:{ kids:("cat dog sun ...").split(" "), adult:("absolute abundant ...").split(" ") },
  tr:{ kids:("ana ada ata ...").split(" "), adult:("anlayış araştırma ...").split(" ") }
};
```

Kelimeler tek boşlukla ayrılıyor. Metni düzenleyip kaydetmek ve sayfayı yenilemek yeterli. Her liste karıştırılıyor ve tükenene kadar tekrarsız veriliyor; dolayısıyla liste uzunluğu yalnızca kelimelerin ne kadar sonra yeniden geleceğini etkiliyor.

Üçüncü bir dil eklemek için `WORDS` nesnesine bir anahtar, `T` çeviri nesnesine bir blok ve dil düğmelerine bir düğme eklemek gerekiyor.

## Nasıl yapıldı

Yalın HTML, CSS ve JavaScript. Tık sesi dosyadan çalınmıyor, Web Audio API ile üretiliyor. Okuma yazı tipi, okuma akıcılığı için tasarlanmış [Lexend](https://www.lexend.com/); arayüzde Figtree kullanılıyor. Ayarlar `localStorage` içinde tutuluyor.

Chrome, Safari, Firefox ve Edge'in güncel sürümlerinde, masaüstünde ve mobilde çalışıyor. iOS'ta dosyanın Dosyalar uygulamasından değil bir adresten açılması gerekiyor; Safari yerel bir HTML dosyasını betikleriyle birlikte açmıyor, bu yüzden yayımlanmış bağlantıyı kullanın.

## Yapılacaklar

- Uygulama simgesi ve dosyaya gömülü yazı tipleri, çevrimdışı kullanım için
- Capacitor ile paketlenmiş iOS ve Android sürümleri
- Türkçe ilk okuma öğretiminin ilk aşaması için hece sayısına göre kademelendirilmiş listeler

## Hazırlayan

Serkan Özdemir — Isparta Uygulamalı Bilimler Üniversitesi.

## Lisans

MIT. Kullanabilir, değiştirebilir, paylaşabilirsiniz; atıf beklenmiyor ama memnuniyetle karşılanır.
