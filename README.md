
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


  **ÖDEV-3**

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

**1-** country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

**2-** country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

**3-** film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

**4-** film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.


**1.**
```bash
    SELECT * FROM country
    WHERE country LIKE 'A%a';
```

**2.**
```bash
    SELECT * FROM country
    WHERE country LIKE '_____n';
```
**3.**
```bash
    SELECT * FROM film
    WHERE title ~~* '%T%T%T%T%';
```
**4.**
```bash
    SELECT * FROM film
    WHERE title LIKE 'C%' AND length > 90 AND rental_rate = 2.99;
```
**ÖDEV-4**

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

**1-** film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.

**2-** film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?

**3-** film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

**4-** country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

**5-** city tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?


**1.**
```bash
    SELECT DISTINCT replacement_cost 
    FROM film;
```

**2.**
```bash
    SELECT COUNT(replacement_cost) 
    FROM film;
```
**3.**
```bash
    SELECT * FROM film
    WHERE title LIKE 'T%' AND rating = 'G';
```
**4.**
```bash
    SELECT DISTINCT country FROM COUNTRY
    WHERE country LIKE '_____';
```
**5.**
```bash
    SELECT * FROM city
    WHERE city LIKE 'R%r';
```
**ÖDEV-5**

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

**1-** film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

**2-** film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.

**3-** customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.


**1.**
```bash
    SELECT title,length FROM film
    WHERE title LIKE '%n'
    ORDER BY length DESC
    LIMIT 5;
```

**2.**
```bash
    SELECT title,length FROM film
    WHERE title LIKE '%n'
    ORDER BY length ASC
    LIMIT 5 OFFSET 5;
```
**3.**
```bash
    SELECT * FROM customer
    WHERE store_id = 1
    ORDER BY last_name ASC
    LIMIT 4;
```
**ÖDEV-6**

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

**1-** film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?

**2-** film tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?

**3-** film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

**4-** film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?




**1.**
```bash
    SELECT AVG(rental_rate) 
    FROM film; 
```

**2.**
```bash
    SELECT * 
    FROM film
    WHERE title LIKE 'C%'; 

```
**3.**
```bash
    SELECT MAX(length) 
    FROM film
    WHERE rental_rate = 0.99; 
```
**4.**
```bash
    SELECT 
    COUNT(DISTINCT replacement_cost) 
    FROM film 
    WHERE length > 150;
```
**ÖDEV-7**

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

**1-** film tablosunda bulunan filmleri rating değerlerine göre gruplayınız?

**2-** film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız?

**3-** customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?

**4-** city tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız?




**1.**
```bash
    SELECT rating, COUNT(*) 
    FROM film
    GROUP BY rating;
```

**2.**
```bash
    SELECT replacement_cost, COUNT(*) 
    FROM film
    GROUP BY replacement_cost
    HAVING COUNT(*) > 50;

```
**3.**
```bash
    SELECT store_id, COUNT(*) 
    FROM customer
    GROUP BY store_id;
```
**4.**
```bash
    SELECT country_id, COUNT(*) 
    FROM city
    GROUP BY country_id
    ORDER BY COUNT(*) DESC
    LIMIT 1;
```
**ÖDEV-8**

Aşağıdaki sorgu senaryolarını örnek veri tabanı üzerinden gerçekleştiriniz.

**1-** Test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım ?

**2-** Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim?

**3-** Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım?

**4-** Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım?




**1.**
```bash
    CREATE TABLE employee (
	id SERIAL PRIMARY KEY ,
	name VARCHAR(50) NOT NULL,
	birthday DATE,
	email VARCHAR(100) 
    );
```

**2.**
```bash
insert into MOCK_DATA (id, Name, Birthday, Email) values (1, 'Frank Delaprelle', '6/3/1918', 'fdelaprelle0@kickstarter.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (2, 'Timmie Tompsett', '6/13/1988', 'ttompsett1@t.co');
insert into MOCK_DATA (id, Name, Birthday, Email) values (3, 'Adele Wilmut', '3/9/1935', 'awilmut2@chronoengine.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (4, 'Taylor Winman', '3/16/1913', 'twinman3@tinyurl.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (5, 'Idaline Dashwood', '4/28/1920', 'idashwood4@ebay.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (6, 'Melodee Chater', '2/5/1981', 'mchater5@clickbank.net');
insert into MOCK_DATA (id, Name, Birthday, Email) values (7, 'Grier Juschke', '5/9/1955', 'gjuschke6@tripadvisor.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (8, 'Aldon Bolsover', '8/6/2001', 'abolsover7@patch.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (9, 'Tammara Kinnoch', '12/25/1981', 'tkinnoch8@bbc.co.uk');
insert into MOCK_DATA (id, Name, Birthday, Email) values (10, 'Lewie Jonke', '2/3/2020', 'ljonke9@networksolutions.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (11, 'Deeann Hatherleigh', null, 'dhatherleigha@nationalgeographic.com')
insert into MOCK_DATA (id, Name, Birthday, Email) values (12, 'Abie Elven', '7/15/2007', 'aelvenb@zdnet.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (13, 'Daffie Dundin', '2/18/1985', 'ddundinc@skype.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (14, 'Una Andrasch', null, 'uandraschd@ustream.tv');
insert into MOCK_DATA (id, Name, Birthday, Email) values (15, 'Caro Brimming', null, 'cbrimminge@fc2.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (16, 'Nealy Adao', null, 'nadaof@nifty.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (17, 'Judi Meekins', '4/2/1913', 'jmeekinsg@admin.ch');
insert into MOCK_DATA (id, Name, Birthday, Email) values (18, 'Orelie Goodison', '6/22/2007', 'ogoodisonh@i2i.jp');
insert into MOCK_DATA (id, Name, Birthday, Email) values (19, 'Guenna Devote', '4/6/2006', 'gdevotei@topsy.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (20, 'Derby La Wille', '1/8/1965', 'dlaj@pen.io');
insert into MOCK_DATA (id, Name, Birthday, Email) values (21, 'Dolley Grafhom', '8/31/1932', 'dgrafhomk@mlb.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (22, 'Osborne Reihill', '9/29/1948', 'oreihilll@artisteer.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (23, 'Lemmie Durbridge', null, 'ldurbridgem@usda.gov');
insert into MOCK_DATA (id, Name, Birthday, Email) values (24, 'Josselyn Grimm', '1/15/1991', 'jgrimmn@wikia.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (25, 'Rollo Sheard', '11/20/1918', 'rsheardo@dagondesign.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (26, 'Milton Oen', '3/18/1948', 'moenp@mozilla.org');
insert into MOCK_DATA (id, Name, Birthday, Email) values (27, 'Eddy Dunthorn', null, 'edunthornq@homestead.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (28, 'Latia Liversley', null, 'lliversleyr@nbcnews.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (29, 'Carmelle Nesbeth', '6/24/2021', 'cnesbeths@oracle.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (30, 'Glen Foote', '12/9/2018', 'gfootet@tiny.cc');
insert into MOCK_DATA (id, Name, Birthday, Email) values (31, 'Hillary Ocheltree', '3/26/1981', 'hocheltreeu@usda.gov');
insert into MOCK_DATA (id, Name, Birthday, Email) values (32, 'Saloma Cody', '9/29/1931', 'scodyv@naver.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (33, 'Katlin Sivil', '12/14/2021', 'ksivilw@fema.gov');
insert into MOCK_DATA (id, Name, Birthday, Email) values (34, 'Arlana Spavins', '4/28/2012', 'aspavinsx@histats.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (35, 'Caresa Aldin', '10/19/1984', 'caldiny@flickr.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (36, 'Sharl Rattray', '4/26/1983', 'srattrayz@ask.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (37, 'Jocelyne Kobpac', null, 'jkobpac10@npr.org');
insert into MOCK_DATA (id, Name, Birthday, Email) values (38, 'Gar Jacqueminot', null, 'gjacqueminot11@ihg.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (39, 'Dorothea Burnel', '4/15/2003', 'dburnel12@ning.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (40, 'Janie Ioannou', null, 'jioannou13@slashdot.org');
insert into MOCK_DATA (id, Name, Birthday, Email) values (41, 'Vidovic Esch', '2/8/1963', 'vesch14@gizmodo.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (42, 'Flossy Vinton', '3/9/2020', 'fvinton15@tiny.cc');
insert into MOCK_DATA (id, Name, Birthday, Email) values (43, 'Wandie Ties', '3/10/1936', 'wties16@ed.gov');
insert into MOCK_DATA (id, Name, Birthday, Email) values (44, 'Herminia Cabbell', '4/18/1917', 'hcabbell17@pen.io');
insert into MOCK_DATA (id, Name, Birthday, Email) values (45, 'Alika Leaburn', '7/16/1951', 'aleaburn18@usatoday.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (46, 'Gertrud Cottie', '1/9/1936', 'gcottie19@shareasale.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (47, 'Jerrome Ioan', '1/19/1910', 'jioan1a@sun.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (48, 'Delano De Lascy', '4/8/1916', 'dde1b@icq.com');
insert into MOCK_DATA (id, Name, Birthday, Email) values (49, 'Patin Dimbylow', '3/3/2019', 'pdimbylow1c@dmoz.org');
insert into MOCK_DATA (id, Name, Birthday, Email) values (50, 'Glynda Schruurs', '5/27/1907', 'gschruurs1d@elpais.com');

```
**3.**
```bash
// İsim (name) sütununu güncellemek:

    UPDATE employee
    SET name = 'John Doe'
    WHERE name = 'Coob';


// Doğum günü (birthday) sütununu güncellemek:

    UPDATE employee
    SET birthday = '1990-06-15'
    WHERE email = 'yserckd@home.pl';


// E-posta (email) sütununu güncellemek:

    UPDATE employee
    SET email = 'johndoe@example.com'
    WHERE birthday = '1950/04/10';


// İsim ve doğum günü sütunlarını güncellemek:

    UPDATE employee
    SET name = 'Jane Smith',
    birthday = '1985-03-20'
    WHERE id = 4;


// Tüm sütunları güncellemek:

    UPDATE employee
    SET name = 'Robert Johnson',
    birthday = '1978-12-10',
    email = 'robertjohnson@example.com'
    WHERE id = 5; 
```
**4.**
```bash
    DELETE FROM employee
    WHERE id = 44;

    DELETE FROM employee
    WHERE name ='Constantin';

    DELETE FROM employee
    WHERE name = 'Jane Smith' AND birthday = '1985-03-20';

    DELETE FROM employee
    WHERE email = 'umallinsonn@hp.com';

    DELETE FROM employee
    WHERE id >5
    RETURNING *;
```
**ÖDEV-9**

Aşağıdaki sorgu senaryolarını örnek veri tabanı üzerinden gerçekleştiriniz.

**1-** city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız ?

**2-** customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız?

**3-** customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız?




**1.**
```bash
    SELECT city,country 
    FROM city
    INNER JOIN country ON city.country_id = country.country_id;
```

**2.**
```bash
    SELECT payment.payment_id,customer.first_name,customer.    last_name 
    FROM customer
    --INNER JOIN payment ON payment.payment_id = customer.customer_id;
    INNER JOIN payment ON customer.customer_id = payment.payment_id;
```
**3.**
```bash
    SELECT rental.rental_id,customer.first_name,customer.last_name 
    FROM customer
    INNER JOIN rental ON rental.rental_id = customer.customer_id;
```

**ÖDEV-10**

Aşağıdaki sorgu senaryolarını örnek veri tabanı üzerinden gerçekleştiriniz.

**1-** city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız ?

**2-** customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız ?

**3-** customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız ?




**1.**
```bash
    SELECT city,country
    FROM CITY
    LEFT JOIN country ON city.country_id = country.country_id;
```

**2.**
```bash
    SELECT payment.payment_id,customer.first_name, customer.last_name
    FROM customer
    --LEFT JOIN payment ON customer.customer_id = payment.payment_id;
    LEFT JOIN payment ON payment.payment_id = customer.customer_id;
```
**3.**
```bash
   --SELECT rental.rental_id, customer.first_name, customer.last_name
    SELECT *
    FROM customer
    FULL JOIN rental ON rental.rental_id = customer.customer_id;
```

**ÖDEV-11**

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

**1-** actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım. ?

**2-** actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım. ?

**3-** actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım. ?

**4-** İlk 3 sorguyu tekrar eden veriler için de yapalım ?




**1.**
```bash
    SELECT first_name FROM actor
    UNION
    SELECT first_name FROM customer;
```

**2.**
```bash
    SELECT first_name FROM actor
    INTERSECT
    SELECT first_name FROM customer;
```
**3.**
```bash
    SELECT first_name FROM actor
    EXCEPT
    SELECT first_name FROM customer;
```
**4.**
```bash
    SELECT first_name FROM actor
    UNION ALL
    SELECT first_name FROM customer;


    SELECT first_name FROM actor
    INTERSECT ALL
    SELECT first_name FROM customer;


    SELECT first_name FROM actor 
    EXCEPT ALL
    SELECT first_name FROM customer;
```
