# MyProfile

Open source link page with custom filters to keep all your links in one place.

## Description

**MyProfile** is a all in one open-source links page with optionally categories filter to better link sort with infinite possibilities.

## Get started

This project was created on [NextJS](https://nextjs.org/) with Typescript and [Tailwind CSS](https://tailwindcss.com/).
Icons from [Phosphoricons](https://phosphoricons.com/) lib

1. Begin installing all dependencies:

```shell
npm run install
# or
yarn
```

2. Run dev command to load nextjs

```shell
npm run dev
```

3. Open local URL

```
http://localhost:3000
```

## Base structure

### Content location

All content are located in:

```shell
./src/lib/links.json
./src/lib/categories.json
./src/lib/user.json
```

#### Links

Links are array with the following structure:

| name       | type   | description                   |
| ---------- | ------ | ----------------------------- |
| label      | string | label visible on page         |
| categoryId | string | **optional** id from category |
| url        | string | url from link                 |

```json
[
  {
    "label": "Open-source link page",
    "categoryId": "projects",
    "url": "https://github.com/mushlihun/myprofile"
  }
]
```

#### Categories (optional)

Categories are optional to filter links, keep the array empty if you don't use.

| name  | type   | description           |
| ----- | ------ | --------------------- |
| label | string | label visible on page |
| id    | string | category identifier   |

```json
[
  {
    "label": "Projects",
    "id": "projects"
  }
]
```

#### User

The user file is all personal content from page, feel free to create/update new fields and use in your page.

| name        | type   | description                    |
| ----------- | ------ | ------------------------------ |
| fullname    | string | Page name                      |
| website     | string | **optional** website url       |
| role        | string | Your role                      |
| bio         | string | short description about you    |
| image       | string | profile image                  |
| socialLinks | object | object with social media links |

```json
[
  "fullname": "Mushlihun",
  "website": "https://github.com/mushlihun",
  "role": "UI Designer & Front-end dev",
  "bio": "UI Designer and Front-end developer, based on Brazil and working at Nuvemshop",
  "image": "https://avatars3.githubusercontent.com/u/6071639?s=400&u=6a0bc68ed0ccaadac5fdad016d3c357a7f7d1568&v=4",

   "socialLinks": {
    "twitter": "https://twitter.com/liihunn",
    "linkedin": "https://linkedin.com/id/mushlihun",
    "github": "https://github.com/mushlihun",
    "medium": "",
    "facebook": "",
    "youtube": "",
    "instagram": "www.instagram.com/mushlihun",
    "dribbble": ""
  }
]
```

## Themes

Here is the best part, you can use the current themes or create your own.
Use your creativity and/or tech skill to generate awesome themes.

We have 2 custom themes: **Alpha** e **Dracula** (based on [Dracula](https://draculatheme.com/contribute) dark theme from [Zeno Rocha](https://github.com/zenorocha))

Themes are located in:

```shell
./src/themes/[THEME_NAME]
```

To use your theme, after created you can import in `./src/index.tsx`

```ts
...
import { Alpha } from '@themes/alpha';
import { DATA } from '@lib/data';

export default function Home() {
  const { user } = DATA;
  return (
    <>
      ...
      <Alpha data={DATA} />
    </>
  );
}
```

## Environment variables - SEO

We have **Google Analytics 4** pre-configured in the project. And you don't need touch in code to setup, it simple:
To use local, create `.env.local` file at root project directory with your GA4 id:

```shell
# .env.local
NEXT_PUBLIC_GA4_ID=G-AAA0001112T
```

## Design

Some themes are availbale with [Figma](https://tinu.be/uilinks)