# Customizing this lab website

This version keeps the original Allan Lab data and images as demo content, but replaces the old visual system with a new responsive theme.

## 1. Edit the site identity

Open `_config.yml` and change:

- `title`, `short_title`, `lab_name`
- `institution`, `department`
- `email`, `address`
- `url` and `baseurl`

For the current GitHub project page, keep:

```yaml
url: "https://yumenglu417.github.io"
baseurl: "/labtest.github.io"
```

For a root site named `your-account.github.io`, use:

```yaml
url: "https://your-account.github.io"
baseurl: ""
```

## 2. Replace content

- Home page: `_pages/home.md`
- News: `_data/news.yml`
- Research cards: `_data/research.yml`
- Detailed research page: `_pages/research.md`
- Publications: `_data/publist.yml`
- Team: `_data/team_members.yml`
- Gallery: `_data/pictures_Leiden.yml`
- Openings: `_pages/openings.md`

## 3. Replace images

- Team portraits: `images/teampic/`
- Publication images: `images/pubpic/`
- Research images: `images/respic/`
- Gallery images: `images/picpic/Gallery/`
- Home hero image: `images/slider7001400/lab.jpg`
- Home group image: `images/slider7001400/Group2015_red.jpg`

## 4. Navigation

Edit `_data/navigation.yml`. All internal links use Jekyll's `relative_url` filter, so the site works both at a GitHub Pages root domain and under a project subpath.

## 5. Important

The original repository contained a `CNAME` file pointing to `www.allanlab.org`. It has been removed. Do not restore it unless you own and configure a custom domain.

## 6. Analytics (optional)

No analytics account is enabled by default. To use Google Analytics, set your own measurement ID in `_config.yml`:

```yaml
google_analytics: "G-XXXXXXXXXX"
```
