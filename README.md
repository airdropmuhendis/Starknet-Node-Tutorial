<h1 align="center">Starknet Node Kurulumu

## StarkNet, StarkWare tarafından geliştirilen bir Ethereum ikincil katman çözümüdür.

## Video [Linki](https://youtu.be/jf5dvWblYek) 
## Ödüller hakkında henüz bir bilgi yok yada node kuranlara ödül verilecek tarzında bir bilgi yok sadece ihtimalleri değerlendiriyoruz, ancak token lansmanının çok uzak olmadığını gösteren birkaç detay var. StarkNet'in ERC20 token sözleşmesi Ethereum üzerinde konuşlandırıldı. [Link](https://twitter.com/StarkWareLtd/status/1592897313273712640?s=20&t=judEK08Ud7__KUFNLiXThA)



## Starknet için Sunucuyu nerden nasıl alacağınızı bilmiyorsanız node eğitim serimizi izleyebilirsiniz. [Node Eğitim Serisi](https://www.youtube.com/playlist?list=PLKxGUfdcj7MVXls2OvTpwx6CnpVJN685w)

![image](https://miro.medium.com/max/1400/1*3pFkdORoGg874-rRo5Z-2w.webp)

### Sistem Gereksinimleri
 - Belli bir sınırlandırma yok ama ben aşşağıdaki sisteme kurdum herhangi bir sorun ile karşılaşmadım.
 - Ubuntu 20.04
 - 6 CPU
 - 16GB RAM
 - 400 GB Disk 

<h1 align="center">Hazırlık

Bir ethereum noduna ihtiyacımız olacak bunun için eğer varsa kendi Ethereuum nodunuza bağlanabilirsiniz veya [Alchemy](https://www.alchemy.com/) veya [Infura](https://www.infura.io/) üzerinde hesap oluşturup kullanabilirsiniz videoda detaylar mevcut.

  ## Root yetkisi almak için aşağğıdaki kodu giriyoruz bazı sunucularda bunu sürekli girmemiz gerekiyor. eğer bunu girmezseniz yazdığınız kodun başına sudo komutunu yazarkata devam edebilirsiniz ancak karışıklık olmaması için aşğıdaki komutu yazmanızı tavsiye ederim. ( root: Windows cihazlarda olduğu gibi yönetici olarak çalıştırmamıza, yani bize yetki veren bir komuttur.)
  ```
  sudo su
  cd
  ```

 ## Aşşağıdaki komutlarla sunucumuzdaki güncellemeleri, yükseltmeleri kontrol ediyoruz, sondaki -y işareti gelen onay işlemlerini otamatik olarak onaylanmasını sağlayacaktır. kısaca kurulum için sunucumuzu hazır hale getiriyoruz.

  ```
 sudo apt update && sudo apt upgrade -y
  ```
   ```
 sudo apt install pkg-config curl git build-essential libssl-dev

 ```

# Screen kuruyoruz.

 ```
  sudo apt install screen
   ```

 # Docker ile kurulum yapacağız. Docker kuralım.
 
 ## Sunucunuz üzerinde daha önceden kurulu docker uygulaması var ise kaldırılması için aşağıdaki komutu çalıştırın.

  ```
sudo apt-get remove docker docker-engine docker.io containerd runc
 ```
 ## Güncelleyin
  ```
sudo apt update && sudo apt upgrade -y
 ```
 ## Kurulum
  ```
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
 ```
 ```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add
 ```
  ```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
 ```
 ```
sudo apt-get install docker-ce docker-ce-cli containerd.io
 ```
  ## Pathfinder reposunu clonlayalım şuanda son versiyon v0.4.0 da eğer ilerleyen zamanlarda versiyon hatası alırsanız. [buradan](https://github.com/eqlabs/pathfinder/tags) son versiyonu kontrol edip güncelleyebilirsiniz.
  
   ```
git clone --branch v0.4.0 https://github.com/eqlabs/pathfinder.git
 ```
 
 #Screen Açalım 
  ```
 screen -S node
  ```
  ## bu adımdaki aşşağıdaki kodu güncellemeniz gerekcek alchemy veya infuradan aldığınız node bağlantısı ile güncelleyin. Videoda detaylar mevcut.
```
mkdir -p $HOME/pathfinder
docker run \
  --rm \
  -p 9545:9545 \
  --user "$(id -u):$(id -g)" \
  -e RUST_LOG=info \
  -e PATHFINDER_ETHEREUM_API_URL="http ile başlayan ethereum node bağlantısı" \
  -v $HOME/pathfinder:/usr/share/pathfinder/data \
  eqlabs/pathfinder
  ```
 ##Biraz bekledikten sonra loglar akmaya başlayacaktır son bloğu yaklamaya çalışacaktır son bloğu [burdan] https://voyager.online/ görüntüleyebilirsiniz . 

# Screenden cıkmak için ctrl + A + D yapabilirsiniz.

# Screene tekrar girmek için girmek için aşğıdaki komutu kullanabilirsiniz.

 ```
screen -r node
 ```
 ## Node kurulduktan sonra [Discord](https://discord.gg/qypnmzkhbc) sunucularına gidip node hakkında bilgi verelim önce tweet atıyoruz daha sonra tweet bağlantısını ve ıp adresimizi ekleyip Full-node succes odasında paylaşıyoruz.

Son olarak [Starknet topluluğuna](https://community.starknet.io/) üye olalım ve sosyal medya hesaplarımızı bağlayalım ayrıca toplulukta aktif olmaya çalışalım rozet mantığı var. Her türlü ihtimalli değerlendirmek adına node kurduk ödül garantisi yoktur. 
 
 
 
  


