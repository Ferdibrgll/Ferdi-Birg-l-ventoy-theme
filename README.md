
# Ventoy Özel Tema ve Yapılandırma

Ventoy ile hazırlanmış çoklu önyükleme (multiboot) USB bellekler için özelleştirilmiş tema, simge seti ve menü yapılandırmasıdır. Kali Linux, Windows kurulum imajları ve kurtarma/yedekleme araçları için hazır menü simgeleri içerir.

<img width="1470" height="1070" alt="image" src="https://github.com/user-attachments/assets/41e78257-6859-4e68-b796-72b34d9545e6" />

## Özellikler

- 1920x1080 çözünürlük için hazırlanmış özel arka plan ve menü teması
- Ağaç görünümlü (TreeView) menü
- Windows 11 kurulumunda donanım denetimini atlama (`VTOY_WIN11_BYPASS_CHECK`)
- Şu araçlar için ayrı menü simgeleri: Kali Linux, Windows 8 / 10 / 11, Acronis True Image, Acronis Cyber Backup, BootIt Bare Metal, Boot Repair Disk, Elcomsoft System Recovery, Rescatux, Hiren's BootCD
- Özel GRUB menüsü ve alt menü örneği (`ventoy_grub.cfg`)
- Legacy BIOS, UEFI, IA32 ve ARM64 için ortak tema ayarı

## Kurulum

1. Ventoy'u USB belleğe kur: [ventoy.net](https://www.ventoy.net)
2. USB bellekte `ventoy` adında bir klasör oluştur.
3. Bu repodaki dosyaları şu şekilde kopyala:

```
USB:\
└── ventoy\
    ├── ventoy.json
    ├── ventoy_grub.cfg
    └── theme\
        ├── theme.txt
        ├── background.png
        └── icons\
```

4. Bilgisayarı USB'den başlat, tema ve menü otomatik yüklenecektir.

## Simgelerin Eşleşmesi

`ventoy.json` içindeki `menu_class` bölümü, ISO dosya adındaki anahtar kelimeye bakarak simgeyi seçer. Örneğin dosya adında `Windows_11` geçen bir ISO, `windows11.png` simgesiyle görünür. Yeni bir simge eklemek için `theme/icons/` klasörüne bir `.png` koy ve `menu_class` listesine yeni bir giriş ekle:

```json
{ "key": "DosyaAdindaGecenKelime", "class": "simgeadi" }
```

## Notlar

- Tema dosyası yolu `/ventoy/theme/theme.txt` olmalıdır, farklı bir yere koyarsan `ventoy.json` içindeki `file` değerlerini de güncelle.
- `ventoy_grub.cfg` içindeki `custom`, `customsub` ve `custom2` sınıfları için `theme/icons/` klasörüne aynı adlarla simge eklenebilir.

## Hazırlayan

**Ferdi Birgül**
