# Power BI'da Depolama Modları

Günlük işlerimizde hızlı ve doğru kararlar alabilmemiz için veri analizi oldukça önemlidir. Bu noktada, Power BI gibi araçlar da bize büyük kolaylık sağlamaktadır. Power BI, verilerinizi farklı depolama modlarında saklayabilmenizi ve kullanabilmenizi sağlar. Fakat hangi depolama modunu seçmeniz gerektiğine karar vermek de oldukça önemlidir.

![image](https://github.com/aysegulyigitbi/Powerbi/assets/127193220/172738a7-8516-4c1c-b0d6-3c3135065b67)

**Direct Query Modu** verilerinizi orijinal veri kaynağına bağlı tutarak sorguları gerçek zamanlı olarak veri kaynağına gönderir. Bu sayede, verileriniz her zaman güncel ve doğru tutulur. Özellikle büyük veri kümeleriyle çalıştığınızda tercih edilen bir depolama modudur. Ancak, verilerinizi depolama alanında saklamadığınız için, raporlama performansı etkilenebilir.

**Import Modu** ise verilerinizi Power BI'ya aktararak ve depolama alanında saklayarak kullanır. Bu modda, verilerinizi önceden işleyebilir, önemli hesaplamalar yapabilir ve verileri hızlı bir şekilde filtreleyebilirsiniz. Raporlama performansı da Import modunda daha hızlıdır. Ancak, büyük veri kümeleriyle çalıştığınızda, verilerinizi depolama alanında sakladığınız için, depolama maliyeti artabilir.

**Dual Modu** ise DirectQuery ve Import modlarının bir kombinasyonudur. Verilerin bir kısmı Import modunda saklanırken, bir kısmı DirectQuery modunda veri kaynağına bağlıdır. Bu sayede, verilerinizi filtrelemek ve önemli hesaplamalar yapmak için Import modundan yararlanabilirsiniz. Aynı zamanda, verilerinizi DirectQuery modunda da güncel ve doğru tutabilirsiniz. Bu mod, büyük veri kümeleriyle çalışırken depolama maliyetlerini azaltırken, raporlama performansını korur.

**Live Connection Modu** verilerinizi orijinal veri kaynağında bırakarak Power BI Desktop veya Power BI Servisi aracılığıyla sorguları gerçekleştirir. Bu sayede, verileriniz her zaman güncel ve doğru tutulur. Ancak, Live Connection modunda raporlama performansı, DirectQuery veya Import modlarına göre daha yavaş olabilir.

# Hangi Depolama Modu Hangi Senaryoda Kullanılmalıdır?

**Direct Query Modu**

Eğer verileriniz büyük boyutlarda ve sorgularınız kompleks ise, Direct Query modunu kullanabilirsiniz. Böylece verilerin güncel ve doğru kalır.
Direct Query modu, Power BI'nın canlı veri kaynaklarına doğrudan bağlanarak raporlama yapılmasını sağlayan bir depolama modudur. Veriler, her zaman canlı veri kaynaklarından alınır ve Power BI hafızasında saklanmaz.

![image](https://github.com/aysegulyigitbi/Powerbi/assets/127193220/757c547c-3d65-4369-9ed0-05aac0a0a5c1)

**Avantajları:**
•	Veriler her zaman gerçek zamanlı olarak güncel kalır.
•	Büyük veri kümeleri hızlı bir şekilde analiz edilebilir.
•	Verilerin saklanması için ek depolama alanına ihtiyaç duyulmaz.
•	Verilerin işlenmesi ve analiz edilmesi daha hızlıdır.

**Dezavantajları:**
•	Veritabanı üzerindeki yük artabilir.
•	Veritabanı sorguları doğrudan Power BI tarafından çalıştırıldığından, bazı sorguların yavaş çalışması mümkündür.
•	Veritabanına erişim izni olan kişilerin verilere erişimini kontrol etmek zor olabilir.

**Kullanım senaryoları:**
•	Gerçek zamanlı veri güncellemesi gerektiren senaryolar (örneğin, bir web sitesindeki canlı trafiği analiz etmek).
•	Büyük veri kümeleri üzerinde çalışırken depolama alanından tasarruf etmek istediğiniz senaryolar.
•	Veri modelinizi özelleştirmek istediğiniz senaryolar (örneğin, bir veri ambarı oluştururken).

Örnek olarak, bir bankanın veri analizini ele alalım. Banka, tüm müşteri verilerini saklamak istiyor ve bu verilerin mümkün olduğunca güncel kalmasını sağlamak istiyor. Bu durumda, DirectQuery modu kullanmak en uygun seçenek olabilir. Verileri güncel tutmak için, bankanın veritabanındaki tüm müşteri verileri DirectQuery moduyla bağlanabilir. Bu sayede, banka müşterilerinin tüm işlemlerini gerçek zamanlı olarak izleyebilir ve analiz edebilir.

**Import Mode**

Eğer verileriniz düşük maliyetli ve hızlı bir şekilde filtrelemek istiyorsanız Import modunu kullanabilirsiniz.
Import modu, verilerin Power BI Desktop veya Power Query aracılığıyla içe aktarıldığı bir depolama modudur. İçe aktarma işlemi, verilerin Power BI hafızasına yüklenmesi ve burada işlenmesi anlamına gelir.

**Not:** Bir tablonun Depolama modu ayarını Import Mode olarak değiştirme işlemi geri alınamaz. Bu özellik ayarlandıktan sonra Direct Query veya Dual olarak değiştirilemez.

![image](https://github.com/aysegulyigitbi/Powerbi/assets/127193220/f11e9adf-fe0f-4ab7-a32e-ee1aeacddd12)

**Avantajları:**
•	Verilerin hafıza içinde işlenmesi, raporlama ve analiz performansını arttırır.
•	Büyük veri kümeleri kolaylıkla işlenebilir ve hızlı bir şekilde analiz edilebilir.
•	Verilerin özetlenmesi ve ön işlenmesi için ETL (Extract, Transform, Load) işlemleri kullanılabilir.
•	Verilerin hızlıca güncellenmesi ve yüksek veri hacimleri ile çalışırken kesintisiz raporlama sağlanabilir.

**Dezavantajları:**
•	Verilerin Power BI hafızasında depolanması, performansı arttırmasına rağmen depolama alanı sınırlamalarına neden olabilir.
•	Veri kaynaklarındaki değişikliklerin güncellenmesi, manuel olarak yapılması gerekebilir.
•	Birden çok veri kaynağı varsa, bu kaynaklardan alınan verilerin ayrıştırılması zor olabilir.
•	Veri güvenliği, yalnızca Power BI hafızası içinde depolandığından, güvenlik konusunda daha fazla kaygı yaratabilir.

**Kullanım Senaryoları:**
•	Küçük ve orta ölçekli veri kümeleri için kullanılabilir.
•	Verilerin özetlenmesi ve ön işlenmesi için ETL işlemlerinin gerektiği senaryolarda kullanılabilir.
•	Kesintisiz raporlama gerektiren durumlarda kullanılabilir.

**Dual Mode**

![image](https://github.com/aysegulyigitbi/Powerbi/assets/127193220/245ad322-fa39-432e-bef8-c03e830969e8)

**Avantajları:**
Dual mode, verilerin hem Power BI raporunda hem de veri kaynağında saklandığı bir depolama modudur. Bu modun en büyük avantajı, veri kaynağındaki değişikliklerin hızlı bir şekilde raporlara yansıtılabilmesidir. Ayrıca, verilerin büyük olması durumunda, raporların performansını artırabilir.

**Dezavantajları:**
 Bu depolama modunun dezavantajı, büyük veri kümelerinin Power BI raporlarında performans sorunlarına neden olabileceğidir. Ayrıca, bu modun kullanımı için verilerin iki kez saklanması gerekir, bu da depolama alanını artırabilir.
Kullanım senaryoları: 
Bu mod, verilerin gerçek zamanlı olarak güncellenmesi gereken senaryolarda kullanılır. Örneğin, bir şirketin güncel stok bilgilerini veya satış verilerini izlemesi gerektiği bir durumda, dual mode kullanışlı olabilir.

**Live Connection Mode**
Power BI'ın harici olarak (çoğunlukla Azure Analysis Services veya SQL Server Analysis Services) barındırılan bir veri modeline doğrudan bağlandığı senaryoyu temsil eder.

**Avantajları:** 
Bu mod, Power BI raporlarının ve görselleştirmelerinin, verilerin orijinal kaynakta saklandığı bir yerden alınması anlamına gelir. Bu, veri depolama ihtiyacını ortadan kaldırır ve depolama alanı kullanımını azaltır. Ayrıca, büyük veri kümelerinin performansını artırabilir.

**Dezavantajları:** 
Live connection modunun dezavantajı, internet bağlantısının kopması veya veri kaynağındaki değişikliklerin raporlara yansıtılması için manuel bir yenileme gerektirebilir.

**Kullanım senaryoları:** 
Bu mod, verilerin büyük olduğu ve depolama alanı maliyetlerini azaltmak istediğiniz senaryolarda kullanılır. Örneğin, bir şirketin yıllık satış verilerini Power BI raporlarında göstermek istediği bir durumda, live connection modu kullanmak uygun olabilir.

**Örnek senaryo:**
Bir şirket, bir önceki senenin satış verilerini Power BI raporlarında göstermek istiyor. Bu veriler, bir SQL veritabanında saklanmaktadır. Şirket, depolama alanı maliyetlerini azaltmak istediği için live connection modunu kullanmaya karar verir. Böylece, veriler SQL veritabanında saklanır ve Power BI raporları doğrudan bu verileri kullanır. Verilerin herhangi bir değişikliği olduğunda, şirket manuel olarak yenileme yapabilir. Ancak, raporların performansını etkilemeden verilerin güncel kalmalarını sağlayan dual mode da uygun olabilir.

Sonuç olarak, bu yazıda Power BI'da bulunan depolama modlarını, avantajlarını, dezavantajlarını ve kullanım senaryolarını açıkladım. Hangi depolama modunun tercih edileceği, projenin gereksinimlerine ve hedeflerine bağlıdır. Umarım bu yazı, Power BI kullanıcılarına verilerini optimize etmek için farklı seçenekler sunmuştur.
