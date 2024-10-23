# Balık Türleri Sınıflandırma Projesi

Bu proje, derin öğrenme yöntemlerini kullanarak balık türlerini sınıflandırmak için yapay sinir ağları (ANN) kullanmaktadır. Proje, bir dizi görüntüden balık türlerini otomatik olarak tanımak amacıyla tasarlanmıştır.

## İçindekiler

- [Proje Hakkında](#proje-hakkında)
- [Kullanılan Teknolojiler](#kullanılan-teknolojiler)
- [Veri Seti](#veri-seti)
- [Model Mimarisinin Özeti](#model-mimarisinin-özeti)
- [Model Eğitimi](#model-eğitimi)
- [Sonuçlar ve Değerlendirme](#sonuçlar-ve-değerlendirme)
- [Projenin Kaggle Linki](#projenin-kaggle-linki)


## Proje Hakkında

Bu proje, farklı balık türlerini sınıflandırmak için görüntü işleme ve derin öğrenme tekniklerini kullanır. Hedefimiz, verilen bir balık resmi ile türünü otomatik olarak tanımlamaktır.

## Kullanılan Teknolojiler

- **Python**: Projenin temel programlama dili.
- **TensorFlow**: Derin öğrenme modeli geliştirmek için kullanılan kütüphane.
- **Keras**: TensorFlow ile entegre çalışarak ANN mimarisini kolayca oluşturmayı sağlar.
- **Scikit-learn**: Veri ön işleme, model değerlendirme ve istatistiksel analiz için kullanılır.
- **Pandas ve NumPy**: Veri işleme ve analizi için kullanılır.
- **Matplotlib ve Seaborn**: Verilerin görselleştirilmesi için kullanılır.
  
## Veri Seti

Kullanılan veri seti, **A Large-Scale Fish Dataset** adlı Kaggle veri setidir. Veri seti, çeşitli balık türlerini temsil eden birçok görüntü içerir. Veri setindeki her görüntü, ilgili balık türü ile etiketlenmiştir.

## Model Mimarisinin Özeti

Model, aşağıdaki katmanları içeren bir yapay sinir ağıdır:

- **Giriş Katmanı**: 225x225 boyutunda renkli görüntüler için giriş.
- **Düzleştirme Katmanı**: Görüntü verilerini düzleştirir.
- **Gizli Katmanlar**: 
  - 512 nöron, Leaky ReLU aktivasyon fonksiyonu.
  - 256 nöron, Leaky ReLU aktivasyon fonksiyonu.
  - 128 nöron, Leaky ReLU aktivasyon fonksiyonu.
  - 64 nöron, Leaky ReLU aktivasyon fonksiyonu.
- **Çıkış Katmanı**: 9 nöron, softmax aktivasyon fonksiyonu (balık türlerinin sınıflandırılması için).

## Model Eğitimi

Model, RMSprop optimizasyon algoritması ile derlenmiştir. Eğitimin her aşamasında doğruluk ve kayıp grafikleri görselleştirilmiştir. Ayrıca erken durdurma yöntemi kullanılarak overfitting (aşırı öğrenme) önlenmiştir.

```python
optimizer = tf.keras.optimizers.RMSprop(learning_rate=0.0001)
model.compile(optimizer=optimizer, loss='categorical_crossentropy', metrics=['accuracy'])
```



## Sonuçlar ve Değerlendirme
Model, test verileri üzerinde değerlendirildiğinde yüksek doğruluk oranları elde etmiştir. Eğitim ve doğrulama kayıpları ile doğrulukları grafikte gösterilmektedir.

Ayrıca, modelin performansı confusion matrix ve ROC-AUC eğrileri ile değerlendirilmiştir. Bu metrikler, modelin genel performansını görsel olarak anlamak için kullanılmıştır.

## Projenin Kaggle Linki
[kaggle-link]([URL](https://www.kaggle.com/code/okutanerdem/erdem-okutan-global-ai-hub-ann-project))




