# 자신의 프로젝트를 built한 과정을 기술

컴퓨터에 git 을 설치한 후 markdown 문법을 익히고,
github에 jerome000.github.io 이름의 repo를 생성함.
주소 복사 후 git clone으로 local과 연동하여 index.html 작성하고 
git add, git commit, git branch, git push 과정을 통해 원격 저장소에 반영함.
git push 과정에서 PAT가 필요하여 github settings 에서 생성하였고, 바탕화면 메모장에 저장해놓음.
이후 git push 과정에서 토큰을 활용하여 성공적으로 push 을 마침.
index.html 이 반영되어 github page가 생성됨.
컴퓨터에 jekyll 을 설치하고 jekyll new . --force 명령을 통해 blog 디렉토리에 jekyll 설치함.
jekyll serve로 localhost:4000 에 접속해 jekyll 사이트가 생성된 걸 확인하고 
_posts 폴더에 새 파일을 만들어 일기 형식으로 게시물을 저장함.
remote로 push하면서 항상 git status를 사용하여 놓치는 부분이 없도록 노력함.
테마를 입히는 과정에서 많은 힘을 들였음.. 새 디렉토리 만드는 일만 20번 넘게 하느라 거의 12시간 소모함..
원하는 테마를 입히려고 노력하였으나.. gem 파일에서인지 계속 오류가 나고 실패하여 lanyon 테마로 타협을 봄.
git clone 으로 테마를 받아와 적용시킴. 권한 오류가 계속 떠서 검색 결과 나온 git remote 명령으로 연동된 주소를 다시 옮김.
댓글 기능을 추가하고자 disqus 사이트에 로그인 하여 jerome000 사이트로 page를 만들고 universal code 를 찾느라 애를 먹음..
setting에서 열심히 찾은 결과 작은 창에서 universal code를 찾냐고 물어봐서 울먹이면서 네.. 대답함..
universal code를 레이아웃의 포스트에 추가하고 page url, identifier 이 포함된 주석을 주석해제함.
이후 이전에 적어놓았던 일기 등에 댓글 기능 추가함.

# Lanyon

Lanyon is an unassuming [Jekyll](http://jekyllrb.com) theme that places content first by tucking away navigation in a hidden drawer. It's based on [Poole](http://getpoole.com), the Jekyll butler.

![Lanyon](https://f.cloud.github.com/assets/98681/1825266/be03f014-71b0-11e3-9539-876e61530e24.png)
![Lanyon with open sidebar](https://f.cloud.github.com/assets/98681/1825267/be04a914-71b0-11e3-966f-8afe9894c729.png)


## Contents

- [Usage](#usage)
- [Options](#options)
  - [Sidebar menu](#sidebar-menu)
  - [Themes](#themes)
  - [Reverse layout](#reverse-layout)
- [Development](#development)
- [Author](#author)
- [License](#license)


## Usage

Lanyon is a theme built on top of [Poole](https://github.com/poole/poole), which provides a fully furnished Jekyll setup—just download and start the Jekyll server. See [the Poole usage guidelines](https://github.com/poole/poole#usage) for how to install and use Jekyll.


## Options

Lanyon includes some customizable options, typically applied via classes on the `<body>` element.


### Sidebar menu

Create a list of nav links in the sidebar by assigning each Jekyll page the correct layout in the page's [front-matter](http://jekyllrb.com/docs/frontmatter/).

```
---
layout: page
title: About
---
```

**Why require a specific layout?** Jekyll will return *all* pages, including the `atom.xml`, and with an alphabetical sort order. To ensure the first link is *Home*, we exclude the `index.html` page from this list by specifying the `page` layout.


### Themes

Lanyon ships with eight optional themes based on the [base16 color scheme](https://github.com/chriskempson/base16). Apply a theme to change the color scheme (mostly applies to sidebar and links).

![Lanyon with red theme](https://f.cloud.github.com/assets/98681/1825270/be065110-71b0-11e3-9ed8-9b8de753a4af.png)
![Lanyon with red theme and open sidebar](https://f.cloud.github.com/assets/98681/1825269/be05ec20-71b0-11e3-91ea-a9138ef07186.png)

There are eight themes available at this time.

![Available theme classes](https://f.cloud.github.com/assets/98681/1817044/e5b0ec06-6f68-11e3-83d7-acd1942797a1.png)

To use a theme, add any one of the available theme classes to the `<body>` element in the `default.html` layout, like so:

```html
<body class="theme-base-08">
  ...
</body>
```

To create your own theme, look to the Themes section of [included CSS file](https://github.com/poole/lanyon/blob/master/public/css/lanyon.css). Copy any existing theme (they're only a few lines of CSS), rename it, and change the provided colors.


### Reverse layout

![Lanyon with reverse layout](https://f.cloud.github.com/assets/98681/1825265/be03f2e4-71b0-11e3-89f1-360705524495.png)
![Lanyon with reverse layout and open sidebar](https://f.cloud.github.com/assets/98681/1825268/be056174-71b0-11e3-88c8-5055bca4307f.png)

Reverse the page orientation with a single class.

```html
<body class="layout-reverse">
  ...
</body>
```


### Sidebar overlay instead of push

Make the sidebar overlap the viewport content with a single class:

```html
<body class="sidebar-overlay">
  ...
</body>
```

This will keep the content stationary and slide in the sidebar over the side content. It also adds a `box-shadow` based outline to the toggle for contrast against backgrounds, as well as a `box-shadow` on the sidebar for depth.

It's also available for a reversed layout when you add both classes:

```html
<body class="layout-reverse sidebar-overlay">
  ...
</body>
```

### Sidebar open on page load

Show an open sidebar on page load by modifying the `<input>` tag within the `sidebar.html` layout to add the `checked` boolean attribute:

```html
<input type="checkbox" class="sidebar-checkbox" id="sidebar-checkbox" checked>
```

Using Liquid you can also conditionally show the sidebar open on a per-page basis. For example, here's how you could have it open on the homepage only:

```html
<input type="checkbox" class="sidebar-checkbox" id="sidebar-checkbox" {% if page.title =="Home" %}checked{% endif %}>
```

## Development

Lanyon has two branches, but only one is used for active development.

- `master` for development.  **All pull requests should be to submitted against `master`.**
- `gh-pages` for our hosted site, which includes our analytics tracking code. **Please avoid using this branch.**


## Author

**Mark Otto**
- <https://github.com/mdo>
- <https://twitter.com/mdo>


## License

Open sourced under the [MIT license](LICENSE.md).

<3
