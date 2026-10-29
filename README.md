# Duvardan Kacan Kaplumbaga (ROS 2 Humble)

Bu proje, ROS 2 Humble ortamında `turtlesim` simülasyonundaki kaplumbağanın hareketini kontrol eden bir Python paketidir. 

Kaplumbağa, ekran sınırlarına ($x < 1.0$, $x > 10.0$, $y < 1.0$ veya $y > 10.0$) yaklaştığında otomatik olarak yön değiştirir ve duvara çarpmaktan kaçınır.

## Özellikler

- **Abone (Subscriber):** `/turtle1/pose` konusundan (topic) konum ($x, y$) bilgilerini dinler.
- **Yayıncı (Publisher):** `/turtle1/cmd_vel` konusuna `geometry_msgs/msg/Twist` mesajları göndererek kaplumbağayı hareket ettirir.
- **Loglama:** Saniyede bir `get_logger().info` kullanarak anlık $x$ ve $y$ konumunu terminale basar.
- **Parametre Desteği (Bonus):** Çarpma sınırları ve hareket hızları ROS 2 parametreleri olarak tanımlanmıştır.

## Kurulum ve Çalıştırma

### 1. Derleme
Workspace dizininize gidip paketi derleyin:

```bash
cd ~/ros2_ws
colcon build --packages-select turtle_duvar_py
source install/setup.bash
