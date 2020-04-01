## SCSS
=====
- SCSS is preprocessor for CSS
- sass compiles SCSS into CSS
- with SCSS, we can make CSS like a programming language.

### Development environment 
- npm -g 내꺼에서 절대로 안돌아감... sudo써도 안돼... 
- 고생하지 말고 nvm으로 node 설치하기! npm <<<< yarn 

```
yarn init
yarn add @babel/{register,core,preset-env}
yarn add gulp gulp-sass gulp-csso node-sass gulp-autoprefixer del -D
```
- +gulp del 도 추가설치 했었나.. 
### Add Babel 
- gulp can't understand new JS. 🤪
- Add script to package.json
```
"scripts": {
    "dev": "gulp dev"
  },

```
- .babelrc
```
{
  "presets": ["@babel/preset-env"]
}
```
- gulpfle.js to gulpfile.babel.js

### 🤩
```
yarn dev 
```

## SCSS Concepts
=====

### Variables
- css로 바꿀 필요없는 파일은 맨 앞에 _를 붙인다.
```
/* _variables.scss */
$bg: pink;
```
```
/* styles.scss */
@import "_variables";

body {
  color: $bg;
}
```
### Nesting
- Targeting specific elements under div class(= "box") elements
HTML
```
<body>
    <h2>Title</h2>
    <div class="box">
      <h2>Another title</h2>
    </div>
```
SCSS
```
/* targeting h2 tag */
h2 {
  color: $bg;
}

/* targeting h2 tag under <div class="box"> */
.box {
  h2 {
    color: P;
  }
}
```

### Mixin
- mixin에 argument 값을 보내면 css 결과값을 바꿔줘
- 상황에 따라 다르게 코딩하고 싶을 때 if else
_mixins.scss
```
@mixin link($word) {
  text-decoration: none;
  display: block;
  @if $word == "odd" {
    color: blue;
  } @else {
    color: red;
  }
}
```
styles.scss
```
@import "_mixins";

a {
  margin-bottom: 10px;

  &:nth-child(odd) {
    @include link("odd");
  }

  &:nth-child(even) {
    @include link("even");
  }
}
```

### extends
- 같은 코드를 중복하고 싶지 않을 때 사용
- extends the codes or reuse the code
- 예시 : link와 button을 extends로만 같게 보이게 하기!