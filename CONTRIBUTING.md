# Katkıda Bulunma Rehberi

Ansible Playbook Koleksiyonu'na katkıda bulunmak istediğiniz için teşekkürler! 🎉

## 🤝 Katkı Türleri

Aşağıdaki şekillerde katkıda bulunabilirsiniz:

- 🐛 **Hata raporları**: Bulduğunuz hataları bildirin
- 💡 **Özellik önerileri**: Yeni playbook veya iyileştirme önerileri
- 📝 **Dokümantasyon**: README, kod yorumları ve rehber iyileştirmeleri
- 🔧 **Kod katkıları**: Yeni playbook'lar veya mevcut olanların iyileştirilmesi

## 📋 Katkı Adımları

### 1. İssue Oluşturma

Yeni bir özellik veya hata düzeltmesi üzerinde çalışmadan önce:

1. [Mevcut issue'ları](https://github.com/aleynatila/ansible-playbook-collection/issues) kontrol edin
2. Benzer bir issue yoksa yeni bir issue açın
3. Issue'da ne yapmak istediğinizi detaylı bir şekilde açıklayın

### 2. Fork ve Clone

```bash
# Repository'yi fork edin (GitHub web arayüzünden)
# Sonra fork'unuzu local'e clone edin
git clone https://github.com/KULLANICI_ADINIZ/ansible-playbook-collection.git
cd ansible-playbook-collection

# Upstream remote ekleyin
git remote add upstream https://github.com/aleynatila/ansible-playbook-collection.git
```

### 3. Branch Oluşturma

```bash
# Ana branch'ten yeni bir feature branch oluşturun
git checkout -b feature/yeni-ozellik-adi
```

### 4. Geliştirme

#### Playbook Geliştirme Standartları

- **YAML Format**: 2 space indentation kullanın
- **Task İsimleri**: Açıklayıcı ve İngilizce task isimleri
- **Variables**: Anlamlı değişken isimleri
- **Comments**: Karmaşık logic'ler için yorum ekleyin
- **Idempotency**: Playbook'lar birden fazla çalıştırılabilir olmalı

#### Örnek Task Formatı

```yaml
- name: Install Nginx package
  package:
    name: nginx
    state: present
  become: yes
  tags:
    - nginx
    - packages

- name: Start and enable Nginx service
  service:
    name: nginx
    state: started
    enabled: yes
  become: yes
  tags:
    - nginx
    - services
```

#### Dizin Yapısı

```
playbooks/
├── yeni_playbook.yml           # Ana playbook
├── vars/
│   └── yeni_playbook_vars.yml  # Playbook özel değişkenler
└── templates/                  # Jinja2 templates (eğer varsa)
    └── config.j2
```

### 5. Test Etme

#### Syntax Kontrolü
```bash
# YAML syntax kontrolü
ansible-playbook --syntax-check playbooks/yeni_playbook.yml

# Lint kontrolü (eğer ansible-lint kuruluysa)
ansible-lint playbooks/yeni_playbook.yml
```

#### Dry Run
```bash
# Değişiklik yapmadan test etme
ansible-playbook -i inventory playbooks/yeni_playbook.yml --check
```

### 6. Commit ve Push

```bash
# Değişiklikleri stage edin
git add .

# Anlamlı commit mesajı yazın
git commit -m "feat: Yeni playbook eklendi - PostgreSQL kurulumu

- PostgreSQL 13 kurulumu ve konfigürasyonu
- Kullanıcı ve veritabanı oluşturma
- SSL konfigürasyonu
- Backup script'i eklendi"

# Branch'inizi push edin
git push origin feature/yeni-ozellik-adi
```

#### Commit Mesaj Standartları

Conventional Commits formatını kullanın:

- `feat:` - Yeni özellik
- `fix:` - Hata düzeltmesi
- `docs:` - Dokümantasyon değişiklikleri
- `style:` - Code formatting (logic değişikliği yok)
- `refactor:` - Code refactoring
- `test:` - Test ekleme/düzenleme
- `chore:` - Build scripts, dependencies vb.

### 7. Pull Request

1. GitHub'da repository'nize gidin
2. "Compare & pull request" butonuna tıklayın
3. PR template'ini doldurun:
   - **Başlık**: Kısa ve açıklayıcı
   - **Açıklama**: Ne yaptığınızı detaylı açıklayın
   - **Test**: Nasıl test ettiğinizi belirtin
   - **Screenshots**: Eğer UI değişikliği varsa

#### PR Template

```markdown
## Değişiklik Türü
- [ ] Hata düzeltmesi
- [ ] Yeni özellik
- [ ] Dokümantasyon güncellemesi
- [ ] Performance iyileştirmesi

## Açıklama
Bu PR'da ne yapıldığını açıklayın...

## Test Edildi
- [ ] Syntax kontrolü yapıldı
- [ ] Dry run testi başarılı
- [ ] Gerçek ortamda test edildi

## İlgili Issue
Fixes #123
```

## 📝 Code Review Süreci

1. **Otomatik kontroller**: GitHub Actions ile syntax ve lint kontrolleri
2. **Manuel review**: Maintainer'lar kodu inceleyecek
3. **Feedback**: Gerekli değişiklikler önerilecek
4. **Approval**: Onaylandıktan sonra merge edilecek

## 🏷️ Etiketleme

Issue'lara ve PR'lara uygun etiketler ekleyeceğiz:

- `bug` - Hata raporları
- `enhancement` - Yeni özellik önerileri
- `documentation` - Dokümantasyon
- `good first issue` - Yeni contributor'lar için
- `help wanted` - Yardım aranan konular

## ❓ Sorular

Herhangi bir sorunuz varsa:

1. [Discussions](https://github.com/aleynatila/ansible-playbook-collection/discussions) bölümünde soru sorun
2. Issue açın
3. Mevcut issue'lara yorum yapın

## 🙏 Teşekkürler

Katkılarınız için şimdiden teşekkür ederiz! Her türlü katkı değerlidir. 🎉
