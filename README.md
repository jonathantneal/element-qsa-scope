# QSA Scope

> Return elements matching a selector relative to the current node

[![NPM Version][npm-img]][npm-url]
[![Build Status][cli-img]][cli-url]
[![Licensing][lic-image]][lic-url]
[![Changelog][log-image]][log-url]
[![Gitter Chat][git-image]][git-url]

[QSA Scope] is a polyfill for `:scope` support within QSA methods
([`#Element.querySelector`] and [`#Element.querySelectorAll`]).

```html
<ul>
    <li><a>Link</a>
        <ul>
            <li><a>Sublink</a></li>
        </ul>
    </li>
</ul>
<script>
li = document.querySelector('ul li')
</script>
```

By default, QSA methods return any element matching the CSS selector absolutely, similar to the element being matched by [`#Element.matches`].

```js
li.querySelector('li a'); // returns <a>Link</a> due to it technically matching
```

Adding scope is especially useful when traversing the DOM. 

```js
li.querySelector(':scope li a'); // returns <a>Sublink</a> due to its context
```

## Browser compatibility

| Browser           | Native Support | Polyfill Support |
| ----------------- | -------------- | ---------------- |
| Android           | ✘              | 2.2+             |
| Blackberry        | ✘              | 7+               |
| Chrome            | 27+            | 4 - 26           |
| Edge              | ✘              | 12+              |
| Firefox           | 32+            | 3.5 - 31         |
| Internet Explorer | ✘              | 8 - 11           |
| Opera             | 15+            | 10 - 14          |
| Opera Mini        | ✘              | 5+               |
| Safari (iOS)      | ✘              | 3.2 - 8.4        |
| Safari (MacOS)    | 6.2+           | 4 - 6            |

### Test Results

Additional [tests](http://codepen.io/jonneal/details/e20f8ddced5f5ed111a1e1f3044d4d47) were run against the latest 3 versions of browsers, including common outliers such as Internet Explorer 8+ and Safari 6+.

[Native Support](https://app.crossbrowsertesting.com/public/i76b092cd2b52b86/screenshots/zfe6755a18f932b6386b?size=small&type=chromeless)
[Polyfilled Support](https://app.crossbrowsertesting.com/public/i76b092cd2b52b86/screenshots/ze21b99d139fd4e51127?size=small&type=chromeless)

[QSA Scope]: http://github.com/jonathantneal/element-qsa-scope

[npm-url]: https://www.npmjs.com/package/element-qsa-scope
[npm-img]: https://img.shields.io/npm/v/element-qsa-scope.svg?style=flat-square
[cli-url]: https://travis-ci.org/jonathantneal/element-qsa-scope
[cli-img]: https://img.shields.io/travis/jonathantneal/element-qsa-scope.svg?style=flat-square
[lic-url]: LICENSE.md
[lic-image]: https://img.shields.io/npm/l/element-qsa-scope.svg?style=flat-square
[log-url]: CHANGELOG.md
[log-image]: https://img.shields.io/badge/changelog-md-blue.svg?style=flat-square
[git-url]: https://gitter.im/jonathantneal/element-qsa-scope
[git-image]: https://img.shields.io/badge/chat-gitter-blue.svg?style=flat-square

[`#Element.matches`]: https://dom.spec.whatwg.org/#dom-element-matches
[`#Element.querySelector`]: https://dom.spec.whatwg.org/#dom-parentnode-queryselector
[`#Element.querySelectorAll`]: https://dom.spec.whatwg.org/#dom-parentnode-queryselectorall
