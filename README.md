<h1 align="center">dYmension - IBC - TX</h1>


### Bu içerikte katkısı bulunan arkadaşlara hepimiz adına teşekkürlerimizi iletirim

> @ahmkah - @enzifiri - @resnodes - @avalanchezone

#

<h1 align="center">SUPRİZZZ</h1>

> Eğer bir app kodlayamadıysan bu app'de kendi ağını ve tokenini kullanabilirsin

> http://ruescompare.xyz/

> Kendi ağınızın etkileşiminizi arttırabilirsiniz böylece.

> Ayrıca arbitrajcılara kolay bir app :D

#

<h1 align="center">Bu reponun amacı nedir?</h1>

> Bu [tweetimde](https://x.com/Ruesandora0/status/1719086955370037650?s=20) ki işlemleri daha kolay hale getirmek.

> Maksimum ödüle erişemek.

> Tek yiyen tek ölür mottosu ile birlik olmak.

#

> Not: Bu ağda RUES ağından örnek verilmiştir, kullandıktan sonra diğer ağlarda da aynı işlemleri yapabilirsiniz

#

<h1 align="center">Gelişitirici Modu Açma</h1>

![image](https://github.com/enzifiri/dYmension-app/assets/76253089/adf90139-caea-4831-8d69-d361f9f2f66e)



<h1 align="center">Ağları ekleme</h1>

> Şimdi Roll Applerin ağlarını cüzdanımıza ekleyeceğiz (IBC transfer kısmında lazım olacak)

> [Buradaki](https://portal.dymension.xyz/rollapp/rues_2215298-1) Linke girin ve Deposit Funds butonuna basın 

> Keplrdan Keplra gönderimi seçin. Sırasıyla görsellerdeki butonlara basın


![image](https://github.com/enzifiri/dym-auto-ibc-tx/assets/76253089/354b75c4-8322-4e2b-ae1b-5ad57114578f)


<h1 align="center">Developer modu kullanma</h1>

> Altta verdiğim urlyi tarayıcınızda yeni sekme açıp aratın. 

> chrome-extension://dmkamcknogkgcdfhhbddcghachkejeap/popup.html

> Sonrasında en alttaki Advanced IBC ksımındaki Transfer butonuna basın.

![image](https://github.com/enzifiri/dym-auto-ibc-tx/assets/76253089/51b8a444-620e-49b8-a21d-77f0378ae5f3)


<h1 align="center">Channel-id ekleme</h1>

> DYM tokeni seçin ve Desnation chain kısmına basın en altta New IBC Trasnfer channele basın.

> Ağı eklemeden bu aşamaya geçerseniz Chain kısmına göremeyeceksiniz Önce ağı ekleyin. 

> Destination chain: `Rues_221....` Channel: `6195`, 

> Bilgileri girdikten sonra save diyip kaydedin.

> Kendi veya başkasının channel-id nasıl öğrenirim? burada

![image](https://github.com/enzifiri/dym-auto-ibc-tx/assets/76253089/8393cb2e-829b-4dc6-9c46-c1cf3f11d8ed)


<h1 align="center">Rollapp'leri kullanma</h1>

> Wallet addres kısmına ethm1hmssffakpll0d3hesk2j8s286zd9yfv0pzlcag girin. Bu herkeste aynı, çünkü bu IBC transfer adresi. Channel kısmında ise kime göndereceğimizi belirlemiş oluyoruz.

> adress: `ethm1hmssffakpll0d3hesk2j8s286zd9yfv0pzlcag`

> Adresi girip Next butonuna basın.


![image](https://github.com/enzifiri/dym-auto-ibc-tx/assets/76253089/7eb183c1-4c93-48af-8de2-3235a861ffb4)


<h1 align="center">TX yapmak</h1>

> Sonrasına Amount kısmına rastgele sayılar yazıp tx atın.. 

> Next butonuna basmadan önce fotoğrafta belirttiğim gibi oluşan URLyi bi yere not edin, TX yapacağımız zaman bu urlyi aratıp hızlıca TX kasabileceğiz.

![image](https://github.com/enzifiri/dym-auto-ibc-tx/assets/76253089/0e7444f8-0640-4a41-b2bf-34e5264e27b1)

>  Keplr kullanarak IBC transfer yapmak bu kadar basit, Bu işlemlerden sonra Otomatik olarak IBC Transfer göndermek için script var. 

> Kimin Rollupunda TX kasacaksanız 2. adımda anlattığım Rollup Ağını ekleyip bunu Keplra tanıtmanız gerekiyor. 

#

# Script kullanımı

> kodda ki `window.location.href` kısmında kimle tx kasacaksanız onun urlsini değiştirin.

> Kodu kullanmadan alttaki urlye tekrar gidelim sağ tıklayıp incele diyelim

> Ardından sol üstteki Console butonuna basıp kodu direk yapıştırıp çalıştırın.

>  Not: Sekmeyi arkaplana atarsanız IBC transfer gönderilmiyor, bilgisayarı kullanmadığınız anda açıp Tarayıcınızı arkaplana atmayın.

![image](https://github.com/enzifiri/dym-auto-ibc-tx/assets/76253089/4e50dd07-aea9-4d9f-bd4f-f9f363d5b15a)

### Url: chrome-extension://dmkamcknogkgcdfhhbddcghachkejeap/popup.html

```
async function anaIslem() {
    const bekle = (ms) => new Promise(resolve => setTimeout(resolve, ms));

    while (true) {
        // BASKASINA TRANSFER YAPACAKSANIZ BURDAKİ URLYİ DEĞİŞTİRİN. (default rues_221....)
        window.location.href = 'chrome-extension://dmkamcknogkgcdfhhbddcghachkejeap/popup.html#/ibc-transfer?chainId=froopyland_100-1&coinMinimalDenom=udym&initialGasAdjustment=1.3&initialIBCChannels=%5B%7B%22channelId%22%3A%22channel-6195%22%2C%22counterpartyChainId%22%3A%22rues_2215298-1%22%2C%22portId%22%3A%22transfer%22%7D%5D&initialRecipient=ethm1hmssffakpll0d3hesk2j8s286zd9yfv0pzlcag&initialFeeCurrency=udym&initialFeeType=average&initialAmount=0.01';

        await bekle(1000); // Sayfanın yüklenmesini bekleyin (gerektiğinde süreyi ayarlayın)

        let nextBulundu = false;
        let approveBulundu = false;

        try {
            // İlk Next düğmesine tıkla
            document.querySelector('#app > div > div > div > div.simplebar-wrapper > div.simplebar-mask > div > div > div > div > div.sc-bczRLJ.DypIt > div > div > button').click();
            nextBulundu = true;
        } catch (error) {
            nextBulundu = false;
            console.error('İlk Next düğmesi bulunamadı. Tekrar deneyin.');
        }

        await bekle(1000); // Sayfanın yüklenmesini bekleyin (gerektiğinde süreyi ayarlayın)

        try {
            // İkinci Next düğmesine tıkla
            document.querySelector('#app > div > div > div > div.simplebar-wrapper > div.simplebar-mask > div > div > div > div > div.sc-bczRLJ.DypIt > div > div > button').click();
            nextBulundu = true;
        } catch (error) {
            nextBulundu = false;
            console.error('İkinci Next düğmesi bulunamadı. Tekrar deneyin.');
        }

        await bekle(1000); // Sayfanın yüklenmesini bekleyin (gerektiğinde süreyi ayarlayın)

        try {
            // Approve düğmesine tıkla
            document.querySelector('#app > div > div > div > div.simplebar-wrapper > div.simplebar-mask > div > div > div > div > div.sc-bczRLJ.DypIt > div > button').click();
            approveBulundu = true;
        } catch (error) {
            approveBulundu = false;
        }

        // Eğer "Approve" düğmesi bulunamazsa ve en az bir "Next" düğmesi bulunmuşsa
        if (!approveBulundu && nextBulundu) {
            // Önceki "Next" düğmelerini bulup tıkla
            try {
                document.querySelector('#app > div > div > div > div.simplebar-wrapper > div.simplebar-mask > div > div > div > div > div.sc-bczRLJ.DypIt > div > div > button').click();
            } catch (error) {
                console.error('Önceki "Next" düğmeleri bulunamadı. Tekrar deneyin.');
            }
        }

        // Transaction Success elementini bulana kadar bekleyin
        const transactionSuccess = document.querySelector('div.sc-bczRLJ.gHGHPk > div > div.sc-hKMtZM.sc-iqcoie.vhlUB.ehOBsB');
        if (transactionSuccess) {
            // İşlem başarıyla tamamlandığında döngüyü baştan başlatın
            continue;
        }

        // İşlemi başarıyla tamamlandığında döngüyü baştan başlatın
        await bekle(3000); // Sayfanın yüklenmesini bekleyin (gerektiğinde süreyi ayarlayın)
    }
}

// Ana işlemi başlat
anaIslem();
```
#

> Aşağıda rollapp'in listeli değilse bana aşağıda ki sıralamayı bozmadan bir Pull Request gönderebilirsin seni eklemem için.

#

> Şimdi diğer arkadaşlarımızın Rollapp Ağlarını da cüzdanlarımıza ekleyelim

> Ne kadar çok doğru rollappta işlem yaparsak (tweette anlattım), o kadar iyi

> Tüm Rollapp ağlarını ekleyelim, Otomatik tx işlemi yapacaksanız ağı ekledikten sonra 4. aşamayı yapmanız gerekiyor.

> Sonradan gelecek ağlarıda [burada](https://github.com/ruesandora/dYmension-app/blob/main/README.md#sonradan-gelenler) listeleyeceğim

> Alttaki siteye girin, Keplr cüzdanı bağlayın, sonrasında tüm butonlara sırasıyla basarak ağı cüzdana ekleyin.
[Ağları hızlıca eklemek için Website.](http://135.181.255.93/)

# Sonradan gelenler

..
