## KURULUM TALİMATLARI
# BASİT KURULUM
shell kodları 

     test -f configure || ./bootstrap
     ./configure
     make
     make install
Bu paketi yapılandırmalı, derlemeli ve kurmalısınız.
İlk satır, yani önyükleme yapan satır, geliştiriciler içindir; 
dağıtım tarball'larından derleme yaparken hiçbir şey yapmaz ve atlanabilir. 
Bir paket, önyükleme betiğini farklı şekilde adlandırabilir; 
örneğin, ad "autogen.sh" ise, ilk satır "./bootstrap" yerine "./autogen.sh" şeklinde olmalıdır.

Aşağıdaki daha ayrıntılı talimatlar geneldir;
bu pakete özgü talimatlar için "BENİOKU" dosyasına bakın. 
Bazı paketler bu "KURULUM" dosyasını sağlar, ancak aşağıda belgelenen tüm özellikleri uygulamaz.
Belirli bir pakette isteğe bağlı bir özelliğin olmaması, bir hata anlamına gelmez.
GNU paketleri için daha fazla öneri, GNU Kodlama Standartları'nda bulunabilir.


Birçok paket, sıradan oluşturucular yerine geliştiricilere yönelik betikler içerir;
çünkü daha az yüklü geliştirici araçları kullanabilirler veya gizlilik sorunlarına yol açabilecek ağa erişebilirler. 
Bu betikler, muhtemelen geliştirici araçları veya ağ kullanarak "configure" betiğini ve ilgili dosyaları oluşturarak önyükleme yapmaya çalışır. 
Önyükleme çıktısı sistemden bağımsız olduğundan, genellikle bir paket geliştiricisi tarafından çalıştırılır,
böylece çıktısı dağıtımın tar dosyasına eklenebilir ve sıradan oluşturucuların ve kullanıcıların önyükleme yapması gerekmez. 
Bazı paketlerde, önyükleme üzerinde daha ayrıntılı denetim için "./bootstrap" yerine çalıştırabileceğiniz "./autopull.sh" ve "./autogen.sh" gibi komutlar bulunur.


'configure' betiği, derleme sırasında kullanılan çeşitli sisteme bağlı değişkenler için doğru değerleri tahmin etmeye çalışır. 
Bu değerleri kullanarak paketin her dizininde bir 'Makefile' oluşturur.
Ayrıca, sisteme bağlı tanımlar içeren bir veya daha fazla '.' dosyası da oluşturabilir.
Son olarak, mevcut yapılandırmayı yeniden oluşturmak için gelecekte çalıştırabileceğiniz bir 'config.status' betiği
ve 'configure' hata ayıklaması için yararlı çıktılar içeren bir 'config.log' dosyası oluşturur.


Ayrıca, yeniden yapılandırmayı hızlandırmak için testlerinin sonuçlarını kaydeden isteğe bağlı bir dosya (genellikle 'config.cache' olarak adlandırılır 
ve '--cache-file=config.cache' veya kısaca '-C' ile etkinleştirilir) da kullanabilir. 
Önbelleğe alma, eski önbellek dosyalarının yanlışlıkla kullanılmasıyla ilgili sorunları önlemek için varsayılan olarak devre dışıdır.


Paketi derlemek için alışılmadık şeyler yapmanız gerekiyorsa, lütfen 'configure'ın bunları nasıl kontrol edebileceğini anlamaya çalışın ve farkları veya talimatları 'README' dosyasında verilen adrese gönderin , 
böylece bir sonraki sürümde dikkate alınabilirler.
Önbelleği kullanıyorsanız ve bir noktada 'config.cache' saklamak istemediğiniz sonuçlar içeriyorsa, bunu kaldırabilir veya düzenleyebilirsiniz.


Bu paketi derlemenin en basit yolu şudur:

  1. Paketin kaynak kodunun bulunduğu dizine 'cd' yazın.

  2. Bu bir geliştirici ödemesiyse ve 'configure' dosyası henüz oluşturulmamışsa
     mevcutsa, önyükleme betiğini çalıştırın (genellikle './bootstrap' veya
     Dosyayı önyüklemek ve oluşturmak için './autogen.sh' komutunu kullanın. İhtiyacınız olabilir
     özel geliştirici araçları ve önyüklemeye ağ erişimi ve
     ağ erişiminin gizlilik açısından sakıncaları olabilir.

  3. Paketi sisteminiz için yapılandırmak üzere './configure' yazın. Bu
     Biraz zaman alabilir. Çalışırken, 'configure' mesajları yazdırır
     hangi özelliklerin kontrol edildiğini söyler.

  4. Paketi derlemek için 'make' yazın.

  5. İsteğe bağlı olarak, gelen tüm kendi kendine testleri çalıştırmak için 'make check' yazın
     paket, genellikle yeni oluşturulmuş kaldırılmış ikili dosyaları kullanır.

  6. Programları ve tüm veri dosyalarını yüklemek için 'make install' yazın ve
     belgeler. Kökün sahip olduğu bir önek içine kurulum yaparken,
     Paketin düzenli olarak yapılandırılması ve oluşturulması önerilir
     kullanıcı ve yalnızca 'make install' aşaması kök ile yürütülür
     ayrıcalıklar.

  7. İsteğe bağlı olarak, kendi kendine testleri tekrarlamak için 'make installcheck' yazın, ancak
     bu sefer ikili dosyaları son kurulum yerlerinde kullanıyoruz.
     Bu hedef hiçbir şey yüklemez. Bu hedefi bir
     düzenli kullanıcı, özellikle de önceki 'make install' gerekliyse
     kök ayrıcalıkları, kurulumun tamamlandığını doğrular
     doğru bir şekilde.

  8. Programın ikili dosyalarını ve nesne dosyalarını kaldırabilirsiniz.
     'make clean' yazarak kaynak kod dizinine gidin. Ayrıca kaldırmak için
     'configure' tarafından oluşturulan dosyalar (böylece paketi derleyebilirsiniz)
     (farklı bir bilgisayar türü), 'make distclean' yazın.
     aynı zamanda bir 'bakımcıyı temiz hale getirme' hedefi, ancak bu esas olarak amaçlanmıştır
     Paketin geliştiricileri için. Kullanırsanız, şunları yapmanız gerekebilir:
     tekrar önyükleme.

  9. Paket GNU Kodlama Standartlarını takip ediyorsa, 'make' yazabilirsiniz
     Yüklü dosyaları kaldırmak için 'kaldır'.

## Kurulum Ön Koşulları
==========================

   Kurulum, bir kabuk ve bir POSIX benzeri ortam gerektirir
en azından aşağıdaki standart yardımcı programlar:

     awk cat cp diff echo expr false ls mkdir mv printf pwd rm rmdir sed
     sıralama testi tr

Bu paketin kurulumu için diğer standart yardımcı programlara ihtiyaç duyulabilir:
'grep', 'make', 'sleep' ve 'touch' ile birlikte 'gcc' gibi derleyiciler.

## Derleyiciler ve Seçenekler
=====================
Bazı sistemler derleme veya bağlantı için alışılmadık seçenekler gerektirir
'configure' betiği bunu bilmiyor. './configure --help' komutunu çalıştırın
İlgili ortam değişkenlerinden bazılarının ayrıntıları için.

   Yapılandırma parametreleri için 'configure' başlangıç değerlerini verebilirsiniz
komut satırında veya ortamda değişkenleri ayarlayarak. İşte
bir örnek:

     ./configure CC=gcc CFLAGS=-g LIBS=-lposix

   Daha fazla ayrıntı için “Değişkenleri Tanımlama” bölümüne bakın.

##Birden Fazla Mimari İçin Derleme
===================================== 
Paketi aynı anda birden fazla bilgisayar türü için derleyebilirsiniz.
Bunun için, her sistemin nesne dosyalarını kendi dizinine yerleştirebilirsiniz. 
Bunu yapmak için GNU 'make' komutunu kullanabilirsiniz. 
Nesne dosyalarının ve çalıştırılabilir dosyaların gitmesini istediğiniz dizine 'cd' komutuyla gidin ve 'configure' betiğini çalıştırın.
'configure', 'configure' komutunun bulunduğu dizinde ve '..' dizininde kaynak kodunu otomatik olarak kontrol eder. 
Bu, 'VPATH' derlemesi olarak bilinir.
GNU dışı bir 'make' ile, paketi kaynak kodu dizininde her seferinde tek bir sistem için derlemek daha güvenlidir. 
Paketi bir sistem için kurduktan sonra, başka bir sistem için yeniden yapılandırmadan önce 'make distclean' komutunu kullanın.
Bazı platformlar, özellikle macOS, tek bir ikili dosyanın farklı mimarilerde çalıştırılabildiği "fat" veya "evrensel" ikili dosyaları destekler.
Bu platformlarda, o platforma özgü seçeneklerle yalnızca bir kez yapılandırabilir ve derleyebilirsiniz.

## KURULUM ADLARI
Varsayılan olarak, `make install` paketin komutlarını şu şekilde yükler:
`/usr/local/bin`, `/usr/local/include` altındaki dosyaları dahil et, vb. 
`configure`a `--prefix=PREFIX` seçeneğini 
vererek `/usr/local` dışında bir kurulum öneki belirtebilirsiniz; burada PREFIX 
mutlak bir dosya adı olmalıdır. 
Mimariye özgü dosyalar ve mimariden bağımsız dosyalar 
   için ayrı kurulum önekleri belirtebilirsiniz . 
`configure`a `--exec-prefix=PREFIX` seçeneğini geçirirseniz, paket 
programları ve kitaplıkları yüklemek için önek olarak PREFIX'i kullanır. 
Belgeler ve diğer veri dosyaları hala normal öneki kullanır. Ayrıca, alışılmadık bir dizin düzeni kullanıyorsanız, belirli 
dosya türleri 
için farklı değerler belirtmek üzere `--bindir=DIR` gibi seçenekler 
   verebilirsiniz . 
Ayarlayabileceğiniz dizinlerin ve içlerine hangi tür dosyaların yerleştirileceğinin listesi için `configure --help` komutunu çalıştırın . Genel olarak, 
bu seçeneklerin varsayılan değeri `${prefix}` cinsinden ifade edilir, bu nedenle 
yalnızca '--prefix' belirtmek, 
açıkça belirtilmeyen diğer tüm dizin özelliklerini etkiler. Kurulum konumlarını etkilemenin en taşınabilir yolu 
, doğru konumları `configure` komutuna 
   geçirmektir ; ancak birçok paket 
, kurulum konumlarını yeniden yapılandırmak veya yeniden derlemek zorunda kalmadan değiştirmek için değişken atamalarını `make install` komut satırına 
geçirme kısayollarından birini veya her ikisini de sağlar 
. 
   İlk yöntem, etkilenen her dizin için bir geçersiz kılma değişkeni sağlamayı içerir 
. Örneğin, `make install prefix=/alternate/directory` komutu 
, `${prefix}`
cinsinden ifade edilen 
tüm dizin yapılandırma değişkenleri için alternatif bir konum seçecektir . `configure` sırasında belirtilen 
ancak `${prefix}` ile belirtilmeyen tüm dizinler, 
tüm kurulumun yeniden konumlandırılması için kurulum sırasında geçersiz kılınmalıdır. Her dizin değişkeni için makefile değişkeni geçersiz kılma yaklaşımı 
GNU 
Kodlama Standartları tarafından gereklidir ve ideal olarak yeniden derlemeye neden olmaz. Ancak bazı platformların, özellikle 
GNU Libtool kullanan paketlerde fark edilir şekilde 
, bu yöntemi kullanırken yeniden derleme gerektiren 
paylaşımlı kütüphanelerin semantiğiyle ilgili bilinen sınırlamaları vardır . 
   İkinci yöntem, `DESTDIR` değişkenini sağlamayı içerir. Örneğin 
, `make install DESTDIR=/alternate/directory`, tüm kurulum adlarından önce `/alternate/directory` ekler . 
`DESTDIR` geçersiz kılma 
yaklaşımı GNU Kodlama Standartları tarafından gerekli değildir ve
Sürücü harfleri olan platformlarda çalışmaz. Diğer yandan, 
yeniden derleme sorunlarından kaçınmada daha iyidir ve 
`configure` sırasında 
bazı dizin seçenekleri `${prefix}` açısından belirtilmemiş olsa bile iyi çalışır. 


## İsteğe Bağlı Özellikler 
=================
Paket destekliyorsa, 
`configure`a `--program-prefix=PREFIX` veya `--program-suffix=SUFFIX` seçeneğini 
vererek programların adlarında fazladan bir önek veya sonek ile 
   yüklenmesini sağlayabilirsiniz . 
   Bazı paketler `configure` için `--enable-FEATURE` 
   ve `--disable-FEATURE` seçeneklerine dikkat eder ; burada FEATURE 
paketin isteğe bağlı 
bir kısmını belirtir . Ayrıca, PACKAGE'in 
`gnu-ld` gibi bir şey 
olduğu `--with-PACKAGE` ve `--without-PACKAGE` seçeneklerine de dikkat edebilirler . `./configure --help`
, paketin tanıdığı `--enable-...` ve `--with-...` seçeneklerinden bahsetmelidir. Bazı paketler 
`make` komutunun yürütülmesinin 
ne kadar ayrıntılı olacağını yapılandırma olanağı sunar . Bu paketler için `./configure --enable-silent-rules`
komutunu çalıştırmak varsayılanı en az çıktı olarak ayarlar ve bu da 
`make V=1` ile geçersiz kılınabilir; `./configure 
--disable-silent-rules` komutunu çalıştırmak ise varsayılanı ayrıntılı olarak ayarlar ve bu da 
`make V=0` ile geçersiz kılınabilir. 

## Sistem Türünü Belirtme 
========================= 
   Varsayılan olarak `configure` geçerli sistem için derleme yapar. 
Farklı bir sistem türünde çalışabilecek ikili dosyalar oluşturmak için TYPE için nesne kodunun 
nasıl oluşturulacağını belirten derleyici değişkenleriyle birlikte `--host=TYPE` seçeneğini belirtin 
. Örneğin, 
64-bit ARM işlemcide çalışması amaçlanan ikili dosyalar oluşturmak için: 
     ./configure --host=aarch64-linux-gnu \ 
        CC=aarch64-linux-gnu-gcc \ 
        CXX=aarch64-linux-gnu-g++ 
Bu ikili dosyaları çalıştırabilen bir makinede yapılırsa (örneğin, 
`qemu-aarch64`, `$QEMU_LD_PREFIX` ve Linux'un `binfmt_misc`
yeteneği aracılığıyla), derleme yerel bir derleme gibi davranır. Aksi takdirde çapraz derleme yapılır 
: "configure", test programları çalıştırmak yerine çapraz derleme tahminleri yapar 
ve "make check" çalışmaz. 
   Bir sistem türü, "mingw64" gibi kısa bir ad veya "x86_64-pc-linux-gnu" gibi standart bir ad olabilir 
. Standart adlar 
CPU-COMPANY-SYSTEM biçimindedir; burada SYSTEM, OS veya KERNEL-OS'dir. Bir sistem türünü standartlaştırmak ve doğrulamak için , 
genellikle aşağıdaki gibi bir alt dizinde saklanan "config.sub" 
komutunu çalıştırabilirsiniz :
`build-aux`. Örneğin: 

     $ build-aux/config.sub arm64-linux 
     aarch64-unknown-linux-gnu 
     $ build-aux/config.sub riscv-lnx 
     Geçersiz yapılandırma 'riscv-lnx': İşletim sistemi 'lnx' tanınmıyor 

Hangi türlerin tanındığını görmek için `config.sub` dosyasına bakabilirsiniz. 
Dosya yoksa, bu paketin sistem türüne ihtiyacı yoktur. 

   `configure` "yapı türü tahmin edilemiyor" tanılamasıyla başarısız olursa. 
`config.sub` sisteminizin türünü tanımadı. Bu durumda, önce 
bu dosyaların en yeni sürümlerini GNU yapılandırma paketinden  Eğer bu sorunu çözerse, lütfen 
`configure`
içeren paketin bakımcılarına bildirin . Aksi takdirde, 
TYPE sistem türünüze yakın olduğu için `--build=TYPE` yapılandırma seçeneğini deneyebilirsiniz ; ayrıca, lütfen 
sorunu <zukonizim@gmail.com> adresine bildirin. 
   Sistem türlerini yapılandırma hakkında daha fazla bilgi için Autoconf 
belgelerine bakın.


## Varsayılanları Paylaşma 
================= 
   Paylaşılacak `configure` betikleri için varsayılan değerler ayarlamak istiyorsanız, 
`C`, `cache_file` ve `prefix` gibi değişkenler için varsayılan değerler 
veren `config.site` adlı bir site kabuk betiği oluşturabilirsiniz . 
`configure`, varsa `PREFIX/share/config.site` dizinini arar, 
varsa `PREFIX/etc/config.site` dizinini arar. Veya, 
`CONFIG_SITE` ortam değişkenini site betiğinin konumuna ayarlayabilirsiniz . 
Uyarı: tüm `configure` betikleri bir site betiği aramaz.


## Değişkenleri Tanımlama 
=================== Bir site kabuk betiğinde tanımlanmayan değişkenler 
, `configure`a geçirilen ortamda 
   ayarlanabilir . Ancak, bazı paketler 
derleme sırasında configure'ı tekrar çalıştırabilir ve bu 
değişkenlerin özelleştirilmiş değerleri kaybolabilir. Bu sorunu önlemek için, 
bunları `configure` komut satırında `VAR=value` kullanarak ayarlamalısınız. Örneğin: 
     ./configure CC=/usr/local2/bin/gcc, 
belirtilen `gcc`nin C derleyicisi olarak kullanılmasına neden olur ( 
site kabuk betiğinde geçersiz kılınmadığı sürece). 
Ne yazık ki, bu teknik, bir Autoconf sınırlaması nedeniyle `CONFIG_SHELL` için çalışmıyor 
. Sınırlama kaldırılıncaya kadar, şu geçici çözümü kullanabilirsiniz 
: 
    `CONFIG_SHELL=/bin/bash ./configure CONFIG_SHELL=/bin/bash`
    `configure`   
