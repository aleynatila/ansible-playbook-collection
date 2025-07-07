# Ansible Playbook Koleksiyonu

Bu depo, sık kullanılan sistem yönetimi ve otomasyon senaryoları için hazır Ansible playbook’ları içerir. Amacı, zamandan tasarruf etmek ve sistem yöneticilerine tekrarlanabilir, güvenli işlemler sunmaktır.

## İçerik

- `playbooks/nginx_setup.yml`: Hedef sunucuda Nginx web sunucusu kurar ve temel konfigürasyonu yapar.
- `playbooks/user_management.yml`: Yeni bir kullanıcı oluşturur, SSH anahtarı ekler, sudo yetkisi tanımlar.
- `playbooks/security_hardening.yml`: Temel güvenlik ayarlarını uygular (firewall, SSH, güncellemeler).
- `inventory`: Örnek envanter dosyası.
- `group_vars/`, `host_vars/`: Örnek değişken dosyaları.

## Kullanım

```bash
ansible-playbook -i inventory playbooks/nginx_setup.yml
```

## Gereksinimler

- Ansible 2.9+
- Hedef sunucularda SSH erişimi

## Katkı

PR’lar ve önerileriniz için issue açabilirsiniz.