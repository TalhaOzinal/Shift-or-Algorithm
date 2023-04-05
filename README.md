# Shift-or-Algorithm

Shift Or algoritması, verilen bir kalıbın bir dizgede olup olmadığını kontrol etmek için bit düzeyinde teknikler kullanan bir algoritmadır. Kalıp uzunluğu makinenin bellek kelime boyutundan daha küçükse verimlidir.

Algoritma şu şekilde çalışır: Dize ve kalıp girdi olarak alınır. 256 boyutunda (ASCII karakterlerinin toplam sayısı) bir dizi olan pattern_mask oluşturulur ve ~0 ile başlatılır. Daha sonra kalıp gezilir ve pattern_mask [pattern [i]]'nin sağdan i’nci bitini 0’a başlatılır.


Shift Or algoritması, bir veri kümesindeki elemanların toplamı en çok verilen sınır değerini (threshold) aşmayacak şekilde alt kümelerine bölünmesi problemi için kullanılan bir algoritmadır. Algoritma, sıralama ve önbellek (cache) kullanımına dayanır.

Algoritma, şu adımlardan oluşur:

1.Veri kümesini sıralayın.

2.Önbellek (cache) boyutunu belirleyin.

3.Sıralanmış veri kümesinin ilk öğesinden başlayarak, önbellekte (cache) biriktirilen toplamın sınır değerini aşmayacak şekilde alt kümeleri oluşturun.

4.Önbellek (cache) dolduğunda, en küçük toplamı olan alt küme öğesini çıkarın ve yerine bir sonraki öğeyi ekleyin.

5.Tüm alt kümeler için en küçük toplamı olan öğeleri seçin ve birleştirin.

Shift Or algoritması, her bir adımın zaman karmaşıklığına sahiptir.

1.Adım: Veri kümesini sıralama adımı için, veri kümesinin boyutuna bağlı olarak O(n log n) zaman karmaşıklığına sahiptir.

2.Adım: Önbellek (cache) boyutu belirleme adımı, sabit bir zamanda gerçekleşir.

3.Adım: Alt kümeleri oluşturma adımı için, veri kümesinin boyutuna bağlı olarak O(n) zaman karmaşıklığına sahiptir.

4.Adım: Önbellek (cache) dolduğunda en küçük toplamı olan alt küme öğesini çıkarma ve yerine bir sonraki öğeyi ekleme adımı için, O(1) zaman karmaşıklığına sahiptir.

5.Adım: Tüm alt kümeler için en küçük toplamı olan öğeleri seçme ve birleştirme adımı için, veri kümesinin boyutuna bağlı olarak O(n^2) zaman karmaşıklığına sahiptir.

Bu nedenle, Shift Or algoritmasının toplam zaman karmaşıklığı, O(n log n) + O(n) + O(n) + O(1) + O(n^2) = O(n^2) olarak ifade edilir.

En iyi durumda, Shift Or algoritması, verilen sınır değeri için tam olarak doğru alt kümeleri oluşturur ve bu durumda doğru sonuç verir. En kötü durumda, algoritma her öğe için ayrı bir alt küme oluşturur ve toplamda n^2 adet alt küme oluşturarak en kötü performansı gösterir. Ortalama olarak, Shift Or algoritması verilen sınır değerini aşmayacak şekilde yaklaşık olarak optimum alt kümeleri oluşturur.

Shift Or algoritması sınırı, verilen bir veri kümesi ve bir sınır değeri için en fazla kaç alt küme oluşturulabileceğini ifade eder. Bu sınır, veri kümesinin boyutu, sınır değeri ve önbellek (cache) boyutuna bağlıdır.

Öncelikle, veri kümesinin sıralanması, en küçük öğeden en büyüğüne doğru bir sıralama olduğu için, alt kümeler de en küçük öğeden başlayarak birleştirileceklerdir. Bu nedenle, herhangi bir alt küme, bir sonraki öğe eklenmeden önce en azından sınır değerine ulaşmış olacaktır. Ayrıca, önbellek (cache) boyutu, herhangi bir alt küme için en fazla bir öğe saklayabilecek kadar küçük olabilir.

Dolayısıyla, verilen bir veri kümesi ve sınır değeri için en fazla alt küme sayısı, veri kümesindeki öğe sayısı (n) ve önbellek (cache) boyutu (k) kullanılarak hesaplanabilir. Her alt küme en azından sınır değerine ulaşmalıdır, bu nedenle en fazla n/k alt küme oluşturulabilir. Ayrıca, önbellek (cache) boyutu en fazla 1 olabilir, bu durumda her bir öğe ayrı bir alt küme olarak ele alınır ve en fazla n alt küme oluşturulabilir.

Bu nedenle, Shift Or algoritması sınırı, en fazla n/k veya n olabilir, veri kümesinin boyutuna ve önbellek (cache) boyutuna bağlı olarak değişir.
