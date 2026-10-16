# Публікація

Репозиторій уже готовий: коміт зроблено, `vercel.json` налаштовано.
Лишилось два кроки — обидва виконуються з вашого Mac.

## 1. GitHub

```bash
cd ~/Documents/anna-kovaleva        # куди розпакували архів
gh repo create anna-kovaleva --private --source=. --push
```

Немає `gh`? Тоді створіть порожній репозиторій на github.com і:

```bash
git remote add origin git@github.com:ВАШ_ЛОГІН/anna-kovaleva.git
git push -u origin main
```

## 2. Vercel

Найпростіше — через сайт:

1. vercel.com → **Add New** → **Project**
2. Import з GitHub, вибрати `anna-kovaleva`
3. Framework Preset: **Other**, решту не чіпати
4. **Deploy**

Збирати нічого не треба — це статика, `vercel.json` уже лежить у репозиторії.

Через CLI те саме:

```bash
npm i -g vercel
vercel --prod
```

## Після публікації

- Перевірити швидкість: pagespeed.web.dev, вкладка «Мобільні пристрої»
- Прив'язати домен: Vercel → Settings → Domains
- Кожен наступний `git push` оновлює сайт автоматично

## Що налаштовано у vercel.json

- `assets/` кешуються на рік — фото і відео не перезавантажуються
- `index.html` не кешується — правки видно одразу
- Заголовки безпеки: nosniff, referrer-policy, frame-options
