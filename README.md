# cat_motoko

# Kedi Yönetim Sistemi

Bu proje, kedilerin eklenmesi, güncellenmesi, silinmesi ve evlat edinilmesi işlemlerini gerçekleştiren basit bir kedi yönetim sistemini içerir. Proje, Motoko programlama dili kullanılarak geliştirilmiştir ve Trie veri yapısını kullanmaktadır.

# Kullanılan Kütüphaneler
Trie: Temel Trie veri yapısı.
Text: Metin işlemleri için.
Nat32: 32-bit doğal sayılar için.
Bool: Boolean (doğru/yanlış) veri tipi için.
Option: Opsiyonel değerler için.



# Veri Tipleri
CatId: Nat32 tipinde kedi kimlik numarası.
Cat: Kedi bilgilerini içeren kayıt.
name: Kedi adı (Text).
age: Kedi yaşı (Nat32).
breed: Kedi cinsi (Text).
isAdopted: Kedi evlat edinilmiş mi? (Bool).
ResponseCat: Yanıt olarak döndürülecek kedi bilgileri.
name: Kedi adı (Text).
age: Kedi yaşı (Nat32).
breed: Kedi cinsi (Text).
isAdopted: Kedi evlat edinilmiş mi? (Bool).
id: Kedi kimlik numarası (Nat32).
