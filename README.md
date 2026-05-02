# Arslan Çelik Kapı

Astro tabanlı kurumsal site + Pages CMS içerik yönetimi.

## Teknoloji

- Astro (static output)
- Astro Content Collections
- Pages CMS (`.pages.yml`)
- GitHub Actions (Turhost FTP deploy)

## Lokal Çalıştırma

```bash
npm install
npm run dev
```

Build:

```bash
npm run build
```

## GitHub Repo Bağlantısı (Private)

Repo: `UlasCanSaru/arslan-celik-kapi`

```bash
git remote add origin https://github.com/UlasCanSaru/arslan-celik-kapi.git
git add .
git commit -m "Initial site + CMS setup"
git push -u origin master
```

## Pages CMS Kurulumu

1. `https://app.pagescms.org` adresine GitHub ile giriş yap.
2. GitHub App kurulumunda bu private repoyu seç.
3. Repo içinde `.pages.yml` hazır olduğu için içerikler otomatik görünecek.
4. Müşteriyi collaborator olarak davet et (GitHub hesabı olmasa da içerik düzenleyebilir).

## Turhost Otomatik Yayın (GitHub Actions)

Workflow dosyası: `.github/workflows/deploy-turhost.yml`

GitHub repo -> `Settings` -> `Secrets and variables` -> `Actions` altında şu secretları ekle:

- `TURHOST_FTP_SERVER`
- `TURHOST_FTP_USERNAME`
- `TURHOST_FTP_PASSWORD`
- `TURHOST_SERVER_DIR` (örnek: `/public_html/`)

Not: FTP port varsayılan `21` olarak ayarlanmıştır.

Deploy tetikleme:

- `master` branch'e her push sonrası otomatik deploy
- Pages CMS içinden `Siteyi Yayınla` action butonu
