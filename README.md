# Flight Tracking

### Soru : 

Uçuşların ve pilotların yönetimi için bir sistem tasarlayın.

* Hava yolu şirketleri uçuşları gerçekleştirir. Her hava yolunun bir kimliği vardır.
* Hava yolu şirketi, farklı tipteki uçaklara sahiptir.
* Uçaklar çalışır veya onarım durumunda olabilir.
* Her uçuşun benzersiz kimliği, kalkacağı ve ineceği havaalanı, kalkış ve iniş saatleri vardır.
* Her uçuşun bir pilotu ve yardımcı pilotu vardır ve uçağı kullanırlar.
* Havaalanlarının benzersiz kimlikleri ve isimleri vardır.
* Hava yolu şirketlerinin pilotları vardır ve her pilotun bir deneyim seviyesi mevcuttur.
* Bir uçak tipi, belirli sayıda pilota ihtiyaç duyabilir.
Bu sistemi tasvir eden Class(Sınıf) diyagramını çiziniz.

Uçuş ve Pilot Yönetim Sistemi Sınıf Diyagramı

## Sınıflar :

* HavaYoluSirketi:
    * Kimlik (int)
    * Isim (string)
* UcakTipi:
    * Kimlik (int)
    * Model (string)
    * PilotSayisi (int)
* Ucak:
    * Kimlik (int)
    * Tip (UcakTipi)
    * Durum (string, "Calisir" veya "Onarim")
* Ucus:
    * Kimlik (int)
    * KalkisHavaalani (Havaalani)
    * InisHavaalani (Havaalani)
    * KalkisSaati (datetime)
    * InisSaati (datetime)
    * Pilot (Pilot)
    * YardimciPilot (Pilot)
* Havaalani:
    * Kimlik (int)
    * Isim (string)
* Pilot:
    * Kimlik (int)
    * Isim (string)
    * DeneyimSeviyesi (int)

## İlişkiler :

* HavaYoluSirketi SAHIPTIR Ucak:
    * Bir hava yolu şirketi birden fazla uçağa sahip olabilir.
    * Bir uçak sadece bir hava yolu şirketine ait olabilir.
* UcakTipi KULLANILIR Ucak:
    * Bir uçak tipi birden fazla uçakta kullanılabilir.
    * Bir uçak sadece bir uçak tipine ait olabilir.
* Ucus GERCEKLESIR Ucak:
    * Bir uçuş sadece bir uçak tarafından gerçekleştirilebilir.
    * Bir uçak birden fazla uçuş gerçekleştirebilir.
* Ucus KALKIS/INIS Havaalani:
    * Bir uçuş bir kalkış ve bir iniş havaalanına sahip olmalıdır.
    * Bir havaalanı birden fazla uçuşun kalkış ve iniş noktası olabilir.
* Ucus UCAR Pilot:
    * Bir uçuşun bir pilotu ve bir yardımcı pilotu olmalıdır.
    * Bir pilot birden fazla uçuşta pilot veya yardımcı pilot olabilir.
    * HavaYoluSirketi IStihdam EDER Pilot:
    * Bir hava yolu şirketi birden fazla pilotu istihdam edebilir.
    * Bir pilot sadece bir hava yolu şirketi tarafından istihdam edilebilir.

## Notlar :

* Sınıf diyagramı, sistemin temel unsurlarını ve bunların arasındaki ilişkileri gösterir.
* Her sınıfın, onu tanımlayan bir dizi özelliği ve davranışı vardır.
* İlişkiler, sınıflar arasındaki bağlantıları gösterir ve kardinaliteleri (birden fazla veya tek) gösterir.
* Bu diyagram, uçuş ve pilot yönetim sistemi için temel bir taslaktır. Gerçek sistemde daha fazla sınıf ve ilişki olabilir.

## Örnek : 
```bash
class HavaYoluSirketi:
    def __init__(self, kimlik, isim):
        self.kimlik = kimlik
        self.isim = isim

class UcakTipi:
    def __init__(self, kimlik, model, pilot_sayisi):
        self.kimlik = kimlik
        self.model = model
        self.pilot_sayisi = pilot_sayisi


hava_yolu_sirketi = HavaYoluSirketi(1, "Türk Hava Yolları")
uçak_tipi = UcakTipi(1, "Boeing 737", 2)
uçak = Ucak(1, uçak_tipi, "Calisir")

```

## Diğer:

* UML (Unified Modeling Language) gibi araçlar, sınıf diyagramları oluşturmak için kullanılabilir.
* Sınıf diyagramları, sistemin tasarımı ve belgelenmesi için önemli bir araçtır.
Umarım bu bilgiler uçuş ve pilot yönetim sistemi için bir sınıf diyagramı oluşturmanıza yardımcı olur.
