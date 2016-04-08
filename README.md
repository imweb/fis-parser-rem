# fis-parser-rem

fis px自动转化成rem插件

## fis.conf

### CSS

```javascript
fis.match('*.css', {
    parser: [ 
        fis.plugin('rem')
    ]
})
```

### SCSS

```javascript
fis.match('*.scss', {
    rExt: '.css',
    parser: [ 
        fis.plugin('node-sass'),
        fis.plugin('rem')
    ]
})
```

## Usage

```css
body {
    border-top: 1px;
    border-bottom: 10px;
    padding: 10px; /* @norem */
    background-size: 10px 10px; /* @rem */
}
```

输出:

```css
body {
    border-top: 1px;
    border-bottom: 0.5557rem;
    padding: 10px;
    background-size: 0.5557rem 0.5557rem;
}
```

## Option

- rem `{Number}` 1rem=多少px `default` 18
- min `{Number}` 最小转化值 `default` 3
- exclude `{Array.<String>}` 忽略的样式 `default` `['width', 'height', 'background', 'background-size']`

## Question

- 如何忽略整个文件? 在文件头添加`/* @norem */`即可

