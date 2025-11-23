<img width="1200" height="300" alt="0_5ouMdY_Pjm7wDkVx" src="https://github.com/user-attachments/assets/13a15c9f-5a54-4c46-b075-a23d50ea5fa1" />

Redbelly düğümünüzü normal bir şekilde kurun. Kurulum tamamlandıktan sonra düğümünüz senkronize olmaya başladığında aşağıda ki komutlardan devam edin kuruluma. Bu snapshot dosyası 2633535 bloktan düğümünüzü başlatacaktır.

------

1- Redbelly servisini durdurun

```Sieve
sudo systemctl stop redbelly.service
```
2- Nodekey dosyasını yedekleyin

```Sieve
sudo mv /opt/redbelly/rbn/database/nodekey /opt/redbelly/rbn/nodekey
```

3- Eski veri klasörünü silin

```Sieve
sudo rm -rf /opt/redbelly/rbn/database
```

4- Snapshot’ı indirip klasöre çıkarın.

```Sieve
curl -L http://redbellysnapshot.lorentochain.online/redbelly/redbelly-snapshot.tar.gz | sudo tar -xz -C /opt/redbelly/rbn
```

5- Snapshot yüklemesi tamamlandıktan sonra Nodekey dosyasını geri yükleyin

```Sieve
sudo mv /opt/redbelly/rbn/nodekey /opt/redbelly/rbn/database/nodekey
```

6- Redbelly servisini tekrar başlatın

```Sieve
sudo systemctl start redbelly.service
```

7- Servis durumunu görmek için

```Sieve
systemctl status redbelly.service
```









