# Tutorial: ms-tariff-options-master@f5090668355

Bu proje, bir müşterinin aktif sözleşmelerini getiren bir mikroservistir. Bir talep geldiğinde, önce talebin *yeni dijital kanallardan mı* yoksa *eski sistemlerden mi* geldiğini kontrol ederek doğru iş akışını başlatır. Yeni sistemler için, sözleşme verisini bulmak amacıyla önce hızlı önbellek gibi farklı kaynakları akıllıca dener. Ayrıca, başka bir sisteme bağlanarak sözleşmeden erken ayrılma durumunda oluşacak **cayma bedelini** de hesaplayabilir. Son olarak, tüm teknik verileri alıp kullanıcı için *özet* veya *detaylı* olacak şekilde anlaşılır bir yanıta dönüştürür.


**Source Repository:** [None](None)

```mermaid
flowchart TD
    A0["Ana Akış ve Yönlendirme
"]
    A1["Sözleşme Veri Kaynağı Zinciri (Siebel Akışı)
"]
    A2["Yanıt Oluşturucular (Assemblers)
"]
    A3["Cayma Bedeli Hesaplama (CCS Entegrasyonu)
"]
    A4["Eski Sistem Sözleşme Akışı (Legacy/CCB)
"]
    A5["Sözleşme Ailesi Sıralama ve Normalleştirme
"]
    A0 -- "Yeni sistem isteğini yönlen..." --> A1
    A0 -- "Eski sistem isteğini yönlen..." --> A4
    A1 -- "Ham veriyi formatlamaya gön..." --> A2
    A1 -- "Listeyi sıralamak için kull..." --> A5
    A2 -- "Cayma bedeli bilgisini alır" --> A3
    A4 -- "Yanıtı formatlamak için kul..." --> A2
```
