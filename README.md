# zPhantom a Zola Theme

A blogging theme based on [Phantom](https://html5up.net/phantom) by [HTML5Up](http://html5up.net).

Live at [zphantom.netlify.app/](https://zphantom.netlify.app/)

## How to Use It

Create a new Zola project, then move into the *theme/* folder

```bash
zola init cool-zola-project
cd cool-zola-project/theme
```

Now you need to clone this repository

```bash
git clone https://github.com/davidedelpapa/zphantom.git
cd ..
```

### Main structure

Now you can create an index by creating the following file:

```bash
touch ./content/_index.md
```

The following is an example *content/_index.md*:

```yaml
+++
title = "Demo Zola Theme"
date = 2021-02-01
template = "index.html"
[extra]
subtitle = "made with &#128154 by Davide Del Papa"
+++
Content of the Index Section
```

You can add pages on the main site, for example an "about" page

```bash
touch ./content/about.md
```

That can look like:

```yaml
+++
title = "About Us"
date = 2021-02-02
template = "page.html"
[extra]
image_path = "/images/pic.jpg"
+++
We are the best!
```

Pictures can be put in *static/images/*


### Blog

Next you need to create the structure for your blog

```bash
mkdir ./content/blog/
touch ./content/blog/_index.md
```

The index of the blog section can be as following:

```yaml
+++
title = "Blog Section"
date = 2021-02-10
template = "blog_section.html"
sort_by = "date"
+++
Content of the Blog Section
```

Now we can have also blog articles, our first for example:

```bash
touch ./content/blog/first-article.md
```

That can look like:

```yaml
+++
title = "First Article"
date = 2021-02-15
template = "page.html"
[extra]
image_path = " images/pic13.jpg "
summary = "Donec eget ex magna. Interdum et malesuada fames ..."
+++
Donec eget ex magna. Interdum et malesuada fames ac ante ipsum primis in faucibus. Pellentesque venenatis dolor imperdiet dolor mattis sagittis. Praesent rutrum sem diam, vitae egestas enim auctor sit amet.
```

Again, all images and covers can be put in *static/images/*

### config.toml

These are the variables that can be set in the *config.toml* to configure the theme:

```ini
zphantom_site_name = "zPhantom"
zphantom_site_owner = "Untitled"
zphantom_data_path = ""
```

- *zphantom_site_name*: This sets the title of the Site. 
A Logo can be put in *static/images/logo.svg*, best if 170x170 px, with white or transparent background.
- *zphantom_site_owner*: Site owner, for Copyright notice. Optionally with year(s) "2020-2021, Owner". An HTML link with `<a>` tag is supported.
- *zphantom_data_path*: data path where the *socials.json* can be found (info in the next section).

### Social Buttons

You can add social buttons at the footer of your site, by setting the *config.toml* variable `zphantom_data_path`, for example to:

```ini
zphantom_data_path = "content/socials.json"
```

And creating a *socilas.json* with a list of all socials.

In this scenario, a possible *socilas.json* can be:

```json
{
    "style": "style2",
    "socials": [{
            "id": 1,
            "icon": "brands fa-twitter",
            "caption": "Twitter",
            "link": "#"
        },
        {
            "id": 2,
            "icon": "brands fa-facebook-f",
            "caption": "Facebook",
            "link": "#"
        },
        {
            "id": 3,
            "icon": "brands fa-instagram",
            "caption": "Instagram",
            "link": "#"
        },
        {
            "id": 4,
            "icon": "brands fa-linkedin",
            "caption": "Linkedin",
            "link": "#"
        },
        {
            "id": 5,
            "icon": "brands fa-dribbble",
            "caption": "Dribble",
            "link": "#"
        },
        {
            "id": 6,
            "icon": "brands fa-github",
            "caption": "GitHub",
            "link": "#"
        },
        {
            "id": 7,
            "icon": "brands fa-500px",
            "caption": "500px",
            "link": "#"
        },
        {
            "id": 8,
            "icon": "solid fa-phone",
            "caption": "Phone",
            "link": "tel:001000000000"
        },
        {
            "id": 9,
            "icon": "brands fa-whatsapp",
            "caption": "WhatsApp",
            "link": "https://wa.me/10000000000?text=I'm%20interested"
        },
        {
            "id": 10,
            "icon": "solid fa-envelope",
            "caption": "Email",
            "link": "mailto:me@email.com"
        }
    ]
}
```

The `id` field is not mandatory.
