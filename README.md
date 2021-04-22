minifies all html files in the specified directory

uses [html-minifier](https://github.com/kangax/html-minifier) as the minifier

## setup

- download [tsk-minify-html.tar.xz](https://github.com/r1vn/tsk-minify-html/raw/master/tsk-minify-html.tar.xz) and unpack as `your-project/lib/tsk-minify-html`
- add a config entry to the manifest

example config: minifying all .html files in `build` directory

```
{
    module: 'lib/tsk-minify-html',
    config:
    {
        // path of the directory to look for files to minify in
        dir: 'build',
        // filter function applied to files in the dir
        filter: srcPath => srcPath.endsWith('.html'),
        // https://github.com/kangax/html-minifier#options-quick-reference
        // lib/tsk-minify-html/node_modules/html-minifier/README.md
        opts: 
        {
            collapseWhitespace: true,
            removeComments: true,
            removeTagWhitespace: true,
            minifyCSS: true,
            minifyJS: true
        }
    }
}
```