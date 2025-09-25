Bu proje Akbank Derin Öğrenme Bootcamp içeriklerinden oluşturulmuştur.

GİRİŞ

Bu proje, Convolutional Neural Networks (CNN) kullanılarak yüz ifadelerinin otomatik olarak sınıflandırılmasını amaçlamaktadır. Görsel verilerden duyguları tanıyabilmek, insan-bilgisayar etkileşimi, güvenlik sistemleri, psikoloji araştırmaları ve akıllı asistan teknolojileri gibi birçok alanda önemli bir rol oynamaktadır.
Kullandığımız veri seti, farklı yüz ifadelerini (örneğin mutlu, üzgün, şaşkın, öfkeli vb.) içeren etiketlenmiş görsellerden oluşmaktadır. Bu veriler eğitim, doğrulama ve test aşamalarına uygun şekilde hazırlanmıştır. Görseller gri ölçekli formatta işlenmiş, yeniden boyutlandırılmış ve model için optimize edilmiştir.
Proje boyunca:

•	CNN modeli sıfırdan tasarlanarak temel bir sınıflandırma sistemi kuruldu,

•	Eğitim/Doğrulama doğruluk ve kayıp grafikleri ile süreç izlendi,

•	ROC analizi ve AUC değeri ile model başarımı ölçülerek yüzdelik performans raporlandı.

Bu proje, derin öğrenme tabanlı yüz ifadesi tanımanın temel adımlarını anlamak ve farklı yöntemlerin karşılaştırmasını yapmak için hazırlanmıştır. Teknik detaylar, adım adım açıklamalı şekilde not defteri dosyalarında yer almaktadır.


DEĞERLENDİRMELER

Bu projede yalnızca CNN tabanlı bir model tasarlanmış ve yüz ifadelerini sınıflandırmak üzere eğitilmiştir. Eğitim süreci boyunca modelin başarımı, eğitim/doğrulama doğruluğu (accuracy), kayıp değerleri (loss) ve en sonunda ROC–AUC analizi ile ölçülmüştür.

•	Eğitim ve Doğrulama Doğrulukları: Eğitim boyunca doğruluk değerleri, epoch sayısı arttıkça belirgin bir şekilde yükselmiştir. Doğrulama kaybı ile eğitim kaybı arasındaki fark takip edilerek, modelin overfitting eğilimi kontrol edilmiştir.

•	Optimizer Denemeleri: Adam, RMSprop ve SGD gibi farklı optimizer’lar ile yapılan denemeler sonucunda en iyi doğrulama doğruluğu Adam optimizasyonu ile elde edilmiştir. Bu sonuç, CNN modelinin veri setine en uygun öğrenme stratejisini bu optimizer ile yakaladığını göstermektedir.

•	ROC–AUC Analizi: Test seti üzerinde yapılan ROC analizi, modelin sınıflar arasındaki ayrımı ne kadar iyi yaptığını göstermiştir. Elde edilen AUC değeri, modelin genel başarı performansını yüzdesel olarak ortaya koymuştur.


EKLER

Proje yalnızca CNN tabanlı bir modelden ibaret olmayıp, aynı zamanda deneysel ek çalışmalar da yapılmıştır. Bu çalışmalar, projenin gerçek dünyaya uygulanabilirliğini artırmak ve araştırma kapsamını genişletmek amacıyla eklenmiştir:

•	GPU Desteği ile Eğitim: Model, GPU ortamında eğitilerek daha kısa sürede daha fazla epoch çalıştırılabilmiştir. Bu sayede daha yüksek doğruluk oranları elde edilmiş, eğitim süreci hızlandırılmıştır.

•	Dağıtım (Deployment) Çalışmaları: Projenin çıktılarının sadece model dosyası olarak kalmaması için bir dağıtım denemesi yapılmıştır. Streamlit tabanlı bir arayüz geliştirilmiş, bu arayüz üzerinden kullanıcıların kendi resimlerini yükleyerek modelden tahmin alabilmesi sağlanmıştır.

•	UI Klasörü: Reponun içerisinde ui/ adında bir klasör oluşturulmuş ve Streamlit uygulamasının temel dosyaları burada tutulmuştur. Burada, app.py dosyası çalıştırılarak kullanıcı arayüzü üzerinden yüz ifadesi tahminleri test edilebilmektedir.

•	Model Checkpoint Kullanımı: Eğitim sürecinde en iyi modelin kaydedilmesi için ModelCheckpoint kullanılmıştır. Bu sayede, dağıtım aşamasında doğrulama setinde en iyi performansı veren model doğrudan yüklenip kullanılabilmiştir.

Bu ek çalışmalar sayesinde, proje yalnızca bir araştırma deneyi olmaktan çıkıp, uçtan uca çalışan bir sistem haline gelmiştir. Eğitim sürecinden elde edilen model, basit bir kullanıcı arayüzü ile gerçek dünyada test edilebilir hale getirilmiştir.


SONUÇ

Bu proje kapsamında, CNN tabanlı bir derin öğrenme modeli geliştirilerek yüz ifadelerinin sınıflandırılması gerçekleştirilmiştir. Eğitim ve test süreçlerinden elde edilen doğruluk oranları, CNN mimarisinin görsel veriler üzerinde güçlü bir performans sunduğunu bir kez daha ortaya koymuştur. Eğitim süresince gözlemlenen kayıp ve doğruluk grafiklerinden, modelin başarılı bir şekilde öğrenme gerçekleştirdiği ve genelleme yeteneği kazandığı görülmüştür.


GELECEK ÇALIŞMALAR

Projenin mevcut haliyle tatmin edici sonuçlar üretmesine rağmen, geliştirilmeye açık birçok yönü bulunmaktadır:

•	Arayüz Geliştirme: Kullanıcı dostu bir web veya mobil uygulama arayüzü (ör. Streamlit, Flutter) eklenerek modelin herkes tarafından kolayca kullanılabilmesi sağlanabilir.

•	Gerçek Zamanlı Uygulama: Webcam veya kamera desteği ile modelin gerçek zamanlı yüz ifadesi tanıma sistemine dönüştürülmesi planlanabilir.

•	Veri Seti Genişletme: Mevcut veri setine ek olarak farklı yaş grupları, kültürler ve çevresel koşulları içeren yeni görseller eklenerek modelin daha genelleştirilebilir hale gelmesi sağlanabilir.

•	Model Geliştirme: Transfer learning tabanlı mimariler (VGG19, ResNet, EfficientNet vb.) ile CNN modeli karşılaştırılarak performans artırılabilir.

•	Gerçek Dünya Kullanımı: Eğitim, sağlık, güvenlik gibi farklı sektörlerde yüz ifadesi tanıma tabanlı uygulamalar için prototip sistemler geliştirilebilir.

Bu proje, sadece teknik bir deney değil, aynı zamanda gelecekteki yapay zekâ tabanlı çözümler için temel bir adım olma potansiyeline sahiptir. Bootcamp sonrasında da bu çalışma geliştirilmeye devam edilecek ve yeni özellikler eklenerek daha kapsamlı bir hale getirilecektir.


Çalışma kaggle linki: https://www.kaggle.com/code/ilknurzgen/akbank-derin-renme-bootcamp-ifade-tahmin-modeli

