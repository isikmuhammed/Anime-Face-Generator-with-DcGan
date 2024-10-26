# Anime-Face-Generator-with-DcGan
Bu proje, Deep Convolutional GAN (DCGAN) mimarisini kullanarak görüntü verilerini modellemek ve yeni örnekler üretmek amacıyla geliştirilmiştir. DCGAN'ler, görsel veri setlerinden yararlanarak yeni görüntüler üretmek için yaygın olarak kullanılan bir GAN türüdür. Bu projede, TensorFlow kullanılarak bir DCGAN modeli oluşturulmuş, belirlenen görsel veri seti üzerinde eğitilmiş ve modelin üretim yetenekleri test edilmiştir.
# İçindekiler

## Gereksinimler
  Veri Hazırlığı
  Model Yapısı
  Model Eğitimi ve Parametreler
  Sonuçlar ve Değerlendirme
  Kullanım Talimatları
Gereksinimler
  Python 3.x
  TensorFlow: DCGAN modelini oluşturmak ve eğitmek için kullanılır.
  NumPy: Veri işleme ve modelleme aşamalarında yardımcı olur.
  OpenCV ve PIL: Görsellerin işlenmesi ve düzenlenmesi için.
  Matplotlib: Modelin sonuçlarını görselleştirmek için.

## Veri Hazırlığı

1- Veri Seti: Projede kullanılan veri seti dataset/archive/data klasöründe tutulmaktadır.
2- Görsel Boyutlandırma: Görseller, DCGAN'in verimli bir şekilde eğitilebilmesi için 64x64 piksel boyutuna indirilmiştir. Her görselin RGB renk kanalları bulunmaktadır.
3- Parametreler:
  IMAGE_HEIGHT = 64, IMAGE_WIDTH = 64: Görsellerin boyutu.
  IMAGE_CHANNEL = 3: RGB renk kanalları.
  BATCH_SIZE = 128: Eğitimde kullanılan batch boyutu.
  LATENT_DIMENSION = 128: Rastgele gürültü vektörünün boyutu.
  EPOCHS = 30: Eğitim sürecindeki epoch sayısı.
  
## Model Yapısı
DCGAN modeli, geleneksel GAN mimarisine göre bazı derin öğrenme teknikleri ile güçlendirilmiştir:

1- Generator: Rastgele bir gürültü vektörünü (latent vektör) kullanarak sahte görüntüler üretir. DCGAN'de Transposed Convolutional katmanlar ve Batch Normalization kullanılır.
2- Discriminator: Üretilen görüntülerin gerçek veya sahte olduğunu ayırt etmeye çalışır. Convolutional katmanlar, modelin veri setindeki özellikleri öğrenmesini sağlar.
3- Loss Fonksiyonları:
  Generator Loss: Üretilen görsellerin olabildiğince gerçekçi olmasını sağlar.
  Discriminator Loss: Gerçek ve sahte görüntüler arasındaki farkı maksimize etmeye çalışır.

## Model Eğitimi ve Parametreler

Eğitim süreci, GAN mimarilerinde olduğu gibi Generator ve Discriminator modellerinin sırayla eğitilmesi ile gerçekleşir:
  Adım 1: Rastgele gürültü vektörleri Generator’a giriş olarak verilir ve sahte görüntüler üretilir.
  Adım 2: Discriminator, gerçek ve sahte görüntüleri kullanarak eğitilir.
  Adım 3: Generator, sahte görüntülerin gerçek gibi değerlendirilmesini sağlamak amacıyla yeniden eğitilir.
  
DCGAN, toplamda 30 epoch boyunca eğitilmiştir ve her epoch sonunda üretilen görüntüler kaydedilerek modelin gelişimi izlenmiştir.

## Sonuçlar ve Değerlendirme

Eğitim sürecinin sonunda:

  DCGAN modeli, veri setine benzer, anlamlı görseller üretme yeteneğine sahip hale gelmiştir.
  Modelin başarı seviyesi, Generator Loss ve Discriminator Loss değerleri ile gözlemlenmiş ve değerlendirilmiştir.
  Her epoch sonunda üretilen görüntüler kaydedilerek modelin zaman içindeki iyileşme süreci incelenmiştir.
 Üretilen örnekler genellikle veri setindekine benzer ve gerçekçi görseller sunmaktadır. Eğitim sonuçlarına göre bazı görsellerde daha iyi detayların üretildiği gözlemlenmiştir.

## Kullanım Talimatları

Notebook'u açın ve kütüphanelerin yüklendiğinden emin olun.
Veriyi hazırlamak ve DCGAN modelini oluşturmak için kod hücrelerini sırasıyla çalıştırın.
Model eğitimi tamamlandıktan sonra, üretilen görselleri inceleyebilir ve Generator'ın gerçekçi görseller üretme kapasitesini gözlemleyebilirsiniz.
