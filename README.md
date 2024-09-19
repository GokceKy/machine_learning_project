# machine_learning_project
# Veri Seti Üzerinde Gözetimli ve Gözetimsiz Öğrenme Algoritmalarının Karşılaştırılması

Bu proje, kredi kartı dolandırıcılığını tespit etmek amacıyla gözetimli (Logistic Regression) ve gözetimsiz (KMeans) öğrenme algoritmalarını aynı veri seti üzerinde karşılaştırmayı amaçlamaktadır. Hem model performanslarını analiz ettik hem de hangi öğrenme türünün bu veri seti için daha uygun olduğuna dair sonuçlar çıkardık.

## Proje İçeriği
Veri setine [creditcardfraud](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
[Kaggle Notebook'u](https://www.kaggle.com/code/gokcekelesyilmaz/aygazml-gk)

1. **Veri Seti:** Bu çalışmada kullanılan veri seti, kredi kartı dolandırıcılığı tespitine yönelik bir veri setidir. Veri seti dengesizdir, yani dolandırıcılık işlemlerinin sayısı normal işlemlere kıyasla oldukça düşüktür. Bu durum, özellikle gözetimli öğrenme algoritmalarında dikkat edilmesi gereken bir husustur.

2. **Algoritmalar:**
   - **Gözetimli Öğrenme (Logistic Regression):** Hedef etiketlerinin bilindiği, denetimli bir öğrenme yöntemidir. Bu çalışmada dolandırıcılık olup olmadığını tahmin etmek için Logistic Regression modeli kullanılmıştır.
   - **Gözetimsiz Öğrenme (Isolation Forest):** Veri setinde herhangi bir etiket bilgisi olmadan sınıfları gruplamak için gözetimsiz öğrenme kullanılmıştır. 

### Logistic Regression

- **Doğruluk**: 0.9992
- **Kesinlik**: 0.88
- **Duyarlılık**: 0.64
- **F1 Skoru**: 0.74

**Karışıklık Matrisi**:
[[56855     9]
 [   35    63]]

### Isolation Forest

- **Doğruluk**: 0.999
- **Kesinlik**: 0.29
- **Duyarlılık**: 0.33
- **F1 Skoru**: 0.31

**Karışıklık Matrisi**:
[[283945    370]
 [   372    120]]

 
Algoritmaların Karşılaştırılması
Bu projede iki farklı öğrenme yöntemi üzerinde aynı veri seti kullanılarak dolandırıcılık tespiti gerçekleştirilmiştir. Aşağıda bu iki modelin performans karşılaştırmaları yer almaktadır:

Gözetimli Öğrenme (Logistic Regression):

Kesinlik: Logistic Regression dolandırıcılık işlemlerini %88 kesinlik ile tespit edebilmiştir.
Duyarlılık: Duyarlılık oranı %64'tür, bu da modelin dolandırıcılıkları tespit etmede yeterli olduğunu göstermektedir.
F1 Skoru: %74 F1 skoru, modelin dengesiz veri setindeki performansını genel olarak iyi seviyede tutmuştur.
Gözetimsiz Öğrenme (Isolation Forest):

Kesinlik: Isolation Forest, %29 kesinlik ile dolandırıcılık işlemlerini doğru tahmin etmiştir.
Duyarlılık: Modelin dolandırıcılıkları bulma oranı %33 olmuştur, bu da modelin anormallikleri yakalama konusunda zorlandığını göstermektedir.
F1 Skoru: %31'lik F1 skoru, modelin performansının düşük olduğunu ortaya koymuştur.
Sonuçlar:
Gözetimli öğrenme (Logistic Regression), kredi kartı dolandırıcılığı tespiti için bu veri seti üzerinde çok daha iyi bir performans sergilemiştir. Bu da, etiketli veri kullanmanın dengesiz ve belirli sınıf farkları olan veri setlerinde daha iyi sonuçlar verebileceğini göstermektedir.

Gözetimsiz öğrenme (Isolation Forest) ise anormallik tespit etmeye çalışırken sınırlı başarı göstermiştir. Özellikle dengesiz veri setlerinde, gözetimsiz öğrenmenin performansı yetersiz kalmıştır.

Hiperparametre Optimizasyonu
Logistic Regression modeli üzerinde hiperparametre optimizasyonu yapılmış ve aşağıdaki parametreler ile modelin performansı artırılmıştır:

En İyi Parametreler: {'C': 0.1, 'penalty': 'l2', 'solver': 'liblinear'}
F1 Skoru: 0.716
Bu optimizasyon sonucunda model, dolandırıcılık tespitinde daha iyi bir performans göstermiştir.

Veri Seti ve Model Uygunluğu
Bu veri seti, etiketli veri ile çalışan gözetimli öğrenme algoritmaları için daha uygun bir yapıya sahiptir. Dengesiz veri setlerinde, gözetimli öğrenmenin kesinlik ve duyarlılık gibi metriklerde daha iyi performans göstermesi beklenir. Gözetimsiz öğrenme, dengesiz veri setlerinde anormallik tespit etmede yetersiz kalabilir.

Sonuç
Logistic Regression modeli, kredi kartı dolandırıcılığını tespit etmek için optimize edilmiş haliyle en iyi sonuçları vermiştir. Gözetimsiz öğrenme yöntemleri, özellikle dengesiz veri setlerinde dolandırıcılığı tespit etmede sınırlı başarı sağlamıştır.
