
![Logo](https://cohorts.patika.dev/patika-logo.svg)

    ## SQL GIRIS

-   SQL declerative bir dildir.
    
-   **SELECT**  komutu en cok kullanilan sql anahtar kelimeisidir
    
-   SQL'de komutlar  **case sensitive**  degildir!
    
-   SQL, yapılandırılmış bir dildir ve belirli bir söz dizimine sahiptir. SQL kullanarak veritabanlarında sorgular yazabilir, veritabanı şemalarını oluşturabilir, veritabanı nesnelerini yönetebilir ve veritabanı işlemleri gerçekleştirebilirsiniz. SQL, farklı veritabanı yönetim sistemleri arasında genellikle taşınabilirlik sağlayan standart bir dil olarak kabul edilir, yani birçok veritabanı yönetim sistemi SQL'i destekler.
    
-   [W3Schools SQL SELECT](https://www.w3schools.com/sql/sql_select.asp)  'dan sql kodlarina calismalisin!!!
    
-   [PostgreSQL Tutorial SQL SELECT](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-select/)  'burayi da kullan!!
    

WHERE KEYWORD

SELECT * FROM football_player WHERE Country == 'France';

SELECT * FORM film WHERE replacement_cost >= 12.99;

WHERE AND LOGIC OPERATORS

-   **AND**  command'ini kullanarak sorgumuza ekleme yapip daha detayli yapabiliriz.

SELECT first_name, last_name FROM actor
WHERE first_name = 'Penelope' AND last_name = 'Monroe';

**AND, OR, NOT**

-   **AND**  two condition must be true;
-   **OR**  if one of the conditions is true then the statement become true ;
-   **NOT**  it lists the excat opposite of the written statement;

SELECT * FROM film WHERE NOT (rental_rate >= 5.00 OR rental_rate = 2.99);

> Bu projelerin, işlerimizin ilerlemesini ve başarılarımızı gösterme
> açısından önemli olduğunu düşünüyorum. İlgilendiğiniz projelerle
> ilgili daha detaylı bilgilere ihtiyaç duyarsanız, lütfen bana
> bildirin. Size bu konuda yardımcı olmaktan memnuniyet duyarım.



## PATİKA SQL EĞİTİMİ TÜM ÖDEVLER

Bu repo'da Patika SQL eğitiminde yapmış olduğunuz bütün ödevler bulunmaktadır.

**ÖDEV-1**

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

**1-** film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.
**2-** film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.
**3-** film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.
**4-** customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?
**5-** film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

**1.**
```bash
    SELECT title,description FROM film;
```

**2.**
```bash
    SELECT * FROM film
    WHERE length>60 AND length <75;
```
**3.**
```bash
    SELECT * FROM film
    WHERE rental_rate>0.99 AND replacement_cost = 12.99 
    OR replacement_cost = 28.99;
```
**4.**
```bash
    SELECT * FROM customer
    WHERE first_name='Mary';
```
**5.**
```bash
    SELECT * FROM film
    WHERE length <= 49 
    AND rental_rate != 2.99 OR rental_rate != 4.99;
```

  **ÖDEV-2**

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

**1-** film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)

**2-** actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

**3-** film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)


**1.**
```bash
    SELECT * FROM film
    WHERE replacement_cost BETWEEN 12.99 AND 16.99; 
```

**2.**
```bash
    SELECT first_name, last_name FROM actor
    WHERE first_name IN ('Penolope','Nick','Ed');
```
**3.**
```bash
    SELECT * FROM film
    WHERE (rental_rate IN (0.99, 2.99, 4.99)) And (replacement_cost IN(12.99,15.99,28.99));
```


  
