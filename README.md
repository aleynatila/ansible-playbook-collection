# 🚀 Ansible Playbook Koleksiyonu

[![Ansible](https://img.shields.io/badge/ansible-%231A1918.svg?styl## 🤝 Katkıda Bulunma

Katkılarınızı bekliyoruz! Lütfen aşağıdaki adımları takip edin:

1. 🍴 Repository'yi fork edin
2. 🌿 Feature branch oluşturun (`git checkout -b feature/amazing-feature`)
3. 💾 Değişikliklerinizi commit edin (`git commit -m 'Add amazing feature'`)
4. 🚀 Branch'inizi push edin (`git push origin feature/amazing-feature`)
5. 🔀 Pull Request açın

### 📝 Issue Raporlama
Hata bildirimi veya önerilerde bulunmak için [issue açabilirsiniz](https://github.com/aleynatila/ansible-playbook-collection/issues).

## 📄 Lisans

Bu proje MIT lisansı altında lisanslanmıştır. Detaylar için [LICENSE](LICENSE) dosyasına bakın.

## 🙏 Teşekkürler

- Ansible topluluğuna katkıları için
- Open source ekosisteminin geliştiricilerine

## 📞 İletişim

- 👨‍💻 **Geliştirici**: [aleynatila](https://github.com/aleynatila)
- 📧 **E-posta**: [GitHub profilinden ulaşabilirsiniz](https://github.com/aleynatila)
- 🐛 **Hata Raporları**: [Issues](https://github.com/aleynatila/ansible-playbook-collection/issues)

---

⭐ **Bu projeyi beğendiyseniz yıldız vermeyi unutmayın!**or-the-badge&logo=ansible&logoColor=white)](https://www.ansible.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/aleynatila/ansible-playbook-collection.svg)](https://github.com/aleynatila/ansible-playbook-collection/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/aleynatila/ansible-playbook-collection.svg)](https://github.com/aleynatila/ansible-playbook-collection/network)

Bu depo, sık kullanılan sistem yönetimi ve otomasyon senaryoları için hazır Ansible playbook'ları içerir. Amacı, zamandan tasarruf etmek ve sistem yöneticilerine tekrarlanabilir, güvenli işlemler sunmaktır.

## 📋 Özellikler

- ✅ Production-ready playbook'lar
- ✅ Best practice uyumlu kod yapısı
- ✅ Detaylı dokümantasyon
- ✅ Modüler ve yeniden kullanılabilir
- ✅ Güvenlik odaklı konfigürasyonlarnsible Playbook Koleksiyonu

Bu depo, sık kullanılan sistem yönetimi ve otomasyon senaryoları için hazır Ansible playbook’ları içerir. Amacı, zamandan tasarruf etmek ve sistem yöneticilerine tekrarlanabilir, güvenli işlemler sunmaktır.

## 📁 İçerik

| Playbook | Açıklama | Desteklenen OS |
|----------|----------|----------------|
| 🌐 `nginx_setup.yml` | Nginx web sunucusu kurulumu ve konfigürasyonu | Ubuntu, CentOS, RHEL |
| 👤 `user_management.yml` | Kullanıcı oluşturma, SSH key ve sudo yetkileri | Tüm Linux dağıtımları |
| 🔒 `security_hardening.yml` | Temel güvenlik sıkılaştırma ayarları | Ubuntu, CentOS, RHEL |

### 📂 Dizin Yapısı
```
ansible-playbook-collection/
├── 📁 playbooks/           # Ana playbook dosyaları
├── 📁 group_vars/         # Grup bazlı değişkenler
├── 📁 host_vars/          # Host bazlı değişkenler (opsiyonel)
├── 📄 inventory           # Örnek envanter dosyası
└── 📄 README.md          # Bu dosya
```

## 🚀 Hızlı Başlangıç

### Önkoşullar
- **Ansible 2.9+** kurulu olmalı
- Hedef sunucularda **SSH erişimi** mevcut olmalı
- **Python 3.6+** (hedef sunucularda)

### Kurulum
```bash
# Repository'yi klonlayın
git clone https://github.com/aleynatila/ansible-playbook-collection.git
cd ansible-playbook-collection

# Inventory dosyasını düzenleyin
nano inventory

# Test bağlantısı
ansible all -i inventory -m ping
```

### Kullanım Örnekleri

#### 🌐 Nginx Kurulumu
```bash
ansible-playbook -i inventory playbooks/nginx_setup.yml
```

#### 👤 Kullanıcı Yönetimi
```bash
ansible-playbook -i inventory playbooks/user_management.yml \
  --extra-vars "username=johndoe ssh_key='ssh-rsa AAAAB3...'"
```

#### 🔒 Güvenlik Sıkılaştırma
```bash
ansible-playbook -i inventory playbooks/security_hardening.yml
```

## ⚙️ Konfigürasyon

### Inventory Dosyası
```ini
[webservers]
web1.example.com ansible_user=ubuntu
web2.example.com ansible_user=ubuntu

[databases]
db1.example.com ansible_user=ubuntu

[all:vars]
ansible_ssh_private_key_file=~/.ssh/id_rsa
```

### Group Variables
`group_vars/all.yml` dosyasında global değişkenleri tanımlayabilirsiniz:
```yaml
# Nginx konfigürasyonu
nginx_user: www-data
nginx_worker_processes: auto

# Güvenlik ayarları
ssh_port: 22
allowed_users: ['ubuntu', 'admin']
```

## Katkı

PR’lar ve önerileriniz için issue açabilirsiniz.