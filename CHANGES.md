# Hydra için değişiklik günlüğü
-------------------

## Sürüm 9.7-dev
* Elboulangero tarafından xhydra için GTK3 desteği
* mongo v2 desteği (devjunix'e teşekkürler)

Sürüm 9.6
* freerdp v2 -> v3
* derleme düzeltmeleri (örn. gcc-15)
* pop3 yeteneği düzeltmesi
* mysql kütüphanesi yükseltmesi
* http-form düzeltmeleri
* postgres özel port desteği
* smb daha iyi süresi dolmuş destek
* ssh eski şifreleme desteği
* http 403 desteği
! Tüm çekme istekleri için teşekkürler!

## Sürüm 9.5
* birçok modül -W'yi desteklemiyordu (bir kütüphane kullananların hepsi)
  Bağlantı). Hepsi (ya da çoğu?) artık düzelmiş olmalı.
* http-formu:
  - http-form için yardım yanlıştı. koşul değişkeni her zaman olmalıdır
    *son* parametre, üçüncü değil
  - Proxy desteği düzgün çalışmıyordu
* smb2: doğru tahmin girişimleriyle sonuçlanan güncellenmiş libsmb2 için düzeltme
  tespit edilmiyor
* smtp: sunucu kimlik doğrulamasına izin vermiyorsa erken sonlandır
* rdp: Bir kullanıcının devre dışı bırakıldığını vb. belirten daha fazla dönüş kodunu algılar.


## Sürüm 9.4
* pcre/pcre3 Debian'dan kaldırılacağı için pcre/pcre3'ten pcre2'ye geçildi
* Garip RTSP sunucuları için küçük bir düzeltme
* Hydra'ya şunu söylemek için http-post-form modülüne isteğe bağlı "2=" parametresi eklendi
  "302" HTTP dönüş kodu başarı anlamına gelir
* Daha iyi uyumluluk için wait3 yerine waitpid kullanıldı


## Sürüm 9.3
* Xcode derlemesini destekler
* yeni modül: ultimaiiii tarafından geliştirilen cobaltstrike, teşekkürler!
* SSH'nin -M veya ip/range'i desteklemesi için düzeltme
* rdp'nin boş parolaları algılaması için düzeltme
* http-form'un boş başlıkları göndermemesi için düzeltme
* Proxy ile kullanıldığında varsayılan olmayan portlarda http için düzeltme
* vnc/cisco/... protokolleri için yalnızca parolayı kontrol eden, ana bilgisayarı atlayan protokoller
  şifre bulunduktan sonra
* -M'de IPv6 adreslerini desteklemek için düzeltme
* -C dosyalarındaki tüm girdileri test etmek için düzeltme, ilk bulunan girdiden sonra çıkılmaması
* Kaybolan hedeflerin daha hızlı sonlandırılması
* "make uninstall" eklendi


## Sürüm 9.2
* http-post-form isteğe bağlı parametreleri için düzeltme
* xhydra için de gcc 10 desteğini etkinleştirin :)
* msys desteği
* verimsizlik nedeniyle yağmur modu (-r) kaldırıldı
* Host için IPv6 desteği: http tabanlı modüller için başlık


## Sürüm 9.1
* rdb: libfreerdp3 desteği (animetauren'e teşekkürler)
* yeni modül: smb3'ü de destekleyen smb2 (libsmbclient-dev'i kullanır) (modül için Karim Kanso'ya teşekkürler!)
* oracle: başarı koşulu eklendi (kazkansouh'a teşekkürler), Cygwin'de derlendi (maaaaz'a teşekkürler)
* rtsp: MD5 yetkilendirmesindeki çökme düzeltildi
* svn: geçmiş ve yeni API'leri destekleyecek şekilde güncellendi
* http: artık F=/S= dize eşleştirme koşullarını destekliyor (poucz@github'a teşekkürler)
* http-proxy: arabellek düzeltmesi, 404 başarı durumu (kazkansouh'a teşekkürler)
* mysql: mysql veritabanının varsayılan olarak kullanılmaması için değiştirildi. Kullanıcının bu veritabanına erişimi yoksa yetkilendirme başarısız olur...
* sasl: tampon düzeltmesi (TenGbps'ye teşekkürler)
* https modülleri için yardım düzeltildi (Jab2870'e teşekkürler)
* Tekrarlama girişimlerini devre dışı bırakmak için -K komut satırı anahtarı eklendi (toplu tarama için iyi)
* Hydra yardım çıktısında -m seçeneğinin olması unutuldu
* gcc-10 desteği ve Jeroen Roovers tarafından yapılan çeşitli temizlikler için teşekkürler!
* .clang-format eklendi ve tüm kod biçimlendirildi


## Sürüm 9.0
* rdp: FreeRDP kütüphanesini kullanacak şekilde yenilenen rdp modülü (yama için loianhtuan@github'a teşekkürler!)
* Memcached modülü eklendi
* Mongodb modülü eklendi
* http: http modülü artık http kimlik doğrulama türünü seçmek için a= seçeneğini destekliyor
* JSON çıktısı artık varsa dosyayı kesmiyor.
* Svn modülü bellek sızıntıları düzeltildi
* Sabit rtsp modülü potansiyel arabellek taşması
* http modülü DIGEST-MD5 modu düzeltildi




## Sürüm 8.9.1
* rdp hata mesajı için açıklama
* CIDR gösterimi (hydra -l test -p test 192.168.0.0/24 ftp) algılanmadı, düzeltildi


## Sürüm 8.8
* Yeni web sayfası: https://github.com/vanhauser-thc/thc-hydra
* Bilinen sorunlarla birlikte PROBLEMS dosyası eklendi
* rdp: Mevcut protokolü desteklemediği için modülü devre dışı bıraktım. Eklemek isterseniz benimle iletişime geçin.
* ldap: potansiyel bir boş işaretçi üzerindeki aptal strlen düzeltildi
* http-get/http-post:
   - artık http-form ile aynı H=/h= parametrelerini destekliyor (yama için mathewmarcus@github'a teşekkürler)
   - 403/404 hataları artık her zaman başarısız girişimler olarak kaydediliyor
* mysql modülü: varsayılan olmayan bir port çalışmıyordu, düzeltildi
* ssh modülüne -w zaman aşımı desteği eklendi
* http-form modülündeki çeşitli bellek sızıntıları düzeltildi
* Başarılı olduğunda hydra dönüş kodu 0 olacak şekilde düzeltildi
* Debian bakımcılarından yazım hatalarını düzelten yama eklendi
* x64 sistemlerindeki garip çökme düzeltildi
* crondaemon tarafından birçok uyarı düzeltmesi yapıldı


## Sürüm 8.6
* catatonic prime tarafından radmin2 modülü eklendi - harika çalışma!
* smb modülü artık SMBv1'in sunucu tarafından desteklenip desteklenmediğini ve imzalama gerekip gerekmediğini kontrol ediyor
* http-form modülü artık 6000 bayta kadar URL'leri destekliyor (yama için petrock6@github'a teşekkürler)
* 00000000:lib(0):func(0):reason(0) hatasıyla başarısız olan SSL bağlantıları için düzeltme (bildirim için gaia@github'a teşekkürler)
* Yeni komut satırı seçeneği eklendi:
   -c TIME: oturum açma girişimleri arasındaki saniyeler (tüm iş parçacıkları için, bu nedenle -t 1 önerilir)
* -R'den sonra (geri yükleme dosyasını yüklemek için) eklenen seçenekler artık geçerli (ve daha önce izin verilmiyordu)
* Kodu daha kolay okunabilir hale getirmek için Diadlo@github'ın birkaç yamasını birleştirdim. Bunun için teşekkürler!
* Yardım çıktısını bireysel modüle taşıyan Diadlo@github tarafından yapılan bir yama birleştirildi


## Sürüm 8.5
* Yeni komut satırı seçeneği:
   -b : -o çıktı dosyası için biçimlendirme seçeneği (şimdilik sadece json, diğerlerini destekleyen yamalar için mutluyum :) ) - yama için veggiespam'e teşekkürler
* ./configure artık mevcutsa CC ortam değişkenini dikkate alıyor
* Bazı x64 platformlarında geri yükleme dosyası çökmesi sorunu giderildi (sonunda! lukas227'ye teşekkürler!)
* Geri yükleme dosyasının biçimi, platformlar arası kopyaları algılayacak şekilde değiştirildi
* NCP modülündeki bir hata düzeltildi
* rindex() yerine strrchr()'ı tercih edin
* diadlo tarafından yeniden düzenleme yaması eklendi
* Eksik komut satırı seçenekleriyle güncellenmiş man sayfası


## Sürüm 8.4
! RDP modülünün bazen güvenilir bir şekilde çalışmadığı, büyük olasılıkla yeni Windows sürümlerinde çalışmadığı yönünde raporlar geldi. Lütfen test edin, raporlayın ve mümkünse bir düzeltme gönderin
* Proxy desteği yeniden uygulandı:
  - HYDRA_PROXY[_HTTP] ortamı, 64'e kadar giriş içeren bir metin dosyası olabilir
  - HYDRA_PROXY_AUTH kullanımdan kaldırıldı, HTTP_PROXY[_HTTP]'de oturum açma/şifreyi ayarlayın
* Yeni protokol: adam6500 - bu üzerinde çalışılan bir konu, lütfen test edin ve raporlayın
* Yeni protokol: rpcap - Petar Kaleychev'e teşekkürler <petar.kaleychev@gmail.com>
* Yeni komut satırı seçenekleri:
   -y : -x 1aA yorumlamasını devre dışı bırakır, yama için crondaemon'a teşekkürler
   -I : Mevcut bir hydra.restore dosyasını yoksay (10 saniye bekleme)
* hydra-svn: artık geçerli libsvn sürümüyle çalışıyor
* hydra-ssh: parola doğrulama desteği için ilk kontrol artık sağlanan oturum açma bilgilerini kullanıyor
* dpl4hydra'nın web üzerinden tekrar güncellenebilmesi için düzeltme yapıldı
* -U herhangi bir servis olmadan kullanıldığında oluşan çökme düzeltildi (raporlama için thecarterb'e teşekkürler)
* Varsayılan parola listeleri güncellendi
* vnc, xmpp, telnet, imap, nntp ve pcanywhere protokolleri 8.2'deki bir yama nedeniyle yanlışlıkla uzun uyku komutları aldı, düzeltildi
* Bilgisiz kullanıcılar için özel hata mesajı eklendi :)


## Sürüm 8.3
* Yakında çıkacak olan OpenSSL 1.1 desteği eklendi. Test edilmesi gerekiyor.
* Hydra yeniden yapma hatası düzeltildi (sorun #113)
* Yeni Hydra özellikleri ve seçenekleri için xhydra güncellendi
* Komut satırında daha fazla hata kontrolü
* Gereksiz soketlerin kapatıldığından emin olundu

## Sürüm 8.2
* RTSP modülü eklendi, jjavi89'a sağladığı için teşekkürler!
* Hydra'nın bağlanmayı durdurmasını düzelten ssh için yama eklendi, yama için ShantonRU'ya teşekkürler
* TLS'yi desteklemeyen SSL sunucularını desteklemek için Hydra'ya yeni -O seçeneği eklendi
* Kullanıcı adı kullanmayan modülleri desteklemek için Petar Kaleychev tarafından xhydra gtk yaması eklendi
* Petar Kaleychev tarafından ilk servis kontrolü için redis'e yama eklendi - çok teşekkürler!
* Hydra-http'de http-post için destek eklendi (içerik uzunluğu 0)
* http-*://server/url komut satırı işlemesindeki önemli hata düzeltildi
* SSL SNI desteği eklendi
* HTTP Form yönlendirmesindeki hata düzeltildi - bildiren herkese ve özellikle hata ayıklama için bir test sayfası oluşturan Hayden Young'a teşekkürler
* SVN için ./configure'da daha iyi kütüphane bulma + Darwin Homebrew desteği (ve daha da geliştirildi)
* Yalnızca BSD/OSX sistemlerinde oluşan http-form modülü çökmesi düzeltildi. Bildirim için zdk'ya teşekkürler!
* SSL bağlantısının TLSv1.2 vb.'yi desteklemesi için düzeltme yapıldı.
* Farklı RSA anahtar uzunlukları için destek, yama için fann95'e teşekkürler
* Cisco-enable modülünün yalnızca parola oturum açma moduyla çalışmadığı bir hata düzeltildi
* http-form'daki bellek yetersizliği hatası düzeltildi
* Sabit imap PLAIN yöntemi
* Çok fazla parola (4 milyardan fazla) üretilmesi durumunda kurtarmayı sağlayan -x seçeneği düzeltildi
* HYDRA_PROXY_CONNECT ortamı algılanırsa uyarı eklendi, bu güncel olmayan bir ayardır
* Linux dağıtım kullanımı için yapılandırmaya --fhs anahtarı eklendi
* ... yamalarınız mı?


## Sürüm 8.1
* İş ortağım David Maciejak başka bir işe ve ülkeye taşındı ve artık Hydra'ya yardımcı olamıyor - ne yazık ki! Her şeyin gönlünüzce olmasını dilerim!
* Ander Juaristi'nin http-form-* için h/H başlık seçeneklerini ekleyen yaması eklendi, harika çalışma, teşekkürler!
* -M seçeneği düzeltildi, artık birçok hedefle çalışıyor :-)
* -M seçeneği artık portları destekliyor, "host:port" arasına iki nokta üst üste ekleyin veya IPv6 ise "[ipv6ipaddress]:port"
* Bulunan oturum açma:şifre kombinasyonları artık belirtilen adla (ana bilgisayar adı veya IP) yazdırılıyor, her zaman IP ile değil
* İlk Oturum Açma/Parola kullanıldığında cisco-enable için düzeltme yapıldı (bildirim için joswr1te'ye teşekkürler)
* Daha iyi MySQL derlemesi ve Android yamaları ve Makefile için tux-mind tarafından yama eklendi. Teşekkürler!
* Petar Kaleychev'in -h, -U, -f, -F, -q ve -er seçeneklerini desteklemek için xhydra gtk yamaları eklendi, teşekkürler!
* Sunucu hatalarını ve kimlik doğrulama hatalarını daha iyi tespit etmek için teamspeak'e yama eklendi (Petar Kaleychev'e teşekkürler)
* Cisco modülündeki bir çökme düzeltildi (raporlama için Anatoly Mamaev'e teşekkürler)
* S= dize eşleşmesinin çalışmadığı yönlendirme sayfaları için HTTP form modülü için küçük bir düzeltme (raporlama için mkosmach'a teşekkürler)
* Mevcut Cygwin'deki yıkıcı paketleri algılamak için yapılandırma güncellendi
* RDP modülü port seçeneğini destekleyecek şekilde düzeltildi (and.enshin(at)gmail.com'a teşekkürler)


## Sürüm 8.0
! Geliştirme herkese açık bir github deposuna taşındı: https://github.com/vanhauser-thc/thc-hydra
* Redis için modül eklendi (Alejandro Ramos tarafından gönderildi, teşekkürler!)
* SMB modülü için Unicode desteği ekleyen yama eklendi (Max Kosmach'a teşekkürler)
* SSH için ilk etkileşimli parola kimlik doğrulama testi eklendi (Joshua Houghton'a teşekkürler)
* GUI'ye bruteforce üreteci ekleyen xhydra için yama eklendi (Petar Kaleychev'e teşekkürler)
* Komut satırındaki hedef artık bir CIDR tanımı olabilir, örneğin 192.168.0.0/24
* -M <hedefdosya> ile artık her giriş için bir port belirtebilirsiniz (satır başına "hedef:port" kullanın)
* Hydra'nın QNX / Blackberry 10'da temiz bir şekilde derlendiği doğrulandı :-)
* -x seçeneği için hata düzeltmeleri:
  - Bağlantı hataları oluştuğunda şifre denemeleri kaybedildi (bildirim için Vineet Kumar'a teşekkürler)
  - -e seçeneğiyle birlikte kullanıldığında oluşan çökme düzeltildi
* Hydra'nın libssh olmadan derlenemediği hatası düzeltildi (v7.6'da tanıtıldı)
* Birçok hedefe paralel olarak saldırı yapılması durumunda çeşitli hata düzeltmeleri
* Cygwin'in Postgresql'i tekrar çalışıyor, dolayısıyla algılama yapılandırması yeniden etkinleştirildi
* Gcc derleme güvenlik seçenekleri eklendi (yapılandırma betiği tarafından desteklendiği tespit edilirse)
* Güvenli derleme seçeneklerinde iyileştirmeler
* Kod cppcheck ile kontrol edildi ve bazı küçük sorunlar düzeltildi.
* Kod Coverity ile kontrol edildi. Küçük ve orta ölçekli birçok sorun düzeltildi.


## Sürüm 7.6
* Shivang Desai <shiv> tarafından yazılan bir betiğe dayanan Hydra için bir sihirbaz betiği eklendi
* Siemens S7-300 için modül eklendi (Alexander Timorin ve Sergey Gordeychik tarafından gönderildi, teşekkürler!)
* HTTP HEAD/GET: MD5 özeti yetkilendirmesi çalışmıyordu, düzeltildi (Paul Kenyon'a teşekkürler)
* SMTP Enum: HELO artık her zaman gönderiliyor, 500 hata tespiti daha iyi
   - Bir port sağlandığında IPv6 adres ayrıştırmasında oluşan bir hata düzeltildi
   - pop3, imap ve smtp protokol kullanımı için bilgi mesajı eklendi
* hydra GTK: bazı hizmetler atlandı, eklendi
* dpl4hydra.sh:
   - Siemens S7-300 ortak parolaları varsayılan parola listesine eklendi
   - listede daha geniş arama
* Tüm C dosyalarında kod girintisi yapıldı :-)
* .../etc dizininin orada olduğundan emin olmak için Makefile yaması (vonnyfly'a teşekkürler)


Sürüm 7.5
* Lisans GPLv3'ten AGPLv3'e taşındı (LICENSE dosyasına bakın)
* Asterisk Çağrı Yöneticisi için modül eklendi
* Bazı işlevlerin kullanılamadığı Android desteği eklendi
* hydra ana:
   -h olmadan çalıştırıldığında ekran çıktısı küçültüldü, -h ile tam ekran
   - IPv6 ve port ayrıştırma için service://[ipv6address]:port/OPTIONS ile düzeltme
   - -o çıkışı düzeltildi (www417'ye teşekkürler)
   - HYDRA_PROXY tanımlanmışsa ancak modül bunu kullanmıyorsa uyarı
   - büyük giriş dosyaları ve uzun girdilerle ilgili bir sorun düzeltildi
* hydra kütüphanesi:
   - SSL bağlantıları artık SSLv3'e sabitlendi, aksi takdirde bazı SSL sunucuları başarısız oluyor, bu size sorun çıkarırsa bildirin
   - eski OPENSSL kütüphanelerine yönelik destek kaldırıldı
* HTTP Form modülü:
   - Özel karakterler mevcutsa artık oturum açma ve parola değerleri kodlanıyor
   - ^USER^ ve ^PASS^ artık H= başlık değerlerinde de destekleniyor
   - Seçenek dizinizde iki nokta üst üsteyi bir değer olarak kullanırsanız, artık onu \ ile kaçırabilirsiniz: - ancak \'yi \\ ile kodlamayın
* Mysql modülü: protokol 10 artık destekleniyor
* SMTP, POP3, IMAP modülleri: Varsayılan olarak TLS devre dışı bırakıldı. TLS artık devre dışı bırakılmalıdır.
  Gerekirse "TLS" seçeneği olarak tanımlanabilir. Bu, performansı artırır.
* Cisco modülü: Küçük bir hata düzeltildi (Vitaly McLain'e teşekkürler)
* Postgres modülü: Cygwin'deki kütüphaneler şu anda hatalı, bu nedenle modül
  Cygwin'de devre dışı bırakıldı

Sürüm 7.4.3 7.4'te tanıtılan hatalar için düzeltme sürümleri
* Libssh'i yüklememiş kişiler için hızlı düzeltme (aksi takdirde derleme yapılmayacaktır)
* Yeni bir özellik nedeniyle çalışmayan http-get/http-head ve irc modülü için hızlı düzeltme.
* Bir servis kullanılamaz hale geldiğinde sonsuz döngüyü kıran ssh modülü için düzeltme (bildirim için shark0der(at)gmail(dot)com'a teşekkürler)


Sürüm 7.4
* Yeni modül: SSHKEY - ssh özel anahtarlarını test etmek için (deadbyte(at)toucan-system(dot)com'a teşekkürler!)
* RDP modülüne win8 ve win2012 sunucusu desteği eklendi
* -M kullanılırsa daha iyi hedef dağılımı
* Renkli çıktı eklendi (libcurses'a ihtiyaç duyar)
* Güncel Cygwin ve OS X için daha iyi kütüphane algılama
* -W seçeneği düzeltildi
* -u, -l, -L veya -C olmadan -e seçeneği kullanıldığında oluşan bir hata düzeltildi, oturum açma işlemlerinin yalnızca yarısı test edildi
* Sunucudan yanıt alınamadığında HTTP Form modülünde oluşan yanlış pozitif hatası düzeltildi
* Geçersiz saat oturum açma ve LM yetkilendirmesi devre dışı bırakıldığında SMB modülü dönüş kodu düzeltildi
* xhydra'dan http-{get|post-form} düzeltildi
* OS/390 ana bilgisayar 64 bit desteği eklendi (dan(at)danny(dot)cz'ye teşekkürler)
* -L, -P, -C ve -M için giriş dosyalarına sınırlamalar eklendi - insanlar sağlıksız büyük dosyalar kullanıyordu! ;-)
* Kullanıma hata ayıklama modu seçeneği eklendi (Anold Black'e teşekkürler)


Sürüm 7.3
* Hydra ana:
    - Bir çift bulunursa tüm hedeflerden çıkmak için -F anahtarı eklendi (-M için)
    - Hydra'nın başarılı bir bildirimden sonra sonlanmasına neden olan bir hata düzeltildi
      bir hesap herhangi bir şifreyi kabul ettiğinde oturum açın
    - Çok büyük kelime listelerindeki bir hata düzeltildi (raporladığı için sheepdestroyer'a teşekkürler!)
    - Modül yardımı geliştirildi
* yapılandırma betiği:
    - Oracle kütüphanesinin dahil edilmesiyle ilgili düzeltme eklendi, Brandon Archer'a teşekkürler!
    - İkili soymayı önlemek için --nostrip seçeneği eklendi (Fedora tarafından talep edildi)
      (bakımcı)
* Debian bakımcıları tarafından kendi sürümlerini desteklemek için bir Makefile yaması eklendi
  İstendiği gibi wheezy yapısı için SecurityHardeningBuildFlags
* dpl4hydra: kurulum dizini desteği eklendi
* Tüm kod: mesaj temizlemeleri
* SNMP modülü
    - başlangıçta yazma ve v2 zaten destekleniyordu ancak bu mevcut değildi
      Modül yardım çıktısı. Eklendi :-)
    - SNMPv3 MD5/SHA1 kimlik doğrulama desteği eklendi, ancak hala beta aşamasında
* HTTP modülü:
    - HTTP NTLM kimlik doğrulama oturumu düzeltildi
    - HTTP özeti md5-sess algoritması için hata düzeltmesi uygulandı
    - varsayılan yolu / olarak ayarla
* HTTP Form modülü:
    - varsayılan yolu / olarak ayarla
    - HTTP/1.0 yönlendirmelerini destekler
    - pcre kullanılmadığında başarısız olan durum denetimi düzeltildi
* IMAP modülü: sabit kimlik doğrulama tespiti
* POP3 modülü: Güncellenmiş yetkilendirme ve yetenek tespiti
* Oracle modülü: kötü kullanım düzeltildi
* Oracle dinleyici modülü: karma boyutu işleme düzeltildi
* Telnet/Cisco/Cisco-etkinleştirme modülleri: "ENTER tuşuna basın" komutlarını destekler
* FTP modülü:
    - 530 mesajın yanlış işlendiği bir hata düzeltildi
    - FTPS kullanımına ilişkin açıklama
* Mysql modülü: Redhat/Fedora'dan derleme sorunlarını düzelten yama eklendi
* Cygwin için IDN ve PCRE desteği eklendi


Sürüm 7.2
* Http modüllerinin kimlik doğrulama mekanizmasının tespitini hızlandırın
* Boş oturum açma/parolalar kullanıldığında -C colonfile modu düzeltildi (teşekkürler
  (raporlama için will(at)configitnow(dot)com)
* -f anahtarı postgres, afp, socks5, firebird ve ncp için çalışmıyordu,
  Richard Whitcroft'a bildirimi için teşekkürler!
* http-proxy/http-proxy-url modülünde NTLM kimlik doğrulaması düzeltildi
* http-form modülünde yönlendirilirken sabit URL, gash(at)chaostreff(dot)at sayesinde
* whistle_master(at)live(dot)com sayesinde MSSQL başarılı oturum açma koşulu düzeltildi
* http form modülünü düzeltin: isteğe bağlı başlıklar ve 3xx durum yönlendirmesi, Gash'e teşekkürler
* Dazzlepod sayesinde --prefix seçeneği için yapılandırma betiğinde düzeltme yapıldı
* Roland Kessler'in dpl4hydra betiğinin güncellenmesi, teşekkürler!
* Hydra man sayfası için küçük bir düzeltme, brad(at)comstyle(dot)com'a teşekkürler


Sürüm 7.1
* HTTP Proxy URL numaralandırma modülü eklendi
* Kimlik doğrulamasıyla SOCKS4/SOCKS5 proxy desteği eklendi
* SOCKS5 modülü için IPv6 desteği eklendi
* Ters girişi şifre olarak denemek için -er seçeneği eklendi
* Kod çok fazla soruna yol açtığı için -x işlevselliği yeniden yazıldı (teşekkürler
  (Sorunlardan birini bildirmek için murder.net7(at)gmail.com adresini ziyaret edin)
* Hedeflere karşı birden fazla ana bilgisayar (-M) ve http modülleriyle ilgili bir hata düzeltildi
  sanal sunuculardır. Tyler Krpata bunu çok iyi fark etti!
* SVN IPv6 desteği düzeltildi ve kullanım dışı bırakılan çağrılar güncellendi
* RDP başarısız çocuk bağlantısında döndürülen değer ve yanlış pozitif sorunları düzeltildi
  Wangchaohui'nin bildirdiğine göre, teşekkürler!
* Dosya geri yükleme işlevi düzeltildi, -o seçeneğiyle birlikte çalışmıyordu
* 7.0'da ortaya çıkan http-form modülündeki hata düzeltildi
* http-proxy modülü için xhydra'ya özgü parametre değeri düzeltildi
* küçük iyileştirmeler


Sürüm 7.0
* Hydra için yeni ana motor: daha iyi performans, esneklik ve denge
* Yeni seçenek -u - şifreler değil, kullanıcılar etrafında döngü
* -e seçeneği artık -x ve -C ile de çalışır
* RDP modülü eklendi, etki alanı argüman olarak geçirilebilir
* Güvenilir etki alanlarını test etmek için smb modülüne other_domain seçeneği eklendi
* Standart sunucuları görmezden gelmek için http ve http-proxy modülünde küçük bir geliştirme
* Özellikle çok sayıda görev, birden fazla hedef ve geri yükleme dosyasıyla ilgili birçok hata düzeltmesi
* Birkaç http-form sorunu için düzeltmeler
* Smb modülünün NTLM karma kullanımını düzeltin
* Firebird modülünün kullanım dışı bırakılan API çağrısı düzeltildi
* dpl4hydra'nın eski sed uygulamalarında (OS/X ...) çalışması için düzeltme yapıldı
* Dpl4hydra'yı kurmak için makefile düzeltildi (teşekkürler @sitecrea)
* Hata ayıklama çıktı işlevindeki yerel arabellek taşması düzeltildi (kullanılması için -d gereklidir)
* Xhydra çalışma uyarıları düzeltildi ve çıkış eylemi olayı düzeltildi


Sürüm 6.5
* Geliştirilmiş HTTP form modülü: çerez alma, başarısız veya başarılı koşulu, takip
  birden fazla yönlendirme, çerez toplama URL'sini destekleme, birden fazla kullanıcı tanımlı
  başlıklar
* Yerel fe80:: bağlantısına bağlanmak için gereken IPv6 için arayüz desteği eklendi
  adresler. Yalnızca Linux ve OS/X'te çalışır. Solaris ve *BSD için bilgiler memnuniyetle karşılanır.
* Bağlantılar arasında -W bekleme süresi seçeneği eklendi
* -x kaba kuvvet modu artık 2 milyardan büyük parola miktarlarının oluşturulmasına izin veriyor
* -L'nin -x ile birlikte kullanılması durumunda düzeltme
* http-...://target/options biçimi kullanıldığında http- modülleri için düzeltmeler
* Çökmeye yol açabilecek geri yükleme dosyası yazma işlevindeki bir hata düzeltildi
* XMPP modülü jabber başlatma isteği ve meydan okuma yanıt denetimi düzeltildi, "F e L o R e T" sayesinde
* Düzeltme: Bir proxy kullanıldığında, çözümlenemeyen hedefler devre dışı bırakılıyordu. Şimdi sorun yok
* URI'den sonra iki nokta üst üste kullanıldığında service://host/ kullanımı için düzeltme
  port tanımlandı
 

Sürüm 6.4
* Sunucu hatasından dönen harici IP adresini çıkarmak ve kullanmak için SIP modülünü güncelleyin ve NAT'ı atlayın
* SIP modülünü SASL kütüphanesini kullanacak şekilde güncelleyin
* TLS modu başarısız olduğunda temizleme modunu kontrol etmek için e-posta modüllerini güncelleyin
* Oracle Listener modülünün Oracle DB 9.2 ile çalışması için güncellenmesi
* LDAP modülünü Windows 2008 etkin dizin basit kimlik doğrulamasını destekleyecek şekilde güncelleyin
* Planlanan girişimleri kaybetmeye neden olan bağlantı uyarlama motorunda düzeltme
* CentOS için ya0wei tarafından bildirilen komut dosyası oluşturma düzeltildi
* Bir servis bağlantıları sınırladığında ve birkaç çiftin test edilmesi gerektiğinde yazdırma hatası
* Mysql modülü yalnızca gerektiğinde başlatılacak/kapatılacak şekilde iyileştirildi
* FreeBSD bakımcılarından yama eklendi
* Modül kullanım yardımı artık bir hedefin belirtilmesine ihtiyaç duymuyor
* Yapılandırma betiği artık /etc/ld.so.conf.d/ dizinini destekliyor
* Daha fazla SMB lehçesi ekleyin



Sürüm 6.3
* Petar Kaleychev tarafından cygwin hydra dosyalarına güzel simgeler ekleyen yama eklendi
* Gauillaume Rousse tarafından uyarı görüntüsünü düzelten yama eklendi
* Yeni Oracle modülü (OCI üzerinden veritabanları için, TNS Listener passwd için, SID numaralandırması için)
* Yeni SMTP kullanıcı enum modülü (VRFY, EXPN veya RCPT komutunu kullanarak)
* Alex Lau tarafından bildirilen -x bruteforce seçeneği için bellek sızıntısı düzeltmesi
* Svn modülü için düzeltme, bazı sürümler için bir kütüphaneye daha ihtiyaç duyuluyor, teşekkürler
  Bildiriminiz için Debian ekibine teşekkürler!
* Ssh modülü düzeltildi, bağlantı reddedildiğinde kimlik bilgileri kaybolabiliyordu
* http-form modülü düzeltildi, yönlendirme her zaman takip edilmiyordu
* Bellek sızıntıları için tüm modüllerde QA
* Daha iyi gtk tespiti (işe yaramaz olduğunda xhydra derlemesini denememek)
* x64 sistemlerine (Linux ve *BSD) yapılandırma için ilk açık deneme
* Web sayfasında ağ şifre kırıcı karşılaştırması güncellendi (hydra ve yeni ncrack için)
* Tüm kaynak kodları girintili


Sürüm 6.2
* Jan Dlabal tarafından şifre oluşturma ve kaba kuvvet kullanma özelliğini ekleyen bir yama eklendi (şifre dosyaları artık yok :-) )
* Xhydra'da ssh2'yi ssh olarak yeniden adlandırmayı unuttum, düzeltildi
* CRAM-MD5 ve DIGEST-MD5 kimlik doğrulaması için ldap modülüne destek eklendi
* SASL PLAIN kimlik doğrulama yöntemi sorununu düzeltin
* smtp-auth, pop3, imap, ftp ve ldap için TLS müzakere desteği eklendi
* Debian bakımcılarından gelen man sayfaları eklendi
* Teamspeak modülü kontrol edildi, TS2 protokolünde çalışıyor
* SCRAM-SHA1 (RFC 5802) desteği eklendi, bunu destekleyen ilk kimlik doğrulama kırıcı, evet!
* Yeni modül: TLS müzakeresi ve LOGIN, PLAIN, CRAM-MD5, DIGEST-MD5, SCRAM-SHA1 desteğine sahip XMPP
* IMAP modülüne SCRAM-SHA1 yetkilendirmesi eklendi
* Modül kullanım yardımı ekle (-U)
* RFC 4013 desteği eklendi: SASL'de Uluslararasılaştırılmış Dizeler ("SASLPrep")
* smtpauth modülünün adını smtp olarak değiştirin
* NNTP için SASL + TLS desteği eklendi
* SASL DIGEST-MD5 hatası düzeltildi, yanıt bazen yanlış olabiliyor, özellikle 64 bit sistemlerde
* rlogin modülünde hata düzeltmesi yapıldı, bazı kimlik doğrulama hataları doğru bir şekilde tespit edilemedi
* Rsh modülünde hata düzeltmesi yapıldı, bazı kimlik doğrulama hataları doğru bir şekilde tespit edilemedi
* Yeni modül: IRC ölmedi! Genel sunucu şifresini ve /oper kimlik bilgilerini bulmak için kullanılır
* VMware Authentication Daemon modülü için SSL desteği eklendi
* CVS modülündeki hata düzeltildi, artık çalışması gerekiyor, neden kimse bunu bildirmiyor?
* Hat modu kullanılamadığında Telnet modülündeki hata düzeltildi
* Yeni sözdizimi <hizmet-adı>://<hedef>[:<bağlantı noktası numarası>][/<parametreler>] için destek eklendi
* SIP için TLS desteği eklendi
* HALA AÇIK: Hydra'da bir kol/çocuk çıkarken oturum açma+şifre testinin kaybolmasına neden olan bir sorun düzeltildi


Sürüm 6.1
* Debian kullanıcıları için dosyalarda daha fazla lisans güncellemesi
* Postgresql'i doğru şekilde algılamak için yapılandırma betiğinin düzeltilmesi
* libssh v0.4 için kontroller ve ssh v1 için destek eklendi
* Sasl dosyalarındaki tüm son şifreleme kodlarını birleştir
* OpenSUSE'deki SVN derleme sorunu düzeltildi (v11.3 ile test edildi)


Sürüm 6.0
* OpenSSL'e bağlantıya izin vermek için lisansa GPL istisna maddesi eklendi - Debian kullanıcılarının buna ihtiyacı var
* IPv6 desteği nihayet eklendi. Not: sip ve socks5 modülleri henüz IPv6'yı desteklemiyor.
* Solaris 11'de temiz derlemeyi sağlamak için kod ve yapılandırma betiğinde değişiklikler yapıldı,
  OSX, FreeBSD 8.1, Cygwin ve Linux
* SIP modülü için hata düzeltmesi, yori(at)counterhackchallenges(dot)com'a teşekkürler
* OpenSSL olmayan veya eski OpenSSL kurulumları olan sistemler için düzeltmeleri derleyin
* Derleme zamanı uyarıları ortadan kaldırıldı
* xhydra yeni özellikleri desteklemek için güncellendi (david@)
* smtp-auth modülüne CRAM-MD5, DIGEST-MD5 yetkilendirme mekanizması eklendi (david@)
* imap ve pop3 modüllerine LOGIN, PLAIN, CRAM-(MD5,SHA1,SHA256) ve DIGEST-MD5 kimlik doğrulama mekanizmaları eklendi (david@)
* POP3 modülüne APOP yetkilendirmesi eklendi (david@)
* http-auth modülüne NTLM ve DIGEST-MD5, http-proxy modülüne ise DIGEST-MD5 eklendi (david@)
* Hiçbiri ve VLC kimlik doğrulaması için VNC modülü düzeltildi (david@)
* LDAP modülü için düzeltmeler (david@)
* Win7 kullanılarak Telnet modülü satır modu seçeneği müzakeresinde hata düzeltmesi (david@)
* Maksimum yetkilendirme bağlantısına ulaşıldığında SSH modülündeki hata düzeltmesi (david@)


Sürüm 5.9
* Yeni SVN sürümleri için subversion modülü güncellemesi (GMAIL dot com'daki David Maciejak'a teşekkürler)
* David'in smtp-auth modülüne PLAIN yetkilendirme mekanizmasını eklemek için yaptığı bir yama daha
* MySQL modülünün artık iki uygulaması var ve bulunduğunda bir kütüphane kullanıyor (tekrar)
  David Maciejak @GMAIL dot com'a teşekkürler - onsuz Hydra ne olurdu?)
* camiloculpian @gmail.com hydra için bir logo gönderdi - harika görünüyor, teşekkürler!
* Daha iyi FTP 530 hata kodu tespiti
* Standart dışı portlar için SVN modülünde hata düzeltmesi (yine david@)


Sürüm 5.8
* Apple Dosyalama Protokolü eklendi ("asla yorulmayan" David Maciejak'a teşekkürler @GMAIL dot com)
* SSL seçeneğindeki (-S) büyük bir hata düzeltildi


Sürüm 5.7
* ncp desteği ve küçük düzeltmeler eklendi (David Maciejak @ GMAIL dot com tarafından)
* SSL'den gelen bir belleği düzeltmek ve hızlandırmak için kan(at)dcit.cz adresinden eski bir yama eklendi
* Gereksiz derleyici uyarıları kaldırıldı
* Aris(at)0xbadc0de.be'den alınan eski bir yamaya dayanarak SSH2 modülü geliştirildi
* Teamspeak modülündeki küçük yerel tanımlı taşma düzeltildi. Hâlâ çalışıyor mu?


Sürüm 5.6 ÖZEL SÜRÜM
###########
* GPLv3 Lisansına geçildi (birçok kişi bunu istiyordu)
* Ssh2 modülü libssh-0.4.x'e yükseltildi (aris (at) 0xbadc0de.be'ye teşekkürler)
  (0,2 baz)
* Firebird desteği eklendi (David Maciejak @ GMAIL dot com tarafından)
* SIP MD5 yetkilendirme yaması eklendi (Jean-Baptiste Aviat <jba [at] hsc [dot] `french tld` tarafından)
* Palm ve ARM desteği kaldırıldı
* Postgres kütüphanesi olmadığı halde cygwin'in yanlışlıkla Postgres kütüphanesini tespit etmesi sorunu giderildi.
* Birkaç küçük hata düzeltmesi


Sürüm 5.4
###########
* Bazı Apache kurulumları seçici olduğundan http modüllerinde düzeltmeler yapıldı
* MySQL modülü mysqld-5.0 ile de çalışır, güncellendi
* Pop3 modülüne AS/400 dönüş kodu kontrolleri eklendi
* http-form modülündeki bellek sızıntıları düzeltildi.
* Jean-Baptiste.BEAUFRETON (at) turbomeca.fr tarafından yapılan bir teklif uygulandı
  ftp modülünde "530 kullanıcı bilinmiyor" mesajını kontrol edin
* alejandro.mendiondo (at) baicom.com tarafından bir performans yaması eklendi. Bu
  stabilite testine ihtiyacı var!
* Modern gcc'nin derleyici uyarılarını kaldırmak için güzelleştirme


Sürüm 5.3
###########
* Pop3, imap, smtp-auth ve http-proxy için NTLM destek modülleri eklendi.
  Çalışma ilo (at) reversing.org tarafından yapılmıştır. TEŞEKKÜRLER!
* phil (at) irmplc.com'a teşekkürler, bir http form modülü eklendi
* vnc modülündeki bir hata düzeltildi (kan (at) dcit.cz'ye teşekkürler)
* Giriş dosyaları boş baytlar içeremez. Bunu gelecekte düzeltebilirim.
  ama şu anda yapılacaklar listemde yeterince başka şey var.
  Bildirim için didiln (at) gmail.com'a teşekkürler.


Sürüm 5.2
###########
* SSH2 modülü için yine bazı düzeltmeler. Bu son deneme. Eğer
  sonunda güvenilir çalışmıyor, o kütüphaneyi atıyorum!
  Yama için bykhe@mymail.ch'ye teşekkürler
* Yeni bir modül eklendi: VMWare-Auth! david.maciejak@gmail.com'a teşekkürler!


Sürüm 5.1
###########
* SSH2 modülü için yine bazı düzeltmeler yapıldı. Üzgünüm. Yine de çalışmayabilir.
  her durumda. Libssh hepimizin istediği kadar olgun değil :-(
* HYDRA_PROXY_AUTH hiç kullanılmadı... kimsenin bunu bildirmemesi garip. düzeltildi.
* Base64 kodlama işlevindeki hata düzeltildi
* Openssl 0.9.8'den beri ihtiyaç duyulan md5.h eklentisi eklendi
* FTP modülüne piotr_sobolewski@o2.pl'ye teşekkürler, bir geliştirme eklendi
* Şifre kullanılmadığında ve sadece -en/s kullanıldığında oluşan bir hata düzeltildi


Sürüm 5.0
###########
! BU BİR THC - VERGİ - 10. YIL DÖNÜMÜ ÇIKIŞIDIR ! EĞLENCELİ OLUN !
* Çoğu modül için inanılmaz hızlanma :-)
* PC-Anywhere için modül eklendi, david.maciejak(at)kyxar.fr'ye teşekkürler!
* SVN için modül eklendi, david.maciejak(at)kyxar.fr'ye teşekkürler!
* --disable-xhydra yapılandırma seçeneği eklendi, david.maciejak(at)kyxar.fr'ye teşekkürler!
  - en büyük destekçisi oluyor :-)
* SIP (VoIP) için modül eklendi, gh0st(at)staatsfeind.org'a teşekkürler
* Daha yeni sap r/3 rfcsdk için destek eklendi
* Cisco AAA ile çalışması için telnet modülüne kontrol eklendi
* VNC modülü için düzeltme, xmag sayesinde
* pjohnson(at)bosconet.org tarafından mysql eklentisine küçük bir geliştirme
* 4.0.x (ve gelecekteki tüm protokol 10) ile de çalışacak şekilde geliştirilmiş MySQL modülü
  (mysql protokol tipleri)
* Gereksiz daemonları tanımlamak için geliştirilmiş socks5 modülü
  kimlik doğrulama ve yanlış pozitif kontrol (aksi takdirde Dante tüm
  (başarılı olarak denenir)
* D3 için yapılandırmada derleme sorunlarına yol açan bir hata düzeltildi
  libcrypto gerektiren birkaç platform

D3 Sürümü
* sapr3 saldırı modülü eklendi (libsdk.a ve saprfc.h gerektirir)
* ssh2 saldırı modülü eklendi (libssh gerektirir)
* snakebyte@gmx.de, PalmPilot için telnet modülü desteği ekledi
* mssql modülü düzeltildi, artık çalışmalı
* -e seçeneği hatası düzeltildi
* -C seçeneği hatası düzeltildi (hiç çalışmıyordu!!)
* sabit çift algılama (-e seçeneğiyle) artı basit sözlük eklendi
  çift tespit
* Hedef bağlantı noktası artık başlangıçta görüntüleniyor

D2 Sürümü
* www/http/https/ssl modülüne daha iyi sanal ana bilgisayar desteği eklendi
  (alla@scanit.be'den gelen bir yamaya dayanarak)
* ARM desteği eklendi (henüz libdes için çalışmıyor, ssl çalışıyor), tarafından yapıldı
  <tick@thc.org> adresini işaretleyin
* Palm desteği eklendi (aslında bu daha çok yeniden yazılmış bir versiyondur ve kullanılabilir
  (hydra-modüller) snakebyte <snakebyte@gmx.de> tarafından yapılmıştır
* ms-sql saldırı modülü eklendi (HD Moore'dan perl betiğine dayalı kod)
  <hdm@digitaloffense.net>, katkınız için teşekkürler)

Sürüm D1 (3 Mart 2003)
* Dahili dağıtım işlevlerini sıfırdan yeniden yazdı. Kod artık
  daha güvenli, daha az hata içeren, okunması daha kolay.
* Akıllı yüklemeyi de içeren çoklu hedef desteği yeniden yazıldı
  başarı, hata ve yükleme oranına dayalı dengeleme
* Hizmetler için maksimum bağlantı sayısını akıllıca algılar (eğer sunucu başına)
  (birden fazla hedef kullanılır)
* akıllı geri yükleme dosyası yazma
* Daha hızlı (%15'e kadar)
* Tam Cygwin ve Cygwin IPv6 desteği
* Yeni araç eklendi: pw-inspector - yalnızca şifreleri denemek için kullanılabilir
  hedefin parola politikasıyla eşleşir

###########################################################################

v3.0 (ŞUBAT 2004) KAMUYA AÇIKLANMIŞTIR
* İptal edilen/çöken işlemlerinize devam edebilmeniz için bir geri yükleme işlevi eklendi
  Oturumlara devam etmek için "hydra -R" yazmanız yeterli.
  NOT: Bu özellik -M seçeneğiyle çalışmaz! Bu durumda bu özellik devre dışı kalır!
* http proxy kimlik doğrulama kırma ("http-proxy") için bir modül eklendi :-)
* HTTP ve SSL/CONNECT proxy desteği eklendi. SSL/CONNECT proxy desteği çalışıyor
  *Tüm* TCP protokolleri için, yalnızca size izin veren bir proxy bulmanız gerekir
  23 numaralı porttan BAĞLANIN...
  HYDRA_PROXY_HTTP ortam değişkeni web proxy'sini tanımlar.
  Aşağıdaki sözdizimi geçerlidir: HYDRA_PROXY_HTTP="http://123.45.67.89:8080/"
  Aynısı HYDRA_PROXY_CONNECT için de geçerli.
  Proxy için kimlik doğrulaması gerekiyorsa HYDRA_PROXY_AUTH kullanın
  ortam değişkeni:
    HYDRA_PROXY_AUTH="giriş:şifre"
* Sabit paralel ana bilgisayar tarama motoru (raporlama için m0j0.j0j0'a teşekkürler)
* Artık her dakika durum, hız ve tamamlanma süresi raporu yazdırılıyor.
* Sonunda README'yi güncelledim

v2.9 (ŞUBAT 2004) ÖZEL SÜRÜM
...

v2.8 (OCAK 2004) ÖZEL SÜRÜM
...

v2.7 (OCAK 2004) KAMUYA AÇIKLANMIŞTIR
* paralel ana bilgisayar kodu için küçük bir düzeltme (m0j0@foofus.net'e teşekkürler)

v2.6 (ARALIK 2003) KAMUYA AÇIKLANMIŞTIR
* seçici derleyiciler için bir derleme sorunu düzeltildi.

v2.5 (KASIM 2003) KAMUYA AÇIKLANMIŞTIR
* m0j0@foofus.net adresinden büyük bir yama eklendi:
    - cisco-enable modülüne AAA kimlik doğrulaması
    - Ana bilgisayarlara yönelik saldırıları paralel olarak çalıştırma
    - Kimlik doğrulama için lanman karmalarını kullanan yeni smbnt modülü libdes'e ihtiyaç duyuyor
  ! harika bir çalışma ve teşekkürler !
* FreeBSD'de kolayca derlenebilmesi için kod değiştirildi
* MacOS X - Panther'de (bu arada harika bir işletim sistemi ...) kolayca derlenebilmesi için yapılandırma değiştirildi

v2.4 (AĞUSTOS 2003) KAMUYA AÇIKLANMA
* kamuya açık yayın
=== 2.3 şeyler===
* mysql modülü eklendi (mcbethh@unf.com'a teşekkürler)
* vnc'de küçük bir düzeltme (Nessus ekibine teşekkürler)
* vnc-module (FX/Phenolite) için krediler eklendi
* Daha iyi Solaris ve *BSD desteği için yeni ./configure betiği (amap'ten kopyalandı)
* yeni e-posta/www adreslerine güncellendi => www.thc.org

v2.2 (EKİM 2002) KAMUYA AÇIKLANMIŞTIR
* -P passwordfile kullanımındaki bir hata düzeltildi... ııııı... hepinize teşekkürler
  Bu hatayı bildiren çok sayıda insan var!
* -P passwordfile'da bir parolanın daha önce yapılıp yapılmadığının kontrolü eklendi
  -tr|s anahtarı

v2.1 (NİSAN 2002) KAMUYA AÇIKLANMA
* ldap kırma modu eklendi (kendime teşekkürler, ha ;-)
* Boş parolaları ("-e n") ve aynı parolalara sahip parolaları denemek için -e seçeneği eklendi
  giriş ("-e s"). -e, -p/-P belirtildiğinde isteğe bağlıdır (ve tersi).
* Bir oturum açma bulunduğunda, Hydra artık bir sonraki oturum açma işlemine devam edecek

v2.0 (NİSAN 2002) ÖZEL SÜRÜM
! Nessus'un v1.1.14 sürümüyle Hydra bir Nessus eklentisidir!
* Hydra'yı bir nessus eklentisi yapmak için kod eklendi (deraison@cvs.nessus.org'a teşekkürler!)
* smb/samba/CIFS kırma modu eklendi (deraison@cvs.nessus.org'a teşekkürler!)
* cisco-enable kırma modu eklendi (J.Marx@secunet.de'ye teşekkürler!)
* küçük iyileştirmeler ve düzeltmeler

v1.7 (MART 2002) ÖZEL SÜRÜM
* OpenSSL'yi daha iyi algılamak için değişikliği yapılandırın
* Solaris'e taşındı

v1.6 (ŞUBAT 2002) KAMUYA AÇIKLANMIŞTIR
* socks5 desteği eklendi (bigbud@weed.tc'ye teşekkürler!)

v1.5 (ARALIK 2001) ÖZEL YAYIN
* SSL desteği için -S seçeneği eklendi (tüm TCP tabanlı protokoller için)
* Geçerli bir oturum açma/şifre keşfedildiğinde saldırıyı durdurmak için -f seçeneği eklendi
* Modüller hydra-mod'a daha uyumlu hale getirildi
* atılan şeyleri yapılandırın - gerçekten kullanılmadı ve çok karmaşıktı,
  kendim yazdım, umarım her yerde işe yarar ;-)

v1.4 (ARALIK 2001) KAMUYA AÇIKLANMIŞTIR
* REXEC kırma modülü eklendi
* NNTP kırma modülü eklendi
* VNC kırma modülü eklendi (artı ihtiyaç duyulan 3DES kütüphanesi) - bazı
  FX/Phenolite'den alınan kodun :-) çok teşekkürler
* PCNFS kırma modülü eklendi
* ICQ kırma modülü eklendi (ocsic <pisco@private.as>'a teşekkürler!!)
* pcnfs kırma modülü için hydra_connect_udp fonksiyonunu eklemem gerekiyordu
* Tüm M$ saçmalıklarıyla çalışmak için birkaç sıkıştırılabilirlik öğesi eklendi

v1.3 (Eylül 2001) KAMUYA AÇIKLANMIŞTIR
* uh W2K telnetd müzakere modunda boş baytlar gönderiyor. Geçici çözüm uygulandı.
* Bazen donan bitirme işlevleri yeniden yazıldı. Kapanışlar daha hızlı
  şimdi de öyle.
* Satır sayısı düzeltildi (her zaman bir fazlaydı)
* Çıktı dosyasına daha fazla bilgi koyun (-o)
* Bazı yapılandırma saçmalıkları kaldırıldı.

v1.2 (Ağustos 2001) ÖZEL SÜRÜM
* Hesapların birkaç kez kontrol edilmesine neden olan BÜYÜK bir hata düzeltildi.
* Telnet saldırısı için yanlış şifreyi gösteren hata düzeltildi. Şunlar için çalışır:
  bana. lütfen test edin.
* http temel kimlik doğrulama kırma eklendi. Benim işime yarıyor. Lütfen deneyin.
* Uzun bir karşılama mesajının gönderildiği durumlarda ftp cracker modülü düzeltildi
  ftp için görüntüleniyor.
* Bazı derleyici uyarıları kaldırıldı.

v1.1 (Mayıs 2001) KAMUYA AÇIKLANMA
* Hydra-mod'a bekleme+yeniden bağlanma işlevi eklendi
* Cisco modülü için ek bekleme+yeniden bağlanma
* Çok hızlı yeniden bağlanmaları önlemek için tüm saldırı modüllerine küçük bekleme süreleri eklendi
* Telnet modülüne Cisco Kullanıcı Adı/Parola desteği eklendi
* Modüllerdeki bir çıkmaz düzeltildi, ayrıca telnet modülündeki bir çıkmaz da düzeltildi

v1.0 (Nisan 2001) KAMUYA AÇIKLANMA
* Tüm servis modüllerinin gerçekten çalıştığı doğrulandı, herhangi bir düzeltmeye gerek yok ;-)
  ... o halde bunu kamuoyuna açıklayalım
* LİSANS değiştirildi

v0.6 (Nisan 2001) ÖZEL SÜRÜM
* Cisco'nun 3 kez "Parola:" türü için hydra-cisco.c eklendi
* imap hizmeti için hydra-imap.c eklendi
* Hydra-mod.c'deki bir hata düzeltildi: boş oturum açmalar boş bir oturum açmayla sonuçlandı
  hydra_get_next_password() :-(, ayrıca engelleme/alma daha iyi çalışıyor
  şimdi. (hayır, daha iyi değil - mükemmel ;-)
* Hydra-telnet.c'deki bir hata düzeltildi: bazı hatalar nedeniyle başarıya ulaşmak için çok fazla yanlış alarm veriliyor.
  Benim tarafımdan yanlış düşünüldü ve ayrıca daha esnek bir kontrol uyguladım
* Hydra-ftp.c daha tuhaf tepkilere izin verecek şekilde düzeltildi
* Tüm ;-) bellek sızıntıları düzeltildi

v0.5 (Aralık 2000) KAMUYA AÇIKLANMIŞTIR
* NOT: YENİ BİR WWW ADRESİMİZ VAR -> www.thehackerschoice.com
* telnet protokolü eklendi
* snprintf'i sprintf(%.250s) ile değiştirerek daha fazla platformda derlenmesini sağladık
  ancak hala tampon taşma koruması var.
* Makefile.in'deki bir hata düzeltildi (Plasmo tarafından tanıtıldı,-)

v0.4 (Ağustos 2000) KAMUYA AÇIKLANMA
* Plasmoid'e ./configure betiği eklendi. Teşekkürler!

v0.3 (Ağustos 2000)
* ilk sürüm
