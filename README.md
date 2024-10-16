# Xardian-Mainnet

Neden XProtocol.org yatırımı yaptım çünkü;

1) Yatırımcıları arasında Dragon Fly var:
   ![Ekran görüntüsü 2024-10-15 225041](https://github.com/user-attachments/assets/f461572a-3397-4e57-96a5-2868b876d2dc)

2) Animoca Brands ve Aethir gibi iki önemli unsur var:
   ![Ekran görüntüsü 2024-10-15 225305](https://github.com/user-attachments/assets/43b4c919-e341-444d-be9f-2c491876413a)

3) Nod fiyatı ve buna karşılık gelen FDV bana uygun geldi, aşağıdaki tabloya göre ben Tier 2'den ve 9.970.625$ gibi düşük bir FDV ile almış oldum:
   ![Ekran görüntüsü 2024-10-15 225451](https://github.com/user-attachments/assets/f626fc3e-9334-48be-a882-a5fe9eeeec59)

4) 2025 Q1'de dünyanın ilk DePin akıllı cep telefonunu piyasaya sürecek olmaları

Proje Linkleri:

Resmi Site: https://xprotocol.org/

X: https://x.com/xprotocol_org

Discord: https://discord.gg/xprotocol

Nod Satış Linki: https://xprotocol.org/node-sales

Kaynak Döküman: https://docs.xprotocol.org/x-protocol-litepaper/overview/xardian-nodes/how-to-run-nodes

Tabi her projede olduğu gibi kendiniz iyice araştırma yapıp öyle adım atın, yaptığım şey kesinlikle bir Yatırım Tavsiyesi Değildir!!!

### Sistem Gereksinimleri

```
4 GB RAM
2 CPU
60 GB SSD
Ubuntu 22.04
```

## Öncelikle sistem paketlerini güncelleyelim

```
sudo apt update && sudo apt upgrade -y
```

## Xardian nod yazılımını indirelim

```
wget https://github.com/xprotocol-org/xardian/releases/latest/download/runner.linux.amd64
```

## Çalışması için izin verelim

```
chmod +x runner.linux.amd64
```

## Screen açalım

Eğer sıfır sunucu kullanıyorsak screen açmadan önce screen yüklemek gerekebilir, bu sunucuyu aldığınız firmaya göre değişiyor

```
screen -S xardian
```
Bu kod screen açmazsa;
```
sudo apt install screen
```
komutunu girip sonra screen -S xardian komutunu girelim

## Nodu çalıştıralım

```
./runner.linux.amd64
```

## Delege edelim
Eğer nod satın aldığınız bir cüzdan varsa bu adımda o cüzdanı import etmemiz gerekiyor. Bunun için aşağıdaki kodda "cüzdan-priv-keyi" yazan yere kendi nod satın aldığınız cüzdanın priv keyini yazın!

```
./runner.linux.amd64 import --key cüzdan-priv-keyi
```
#### Delege işlemini tamamlayalım
```
./runner.linux.amd64 delegate
```
Bu kod size bir URL verecek, bu URL'yi kopyalayıp tarayıcınıza yapıştırın ve nod satın aldığınız cüzdanla bağlanın, adres şöyle bir şey olacak: https://xprotocol.org/assign-wallet/0x... şeklinde import ettiğiniz cüzdan adresiyle biter. 

![Ekran görüntüsü 2024-10-15 223505](https://github.com/user-attachments/assets/70945174-cbfd-4092-92e6-3f6c9a16dbb8)

Assign Wallet tuşuna tıklayıp cüzdandan onay veriyoruz. Sonra cüzdan adresimizi kopyalayıp terminale yapıştırıyoruz ve enter ile devam ediyoruz. İşlem başarılıysa şöyle bir çıktı almanız gerekecek:

![Ekran görüntüsü 2024-10-15 223339](https://github.com/user-attachments/assets/56d342e8-b3ba-49b0-b8ff-88ded9808647)

## Son olarak düğümü başlatıyoruz

```
./runner.linux.amd64 run
```
Çıktımız şu şekilde olacak:

![Ekran görüntüsü 2024-10-15 223505](https://github.com/user-attachments/assets/0f4bbe99-bd19-432f-a4af-32bf83782d30)

Önemli Notlar:

i) Ödüllerimizi xKICK tokeni cüzdanımıza import ederek görebiliriz. Ödüller 3-8 saatte bir güncelleniyor. Ödülleri claim edebilmek için cüzdanınızda Base ağında 0.005ETH bulundurmalısınız. 
   xKICK contract: 0xB51eFF119Ce6a238f67db7cA48431C3D319C7211

![Ekran görüntüsü 2024-10-16 125414](https://github.com/user-attachments/assets/7aa4888c-c421-486b-bef1-6d6ab680e7d8)


ii) İmport ettiğiniz priv key ile noddaki priv key aynı mı kontrol etmek için xardian.yaml dosyasını kontrol edin. Bu dosyayı /root/.config/xardian.yaml dizininde bulabilirsiniz. Ya da 
```
sudo cat /root/.config/xardian.yaml
```
kodunu girerek terminalden de kontrol edebilirsiniz.

