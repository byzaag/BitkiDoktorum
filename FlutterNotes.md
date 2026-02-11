# flutter--> mobil app enviorentment
Flutter'da her şey "Widget" adını verdiğimiz kutucuklardan oluşur. Flutter widget’ları, her biri belirli bir işlevi yerine getiren ve uygulamanın görüntüsünü oluşturan yapılardır.Bu küçük parçaları (Widget'ları) iç içe koyarak veya alt alta dizerek bir uygulama ekranı oluşturursun. 
## Dart dili kullnaılır ; ile biter bloklar { ile açılır}
Flutter projesi açtığında lib klasörünün içinde main.dart dosyası olur. Her şey burada başlar.
Widget türleri: Gövde #Root Widget'tır. Kodun en başında runApp() diye bir komut vardır. İşte onun içine yazdığın ilk Widget senin Root'undur.Genellikle bu MaterialApp olur.
StatelessWidget--> Ekranda hareket etmeyen, kullanıcının tıklamasıyla şekil değiştirmeyen şeyler için.
StatefulWidget---> Ekrana çizilir ama sonra değişebilir. İçinde "State" (Durum) denilen bir hafıza taşır.Bu widget'ın içinde ne zaman bir şeyi değiştirmek istesen setState() komutunu verirsin.

**Widget sınıfından türetilen HER ŞEY (ister Stateless olsun ister Stateful olsun) teknik olarak "Immutable" (Değişmez) olmak zorundadır.**
## Array yapısı: List<String> hastaliklar = ["Mantar", "Bakteri", "Virüs"];
## function yapısı:
String selam(String isim) {
  return "Merhaba $isim";
}
## Flutter Lifecycle (StatefulWidget için)
Bir sayfa açıldığında sırasıyla şunlar olur:
createState()
   ↓
initState()
   ↓
build()
   ↓
(setState olursa tekrar build)
   ↓
dispose() (sayfa kapanırken)

## <img width="300" height="100" alt="image" src="https://github.com/user-attachments/assets/3d1ba492-7eb8-44ed-a1fe-fd4fcfb60c61" />
Flutter burada State nesnesini oluşturur. Bu kısım otomatik oluşur.

## initState() 🔥
Sayfa ilk kez oluşturulurken çalışır.Burada ne yapılır? API çağrısı--Controller başlatma--Animation başlatma--
Veri hazırlama
<img width="400" height="150" alt="image" src="https://github.com/user-attachments/assets/0399fb20-5e39-4e27-8a36-c1131ca09da7" />

## build() 🎨 Ekranı çizen fonksiyon.
<img width="300" height="150" alt="image" src="https://github.com/user-attachments/assets/82a159ce-beea-45a9-8557-a3d35712b9f4" />

## setState() Ekranı yeniler.Bu ne yapar? 👉 build() yeniden çalışır 👉 UI güncellenir
<img width="300" height="165" alt="image" src="https://github.com/user-attachments/assets/24f5c2fa-55d3-43f5-9931-9dbe5ba0f4c2" />

## dispose() 💀  Sayfa kapatılırken çalışır. 📌 Burada ne yapılır?--Controller kapatma--Stream iptal etme--Bellek temizleme. Eğer dispose etmezsen memory leak olur.
<img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/b8d7268c-6d87-4d31-8459-52bfd5bd650f" />

## <img width="282" height="221" alt="image" src="https://github.com/user-attachments/assets/5fe62819-7f4d-4569-be92-9d6b3020c4da" />
## <img width="235" height="492" alt="image" src="https://github.com/user-attachments/assets/ca383f4b-89eb-4119-b5e4-6acd655bf2c7" />
setstate yapısı olmazsa build cagrılamaz ve sayı değişimi ekrana verilemez.
## Büyük projelerde bu setstate yapısı kullanılmaz cunku etState sadece bulunduğu sayfayı günceller.Diğer sayfalar güncellenmez 😬 bundan dolayı karmaşıklıklar oluşur. Ve  rebuild maaliyetli olabilir.
SetState yerine State Management çözümleri: Provider (en yaygın)--Riverpod (daha modern)--Bloc (kurumsal)--GetX (pratik)--
Bunlar ne yapar?
👉 Global state tutar
👉 Her yerden erişilir
👉 Sadece gereken widget rebuild olur
## Navigator → yeni sayfa aç
MaterialPageRoute → bu sayfayı Material tasarım animasyonuyla aç
 builder → hangi sayfa açılacak? → DetaySayfa <br/>
<img width="500" height="196" alt="image" src="https://github.com/user-attachments/assets/85877467-4354-4290-8801-347b9a3bad5d" />

## örneks
<img width="417" height="760" alt="image" src="https://github.com/user-attachments/assets/fd977299-f230-4a41-9d75-61656a527f71" />

<img width="198" height="405" alt="image" src="https://github.com/user-attachments/assets/5bbfb011-0459-4bb9-bba1-2d6edf91709b" />


