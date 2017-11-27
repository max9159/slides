# Webpack - css

prepare by Andy Chen

---

## What is loader

[Webpack custom loader](https://github.com/Asing1001/webpack-custom-loader)

---

```javascript
{
    test: /\.[s]*css$/,
    use: ExtractTextPlugin.extract({
        publicPath: "./",
        fallback: "style-loader",
        use: [
            {
                loader: "css-loader",
                options: {
                    root: "../../",
                    sourceMap: true
                }
            },
            {
                loader: "postcss-loader",
                options: {
                    sourceMap: true,
                    ident: "postcss",                    
                    plugins: loader => [require("autoprefixer")()]
                }
            },
            {
                loader: "sass-loader",
                options: { sourceMap: true }
            },
        ]
    })
}
```

---

## Demo

[webpack-custom-loader](https://github.com/Asing1001/webpack-custom-loader)

---

## [AutoPrefixer](https://github.com/postcss/autoprefixer)

Autoprefix css compatible with [Browsers List](https://github.com/ai/browserslist) in `package.json`.

```json
"browserslist": [
    "ie >= 10",
    "Chrome >= 31",
    "Firefox >= 35"
]
```

---

## Q & A

---

## Thank you