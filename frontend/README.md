# About this repository

## Best practices

### Use multiple stylesheets, but be aware of them expanding beyond control | [source](https://www.belatrixsf.com/blog/best-practices-for-front-end-coding/)
Depending on the complexity of the design and the size of the site, sometimes it’s easier to make smaller, multiple stylesheets instead of a giant one. If you cross the line and end up having too many stylesheets it might be hard to follow and find where some styles are.

### Modularize styles for reuse | [source](https://www.belatrixsf.com/blog/best-practices-for-front-end-coding/)
CSS is built to allow styles to be reused, specifically with the use of classes. For this reason, styles assigned to a class should be modular and available to share across elements as necessary.

### Avoid units on zero values | [source](https://www.belatrixsf.com/blog/best-practices-for-front-end-coding/)
One way to easily cut down on the amount of CSS we write is to remove the unit from any zero value. A zero will always be a zero.

### Minify Images | [source](https://www.quora.com/What-are-front-end-development-guidelines-and-best-practices)
Images are taking at least 80% of the total page load time. We optimize image size and using lazy loading concepts (on demand loading) for images so that will not block required content. We are reducing number of DOM elements in pages.

### Avoiding @Import tag for CSS anywhere in website | [source](https://varvy.com/pagespeed/avoid-css-import.html)
CSS @import is notorious for loading every single imported file separately instead of paralleled. In other words, the browser of the visitor has to wait for every imported file to load instead of being able to load all your CSS files at once. This can heavily slow down your website, depending on the amount of CSS files you import. Also, when you use @import to include extra CSS files it creates extra HTTP requests, extra requests for the browser of your visitor to deal with.


## Image gallery

## Async API Data
